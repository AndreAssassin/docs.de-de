---
title: 'Vorgehensweise: Asynchrones Aufrufen von WCF-Dienstvorgänge'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0face17f-43ca-417b-9b33-737c0fc360df
ms.openlocfilehash: 2815757bf9b00375f763673f18180bfbf51a165a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317441"
---
# <a name="how-to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="bf977-102">Vorgehensweise: Asynchrones Aufrufen von WCF-Dienstvorgänge</span><span class="sxs-lookup"><span data-stu-id="bf977-102">How to: Call WCF Service Operations Asynchronously</span></span>
<span data-ttu-id="bf977-103">In diesem Thema wird beschrieben, wie ein Client auf einen Dienstvorgang asynchron zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="bf977-103">This topic covers how a client can access a service operation asynchronously.</span></span> <span data-ttu-id="bf977-104">Der in diesem Thema behandelte Dienst implementiert die `ICalculator`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="bf977-104">The service in this topic implements the `ICalculator` interface.</span></span> <span data-ttu-id="bf977-105">Der Client kann mithilfe des ereignisgesteuerten asynchronen Aufrufmodells die Vorgänge asynchron an dieser Schnittstelle aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bf977-105">The client can call the operations on this interface asynchronously by using the event-driven asynchronous calling model.</span></span> <span data-ttu-id="bf977-106">(Weitere Informationen über den ereignisbasierten asynchronen aufrufmodells finden Sie unter [Multithreadprogrammierung mit dem ereignisbasierten asynchronen Muster](https://go.microsoft.com/fwlink/?LinkId=248184)).</span><span class="sxs-lookup"><span data-stu-id="bf977-106">(For more information about the event-based asynchronous calling model, see [Multithreaded Programming with the Event-based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=248184)).</span></span> <span data-ttu-id="bf977-107">Ein Beispiel, wie Sie das asynchrone Implementieren eines Vorgangs in einem Dienst veranschaulicht, finden Sie unter [Vorgehensweise: Implementieren ein asynchronen Dienstvorgangs](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span><span class="sxs-lookup"><span data-stu-id="bf977-107">For an example that shows how to implement an operation asynchronously in a service, see [How to: Implement an Asynchronous Service Operation](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md).</span></span> <span data-ttu-id="bf977-108">Weitere Informationen zu synchronen und asynchronen Vorgängen, finden Sie unter [synchrone und asynchrone Vorgänge](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span><span class="sxs-lookup"><span data-stu-id="bf977-108">For more information about synchronous and asynchronous operations, see [Synchronous and Asynchronous Operations](../../../../docs/framework/wcf/synchronous-and-asynchronous-operations.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf977-109">Bei Verwendung einer <xref:System.ServiceModel.ChannelFactory%601> wird das ereignisgesteuerte asynchrone Aufrufmodell nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bf977-109">The event-driven asynchronous calling model is not supported when using a <xref:System.ServiceModel.ChannelFactory%601>.</span></span> <span data-ttu-id="bf977-110">Weitere Informationen zur Verwendung asynchroner Aufrufe mit den <xref:System.ServiceModel.ChannelFactory%601>, finden Sie unter [Vorgehensweise: Aufrufen von Vorgängen, die asynchron mit einer Kanalfactory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span><span class="sxs-lookup"><span data-stu-id="bf977-110">For information about making asynchronous calls using the <xref:System.ServiceModel.ChannelFactory%601>, see [How to: Call Operations Asynchronously Using a Channel Factory](../../../../docs/framework/wcf/feature-details/how-to-call-operations-asynchronously-using-a-channel-factory.md).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="bf977-111">Prozedur</span><span class="sxs-lookup"><span data-stu-id="bf977-111">Procedure</span></span>  
  
#### <a name="to-call-wcf-service-operations-asynchronously"></a><span data-ttu-id="bf977-112">So rufen Sie WCF-Dienstvorgänge asynchron auf</span><span class="sxs-lookup"><span data-stu-id="bf977-112">To call WCF service operations asynchronously</span></span>  
  
