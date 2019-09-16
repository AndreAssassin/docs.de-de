---
title: Versionsverwaltung und .NET-Bibliotheken
description: Empfehlungen für bewährte Methoden für die Versionsverwaltung für .NET-Bibliotheken.
author: jamesnk
ms.author: mairaw
ms.date: 12/10/2018
ms.openlocfilehash: 9250e48707c0ea72cdf8bef9663f5a3516309b86
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2019
ms.locfileid: "70969006"
---
# <a name="versioning"></a>Versionskontrolle

Eine Softwarebibliothek ist in Version 1.0 nur selten vollständig. Gute Bibliotheken entwickeln sich im Laufe der Zeit weiter, indem Funktionen hinzugefügt, Fehler behoben und die Leistung verbessert werden. Es ist wichtig, dass Sie neue Versionen einer .NET-Bibliothek freigeben können, die mit jeder Version einen zusätzlichen Wert bieten, ohne bestehende Benutzer zu beeinträchtigen.

## <a name="breaking-changes"></a>Breaking Changes

Weitere Informationen zur Verarbeitung von Breaking Changes zwischen den Versionen finden Sie unter [Breaking Changes](./breaking-changes.md).

## <a name="version-numbers"></a>Versionsnummern

Bei einer .NET-Bibliothek gibt es viele Möglichkeiten, eine Version angeben. Diese Versionen sind die wichtigsten:

### <a name="nuget-package-version"></a>NuGet-Paketversion

Die [NuGet-Paketversion](/nuget/reference/package-versioning) wird auf NuGet.org, dem Visual Studio NuGet-Paket-Manager, angezeigt und dem Quellcode hinzugefügt, wenn das Paket verwendet wird. Die NuGet-Paketversion ist die Versionsnummer, die Benutzern häufig angezeigt wird. Außerdem wird darauf verwiesen, wenn sie die von ihnen verwendete Bibliothek angeben. Die NuGet-Paket-Version wird von NuGet verwendet und hat keine Auswirkungen auf das Runtimeverhalten.

```xml
<PackageVersion>1.0.0-alpha1</PackageVersion>
```

