---
title: 'Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse'
ms.date: 03/21/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- downloading Internet resources, steps
- requesting data from Internet, steps
- WebRequest class, receiving data
- receiving data, using WebRequest class
- Internet, requesting data
ms.assetid: 368b8d0f-dc5e-4469-a8b8-b2adbf5dd800
ms.openlocfilehash: eb38a95891afaf4cab98e43a250b67823fa5eb24
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040874"
---
# <a name="how-to-request-data-by-using-the-webrequest-class"></a><span data-ttu-id="b3254-102">Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse</span><span class="sxs-lookup"><span data-stu-id="b3254-102">How to: Request data by using the WebRequest class</span></span>

<span data-ttu-id="b3254-103">Das folgende Verfahren beschreibt die Schritte zum Anfordern einer Ressource von einem Server, wie z.B. einer Webseite oder Datei.</span><span class="sxs-lookup"><span data-stu-id="b3254-103">The following procedure describes the steps to request a resource, such as a Web page or a file, from a server.</span></span> <span data-ttu-id="b3254-104">Die Ressource muss von einem URI identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="b3254-104">The resource must be identified by a URI.</span></span>

## <a name="to-request-data-from-a-host-server"></a><span data-ttu-id="b3254-105">Anfordern von Daten von einem Hostserver</span><span class="sxs-lookup"><span data-stu-id="b3254-105">To request data from a host server</span></span>

