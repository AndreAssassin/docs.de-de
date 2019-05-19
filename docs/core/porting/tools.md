---
title: Tools für das Portieren zu .NET Core
description: Erfahren Sie mehr über einige der Tools, die Sie zum Portieren zu .NET Core verwenden können.
author: cartermp
ms.author: mairaw
ms.date: 12/07/2018
ms.openlocfilehash: d0b74b5708f31922b72fa0e236c8bbe69ae06217
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632252"
---
# <a name="tools-to-help-with-porting-to-net-core"></a>Tools für das Portieren zu .NET Core

Die folgenden, in diesem Artikel aufgeführten Tools können sich beim Portieren als nützlich erweisen:

* [.NET Portability Analyzer:](../../standard/analyzers/portability-analyzer.md) Hierbei handelt es sich um eine Toolkette, mit der ein Bericht darüber generiert werden kann, wie portabel Ihr Code zwischen .NET Framework und .NET Core ist:  Als [Befehlszeilentool](https://github.com/Microsoft/dotnet-apiport/releases) oder als [Visual Studio-Erweiterung](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b).
* [.NET API-Analysetool:](../../standard/analyzers/api-analyzer.md) Hierbei handelt es sich um ein Roslyn-Analysetool, das potenzielle Kompatibilitätsrisiken für C#-APIs auf verschiedenen Plattformen erkennt und Aufrufe an veraltete APIs ermittelt.

Darüber hinaus können Sie mit dem Tool [CsprojToVs2017](https://github.com/hvanbakel/CsprojToVs2017) versuchen, kleinere Lösungen oder einzelne Projekte auf das .NET Core-Projektdateiformat zu portieren.

> [!WARNING] 
> CsprojToVs2017 ist ein Drittanbietertool. Es kann nicht garantiert werden, dass das Tool für all Ihre Projekte funktioniert, und es kann zu subtilen Änderungen bei Verhalten kommen, von dem Sie abhängig sind. CsprojToVs2017 sollte als _Ausgangspunkt_ verwendet werden, um grundlegende Elemente zu automatisieren. Es handelt sich nicht um ein garantierte Lösung zum Migrieren von Projektdateiformaten.
