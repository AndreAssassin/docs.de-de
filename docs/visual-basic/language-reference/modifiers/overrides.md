---
title: Overrides (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Overrides
- vb.Overrides
helpviewer_keywords:
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- Overrides keyword [Visual Basic]
- overriding, Overrides keyword
- properties [Visual Basic], overriding
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
ms.openlocfilehash: 9eb19bf5e89b12a32cae28b2c087570acc10f3ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826586"
---
# <a name="overrides-visual-basic"></a><span data-ttu-id="a0d2a-102">Overrides (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0d2a-102">Overrides (Visual Basic)</span></span>
<span data-ttu-id="a0d2a-103">Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur mit dem gleichen Namen überschreibt, die von einer Basisklasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="a0d2a-103">Specifies that a property or procedure overrides an identically named property or procedure inherited from a base class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0d2a-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0d2a-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="a0d2a-105">Regeln</span><span class="sxs-lookup"><span data-stu-id="a0d2a-105">Rules</span></span>  
  
-   <span data-ttu-id="a0d2a-106">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="a0d2a-106">**Declaration Context.**</span></span> <span data-ttu-id="a0d2a-107">Sie können `Overrides` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0d2a-107">You can use `Overrides` only in a property or procedure declaration statement.</span></span>  
  
-   <span data-ttu-id="a0d2a-108">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="a0d2a-108">**Combined Modifiers.**</span></span> <span data-ttu-id="a0d2a-109">Sie können `Overrides` nicht zusammen mit `Shadows` oder `Shared` in derselben Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="a0d2a-109">You cannot specify `Overrides` together with `Shadows` or `Shared` in the same declaration.</span></span> <span data-ttu-id="a0d2a-110">Da ein überschreibendes Element implizit überschreibbar ist, können Sie `Overridable` nicht mit `Overrides` kombinieren.</span><span class="sxs-lookup"><span data-stu-id="a0d2a-110">Because an overriding element is implicitly overridable, you cannot combine `Overridable` with `Overrides`.</span></span>  
  
-   <span data-ttu-id="a0d2a-111">**Übereinstimmende Signaturen.**</span><span class="sxs-lookup"><span data-stu-id="a0d2a-111">**Matching Signatures.**</span></span> <span data-ttu-id="a0d2a-112">Die Signatur dieser Deklaration muss genau übereinstimmen. die *Signatur* der Eigenschaft oder Prozedur, die sie überschreibt.</span><span class="sxs-lookup"><span data-stu-id="a0d2a-112">The signature of this declaration must exactly match the *signature* of the property or procedure that it overrides.</span></span> <span data-ttu-id="a0d2a-113">Das bedeutet, dass die Anzahl, die Reihenfolge und die Datentypen der Parameter in den Parameterlisten gleich sein müssen.</span><span class="sxs-lookup"><span data-stu-id="a0d2a-113">This means the parameter lists must have the same number of parameters, in the same order, with the same data types.</span></span>  
  
     <span data-ttu-id="a0d2a-114">Neben der Signatur müssen auch die folgenden Elemente der überschreibenden Deklaration genau übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="a0d2a-114">In addition to the signature, the overriding declaration must also exactly match the following:</span></span>  
  
    -   <span data-ttu-id="a0d2a-115">Die Zugriffsebene</span><span class="sxs-lookup"><span data-stu-id="a0d2a-115">The access level</span></span>  
  
    -   <span data-ttu-id="a0d2a-116">Der Rückgabetyp, falls vorhanden</span><span class="sxs-lookup"><span data-stu-id="a0d2a-116">The return type, if any</span></span>  
  
-   <span data-ttu-id="a0d2a-117">**Generische Signaturen.**</span><span class="sxs-lookup"><span data-stu-id="a0d2a-117">**Generic Signatures.**</span></span> <span data-ttu-id="a0d2a-118">Bei einer generischen Prozedur umfasst die Signatur die Anzahl der Typparameter.</span><span class="sxs-lookup"><span data-stu-id="a0d2a-118">For a generic procedure, the signature includes the number of type parameters.</span></span> <span data-ttu-id="a0d2a-119">Daher muss die überschreibende Deklaration auch in dieser Hinsicht mit der Basisklassenversion übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a0d2a-119">Therefore, the overriding declaration must match the base class version in that respect as well.</span></span>  
  
-   <span data-ttu-id="a0d2a-120">**Zusätzliche Übereinstimmung.**</span><span class="sxs-lookup"><span data-stu-id="a0d2a-120">**Additional Matching.**</span></span> <span data-ttu-id="a0d2a-121">Diese Deklaration muss nicht nur in Bezug auf die Signatur, sondern auch in folgenden Punkten mit der Basisklassenversion übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="a0d2a-121">In addition to matching the signature of the base class version, this declaration must also match it in the following respects:</span></span>  
  
    -   <span data-ttu-id="a0d2a-122">Zugriffsebenenmodifizierer (z. B. [öffentliche](../../../visual-basic/language-reference/modifiers/public.md))</span><span class="sxs-lookup"><span data-stu-id="a0d2a-122">Access-level modifier (such as [Public](../../../visual-basic/language-reference/modifiers/public.md))</span></span>  
  
    -   <span data-ttu-id="a0d2a-123">Übergabemechanismus jedes Parameters ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span><span class="sxs-lookup"><span data-stu-id="a0d2a-123">Passing mechanism of each parameter ([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../visual-basic/language-reference/modifiers/byref.md))</span></span>  
  
    -   <span data-ttu-id="a0d2a-124">Einschränkungslisten für jeden Typparameter einer generischen Prozedur</span><span class="sxs-lookup"><span data-stu-id="a0d2a-124">Constraint lists on each type parameter of a generic procedure</span></span>  
  
-   <span data-ttu-id="a0d2a-125">**Shadowing und überschreiben.**</span><span class="sxs-lookup"><span data-stu-id="a0d2a-125">**Shadowing and Overriding.**</span></span> <span data-ttu-id="a0d2a-126">Sowohl das Shadowing als auch das Überschreiben definieren ein geerbtes Element neu, es gibt jedoch bedeutende Unterschiede zwischen den beiden Vorgehensweisen.</span><span class="sxs-lookup"><span data-stu-id="a0d2a-126">Both shadowing and overriding redefine an inherited element, but there are significant differences between the two approaches.</span></span> <span data-ttu-id="a0d2a-127">Weitere Informationen finden Sie unter [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span><span class="sxs-lookup"><span data-stu-id="a0d2a-127">For more information, see [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).</span></span>  
  
 <span data-ttu-id="a0d2a-128">Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks-APIs leichter mit C# verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a0d2a-128">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="a0d2a-129">Der `Overrides`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="a0d2a-129">The `Overrides` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="a0d2a-130">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a0d2a-130">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="a0d2a-131">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a0d2a-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="a0d2a-132">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a0d2a-132">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="a0d2a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0d2a-133">See also</span></span>

- [<span data-ttu-id="a0d2a-134">MustOverride</span><span class="sxs-lookup"><span data-stu-id="a0d2a-134">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)
- [<span data-ttu-id="a0d2a-135">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="a0d2a-135">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)
- [<span data-ttu-id="a0d2a-136">Overridable</span><span class="sxs-lookup"><span data-stu-id="a0d2a-136">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)
- [<span data-ttu-id="a0d2a-137">Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a0d2a-137">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
- [<span data-ttu-id="a0d2a-138">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0d2a-138">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [<span data-ttu-id="a0d2a-139">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0d2a-139">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="a0d2a-140">Typliste</span><span class="sxs-lookup"><span data-stu-id="a0d2a-140">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
