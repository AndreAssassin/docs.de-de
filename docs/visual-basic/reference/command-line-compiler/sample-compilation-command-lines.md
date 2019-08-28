---
title: Beispiele für Kompilierungsbefehlszeilen (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
ms.openlocfilehash: b7879c23bc64269c793c21b61b84d6f0fd4bdc24
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046293"
---
# <a name="sample-compilation-command-lines-visual-basic"></a>Beispiel-Kompilierungs Befehlszeilen (Visual Basic)

Als Alternative zum Kompilieren von Visual Basic Programmen in Visual Studio können Sie über die Befehlszeile kompilieren, um ausführbare Dateien (. exe) oder DLL-Dateien (Dynamic Link Library) zu erstellen.

Der Visual Basic-Befehlszeilen Compiler unterstützt einen kompletten Satz von Optionen, die Eingabe-und Ausgabedateien, Assemblys sowie Debug-und Präprozessoroptionen steuern. Jede Option ist in zwei austauschbaren Formularen verfügbar `-option` : `/option`und. In dieser Dokumentation wird nur `-option` das Formular angezeigt.

In der folgenden Tabelle sind einige Beispiel Befehlszeilen aufgelistet, die Sie für Ihre eigene Verwendung ändern können.

|Beschreibung|Mit|
|--------|---------|
|Kompilieren Sie File. vb, und erstellen Sie File. exe.|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|
|Kompilieren Sie File. vb, und erstellen Sie File. dll.|`vbc -target:library File.vb`|
|Kompilieren Sie File. vb, und erstellen Sie My. exe.|`vbc -out:My.exe File.vb`|
|Kompilieren Sie File. vb, und erstellen Sie eine Bibliothek und eine Verweisassembly mit dem Namen file. dll.|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|Kompilieren Sie alle Visual Basic Dateien im aktuellen Verzeichnis mit Optimierungen für und das definierte Symbol `DEBUG` , die file2. exe erstellt.|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|
|Kompilieren Sie alle Visual Basic Dateien im aktuellen Verzeichnis, und erstellen Sie eine Debugversion von file2. dll, ohne das Logo oder die Warnungen anzuzeigen.|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|
|Alle Visual Basic Dateien im aktuellen Verzeichnis in ". dll" kompilieren|`vbc -target:library -out:Something.dll *.vb`|

> [!TIP]
> Wenn Sie ein Projekt mithilfe der Visual Studio-IDE erstellen, können Sie Informationen zum zugeordneten **vbc** -Befehl mit seinen Compileroptionen im Ausgabefenster anzeigen. Um diese Informationen anzuzeigen, öffnen Sie das [Dialog Feld Optionen, Projekte und Projektmappen, erstellen und ausführen](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), und legen Sie dann die Ausführlichkeit der **MSBuild** -Projektbuildausgabe auf **Normal** oder eine höhere ausführlichkeits Stufe fest.

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
