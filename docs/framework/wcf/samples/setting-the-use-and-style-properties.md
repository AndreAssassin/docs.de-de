---
title: Festlegen der Use- und Style-Eigenschaften - WCF-Beispiele
ms.date: 03/30/2017
ms.assetid: c09a0600-116f-41cf-900a-1b7e4ea4e300
ms.openlocfilehash: 64cf64cf5d53ef0dfb4bc38cf86f91c7acd2e5af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62007863"
---
# <a name="setting-the-use-and-style-properties"></a><span data-ttu-id="c2e9c-102">Festlegen der Use-Eigenschaft und der Style-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c2e9c-102">Setting the Use and Style Properties</span></span>

<span data-ttu-id="c2e9c-103">In diesem Beispiel wird die Verwendung der Use-Eigenschaft und der Style-Eigenschaft in <xref:System.ServiceModel.XmlSerializerFormatAttribute> und <xref:System.ServiceModel.DataContractFormatAttribute> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-103">This sample demonstrates how to use the Use and Style properties on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> and the <xref:System.ServiceModel.DataContractFormatAttribute>.</span></span> <span data-ttu-id="c2e9c-104">Diese Eigenschaften beeinflussen die Formatierung von Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-104">These properties affect how messages are formatted.</span></span> <span data-ttu-id="c2e9c-105">Standardmäßig wird der Nachrichtentext mit dem auf <xref:System.ServiceModel.OperationFormatStyle.Document> festgelegten Format formatiert.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-105">By default, the message body is formatted with the style set to <xref:System.ServiceModel.OperationFormatStyle.Document>.</span></span> <span data-ttu-id="c2e9c-106">Diese Einstellungen können entweder auf der Dienstvertragsebene oder der Vorgangsvertragsebene angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-106">These settings can be specified at either the service contract level or the operation contract level.</span></span>

> [!NOTE]
>  <span data-ttu-id="c2e9c-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="c2e9c-108">Die <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A>-Stileigenschaft bestimmt, wie die WSDL-Metadaten für den Dienst formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-108">The <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> style property determines how the WSDL metadata for the service is formatted.</span></span> <span data-ttu-id="c2e9c-109">Mögliche Werte sind <xref:System.ServiceModel.OperationFormatStyle.Document> und <xref:System.ServiceModel.OperationFormatStyle.Rpc>.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-109">Possible values are <xref:System.ServiceModel.OperationFormatStyle.Document>, and <xref:System.ServiceModel.OperationFormatStyle.Rpc>.</span></span> <span data-ttu-id="c2e9c-110">RPC bedeutet, dass die WSDL-Darstellung von Nachrichten, die für einen Vorgang ausgetauscht wurden, Parameter entsprechend einem Remoteprozeduraufruf enthält.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-110">RPC means that the WSDL representation of messages exchanged for an operation contains parameters as if it were a remote procedure call.</span></span> <span data-ttu-id="c2e9c-111">Nachfolgend finden Sie ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c2e9c-111">The following is an example.</span></span>

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="n1" type="xsd:double"/>
  <wsdl:part name="n2" type="xsd:double"/>
</wsdl:message>
```

<span data-ttu-id="c2e9c-112">Das Format auf <xref:System.ServiceModel.OperationFormatStyle.Document> festzulegen, bedeutet, dass die WSDL-Darstellung ein einzelnes Element enthält, das das gegen einen Vorgang ausgetauschte Dokument darstellt. Dies ist im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-112">Setting the style to <xref:System.ServiceModel.OperationFormatStyle.Document> means that the WSDL representation contains a single element that represents the document that is exchanged for an operation as shown in the following example.</span></span>

```xml
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">
  <wsdl:part name="parameters" element="tns:Add"/>
</wsdl:message>
```

<span data-ttu-id="c2e9c-113">Die <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A>-Eigenschaft bestimmt das Format der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-113">The <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> property determines the format of the message.</span></span> <span data-ttu-id="c2e9c-114">Mögliche Werte sind <xref:System.ServiceModel.OperationFormatUse.Literal> und <xref:System.ServiceModel.OperationFormatUse.Encoded>. Der Standardwert ist <xref:System.ServiceModel.OperationFormatUse.Literal>.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-114">Possible values are <xref:System.ServiceModel.OperationFormatUse.Literal> and <xref:System.ServiceModel.OperationFormatUse.Encoded>; the default value is <xref:System.ServiceModel.OperationFormatUse.Literal>.</span></span> <span data-ttu-id="c2e9c-115">Literal bedeutet, dass die Nachricht eine Literalinstanz des Schemas in der WSDL ist, wie im folgenden Dokument-/Literal-Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-115">Literal means that the message is a literal instance of the schema in the WSDL as shown in the following Document/ Literal example.</span></span>

```xml
<Add xmlns="http://Microsoft.ServiceModel.Samples">
  <n1>100</n1>
  <n2>15.99</n2>
</Add>
```

<span data-ttu-id="c2e9c-116">Encoded bedeutet, dass die Schemen in der WSDL abstrakte Spezifikationen sind, die gemäß den Regeln in SOAP 1.1, Abschnitt 5 codiert werden.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-116">Encoded means that the schemas in the WSDL are abstract specifications that are encoded according to the rules found in SOAP 1.1 section 5.</span></span> <span data-ttu-id="c2e9c-117">Es folgt ein RPC/Encoded-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-117">The following is an RPC/Encoded example.</span></span>

```xml
<q1:Add xmlns:q1="http://Microsoft.ServiceModel.Samples">
  <n1 xsi:type="xsd:double" xmlns="">100</n1>
  <n2 xsi:type="xsd:double" xmlns="">15.99</n2>
