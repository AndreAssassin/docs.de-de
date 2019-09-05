---
title: Entwicklungsprozess für auf Docker-basierende Anwendungen
description: Verschaffen Sie sich einen Überblick über die Möglichkeiten bei der Entwicklung von Docker-basierten Anwendungen. Sie haben die Wahl zwischen Visual Studio für Windows, Visual Studio für Mac oder Visual Studio Code für die Unterstützung mehrerer Plattformen (Windows, Mac und Linux).
ms.date: 09/27/2018
ms.openlocfilehash: a32b27f3d98ed7ebf63b637ec0c979c22ee8e1e8
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "70295138"
---
# <a name="development-process-for-docker-based-applications"></a>Entwicklungsprozess für auf Docker-basierende Anwendungen

*Entwickeln Sie .NET-Containeranwendungen nach Ihren Wünschen, egal ob mit Fokus auf IDE mit Visual Studio und Visual Studio-Tools für Docker oder mit Fokus auf CLI/Editor mit Docker-CLI und Visual Studio Code.*

## <a name="development-environment-for-docker-apps"></a>Entwicklungsumgebung für Docker-Apps

### <a name="development-tool-choices-ide-or-editor"></a>Auswahlmöglichkeiten für das Entwicklungstool: IDE oder Editor

Egal, ob Sie eine vollständige und leistungsstarke integrierte Entwicklungsumgebung (IDE) oder einen einfachen und agilen Editor bevorzugen: Microsoft bietet Ihnen Tools, die Sie zum Entwickeln von Docker-Anwendungen verwenden können.

**Visual Studio (für Windows)** Bei der Entwicklung von Docker-basierten Anwendungen mit Visual Studio wird empfohlen, Visual Studio 2017 Version 15.7 oder höher zu verwenden, bei dem bereits integrierte Tools für Docker im Lieferumfang enthalten sind. Mit den Tools für Docker können Sie Ihre Anwendungen direkt in der Docker-Zielumgebung entwickeln, ausführen und überprüfen. Sie können F5 drücken, um Ihre Anwendungen (einzelner oder mehrere Container) direkt in einem Docker-Host auszuführen und zu debuggen. Alternativ drücken Sie STRG+F5, um Ihre Anwendungen zu bearbeiten und zu aktualisieren, ohne den Container erneut erstellen zu müssen. Dies ist die leistungsstärkste Entwicklungsoption für Docker-basierte Anwendungen.

**Visual Studio für Mac** Dies ist die weiterentwickelte IDE von Xamarin Studio, die unter macOS ausgeführt wird und Docker seit Mitte 2017 unterstützt. Dies sollte die bevorzugte Wahl für Entwickler sein, die auf Mac-Computern arbeiten und eine leistungsfähige IDE verwenden möchten.

**Visual Studio Code und Docker-CLI** Wenn Sie einen einfachen und plattformübergreifenden Editor bevorzugen, der jede beliebige Entwicklungssprache unterstützt, können Sie Microsoft Visual Studio Code (VS Code) sowie die Docker-CLI verwenden. Dies ist ein plattformübergreifender Entwicklungsansatz für Mac, Linux und Windows. Zusätzlich unterstützt Visual Studio Code Erweiterungen für Docker, z.B. IntelliSense für Docker-Dateien und Verknüpfungsaufgaben, um Docker-Befehle aus dem Editor auszuführen.

Durch Installation von [Docker Desktop Community Edition (CE)](https://hub.docker.com/search/?type=edition&offering=community) können Sie eine einzelne Docker-CLI zum Erstellen von Apps für Windows und Linux verwenden.

### <a name="additional-resources"></a>Zusätzliche Ressourcen

- **Visual Studio**. Offizielle Website. \
  [https://visualstudio.microsoft.com/vs/](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)

- **Visual Studio Code**. Offizielle Website. \
  <https://code.visualstudio.com/download>

- **Docker Desktop für Windows Community Edition (CE)**  \
  [https://hub.docker.com/editions/community/docker-ce-desktop-windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows)
  
- **Docker Desktop für Mac Community Edition (CE)**  \
  [https://hub.docker.com/editions/community/docker-ce-desktop-mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>.NET-Sprachen und -Frameworks für Docker-Container

Wie in vorherigen Abschnitten diese Handbuchs erwähnt, können Sie .NET Framework, .NET Core oder das Open-Source-Mono-Projekt verwenden, wenn Sie .NET-Containeranwendungen für Docker entwickeln. Sie können C\#, F\# oder Visual Studio entwickeln, wenn Sie Linux- oder Windows-Container als Ziel haben, je nachdem, welches .NET-Framework verwendet wird. Weitere Details zu .NET-Sprachen finden Sie im Blogbeitrag [The .NET Language Strategy (Strategie für die .NET-Sprache)](https://devblogs.microsoft.com/dotnet/the-net-language-strategy/).

>[!div class="step-by-step"]
>[Zurück](../architect-microservice-container-applications/scalable-available-multi-container-microservice-applications.md)
>[Weiter](docker-app-development-workflow.md)
