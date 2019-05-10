---
title: Overloads (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: ab8660ff0cf02956e760132f5aad69e359913950
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661083"
---
# <a name="overloads-visual-basic"></a><span data-ttu-id="d7a6b-102">Overloads (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7a6b-102">Overloads (Visual Basic)</span></span>
<span data-ttu-id="d7a6b-103">Gibt an, dass eine Eigenschaft oder Prozedur eine Eigenschaft oder Prozedur bzw. mehrere mit dem gleichen Namen neu deklariert.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-103">Specifies that a property or procedure redeclares one or more existing properties or procedures with the same name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7a6b-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d7a6b-104">Remarks</span></span>  
 <span data-ttu-id="d7a6b-105">*Überladen von* wird die Bereitstellung von mehr als eine Definition für einen angegebenen Eigenschaft oder Prozedur im gleichen Bereich.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-105">*Overloading* is the practice of supplying more than one definition for a given property or procedure name in the same scope.</span></span> <span data-ttu-id="d7a6b-106">Durch das erneute Deklarieren einer Eigenschaft oder Prozedur mit einer anderen Signatur wird gelegentlich aufgerufen *Ausblenden nach Signatur*.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-106">Redeclaring a property or procedure with a different signature is sometimes called *hiding by signature*.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="d7a6b-107">Regeln</span><span class="sxs-lookup"><span data-stu-id="d7a6b-107">Rules</span></span>  
  
- <span data-ttu-id="d7a6b-108">**Deklarationskontext.**</span><span class="sxs-lookup"><span data-stu-id="d7a6b-108">**Declaration Context.**</span></span> <span data-ttu-id="d7a6b-109">Sie können `Overloads` nur in einer Eigenschaft oder einer Prozedurdeklarationsanweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-109">You can use `Overloads` only in a property or procedure declaration statement.</span></span>  
  
- <span data-ttu-id="d7a6b-110">**Kombinierte Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="d7a6b-110">**Combined Modifiers.**</span></span> <span data-ttu-id="d7a6b-111">Sie können keine angeben `Overloads` zusammen mit [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in derselben Prozedurdeklaration.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-111">You cannot specify `Overloads` together with [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) in the same procedure declaration.</span></span>  
  
- <span data-ttu-id="d7a6b-112">**Erforderliche Unterschiede.**</span><span class="sxs-lookup"><span data-stu-id="d7a6b-112">**Required Differences.**</span></span> <span data-ttu-id="d7a6b-113">Die *Signatur* in dieser Deklaration muss sich von der Signatur jeder Eigenschaft oder Prozedur, die sie überlädt.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-113">The *signature* in this declaration must be different from the signature of every property or procedure that it overloads.</span></span> <span data-ttu-id="d7a6b-114">Die Signatur besteht aus der Eigenschaft oder dem Prozedurnamen und dem Folgenden:</span><span class="sxs-lookup"><span data-stu-id="d7a6b-114">The signature comprises the property or procedure name together with the following:</span></span>  
  
    - <span data-ttu-id="d7a6b-115">der Anzahl der Parameter</span><span class="sxs-lookup"><span data-stu-id="d7a6b-115">the number of parameters</span></span>  
  
    - <span data-ttu-id="d7a6b-116">Der Reihenfolge der Parameter</span><span class="sxs-lookup"><span data-stu-id="d7a6b-116">the order of the parameters</span></span>  
  
    - <span data-ttu-id="d7a6b-117">der Datentypen der Parameter</span><span class="sxs-lookup"><span data-stu-id="d7a6b-117">the data types of the parameters</span></span>  
  
    - <span data-ttu-id="d7a6b-118">der Anzahl der Typparameter (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="d7a6b-118">the number of type parameters (for a generic procedure)</span></span>  
  
    - <span data-ttu-id="d7a6b-119">der Rückgabetyp (nur für eine Konvertierungsoperatorprozedur)</span><span class="sxs-lookup"><span data-stu-id="d7a6b-119">the return type (only for a conversion operator procedure)</span></span>  
  
     <span data-ttu-id="d7a6b-120">Alle Überladungen müssen denselben Namen aufweisen. Jede muss sich jedoch von allen anderen in mindestens einem der vorstehenden Punkte unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-120">All overloads must have the same name, but each must differ from all the others in one or more of the preceding respects.</span></span> <span data-ttu-id="d7a6b-121">Dadurch kann der Compiler unterscheiden, welche Version verwendet werden muss, wenn der Code die Eigenschaft oder Prozedur aufruft.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-121">This allows the compiler to distinguish which version to use when code calls the property or procedure.</span></span>  
  
- <span data-ttu-id="d7a6b-122">**Nicht zulässige Unterschiede.**</span><span class="sxs-lookup"><span data-stu-id="d7a6b-122">**Disallowed Differences.**</span></span> <span data-ttu-id="d7a6b-123">Das Ändern von mindestens einem der folgenden Punkte ist für das Überladen einer Eigenschaft oder Prozedur nicht gültig, da sie kein Bestandteil der Signatur sind:</span><span class="sxs-lookup"><span data-stu-id="d7a6b-123">Changing one or more of the following is not valid for overloading a property or procedure, because they are not part of the signature:</span></span>  
  
    - <span data-ttu-id="d7a6b-124">ob ein Wert (für eine Prozedur) zurückgegeben wird</span><span class="sxs-lookup"><span data-stu-id="d7a6b-124">whether or not it returns a value (for a procedure)</span></span>  
  
    - <span data-ttu-id="d7a6b-125">der Datentyp des Rückgabewerts (mit Ausnahme eines Konvertierungsoperators)</span><span class="sxs-lookup"><span data-stu-id="d7a6b-125">the data type of the return value (except for a conversion operator)</span></span>  
  
    - <span data-ttu-id="d7a6b-126">die Namen der Parameter oder Typparameter</span><span class="sxs-lookup"><span data-stu-id="d7a6b-126">the names of the parameters or type parameters</span></span>  
  
    - <span data-ttu-id="d7a6b-127">die Einschränkungen hinsichtlich der Typparameter (für eine generische Prozedur)</span><span class="sxs-lookup"><span data-stu-id="d7a6b-127">the constraints on the type parameters (for a generic procedure)</span></span>  
  
    - <span data-ttu-id="d7a6b-128">Parametermodifiziererschlüsselwörter (wie `ByRef` oder `Optional`)</span><span class="sxs-lookup"><span data-stu-id="d7a6b-128">parameter modifier keywords (such as `ByRef` or `Optional`)</span></span>  
  
    - <span data-ttu-id="d7a6b-129">Eigenschaft oder Prozedurmodifiziererschlüsselwörter (wie `Public` oder `Shared`)</span><span class="sxs-lookup"><span data-stu-id="d7a6b-129">property or procedure modifier keywords (such as `Public` or `Shared`)</span></span>  
  
- <span data-ttu-id="d7a6b-130">**Optionaler Modifizierer.**</span><span class="sxs-lookup"><span data-stu-id="d7a6b-130">**Optional Modifier.**</span></span> <span data-ttu-id="d7a6b-131">Sie müssen den `Overloads`-Modifizierer nicht verwenden, wenn Sie mehrere überladene Eigenschaften oder Prozeduren in derselben Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-131">You do not have to use the `Overloads` modifier when you are defining multiple overloaded properties or procedures in the same class.</span></span> <span data-ttu-id="d7a6b-132">Wenn Sie jedoch `Overloads` in einer der Deklarationen verwenden, müssen Sie sie in allen davon verwenden.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-132">However, if you use `Overloads` in one of the declarations, you must use it in all of them.</span></span>  
  
- <span data-ttu-id="d7a6b-133">**Shadowing und Überladung.**</span><span class="sxs-lookup"><span data-stu-id="d7a6b-133">**Shadowing and Overloading.**</span></span> <span data-ttu-id="d7a6b-134">`Overloads` kann auch auf ein vorhandenes Member oder eine Gruppe von überladenen Membern in einer Basisklasse verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-134">`Overloads` can also be used to shadow an existing member, or set of overloaded members, in a base class.</span></span> <span data-ttu-id="d7a6b-135">Wenn Sie `Overloads` auf diese Art und Weise verwenden, deklarieren Sie die Eigenschaft oder Methode mit demselben Namen und derselben Parameterliste als Basisklassenmember, und Sie stellen das `Shadows`-Schlüsselwort nicht bereit.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-135">When you use `Overloads` in this way, you declare the property or method with the same name and the same parameter list as the base class member, and you do not supply the `Shadows` keyword.</span></span>  
  
 <span data-ttu-id="d7a6b-136">Beim Verwenden von `Overrides` fügt der Compiler implizit `Overloads` hinzu, sodass Ihre Bibliotheks-APIs leichter mit C# verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d7a6b-136">If you use `Overrides`, the compiler implicitly adds `Overloads` so that your library APIs work with C# more easily.</span></span>  
  
 <span data-ttu-id="d7a6b-137">Der `Overloads`-Modifizierer kann in folgenden Kontexten verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="d7a6b-137">The `Overloads` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="d7a6b-138">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d7a6b-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="d7a6b-139">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d7a6b-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [<span data-ttu-id="d7a6b-140">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d7a6b-140">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="d7a6b-141">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d7a6b-141">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="d7a6b-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d7a6b-142">See also</span></span>

- [<span data-ttu-id="d7a6b-143">Shadows</span><span class="sxs-lookup"><span data-stu-id="d7a6b-143">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)
- [<span data-ttu-id="d7a6b-144">Prozedurüberladung</span><span class="sxs-lookup"><span data-stu-id="d7a6b-144">Procedure Overloading</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [<span data-ttu-id="d7a6b-145">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7a6b-145">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="d7a6b-146">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="d7a6b-146">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [<span data-ttu-id="d7a6b-147">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="d7a6b-147">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
