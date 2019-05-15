---
title: do-Bindungen in Klassen
description: Erfahren Sie, wie Sie mit einem F# 'do'-Bindung in einer Klassendefinition, Aktionen ausgeführt werden, wenn das Objekt erstellt wird, oder wenn der Typ zuerst verwendet wird.
ms.date: 05/16/2016
ms.openlocfilehash: c924c882974989436d8ea404ebee0a7ef3c54fd3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641796"
---
# <a name="do-bindings-in-classes"></a><span data-ttu-id="80026-103">do-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="80026-103">do Bindings in Classes</span></span>

<span data-ttu-id="80026-104">Ein `do` Bindung in einer Klassendefinition führt Aktionen aus, wenn das Objekt erstellt wird, oder, für eine statische `do` binden, wenn der Typ zuerst verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="80026-104">A `do` binding in a class definition performs actions when the object is constructed or, for a static `do` binding, when the type is first used.</span></span>

## <a name="syntax"></a><span data-ttu-id="80026-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="80026-105">Syntax</span></span>

```fsharp
[static] do expression
```

## <a name="remarks"></a><span data-ttu-id="80026-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80026-106">Remarks</span></span>

<span data-ttu-id="80026-107">Ein `do` Bindung angezeigt wird, zusammen mit oder nach `let` Bindungen, aber vor den Definitionen der Elemente in einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="80026-107">A `do` binding appears together with or after `let` bindings but before member definitions in a class definition.</span></span> <span data-ttu-id="80026-108">Obwohl die `do` -Schlüsselwort ist optional für `do` Bindungen auf Modulebene, es ist nicht optional für `do` Bindungen in einer Klassendefinition.</span><span class="sxs-lookup"><span data-stu-id="80026-108">Although the `do` keyword is optional for `do` bindings at the module level, it is not optional for `do` bindings in a class definition.</span></span>

<span data-ttu-id="80026-109">Für die Erstellung der jedes Objekt eines beliebigen angegebenen Typs, die nicht statische `do` Bindungen und nicht statische `let` Bindungen werden in der Reihenfolge in der Definition der Klasse ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="80026-109">For the construction of every object of any given type, non-static `do` bindings and non-static `let` bindings are executed in the order in which they appear in the class definition.</span></span> <span data-ttu-id="80026-110">Mehrere `do` Bindungen in einem Typ auftreten können.</span><span class="sxs-lookup"><span data-stu-id="80026-110">Multiple `do` bindings can occur in one type.</span></span> <span data-ttu-id="80026-111">Die nicht statische `let` Bindungen und die nicht statische `do` Bindungen werden der Text des primären Konstruktors.</span><span class="sxs-lookup"><span data-stu-id="80026-111">The non-static `let` bindings and the non-static `do` bindings become the body of the primary constructor.</span></span> <span data-ttu-id="80026-112">Der Code in der nicht statischen `do` Parameter des primären Konstruktors und alle Werte oder Funktionen, die definiert sind, kann im Abschnitt über Bindungen verweisen die `let` im Abschnitt über Bindungen.</span><span class="sxs-lookup"><span data-stu-id="80026-112">The code in the non-static `do` bindings section can reference the primary constructor parameters and any values or functions that are defined in the `let` bindings section.</span></span>

<span data-ttu-id="80026-113">Nicht statische `do` Bindungen können auf Member der Klasse zugreifen, solange die Klasse verfügt über ein Self-Bezeichner, die von definiert ist ein `as` Schlüsselwort in der Klasse, die Spaltenüberschrift, und so lange, wie Sie alle Vorkommen dieser Elemente mit der Selbstbezeichner für die Klasse qualifiziert sind.</span><span class="sxs-lookup"><span data-stu-id="80026-113">Non-static `do` bindings can access members of the class as long as the class has a self identifier that is defined by an `as` keyword in the class heading, and as long as all uses of those members are qualified with the self identifier for the class.</span></span>

