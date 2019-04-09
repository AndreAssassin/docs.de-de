---
title: 'Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8a7613ef-0df9-47c3-b8dc-47f42cb1fd8b
ms.openlocfilehash: c104798fa3ef0e8b9dc43ad9cc68599b71de4011
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140490"
---
# <a name="how-to-create-a-service-that-requires-sessions"></a><span data-ttu-id="a9a86-102">Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert</span><span class="sxs-lookup"><span data-stu-id="a9a86-102">How to: Create a Service That Requires Sessions</span></span>
<span data-ttu-id="a9a86-103">Sitzungen erstellen einen Freigabezustand zwischen zwei oder mehr Endpunkten, der nützliche Funktionen wie Rückrufe, Multi-Hop-Sicherheit und Zuordnungen zwischen Clients und Dienstinstanzen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a9a86-103">Sessions create a shared state between two or more endpoints that enables useful features such as callbacks, multi-hop security, and associations between clients and service instances.</span></span> <span data-ttu-id="a9a86-104">Weitere Informationen zu Sitzungen in Windows Communication Foundation (WCF)-Anwendungen finden Sie unter [mithilfe von Sitzungen](../../../../docs/framework/wcf/using-sessions.md).</span><span class="sxs-lookup"><span data-stu-id="a9a86-104">For more information about sessions in Windows Communication Foundation (WCF) applications, see [Using Sessions](../../../../docs/framework/wcf/using-sessions.md).</span></span>  
  
### <a name="to-specify-that-a-contract-require-its-binding-to-support-sessions"></a><span data-ttu-id="a9a86-105">So geben Sie an, dass die Bindung eines Vertrags Sitzungen unterstützen muss</span><span class="sxs-lookup"><span data-stu-id="a9a86-105">To specify that a contract require its binding to support sessions</span></span>  
  
1.  <span data-ttu-id="a9a86-106">Erstellen Sie einen Dienstvertrag mit mindestens einem Vorgang.</span><span class="sxs-lookup"><span data-stu-id="a9a86-106">Create a service contract with at least one operation.</span></span> <span data-ttu-id="a9a86-107">Ein Beispiel zum Erstellen eines Dienstvertrags finden Sie unter [Vorgehensweise: Definieren eines Dienstvertrags](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span><span class="sxs-lookup"><span data-stu-id="a9a86-107">For an example of how to create a service contract, see [How to: Define a Service Contract](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md).</span></span>  
  
2.  <span data-ttu-id="a9a86-108">Ändern Sie <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>, das den Vertrag deklariert, durch Festlegen der <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>-Eigenschaft auf einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="a9a86-108">Modify the <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType> that declares the contract by setting the <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> property to either:</span></span>  
  
    -   <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType> <span data-ttu-id="a9a86-109">Wenn dieser Vertrag innerhalb einer Sitzung ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="a9a86-109">if this contract must be run within a session.</span></span>  
  
    -   <xref:System.ServiceModel.SessionMode.Allowed?displayProperty=nameWithType> <span data-ttu-id="a9a86-110">Wenn dieser Vertrag innerhalb einer Sitzung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a9a86-110">if this contract can be run within a session.</span></span>  
  
    -   <xref:System.ServiceModel.SessionMode.NotAllowed?displayProperty=nameWithType> <span data-ttu-id="a9a86-111">Wenn dieser Vertrag innerhalb einer Sitzung nicht ausgeführt werden muss.</span><span class="sxs-lookup"><span data-stu-id="a9a86-111">if this contract must not be run within a session.</span></span>  
  
3.  <span data-ttu-id="a9a86-112">Konfigurieren Sie den Dienstendpunkt so, dass er eine Bindung verwendet, die Sitzungen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9a86-112">Configure your service endpoint to use a binding that supports sessions.</span></span> <span data-ttu-id="a9a86-113">Im folgenden Konfigurationsbeispiel wird die Verwendung von <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> veranschaulicht, die eine WS`-`ReliableMessaging-Sitzung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a9a86-113">The following configuration example shows the use of the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>, which supports a WS`-`ReliableMessaging session.</span></span>  
  
     [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]   
  
## <a name="example"></a><span data-ttu-id="a9a86-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a9a86-114">Example</span></span>  
 <span data-ttu-id="a9a86-115">Der folgende Beispielcode zeigt, wie Sie mit der <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType>-Bindung eine Sitzungsanforderung auf Vertragsebene angeben und eine Konfigurationsdatei verwenden, um diese Anforderung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a9a86-115">The following example code shows how to specify a contract-level session requirement and use a configuration file to support that requirement with the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> binding.</span></span>  
  
 [!code-csharp[SCA.Session#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/services.cs#1)] 
 [!code-vb[SCA.Session#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/sca.session/vb/services.vb#1)]      
 [!code-xml[SCA.Session#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/sca.session/cs/hostapplication.exe.config#2)]     
  
## <a name="see-also"></a><span data-ttu-id="a9a86-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9a86-116">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute?displayProperty=nameWithType>
- <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType>
- <xref:System.ServiceModel.SessionMode?displayProperty=nameWithType>
