---
title: WCF-Web-HTTP-Fehlerbehandlung
ms.date: 03/30/2017
ms.assetid: 02891563-0fce-4c32-84dc-d794b1a5c040
ms.openlocfilehash: 834c642e36e1551081dbe1f14529ed7596df1360
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152697"
---
# <a name="wcf-web-http-error-handling"></a><span data-ttu-id="a2ea9-102">WCF-Web-HTTP-Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="a2ea9-102">WCF Web HTTP Error Handling</span></span>
<span data-ttu-id="a2ea9-103">Windows Communication Foundation (WCF)-Web-HTTP-Fehlerbehandlung ermöglicht es Ihnen, Fehler von WCF-Web-HTTP-Diensten zurückzugeben, die HTTP-Statuscode angeben und die Fehlerdetails, die mit dem gleichen Format wie des Vorgangs (z. B. XML oder JSON) zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-103">Windows Communication Foundation (WCF) Web HTTP error handling enables you to return errors from WCF Web HTTP services that specify an HTTP status code and return error details using the same format as the operation (for example, XML or JSON).</span></span>  
  
## <a name="wcf-web-http-error-handling"></a><span data-ttu-id="a2ea9-104">WCF-Web-HTTP-Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="a2ea9-104">WCF Web HTTP Error Handling</span></span>  
 <span data-ttu-id="a2ea9-105">Die <xref:System.ServiceModel.Web.WebFaultException>-Klasse definiert einen Konstruktor, der Ihnen das Angeben eines HTTP-Statuscodes ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-105">The <xref:System.ServiceModel.Web.WebFaultException> class defines a constructor that allows you to specify an HTTP status code.</span></span> <span data-ttu-id="a2ea9-106">Dieser Statuscode wird dann an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-106">This status code is then returned to the client.</span></span> <span data-ttu-id="a2ea9-107">Dies ist eine generische Version der <xref:System.ServiceModel.Web.WebFaultException>-Klasse. Mit <xref:System.ServiceModel.Web.WebFaultException%601> können Sie einen benutzerdefinierten Typ zurückgeben, der Informationen zum aufgetretenen Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-107">A generic version of the <xref:System.ServiceModel.Web.WebFaultException> class, <xref:System.ServiceModel.Web.WebFaultException%601> enables you to return a user-defined type that contains information about the error that occurred.</span></span> <span data-ttu-id="a2ea9-108">Dieses benutzerdefinierte Objekt wird in dem Format serialisiert, das vom Vorgang angegeben und an den Client zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-108">This custom object is serialized using the format specified by the operation and returned to the client.</span></span> <span data-ttu-id="a2ea9-109">Im folgenden Beispiel wird gezeigt, wie Sie einen HTTP-Statuscode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-109">The following example shows how to return an HTTP status code.</span></span>  
  
```  
Public string Operation1()  
{   // Operation logic  
   // ...  
   Throw new WebFaultException(HttpStatusCode.Forbidden);  
}  
```  
  
 <span data-ttu-id="a2ea9-110">Im folgenden Beispiel wird gezeigt, wie Sie einen HTTP-Statuscode und zusätzliche Informationen in einem benutzerdefinierten Typ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-110">The following example shows how to return an HTTP status code and extra information in a user-defined type.</span></span> <span data-ttu-id="a2ea9-111">`MyErrorDetail` ist ein benutzerdefinierter Typ, der zusätzliche Informationen zum aufgetretenen Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-111">`MyErrorDetail` is a user-defined type that contains extra information about the error that occurred.</span></span>  
  