Der NuGet-Paketbezeichner wird in Kombination mit der NuGet-Paket-Version verwendet, um ein Paket in NuGet zu identifizieren. Beispiel: `Newtonsoft.Json` + `11.0.2` Ein Paket mit einem Suffix ist ein Vorabversionspaket, das ein bestimmtes Verhalten aufweist, wodurch es sich ideal für Tests eignet. Weitere Informationen finden Sie unter [Vorabversionspakete](./nuget.md#pre-release-packages).

Da die NuGet-Paketversion für Entwickler die sichtbarste Version ist, ist es eine gute Idee, sie mit der [semantischen Versionierung (SemVer)](https://semver.org/) zu aktualisieren. SemVer zeigt die Bedeutung von Änderungen zwischen den Versionen an und hilft Entwicklern, eine fundierte Entscheidung bei der Auswahl der zu verwendenden Version zu treffen. Wenn Sie beispielsweise von `1.0` auf `2.0` wechseln, zeigt dies an, dass es möglicherweise Änderungen gibt, die den Prozess unterbrechen.

**✔️ ERWÄGEN** Sie, [SemVer 2.0.0](https://semver.org/) für die Versionskontrolle Ihres NuGet-Pakets zu verwenden.

**✔️ DO** Verwenden Sie die NuGet-Paketversion in der öffentlichen Dokumentation, da es die Versionsnummer ist, die den Benutzern häufig angezeigt wird.

**✔️ DO** Fügen Sie ein Suffix der Vorabversion hinzu, wenn Sie ein nicht stabiles Paket freigeben.

> Benutzer müssen sich dafür entscheiden, Vorabversionspakete zu erhalten, sodass ihnen bewusst ist, dass das Paket nicht vollständig ist.

### <a name="assembly-version"></a>Assemblyversion

Die Assemblyversion wird von CLR zur Runtime verwendet, um die zu ladende Version einer Assembly auszuwählen. Die Auswahl einer Assembly über die Versionsverwaltung gilt nur für Assemblys mit einem starken Namen.

```xml
<AssemblyVersion>1.0.0.0</AssemblyVersion>
```

Die Windows .NET Framework-CLR verlangt eine genaue Übereinstimmung, um eine Assembly mit einem starken Namen zu laden. Beispielsweise wurde `Libary1, Version=1.0.0.0` mit einer Referenz auf `Newtonsoft.Json, Version=11.0.0.0` kompiliert. Das .NET Framework lädt nur die genaue Version `11.0.0.0`. Um zur Runtime eine andere Version zu laden, muss der Konfigurationsdatei der .NET-Anwendung eine Bindungsumleitung hinzugefügt werden.

Ein starker Name in Kombination mit der Assemblyversion ermöglicht das [strikte Laden der Assemblyversion](../assembly/versioning.md). Obwohl ein starker Name einer Bibliothek eine Reihe von Vorteilen hat, führt sie oft zu Runtimeausnahmen, dass eine Assembly nicht gefunden werden kann und [Bindungsumleitungen](../../framework/configure-apps/redirect-assembly-versions.md) in `app.config`/`web.config` erforderlich sind, um das Problem zu beheben. Das Laden von .NET Core-Assemblys wurde vereinfacht, und die .NET Core-CLR lädt Assemblys zur Runtime automatisch mit einer höheren Version.

**✔️ ERWÄGEN** Sie, nur eine Hauptversion in der Assemblyversion zu integrieren.

> Beispielsweise haben Bibliothek 1.0 und Bibliothek 1.0.1 beide eine Assemblyversion von `1.0.0.0`, während Bibliothek 2.0 eine Assemblyversion von `2.0.0.0` hat. Wenn die Assemblyversion seltener geändert wird, sind weniger Bindungsumleitungen erforderlich.

**✔ ERWÄGEN** Sie, die Hauptversionsnummer der Assemblyversion und die NuGet-Paketversion immer zu synchronisieren.

> Die Assemblyversion ist in einigen Informationsmeldungen enthalten, die dem Benutzer angezeigt werden, z.B. der Assemblyname und Typnamen mit Assemblyqualifikation in Ausnahmemeldungen. Durch die Beibehaltung einer Beziehung zwischen den Versionen erhalten Entwickler weitere Informationen darüber, welche Version sie verwenden.

**❌ DON‘T** Verwenden Sie keine feste Assemblyversion.

> Da eine unveränderliche Assemblyversion die Notwendigkeit von Bindungsumleitungen vermeidet, bedeutet dies, dass nur eine einzige Version der Assembly im globalen Assemblycache (GAC) installiert werden kann. Außerdem werden die Anwendungen, die auf die Assembly im GAC verweisen, unterbrochen, wenn eine andere Anwendung die GAC-Assembly mit Änderungen aktualisiert.

### <a name="assembly-file-version"></a>Assemblydateiversion

Die Assemblydateiversion wird verwendet, um eine Dateiversion unter Windows anzuzeigen und hat keinen Einfluss auf das Runtimeverhalten. Das Festlegen dieser Version ist optional. Sie wird im Dialogfeld „Dateieigenschaften“ im Windows Explorer angezeigt:

```xml
<FileVersion>11.0.2.21924</FileVersion>
```

![Windows Explorer](./media/versioning/win-properties.png "Windows Explorer")

**✔️ ERWÄGEN** Sie, eine fortlaufenden Continuous Integration-Buildnummer als AssemblyFileVersion-Revision hinzuzufügen.

> Wenn Sie beispielsweise Version 1.0.0 Ihres Projekts erstellen, und die Nummer des Continuous Integration-Builds ist 99, lautet Ihre Assemblydateiversion 1.0.0.99.

**✔️ VERWENDEN** Sie das Format `Major.Minor.Build.Revision` für die Dateiversion.

> Obwohl die Dateiversion von .NET nie verwendet wird, [setzt Windows die Dateiversion](/windows/desktop/menurc/versioninfo-resource) im `Major.Minor.Build.Revision`-Format voraus. Es wird eine Warnung ausgelöst, wenn die Version nicht dieses Format aufweist.

### <a name="assembly-informational-version"></a>Assemblyinformationsversion

Die Assemblyinformationsversion wird verwendet, um zusätzliche Versionsinformationen zu erfassen und hat keinen Einfluss auf das Runtimeverhalten. Das Festlegen dieser Version ist optional. Wenn Sie SourceLink verwenden, wird diese Version für das Build mit der NuGet-Paketversion plus einer Version der Versionsverwaltung festgelegt. Zum Beispiel beinhaltet `1.0.0-beta1+204ff0a` den Commithash des Quellcodes, aus dem die Assembly erstellt wurde. Weitere Informationen finden Sie unter [SourceLink](./sourcelink.md).

```xml
<AssemblyInformationalVersion>The quick brown fox jumped over the lazy dog.</AssemblyInformationalVersion>
```

> [!NOTE]
> Bei älteren Versionen von Visual Studio wird eine Buildwarnung ausgelöst, wenn diese Version nicht das Format `Major.Minor.Build.Revision` aufweist. Sie können sie ignorieren.

**❌ VERMEIDEN** Sie, die Assemblyinformationsversion selbst festzulegen.

> Erlauben Sie SourceLink, die Version automatisch zu generieren, die NuGet- und Metadaten der Quellcodeverwaltung enthält.

>[!div class="step-by-step"]
>[Zurück](publish-nuget-package.md)
>[Weiter](breaking-changes.md)
