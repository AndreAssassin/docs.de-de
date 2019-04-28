---
title: Zugriffssteuerung
description: Informationen Sie zum Steuern des Zugriffs auf Programmierelemente wie Typen, Methoden und Funktionen, die in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: 8db178b26f3beb6ce95bff84ccad9ac9e8c40ce7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772735"
---
# <a name="access-control"></a><span data-ttu-id="1472c-103">Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="1472c-103">Access Control</span></span>

<span data-ttu-id="1472c-104">*Steuerung des Zugriffs* bezieht sich auf die deklarieren, welche Clients bestimmte Programmelemente, z. B. Typen, Methoden und Funktionen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1472c-104">*Access control* refers to declaring which clients can use certain program elements, such as types, methods, and functions.</span></span>

## <a name="basics-of-access-control"></a><span data-ttu-id="1472c-105">Grundlagen der Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="1472c-105">Basics of Access Control</span></span>

<span data-ttu-id="1472c-106">In F#, Steuern der Zugriff Spezifizierer `public`, `internal`, und `private` kann auf Module, Typen, Methoden, wertedefinitionen, Funktionen, Eigenschaften und explizite Felder angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1472c-106">In F#, the access control specifiers `public`, `internal`, and `private` can be applied to modules, types, methods, value definitions, functions, properties, and explicit fields.</span></span>

- <span data-ttu-id="1472c-107">`public` Gibt an, dass die Entität, die von allen Aufrufern zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1472c-107">`public` indicates that the entity can be accessed by all callers.</span></span>

- <span data-ttu-id="1472c-108">`internal` Gibt an, dass die Entität, die nur von der gleichen Assembly zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1472c-108">`internal` indicates that the entity can be accessed only from the same assembly.</span></span>

- <span data-ttu-id="1472c-109">`private` Gibt an, dass die Entität nur aus dem einschließenden Typ oder Modul zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1472c-109">`private` indicates that the entity can be accessed only from the enclosing type or module.</span></span>

> [!NOTE]
> <span data-ttu-id="1472c-110">Der Zugriffsspezifizierer `protected` wird nicht in F# verwendet, obwohl es akzeptabel ist, bei Verwendung von Typen, die in Sprachen, unterstützen erstellte `protected` Zugriff.</span><span class="sxs-lookup"><span data-stu-id="1472c-110">The access specifier `protected` is not used in F#, although it is acceptable if you are using types authored in languages that do support `protected` access.</span></span> <span data-ttu-id="1472c-111">Wenn Sie eine geschützte Methode überschreiben, bleibt die Methode aus diesem Grund nur innerhalb der Klasse und ihrer untergeordneten Klassen zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1472c-111">Therefore, if you override a protected method, your method remains accessible only within the class and its descendents.</span></span>

<span data-ttu-id="1472c-112">Der Bezeichner wird in der Regel vor dem Namen der Entität, außer wenn versetzt einen `mutable` oder `inline` Bezeichner verwendet wird, die nach dem Zugriffsspezifizierer-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1472c-112">In general, the specifier is put in front of the name of the entity, except when a `mutable` or `inline` specifier is used, which appear after the access control specifier.</span></span>

<span data-ttu-id="1472c-113">Wenn keine Zugriffsspezifizierer verwendet wird, wird der Standardwert ist `public`, mit Ausnahme von `let` Bindungen in einem Typ, der immer `private` in den Typ.</span><span class="sxs-lookup"><span data-stu-id="1472c-113">If no access specifier is used, the default is `public`, except for `let` bindings in a type, which are always `private` to the type.</span></span>

<span data-ttu-id="1472c-114">Signaturen in F#-Geben Sie einen anderen Mechanismus zur Steuerung des Zugriffs auf Programmelemente in F#.</span><span class="sxs-lookup"><span data-stu-id="1472c-114">Signatures in F# provide another mechanism for controlling access to F# program elements.</span></span> <span data-ttu-id="1472c-115">Signaturen sind nicht erforderlich, für die Zugriffssteuerung.</span><span class="sxs-lookup"><span data-stu-id="1472c-115">Signatures are not required for access control.</span></span> <span data-ttu-id="1472c-116">Weitere Informationen finden Sie unter [Signaturen](signatures.md).</span><span class="sxs-lookup"><span data-stu-id="1472c-116">For more information, see [Signatures](signatures.md).</span></span>

## <a name="rules-for-access-control"></a><span data-ttu-id="1472c-117">Regeln für die Zugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="1472c-117">Rules for Access Control</span></span>

