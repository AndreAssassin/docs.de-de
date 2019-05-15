---
title: Umwandlung und Typkonvertierungen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
ms.openlocfilehash: bfcad2669c5ae34605c142f9834c52b4b84c36ae
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608092"
---
# <a name="casting-and-type-conversions-c-programming-guide"></a>Umwandlung und Typkonvertierungen (C#-Programmierhandbuch)

Weil C# zur Kompilierzeit statisch typisiert ist, kann eine Variable, nachdem sie deklariert wurde, nicht erneut deklariert werden oder einen Wert von einem anderen Typ zugewiesen bekommen, es sei denn, dieser Typ ist implizit in den Typ der Variable konvertierbar. `string` kann beispielsweise nicht implizit in `int` konvertiert werden. Deshalb können Sie, nachdem Sie `i` als `int` deklariert haben, nicht die Zeichenfolge „Hello“ zuweisen. Dies wird im folgenden Beispiel veranschaulicht:
  
```csharp  
int i;  
i = "Hello"; // error CS0029: Cannot implicitly convert type 'string' to 'int'
```  
  
 Manchmal müssen Sie möglicherweise einen Wert in eine Variable oder einen Methodenparameter eines anderen Typen kopieren. Sie haben z.B. möglicherweise eine Ganzzahlvariable, die Sie an eine Methode übergeben müssen, deren Parameter vom Type `double` ist. Möglicherweise müssen Sie auch einer Variablen eines Schnittstellentyps eine Klassenvariable zuweisen. Derartige Vorgänge werden als *Typkonvertierungen* bezeichnet. In C# können Sie folgende Arten von Konvertierungen durchführen:  
  
- **Implizite Konvertierungen**: Es ist keine besondere Syntax erforderlich, da die Konvertierung typsicher ist und keine Daten verloren gehen. Beispiele sind Konvertierungen von kleinere in größere Ganzzahltypen und Konvertierungen von abgeleiteten in Basisklassen.  
  
- **Explizite Konvertierungen (Umwandlungen)**: Für explizite Konvertierungen ist ein Umwandlungsoperator erforderlich. Eine Umwandlung ist erforderlich, wenn Informationen bei einer Konvertierung verloren gehen können oder wenn die Konvertierung aus anderen Gründen fehlschlagen könnte.  Häufig auftretende Beispiele sind u.a. numerische Konvertierungen in einen Typen, der eine geringere Genauigkeit oder einen kleineren Bereich aufweist, oder Konvertierungen einer Instanz einer Basisklasse in eine abgeleitete Klasse.  
  
- **Benutzerdefinierte Konvertierungen**: Benutzerdefinierte Konvertierungen werden anhand spezieller Methoden durchgeführt, die Sie definieren können, um explizite und implizite Konvertierungen zwischen benutzerdefinierten Typen zu ermöglichen, die nicht in einer Beziehung „Basisklasse – abgeleitete Klasse“ zueinander stehen. Weitere Informationen finden Sie unter [Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md).  
  
- **Konvertierungen mit Hilfsklassen**: Für eine Konvertierung von nicht kompatiblen Typen, z.B. von ganzen Zahlen und <xref:System.DateTime?displayProperty=nameWithType>-Objekten, oder von Hexadezimalzeichenfolgen und Bytearrays können Sie die <xref:System.BitConverter?displayProperty=nameWithType>-Klasse, die <xref:System.Convert?displayProperty=nameWithType>-Klasse und die `Parse`-Methoden der integrierten numerischen Typen (z.B. <xref:System.Int32.Parse%2A?displayProperty=nameWithType>) verwenden. Weitere Informationen finden Sie unter [Vorgehensweise: Konvertieren eines Bytearrays in einen ganzzahligen Typ](../../../csharp/programming-guide/types/how-to-convert-a-byte-array-to-an-int.md), [Vorgehensweise: Konvertieren einer Zeichenfolge in eine Zahl](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md) und [Vorgehensweise: Konvertieren zwischen Hexadezimalzeichenfolgen und numerischen Typen](../../../csharp/programming-guide/types/how-to-convert-between-hexadecimal-strings-and-numeric-types.md).  
  
