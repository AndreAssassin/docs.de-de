---
title: 'lock-Anweisung: C#-Referenz'
ms.custom: seodec18
description: Verwenden Sie die lock-Anweisung von C#, um den Threadzugriff auf eine freigegebene Ressource zu synchronisieren.
ms.date: 10/01/2018
f1_keywords:
- lock_CSharpKeyword
- lock
helpviewer_keywords:
- lock keyword [C#]
ms.assetid: 656da1a4-707e-4ef6-9c6e-6d13b646af42
ms.openlocfilehash: 96609264044e531bcc8671cb226a02fdc1b962b8
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796452"
---
# <a name="lock-statement-c-reference"></a>lock-Anweisung (C#-Referenz)

Die `lock`-Anweisung ruft die Sperre für gegenseitigen Ausschluss für ein bestimmtes Objekt ab, führt einen Anweisungsblock aus und hebt die Sperre anschließend auf. Während eine Sperre aufrechterhalten wird, kann der Thread, der die Sperre aufrechterhält, die Sperre abrufen und aufheben. Für jeden anderen Thread wird das Abrufen der Sperre blockiert, und die Sperre wartet auf die Aufhebung.

Die `lock`-Anweisung weist folgendes Format auf:

```csharp
lock (x)
{
    // Your code...
}
```

`x` entspricht einem Ausdruck eines [Verweistyps](reference-types.md). Dieser entspricht exakt Folgendem:

```csharp
object __lockObj = x;
bool __lockWasTaken = false;
try
{
    System.Threading.Monitor.Enter(__lockObj, ref __lockWasTaken);
    // Your code...
}
finally
{
    if (__lockWasTaken) System.Threading.Monitor.Exit(__lockObj);
}
```

Da ein [try...finally](try-finally.md)-Block in diesem Code verwendet wird, wird die Sperre aufgehoben, wenn eine Ausnahme innerhalb des Texts einer `lock`-Anweisung ausgelöst wird.

Sie können das Schlüsselwort [await](await.md) nicht im Text einer `lock`-Anweisung verwenden.

## <a name="remarks"></a>Hinweise

Wenn Sie den Threadzugriff auf eine freigegebene Ressource synchronisieren, sperren Sie eine dedizierte Objektinstanz (z.B. `private readonly object balanceLock = new object();`) oder eine andere Instanz, die wahrscheinlich nicht von anderen Teilen des Codes als lock-Objekt verwendet wird. Vermeiden Sie, die gleiche lock-Objektinstanz für verschiedene freigegebene Ressourcen zu verwenden, da dies zu einem Deadlock oder Sperrkonflikt führen kann. Vermeiden Sie insbesondere die Verwendung der folgenden Objekte als Sperre:

- `this` – kann von den Aufrufern als Sperre verwendet werden.
- <xref:System.Type>-Instanzen – können vom [typeof](../operators/type-testing-and-conversion-operators.md#typeof-operator)-Operator oder der Reflektion abgerufen werden.
- Zeichenfolgeninstanzen, einschließlich Zeichenfolgenliteralen – können [internalisiert](/dotnet/api/system.string.intern#remarks) sein.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine `Account`-Klasse definiert, die den Zugriff auf das private `balance`-Feld synchronisiert, indem eine dedizierte `balanceLock`-Instanz gesperrt wird. Durch Verwendung der gleichen Instanz für die Sperre wird sichergestellt, dass das `balance`-Feld nicht von zwei Threads gleichzeitig aktualisiert werden kann, die zur gleichen Zeit versuchen, die Methoden `Debit` oder `Credit` aufzurufen.

[!code-csharp[lock-statement-example](~/samples/snippets/csharp/keywords/LockStatementExample.cs)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Die lock-Anweisung](~/_csharplang/spec/statements.md#the-lock-statement) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- <xref:System.Threading.SpinLock?displayProperty=nameWithType>
- <xref:System.Threading.Interlocked?displayProperty=nameWithType>
- [C#-Referenz](../index.md)
- [C#-Schlüsselwörter](index.md)
- [Übersicht über Synchronisierungsprimitiven](../../../standard/threading/overview-of-synchronization-primitives.md)
