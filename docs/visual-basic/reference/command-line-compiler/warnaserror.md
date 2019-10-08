---
title: -warnaserror (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: 8af6d3ef4efecd53dcf38c33d0aa2cf182f07d30
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004647"
---
# <a name="-warnaserror-visual-basic"></a>-warnaserror (Visual Basic)
Bewirkt, dass der Compiler das erste Vorkommen einer Warnung als Fehler behandelt.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|+ &#124; -|Optional. Standardmäßig ist `-warnaserror-` aktiviert, sodass Warnungen den Compiler nicht daran hindern, eine Ausgabedatei zu erstellen. Die `-warnaserror`-Option, die mit `-warnaserror+` identisch ist, bewirkt, dass Warnungen als Fehler behandelt werden.|  
|`numberList`|Optional. Mit Kommas als Trennzeichen getrennte Liste der Warnungs-ID-Nummern, für die die `-warnaserror`-Option gilt. Ist keine Warnungs-ID angegeben, gilt die `-warnaserror`-Option für alle Warnungen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `-warnaserror`-Option bewirkt, dass alle Warnungen als Fehler behandelt werden. Alle Nachrichten, die in der Regel als Warnungen gemeldet worden wären, werden stattdessen als Fehler gemeldet. Der Compiler meldet weitere Vorkommen derselben Warnung als Warnungen.  
  
 Standardmäßig ist `-warnaserror-` aktiv, sodass Warnungen nur als Informationen gemeldet werden. Die `-warnaserror`-Option, die mit `-warnaserror+` identisch ist, bewirkt, dass Warnungen als Fehler behandelt werden.  
  
 Wenn nur bestimmte Warnungen als Fehler behandelt werden sollen, können Sie eine durch Kommas als Trennzeichen getrennte Liste mit Warnungsnummern angeben, die als Fehler behandelt werden sollen.  
  
> [!NOTE]
> Die `-warnaserror`-Option steuert nicht, wie Warnungen angezeigt werden. Verwenden Sie die [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)-Option, um Warnungen zu deaktivieren.  
  
|So legen Sie „-warnaserror“ so fest, dass alle Warnungen in der Visual Studio-IDE als Fehler behandelt werden|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**. <br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen deaktivieren**.<br />4.  Aktivieren Sie das Kontrollkästchen **Alle Warnungen als Fehler behandeln**.|  
  
|So legen Sie „-warnaserror“ so fest, dass bestimmte Warnungen in der Visual Studio-IDE als Fehler behandelt werden|  
|---|  
|1.  Ein Projekt auswählen in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.<br />2.  Klicken Sie auf die Registerkarte **Kompilieren**.<br />3.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen deaktivieren**.<br />4.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen als Fehler behandeln**.<br />5.  Wählen Sie **Fehler** in der **Benachrichtigung**-Spalte neben der Warnung aus, die als Fehler behandelt werden soll.|  
  
## <a name="example"></a>Beispiel  
 Im folgende Code wird `In.vb` kompiliert und wird der Compiler angewiesen, für das erste Vorkommen jeder von ihm gefundenen Warnung einen Fehler anzuzeigen.  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Code wird `T2.vb` kompiliert und nur die Warnung für nicht verwendete lokale Variablen (42024) als Fehler behandelt.  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
