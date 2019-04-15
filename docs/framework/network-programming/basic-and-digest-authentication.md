---
title: Standard- und Digestauthentifizierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- authentication [.NET Framework], classes
- Basic authentication
- authentication [.NET Framework], basic
- client authentication, basic
- user authentication, basic
- authentication [.NET Framework], digest
- receiving data, authentication
- client authentication, digest
- Internet, authentication
- digest authentication
- sending data, authentication
- network resources, authentication
- user authentication, digest
ms.assetid: 8cce2742-8d52-4643-9dd2-64ddf38aa878
ms.openlocfilehash: 4f70d2aef3bb064a3df9db9c87671040776332a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59089821"
---
# <a name="basic-and-digest-authentication"></a>Standard- und Digestauthentifizierung
Die <xref:System.Net>-Implementierung der einfachen und Digestauthentifizierung entspricht dem Dokument zur HTTP-Authentifizierung RCF 2617: „Basic and Digest Authentication“ (Einfache und Digestauthentifizierung), das auf der Website des [World Wide Web Consortium](https://www.w3.org) zum Download zur Verfügung steht.  
  
 Um Standard- und Digestauthentifizierung zu verwenden, muss eine Anwendung einen Benutzernamen und ein Kennwort in der <xref:System.Net.WebRequest.Credentials%2A>-Eigenschaft des <xref:System.Net.WebRequest>-Objekts bereitstellen, das zur Anforderung von Daten aus dem Internet verwendet wird, wie im folgenden Beispiel gezeigt.  
  
```vb  
Dim MyURI As String = "http://www.contoso.com/"  
Dim WReq As WebRequest = WebRequest.Create(MyURI)  
WReq.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword)  
```  
  
```csharp  
String MyURI = "http://www.contoso.com/";  
WebRequest WReq = WebRequest.Create(MyURI);  
WReq.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword);  
```  
  
> [!CAUTION]
>  Mittels Standard- und Hashwertauthentifizierung gesendete Daten sind nicht verschlüsselt und daher für Angreifer sichtbar. Anmeldeinformationen für die Standardauthentifizierung (Benutzername und Kennwort) werden zudem in Klartext gesendet und können abgefangen werden.  
  
## <a name="see-also"></a>Siehe auch

- [NTLM- und Kerberos-Authentifizierung](../../../docs/framework/network-programming/ntlm-and-kerberos-authentication.md)
- [Internetauthentifizierung](../../../docs/framework/network-programming/internet-authentication.md)
