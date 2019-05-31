---
title: Verpacken einer Verteilung von .NET Core
description: Erfahren Sie, wie Sie .NET Core für die Verteilung verpacken, benennen und mit einer Versionsnummer versehen.
author: tmds
ms.date: 03/02/2018
ms.custom: seodec18
ms.openlocfilehash: b961d84053dc41e75e002c8c12419fdef99ded4b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64585256"
---
# <a name="net-core-distribution-packaging"></a>Verpacken einer Verteilung von .NET Core

Da .NET Core auf immer mehr Plattformen verfügbar wird, ist es hilfreich zu erfahren, wie man es verpackt, benennt und mit einer Versionsnummer versieht. Auf diese Weise kann mithilfe von Paketverwaltern eine konsistente Benutzererfahrung sichergestellt werden, unabhängig davon, wo Benutzer .NET ausführen. Dieser Artikel ist für Benutzer hilfreich, die

* versuchen, .NET Core von der Quelle aus zu erstellen.
* Änderungen an der .NET Core-CLI vornehmen möchten, die sich auf das resultierende Layout oder die erzeugten Pakete auswirken könnten.

## <a name="disk-layout"></a>Datenträgerlayout

.NET Core besteht aus mehreren Komponenten, die im Dateisystem folgendermaßen angeordnet sind:

```
.
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host
│   └── fxr
│       └── <fxr version>        (2)
├── sdk
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)
└── shared
    ├── Microsoft.NETCore.App
    │   └── <runtime version>    (5)
    └── Microsoft.AspNetCore.App
        └── <aspnetcore version> (6)
    └── Microsoft.AspNetCore.All
        └── <aspnetcore version> (7)
/
├─usr/share/man/man1
│       └── dotnet.1.gz          (9)
└─usr/bin
        └── dotnet               (10)
```

- (1) **dotnet**: Der Host (auch bekannt als „Muxer“) führt zwei unterschiedliche Rollen aus: das Aktivieren einer Runtime, um eine Anwendung zu starten, und das Aktivieren eines SDK, um Befehle an dieses weiterzuleiten. Der Host ist eine native ausführbare Datei (`dotnet.exe`).

Es gibt nur einen Host, die meisten anderen Komponenten befinden sich jedoch in Verzeichnissen mit Versionsangabe (2, 3, 5, 6). Das bedeutet, dass auf dem System mehrere Versionen vorhanden sein können, da sie nebeneinander installiert werden können.

- (2) **host/fxr/\<fxr version>** : Enthält die vom Host verwendete Framework-Auflösungslogik. Der Host verwendet die neueste installierte hostfxr-Version. „hostfxr“ ist für die Auswahl der geeigneten Runtime beim Ausführen einer .NET Core-Anwendung zuständig. Eine Anwendung, die für .NET Core 2.0.0 erstellt wurde, verwendet beispielsweise die Runtime 2.0.5, wenn sie verfügbar ist. Ebenso wählt „hostfxr“ während der Entwicklung das geeignete SDK aus.

- (3) **sdk/\<sdk version>** : Das SDK (auch bekannt als „die Tools“) ist ein Satz verwalteter Tools, die zum Schreiben und Erstellen von .NET Core-Bibliotheken und -Anwendungen verwendet werden. Das SDK enthält die .NET Core-Befehlszeilenschnittstelle (Command-Line Interface, CLI), die verwalteten Sprachencompiler, MSBuild und zugeordnete Buildaufgaben und Ziele, NuGet, neue Projektvorlagen usw.

- (4) **sdk/NuGetFallbackFolder** enthält einen Cache der NuGet-Pakete, die von einem SDK während der Wiederherstellung verwendet werden, etwa bei der Ausführung von `dotnet restore` oder `dotnet build /t:Restore`.

Der Ordner **shared** enthält Frameworks. Ein gemeinsames (shared) Framework stellt einen Satz Bibliotheken an einem zentralen Speicherort bereit, sodass diese von verschiedenen Anwendungen verwendet werden können.

- (5) **shared/Microsoft.NETCore.App/\<runtime version>** : Dieses Framework enthält die .NET-Runtime und die unterstützenden verwalteten Bibliotheken.

