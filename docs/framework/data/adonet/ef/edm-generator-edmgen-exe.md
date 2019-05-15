---
title: EDM-Generator (EdmGen.exe)
ms.date: 03/30/2017
ms.assetid: fe8297a1-1fc3-48ce-8eeb-f70f63f857aa
ms.openlocfilehash: f9c75cd7589b1c5fb28112a22390acf90f46e465
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65584589"
---
# <a name="edm-generator-edmgenexe"></a>EDM-Generator (EdmGen.exe)

EdmGen.exe ist ein Befehlszeilentool, das für die Arbeit mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Modell- und Zuordnungsdateien verwendet wird. Mit dem Tool EdmGen.exe können folgende Aufgaben ausgeführt werden:

- Herstellen einer Verbindung zu einer Datenquelle mithilfe eines datenquellenspezifischen .NET Framework-Datenanbieters, und Erstellen der Dateien für das konzeptionelle Modell (CSDL), das Speichermodell (SSDL) und die Zuordnungen (MSL), die von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwendet werden. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie zum Generieren von Modell- und Zuordnungsdateien EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).

- Überprüfen eines bestehenden Modells. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden von EdmGen.exe zum Überprüfen von Modell- und Zuordnungsdateien](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md).

- Erstellen einer C#- oder Visual Basic-Codedatei, die die Objektklassen enthält, die aus einer Datei für das konzeptionelle Modell (CSDL) generiert wurden. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden Sie zum Generieren von Objektebenencode EdmGen.exe](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md).

- Generieren einer C#- oder Visual Basic-Codedatei, die die vorab generierten Sichten für ein vorhandenes Modell enthält. Weitere Informationen [Vorgehensweise: Vorgenerieren von Ansichten zur Verbesserung der Abfrageleistung](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100)).

Das Tool EdmGen.exe wird im .NET Framework-Verzeichnis installiert. Dieses befindet sich meist unter C:\Windows\Microsoft.NET\Framework\v4.0. Bei 64-Bit-Systemen befindet es sich unter C:\Windows\Microsoft.NET\Framework64\v4.0. Sie können auch das Tool EdmGen.exe zugreifen, von der Visual Studio-Eingabeaufforderung (klicken Sie auf **starten**, zeigen Sie auf **Programme**, zeigen Sie auf **Microsoft Visual Studio 2010**, zeigen Sie auf **Visual Studio-Tools**, und klicken Sie dann auf **Visual Studio 2010-Eingabeaufforderung**).

## <a name="syntax"></a>Syntax

```
EdmGen /mode:choice [options]
```

## <a name="mode"></a>Modus

Wenn Sie das Tool EdmGen.exe verwenden, müssen Sie einen der folgenden Modi angeben.

|Modus|Beschreibung|
|----------|-----------------|
|`/mode:ValidateArtifacts`|Überprüft die CSDL-, SSDL- und MSL-Dateien und zeigt alle Fehler und Warnungen an.<br /><br /> Diese Option erfordert mindestens eines der Argumente `/inssdl` oder `/incsdl`. Wenn `/inmsl` angegeben wird, sind auch die Argumente `/inssdl` und `/incsdl` erforderlich.|
|`/mode:FullGeneration`|Verwendet die in der `/connectionstring`-Option angegebenen Informationen zur Datenbankverbindung, und erstellt die CSDL-, SSDL-, .MSL-, Objektebenen- und Sichtdateien.<br /><br /> Diese Option erfordert ein `/connectionstring`-Argument sowie entweder ein `/project`-Argument oder die Argumente `/outssdl`, `/outcsdl`, `/outmsdl`, `/outobjectlayer`, `/outviews`, `/namespace` und `/entitycontainer`.|
|`/mode:FromSSDLGeneration`|Generiert CSDL- und MSL-Dateien, Quellcode und Sichten mithilfe der angegebenen SSDL-Datei.<br /><br /> Diese Option erfordert das `/inssdl`-Argument und entweder ein `/project`-Argument oder die Argumente `/outcsdl`, `/outmsl`, `/outobjectlayer`, `/outviews`, `/namespace,` und `/entitycontainer`.|
|`/mode:EntityClassGeneration`|Erstellt eine Quellcodedatei, die die mithilfe der CSDL-Datei generierten Klassen enthält.<br /><br /> Diese Option erfordert das `/incsdl`-Argument sowie das `/project`-Argument oder das `/outobjectlayer`-Argument. Das `/language`-Argument ist optional.|
|`/mode:ViewGeneration`|Erstellt eine Quellcodedatei, die die aus den CSDL-, SSDL- und MSL-Dateien generierten Sichten enthält.<br /><br /> Diese Option erfordert die Argumente `/inssdl`, `/incsdl` und `/inmsl,` sowie entweder das `/project`-Argument oder das `/outviews`-Argument. Das `/language`-Argument ist optional.|

## <a name="options"></a>Optionen

