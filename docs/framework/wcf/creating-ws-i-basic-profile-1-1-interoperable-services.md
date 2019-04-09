---
title: Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- configuration [WCF], interoperable services
ms.assetid: 91b70a21-8f5c-4679-808c-2ed5fa6b2013
ms.openlocfilehash: b9cacee9a69695b0001b94b74648d5154b8a52b4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59123915"
---
# <a name="creating-ws-i-basic-profile-11-interoperable-services"></a><span data-ttu-id="66108-102">Erstellen von interoperablen WS-I Basic Profile 1.1-Diensten</span><span class="sxs-lookup"><span data-stu-id="66108-102">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>
<span data-ttu-id="66108-103">So konfigurieren Sie einen WCF-Dienstendpunkt, um Interoperabilität mit [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Webdienstclients:</span><span class="sxs-lookup"><span data-stu-id="66108-103">To configure a WCF service endpoint to be interoperable with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients:</span></span>  
  
-   <span data-ttu-id="66108-104">Verwenden Sie den <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType>-Typ als Bindungstyp für den Dienstendpunkt.</span><span class="sxs-lookup"><span data-stu-id="66108-104">Use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
-   <span data-ttu-id="66108-105">Verwenden Sie für den Dienstendpunkt keine Rückruf- und Sitzungsvertragsfunktionen oder Transaktionsverhalten.</span><span class="sxs-lookup"><span data-stu-id="66108-105">Do not use callback and session contract features or transaction behaviors on your service endpoint</span></span>  
  
 <span data-ttu-id="66108-106">Sie können für die Bindung auch Unterstützung für HTTPS und Clientauthentifizierung auf Transportebene aktivieren.</span><span class="sxs-lookup"><span data-stu-id="66108-106">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span>  
  
 <span data-ttu-id="66108-107">Die folgenden Funktionen der <xref:System.ServiceModel.BasicHttpBinding>-Klasse erfordern Funktionalität jenseits von WS-I Basic Profiles 1.1:</span><span class="sxs-lookup"><span data-stu-id="66108-107">The following features of the <xref:System.ServiceModel.BasicHttpBinding> class require functionality beyond WS-I Basic Profile 1.1:</span></span>  
  
-   <span data-ttu-id="66108-108">MTOM-Meldungscodierung (Message Transmission Optimization Mechanism), die von der <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType>-Eigenschaft gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="66108-108">Message Transmission Optimization Mechanism (MTOM) message encoding controlled by the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="66108-109">Behalten Sie für diese Eigenschaft den Standardwert bei, der <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> ist, was bedeutet, dass kein MTOM verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="66108-109">Leave  this property at its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType> to not use MTOM.</span></span>  
  
-   <span data-ttu-id="66108-110">Meldungssicherheit, die vom <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType>-Wert gesteuert wird, stellt WS-Sicherheit bereit, die mit WS-I Basic Security Profile 1.0 kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="66108-110">Message security controlled by the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> value provides WS-Security support compliant with WS-I Basic Security Profile 1.0.</span></span> <span data-ttu-id="66108-111">Behalten Sie für diese Eigenschaft den Standardwert <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> bei, d. h. es wird keine WS-Sicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="66108-111">Leave this property at its default value, which is <xref:System.ServiceModel.SecurityMode.Transport?displayProperty=nameWithType> to not use WS-Security.</span></span>  
  
 <span data-ttu-id="66108-112">Um die Metadaten für einen WCF-Dienst verfügbar zu machen [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], verwenden Sie die Web Service-Generation-Clienttools: [Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [Web Services Discovery Tool (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29), und die `Add Web Reference` Features in Visual Studio; Sie müssen die Metadatenveröffentlichung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="66108-112">To make the metadata for a WCF service available to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)], use the Web service client generation tools: [Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6%28v=vs.100%29), [Web Services Discovery Tool (Disco.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cy2a3ybs%28v=vs.100%29), and the `Add Web Reference` feature in Visual Studio; you must enable metadata publication.</span></span> <span data-ttu-id="66108-113">Weitere Informationen finden Sie unter [Veröffentlichen von Metadatenendpunkten](../../../docs/framework/wcf/publishing-metadata-endpoints.md).</span><span class="sxs-lookup"><span data-stu-id="66108-113">For more information, see [Publishing Metadata Endpoints](../../../docs/framework/wcf/publishing-metadata-endpoints.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66108-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66108-114">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="66108-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="66108-115">Description</span></span>  
 <span data-ttu-id="66108-116">Der folgende Beispielcode veranschaulicht, wie einen WCF-Endpunkt hinzufügen, die kompatibel mit [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] -Webdienstclients, die im Code und Alternativ in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="66108-116">The following example code demonstrates how to add a WCF endpoint that is compatible with [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web service clients in code and, alternatively, in a configuration file.</span></span>  
  
### <a name="code"></a><span data-ttu-id="66108-117">Code</span><span class="sxs-lookup"><span data-stu-id="66108-117">Code</span></span>  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)]
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)]  
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]  
  
## <a name="see-also"></a><span data-ttu-id="66108-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="66108-118">See also</span></span>

- [<span data-ttu-id="66108-119">Interoperabilität mit ASP.NET-Webdiensten</span><span class="sxs-lookup"><span data-stu-id="66108-119">Interoperability with ASP.NET Web Services</span></span>](../../../docs/framework/wcf/feature-details/interop-with-aspnet-web-services.md)