- (6, 7) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** : Enthält die ASP.NET Core-Bibliotheken. Die Bibliotheken unter `Microsoft.AspNetCore.App` werden im Rahmen des .NET Core-Projekts entwickelt und unterstützt. Die Bibliotheken unter `Microsoft.AspNetCore.All` sind ein übergeordnetes Set, das auch Drittanbieterbibliotheken enthält.

- (8) **LICENSE.txt,ThirdPartyNotices.txt**: Dies sind die .NET Core-Lizenzen und die Lizenzen von Drittanbieterbibliotheken, die in .NET Core jeweils verwendet werden.

- (9, 10) **dotnet.1.gz, dotnet**: `dotnet.1.gz` ist die Dotnet-Handbuchseite. `dotnet` ist eine symbolische Verknüpfung mit dem Dotnet-Host (1). Diese Dateien werden zur Systemintegration an bekannten Speicherorten installiert.

## <a name="recommended-packages"></a>Empfohlene Pakete

Die .NET Core-Versionierung basiert auf dem Versionsnummernmuster `[major].[minor]` der Runtimekomponente.
Die SDK-Version verwendet das gleiche `[major].[minor]`-Muster und weist eine unabhängige `[patch]`-Zeichenfolge auf, die die Feature- und Patchsemantik für das SDK kombiniert.
Beispiel: Die SDK-Version 2.2.302 ist das zweite Patchrelease des dritten Featurerelease des SDK, das die Runtimeversion 2.2 unterstützt. Weitere Informationen zur Funktionsweise der Versionsverwaltung finden Sie unter [.NET Core-Versionskontrolle: Übersicht](../versions/index.md).

Einige Pakete enthalten einen Teil der Versionsnummer im Namen. Dies ermöglicht Ihnen, eine bestimmte Version zu installieren.
Der Rest der Version ist im Versionsnamen nicht enthalten. Dies ermöglicht dem Paket-Manager des Betriebssystems, die Pakete zu aktualisieren (z.B. durch automatisches Installieren von Sicherheitsfixes). Unterstützte Paket-Manager sind Linux-spezifisch.

Die folgende Tabelle zeigt die empfohlenen Pakete:

| name                                    | Beispiel                | Anwendungsfall: Installieren von ...           | Enthält           | Abhängigkeiten                                   | Version            |
|-----------------------------------------|------------------------|---------------------------------|--------------------|------------------------------------------------|--------------------|
| dotnet-sdk-[major]                      | dotnet-sdk-2           | Das neueste SDK für die Hauptversion der Runtime    |                    | dotnet-sdk-[major].[latestminor]               | \<SDK-Version>     |
| dotnet-sdk-[major].[minor]              | dotnet-sdk-2.1         | Das neueste SDK für die spezifische Runtime |                    | dotnet-sdk-[major].[minor].[latest sdk feat]xx | \<SDK-Version>     |
| dotnet-sdk-[major].[minor].[sdk feat]xx | dotnet-sdk-2.1.3xx     | Ein bestimmtes SDK-Featurerelease    | (3), (4)            | aspnetcore-runtime-[major].[minor]             | \<SDK-Version>     |
| aspnetcore-runtime-[major].[minor]      | aspnetcore-runtime-2.1 | Eine spezifische ASP.NET Core-Runtime   | (6), [(7)]          | dotnet-runtime-[major].[minor]                 | \<Runtimeversion> |
| dotnet-runtime-[major].[minor]          | dotnet-runtime-2.1     | Eine spezifische Runtime                | (5)                | host-fxr:\<Runtimeversion>+                   | \<Runtimeversion> |
| dotnet-host-fxr                         | dotnet-host-fxr        | _Abhängigkeit_                    | (2)                | host:\<Runtimeversion>+                       | \<Runtimeversion> |
| dotnet-host                             | dotnet-host            | _Abhängigkeit_                    | (1), (8), (9), (10)   |                                                | \<Runtimeversion> |

Für die meisten Verteilungen müssen alle Artefakte aus der Quelle erstellt werden. Dies wirkt sich auf die Pakete aus:

- Die Drittanbieterbibliotheken unter `shared/Microsoft.AspNetCore.All` können nicht einfach aus der Quelle erstellt werden. Daher ist dieser Ordner im `aspnetcore-runtime`-Paket nicht enthalten.