1. <span data-ttu-id="bf977-113">Führen Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Tool, mit der `/async` und `/tcv:Version35` Befehlsoptionen wie in den folgenden Befehl gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bf977-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool with both the `/async` and the `/tcv:Version35` command options together as shown in the following command.</span></span>  
  
    ```  
    svcutil /n:http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples http://localhost:8000/servicemodelsamples/service/mex /a /tcv:Version35  
    ```  
  
     <span data-ttu-id="bf977-114">Dies wird generiert, zusätzlich zu den synchronen "und" standard delegatbasierte asynchrone Vorgänge, eine WCF-Client-Klasse enthält:</span><span class="sxs-lookup"><span data-stu-id="bf977-114">This generates, in addition to the synchronous and standard delegate-based asynchronous operations, a WCF client class that contains:</span></span>  
  
    -   <span data-ttu-id="bf977-115">Zwei <`operationName` > `Async` Vorgänge für die Verwendung mit dem ereignisbasierten asynchronen Aufrufmodell.</span><span class="sxs-lookup"><span data-stu-id="bf977-115">Two <`operationName`>`Async` operations for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="bf977-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bf977-116">For example:</span></span>  
  
         [!code-csharp[EventAsync#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#1)]
         [!code-vb[EventAsync#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#1)]  
  
    -   <span data-ttu-id="bf977-117">Abgeschlossen-Ereignisse im Format <`operationName` > `Completed` für die Verwendung mit dem ereignisbasierten asynchronen Aufrufmodell.</span><span class="sxs-lookup"><span data-stu-id="bf977-117">Operation completed events of the form <`operationName`>`Completed` for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="bf977-118">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bf977-118">For example:</span></span>  
  
         [!code-csharp[EventAsync#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#2)]
         [!code-vb[EventAsync#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#2)]  
  
    -   <xref:System.EventArgs?displayProperty=nameWithType> <span data-ttu-id="bf977-119">Typen, die für jeden Vorgang (im Format <`operationName`>`CompletedEventArgs`) für die Verwendung mit dem ereignisbasierten asynchronen Aufrufmodell.</span><span class="sxs-lookup"><span data-stu-id="bf977-119">types for each operation (of the form <`operationName`>`CompletedEventArgs`) for use with the event-based asynchronous calling approach.</span></span> <span data-ttu-id="bf977-120">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bf977-120">For example:</span></span>  
  
         [!code-csharp[EventAsync#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/generatedclient.cs#3)]
         [!code-vb[EventAsync#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/generatedclient.vb#3)]  
  
2. <span data-ttu-id="bf977-121">Erstellen Sie in der aufrufenden Anwendung eine Rückrufmethode, die aufgerufen wird, wenn der asynchrone Vorgang abgeschlossen ist, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="bf977-121">In the calling application, create a callback method to be called when the asynchronous operation is complete, as shown in the following sample code.</span></span>  
  
     [!code-csharp[EventAsync#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#4)]
     [!code-vb[EventAsync#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#4)]  
  
3. <span data-ttu-id="bf977-122">Verwenden Sie vor dem Aufruf des Vorgangs einen neuen generischen <xref:System.EventHandler%601?displayProperty=nameWithType> vom Typ <`operationName` > `EventArgs` hinzuzufügende Handlermethode (im vorherigen Schritt erstellt) die <`operationName` > `Completed` Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bf977-122">Prior to calling the operation, use a new generic <xref:System.EventHandler%601?displayProperty=nameWithType> of type <`operationName`>`EventArgs` to add the handler method (created in the preceding step) to the <`operationName`>`Completed` event.</span></span> <span data-ttu-id="bf977-123">Rufen Sie dann die <`operationName` > `Async` Methode.</span><span class="sxs-lookup"><span data-stu-id="bf977-123">Then call the <`operationName`>`Async` method.</span></span> <span data-ttu-id="bf977-124">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bf977-124">For example:</span></span>  
  
     [!code-csharp[EventAsync#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#5)]
     [!code-vb[EventAsync#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="bf977-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf977-125">Example</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf977-126">Die Entwurfsrichtlinien für das ereignisbasierte asynchrone Modell besagen, dass in den Fällen, in denen mehr als ein Wert zurückgegeben wird, ein Wert in der `Result`-Eigenschaft und die übrigen Werte in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bf977-126">The design guidelines for the event-based asynchronous model state that if more than one value is returned, one value is returned as the `Result` property and the others are returned as properties on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="bf977-127">Wenn ein Client Metadaten mithilfe der ereignisbasierten asynchronen Befehlsoptionen importiert und der Vorgang mehr als einen Wert zurückgibt, dann gibt das <xref:System.EventArgs>-Objekt infolgedessen einen Wert in der `Result`-Eigenschaft zurück, und die übrigen Werte werden in Eigenschaften des <xref:System.EventArgs>-Objekts zurückgegeben. Wenn das Nachrichtenobjekt in der `Result`-Eigenschaft und die Rückgabewerte als Eigenschaften dieses Objekts übermittelt werden sollen, verwenden Sie die Befehlsoption `/messageContract`.</span><span class="sxs-lookup"><span data-stu-id="bf977-127">One result of this is that if a client imports metadata using the event-based asynchronous command options and the operation returns more than one value, the default <xref:System.EventArgs> object returns one value as the `Result` property and the remainder are properties of the <xref:System.EventArgs> object.If you want to receive the message object as the `Result` property and have the returned values as properties on that object, use the `/messageContract` command option.</span></span> <span data-ttu-id="bf977-128">Damit wird eine Signatur generiert, bei der die Antwortnachricht in der `Result`-Eigenschaft des <xref:System.EventArgs>-Objekts zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bf977-128">This generates a signature that returns the response message as the `Result` property on the <xref:System.EventArgs> object.</span></span> <span data-ttu-id="bf977-129">Alle internen Rückgabewerte sind dann Eigenschaften des Antwortnachrichtenobjekts.</span><span class="sxs-lookup"><span data-stu-id="bf977-129">All internal return values are then properties of the response message object.</span></span>  
  
 [!code-csharp[EventAsync#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/eventasync/cs/client.cs#6)]
 [!code-vb[EventAsync#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/eventasync/vb/client.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="bf977-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf977-130">See also</span></span>

- [<span data-ttu-id="bf977-131">Vorgehensweise: Implementieren eines asynchronen Dienstvorgangs</span><span class="sxs-lookup"><span data-stu-id="bf977-131">How to: Implement an Asynchronous Service Operation</span></span>](../../../../docs/framework/wcf/how-to-implement-an-asynchronous-service-operation.md)
