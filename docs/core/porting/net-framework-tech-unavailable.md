---
title: .NET Framework-Technologien, die auf .NET Core nicht verfügbar sind
description: Erfahren Sie mehr über .NET Framework-Technologien, die in .NET Core nicht verfügbar sind
author: cartermp
ms.date: 04/30/2019
ms.openlocfilehash: e5626d7b3e402848e2e84c49d4e98e109f62982d
ms.sourcegitcommit: 337bdc5a463875daf2cc6883e5a2da97d56f5000
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2019
ms.locfileid: "72846815"
---
# <a name="net-framework-technologies-unavailable-on-net-core"></a>.NET Framework-Technologien, die auf .NET Core nicht verfügbar sind

Einige Technologien, die für .NET Framework-Bibliotheken verfügbar sind, sind für die Verwendung mit .NET Core nicht verfügbar, z.B. AppDomains, Remoting, Codezugriffssicherheit (Code Access Security, CAS) und Sicherheitstransparenz. Wenn Ihre Bibliotheken eine oder mehrere dieser Technologien benötigen, sollten Sie die unten beschriebenen alternativen Ansätze in Erwägung ziehen. Weitere Informationen zur API-Kompatibilität finden Sie im Artikel [Breaking Changes in .NET Core](../compatibility/breaking-changes.md).

Nur weil eine API oder Technologie derzeit nicht implementiert ist, bedeutet dies nicht zwangsläufig, dass sie absichtlich nicht unterstützt wird. Sie sollten zunächst die GitHub-Repositorys für .NET Core durchsuchen, um in Erfahrung zu bringen, ob bestimmte Probleme beabsichtigt sind. Wenn Sie jedoch keine Zeichen dafür finden können, melden Sie ein GitHub-Issue unter [dotnet/corefx repository issues (Issues im Repository „dotnet/corefx“)](https://github.com/dotnet/corefx/issues), um Fragen zu spezifischen APIs und Technologien zu stellen. [Portierte Anfragen in den Problemen](https://github.com/dotnet/corefx/labels/port-to-core) sind mit der Bezeichnung `port-to-core` markiert.

## <a name="appdomains"></a>AppDomains

Anwendungsdomänen (AppDomains) isolieren Apps voneinander. AppDomains benötigen eine Runtimeunterstützung und sind im Allgemeinen sehr teuer. Das Erstellen zusätzlicher Anwendungsdomänen wird nicht unterstützt. Wir planen nicht, diese Funktion in Zukunft hinzuzufügen. Für die Codeisolierung empfehlen wir separate Prozesse oder die Verwendung von Containern als Alternative. Für das dynamische Laden von Assemblys wird die neue Klasse <xref:System.Runtime.Loader.AssemblyLoadContext> empfohlen.

Zur Vereinfachung der Codemigration von .NET Framework stellt .NET Core einiges der <xref:System.AppDomain>-API-Oberfläche zur Verfügung. Manche Elemente der APIs funktionieren normal (z.B. <xref:System.AppDomain.UnhandledException?displayProperty=nameWithType>), einige Member führen keine Aktion aus (z.B. <xref:System.AppDomain.SetCachePath%2A>), und einige davon lösen <xref:System.PlatformNotSupportedException> aus (z.B. <xref:System.AppDomain.CreateDomain%2A>). Überprüfen Sie die Typen, die Sie für die [`System.AppDomain`-Verweisquelle](https://github.com/dotnet/corefx/blob/master/src/Common/src/CoreLib/System/AppDomain.cs) im [dotnet/corefx GitHub repository (dotnet/CoreFX-GitHub-Repository)](https://github.com/dotnet/corefx) verwenden. Stellen Sie dabei sicher, dass Sie den Branch auswählen, der mit Ihrer implementierten Version übereinstimmt.

## <a name="remoting"></a>Remoting

.NET-Remoting wurde als eine problematische Architektur identifiziert. Es wird für die AppDomain-übergreifende Kommunikation verwendet, die nicht mehr unterstützt wird. Darüber hinaus erfordert Remoting die Runtimeunterstützung, die teuer in der Wartung ist. Aus diesen Gründen wird .NET-Remoting auf .NET Core nicht unterstützt, und wir planen nicht, zukünftig eine Unterstützung dafür hinzuzufügen.

Für die Kommunikation zwischen Prozessen sollten Sie die Mechanismen der prozessübergreifenden Kommunikation (interprocess communication, IPC) als Alternative zu Remoting berücksichtigen, zB die Klassen <xref:System.IO.Pipes> oder <xref:System.IO.MemoryMappedFiles.MemoryMappedFile>.

Verwenden Sie computerübergreifend eine netzwerkbasierte Lösung als Alternative. Verwenden Sie vorzugsweise ein Nur-Text-Protokoll mit geringem Verwaltungsaufwand, z.B. HTTP. Der [Kestrel Webserver](https://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel), der von ASP.NET Core verwendete Webserver, ist hier eine Option. Ziehen Sie auch die Verwendung von <xref:System.Net.Sockets> für netzwerkbasierte, computerübergreifende Szenarios in Erwägung. Weitere Optionen finden Sie unter [.NET Open Source Developer Projects: Messaging (.NET Open Source-Entwicklerprojekte: Messaging)](https://github.com/Microsoft/dotnet/blob/master/dotnet-developer-projects.md#messaging).

## <a name="code-access-security-cas"></a>Codezugriffssicherheit (Code Access Security, CAS)

Das Verwenden einer Sandbox, das sich auf die Runtime oder das Framework verlässt, um einzuschränken, welche Ressourcen eine verwaltete Anwendung oder Bibliothek verwendet oder ausführt, [wird in .NET Framework nicht unterstützt](../../framework/misc/code-access-security.md). Daher wird es auch in .NET Core nicht unterstützt. Es gibt zu viele Fälle im .NET Framework und in der Runtime, in denen eine Rechteerweiterung auftritt, damit CAS weiterhin als Sicherheitsgrenze behandelt wird. Darüber hinaus macht CAS die Implementierung komplizierter und führt oft zu Auswirkungen auf die Leistung der Korrektheitsprüfung für Anwendungen, die dies nicht verwenden sollen.

Verwenden Sie vom Betriebssystem bereitgestellte Sicherheitsgrenzen, wie Virtualisierung, Container oder Benutzerkonten zum Ausführen von Prozessen mit den geringsten Rechten.

## <a name="security-transparency"></a>Sicherheitstransparenz

Ähnlich wie CAS trennt die Sicherheitstransparenz den Sandboxcode von sicherheitsrelevantem Code in einer deklarativen Weise, aber sie wird [nicht mehr als Sicherheitsgrenze unterstützt](../../framework/misc/security-transparent-code.md). Diese Funktion wird oft von Silverlight verwendet. 

Verwenden Sie vom Betriebssystem bereitgestellte Sicherheitsgrenzen, wie Virtualisierung, Container oder Benutzerkonten zum Ausführen von Prozessen mit den geringsten Rechten.

## <a name="systementerpriseservices"></a>System.EnterpriseServices

System.EnterpriseServices (COM+) wird von .NET Core nicht unterstützt.

>[!div class="step-by-step"]
>[Nächste](third-party-deps.md)
