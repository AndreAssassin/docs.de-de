---
title: 'Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 885037f7-1c2b-4d7a-90d9-06b89be172f2
ms.openlocfilehash: 245fe50ed5a80c51163652defb642cebefd55dbd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184022"
---
# <a name="how-to-specify-a-service-binding-in-configuration"></a>Vorgehensweise: Angeben einer Dienstbindung in einer Konfiguration
In diesem Beispiel wird ein `ICalculator`-Vertrag für einen grundlegenden Rechnerdienst definiert. Der Dienst wird in die `CalculatorService`-Klasse implementiert. Anschließend wird der Endpunkt in der Datei "Web.config" konfiguriert, in der angegeben wird, dass der Dienst die <xref:System.ServiceModel.BasicHttpBinding> verwendet. Eine Beschreibung zum Konfigurieren dieses Dienstes mithilfe von Code anstelle einer Konfiguration finden Sie unter [Gewusst wie: Angeben einer Dienstbindung im Code](how-to-specify-a-service-binding-in-code.md).  
  
 Normalerweise ist es die bewährte Methode, die Bindung anzugeben und die Informationen deklarativ in der Konfiguration anzusprechen anstatt imperativ im Code. Die Definition von Endpunkten im Code ist normalerweise nicht geeignet, da die Bindungen und Adressen für einen bereitgestellten Dienst sich in der Regel von denen unterscheiden, die während der Entwicklung des Diensts verwendet werden. Allgemeiner gesagt ist es durch die Trennung von Bindungs- und Adressierungsinformationen vom Code möglich, diese zu ändern, ohne die Anwendung neu kompilieren oder erneut bereitstellen zu müssen.  
  
 Alle folgenden Konfigurationsschritte können mit dem [Configuration Editor Tool (SvcConfigEditor.exe)](configuration-editor-tool-svcconfigeditor-exe.md)ausgeführt werden.  
  
 Die Quellkopie dieses Beispiels finden Sie unter [BasicBinding](./samples/basicbinding.md).  
  
## <a name="to-specify-the-basichttpbinding-to-use-to-configure-the-service"></a>So geben Sie die BasicHttpBinding zur Konfiguration des Dienstes an  
  
1. Definieren Sie einen Dienstvertrag für den Diensttyp.  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#1)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#1)]  
  
2. Implementieren Sie den Dienstvertrag in einer Dienstklasse.  
  
     [!code-csharp[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_configureservicebinding/cs/source.cs#2)]
     [!code-vb[C_HowTo_ConfigureServiceBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_configureservicebinding/vb/source.vb#2)]  
  
    > [!NOTE]
    > Die Adresse oder die Bindungsinformationen werden nicht in der Implementierung des Dienstes angegeben. Ebenso wenig muss Code geschrieben werden, um diese Informationen aus der Konfigurationsdatei abzurufen.  
  
3. Erstellen Sie eine Web.config-Datei, um einen Endpunkt für den `CalculatorService` zu konfigurieren, der die <xref:System.ServiceModel.WSHttpBinding> verwendet.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <services>  
          <service name=" CalculatorService" >  

            <!-- Leave the address blank to be populated by default -->
            <!-- from the hosting environment,in this case IIS, so -->
            <!-- the address will just be that of the IIS Virtual -->
            <!-- Directory. -->

            <!-- Specify the binding configuration name for that -->
            <!-- binding type. This is optional but useful if you -->
            <!-- want to modify the properties of the binding. -->
            <!-- The bindingConfiguration name Binding1 is defined -->
            <!-- below in the bindings element. -->
            <endpoint
                address=""
                binding="wsHttpBinding"  
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
  
## <a name="to-modify-the-default-values-of-the-binding-properties"></a>So ändern Sie die Standardwerte für die Bindungseigenschaften  
  
1. Um einen der Standardeigenschaftswerte <xref:System.ServiceModel.WSHttpBinding>des zu ändern, `<binding name="Binding1">` erstellen Sie einen neuen Bindungskonfigurationsnamen - innerhalb des [ \<wsHttpBinding>-Elements,](../configure-apps/file-schema/wcf/wshttpbinding.md) und legen Sie die neuen Werte für die Attribute der Bindung in diesem Bindungselement fest. Wenn Sie beispielsweise die standardmäßigen Timeoutwerte für das Öffnen und Schließen von 1 Minute in 2 Minuten ändern möchten, fügen Sie Folgendes der Konfigurationsdatei hinzu:  
  
    ```xml  
    <wsHttpBinding>  
      <binding name="Binding1"  
               closeTimeout="00:02:00"  
               openTimeout="00:02:00">  
      </binding>  
    </wsHttpBinding>  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](using-bindings-to-configure-services-and-clients.md)
- [Angeben einer Endpunktadresse](specifying-an-endpoint-address.md)