|Option|Beschreibung|
|------------|-----------------|
|`/p[roject]:`\<string>|Gibt den zu verwendenden Projektnamen an. Der Projektname wird für die standardmäßige Namespaceeinstellung, die Namen der Modell- und Zuordnungsdateien, den Namen der Objektquelldatei und den Namen der Quelldatei für das Generieren von Ansichten verwendet. Der Name des Entitätscontainers nastaven NA hodnotu \<Projekt > Kontext.|
|`/prov[ider]:`\<string>|Der Name des .NET Framework-Datenanbieters zum Erstellen der Speichermodelldatei (SSDL). Der Standardanbieter ist der .NET Framework-Datenanbieter für SQL Server (<xref:System.Data.SqlClient?displayProperty=nameWithType>).|
|`/c[onnectionstring]:`\<Verbindungszeichenfolge >|Gibt die Zeichenfolge an, die verwendet wird, um eine Verbindung mit der Datenquelle herzustellen.|
|`/incsdl:`\<file>|Gibt die CSDL-Datei oder ein Verzeichnis an, in dem sich die CSDL-Dateien befinden. Dieses Argument kann mehrmals angegeben werden, damit Sie mehrere Verzeichnisse oder CSDL-Dateien angeben können. Das Angeben mehrerer Verzeichnisse ist beim Erstellen von Klassen (`/mode:EntityClassGeneration`) oder Sichten (`/mode:ViewGeneration`) hilfreich, wenn das konzeptionelle Modell in mehrere Dateien aufgeteilt ist. Dies kann auch nützlich sein, wenn Sie mehrere Modelle (`/mode:ValidateArtifacts`) überprüfen möchten.|
|`/refcsdl:`\<file>|Gibt die zusätzliche CSDL-Datei bzw. -Dateien an, die verwendet werden, um die Verweise in der CSDL-Quelldatei aufzulösen. (Die CSDL-Quelldatei ist die mit der `/incsdl`-Option angegebene Datei). Die `/refcsdl`-Datei enthält Typen, von denen die CSDL-Quelldatei abhängt. Dieses Argument kann mehrmals angegeben werden.|
|`/inmsl:`\<file>|Gibt die MSL-Datei oder ein Verzeichnis an, in dem sich die MSL-Dateien befinden. Dieses Argument kann mehrmals angegeben werden, um mehrere Verzeichnisse oder MSL-Dateien anzugeben. Das Angeben mehrerer Dateien ist beim Erstellen von Sichten (`/mode:ViewGeneration`) hilfreich, wenn das konzeptionelle Modell in mehrere Dateien aufgeteilt ist. Dies kann auch nützlich sein, wenn Sie mehrere Modelle (`/mode:ValidateArtifacts`) überprüfen möchten.|
|`/inssdl:`\<file>|Gibt die SSDL-Datei oder ein Verzeichnis an, in dem sich die SSDL-Datei befindet. Dieses Argument kann mehrmals angegeben werden, damit Sie mehrere Verzeichnisse oder SSDL-Dateien angeben können. Dies kann auch nützlich sein, wenn Sie mehrere Modelle `(/mode:ValidateArtifacts)` überprüfen möchten.|
|`/outcsdl:`\<file>|Gibt den Namen der CSDL-Datei an, die erstellt wird.|
|`/outmsl:`\<file>|Gibt den Namen der MSL-Datei an, die erstellt wird.|
|`/outssdl:`\<file>|Gibt den Namen der SSDL-Datei an, die erstellt wird.|
|`/outobjectlayer:`\<file>|Gibt den Namen der Quellcodedatei an, die die mit der CSDL-Datei generierten Objekte enthält.|
|`/outviews:`\<file>|Gibt den Namen der Quellcodedatei an, die die generierten Sichten enthält.|
|`/language:`[VB&#124;CSharp]|Gibt die Sprache für die erstellten Quellcodedateien an. Die Standardsprache ist C#.|
|`/namespace:`\<string>|Gibt den zu verwendenden Namespace für das Modell an. Der Namespace wird beim Ausführen von `/mode:FullGeneration` oder `/mode:FromSSDLGeneration` in der CSDL-Datei festgelegt. Beim Ausführen `/mode:EntityClassGeneration` wird der Namespace nicht verwendet.|
|`/entitycontainer:`\<string>|Gibt den Namen an, der dem `<EntityContainer>`-Element in den generierten Modell- und Zuordnungsdateien hinzugefügt wird.|
|`/pl[uralize]`|Wendet für das Englische geltende Regeln für Singular- und Pluralbildung auf die Namen von `Entity`, `EntitySet` und `NavigationProperty` im konzeptionellen Modell an. Diese Option führt die folgenden Aktionen aus:<br /><br /> -Stellen Sie alle `EntityType` Namen im singular.<br />-Stellen Sie alle `EntitySet` Namen im plural.<br />– Für jede `NavigationProperty` , die höchstens eine Entität zurückgibt, wird der Name den Singular gesetzt.<br />– Für jede `NavigationProperty` , die mehr als eine Entität zurückgibt, wird der Name den plural gesetzt.|
|`/SuppressForeignKeyProperties or /nofk`|Verhindert, dass Fremdschlüsselspalten als skalare Eigenschaften von Entitätstypen im konzeptionellen Modell verfügbar gemacht werden.|
|`/help` oder `?`|Zeigt Befehlssyntax und Optionen für das Tool an.|
|`/nologo`|Unterdrückt die Anzeige der Copyrightmeldung.|
|`/targetversion:` \<string>|Die Version von .NET Framework, die zum Kompilieren des generierten Codes verwendet wird. Unterstützt werden Version 4 und 4.5. Der Standardwert ist 4.|

## <a name="in-this-section"></a>In diesem Abschnitt

[Vorgehensweise: Verwenden von EdmGen.exe zum Generieren von Modell- und Zuordnungsdateien](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)

[Vorgehensweise: Mithilfe von EdmGen.exe um Objektebenencode zu generieren.](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)

[Vorgehensweise: Verwenden von EdmGen.exe zum Überprüfen von Modell- und Zuordnungsdateien](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)

## <a name="see-also"></a>Siehe auch

- [ADO.NET Entity Data Model-Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md)
- [CSDL, SSDL, and MSL Specifications (CSDL-, SSDL- und MSL-Spezifikationen)](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md)
