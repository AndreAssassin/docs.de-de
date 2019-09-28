---
title: Atomisierte XName-und XNamespace-Objekte (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
ms.openlocfilehash: ae6d21c21aac4455e7932015c131fb4295673056
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71351829"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a>Atomisierte XName-und XNamespace-Objekte (LINQ to XML) (Visual Basic)

Die <xref:System.Xml.Linq.XName>- und <xref:System.Xml.Linq.XNamespace>-Objekte sind *atomisiert*. Dies bedeutet, dass sie auf dasselbe Objekt verweisen, wenn sie denselben qualifizierten Namen enthalten. Dies wirkt sich positiv auf die Leistung bei Abfragen aus: Beim Vergleichen zweier atomisierter Namen auf Übereinstimmung muss die zugrunde liegende Zwischensprache nur ermitteln, ob die beiden Verweise auf dasselbe Objekt zeigen. Im zugrunde liegenden Code müssen keine zeitaufwändigen Zeichenfolgenvergleiche ausgeführt werden.

## <a name="atomization-semantics"></a>Atomisierungssemantik

Atomisierung bedeutet, dass zwei <xref:System.Xml.Linq.XName>-Objekte dieselbe Instanz gemeinsam nutzen, wenn sie über denselben lokalen Namen verfügen und sich im selben Namespace befinden. Dementsprechend nutzen zwei <xref:System.Xml.Linq.XNamespace>-Objekte dieselbe Instanz gemeinsam, wenn sie über denselben Namespace-URI verfügen.

Damit eine Klasse atomisierte Objekte unterstützt, muss der Konstruktor für die Klasse privat sein, nicht öffentlich. Bei einem öffentlichen Konstruktor könnten Sie ein nicht atomisiertes Objekt erstellen. Die <xref:System.Xml.Linq.XName>-Klasse und die <xref:System.Xml.Linq.XNamespace>-Klasse implementieren einen impliziten Konvertierungsoperator, um eine Zeichenfolge in einen <xref:System.Xml.Linq.XName> oder einen <xref:System.Xml.Linq.XNamespace> zu konvertieren. Auf diese Weise können Sie eine Instanz dieser Objekte abrufen. Sie können keine Instanz über einen Konstruktor abrufen, da Sie auf den Konstruktor nicht zugreifen können.

Außerdem werden von <xref:System.Xml.Linq.XName> und <xref:System.Xml.Linq.XNamespace> Gleichheits- und Ungleichheitsoperatoren implementiert, mit denen Sie ermitteln können, ob die beiden verglichenen Objekte Verweise auf dieselbe Instanz darstellen.

## <a name="example"></a>Beispiel

Im folgenden Code werden mehrere <xref:System.Xml.Linq.XElement>-Objekte erstellt, und es wird veranschaulicht, dass identische Namen dieselbe Instanz aufweisen.

```vb
Dim r1 As New XElement("Root", "data1")
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")

If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")
Else
    Console.WriteLine("Different")
End If

Dim n As XName = "Root"

If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")
Else
    Console.WriteLine("Different")
End If
```

Dieses Beispiel erzeugt die folgende Ausgabe:

```console
r1 and r2 have names that refer to the same instance.
The name of r1 and the name in 'n' refer to the same instance.
```

Wie bereits erwähnt, besteht der Vorteil atomisierter Objekte darin, dass beim Verwenden einer der Achsenmethoden, die als Parameter einen <xref:System.Xml.Linq.XName> erfordert, zum Auswählen der gewünschten Elemente nur ermittelt werden muss, ob die beiden Namen auf dieselbe Instanz verweisen.

Im folgenden Beispiel wird ein <xref:System.Xml.Linq.XName> an den <xref:System.Xml.Linq.XContainer.Descendants%2A>-Methodenaufruf übergeben. Dieser erreicht aufgrund des Atomarisierungsmusters eine bessere Leistung.

```vb
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))

Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e

For Each z As var In query
    Console.WriteLine(z)
Next
```

Dieses Beispiel erzeugt die folgende Ausgabe:

```xml
<C1>1</C1>
<C1>1</C1>
```

## <a name="see-also"></a>Siehe auch

- [Leistung (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
