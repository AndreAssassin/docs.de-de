---
title: Codezugriffssicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- named permission sets, code access security
- call stacks
- malicious code
- stack walk
- security [.NET Framework], code access security
- permissions [.NET Framework], code access security
- trusted code
- mobile code security
- unmanaged code, code access security
- granting permissions, code access security
- user authentication, code access security
- code access security
ms.assetid: 859af632-c80d-4736-8d6f-1e01b09ce127
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aa256fe95013494488ff52258186763fab7a85c9
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456654"
---
# <a name="code-access-security"></a>Codezugriffssicherheit
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Die heutigen hochgradig vernetzten Computersysteme sind häufig Code ausgesetzt, der aus unterschiedlichen, teilweise auch unbekannten Quellen stammt. Code kann an e-Mail-Adresse zugeordnet, in Dokumenten enthaltenen oder über das Internet heruntergeladen werden. Viele Computerbenutzer haben leider die Auswirkungen von bösartigem mobilem Code hautnah zu spüren bekommen, beispielsweise von Viren und Würmern, die Daten beschädigen oder zerstören können und deren Beseitigung zeit- und kostenintensiv ist.  
  
 Bei den gängigen Sicherheitsverfahren werden Benutzern Rechte auf Grundlage ihrer Anmeldeinformationen (üblicherweise des Kennworts) erteilt, und der Zugriff auf Ressourcen, bei denen es sich häufig um Verzeichnisse und Dateien handelt, wird eingeschränkt. Bei diesem Ansatz bleiben jedoch einige Aspekte unberücksichtigt: Benutzer erhalten Code aus zahlreichen Quellen, von denen einige möglicherweise unzuverlässig oder nicht vertrauenswürdig sind. Code kann Fehler oder Sicherheitsrisiken enthalten, die von bösartigem Code ausgenutzt werden können. Und in manchen Fällen kann Code zu unerwartetem Verhalten führen. Daher können Computersysteme beschädigt werden und private Daten in die falschen Hände gelangen, wenn umsichtige und vertrauenswürdige Benutzer schädliche oder fehlerhafte Software ausführen. Bei den meisten Sicherheitsmechanismen von Betriebssystemen muss sämtlicher Code vollständig vertrauenswürdig sein, um ausgeführt werden zu können. Skripts auf einer Webseite können davon ausgenommen sein. Daher ist nach wie vor ein umfassend anwendbarer Sicherheitsmechanismus erforderlich, der die geschützte Ausführung von Code eines Computersystems auf einem anderen System ermöglicht, selbst wenn keine gegenseitige Vertrauensstellung der Systeme besteht.  
  
 .NET Framework bietet einen Sicherheitsmechanismus namens Codezugriffssicherheit, der Computersysteme vor bösartigem, mobilem Code schützt, die geschützte Ausführung von Code unbekannter Herkunft ermöglicht und die absichtliche oder unabsichtliche Verletzung der Sicherheit durch vertrauenswürdigen Code verhindert. Mithilfe der Codezugriffssicherheit können für Code aufgrund des Ursprungs und weiterer Identitätsaspekte verschiedene Vertrauensebenen festgelegt werden. Die Codezugriffssicherheit erzwingt auch die verschiedenen Vertrauensebenen für Code, wodurch die Menge an Code, für dessen Ausführung vollständige Vertrauenswürdigkeit erforderlich ist, minimiert wird. Durch die Codezugriffssicherheit kann die Wahrscheinlichkeit verringert werden, dass Ihr Code durch bösartigen oder fehlerhaften Code missbraucht wird. Außerdem kann dadurch Ihre Haftung verringert werden, weil Sie die Vorgänge angeben können, die vom Code ausgeführt werden dürfen. Die Codezugriffssicherheit kann auch den Schaden begrenzen, der durch Sicherheitsschwachstellen im Code entstehen kann.  
  
> [!NOTE]
>  In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] wurden wesentliche Änderungen an der Codezugriffssicherheit vorgenommen. Die wichtigste Änderung wurde [Sicherheitstransparenz](../../../docs/framework/misc/security-transparent-code.md), aber es gibt auch andere wichtige Änderungen, die sich auf die Codezugriffssicherheit auswirken. Weitere Informationen zu diesen Änderungen finden Sie unter [Sicherheitsänderungen](../../../docs/framework/security/security-changes.md).  
  
 Die Codezugriffssicherheit wirkt sich in erster Linie auf Bibliothekscode und teilweise vertrauenswürdige Anwendungen aus. Entwickler von Bibliotheken müssen ihren Code vor nicht autorisiertem Zugriff von teilweise vertrauenswürdigen Anwendungen schützen. Teilweise vertrauenswürdige Anwendungen sind Anwendungen, die aus externen Quellen (wie z. B. dem Internet) geladen werden. Auf dem Desktop oder im lokalen Intranet installierte Anwendungen werden mit vollständiger Vertrauenswürdigkeit ausgeführt. Voll vertrauenswürdige Anwendungen sind von der Codezugriffssicherheit nicht betroffen, es sei denn, sie als markiert sind [sicherheitstransparent](../../../docs/framework/misc/security-transparent-code.md), da sie voll vertrauenswürdig sind. Die einzige Einschränkung für Anwendungen mit vollständiger Vertrauenswürdigkeit ist, dass mit dem <xref:System.Security.SecurityTransparentAttribute>-Attribut markierte Anwendungen keinen Code aufrufen können, der mit dem <xref:System.Security.SecurityCriticalAttribute>-Attribut markiert ist. Teilweise vertrauenswürdige Anwendungen müssen in einem Sandkasten (z. B. in Internet Explorer) ausgeführt werden, damit die Codezugriffssicherheit angewendet werden kann. Wenn Sie eine Anwendung aus dem Internet herunterladen, und versuchen es auf Ihrem Desktop, ausführen, erhalten Sie eine <xref:System.NotSupportedException> mit der Meldung: "Es wurde versucht, eine Assembly über ein Netzwerk zu laden, wodurch die Sandbox in früheren Versionen von .NET Framework werden die Assembly verursacht hätte. In dieser Version von .NET Framework wird die CAS-Richtlinie standardmäßig nicht aktiviert, dieser Ladevorgang kann daher gefährlich sein." Wenn Sie sicher sind, dass die Anwendung vertrauenswürdig ist, können Sie aktivieren, es als voll vertrauenswürdig ausgeführt werden, mithilfe der [ \<LoadFromRemoteSources >-Element](../../../docs/framework/configure-apps/file-schema/runtime/loadfromremotesources-element.md). Informationen zum Ausführen von Anwendungen in einem Sandkasten finden Sie unter [Vorgehensweise: Ausführen von teilweise vertrauenswürdigem Code in einem Sandkasten](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md) beschrieben.  
  
 Die Vorteile der Codezugriffssicherheit gelten für den gesamten verwalteten Code, der für die Common Language Runtime geschrieben wird, auch wenn dieser Code die Codezugriffssicherheit nicht aufruft. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](../../../docs/framework/misc/code-access-security-basics.md).  
  