## <a name="implicit-conversions"></a>Implizite Konvertierungen

 Eine implizite Konvertierung kann für integrierte numerische Typen durchgeführt werden, wenn der zu speichernde Wert in die Variable passt, ohne abgeschnitten oder abgerundet zu werden. Zum Beispiel kann eine Variable vom Typ [long](../../../csharp/language-reference/keywords/long.md) (64-Bit-Integer) jeden Wert speichern, den eine Variable vom Typ [int](../../../csharp/language-reference/keywords/int.md) (32-Bit-Integer) speichern kann. Im folgenden Beispiel konvertiert der Compiler den Wert von `num` auf der rechten Seite implizit in einen `long`-Typ, bevor er ihn `bigNum` zuweist.  
  
 [!code-csharp[csProgGuideTypes#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#34)]  
  
 Eine vollständige Liste aller impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).  
  
 Eine implizite Konvertierungen für Verweistypen von einer Klasse in jede ihrer direkten oder indirekten Basisklassen oder Schnittstellen ist immer möglich. Es ist keine spezielle Syntax erforderlich, da eine abgeleitete Klasse immer alle Member der Basisklasse enthält.  
  
```  
Derived d = new Derived();  
Base b = d; // Always OK.  
```  
  
## <a name="explicit-conversions"></a>Explizite Konvertierungen

 Wenn allerdings eine Konvertierung nicht ohne möglichen Informationsverlust durchgeführt werden kann, fordert der Compiler eine explizite Konvertierung; diese wird als *Umwandlung* bezeichnet. Eine Umwandlung bietet die Möglichkeit, den Compiler explizit zu verständigen, dass Sie eine Konvertierung vornehmen möchten, und dass es Ihnen bewusst ist, dass dies einen Datenverlust zur Folge haben kann. Wenn Sie eine Umwandlung durchführen möchten, geben Sie den Typ, in den umgewandelt werden soll, in Klammern am Anfang des zu konvertierenden Wertes oder der zu konvertierenden Variablen an. Das folgende Programm wandelt ein [double](../../../csharp/language-reference/keywords/double.md) in ein [int](../../../csharp/language-reference/keywords/int.md) um. Das Programm führt ohne die Umwandlung keine Kompilierung durch.  
  
 [!code-csharp[csProgGuideTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#2)]  
  
 Eine Liste der zulässigen expliziten numerischen Konvertierungen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).  
  
 Eine explizite Umwandlung ist für Verweistypen erforderlich, wenn Sie von einer Basisklasse in eine abgeleitete Klasse konvertieren möchten:  
  
```csharp  
// Create a new derived type.  
Giraffe g = new Giraffe();  
  
// Implicit conversion to base type is safe.  
Animal a = g;  
  
// Explicit conversion is required to cast back  
// to derived type. Note: This will compile but will  
// throw an exception at run time if the right-side  
// object is not in fact a Giraffe.  
Giraffe g2 = (Giraffe) a;  
```  
  
 Ein Umwandlungsvorgang zwischen Verweistypen ändert nicht den Laufzeittypen des zugrunde liegenden Objekts; er ändert lediglich den Typ des Wertes, der als Verweis auf das Objekt verwendet wird. Weitere Informationen finden Sie unter [Polymorphie](../../../csharp/programming-guide/classes-and-structs/polymorphism.md).  
  
## <a name="type-conversion-exceptions-at-run-time"></a>Typkonvertierungsausnahmen zur Laufzeit

 In manchen Verweistypkonvertierungen kann der Compiler nicht bestimmen, ob eine Umwandlung zulässig wäre. Es ist möglich, dass ein Umwandlungsvorgang, der ordnungsgemäß kompiliert, zur Laufzeit fehlschlägt. Eine fehlgeschlagene Typumwandlung zur Laufzeit löst wie in folgendem Beispiel dargestellt eine <xref:System.InvalidCastException> aus.  
  
 [!code-csharp[csProgGuideTypes#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#41)]  
  
 C# stellt die Operatoren [is](../../../csharp/language-reference/keywords/is.md) und [as](../../../csharp/language-reference/keywords/as.md) bereit, mit denen Sie vor einer Umwandlung auf Kompatibilität prüfen können. Weitere Informationen finden Sie unter [Vorgehensweise: Sicheres Umwandeln mit Musterabgleich und den Operatoren „as“ und „is“](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md).  
  
## <a name="c-language-specification"></a>C#-Sprachspezifikation

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Typen](../../../csharp/programming-guide/types/index.md)
- [()-Operator](../../../csharp/language-reference/operators/invocation-operator.md)
- [explicit](../../../csharp/language-reference/keywords/explicit.md)
- [implicit](../../../csharp/language-reference/keywords/implicit.md)
- [Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/conversion-operators.md)
- [Verallgemeinerte Typkonvertierung](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/yy580hbd(v=vs.120))
- [Vorgehensweise: Konvertieren einer Zeichenfolge in eine Zahl](../../../csharp/programming-guide/types/how-to-convert-a-string-to-a-number.md)
