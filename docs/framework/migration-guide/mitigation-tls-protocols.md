---
title: 'Entschärfung: TLS-Protokolle'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
ms.openlocfilehash: 45225d73ac60564d3e22c73270faab6b4e04d697
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73457837"
---
# <a name="mitigation-tls-protocols"></a>Entschärfung: TLS-Protokolle
Ab .NET Framework 4.6 dürfen die Klassen <xref:System.Net.ServicePointManager?displayProperty=nameWithType> und <xref:System.Net.Security.SslStream?displayProperty=nameWithType> eines der drei folgenden Protokolle verwenden: Tls1.0, Tls1.1 oder Tls 1.2. Weder das SSL3.0-Protokoll noch das RC4-Verschlüsselungsverfahren werden unterstützt.  
  
## <a name="impact"></a>Auswirkungen  
 Von dieser Änderung sind folgende Punkte betroffen:  
  
- Jede App, die SSL für die Kommunikation zu einem HTTPS- oder Socketserver mithilfe eines der folgenden Typen verwendet: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> und <xref:System.Net.Security.SslStream>.  
  
- Alle serverseitigen Apps, die nicht für die Unterstützung von Tls1.0, Tls1.1 oder Tls 1.2 aktualisiert werden können.  
  
## <a name="mitigation"></a>Minderung  
 Die empfohlene Minderung besteht darin, die serverseitige App auf Tls1.0, Tls1.1 oder Tls 1.2 zu aktualisieren. Wenn dies nicht möglich ist oder die Client-Apps fehlerhaft sind, kann die Klasse <xref:System.AppContext> verwendet werden, um das Feature auf zwei verschiedene Art und Weisen abzuwählen:  
  
- Programmgesteuert, durch die Verwendung eines Codeausschnitts wie dem Folgenden:  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     Da das <xref:System.Net.ServicePointManager>-Objekt nur einmal initialisiert wird, muss die Anwendung zunächst diese Kompatibilitätseinstellungen definieren.  
  
- Durch Hinzufügen der folgenden Zeile zum Abschnitt [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) Ihrer Datei „app.config“:  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 Beachten Sie jedoch, dass das Abwählen des Standardverhaltens nicht empfohlen wird, da die Anwendung dadurch unsichererer wird.  
  
## <a name="see-also"></a>Weitere Informationen

- [Anwendungskompatibilität](application-compatibility.md)
