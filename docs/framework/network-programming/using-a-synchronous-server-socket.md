---
title: Verwenden eines synchronen Serversockets
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application protocols, sockets
- synchronous server sockets
- sending data, sockets
- data requests, sockets
- requesting data from Internet, sockets
- server sockets
- receiving data, sockets
- Socket class, synchronous server sockets
- protocols, sockets
- sockets, synchronous server sockets
- Internet, sockets
ms.assetid: d1ce882e-653e-41f5-9289-844ec855b804
ms.openlocfilehash: cbc02c755ceefa8f31439f121a98978b82f33fa2
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71047036"
---
# <a name="using-a-synchronous-server-socket"></a><span data-ttu-id="799c8-102">Verwenden eines synchronen Serversockets</span><span class="sxs-lookup"><span data-stu-id="799c8-102">Using a Synchronous Server Socket</span></span>
<span data-ttu-id="799c8-103">Synchrone Serversockets halten die Ausführung der Anwendung an, bis eine Verbindungsanforderung für den Socket empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="799c8-103">Synchronous server sockets suspend the execution of the application until a connection request is received on the socket.</span></span> <span data-ttu-id="799c8-104">Synchrone Serversockets eignen sich nicht für Anwendungen, die das Netzwerk in ihrem Betrieb stark nutzen, aber sie können für einfache Netzwerkanwendungen geeignet sein.</span><span class="sxs-lookup"><span data-stu-id="799c8-104">Synchronous server sockets are not suitable for applications that make heavy use of the network in their operation, but they can be suitable for simple network applications.</span></span>  
  
 <span data-ttu-id="799c8-105">Nachdem <xref:System.Net.Sockets.Socket> zum Lauschen an einem Endpunkt mithilfe der <xref:System.Net.Sockets.Socket.Bind%2A>- und <xref:System.Net.Sockets.Socket.Listen%2A>-Methoden festgelegt wurde, sind sie bereit zur Annahme von eingehenden Verbindungsanforderungen, die die <xref:System.Net.Sockets.Socket.Accept%2A>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="799c8-105">After a <xref:System.Net.Sockets.Socket> is set to listen on an endpoint using the <xref:System.Net.Sockets.Socket.Bind%2A> and <xref:System.Net.Sockets.Socket.Listen%2A> methods, it is ready to accept incoming connection requests using the <xref:System.Net.Sockets.Socket.Accept%2A> method.</span></span> <span data-ttu-id="799c8-106">Die Anwendung wird angehalten, bis eine Verbindungsanforderung beim Aufruf der **Accept**-Methode empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="799c8-106">The application is suspended until a connection request is received when the **Accept** method is called.</span></span>  
  
 <span data-ttu-id="799c8-107">Wenn eine Verbindungsanforderung eingeht, gibt **Accept** eine neue **Socket**-Instanz zurück, die dem verbundenen Client zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="799c8-107">When a connection request is received, **Accept** returns a new **Socket** instance that is associated with the connecting client.</span></span> <span data-ttu-id="799c8-108">Das folgende Beispiel liest Daten aus dem Client, zeigt sie auf der Konsole an und gibt sie an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="799c8-108">The following example reads data from the client, displays it on the console, and echoes the data back to the client.</span></span> <span data-ttu-id="799c8-109">Der **Socket** gibt kein Messaging-Protokoll an, sodass die Zeichenfolge "\<EOF>" das Ende der Nachrichtendaten signalisiert.</span><span class="sxs-lookup"><span data-stu-id="799c8-109">The **Socket** does not specify any messaging protocol, so the string "\<EOF>" marks the end of the message data.</span></span> <span data-ttu-id="799c8-110">Es wird vorausgesetzt, dass ein **Socket** mit dem Namen `listener` initialisiert und an einen Endpunkt gebunden wurde.</span><span class="sxs-lookup"><span data-stu-id="799c8-110">It assumes that a **Socket** named `listener` has been initialized and bound to an endpoint.</span></span>  
  
```vb  
Console.WriteLine("Waiting for a connection...")  
Dim handler As Socket = listener.Accept()  
Dim data As String = Nothing  
  
While True  
    bytes = New Byte(1024) {}  
    Dim bytesRec As Integer = handler.Receive(bytes)  
    data += Encoding.ASCII.GetString(bytes, 0, bytesRec)  
    If data.IndexOf("<EOF>") > - 1 Then  
        Exit While  
    End If  
End While  
  
Console.WriteLine("Text received : {0}", data)  
  
Dim msg As Byte() = Encoding.ASCII.GetBytes(data)  
handler.Send(msg)  
handler.Shutdown(SocketShutdown.Both)  
handler.Close()  
```  
  
```csharp  
Console.WriteLine("Waiting for a connection...");  
Socket handler = listener.Accept();  
String data = null;  
  
while (true) {  
    bytes = new byte[1024];  
    int bytesRec = handler.Receive(bytes);  
    data += Encoding.ASCII.GetString(bytes,0,bytesRec);  
    if (data.IndexOf("<EOF>") > -1) {  
        break;  
    }  
}  
  
Console.WriteLine( "Text received : {0}", data);  
  
byte[] msg = Encoding.ASCII.GetBytes(data);  
handler.Send(msg);  
handler.Shutdown(SocketShutdown.Both);  
handler.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="799c8-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="799c8-111">See also</span></span>

- [<span data-ttu-id="799c8-112">Verwenden eines asynchronen Serversockets</span><span class="sxs-lookup"><span data-stu-id="799c8-112">Using an Asynchronous Server Socket</span></span>](using-an-asynchronous-server-socket.md)
- [<span data-ttu-id="799c8-113">Synchroner Serversocket, Beispiel</span><span class="sxs-lookup"><span data-stu-id="799c8-113">Synchronous Server Socket Example</span></span>](synchronous-server-socket-example.md)
- [<span data-ttu-id="799c8-114">Überwachen mit Sockets</span><span class="sxs-lookup"><span data-stu-id="799c8-114">Listening with Sockets</span></span>](listening-with-sockets.md)
