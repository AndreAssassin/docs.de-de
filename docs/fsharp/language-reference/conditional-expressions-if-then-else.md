---
title: 'Bedingte Ausdrücke: if... then... else'
description: Erfahren Sie, wie Sie bedingte Ausdrücke in F# zum Ausführen der unterschiedliche Codezweige geschrieben.
ms.date: 05/16/2016
ms.openlocfilehash: db2d5ce5b75ecda171f2623c986878dcee1cf4d9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641990"
---
# <a name="conditional-expressions-ifthenelse"></a><span data-ttu-id="86d71-103">Bedingte Ausdrücke: `if...then...else`</span><span class="sxs-lookup"><span data-stu-id="86d71-103">Conditional Expressions: `if...then...else`</span></span>

<span data-ttu-id="86d71-104">Die `if...then...else` Ausdruck unterschiedliche Codezweige ausführt und auch auf einen anderen Wert je nach angegebenem booleschen Ausdruck ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="86d71-104">The `if...then...else` expression runs different branches of code and also evaluates to a different value depending on the Boolean expression given.</span></span>

## <a name="syntax"></a><span data-ttu-id="86d71-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="86d71-105">Syntax</span></span>

```fsharp
if boolean-expression then expression1 [ else expression2 ]
```

## <a name="remarks"></a><span data-ttu-id="86d71-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86d71-106">Remarks</span></span>

<span data-ttu-id="86d71-107">In der vorherigen Syntax *expression1* ausgeführt wird, wenn der boolesche Ausdruck ergibt `true`ist, andernfalls *expression2* ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="86d71-107">In the previous syntax, *expression1* runs when the Boolean expression evaluates to `true`; otherwise, *expression2* runs.</span></span>

<span data-ttu-id="86d71-108">Anders als in anderen Sprachen, die `if...then...else` Konstrukt ist ein Ausdruck, der keine Anweisung.</span><span class="sxs-lookup"><span data-stu-id="86d71-108">Unlike in other languages, the `if...then...else` construct is an expression, not a statement.</span></span> <span data-ttu-id="86d71-109">Das bedeutet, dass sie einen Wert erzeugt, das den Wert des letzten Ausdrucks im Branch, der ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="86d71-109">That means that it produces a value, which is the value of the last expression in the branch that executes.</span></span> <span data-ttu-id="86d71-110">Die Typen der Werte produziert, die in jeder Verzweigung müssen übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="86d71-110">The types of the values produced in each branch must match.</span></span> <span data-ttu-id="86d71-111">Wenn es keine explizite ist `else` Branch, der Typ ist `unit`.</span><span class="sxs-lookup"><span data-stu-id="86d71-111">If there is no explicit `else` branch, its type is `unit`.</span></span> <span data-ttu-id="86d71-112">Aus diesem Grund, wenn der Typ des der `then` Branch ist ein beliebiger Typ außer `unit`, muss vorhanden sein ein `else` Branch mit den gleichen Rückgabetyp.</span><span class="sxs-lookup"><span data-stu-id="86d71-112">Therefore, if the type of the `then` branch is any type other than `unit`, there must be an `else` branch with the same return type.</span></span> <span data-ttu-id="86d71-113">Beim Verketten `if...then...else` Ausdrücke, können Sie das Schlüsselwort `elif` anstelle von `else if`; sie gleichwertig sind.</span><span class="sxs-lookup"><span data-stu-id="86d71-113">When chaining `if...then...else` expressions together, you can use the keyword `elif` instead of `else if`; they are equivalent.</span></span>

## <a name="example"></a><span data-ttu-id="86d71-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86d71-114">Example</span></span>

<span data-ttu-id="86d71-115">Das folgende Beispiel veranschaulicht, wie Sie mit der `if...then...else` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="86d71-115">The following example illustrates how to use the `if...then...else` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4501.fs)]

```
10 is less than 20
What is your name? John
How old are you? 9
You are only 9 years old and already learning F#? Wow!
```

## <a name="see-also"></a><span data-ttu-id="86d71-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86d71-116">See also</span></span>

- [<span data-ttu-id="86d71-117">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="86d71-117">F# Language Reference</span></span>](index.md)