<span data-ttu-id="80026-114">Da `let` Bindungen initialisieren die privaten Felder einer Klasse, die häufig notwendig ist, um sicherzustellen, dass Mitglieder Verhalten sich wie erwartet, `do` Bindungen werden in der Regel fügen Sie nach dem `let` Bindungen, so dass der code in die `do` Bindung kann Führen Sie mit der ein vollständig initialisiertes Objekt.</span><span class="sxs-lookup"><span data-stu-id="80026-114">Because `let` bindings initialize the private fields of a class, which is often necessary to guarantee that members behave as expected, `do` bindings are usually put after `let` bindings so that code in the `do` binding can execute with a fully initialized object.</span></span> <span data-ttu-id="80026-115">Wenn Ihr Code versucht, einen Member zu verwenden, bevor die Initialisierung abgeschlossen ist, wird eine "InvalidOperationException" ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="80026-115">If your code attempts to use a member before the initialization is complete, an InvalidOperationException is raised.</span></span>

<span data-ttu-id="80026-116">Statische `do` Bindungen können auf statische Member verweisen oder Felder der einschließenden Klasse aber für die Instanz nicht, Member oder Felder.</span><span class="sxs-lookup"><span data-stu-id="80026-116">Static `do` bindings can reference static members or fields of the enclosing class but not instance members or fields.</span></span> <span data-ttu-id="80026-117">Statische `do` Bindungen Teil der statische Initialisierer für die Klasse, die Ausführung vor der ersten Verwendung die Klasse gewährleistet ist.</span><span class="sxs-lookup"><span data-stu-id="80026-117">Static `do` bindings become part of the static initializer for the class, which is guaranteed to execute before the class is first used.</span></span>

<span data-ttu-id="80026-118">Attribute werden ignoriert, für die `do` Bindungen in Typen.</span><span class="sxs-lookup"><span data-stu-id="80026-118">Attributes are ignored for `do` bindings in types.</span></span> <span data-ttu-id="80026-119">Wenn ein Attribut für Code erforderlich ist, der ausgeführt wird ein `do` binden, muss angewendet werden auf den primären Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="80026-119">If an attribute is required for code that executes in a `do` binding, it must be applied to the primary constructor.</span></span>

<span data-ttu-id="80026-120">Im folgenden Code wird eine Klasse weist eine statische `do` Bindung und eine nicht statische `do` Bindung.</span><span class="sxs-lookup"><span data-stu-id="80026-120">In the following code, a class has a static `do` binding and a non-static `do` binding.</span></span> <span data-ttu-id="80026-121">Das Objekt hat einen Konstruktor, der zwei Parameter verfügt `a` und `b`, zwei private Felder werden in definiert die `let` Bindungen für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="80026-121">The object has a constructor that has two parameters, `a` and `b`, and two private fields are defined in the `let` bindings for the class.</span></span> <span data-ttu-id="80026-122">Außerdem werden die zwei Eigenschaften definiert.</span><span class="sxs-lookup"><span data-stu-id="80026-122">Two properties are also defined.</span></span> <span data-ttu-id="80026-123">Alle diese befinden sich im Gültigkeitsbereich, in der nicht statischen `do` Bindungsabschnitt, wie durch die Linie dargestellt wird, die alle diese Werte ausgibt.</span><span class="sxs-lookup"><span data-stu-id="80026-123">All of these are in scope in the non-static `do` bindings section, as is illustrated by the line that prints all those values.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3101.fs)]

<span data-ttu-id="80026-124">Die Ausgabe lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="80026-124">The output is as follows.</span></span>

```console
Initializing MyType.
Initializing object 1 2 2 4 8 16
```

## <a name="see-also"></a><span data-ttu-id="80026-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80026-125">See also</span></span>

- [<span data-ttu-id="80026-126">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="80026-126">Members</span></span>](index.md)
- [<span data-ttu-id="80026-127">Klassen</span><span class="sxs-lookup"><span data-stu-id="80026-127">Classes</span></span>](../classes.md)
- [<span data-ttu-id="80026-128">Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="80026-128">Constructors</span></span>](constructors.md)
- [<span data-ttu-id="80026-129">`let`-Bindungen in Klassen</span><span class="sxs-lookup"><span data-stu-id="80026-129">`let` Bindings in Classes</span></span>](let-bindings-in-classes.md)
- [<span data-ttu-id="80026-130">`do` Bindungen</span><span class="sxs-lookup"><span data-stu-id="80026-130">`do` Bindings</span></span>](../functions/do-Bindings.md)
