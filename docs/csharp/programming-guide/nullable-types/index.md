---
title: Nullable-Typen – C#-Programmierhandbuch
ms.custom: seodec18
description: Informationen zu Nullable-Typen in C# und der Verwendung dieser Typen
ms.date: 07/30/2018
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: 740b39c9c729f0768e75b0465eb8ca98eb5b318f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61710146"
---
# <a name="nullable-types-c-programming-guide"></a>Nullable-Typen (C#-Programmierhandbuch)

Auf NULL festlegbare Typen sind Instanzen der <xref:System.Nullable%601?displayProperty=nameWithType>-Struktur. Nullable-Typen können alle Werte eines zugrunde liegenden `T`-Typs und einen zusätzlichen [NULL](../../language-reference/keywords/null.md)-Wert darstellen. Der zugrunde liegende Typ `T` kann jeder [Werttyp](../../language-reference/keywords/value-types.md) sein, der keine NULL-Werte zulässt. `T` kann kein Referenztyp sein.

Sie können beispielsweise `null` oder jeden anderen Integerwert von <xref:System.Int32.MinValue?displayProperty=nameWithType> bis <xref:System.Int32.MaxValue?displayProperty=nameWithType> einem `Nullable<int>`-, [TRUE](../../language-reference/keywords/true-literal.md)- und [FALSE](../../language-reference/keywords/false-literal.md)-Wert zuweisen, oder `null` zu `Nullable<bool>`.

Sie verwenden einen Nullable-Typ, wenn Sie den nicht definierten Wert eines zugrunde liegenden Typs darstellen müssen. Eine boolesche Variable darf nur zwei Werte besitzen: TRUE und FALSE. Es gibt keinen „nicht definierten“ Wert. In den meisten Programmierungsanwendungen – allen voran Datenbankinteraktionen – kann ein Variablenwert in einem nicht definierten Zustand vorkommen oder fehlen. Ein Feld in einer Datenbank kann z.B. die Werte TRUE und FALSE enthalten; ebenso kann es aber auch gar keinen Wert enthalten. In diesem Fall verwenden Sie einen `Nullable<bool>`-Typ.

Nullable-Typen weisen die folgenden Eigenschaften auf:
  
- Nullable-Typen stellen Werttypvariablen dar, denen der Wert `null` zugewiesen werden kann. Sie können keinen Nullable-Typ basierend auf einem Verweistyp erstellen. (Verweistypen unterstützen immer den `null`-Wert.)  
  
- Die Syntax `T?` ist eine Kurzform für `Nullable<T>`. Die beiden Formen sind austauschbar.  
  
- Sie weisen einem Nullable-Typ einen Wert genauso zu, wie Sie es für einen zugrunde liegenden Werttyp tun würden: `int? x = 10;` oder `double? d = 4.108;`. Sie können ebenfalls den `null`-Wert zuweisen: `int? x = null;`.  
  
- Verwenden Sie die schreibgeschützten Eigenschaften <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> und <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType>, um auf NULL zu prüfen und den Wert abzurufen, wie im folgenden Beispiel gezeigt: `if (x.HasValue) y = x.Value;`  
  
  - Die Eigenschaft <xref:System.Nullable%601.HasValue%2A> gibt `true` zurück, wenn die Variable einen Wert enthält, oder sie gibt `false` zurück, wenn die Variable `null` ist.
  
  - Die Eigenschaft <xref:System.Nullable%601.Value%2A> gibt einen Wert zurück, sofern <xref:System.Nullable%601.HasValue%2A> `true` zurückgibt. Andernfalls wird eine <xref:System.InvalidOperationException> ausgelöst.  
  
- Sie können wie im folgenden Beispiel dargestellt auch die Operatoren `==` und `!=` mit einem Nullable-Typ verwenden: `if (x != null) y = x.Value;` Wenn `a` und `b` jeweils NULL sind, ergibt `a == b` `true`.  

- Ab C# 7.0 können Sie den [Musterabgleich](../../pattern-matching.md#the-is-type-pattern-expression) verwenden, um einen Wert eines Nullable-Typs zu untersuchen und abzurufen: `if (x is int valueOfX) y = valueOfX;`.
  
- Der Standardwert von `T?` ist eine Instanz, deren <xref:System.Nullable%601.HasValue%2A>-Eigenschaft `false` zurückgibt.  

- Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault>-Methode, um entweder den zugewiesenen Wert oder den [Standardwert](../../language-reference/keywords/default-values-table.md) für den zugrunde liegenden Werttyp zurückzugeben, wenn der Wert des Nullable-Typs `null` ist.  

- Verwenden Sie die <xref:System.Nullable%601.GetValueOrDefault(%600)>-Methode, um entweder den zugewiesenen Wert oder den bereitgestellten Standardwert zurückzugeben, wenn der Wert des Nullable-Typs `null` ist.
  
- Verwenden Sie den [NULL-Sammeloperator](../../language-reference/operators/null-coalescing-operator.md), `??`, um einen Wert einem zugrunde liegenden Typ auf Grundlage eines Werts des Nullable-Typs zuzuweisen: `int? x = null; int y = x ?? -1;` Da `x` NULL ist, ist in diesem Beispiel der Ergebniswert von `y` `-1`.

- Wenn eine benutzerdefinierte Konvertierung zwischen zwei Datentypen definiert ist, kann die gleiche Konvertierung auch mit der Version dieser Datentypen verwendet werden, die NULL-Werte zulassen.
  
- Geschachtelte Nullable-Typen sind nicht zulässig. Die folgende Zeile wird nicht kompiliert: `Nullable<Nullable<int>> n;`  

Weitere Informationen finden Sie in den Themen [Verwenden von Nullable-Typen](using-nullable-types.md) und [Vorgehensweise: Identifizieren eines Nullable-Typs](how-to-identify-a-nullable-type.md).
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
- [?? Operator](../../language-reference/operators/null-coalescing-operator.md)
- [C#-Programmierhandbuch](../index.md)
- [Leitfaden für C#](../../index.md)
- [C#-Referenz](../../language-reference/index.md)
- [Auf NULL festlegbare Werttypen (Visual Basic)](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