1. <span data-ttu-id="b3254-106">Erstellen Sie eine <xref:System.Net.WebRequest>-Instanz, indem Sie <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> mit dem URI einer Ressource aufrufen.</span><span class="sxs-lookup"><span data-stu-id="b3254-106">Create a <xref:System.Net.WebRequest> instance by calling <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType> with the URI of a resource.</span></span> <span data-ttu-id="b3254-107">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b3254-107">For example:</span></span>

    ```csharp
    WebRequest request = WebRequest.Create("http://www.contoso.com/default.html");
    ```

    ```vb
    Dim request as WebRequest = WebRequest.Create("http://www.contoso.com/default.html")
    ```

    > [!NOTE]
    > <span data-ttu-id="b3254-108">.NET Framework stellt von den Klassen <xref:System.Net.WebRequest> und <xref:System.Net.WebResponse> abgeleitete protokollspezifische Klassen für URIs bereit, die mit *http:* , *https:* , *ftp:* und *file:* beginnen.</span><span class="sxs-lookup"><span data-stu-id="b3254-108">The .NET Framework provides protocol-specific classes derived from the <xref:System.Net.WebRequest> and <xref:System.Net.WebResponse> classes for URIs that begin with *http:*, *https:*, *ftp:*, and *file:*.</span></span>

    <span data-ttu-id="b3254-109">Wenn Sie protokollspezifische Eigenschaften festlegen oder lesen müssen, wandeln Sie Ihr <xref:System.Net.WebRequest>- oder <xref:System.Net.WebResponse>-Objekt in einen protokollspezifischen Objekttyp um.</span><span class="sxs-lookup"><span data-stu-id="b3254-109">If you need to set or read protocol-specific properties, you must cast your <xref:System.Net.WebRequest> or <xref:System.Net.WebResponse> object to a protocol-specific object type.</span></span> <span data-ttu-id="b3254-110">Weitere Informationen finden Sie unter [Programmieren austauschbarer Protokolle](programming-pluggable-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="b3254-110">For more information, see [Programming pluggable protocols](programming-pluggable-protocols.md).</span></span>

2. <span data-ttu-id="b3254-111">Legen Sie alle Eigenschaftswerte, die Sie benötigen, in Ihrem `WebRequest`-Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="b3254-111">Set any property values that you need in your `WebRequest` object.</span></span> <span data-ttu-id="b3254-112">Legen Sie z.B. zum Aktivieren der Authentifizierung die Eigenschaft <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> auf eine Instanz der <xref:System.Net.NetworkCredential>-Klasse fest:</span><span class="sxs-lookup"><span data-stu-id="b3254-112">For example, to enable authentication, set the <xref:System.Net.WebRequest.Credentials%2A?displayProperty=nameWithType> property to an instance of the <xref:System.Net.NetworkCredential> class:</span></span>

    ```csharp
    request.Credentials = CredentialCache.DefaultCredentials;
    ```

    ```vb
    request.Credentials = CredentialCache.DefaultCredentials
    ```

3. <span data-ttu-id="b3254-113">Senden Sie die Anforderung an den Server durch Aufrufen von <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b3254-113">Send the request to the server by calling <xref:System.Net.WebRequest.GetResponse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b3254-114">Diese Methode gibt ein Objekt zurück, das die Antwort des Servers enthält.</span><span class="sxs-lookup"><span data-stu-id="b3254-114">This method returns an object containing the server's response.</span></span> <span data-ttu-id="b3254-115">Der Typ des zurückgegebenen <xref:System.Net.WebResponse>-Objekts wird durch das URI-Schema der Anforderung bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b3254-115">The returned <xref:System.Net.WebResponse> object's type is determined by the scheme of the request's URI.</span></span> <span data-ttu-id="b3254-116">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b3254-116">For example:</span></span>

    ```csharp
    WebResponse response = request.GetResponse();
    ```

    ```vb
    Dim response As WebResponse = request.GetResponse()
    ```

4. <span data-ttu-id="b3254-117">Sie können die protokollspezifischen Eigenschaften lesen, indem Sie auf die Eigenschaften des `WebResponse`-Objekts zugreifen oder das Objekt in eine protokollspezifische Instanz umwandeln.</span><span class="sxs-lookup"><span data-stu-id="b3254-117">You can access the properties of your `WebResponse` object or cast it to a protocol-specific instance to read protocol-specific properties.</span></span>

    <span data-ttu-id="b3254-118">Wandeln Sie z.B. das `WebResponse`-Objekt in einen `HttpWebResponse`-Verweis um, wenn Sie auf die HTTP-spezifischen Eigenschaften von <xref:System.Net.HttpWebResponse> zugreifen möchten.</span><span class="sxs-lookup"><span data-stu-id="b3254-118">For example, to access the HTTP-specific properties of <xref:System.Net.HttpWebResponse>, cast your `WebResponse` object to an `HttpWebResponse` reference.</span></span> <span data-ttu-id="b3254-119">Das folgende Codebeispiel zeigt die Vorgehensweise beim Anzeigen der HTTP-spezifischen Eigenschaft <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType>, die mit einer Antwort gesendet wird:</span><span class="sxs-lookup"><span data-stu-id="b3254-119">The following code example shows how to display the HTTP-specific <xref:System.Net.HttpWebResponse.StatusDescription%2A?displayProperty=nameWithType> property sent with a response:</span></span>

    ```csharp
    Console.WriteLine (((HttpWebResponse)response).StatusDescription);
    ```

    ```vb
    Console.WriteLine(CType(response,HttpWebResponse).StatusDescription)
    ```

5. <span data-ttu-id="b3254-120">Zum Abrufen des Datenstroms, der die vom Server gesendeten Antwortdaten enthält, rufen Sie die <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType>-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="b3254-120">To get the stream containing response data sent by the server, call the <xref:System.Net.WebResponse.GetResponseStream%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b3254-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b3254-121">For example:</span></span>

    ```csharp
    Stream dataStream = response.GetResponseStream();
    ```

    ```vb
    Dim dataStream As Stream = response.GetResponseStream()
    ```

6. <span data-ttu-id="b3254-122">Nachdem Sie die Daten des Antwortobjekts gelesen haben, können Sie entweder das Objekt mit der <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType>-Methode oder den Antwortdatenstrom mit der <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType>-Methode schließen.</span><span class="sxs-lookup"><span data-stu-id="b3254-122">After you've read the data from the response object, either close it with the <xref:System.Net.WebResponse.Close%2A?displayProperty=nameWithType> method or close the response stream with the <xref:System.IO.Stream.Close%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="b3254-123">Wird weder das Antwortobjekt noch der Datenstrom geschlossen, verfügt die Anwendung möglicherweise nicht mehr über genügend Serververbindungen und kann somit weitere Anforderungen nicht mehr verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b3254-123">If you don't close either the response object or the stream, your application can run out of server connections and become unable to process additional requests.</span></span> <span data-ttu-id="b3254-124">Da die `WebResponse.Close`-Methode beim Schließen der Antwort `Stream.Close` aufruft, ist das Aufrufen von `Close` für Antwort- und Datenstromobjekt nicht notwendig (aber auch nicht schädlich).</span><span class="sxs-lookup"><span data-stu-id="b3254-124">Because the `WebResponse.Close` method calls `Stream.Close` when it closes the response, it's not necessary to call `Close` on both the response and stream objects, although doing so isn't harmful.</span></span> <span data-ttu-id="b3254-125">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b3254-125">For example:</span></span>

    ```csharp
    response.Close();
    ```

    ```vb
    response.Close()
    ```

## <a name="example"></a><span data-ttu-id="b3254-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3254-126">Example</span></span>

<span data-ttu-id="b3254-127">Im folgenden Codebeispiel wird die Vorgehensweise beim Erstellen einer Anforderung an einen Webserver und dem Lesen der Daten in der Antwort veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b3254-127">The following code example shows how to create a request to a web server and read the data in its response:</span></span>

[!code-csharp[RequestDataUsingWebRequest](../../../samples/snippets/csharp/VS_Snippets_Network/RequestDataUsingWebRequest/cs/WebRequestGetExample.cs)]
[!code-vb[RequestDataUsingWebRequest](../../../samples/snippets/visualbasic/VS_Snippets_Network/RequestDataUsingWebRequest/vb/WebRequestGetExample.vb)]

## <a name="see-also"></a><span data-ttu-id="b3254-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3254-128">See also</span></span>

- [<span data-ttu-id="b3254-129">Erstellen von Internetanforderungen</span><span class="sxs-lookup"><span data-stu-id="b3254-129">Creating internet requests</span></span>](creating-internet-requests.md)
- [<span data-ttu-id="b3254-130">Verwenden von Datenströmen im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="b3254-130">Using Streams on the network</span></span>](using-streams-on-the-network.md)
- [<span data-ttu-id="b3254-131">Zugreifen auf das Internet über einen Proxy</span><span class="sxs-lookup"><span data-stu-id="b3254-131">Accessing the internet through a proxy</span></span>](accessing-the-internet-through-a-proxy.md)
- [<span data-ttu-id="b3254-132">Anfordern von Daten</span><span class="sxs-lookup"><span data-stu-id="b3254-132">Requesting data</span></span>](requesting-data.md)
- [<span data-ttu-id="b3254-133">Vorgehensweise: Senden von Daten mithilfe der WebRequest-Klasse</span><span class="sxs-lookup"><span data-stu-id="b3254-133">How to: Send data by using the WebRequest class</span></span>](how-to-send-data-using-the-webrequest-class.md)