- Der `NuGetFallbackFolder` wird mithilfe von binären Artefakten aus `nuget.org` aufgefüllt. Der Ordner sollte leer bleiben.

Möglicherweise stellen mehrere `dotnet-sdk`-Pakete die gleichen Dateien für den `NuGetFallbackFolder` bereit. Um Probleme mit dem Paket-Manager zu vermeiden, sollten diese Dateien identisch sein (Prüfsumme, Änderungsdatum usw.).

### <a name="preview-versions"></a>Vorschauversionen

Paketverwalter können möglicherweise Vorschauversionen des gemeinsam genutzten Frameworks und des SDK einschließen. Vorschauversionen können mithilfe der Pakete `dotnet-sdk-[major].[minor].[sdk feat]xx`, `aspnetcore-runtime-[major].[minor]` oder `dotnet-runtime-[major].[minor]` bereitgestellt werden. Bei Vorschauversionen muss die Hauptversion des Pakets auf 0 festgelegt werden. Auf dieses Weise wird das endgültige Release als Upgrade des Pakets installiert.

### <a name="patch-packages"></a>Patchpakete

Da eine Patchversion eines Pakets Änderungen mit Auswirkung auf die Lauffähigkeit mit sich bringen kann, sollte ein Paketverwalter _Patchpakete_ bereitstellen. Diese Pakete ermöglichen Ihnen die Installation einer bestimmten Patchversion, für die nicht automatisch ein Upgrade durchgeführt wird. Verwenden Sie Patchpakete nur in seltenen Fällen, da sie bei Fixes (bzw. Sicherheitsfixes) nicht aktualisiert werden.

Die folgende Tabelle zeigt die empfohlenen Pakete und **Patchpakete**:

| name                                           | Beispiel                  | Enthält         | Abhängigkeiten                                              |
|------------------------------------------------|--------------------------|------------------|-----------------------------------------------------------|
| dotnet-sdk-[major]                             | dotnet-sdk-2             |                  | dotnet-sdk-[major].[latest sdk minor]                     |
| dotnet-sdk-[major].[minor]                     | dotnet-sdk-2.1           |                  | dotnet-sdk-[major].[minor].[latest sdk feat]xx            |
| dotnet-sdk-[major].[minor].[sdk feat]xx        | dotnet-sdk-2.1.3xx       |                  | dotnet-sdk-[major].[minor].[latest sdk patch]             |
| **dotnet-sdk-[major].[minor].[patch]**         | dotnet-sdk-2.1.300       | (3), (4)          | aspnetcore-runtime-[major].[minor].[sdk runtime patch]    |
| aspnetcore-runtime-[major].[minor]             | aspnetcore-runtime-2.1   |                  | aspnetcore-runtime-[major].[minor].[latest runtime patch] |
| **aspnetcore-runtime-[major].[minor].[patch]** | aspnetcore-runtime-2.1.0 | (6), [(7)]        | dotnet-runtime-[major].[minor].[patch]                    |
| dotnet-runtime-[major].[minor]                 | dotnet-runtime-2.1       |                  | dotnet-runtime-[major].[minor].[latest runtime patch]     |
| **dotnet-runtime-[major].[minor].[patch]**     | dotnet-runtime-2.1.0     | (5)              | host-fxr:\<Runtimeversion>+                              |
| dotnet-host-fxr                                | dotnet-host-fxr          | (2)              | host:\<Runtimeversion>+                                  |
| dotnet-host                                    | dotnet-host              | (1), (8), (9), (10) |                                                           |

Eine Alternative zur Verwendung von Patchpaketen ist das _Anheften_ der Pakete an eine bestimmte Version mithilfe des Paket-Managers. Um Auswirkungen auf andere Anwendungen/Benutzer zu vermeiden, können solche Anwendungen in einem Container erstellt und bereitgestellt werden.

## <a name="building-packages"></a>Erstellen von Paketen

Das Repository [dotnet/source-build](https://github.com/dotnet/source-build) stellt Anweisungen zum Erstellen eines Quell-Tarballs des .NET Core SDK und aller zugehörigen Komponenten bereit. Die Ausgabe des source-build-Repositorys entspricht der Anordnung, die im ersten Abschnitt dieses Artikels beschrieben wurde.
