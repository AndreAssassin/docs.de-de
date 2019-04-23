---
title: XMLSerializer-Beispiel
ms.date: 03/30/2017
ms.assetid: 7d134453-9a35-4202-ba77-9ca3a65babc3
ms.openlocfilehash: 70c6eb07780296672d663c7d5b9259192b189aad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59769644"
---
# <a name="xmlserializer-sample"></a>XMLSerializer-Beispiel
Dieses Beispiel veranschaulicht die Serialisierung und Deserialisierung von Typen, die mit dem <xref:System.Xml.Serialization.XmlSerializer> kompatibel sind. Das Standardformatierungsprogramm für die Windows Communication Foundation (WCF) ist die <xref:System.Runtime.Serialization.DataContractSerializer> Klasse. Die <xref:System.Xml.Serialization.XmlSerializer>-Klasse kann auch zum Serialisieren und Deserialisieren von Typen verwendet werden, wenn die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse nicht verwendet werden kann. Dies ist oft der Fall, wenn die präzise Steuerung von XML wichtig ist &amp;#8211; beispielsweise, wenn es sich bei einem Datenelement um ein XML-Attribut und nicht um ein XML-Element handeln muss. Darüber hinaus die <xref:System.Xml.Serialization.XmlSerializer> oft automatisch ausgewählt, wenn Sie Clients für nicht-WCF-Dienste zu erstellen.  
  
 In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Das <xref:System.ServiceModel.ServiceContractAttribute> und das <xref:System.ServiceModel.XmlSerializerFormatAttribute> müssen wie im folgenden Beispielcode gezeigt auf die Schnittstelle angewendet werden.  
  
```csharp  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
public interface IXmlSerializerCalculator  
{  
    [OperationContract]  
    ComplexNumber Add(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2);  
}  
```  
  
 Die öffentlichen Member der `ComplexNumber`-Klasse werden vom <xref:System.Xml.Serialization.XmlSerializer> als XML-Attribute serialisiert. Der <xref:System.Runtime.Serialization.DataContractSerializer> kann nicht zum Erstellen solcher XML-Instanzen verwendet werden.  
  
```csharp  
public class ComplexNumber  
{  
    private double real;  
    private double imaginary;  
  
    [XmlAttribute]  
    public double Real  
    {  
        get { return real; }  
        set { real = value; }  
    }  
  
    [XmlAttribute]  
    public double Imaginary  
    {  
        get { return imaginary; }  
        set { imaginary = value; }  
    }  
  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
    public ComplexNumber()  
    {  
        this.Real = 0;  
        this.Imaginary = 0;  
    }  
  
}  
```  
  
 Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück. Dabei werden Werte vom Typ `ComplexNumber` akzeptiert und zurückgegeben.  
  
```csharp  
public class XmlSerializerCalculatorService : IXmlSerializerCalculator  
{  
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)  
    {  
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +  
                                                      n2.Imaginary);  
    }  
    …  
}  
```  
  
 Die Clientimplementierung verwendet ebenfalls komplexe Zahlen. Sowohl der Dienstvertrag und die Datentypen sind in der Quelldatei generatedClient.cs, die vom generiert wurde, definiert der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) aus Dienstmetadaten. Svcutil.exe kann erkennen, wenn ein Vertrag nicht mit dem <xref:System.Runtime.Serialization.DataContractSerializer> serialisierbar ist, und gibt in diesem Fall `XmlSerializable`-Typen aus. Wenn Sie die Verwendung des <xref:System.Xml.Serialization.XmlSerializer> erzwingen möchten, können Sie die Befehlsoption "/serializer:XmlSerializer" (XmlSerializer verwenden) an das Tool "Svcutil.exe" übergeben.  
  
```csharp  
// Create a client.  
XmlSerializerCalculatorClient client = new  
                         XmlSerializerCalculatorClient();  
  
// Call the Add service operation.  
ComplexNumber value1 = new ComplexNumber();  
value1.Real = 1;  
value1.Imaginary = 2;  
ComplexNumber value2 = new ComplexNumber();  
value2.Real = 3;  
value2.Imaginary = 4;  
ComplexNumber result = client.Add(value1, value2);  
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",  
    value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,   
    result.Real, result.Imaginary);  
    …  
}  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```console  
Add(1 + 2i, 3 + 4i) = 4 + 6i  
Subtract(1 + 2i, 3 + 4i) = -2 + -2i  
Multiply(2 + 3i, 4 + 7i) = -13 + 26i  
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 1.41379310344828i  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\Interop\XmlSerializer`  
