---
title: 'Vorgehensweise: Angeben einer Clientbindung im Code'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6bee5da4-adf7-42e6-8f78-63a9e5c6dbad
ms.openlocfilehash: c95e30c65c6096140fca0c1241e76fbc7af4df3d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303433"
---
# <a name="how-to-specify-a-client-binding-in-code"></a><span data-ttu-id="e0234-102">Vorgehensweise: Angeben einer Clientbindung im Code</span><span class="sxs-lookup"><span data-stu-id="e0234-102">How to: Specify a Client Binding in Code</span></span>
<span data-ttu-id="e0234-103">In diesem Beispiel wird ein Client erstellt, um einen Rechnerdienst zu nutzen, und die Bindung des Clients wird imperativ im Code angegeben.</span><span class="sxs-lookup"><span data-stu-id="e0234-103">In this example, a client is created to use a calculator service and the binding for that client is specified imperatively in code.</span></span> <span data-ttu-id="e0234-104">Der Client greift auf den `CalculatorService` zu, der die `ICalculator`-Schnittstelle implementiert, und sowohl der Dienst als auch der Client verwenden die Klasse <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="e0234-104">The client accesses the `CalculatorService`, which implements the `ICalculator` interface, and both the service and the client use the <xref:System.ServiceModel.BasicHttpBinding> class.</span></span>  
  
 <span data-ttu-id="e0234-105">In dieser Prozedur wird davon ausgegangen, dass der Rechnerdienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e0234-105">This procedure assumes that the calculator service is running.</span></span> <span data-ttu-id="e0234-106">Informationen zum Erstellen des Diensts finden Sie unter [Vorgehensweise: Angeben eine Dienstbindung in einer Konfiguration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="e0234-106">For information about building the service, see [How to: Specify a Service Binding in Configuration](../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span> <span data-ttu-id="e0234-107">Darüber hinaus verwendet er die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) bietet, um die Clientkomponenten automatisch zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e0234-107">It also uses the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)Windows Communication Foundation (WCF) provides to automatically generate the client components.</span></span> <span data-ttu-id="e0234-108">Das Tool generiert den Clientcode für den Zugriff auf den Dienst.</span><span class="sxs-lookup"><span data-stu-id="e0234-108">The tool generates the client code for accessing the service.</span></span>  
  
 <span data-ttu-id="e0234-109">Der Client wird in zwei Schritten erstellt.</span><span class="sxs-lookup"><span data-stu-id="e0234-109">The client is built in two parts.</span></span> <span data-ttu-id="e0234-110">Svcutil.exe generiert den `ClientCalculator`, der die `ICalculator`-Schnittstelle implementiert.</span><span class="sxs-lookup"><span data-stu-id="e0234-110">Svcutil.exe generates the `ClientCalculator` that implements the `ICalculator` interface.</span></span> <span data-ttu-id="e0234-111">Anschließend wird die Clientanwendung erstellt, indem eine Instanz von `ClientCalculator` erstellt wird und dann die Bindung und die Adresse für den Dienst im Code angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e0234-111">This client application is then constructed by constructing an instance of `ClientCalculator` and then specifying the binding and the address for the service in code.</span></span>  
  
 <span data-ttu-id="e0234-112">Die Quellkopie dieses Beispiels, finden Sie unter den [Standardbindung](../../../docs/framework/wcf/samples/basicbinding.md) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e0234-112">For the source copy of this example, see the [BasicBinding](../../../docs/framework/wcf/samples/basicbinding.md) sample.</span></span>  
  
### <a name="to-specify-a-custom-binding-in-code"></a><span data-ttu-id="e0234-113">So geben Sie eine benutzerdefinierte Bindung im Code an</span><span class="sxs-lookup"><span data-stu-id="e0234-113">To specify a custom binding in code</span></span>  
  
1. <span data-ttu-id="e0234-114">Verwenden Sie Svcutil.exe in der Befehlszeile, um Code von Dienstmetadaten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="e0234-114">Use Svcutil.exe from the command line to generate code from service metadata.</span></span>  
  
    ```  
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>   
    ```  
  
2. <span data-ttu-id="e0234-115">Der generierte Client enthält die `ICalculator`-Schnittstelle, die den Dienstvertrag definiert, dem die Clientimplementierung entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="e0234-115">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#1)]
     [!code-vb[C_HowTo_CodeClientBinding#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#1)]  
  
3. <span data-ttu-id="e0234-116">Der generierte Client enthält außerdem die Implementierung vom `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="e0234-116">The generated client also contains the implementation of the `ClientCalculator`.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#2](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#2)]
     [!code-vb[C_HowTo_CodeClientBinding#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#2)]  
  
4. <span data-ttu-id="e0234-117">Erstellen Sie eine Instanz des `ClientCalculator`, der die <xref:System.ServiceModel.BasicHttpBinding>-Klasse in einer Clientanwendung verwendet, und rufen Sie anschließend die Dienstvorgänge an der angegebenen Adresse auf.</span><span class="sxs-lookup"><span data-stu-id="e0234-117">Create an instance of the `ClientCalculator` that uses the <xref:System.ServiceModel.BasicHttpBinding> class in a client application, and then call the service operations at the specified address.</span></span>  
  
     [!code-csharp[C_HowTo_CodeClientBinding#3](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_codeclientbinding/cs/client.cs#3)]
     [!code-vb[C_HowTo_CodeClientBinding#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_codeclientbinding/vb/client.vb#3)]  
  
5. <span data-ttu-id="e0234-118">Kompilieren Sie den Code, und führen Sie den Client aus.</span><span class="sxs-lookup"><span data-stu-id="e0234-118">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0234-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0234-119">See also</span></span>

- [<span data-ttu-id="e0234-120">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e0234-120">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
