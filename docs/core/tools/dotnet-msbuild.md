---
title: Befehl „dotnet msbuild“
description: Der Befehl dotnet msbuild ermöglicht den Zugriff auf die MSBuild-Befehlszeile.
ms.date: 12/03/2018
ms.openlocfilehash: 983fae6f4ecf875da0b155a668009984b5df50de
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632033"
---
# <a name="dotnet-msbuild"></a>dotnet msbuild

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet msbuild`: Erstellt ein Projekt und alle seine Abhängigkeiten

## <a name="synopsis"></a>Übersicht

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a>Beschreibung

Der `dotnet msbuild`-Befehl ermöglicht den Zugriff auf eine voll funktionsfähige MSBuild-Instanz.

Der Befehl weist genau die gleichen Funktionen wie der vorhandene MSBuild-Befehlszeilenclient für ausschließlich im SDK-Stil geschriebene Projekte auf. Alle Optionen sind gleich. Weitere Informationen zu den verfügbaren Optionen finden Sie in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).

Der [dotnet build](dotnet-build.md)-Befehl ist äquivalent zu `dotnet msbuild -restore -target:Build`. `dotnet build` wird häufiger zum Erstellen von Projekten verwendet, aber mit `dotnet msbuild` haben Sie mehr Kontrolle. Wenn Sie z.B. ein bestimmtes Ausführungsziel haben (ohne Ausführung des Buildziels), verwenden Sie wahrscheinlich `dotnet msbuild`.

## <a name="examples"></a>Beispiele

* Erstellt ein Projekt und seine Abhängigkeiten:

  ```console
  dotnet msbuild
  ```

* Erstellt ein Projekt und seine Abhängigkeiten mithilfe der Release-Konfiguration:

  ```console
  dotnet msbuild -p:Configuration=Release
  ```

* Führt das Veröffentlichungsziel aus und veröffentlicht für die RID `osx.10.11-x64`:

  ```console
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* Zeigen Sie das gesamte Projekt mit allen Zielen an, die über das SDK eingeschlossen werden:

  ```console
  dotnet msbuild -pp
  ```
