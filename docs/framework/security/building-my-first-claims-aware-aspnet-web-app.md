---
title: Erstellen meiner ersten Ansprüche unterstützenden ASP.NET Web-Anwendung
ms.date: 03/30/2017
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
author: BrucePerlerMS
ms.openlocfilehash: 900ee49b4bf51eeb6e3b0c0cf6879cc12a0cb071
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71045592"
---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a>Erstellen meiner ersten Ansprüche unterstützenden ASP.NET Web-Anwendung
## <a name="applies-to"></a>Gilt für  
  
- Windows Identity Foundation (WIF)  
  
- ASP.NET  
  
 In diesem Thema wird beschrieben, wie Ansprüche unterstützende ASP.NET-Webanwendungen mithilfe von WIF erstellt werden. Normalerweise sind an einem Szenario mit Ansprüche unterstützenden Anwendungen drei Parteien beteiligt: die Anwendung selbst, der Endbenutzer und der Sicherheitstokendienst (STS). Die folgende Abbildung beschreibt dieses Szenario:  
  
 ![Das Diagramm zeigt eine grundlegende WIF-Web-App-Komponente.](./media/building-my-first-claims-aware-aspnet-web-app/windows-identity-foundation-basic-web-application.gif)  
  
1. Die Ansprüche unterstützende Anwendung verwendet WIF, um nicht authentifizierte Anforderungen zu identifizieren und an den STS umzuleiten.  
  
2. Der Endbenutzer gibt Anmeldeinformationen für den STS ein, und nach erfolgreicher Authentifizierung gibt der STS ein Token für den Benutzer aus.  
  
3. Der Benutzer wird mit dem vom STS ausgegebenen Token in der Anforderung vom STS zur Ansprüche unterstützenden Anwendung umgeleitet.  
  
4. Die Ansprüche unterstützende Anwendung wird so konfiguriert, dass sie dem STS und den Token, die sie ausgibt, vertraut. Die Ansprüche unterstützende Anwendung verwendet WIF, um das Token zu überprüfen und zu analysieren. Entwickler verwenden die entsprechende WIF-API und -Typen wie **ClaimsPrincipal** für die Anforderungen der Anwendung, z.B. das Implementieren der entsprechenden Autorisierung.  
  
 Ab .NET 4.5 ist WIF Bestandteil von .NET Framework. Da die WIF-Klassen direkt im Framework selbst verfügbar sind, ist eine weitaus umfassendere Integration der anspruchsbasierten Identität in .NET möglich, sodass Ansprüche einfacher verwendet werden können. Mit WIF 4.5 müssen keine Out-of-Band-Komponenten installiert werden, um Ansprüche unterstützende Webanwendungen zu entwickeln. WIF-Klassen sind nun über mehrere Assemblys verteilt. Die wichtigsten Klassen hierbei sind System.Security.Claims, System.IdentityModel und System.IdentityModel.Services.  
  
 STS ist ein Dienst, der Token nach erfolgreicher Authentifizierung ausgibt. Microsoft bietet zwei STS-Dienste nach Industriestandard an:  
  
- [Active Directory-Verbunddienste (AD FS) (AD FS) 2,0](https://go.microsoft.com/fwlink/?LinkID=247516)
  
- [Windows Azure-Access Control Service (ACS)](https://go.microsoft.com/fwlink/?LinkID=247517)
  
 AD FS 2.0 ist Bestandteil von Windows Server R2 und kann als STS für lokale Szenarien verwendet werden. ACS ist ein Cloud-Dienst, der im Rahmen der Microsoft Azure-Plattform angeboten wird. Zu Test- oder Schulungszwecken können Sie auch andere STS verwenden, um die Ansprüche unterstützenden Anwendungen zu erstellen. Beispielsweise können Sie den lokalen Entwicklungs-STS verwenden, der Teil des [Identitäts-und Zugriffs Tools für Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) ist, das kostenlos online verfügbar ist.  
  
 Um die erste Ansprüche unterstützende ASP.NET-Anwendung mithilfe von WIF zu erstellen, befolgen Sie die Anweisungen in einem der folgenden Abschnitte:  
  
- [How To: Erstellen von Ansprüche unterstützenden ASP.NET MVC-Webanwendungen mithilfe von WIF](how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
- [How To: Erstellen von Ansprüche unterstützenden ASP.net Web Forms Anwendung mithilfe von WIF](how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
- [How To: Erstellen einer Ansprüche unterstützenden ASP.NET-Anwendung mit Formular basierter Authentifizierung](claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte mit WIF](getting-started-with-wif.md)
