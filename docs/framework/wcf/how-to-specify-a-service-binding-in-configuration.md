---
title: 'Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885037f7-1c2b-4d7a-90d9-06b89be172f2
ms.openlocfilehash: 911c13b2a24c1906fe3da787460209f12296c993
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61928580"
---
# <a name="how-to-specify-a-service-binding-in-configuration"></a>Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration
In diesem Beispiel wird ein `ICalculator`-Vertrag für einen grundlegenden Rechnerdienst definiert. Der Dienst wird in die `CalculatorService`-Klasse implementiert. Anschließend wird der Endpunkt in der Datei "Web.config" konfiguriert, in der angegeben wird, dass der Dienst die <xref:System.ServiceModel.BasicHttpBinding> verwendet. Eine Beschreibung des Dienstes mithilfe von Code anstelle einer Konfigurations zu konfigurieren, finden Sie unter [Vorgehensweise: Angeben einer Dienstbindung im Code](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-code.md).  
  
 Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code. Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden. Allgemeiner gesagt ist es durch die Trennung von Bindungs- und Adressierungsinformationen vom Code möglich, diese zu ändern, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.  
  
 Alle folgenden Konfigurationsschritte durchgeführt werden kann mithilfe der [Configuration Editor-Tool (SvcConfigEditor.exe)](../../../docs/framework/wcf/configuration-editor-tool-svcconfigeditor-exe.md).  
  
 Die Quellkopie dieses Beispiels, finden Sie unter [Standardbindung](../../../docs/framework/wcf/samples/basicbinding.md).  
  
### <a name="to-specify-the-basichttpbinding-to-use-to-configure-the-service"></a>So geben Sie die BasicHttpBinding zur Konfiguration des Dienstes an  
  
1. Definieren Sie einen Dienstvertrag für den Diensttyp.  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#1)]  
  
2. Implementieren Sie den Dienstvertrag in einer Dienstklasse.  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#2)]  
  
    > [!NOTE]
    >  Die Adresse oder die Bindungsinformationen werden nicht in der Implementierung des Dienstes angegeben. Ebenso wenig muss Code geschrieben werden, um diese Informationen aus der Konfigurationsdatei abzurufen.  
  
3. Erstellen Sie eine Web.config-Datei, um einen Endpunkt für den `CalculatorService` zu konfigurieren, der die <xref:System.ServiceModel.WSHttpBinding> verwendet.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name=" CalculatorService" >  
            <endpoint   
            <!-- Leave the address blank to be populated by default -->  
            <!-- from the hosting environment,in this case IIS, so -->  
            <!-- the address will just be that of the IIS Virtual -->  
            <!-- Directory. -->  
                address=""   
            <!-- Specify the binding type -->  
                binding="wsHttpBinding"  
            <!-- Specify the binding configuration name for that -->  
            <!-- binding type. This is optional but useful if you -->  
            <!-- want to modify the properties of the binding. -->  
            <!-- The bindingConfiguration name Binding1 is defined -->  
            <!-- below in the bindings element. -->  
                bindingConfiguration="Binding1"  
                contract="ICalculator" />  
          </service>  
        </services>  
        <bindings>  
          <wsHttpBinding>  
            <binding name="Binding1">  
              <!-- Binding property values can be modified here. -->  
              <!-- See the next procedure. -->  
            </binding>  
          </wsHttpBinding>  
       </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. Erstellen Sie eine Service.svc-Datei, die die folgende Zeile enthält, und platzieren Sie sie im virtuellen IIS-Verzeichnis.  
  
    ```  
    <%@ServiceHost language=c# Service="CalculatorService" %>   
    ```  
  
### <a name="to-modify-the-default-values-of-the-binding-properties"></a>So ändern Sie die Standardwerte für die Bindungseigenschaften  
  
1. So ändern Sie eines der Standardeigenschaftswerte der <xref:System.ServiceModel.WSHttpBinding>, erstellen Sie einen neuen Namen der Bindung-Konfiguration – `<binding name="Binding1">` – in der [ \<WsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element und legen Sie die neuen Werte für die Attribute des der die Bindung in dieses Bindungselement. Wenn Sie beispielsweise die standardmäßigen Timeoutwerte für das Öffnen und Schließen von 1 Minute in 2 Minuten ändern möchten, fügen Sie Folgendes der Konfigurationsdatei hinzu:  
  
    ```xml  
    <wsHttpBinding>  
      <binding name="Binding1"  
               closeTimeout="00:02:00"  
               openTimeout="00:02:00">  
      </binding>  
    </wsHttpBinding>  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [Angeben einer Endpunktadresse](../../../docs/framework/wcf/specifying-an-endpoint-address.md)