<span data-ttu-id="1472c-118">Die Zugriffssteuerung ist gemäß den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="1472c-118">Access control is subject to the following rules:</span></span>

- <span data-ttu-id="1472c-119">, Vererbungsdeklarationen (, also die Verwendung von `inherit` auf eine Basisklasse für eine Klasse angeben), Schnittstellendeklarationen (das ist, gibt an, dass eine Klasse eine Schnittstelle implementiert) und abstrakten Member verfügen immer über den gleichen Zugriff wie der einschließende Typ.</span><span class="sxs-lookup"><span data-stu-id="1472c-119">Inheritance declarations (that is, the use of `inherit` to specify a base class for a class), interface declarations (that is, specifying that a class implements an interface), and abstract members always have the same accessibility as the enclosing type.</span></span> <span data-ttu-id="1472c-120">Aus diesem Grund kann ein Steuerelement-Zugriffsspezifizierer auf diese Konstrukte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1472c-120">Therefore, an access control specifier cannot be used on these constructs.</span></span>

- <span data-ttu-id="1472c-121">Zugriff auf einzelne Fälle, in eine Unterscheidungs-Union wird durch den Zugriff auf die Unterscheidungs-Union selbst bestimmt.</span><span class="sxs-lookup"><span data-stu-id="1472c-121">Accessibility for individual cases in a discriminated union is determined by the accessibility of the discriminated union itself.</span></span> <span data-ttu-id="1472c-122">Ein bestimmter union-Fall ist, also nicht weniger zugreifbar als die Union selbst.</span><span class="sxs-lookup"><span data-stu-id="1472c-122">That is, a particular union case is no less accessible than the union itself.</span></span>

- <span data-ttu-id="1472c-123">Barrierefreiheit für einzelne Felder eines Datensatztyps nicht möglich, der durch den Zugriff auf den Datensatz selbst bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="1472c-123">Accessibility for individual fields of a record type cannot is determined by the accessibility of the record itself.</span></span> <span data-ttu-id="1472c-124">Eine Bezeichnung bestimmten Datensatz ist, also nicht kleiner als der Datensatz selbst zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1472c-124">That is, a particular record label is no less accessible than the record itself.</span></span>

## <a name="example"></a><span data-ttu-id="1472c-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1472c-125">Example</span></span>

<span data-ttu-id="1472c-126">Der folgende Code veranschaulicht die Verwendung von Steuerelement-Zugriffsspezifizierer.</span><span class="sxs-lookup"><span data-stu-id="1472c-126">The following code illustrates the use of access control specifiers.</span></span> <span data-ttu-id="1472c-127">Es gibt zwei Dateien im Projekt `Module1.fs` und `Module2.fs`.</span><span class="sxs-lookup"><span data-stu-id="1472c-127">There are two files in the project, `Module1.fs` and `Module2.fs`.</span></span> <span data-ttu-id="1472c-128">Jede Datei ist implizit ein Modul.</span><span class="sxs-lookup"><span data-stu-id="1472c-128">Each file is implicitly a module.</span></span> <span data-ttu-id="1472c-129">Aus diesem Grund sind die beiden Module, `Module1` und `Module2`.</span><span class="sxs-lookup"><span data-stu-id="1472c-129">Therefore, there are two modules, `Module1` and `Module2`.</span></span> <span data-ttu-id="1472c-130">Ein privater Typ und einen internen Typ sind in definiert `Module1`.</span><span class="sxs-lookup"><span data-stu-id="1472c-130">A private type and an internal type are defined in `Module1`.</span></span> <span data-ttu-id="1472c-131">Der private Typ kann nicht zugegriffen werden, von `Module2`, aber Sie können der interne Typ.</span><span class="sxs-lookup"><span data-stu-id="1472c-131">The private type cannot be accessed from `Module2`, but the internal type can.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]

<span data-ttu-id="1472c-132">Der folgende Code überprüft den Zugriff auf die Typen, die im erstellten `Module1.fs`.</span><span class="sxs-lookup"><span data-stu-id="1472c-132">The following code tests the accessibility of the types created in `Module1.fs`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]

## <a name="see-also"></a><span data-ttu-id="1472c-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1472c-133">See also</span></span>

- [<span data-ttu-id="1472c-134">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="1472c-134">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="1472c-135">Signaturen</span><span class="sxs-lookup"><span data-stu-id="1472c-135">Signatures</span></span>](signatures.md)