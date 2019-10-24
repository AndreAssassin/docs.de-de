---
title: Option Compare-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Compare
- vb.OptionCompare
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword [Visual Basic]
- binary comparison [Visual Basic]
- strings [Visual Basic], returning from functions
- binary comparison [Visual Basic], Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword [Visual Basic], Option Compare statement
- Binary keyword [Visual Basic], Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement [Visual Basic]
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
ms.openlocfilehash: efd033e6c12637b8dc12fb886f46a267e677aa42
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775506"
---
# <a name="option-compare-statement"></a>Option Compare-Anweisung
Deklariert die Standardvergleichsmethode, die beim Vergleichen von Zeichenfolgendaten verwendet wird.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`Binary`|Dies ist optional. Resultiert in Zeichenfolgenvergleichen basierend auf einer Sortierreihenfolge, die sich von den internen binären Darstellungen der Zeichen ableitet.<br /><br /> Diese Art von Vergleich ist besonders hilfreich, da die Zeichenfolgen Zeichen enthalten können, die nicht als Text interpretiert werden. In diesem Fall sollten Sie Vergleiche nicht alphabetischen Äquivalenzen, z. B. Groß-/Kleinschreibung vorziehen.|  
|`Text`|Dies ist optional. Führt zu einem Zeichenfolgenvergleich basierend auf einer schreibungsunabhängigen Textsortierreihenfolge, die durch das Gebietsschema des Systems bestimmt wird.<br /><br /> Diese Art von Vergleich ist nützlich, wenn die Zeichenfolgen nur Textzeichen enthalten und Sie nur anhand alphabetischer Äquivalenzen z. B. Groß-/Kleinschreibung oder eng verwandter Buchstaben vergleichen möchten. Sie könnten zum Beispiel `A` und `a` als gleich ansehen und `Ä` und `ä`, die vor `B` und `b` kommen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn sie verwendet wird, muss die `Option Compare`-Anweisung in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.  
  
 Die `Option Compare`-Anweisung gibt die Zeichenfolgenvergleichsmethode vor (`Binary` oder `Text`).  Die Standardmethode zum Textvergleich ist `Binary`.  
  
 Ein `Binary`-Vergleich vergleicht den numerischen Unicode-Wert jedes Zeichens in jeder Zeichenfolge. Ein `Text`-Vergleich vergleicht alle Unicode-Zeichen anhand der lexikalische Bedeutung in der aktuellen Kultur.  
  
 In Microsoft Windows wird die Sortierreihenfolge durch die Codepage festgelegt. Weitere Informationen finden Sie unter [Codepages](/cpp/c-runtime-library/code-pages).  
  
 Im folgenden Beispiel werden Zeichen der Codepage für Westeuropäisch (ANSI 1252) mit `Option Compare Binary` sortiert, wodurch eine typische binäre Sortierreihenfolge erzeugt wird.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 Wenn dieselben Zeichen in derselben Codepage `Option Compare Text` mit sortiert werden, wird die folgende Sortierreihenfolge erzeugt.  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a>Wenn eine Option Compare-Anweisung nicht vorhanden ist  
 Wenn der Quellcode keine `Option Compare`-Anweisung enthält, wird die **Option Compare** -Einstellung auf der [Seite "kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet. Wenn Sie den Befehlszeilen Compiler verwenden, wird die von der [-optioncompare-](../../../visual-basic/reference/command-line-compiler/optioncompare.md) Compileroption angegebene Einstellung verwendet.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a>Festelegen der Option Compare in der IDE  
  
1. Wählen Sie im **Projektmappen-Explorer** ein Projekt aus. Klicken Sie im Menü **Projekt** auf **Eigenschaften**.  
  
2. Klicken Sie auf die Registerkarte **Kompilieren**.  
  
3. Legen Sie den Wert im Feld **options Vergleich** fest.  
  
 Wenn Sie ein Projekt erstellen, wird die **Option Compare** -Einstellung auf der Registerkarte **Kompilieren** auf die **Option Compare** -Einstellung im Dialogfeld **Optionen** festgelegt. Klicken Sie **im Menü Extras** auf **Optionen**, um diese Einstellung zu ändern. Erweitern Sie im Dialogfeld **Optionen** **Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**. Die ursprüngliche Standardeinstellung in **VB-Standardeinstellungen** ist **Binär**.  
  
#### <a name="to-set-option-compare-on-the-command-line"></a>Festlegen der Option Compare in der Befehlszeile  
  
- Schließen Sie die [-optioncompare-](../../../visual-basic/reference/command-line-compiler/optioncompare.md) Compileroption in den **vbc** -Befehl ein.  
  
## <a name="example"></a>Beispiel  
 Das folgenden Beispiel verwendet die `Option Compare`-Anweisung, um den binären Vergleich als die Standardzeichenfolgenvergleichsmethode festzulegen. Um diesen Code zu verwenden, heben Sie die Auskommentierung der `Option Compare Binary`-Anweisung auf und positionieren Sie sie am Anfang der Quelldatei.  
  
 [!code-vb[VbVbalrStatements#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#45)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Option Compare`-Anweisung verwendet, um die Textsortierreihenfolge als die Standardzeichenfolgenvergleichsmethode festzulegen. Um diesen Code zu verwenden, heben Sie die Auskommentierung der `Option Compare Text`-Anweisung auf und positionieren Sie sie am Anfang der Quelldatei.  
  
 [!code-vb[VbVbalrStatements#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#46)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.InStr%2A>
- <xref:Microsoft.VisualBasic.Strings.InStrRev%2A>
- <xref:Microsoft.VisualBasic.Strings.Replace%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:Microsoft.VisualBasic.Strings.StrComp%2A>
- [-optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)
- [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md)
- [Vergleichs Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Like-Operator](../../../visual-basic/language-reference/operators/like-operator.md)
- [String-Funktionen](../../../visual-basic/language-reference/functions/string-functions.md)
- [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)
