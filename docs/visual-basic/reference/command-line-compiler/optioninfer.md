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
ms.openlocfilehash: 4848dec148bc528e7a30940643e3364f1bb5f805
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939205"
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
|`+` &#124; `-`|Optional. Geben Sie `-optioninfer+` an, um lokalen Typrückschluss zu aktivieren oder `-optioninfer-` zu blockieren. Die `-optioninfer` -Option ohne angegebenen Wert entspricht dem `-optioninfer+`. Der Standardwert, wenn die `-optioninfer` Switch nicht vorhanden ist, ist auch `-optioninfer+`. Der Standardwert ist in der Vbc.rsp-Antwortdatei festgelegt.|  
  
> [!NOTE]
> Sie können die `-noconfig` Option nutzen, um die internen Standardwerte des Compilers, anstelle der Werte in vbc.rsp, beizubehalten. Der Compilerstandardwert für diese Option ist `-optioninfer-`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn die Quell Code Datei eine [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md)enthält, überschreibt die- `-optioninfer` Anweisung die Befehlszeilen-Compilereinstellung.  
  
### <a name="to-set--optioninfer-in-the-visual-studio-ide"></a>So legen Sie-optioninfer in der Visual Studio-IDE fest  
  
1. Wählen Sie ein Projekt in **Projektmappen-Explorer**aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2. Ändern Sie auf der Registerkarte **Kompilieren** den Wert im Feld **Option ableiten** .  
  
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
