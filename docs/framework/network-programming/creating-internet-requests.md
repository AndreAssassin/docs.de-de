---
title: Erstellen von Internetanforderungen
ms.date: 03/30/2017
helpviewer_keywords:
- WebRequest class, sending and receiving data
- Networking
- HttpWebResponse class, sending and receiving data
- requesting data from Internet, creating requests
- Network Resources
- Internet, requesting data
- data requests, creating requests
ms.assetid: faab683e-3f1e-4eee-b5e9-59f7245033d5
ms.openlocfilehash: 2a4915796310e4f6899d833f20bc5260e0ee032b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171029"
---
# <a name="creating-internet-requests"></a>Erstellen von Internetanforderungen
Anwendungen erstellen mithilfe der <xref:System.Net.WebRequest.Create%2A?displayProperty=nameWithType>-Methode <xref:System.Net.WebRequest>-Instanzen. Diese statische Methode erstellt eine von **WebRequest** abgeleitete Klasse basierend auf dem URI-Schema, das an sie übergeben wurde.  
  
## <a name="web-file-and-ftp-requests"></a>Web-, Datei- und FTP-Anforderungen  
 .NET Framework stellt die von **WebRequest** abgeleitete <xref:System.Net.HttpWebRequest>-Klasse bereit, um HTTP- und HTTPS-Anforderungen zu verarbeiten. In den meisten Fällen stellt die **WebRequest**-Klasse alle für eine Anforderung erforderlichen Eigenschaften bereit. Bei Bedarf können Sie jedoch mit der **WebRequest.Create**-Methode erstellte **WebRequest**-Objekte in den Typ **HttpWebRequest** umwandeln, um auf die HTTP-spezifischen Eigenschaften der Anforderung zuzugreifen. Auf ähnliche Weise werden die Antworten von HTTP- und HTTPS-Anforderungen durch das **HttpWebResponse**-Objekt verarbeitet. Wenn Sie auf die HTTP-spezifischen Eigenschaften des **HttpWebResponse**-Objekts zugreifen möchten, müssen Sie **WebResponse**-Objekte in den Typ **HttpWebResponse** umwandeln.  
  
 Das .NET Framework stellt außerdem die Klassen <xref:System.Net.FileWebRequest> und <xref:System.Net.FileWebResponse> zum Verarbeiten von Anforderungen für Ressourcen bereit, die das URI-Schema „file:“ verwenden. Dementsprechend werden die Klassen <xref:System.Net.FtpWebRequest> und <xref:System.Net.FtpWebResponse> zur Verarbeitung von Anforderungen für Ressourcen bereitgestellt, die das Schema „ftp:“ verwenden. Bei Anforderungen für eine Ressource, die eines dieser Schemas verwendet, können Sie mithilfe der **WebRequest.Create**-Methode ein Objekt abrufen, mit dem Sie die Anforderung erstellen können.  
  
 Bei Anforderungen, die andere Protokolle auf Anwendungsebene verwenden, müssen Sie von **WebRequest** und **WebResponse** abgeleitete protokollspezifische Klassen implementieren. Weitere Informationen finden Sie unter [Programming Pluggable Protocols (Programmieren austauschbarer Protokolle)](../../../docs/framework/network-programming/programming-pluggable-protocols.md).  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Anfordern von Daten mithilfe der WebRequest-Klasse](../../../docs/framework/network-programming/how-to-request-data-using-the-webrequest-class.md)
- [Anfordern von Daten](../../../docs/framework/network-programming/requesting-data.md)
