---
title: -optioninfer
ms.date: 07/20/2015
f1_keywords:
- -optioninfer
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
ms.openlocfilehash: f1dcc03a67880727893e55c13d65a804586b3f56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788920"
---
# <a name="-optioninfer"></a>-optioninfer
Ermöglicht die Verwendung von lokalem Typrückschluss in Variablendeklarationen.  
  
## <a name="syntax"></a>Syntax  
  
```  
-optioninfer[+ | -]  
```  
  
## <a name="arguments"></a>Argumente  
  
|Begriff|Definition|  
|---|---|  
|`+` &#124; `-`|Dies ist optional. Geben Sie `-optioninfer+` an, um lokalen Typrückschluss zu aktivieren oder `-optioninfer-` zu blockieren. Die `-optioninfer` -Option ohne angegebenen Wert entspricht dem `-optioninfer+`. Der Standardwert, wenn die `-optioninfer` Switch nicht vorhanden ist, ist auch `-optioninfer+`. Der Standardwert ist in der Vbc.rsp-Antwortdatei festgelegt.|  
  
> [!NOTE]
>  Sie können die `-noconfig` Option nutzen, um die internen Standardwerte des Compilers, anstelle der Werte in vbc.rsp, beizubehalten. Der Compilerstandardwert für diese Option ist `-optioninfer-`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Quellcodedatei enthält einen [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md), überschreibt die Anweisung die `-optioninfer` Befehlszeilencompiler-Einstellung.  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a>-Optioninfer in Visual Studio-IDE festlegen  
  
1. Wählen Sie ein Projekt in **Projektmappen-Explorer**. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2. Auf der **Kompilieren** Registerkarte, ändern Sie den Wert in der **Option infer-** Feld.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code kompiliert `test.vb` mit aktiviertem lokalen Typrückschluss.  
  
```console
vbc -optioninfer+ test.vb  
```  
  
## <a name="see-also"></a>Siehe auch

- [Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md)
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [-optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [-optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [VB-Standard, Projekte, Dialogfeld „Optionen“](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)
- [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)
- [Erstellen von der Befehlszeile aus](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)
