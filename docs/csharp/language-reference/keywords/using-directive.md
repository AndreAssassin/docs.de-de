---
title: using-Anweisung – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 072af9850f792cb6d7322724f2adbc978465dc84
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421746"
---
# <a name="using-directive-c-reference"></a>using-Anweisung (C#-Referenz)

Die `using`-Direktive hat drei Verwendungszwecke:

- Sie ermöglicht die Verwendung von Typen in einem Namespace, sodass Sie die Verwendung eines Typs in diesem Namespace nicht qualifizieren müssen:

    ```csharp
    using System.Text;
    ```

- Ermöglicht den Zugriff auf statische Member eines geschachtelten Typs, ohne den Zugriff mit dem Typnamen zu qualifizieren.

    ```csharp
    using static System.Math;
    ```

    Weitere Informationen finden Sie unter [using static-Direktive (C#-Referenz)](using-static.md).

- Erstellen eines Alias für einen Namespace oder Typ. Dies wird als *using-Aliasdirektive* bezeichnet.

    ```csharp
    using Project = PC.MyCompany.Project;
    ```

Das `using`-Schlüsselwort wird auch zum Erstellen von *using-Anweisungen* verwendet, mit denen sichergestellt wird, dass <xref:System.IDisposable>-Objekte wie Dateien und Schriftarten richtig verarbeitet werden. Weitere Informationen finden Sie unter [using-Anweisung](using-statement.md).

## <a name="using-static-type"></a>Verwenden statischer Typen

Sie können auf statische Member eines Typs zugreifen, ohne den Zugriff mit dem Typnamen zu qualifizieren:

```csharp
using static System.Console;
using static System.Math;
class Program
{
    static void Main()
    {
        WriteLine(Sqrt(3*3 + 4*4));
    }
}
```

## <a name="remarks"></a>Anmerkungen

Der Bereich einer `using`-Direktive ist auf die Datei beschränkt, in der er enthalten ist.

Die `using`-Direktive kann an folgenden Stellen erscheinen:

- Am Anfang einer Quellcodedatei, vor Namespace- oder Typdefinitionen.
- In einem beliebigen Namespace, jedoch vor in diesem Namespace deklarierten Namespaces oder Typen.

Andernfalls wird der Compilerfehler [CS1529](../../misc/cs1529.md) generiert.

Erstellen Sie eine `using`-Alias-Direktive, um das Qualifizieren eines Bezeichners in einen Namespace oder Typ zu vereinfachen. In jeder `using`-Direktive muss der vollqualifizierte Namespace oder Typ unabhängig von den davor aufgeführten `using`-Direktiven verwendet werden. In der Deklaration einer `using`-Direktive kann kein `using`-Alias verwendet werden. Der folgende Code verursacht beispielsweise einen Compilerfehler:

```csharp
using s = System.Text;
using s.RegularExpressions;
```

Erstellen Sie eine `using`-Direktive, um die Typen in einem Namespace zu verwenden, ohne den Namespace angeben zu müssen. Eine `using`-Direktive ermöglicht Ihnen nicht den Zugriff auf Namespaces, die im angegebenen Namespace geschachtelt sind.

Gibt zwei Kategorien von Namespaces: benutzerdefinierte und systemdefinierte Namespaces. Benutzerdefinierte Namespaces sind Namespaces, die im Code definiert sind. Eine Liste der systemdefinierten Namespaces finden Sie unter [.NET API-Browser](../../../../api/index.md).

Beispiele für das Verweisen auf Methoden in anderen Assemblys finden Sie unter [Erstellen und Verwenden von Assemblys über die Befehlszeile](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).

## <a name="example-1"></a>Beispiel 1

Das folgende Beispiel zeigt, wie Sie einen `using`-Alias für einen Namespace definieren und verwenden:

[!code-csharp[csrefKeywordsNamespace#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#8)]

Eine using-Aliasanweisung kann auf der rechten Seite nicht über einen offenen generischen Typen verfügen. Sie können zum Beispiel keinen using-Alias für `List<T>` erstellen, jedoch für `List<int>`.

## <a name="example-2"></a>Beispiel 2

Das folgende Beispiel zeigt, wie Sie eine `using`-Direktive und einen `using`-Alias für eine Klasse definieren:

[!code-csharp[csrefKeywordsNamespace#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace2.cs#9)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [using-Direktiven](~/_csharplang/spec/namespaces.md#using-directives) in der [C#-Sprachspezifikation](../language-specification/index.md). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Using-Namespaces](../../programming-guide/namespaces/using-namespaces.md)
- [C#-Schlüsselwörter](index.md)
- [Namespaces](../../programming-guide/namespaces/index.md)
- [Using-Anweisung](using-statement.md)