```  
Public string Operation2()  
   // Operation logic  
   // ...   MyErrorDetail detail = new MyErrorDetail  
   {  
      Message = "Error Message",  
      ErrorCode = 123,  
   }  
   throw new WebFaultException<MyErrorDetail>(detail, HttpStatusCode.Forbidden);  
}  
```  
  
 <span data-ttu-id="a2ea9-112">Der oben angegebene Code gibt eine HTTP-Antwort mit dem unzulässigen Statuscode und einem Text zurück, in der eine Instanz des `MyErrorDetails`-Objekts enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-112">The preceding code returns an HTTP response with the forbidden status code and a body that contains an instance of the `MyErrorDetails` object.</span></span> <span data-ttu-id="a2ea9-113">Zum Bestimmen des Formats des `MyErrorDetails`-Objekts werden folgende Komponenten herangezogen:</span><span class="sxs-lookup"><span data-stu-id="a2ea9-113">The format of the `MyErrorDetails` object is determined by:</span></span>  
  
-   <span data-ttu-id="a2ea9-114">Der Wert des `ResponseFormat`-Parameters des <xref:System.ServiceModel.Web.WebGetAttribute>- oder <xref:System.ServiceModel.Web.WebInvokeAttribute>-Attributs, das für den Dienstvorgang angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-114">The value of the `ResponseFormat` parameter of the <xref:System.ServiceModel.Web.WebGetAttribute> or <xref:System.ServiceModel.Web.WebInvokeAttribute> attribute specified on the service operation.</span></span>  
  
-   <span data-ttu-id="a2ea9-115">Der Wert von <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-115">The value of <xref:System.ServiceModel.Description.WebHttpBehavior.AutomaticFormatSelectionEnabled%2A>.</span></span>  
  
-   <span data-ttu-id="a2ea9-116">Der Wert der <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A>-Eigenschaft, indem auf <xref:System.ServiceModel.Web.OutgoingWebResponseContext> zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-116">The value of the <xref:System.ServiceModel.Web.OutgoingWebResponseContext.Format%2A> property by accessing the <xref:System.ServiceModel.Web.OutgoingWebResponseContext>.</span></span>  
  
 <span data-ttu-id="a2ea9-117">Weitere Informationen dazu, wie diese Werte auf die Formatierung des Vorgangs auswirken, finden Sie unter [WCF Web-HTTP-Formatierung](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="a2ea9-117">For more information about how these values affect the formatting of the operation, see [WCF Web HTTP Formatting](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md).</span></span>  
  
 <span data-ttu-id="a2ea9-118"><xref:System.ServiceModel.Web.WebFaultException> ist ein <xref:System.ServiceModel.FaultException>-Objekt und kann daher als Fehlerausnahme-Programmiermodell für Dienste verwendet werden, die SOAP-Endpunkte sowie Web-HTTP-Endpunkte verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="a2ea9-118"><xref:System.ServiceModel.Web.WebFaultException> is a <xref:System.ServiceModel.FaultException> and therefore can be used as the fault exception programming model for services that expose SOAP endpoints as well as web HTTP endpoints.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ea9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2ea9-119">See also</span></span>

- [<span data-ttu-id="a2ea9-120">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="a2ea9-120">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [<span data-ttu-id="a2ea9-121">WCF-Web-HTTP-Formatierung</span><span class="sxs-lookup"><span data-stu-id="a2ea9-121">WCF Web HTTP Formatting</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-formatting.md)
- [<span data-ttu-id="a2ea9-122">Definieren und Angeben von Fehlern</span><span class="sxs-lookup"><span data-stu-id="a2ea9-122">Defining and Specifying Faults</span></span>](../../../../docs/framework/wcf/defining-and-specifying-faults.md)
- [<span data-ttu-id="a2ea9-123">Behandeln von Ausnahmen und Fehlern</span><span class="sxs-lookup"><span data-stu-id="a2ea9-123">Handling Exceptions and Faults</span></span>](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)
- [<span data-ttu-id="a2ea9-124">Senden und Empfangen von Fehlern</span><span class="sxs-lookup"><span data-stu-id="a2ea9-124">Sending and Receiving Faults</span></span>](../../../../docs/framework/wcf/sending-and-receiving-faults.md)
