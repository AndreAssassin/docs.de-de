---
title: .NET Core SDK-Telemetrie
description: Entdecken Sie die Telemetriefunktionen des .NET Core SDK, die Nutzungsinformationen für die Analyse darüber erfassen, welche Daten gesammelt werden. Erfahren Sie auch, wie Sie diese Features deaktivieren können.
author: richlander
ms.date: 06/20/2018
ms.custom: seodec18
ms.openlocfilehash: 85cceab08fc6e4108a5b951c8b67c1ad5a28f6bb
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/30/2019
ms.locfileid: "66377502"
---
# <a name="net-core-sdk-telemetry"></a>.NET Core SDK-Telemetrie

Das [.NET Core-SDK](index.md) beinhaltet eine [Telemetriefunktion](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry), die Benutzerinformationen sammelt. Es ist wichtig, dass das .NET-Team versteht, wie die Tools verwendet werden, damit sie verbessert werden können. Weitere Informationen finden Sie unter [What we've learned from .NET Core SDK Telemetry (Was wir von der .NET Core SDK Telemetrie gelernt haben)](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/).

Die gesammelten Daten sind anonym und werden unter der [Creative Commons Attribution-Lizenz](https://creativecommons.org/licenses/by/4.0/) in aggregierter Form für die Verwendung sowohl von Microsoft als auch von der Community veröffentlicht.

## <a name="scope"></a>Bereich

Der `dotnet`-Befehl wird zum Starten von sowohl Apps als auch .NET Core-CLI verwendet. Der `dotnet`-Befehl selbst sammelt keine Telemetrie. Die .NET Core-CLI-Befehle, die vom Befehl `dotnet` ausgeführt werden, sammeln die Telemetrie.

Die Telemetrie wird durch die Verwendung des Befehls `dotnet` allein *nicht aktiviert*, wenn kein Befehl angefügt ist:

- `dotnet`
- `dotnet [path-to-app]`

Die Telemetrie wird *aktiviert*, wenn Sie die [.NET Core-CLI-Befehle](index.md) verwenden, zum Beispiel:

- `dotnet build`
- `dotnet pack`
- `dotnet restore`
- `dotnet run`

## <a name="how-to-opt-out"></a>Deaktivierung der Telemetriefunktion

Die Telemetriefeature des .NET Core SDK ist standardmäßig aktiviert. Deaktivieren Sie die Telemetriefeature, indem Sie die Umgebungsvariable `DOTNET_CLI_TELEMETRY_OPTOUT` auf `1` oder `true` festlegen.

## <a name="data-points"></a>Datenpunkte

Die Funktion sammelt die folgenden Daten:

- Den Zeitstempel des Aufrufs&#8224;
- Den aufgerufenen Befehl (zum Beispiel „build“)&#8224;
- Die aus drei Oktetten bestehende IP-Adresse, die zur Bestimmung des geografischen Standorts verwendet wird
- `ExitCode` des Befehls
- Test Runner (für Testprojekte)
- Betriebssystem und Version&#8224;
- Ob Runtime-IDs im Knoten „Laufzeiten“ vorhanden sind
- Die .NET Core SDK-Version&#8224;

&#8224;Diese Metrik wird veröffentlicht.

Ab dem .NET Core 2.0 SDK werden neue Datenpunkte gesammelt:

- Argumente und Optionen des Befehls `dotnet`: nur bekannte Argumente und Optionen werden gesammelt (keine beliebigen Zeichenfolgen).
- Ob das SDK in einem Container ausgeführt wird.
- Zielframeworks.
- MAC-Adresse mit Hash: eine kryptografisch (SHA256) anonyme und eindeutige ID für einen Computer. Diese Metrik wird nicht veröffentlicht.
- Das derzeitige Arbeitsverzeichnis mit Hash.

Die Funktion sammelt keine Daten wie z.B. Benutzernamen oder E-Mail-Adressen. Es scannt Ihren Code nicht und extrahiert keine vertraulichen Daten auf Projektebene, zum Beispiel Name, Repository oder Autor. Die Daten werden mithilfe der Technologie [Microsoft Azure Application Insights](https://azure.microsoft.com/services/application-insights/) sicher an die Microsoft-Server gesendet, unter eingeschränktem Zugriff gespeichert und unter strikter Sicherheitskontrolle durch die Systeme von [Azure Storage](https://azure.microsoft.com/services/storage/) veröffentlicht.

Das .NET-Team ist daran interessiert, wie die Tools verwendet werden und ob sie gut funktionieren, nicht was Sie mit den Tools erstellen. Wenn Sie vermuten, dass durch die Telemetrie vertrauliche Daten gesammelt oder die Daten nicht sicher oder ordnungsgemäß behandelt werden, melden Sie ein Problem mit dem [dotnet/cli](https://github.com/dotnet/cli/issues)-Repository, damit dieses untersucht wird.

## <a name="published-data"></a>Veröffentlichte Daten

Veröffentlichte Daten sind vierteljährlich verfügbar und werden unter [.NET Core SDK Usage Data (.NET Core SDK Nutzungsdaten)](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md) aufgelistet. Die Spalten der Datendatei sind:

- Zeitstempel
- Occurrences&#8224;
- Befehl
- Geography&#8225;
- OSFamily
- RuntimeID
- OSVersion
- SDKVersion

Die Spalte *Occurences* zeigt die Gesamtanzahl der Verwendung dieses Befehls für die Metriken dieser Reihe an diesem Tag an.

&#8225;Die Spalte *Geography* zeigt normalerweise den Namen eines Landes oder einer Region an. In einigen Fällen wird der Kontinent Antarktis in dieser Spalte angezeigt. Dies geschieht entweder, weil Experten .NET Core in der Antarktis verwenden oder wegen falschen Standortdaten.

### <a name="example"></a>Beispiel

| Zeitstempel      | Occurrences | Befehl | Geography | OSFamily | RuntimeID     | OSVersion | SDKVersion |
| -------------- | ----------- | ------- | --------- | -------- | ------------- | --------- | ---------- |
| 4/16/2017 0:00 | 8           | Ausführung     | Uganda    | Darwin   | osx.10.12-x64 | 10.12     | 1.0.1      |

### <a name="datasets"></a>Datasets

- [2016 - Q3](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q3.tsv)
- [2016 - Q4](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2016-q4.tsv)
- [2017 - Q1](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q1.tsv)
- [2017 - Q2](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q2.tsv)
- [2017 – Q3](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q3.tsv)
- [2017 – Q4](https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-2017-q4.tsv)

Zusätzliche Datasets werden mithilfe des Standardformat für URLs bereitgestellt. Ersetzen Sie `<YEAR>` durch das Jahr und `<QUARTER>` durch das Quartal des Jahrs (verwenden Sie `1`, `2`, `3` oder `4`). Die Dateien befinden sich im Format einer durch Tabstopp getrennten Datei (*TSV*).

`https://dotnetcli.blob.core.windows.net/usagedata/dotnet-cli-usage-<YEAR>-q<QUARTER>.tsv`

## <a name="license"></a>Lizenz

Die Microsoft-Verteilung von .NET Core ist lizenziert gemäß den [Microsoft-Softwarelizenzbedingungen: Microsoft .NET-Bibliothek](https://aka.ms/dotnet-core-eula). Ausführlichere Informationen zur Datensammlung und -verarbeitung finden Sie im Abschnitt „Daten“.

[.NET NuGet-Pakete](https://www.nuget.org/profiles/dotnetframework) verwenden die gleiche Lizenz, aktivieren die Telemetrie jedoch nicht (siehe [Bereich](#scope)).

## <a name="disclosure"></a>Offenlegung

Im .NET Core SDK wird beim ersten Ausführen eines der [.NET Core-CLI-Befehle](index.md) (z.B. `dotnet restore`) der folgende Text angezeigt. Der Text kann abhängig von der von Ihnen ausgeführten Version des SDK leicht variieren. Über diese erste Ausführung benachrichtigt Microsoft Sie über die Datensammlung.

```console
Welcome to .NET Core!
---------------------
Learn more about .NET Core: https://aka.ms/dotnet-docs
Use 'dotnet --help' to see available commands or visit: https://aka.ms/dotnet-cli-docs

Telemetry
---------
The .NET Core tools collect usage data in order to help us improve your experience.
The data is anonymous and doesn't include command-line arguments.
The data is collected by Microsoft and shared with the community.
You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET Core CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

## <a name="see-also"></a>Siehe auch

- [What we've learned from .NET Core SDK Telemetry (Was wir von der .NET Core-SDK-Telemetrie gelernt haben)](https://devblogs.microsoft.com/dotnet/what-weve-learned-from-net-core-sdk-telemetry/)
- [Telemetrieverweisquelle (dotnet/cli-Repository)](https://github.com/dotnet/cli/tree/master/src/dotnet/Telemetry)
- [.NET Core SDK Usage Data (.NET Core SDK-Nutzungsdaten)](https://github.com/dotnet/core/blob/master/release-notes/cli-usage-data.md)