</q1:Add>
```

<span data-ttu-id="c2e9c-118">WS-I Basic Profile 1.0 verbietet die Verwendung von <xref:System.ServiceModel.OperationFormatUse.Encoded>. Sie sollten dies daher nur verwenden, wenn es aufgrund von älteren Diensten erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-118">The WS-I Basic Profile 1.0 prohibits the use of <xref:System.ServiceModel.OperationFormatUse.Encoded> and you should only use it when required by legacy services.</span></span> <span data-ttu-id="c2e9c-119">Das `Encoded`-Nachrichtenformat ist nur bei Verwendung von XmlSerializer verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-119">The `Encoded` message format is only available when using the XmlSerializer.</span></span>

<span data-ttu-id="c2e9c-120">Damit Sie die gesendeten und empfangenen Nachrichten anzeigen können, in diesem Beispiel basiert die [Ablaufverfolgung und Nachrichtenprotokollierung](tracing-and-message-logging.md).</span><span class="sxs-lookup"><span data-stu-id="c2e9c-120">To allow you to see the messages being sent and received, this sample is based on the [Tracing and Message Logging](tracing-and-message-logging.md).</span></span> <span data-ttu-id="c2e9c-121">Die Dienstkonfiguration und der Quellcode wurden geändert, um Ablaufverfolgung und Nachrichtenprotokollierung zu aktivieren und zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-121">The service configuration and source code have been modified to enable and utilize tracing and message logging.</span></span> <span data-ttu-id="c2e9c-122">Außerdem wurde <xref:System.ServiceModel.WSHttpBinding> ohne Sicherheit konfiguriert, sodass protokollierte Nachrichten in einem unverschlüsselten Format angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-122">In addition, the <xref:System.ServiceModel.WSHttpBinding> has been configured without security, so the logged messages can be viewed in an unencrypted format.</span></span> <span data-ttu-id="c2e9c-123">Die resultierenden Ablaufverfolgungsprotokolle (System.ServiceModel.e2e und Message.log) sollten angezeigt werden, mithilfe der [Service Trace Viewer-Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c2e9c-123">The resulting trace logs (System.ServiceModel.e2e and Message.log) should be viewed by using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="c2e9c-124">Die Ablaufverfolgungen sind so konfiguriert, dass sie im Ordner C:\LOGS erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-124">The traces are configured to be created in the C:\LOGS folder.</span></span> <span data-ttu-id="c2e9c-125">Erstellen Sie den Ordner vor dem Ausführen des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-125">Create the folder before running the sample.</span></span> <span data-ttu-id="c2e9c-126">Wählen Sie zum Anzeigen von Inhalt im Trace Viewer-Tool **Nachrichten** in der linken und rechten Bereich des Tools.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-126">To view message contents in the Trace Viewer tool, select **Messages** in both the left and the right panes of the tool.</span></span>

<span data-ttu-id="c2e9c-127">Im folgenden Code wird der Dienstvertrag veranschaulicht, wobei die <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A>-Eigenschaft auf <xref:System.ServiceModel.OperationFormatUse> festgelegt und das Format des Nachrichtentexts vom Standard (<xref:System.ServiceModel.OperationFormatStyle>) in <xref:System.ServiceModel.OperationFormatStyle.Document> geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-127">The following code shows the service contract with the <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> property set to <xref:System.ServiceModel.OperationFormatUse> and the format of the message body changed from the default <xref:System.ServiceModel.OperationFormatStyle> to <xref:System.ServiceModel.OperationFormatStyle.Document>.</span></span>

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),
XmlSerializerFormat(Style = OperationFormatStyle.Rpc, 
                                 Use = OperationFormatUse.Encoded)]
public interface IUseAndStyleCalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="c2e9c-128">Um den Unterschied zwischen den unterschiedlichen Einstellungen für <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> und <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A> zu verdeutlichen, ändern Sie sie im Dienst, generieren Sie den Client erneut, führen Sie das Beispiel aus, und betrachten Sie dann die Datei "c:\logs\message.logs" im Service Trace Viewer-Tool.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-128">To see the difference between the different <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> and <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A> settings, modify them in the service, regenerate the client, run the sample, and examine the c:\logs\message.logs file with the Service Trace Viewer tool.</span></span> <span data-ttu-id="c2e9c-129">Beachten Sie die Auswirkungen auf die Metadaten auch anhand `http://localhost/ServiceModelSamples/service.svc?wsdl`.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-129">Also observe the impact on the metadata by viewing `http://localhost/ServiceModelSamples/service.svc?wsdl`.</span></span> <span data-ttu-id="c2e9c-130">Die Metadaten für Dienste sind normalerweise in mehrere Seiten untergeteilt.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-130">The metadata for services is typically broken up into multiple pages.</span></span> <span data-ttu-id="c2e9c-131">WSDL-Hauptseite enthält die WSDL-Bindungen, aber anzeigen `http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0` um die Nachrichtendefinitionen.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-131">The main wsdl page contains the WSDL bindings, but view `http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0` to observe the message definitions.</span></span>

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c2e9c-132">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="c2e9c-132">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="c2e9c-133">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c2e9c-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="c2e9c-134">Erstellen Sie zum Protokollieren von Nachrichten das Verzeichnis C:\LOGS.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-134">Create a C:\LOGS directory for logging messages.</span></span> <span data-ttu-id="c2e9c-135">Weisen Sie dem Benutzer Network Service die Schreibberechtigung für dieses Verzeichnis zu.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-135">Give the user Network Service write permissions for this directory.</span></span>

3. <span data-ttu-id="c2e9c-136">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-136">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="c2e9c-137">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c2e9c-137">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2e9c-138">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c2e9c-139">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-139">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="c2e9c-140">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c2e9c-141">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c2e9c-141">This sample is located in the following directory.</span></span>
> 
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\UseAndStyle`