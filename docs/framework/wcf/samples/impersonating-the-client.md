---
title: Durchführen eines Identitätswechsels für den Client
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, impersonation sample
- Impersonating the Client Sample [Windows Communication Foundation]
- impersonation, Windows Communication Foundation sample
ms.assetid: 8bd974e1-90db-4152-95a3-1d4b1a7734f8
ms.openlocfilehash: 61befdcaf1381120dba6f72ba592dade09d0490a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968342"
---
# <a name="impersonating-the-client"></a>Durchführen eines Identitätswechsels für den Client
Das Beispiel für einen Identitätswechsel veranschaulicht, wie die Identität der Aufruferanwendung vom Dienst angenommen wird, sodass der Dienst im Namen des Aufrufers auf Systemressourcen zugreifen kann.  
  
 Dieses Beispiel basiert auf dem [Self-Host-](../../../../docs/framework/wcf/samples/self-host.md) Beispiel. Die Dienst-und Client Konfigurationsdateien sind identisch mit denen des [Self-Host-](../../../../docs/framework/wcf/samples/self-host.md) Beispiels.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Im folgenden Codebeispiel wird gezeigt, dass der Servicecode so geändert wurde, dass die `Add`-Methode für den Dienst die Identität des Aufrufers mithilfe von <xref:System.ServiceModel.OperationBehaviorAttribute> annimmt.  
  
```csharp
[OperationBehavior(Impersonation = ImpersonationOption.Required)]  
public double Add(double n1, double n2)  
{  
    double result = n1 + n2;  
    Console.WriteLine("Received Add({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 Demzufolge wird der Sicherheitskontext des ausgeführten Threads so geändert, dass die Identität des Aufrufers angenommen wird, bevor die `Add`-Methode eingegeben und auf das Beenden der Methode zurückgesetzt wird.  
  
 Die im folgenden Codebeispiel veranschaulichte `DisplayIdentityInformation`-Methode ist eine Hilfsfunktion, mit der die Identität des Aufrufers dargestellt wird.  
  
```csharp
static void DisplayIdentityInformation()  
{  
    Console.WriteLine("\t\tThread Identity            :{0}",  
         WindowsIdentity.GetCurrent().Name);  
    Console.WriteLine("\t\tThread Identity level  :{0}",   
         WindowsIdentity.GetCurrent().ImpersonationLevel);  
    Console.WriteLine("\t\thToken                     :{0}",  
         WindowsIdentity.GetCurrent().Token.ToString());  
    return;  
}  
```  
  
 Im folgenden Codebeispiel wird gezeigt, dass die `Subtract`-Methode für den Dienst die Identität des Aufrufers mithilfe von imperativen Aufrufen annimmt.  
  
```csharp
public double Subtract(double n1, double n2)  
{  
    double result = n1 - n2;  
    Console.WriteLine("Received Subtract({0},{1})", n1, n2);  
    Console.WriteLine("Return: {0}", result);  
    Console.WriteLine("Before impersonating");  
    DisplayIdentityInformation();  
  
    if (ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Impersonation ||  
        ServiceSecurityContext.Current.WindowsIdentity.ImpersonationLevel == TokenImpersonationLevel.Delegation)  
    {  
        // Impersonate.  
        using (ServiceSecurityContext.Current.WindowsIdentity.Impersonate())  
        {  
            // Make a system call in the caller's context and ACLs   
            // on the system resource are enforced in the caller's context.   
            Console.WriteLine("Impersonating the caller imperatively");  
            DisplayIdentityInformation();  
        }  
    }  
    else  
    {  
        Console.WriteLine("ImpersonationLevel is not high enough to perform this operation.");  
    }  
  
    Console.WriteLine("After reverting");  
    DisplayIdentityInformation();  
    return result;  
}  
```  
  
 Beachten Sie, dass in diesem Fall kein Identitätswechsel für den gesamten Aufruf, sondern nur für einen Teil des Aufrufs vorgenommen wurde. Im Allgemeinen empfiehlt es sich, einen Identitätswechsel für den kleinsten Bereich und nicht für den ganzen Vorgang durchzuführen.  
  
 Die anderen Methoden nehmen die Identität des Aufrufers nicht an.  
  
 Der Clientcode wurde geändert, um die Identitätswechselebene auf <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> festzulegen. Der Client gibt die vom Dienst zu verwendende Identitätswechselebene durch die <xref:System.Security.Principal.TokenImpersonationLevel>-Enumeration an. Die Enumeration unterstützt die folgenden Werte: <xref:System.Security.Principal.TokenImpersonationLevel.None>, <xref:System.Security.Principal.TokenImpersonationLevel.Anonymous>, <xref:System.Security.Principal.TokenImpersonationLevel.Identification>, <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> und <xref:System.Security.Principal.TokenImpersonationLevel.Delegation>. Um beim Zugreifen auf die Systemressource auf dem lokalen Rechner, der mit Windows-Zugriffssteuerungslisten geschützt ist, eine Zugriffsprüfung durchzuführen, muss die Identitätswechselebene auf <xref:System.Security.Principal.TokenImpersonationLevel.Impersonation> festgelegt sein, wie im folgenden Codebeispiel gezeigt.  
  
```csharp
// Create a client with given client endpoint configuration  
CalculatorClient client = new CalculatorClient();  
  
client.ClientCredentials.Windows.AllowedImpersonationLevel = TokenImpersonationLevel.Impersonation;  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt. Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.  
  
> [!NOTE]
> Der Dienst muss entweder unter einem Administrator Konto ausgeführt werden, oder das Konto, unter dem er ausgeführt wird, muss `http://localhost:8000/ServiceModelSamples` über Rechte zum Registrieren des URIs bei der HTTP-Ebene verfügen. Solche Rechte können durch das Einrichten einer [Namespace Reservierung](https://go.microsoft.com/fwlink/?LinkId=95012) mit dem [Tool Httpcfg. exe](https://go.microsoft.com/fwlink/?LinkId=95010)erteilt werden.  
  
> [!NOTE]
> Auf Computern mit [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] wird der Identitätswechsel nur unterstützt, wenn die Host.exe-Anwendung über eine Berechtigung zum Identitätswechsel verfügt. (Standardmäßig verfügen nur Administratoren über diese Berechtigung.) Um dieses Privileg einem Konto hinzuzufügen, unter dem der-Dienst ausgeführt wird, wechseln Sie zu **Verwaltung**, öffnen Sie **lokale Sicherheitsrichtlinie**, öffnen Sie **lokale Richtlinien**, klicken Sie auf Zuweisen von **Benutzerrechten**, und wählen Sie dann Identität eines Clients annehmen aus.  **Authentifizierung** , und doppelklicken Sie auf **Eigenschaften** , um einen Benutzer oder eine Gruppe hinzuzufügen.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
4. Wenn Sie veranschaulichen möchten, dass der Dienst die Identität des Aufrufers annimmt, führen Sie den Client auf einem anderen Konto als dem Konto aus, auf dem der Dienst ausgeführt wird. Geben Sie dazu an der Eingabeaufforderung Folgendes ein:  
  
    ```  
    runas /user:<machine-name>\<user-name> client.exe  
    ```  
  
     Sie werden anschließend zur Eingabe eines Kennworts aufgefordert. Geben Sie das Kennwort für das Konto ein, das Sie vorher angegeben haben.  
  
5. Wenn Sie den Client ausführen, beachten Sie die Identität vor und nach dem Ausführen mit unterschiedlichen Anmeldeinformationen.  
