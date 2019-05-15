---
title: Delegaten
description: Informationen zum Arbeiten mit Delegaten F#.
ms.date: 05/16/2016
ms.openlocfilehash: 0596b67530b0399df41dffdf855a07bce2bf4761
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641971"
---
# <a name="delegates"></a><span data-ttu-id="85992-103">Delegaten</span><span class="sxs-lookup"><span data-stu-id="85992-103">Delegates</span></span>

<span data-ttu-id="85992-104">Ein Delegat stellt einen Funktionsaufruf dar, wie ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="85992-104">A delegate represents a function call as an object.</span></span> <span data-ttu-id="85992-105">In F#, normalerweise verwenden Sie Werte von Funktionen zum Darstellen von Funktionen als erstrangige Werte; Allerdings Delegaten in .NET Framework verwendet werden und daher sind erforderlich, wenn Interoperation mit APIs, die sie erwarten.</span><span class="sxs-lookup"><span data-stu-id="85992-105">In F#, you ordinarily should use function values to represent functions as first-class values; however, delegates are used in the .NET Framework and so are needed when you interoperate with APIs that expect them.</span></span> <span data-ttu-id="85992-106">Sie können auch authoring Bibliotheken zur Verwendung von anderen .NET Framework-Sprachen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85992-106">They may also be used when authoring libraries designed for use from other .NET Framework languages.</span></span>

## <a name="syntax"></a><span data-ttu-id="85992-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="85992-107">Syntax</span></span>

```fsharp
type delegate-typename = delegate of type1 -> type2
```

## <a name="remarks"></a><span data-ttu-id="85992-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85992-108">Remarks</span></span>

<span data-ttu-id="85992-109">In der vorherigen Syntax `type1` stellt den Argumenttyp bzw. die Datentypen und `type2` den Rückgabetyp darstellt.</span><span class="sxs-lookup"><span data-stu-id="85992-109">In the previous syntax, `type1` represents the argument type or types and `type2` represents the return type.</span></span> <span data-ttu-id="85992-110">Die Argumenttypen, das von dargestellt sind `type1` werden automatisch mit Currying.</span><span class="sxs-lookup"><span data-stu-id="85992-110">The argument types that are represented by `type1` are automatically curried.</span></span> <span data-ttu-id="85992-111">Dies deutet darauf hin, die für diesen Typ, der Sie ein Tupel-Formular verwenden, wenn die Argumente der Zielfunktion Currying verarbeitet werden, und ein Tupel in Klammern für Argumente, die bereits in der Tupelform sind.</span><span class="sxs-lookup"><span data-stu-id="85992-111">This suggests that for this type you use a tuple form if the arguments of the target function are curried, and a parenthesized tuple for arguments that are already in the tuple form.</span></span> <span data-ttu-id="85992-112">Die automatische currying entfernt einen Satz von Klammern, sodass ein Tupelargument, das die Zielmethode entspricht.</span><span class="sxs-lookup"><span data-stu-id="85992-112">The automatic currying removes a set of parentheses, leaving a tuple argument that matches the target method.</span></span> <span data-ttu-id="85992-113">Finden Sie im Codebeispiel wird die Syntax, die Sie in jedem Fall verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="85992-113">Refer to the code example for the syntax you should use in each case.</span></span>

<span data-ttu-id="85992-114">Delegaten angefügt werden können, um F#-Funktionswerte, und statische oder Instanzmethoden.</span><span class="sxs-lookup"><span data-stu-id="85992-114">Delegates can be attached to F# function values, and static or instance methods.</span></span> <span data-ttu-id="85992-115">F#Werte von Funktionen können direkt als Argumente für das Delegieren von Konstruktoren übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="85992-115">F# function values can be passed directly as arguments to delegate constructors.</span></span> <span data-ttu-id="85992-116">Für eine statische Methode erstellen Sie den Delegaten, mit dem Namen der Klasse und Methode.</span><span class="sxs-lookup"><span data-stu-id="85992-116">For a static method, you construct the delegate by using the name of the class and the method.</span></span> <span data-ttu-id="85992-117">Für eine Instanzmethode stellen Sie die Objektinstanz und der-Methode in ein Argument bereit.</span><span class="sxs-lookup"><span data-stu-id="85992-117">For an instance method, you provide the object instance and method in one argument.</span></span> <span data-ttu-id="85992-118">In beiden Fällen der Memberzugriffsoperator (`.`) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="85992-118">In both cases, the member access operator (`.`) is used.</span></span>

<span data-ttu-id="85992-119">Die `Invoke` Methode auf dem Delegattyp die gekapselte Funktion aufruft.</span><span class="sxs-lookup"><span data-stu-id="85992-119">The `Invoke` method on the delegate type calls the encapsulated function.</span></span> <span data-ttu-id="85992-120">Darüber hinaus können Delegaten durch Verweisen auf den Namen des Invoke-Methode ohne Klammern als Werte von Funktionen übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="85992-120">Also, delegates can be passed as function values by referencing the Invoke method name without the parentheses.</span></span>

<span data-ttu-id="85992-121">Der folgende Code zeigt die Syntax zum Erstellen von Delegaten, die verschiedene Methoden in einer Klasse darstellen.</span><span class="sxs-lookup"><span data-stu-id="85992-121">The following code shows the syntax for creating delegates that represent various methods in a class.</span></span> <span data-ttu-id="85992-122">Je nachdem, ob die Methode eine statische Methode oder eine Instanzmethode ist, und gibt an, ob Argumente im Tupel Format oder die Curry-Form verfügt ist die Syntax zum Deklarieren und Zuweisen von Delegaten ein wenig anders.</span><span class="sxs-lookup"><span data-stu-id="85992-122">Depending on whether the method is a static method or an instance method, and whether it has arguments in the tuple form or the curried form, the syntax for declaring and assigning the delegate is a little different.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4201.fs)]

<span data-ttu-id="85992-123">Der folgende Code zeigt einige der Möglichkeiten, mit denen, die Sie Delegaten zusammenarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="85992-123">The following code shows some of the different ways you can work with delegates.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4202.fs)]

<span data-ttu-id="85992-124">Die Ausgabe des vorherigen Codebeispiel lautet wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="85992-124">The output of the previous code example is as follows.</span></span>

```console
aaaaa
bbbbb
ccccc
[|"aaa"; "bbb"|]
```

## <a name="see-also"></a><span data-ttu-id="85992-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85992-125">See also</span></span>

- [<span data-ttu-id="85992-126">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="85992-126">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="85992-127">Parameter und Argumente</span><span class="sxs-lookup"><span data-stu-id="85992-127">Parameters and Arguments</span></span>](parameters-and-arguments.md)
- [<span data-ttu-id="85992-128">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="85992-128">Events</span></span>](members/events.md)
