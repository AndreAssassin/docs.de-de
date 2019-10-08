---
title: Select-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: 087472c51d203be083fea0d39ade6f12066cfcb4
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004746"
---
# <a name="select-clause-visual-basic"></a>Select-Klausel (Visual Basic)
Definiert das Ergebnis einer Abfrage.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>Teile  
 `var1`  
 Optional. Ein Alias, der zum Verweisen auf die Ergebnisse des Spalten Ausdrucks verwendet werden kann.  
  
 `fieldName1`  
 Erforderlich. Der Name des Felds, das im Abfrageergebnis zurückgegeben werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Select`-Klausel verwenden, um die Ergebnisse zu definieren, die von einer Abfrage zurückgegeben werden sollen. Dies ermöglicht es Ihnen, entweder die Member eines neuen anonymen Typs zu definieren, der von einer Abfrage erstellt wird, oder die Member eines benannten Typs als Ziel festzulegen, der von einer Abfrage zurückgegeben wird. Die `Select`-Klausel ist für eine Abfrage nicht erforderlich. Wenn keine `Select`-Klausel angegeben wird, gibt die Abfrage einen Typ zurück, der auf allen Elementen der Bereichs Variablen basiert, die für den aktuellen Gültigkeitsbereich identifiziert werden. Weitere Informationen finden Sie unter [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md). Wenn eine Abfrage einen benannten Typ erstellt, wird ein Ergebnis vom Typ <xref:System.Collections.Generic.IEnumerable%601> zurückgegeben, wobei `T` der erstellte Typ ist.  
  
 Die `Select`-Klausel kann auf beliebige Variablen im aktuellen Bereich verweisen. Dies schließt Bereichs Variablen ein, die in der `From`-Klausel (oder `From`-Klauseln) identifiziert werden. Außerdem werden alle neuen Variablen, die mit einem Alias erstellt wurden, durch die `Aggregate`-, `Let`-, `Group By`-oder `Group Join`-Klauseln oder Variablen aus einer früheren `Select`-Klausel im Abfrage Ausdruck eingeschlossen. Die `Select`-Klausel kann auch statische Werte enthalten. Das folgende Codebeispiel zeigt beispielsweise einen Abfrage Ausdruck, in dem die `Select`-Klausel das Abfrageergebnis als neuen anonymen Typ mit vier Mitgliedern definiert: `ProductName`, `Price`, `Discount` und `DiscountedPrice`. Die Element Werte `ProductName` und `Price` stammen aus der in der `From`-Klausel definierten Product Range-Variablen. Der `DiscountedPrice`-Elementwert wird in der `Let`-Klausel berechnet. Der `Discount`-Member ist ein statischer Wert.  
  
 [!code-vb[VbSimpleQuerySamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#27)]  
  
 Die `Select`-Klausel führt einen neuen Satz von Bereichs Variablen für nachfolgende Abfrage Klauseln ein, und vorherige Bereichs Variablen befinden sich nicht mehr im Gültigkeitsbereich. Die letzte `Select`-Klausel in einem Abfrage Ausdruck bestimmt den Rückgabewert der Abfrage. Die folgende Abfrage gibt z. b. den Firmennamen und die Auftrags-ID für jede Kundenbestellung zurück, für die der Gesamtwert 500 überschreitet. Die erste `Select`-Klausel identifiziert die Bereichs Variablen für die `Where`-Klausel und die zweite `Select`-Klausel. Die zweite `Select`-Klausel identifiziert die von der Abfrage zurückgegebenen Werte als neuen anonymen Typ.  
  
 [!code-vb[VbSimpleQuerySamples#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#28)]  
  
 Wenn die `Select`-Klausel ein einzelnes Element identifiziert, das zurückgegeben werden soll, gibt der Abfrage Ausdruck eine Auflistung des Typs dieses einzelnen Elements zurück. Wenn die `Select`-Klausel mehrere zurück zugebende Elemente identifiziert, gibt der Abfrage Ausdruck eine Auflistung eines neuen anonymen Typs zurück, basierend auf den ausgewählten Elementen. Beispielsweise geben die folgenden beiden Abfragen Auflistungen zweier unterschiedlicher Typen basierend auf der `Select`-Klausel zurück. Die erste Abfrage gibt eine Auflistung von Firmennamen als Zeichen folgen zurück. Die zweite Abfrage gibt eine Auflistung von `Customer`-Objekten zurück, die mit den Firmennamen und Adressinformationen aufgefüllt werden.  
  
 [!code-vb[VbSimpleQuerySamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#29)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Abfrage Ausdruck verwendet eine `From`-Klausel, um eine Bereichs Variable `cust` für die `customers`-Auflistung zu deklarieren. Die `Select`-Klausel wählt den Kundennamen und ID-Wert aus und füllt die Spalten "`CompanyName`" und "`CustomerID`" der neuen Bereichs Variablen auf. Mit der `For Each`-Anweisung werden alle zurückgegebenen Objekte durchlaufen, und für jeden Datensatz werden die Spalten `CompanyName` und `CustomerID` angezeigt.  
  
 [!code-vb[VbSimpleQuerySamples#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#30)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
- [Order By-Klausel](../../../visual-basic/language-reference/queries/order-by-clause.md)
- [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