<a name="key_functions"></a>   
## <a name="key-functions-of-code-access-security"></a>Hauptfunktionen der Codezugriffssicherheit  
 Mithilfe der Codezugriffssicherheit wird der Zugriff von Code auf geschützte Ressourcen und Vorgänge eingeschränkt. In .NET Framework erfüllt die Codezugriffssicherheit die folgenden Funktionen:  
  
- Definieren von Berechtigungen und Berechtigungssätzen, die den Zugriff auf die verschiedenen Systemressourcen regeln  
  
- Bereitstellen der Möglichkeit für Code festzulegen, dass seine Aufrufer bestimmte Berechtigungen haben müssen  
  
- Bereitstellen der Möglichkeit für Code festzulegen, dass seine Aufrufer eine digitale Signatur besitzen müssen, sodass der geschützte Code nur von Aufrufern eines bestimmten Unternehmens oder eines bestimmten Standorts aufgerufen werden kann  
  
- Durchsetzen von Einschränkungen für Code zur Laufzeit, indem die erteilten Berechtigungen der einzelnen Aufrufer in der Aufrufliste mit den Berechtigungen verglichen werden, die sie besitzen müssen  
  
<a name="walking_the_call_stack"></a>   
## <a name="walking-the-call-stack"></a>Durchlaufen der Aufrufliste  
 Zur Bestimmung, ob Code auf eine Ressource zugreifen oder einen Vorgang ausführen darf, durchläuft das Laufzeit-Sicherheitssystem die Aufrufliste und vergleicht dabei die erteilten Berechtigungen der einzelnen Aufrufer mit den angeforderten Berechtigungen. Wenn einer der Aufrufer in der Aufrufliste nicht über die angeforderte Berechtigung verfügt, wird eine Sicherheitsausnahme ausgelöst, und der Zugriff wird verweigert. Mit dem Stackwalk sollen Lockangriffe verhindert werden, bei denen weniger vertrauenswürdiger Code äußerst vertrauenswürdigen Code aufruft und verwendet, um nicht autorisierte Aktionen auszuführen. Das Anfordern von Berechtigungen für alle Aufrufer zur Laufzeit beeinträchtigt die Leistung, aber es ist wichtig, den Code vor Lockangriffen durch weniger vertrauenswürdigen Code zu schützen. Zum Optimieren der Leistung können Sie dafür sorgen, dass der Code weniger Stackwalks durchläuft. Sie müssen dabei jedoch unbedingt darauf achten, dass kein Sicherheitsrisiko entsteht.  
  
 In der folgenden Abbildung ist der Stackwalk dargestellt, der entsteht, wenn eine Methode in Assembly A4 fordert, dass ihre Aufrufer über Berechtigung P verfügen.  
  
 ![Codezugriffssicherheit](../../../docs/framework/misc/media/slide-10a.gif "slide_10a")  
Sicherheits-Stackwalk  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Grundlagen der Codezugriffssicherheit](../../../docs/framework/misc/code-access-security-basics.md)|Beschreibt die Codezugriffssicherheit und die häufigsten Anwendungsbereiche.|  
|[Sicherheitstransparenter Code, Ebene 2](../../../docs/framework/misc/security-transparent-code-level-2.md)|Beschreibt das Sicherheitstransparenzmodell in .NET Framework 4.|  
|[Verwenden von Bibliotheken aus teilweise vertrauenswürdigem Code](../../../docs/framework/misc/using-libraries-from-partially-trusted-code.md)|Beschreibt das Aktivieren von Bibliotheken zur Verwendung mit nicht verwaltetem Code und das Verwenden von Bibliotheken aus nicht verwaltetem Code.|  
|[Schlüsselbegriffe der Sicherheit](../../../docs/standard/security/key-security-concepts.md)|Bietet eine Übersicht über viele Schlüsselbegriffe und -konzepte, die im Sicherheitssystem von .NET Framework verwendet werden.|  
|[Rollenbasierte Sicherheit](../../../docs/standard/security/role-based-security.md)|Beschreibt die Integration von Sicherheit basierend auf Rollen.|  
|[Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)|Beschreibt die Integration von Kryptografie in Anwendungen.|
