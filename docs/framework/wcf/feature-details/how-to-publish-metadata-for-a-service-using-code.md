---
title: 'Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über den Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 51407e6d-4d87-42d5-be7c-9887b8652006
ms.openlocfilehash: 5f60bcdb02f61d39711115b07ba989229e39c28c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929133"
---
# <a name="how-to-publish-metadata-for-a-service-using-code"></a><span data-ttu-id="45a13-102">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über den Code</span><span class="sxs-lookup"><span data-stu-id="45a13-102">How to: Publish Metadata for a Service Using Code</span></span>
<span data-ttu-id="45a13-103">Dies ist eines von zwei Themen zur Vorgehensweise, in denen das Veröffentlichen von Metadaten für einen Windows Communication Foundation (WCF)-Dienst erörtert wird.</span><span class="sxs-lookup"><span data-stu-id="45a13-103">This is one of two how-to topics that discuss publishing metadata for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="45a13-104">Es gibt zwei Möglichkeiten, wie ein Dienst Metadaten veröffentlichen kann: mit einer Konfigurationsdatei und mit Code.</span><span class="sxs-lookup"><span data-stu-id="45a13-104">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="45a13-105">In diesem Thema wird das Veröffentlichen von Metadaten für einen Dienst mithilfe von Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="45a13-105">This topic shows how to publish metadata for a service using a code.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="45a13-106">In diesem Thema wird das Veröffentlichen von Metadaten auf unsichere Weise dargestellt.</span><span class="sxs-lookup"><span data-stu-id="45a13-106">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="45a13-107">Jeder Client kann Metadaten vom Dienst abrufen.</span><span class="sxs-lookup"><span data-stu-id="45a13-107">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="45a13-108">Informationen zum sicheren Veröffentlichen von Metadaten für einen Dienst</span><span class="sxs-lookup"><span data-stu-id="45a13-108">If you require your service to publish metadata in a secure manner.</span></span> <span data-ttu-id="45a13-109">siehe [Benutzerdefinierter sicherer Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="45a13-109">see [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="45a13-110">Weitere Informationen zum Veröffentlichen von Metadaten in einer Konfigurationsdatei finden [Sie unter Gewusst wie: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurations](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)Datei.</span><span class="sxs-lookup"><span data-stu-id="45a13-110">For more information about publishing metadata in a configuration file, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span> <span data-ttu-id="45a13-111">Die Veröffentlichung von Metadaten ermöglicht Clients, Metadaten über eine WS-Transfer-GET-Anforderung oder eine HTTP/GET-Anforderung mithilfe einer `?wsdl`-Abfragezeichenfolge abzurufen.</span><span class="sxs-lookup"><span data-stu-id="45a13-111">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="45a13-112">Erstellen Sie einen grundlegenden WCF-Dienst, um sicherzustellen, dass der Code funktioniert.</span><span class="sxs-lookup"><span data-stu-id="45a13-112">To be sure that the code is working you must create a basic WCF service.</span></span> <span data-ttu-id="45a13-113">Im folgenden Code wird ein grundlegender, selbst gehosteter Dienst bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="45a13-113">A basic self-hosted service is provided in the following code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#0)]
 [!code-vb[htPublishMetadataCode#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#0)]  
  
### <a name="to-publish-metadata-in-code"></a><span data-ttu-id="45a13-114">So veröffentlichen Sie Metadaten im Code</span><span class="sxs-lookup"><span data-stu-id="45a13-114">To publish metadata in code</span></span>  
  
1. <span data-ttu-id="45a13-115">Instanziieren Sie in der Hauptmethode einer Konsolenanwendung ein <xref:System.ServiceModel.ServiceHost>-Objekt, indem Sie den Diensttyp und die Basisadresse übergeben.</span><span class="sxs-lookup"><span data-stu-id="45a13-115">Within the main method of a console application, instantiate a <xref:System.ServiceModel.ServiceHost> object by passing in the service type and the base address.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#1)]
     [!code-vb[htPublishMetadataCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#1)]  
  
2. <span data-ttu-id="45a13-116">Erstellen Sie unmittelbar unter dem Code für Schritt&#160;1 einen try-Block, um alle Ausnahmen abzufangen, die während der Ausführung des Diensts ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="45a13-116">Create a try block immediately below the code for step 1, this catches any exceptions that get thrown while the service is running.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#2)]
     [!code-vb[htPublishMetadataCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#2)]  
  
     [!code-csharp[htPublishMetadataCode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#3)]
     [!code-vb[htPublishMetadataCode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#3)]  
  
3. <span data-ttu-id="45a13-117">Überprüfen Sie, ob der Diensthost bereits ein <xref:System.ServiceModel.Description.ServiceMetadataBehavior> enthält. Ist dies nicht der Fall, erstellen Sie eine neue <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz.</span><span class="sxs-lookup"><span data-stu-id="45a13-117">Check to see whether the service host already contains a <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, if not, create a new <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#4)]
     [!code-vb[htPublishMetadataCode#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#4)]  
  
4. <span data-ttu-id="45a13-118">Legen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf `true.` fest.</span><span class="sxs-lookup"><span data-stu-id="45a13-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true.`</span></span>  
  
     [!code-csharp[htPublishMetadataCode#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#5)]
     [!code-vb[htPublishMetadataCode#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#5)]  
  
5. <span data-ttu-id="45a13-119">Das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Objekt enthält die <xref:System.ServiceModel.Description.MetadataExporter>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="45a13-119">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> contains a <xref:System.ServiceModel.Description.MetadataExporter> property.</span></span> <span data-ttu-id="45a13-120">Das <xref:System.ServiceModel.Description.MetadataExporter>-Objekt enthält die <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="45a13-120">The <xref:System.ServiceModel.Description.MetadataExporter> contains a <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property.</span></span> <span data-ttu-id="45a13-121">Legen Sie den Wert der <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>-Eigenschaft auf <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> fest.</span><span class="sxs-lookup"><span data-stu-id="45a13-121">Set the value of the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>.</span></span> <span data-ttu-id="45a13-122">Die <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A>-Eigenschaft kann auch auf <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="45a13-122">The <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property can also be set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>.</span></span> <span data-ttu-id="45a13-123">Wenn diese Einstellung <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> auf festgelegt ist, generiert Metadata Exporter Richtlinien Informationen mit den Metadaten, die WS-Policy 1,5 entsprechen.</span><span class="sxs-lookup"><span data-stu-id="45a13-123">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> the metadata exporter generates policy information with the metadata that" conforms to WS-Policy 1.5.</span></span> <span data-ttu-id="45a13-124">Nach dem Festlegen auf <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> erstellt das Metadatenexportprogramm Richtlinieninformationen gemäß der WS-Richtlinie 1.2.</span><span class="sxs-lookup"><span data-stu-id="45a13-124">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> the metadata exporter generates policy information that conforms to WS-Policy 1.2.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#6)]
     [!code-vb[htPublishMetadataCode#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#6)]  
  
6. <span data-ttu-id="45a13-125">Fügen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Instanz der Verhaltensauflistung des Diensthosts hinzu.</span><span class="sxs-lookup"><span data-stu-id="45a13-125">Add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance to the service host's behaviors collection.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#7)]
     [!code-vb[htPublishMetadataCode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#7)]  
  
7. <span data-ttu-id="45a13-126">Fügen Sie dem Diensthost den Endpunkt für den Metadatenaustausch hinzu.</span><span class="sxs-lookup"><span data-stu-id="45a13-126">Add the metadata exchange endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#8)]
     [!code-vb[htPublishMetadataCode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#8)]  
  
8. <span data-ttu-id="45a13-127">Fügen Sie dem Diensthost einen Anwendungsendpunkt hinzu.</span><span class="sxs-lookup"><span data-stu-id="45a13-127">Add an application endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#9)]
     [!code-vb[htPublishMetadataCode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#9)]  
  
    > [!NOTE]
    > <span data-ttu-id="45a13-128">Wenn Sie dem Dienst keine Endpunkte hinzufügen, werden von der Runtime automatisch Standardendpunkte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="45a13-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="45a13-129">Da in diesem Beispiel das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> des Diensts auf `true` festgelegt ist, ist für den Dienst die Veröffentlichung von Metadaten aktiviert.</span><span class="sxs-lookup"><span data-stu-id="45a13-129">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, the service has publishing metadata enabled.</span></span> <span data-ttu-id="45a13-130">Weitere Informationen zu Standard Endpunkten finden Sie unter [vereinfachte Konfiguration](../../../../docs/framework/wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="45a13-130">For more information about default endpoints, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
9. <span data-ttu-id="45a13-131">Öffnen Sie den Diensthost, und warten Sie auf eingehende Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="45a13-131">Open the service host and wait for incoming calls.</span></span> <span data-ttu-id="45a13-132">Schließen Sie den Diensthost, wenn der Benutzer die Eingabetaste drückt.</span><span class="sxs-lookup"><span data-stu-id="45a13-132">When the user presses ENTER, close the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#10)]
     [!code-vb[htPublishMetadataCode#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#10)]  
  
10. <span data-ttu-id="45a13-133">Erstellen Sie die Konsolenanwendung und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="45a13-133">Build and run the console application.</span></span>  
  
11. <span data-ttu-id="45a13-134">Navigieren Sie mit Internet Explorer zur Basisadresse des Dienstanbieter (http://localhost:8001/MetadataSample in diesem Beispiel), und vergewissern Sie sich, dass die Metadatenveröffentlichung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="45a13-134">Use Internet Explorer to browse to the base address of the service (http://localhost:8001/MetadataSample in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="45a13-135">Es sollte eine Webseite angezeigt werden, die am oberen Rand den Text "Einfacher Dienst" und unmittelbar darunter den Text "Sie haben einen Dienst erstellt" enthält.</span><span class="sxs-lookup"><span data-stu-id="45a13-135">You should see a Web page displayed that says "Simple Service" at the top and immediately below "You have created a service."</span></span> <span data-ttu-id="45a13-136">Wenn dies nicht der Grund ist, wird eine Meldung am oberen Rand der resultierenden Seite angezeigt: "Die Metadatenveröffentlichung für diesen Dienst ist zurzeit deaktiviert."</span><span class="sxs-lookup"><span data-stu-id="45a13-136">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
## <a name="example"></a><span data-ttu-id="45a13-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="45a13-137">Example</span></span>  
 <span data-ttu-id="45a13-138">Das folgende Codebeispiel zeigt die Implementierung eines grundlegenden WCF-diensdienstanbieter, der Metadaten für den Dienst im Code veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="45a13-138">The following code example shows the implementation of a basic WCF service that publishes metadata for the service in code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#11)]
 [!code-vb[htPublishMetadataCode#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="45a13-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45a13-139">See also</span></span>

- [<span data-ttu-id="45a13-140">Vorgehensweise: Hosten eines WCF-Diensts in einer verwalteten Anwendung</span><span class="sxs-lookup"><span data-stu-id="45a13-140">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="45a13-141">Selbst gehostete Dienste</span><span class="sxs-lookup"><span data-stu-id="45a13-141">Self-Host</span></span>](../../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="45a13-142">Übersicht über die Metadatenarchitektur</span><span class="sxs-lookup"><span data-stu-id="45a13-142">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)
- [<span data-ttu-id="45a13-143">Verwenden von Metadaten</span><span class="sxs-lookup"><span data-stu-id="45a13-143">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)
- [<span data-ttu-id="45a13-144">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="45a13-144">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
