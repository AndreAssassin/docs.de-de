---
title: Property-Anweisung (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 7b2d388cbcd1995178adf4102520ecaa1c9b1889
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783993"
---
# <a name="property-statement"></a><span data-ttu-id="b48a7-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="b48a7-102">Property Statement</span></span>

<span data-ttu-id="b48a7-103">Deklariert den Namen einer Eigenschaft sowie die Eigenschaftenprozeduren zum Speichern und Abrufen des Werts der Eigenschaft verwendet.</span><span class="sxs-lookup"><span data-stu-id="b48a7-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="b48a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b48a7-104">Syntax</span></span>

```vb
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
    [ <attributelist> ] [ accessmodifier ] Get
        [ statements ]
    End Get
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )
        [ statements ]
    End Set
End Property
- or -
[ <attributelist> ] [ Default ] [ accessmodifier ]
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]
```

## <a name="parts"></a><span data-ttu-id="b48a7-105">Teile</span><span class="sxs-lookup"><span data-stu-id="b48a7-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="b48a7-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-106">Optional.</span></span> <span data-ttu-id="b48a7-107">Liste der Attribute, die für diese Eigenschaft gelten oder `Get` oder `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="b48a7-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="b48a7-108">Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="b48a7-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-109">Optional.</span></span> <span data-ttu-id="b48a7-110">Gibt an, dass diese Eigenschaft ist die Standardeigenschaft für die Klasse oder Struktur, die auf dem sie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b48a7-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="b48a7-111">Standardeigenschaften können muss Parameter annehmen und festgelegt und ohne Angabe der Namen der Eigenschaft abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b48a7-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="b48a7-112">Wenn Sie die Eigenschaft als deklarieren `Default`, können keine `Private` auf die Eigenschaft oder einer der Eigenschaftenprozeduren.</span><span class="sxs-lookup"><span data-stu-id="b48a7-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="b48a7-113">Optional Klicken Sie auf die `Property` Anweisung und höchstens die `Get` und `Set` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b48a7-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="b48a7-114">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="b48a7-114">Can be one of the following:</span></span>

  - [<span data-ttu-id="b48a7-115">Public</span><span class="sxs-lookup"><span data-stu-id="b48a7-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)

  - [<span data-ttu-id="b48a7-116">Protected</span><span class="sxs-lookup"><span data-stu-id="b48a7-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)

  - [<span data-ttu-id="b48a7-117">Friend</span><span class="sxs-lookup"><span data-stu-id="b48a7-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)

  - [<span data-ttu-id="b48a7-118">Private</span><span class="sxs-lookup"><span data-stu-id="b48a7-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)

  - [<span data-ttu-id="b48a7-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="b48a7-119">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md)

  - [<span data-ttu-id="b48a7-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="b48a7-120">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)

  <span data-ttu-id="b48a7-121">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-121">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="b48a7-122">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-122">Optional.</span></span> <span data-ttu-id="b48a7-123">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="b48a7-123">Can be one of the following:</span></span>

  - [<span data-ttu-id="b48a7-124">Overloads</span><span class="sxs-lookup"><span data-stu-id="b48a7-124">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)

  - [<span data-ttu-id="b48a7-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="b48a7-125">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)

  - [<span data-ttu-id="b48a7-126">Overridable</span><span class="sxs-lookup"><span data-stu-id="b48a7-126">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)

  - [<span data-ttu-id="b48a7-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="b48a7-127">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)

  - [<span data-ttu-id="b48a7-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="b48a7-128">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="b48a7-129">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-129">Optional.</span></span> <span data-ttu-id="b48a7-130">Finden Sie unter [freigegebene](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-130">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="b48a7-131">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-131">Optional.</span></span> <span data-ttu-id="b48a7-132">Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-132">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="b48a7-133">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-133">Optional.</span></span> <span data-ttu-id="b48a7-134">Finden Sie unter [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-134">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="b48a7-135">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-135">Optional.</span></span> <span data-ttu-id="b48a7-136">Finden Sie unter [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-136">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="b48a7-137">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-137">Optional.</span></span> <span data-ttu-id="b48a7-138">Finden Sie unter [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-138">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="b48a7-139">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b48a7-139">Required.</span></span> <span data-ttu-id="b48a7-140">Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b48a7-140">Name of the property.</span></span> <span data-ttu-id="b48a7-141">Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-141">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="b48a7-142">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-142">Optional.</span></span> <span data-ttu-id="b48a7-143">Liste der Namen lokaler Variablen darstellt, die Parameter dieser Eigenschaft, und mögliche zusätzliche Parameter, der die `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="b48a7-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="b48a7-144">Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-144">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="b48a7-145">Erforderlich, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="b48a7-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="b48a7-146">Der Datentyp des von dieser Eigenschaft zurückgegebenen Werts.</span><span class="sxs-lookup"><span data-stu-id="b48a7-146">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="b48a7-147">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-147">Optional.</span></span> <span data-ttu-id="b48a7-148">Gibt an, dass diese Eigenschaft implementiert wird, eine oder mehrere Eigenschaften, die jeweils in einer Schnittstelle implementiert, die von dieser Eigenschaft enthaltende Klasse oder Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="b48a7-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="b48a7-149">Finden Sie unter [Anweisung implementiert](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-149">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="b48a7-150">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b48a7-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="b48a7-151">Liste der Eigenschaften, die implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="b48a7-151">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="b48a7-152">Jede `implementedproperty` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="b48a7-152">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="b48a7-153">Segment</span><span class="sxs-lookup"><span data-stu-id="b48a7-153">Part</span></span>|<span data-ttu-id="b48a7-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b48a7-154">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="b48a7-155">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b48a7-155">Required.</span></span> <span data-ttu-id="b48a7-156">Name einer Schnittstelle implementiert, die von dieser Eigenschaft der enthaltenden Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="b48a7-156">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="b48a7-157">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b48a7-157">Required.</span></span> <span data-ttu-id="b48a7-158">Mit dem die Eigenschaft, im definiert ist Namen `interface`.</span><span class="sxs-lookup"><span data-stu-id="b48a7-158">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="b48a7-159">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-159">Optional.</span></span> <span data-ttu-id="b48a7-160">Erforderlich, wenn die Eigenschaft markiert ist `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="b48a7-160">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="b48a7-161">Startet eine `Get` Eigenschaftenprozedur, die verwendet wird, um den Wert der Eigenschaft zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="b48a7-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>

- `statements`

  <span data-ttu-id="b48a7-162">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-162">Optional.</span></span> <span data-ttu-id="b48a7-163">Block von Anweisungen für die Ausführung innerhalb der `Get` oder `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="b48a7-163">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="b48a7-164">Beendet die `Get` Eigenschaftenprozedur.</span><span class="sxs-lookup"><span data-stu-id="b48a7-164">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="b48a7-165">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b48a7-165">Optional.</span></span> <span data-ttu-id="b48a7-166">Erforderlich, wenn die Eigenschaft markiert ist `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="b48a7-166">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="b48a7-167">Startet eine `Set` Eigenschaftenprozedur, die zum Speichern des Werts der Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b48a7-167">Starts a `Set` property procedure that is used to store the value of the property.</span></span>

- `End Set`

  <span data-ttu-id="b48a7-168">Beendet die `Set` Eigenschaftenprozedur.</span><span class="sxs-lookup"><span data-stu-id="b48a7-168">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="b48a7-169">Beendet die Definition dieser Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b48a7-169">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="b48a7-170">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b48a7-170">Remarks</span></span>

<span data-ttu-id="b48a7-171">Die `Property` -Anweisung führt die Deklaration einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b48a7-171">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="b48a7-172">Eine Eigenschaft haben eine `Get` Verfahren (schreibgeschützt), eine `Set` Prozedur (lesegeschützt) oder beide (Lese-/ Schreibzugriff).</span><span class="sxs-lookup"><span data-stu-id="b48a7-172">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="b48a7-173">Können Sie weglassen der `Get` und `Set` Verfahren, wenn Sie eine automatisch implementierte Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b48a7-173">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="b48a7-174">Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-174">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="b48a7-175">Sie können `Property` nur auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="b48a7-175">You can use `Property` only at class level.</span></span> <span data-ttu-id="b48a7-176">Dies bedeutet, dass die *Deklarationskontext* für eine Eigenschaft eine Klasse, Struktur, Modul oder Schnittstelle sein muss und darf nicht, eine Quelldatei, Namespace, Prozedur oder Block sein.</span><span class="sxs-lookup"><span data-stu-id="b48a7-176">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="b48a7-177">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="b48a7-177">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="b48a7-178">Standardmäßig verwenden Eigenschaften öffentlicher Zugriff.</span><span class="sxs-lookup"><span data-stu-id="b48a7-178">By default, properties use public access.</span></span> <span data-ttu-id="b48a7-179">Sie können die Zugriffsebene für eine Eigenschaft mit einem Zugriffsmodifizierer anpassen, auf die `Property` -Anweisung, und Sie können optional anpassen, einer der Eigenschaftenprozeduren zu einer stärker einschränkende Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="b48a7-179">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="b48a7-180">Visual Basic übergibt einen Parameter für die `Set` Prozedur während der eigenschaftenzuweisungen.</span><span class="sxs-lookup"><span data-stu-id="b48a7-180">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="b48a7-181">Wenn Sie keine Parameter für angeben `Set`, die integrierte Entwicklungsumgebung (IDE) verwendet einen impliziten Parameter mit dem Namen `value`.</span><span class="sxs-lookup"><span data-stu-id="b48a7-181">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="b48a7-182">Dieser Parameter enthält den Wert der Eigenschaft zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="b48a7-182">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="b48a7-183">In der Regel diesen Wert in einer privaten lokalen Variable speichern und zurückgeben immer die `Get` Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b48a7-183">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="b48a7-184">Regeln</span><span class="sxs-lookup"><span data-stu-id="b48a7-184">Rules</span></span>

- <span data-ttu-id="b48a7-185">**Gemischte Zugriffsebenen.**</span><span class="sxs-lookup"><span data-stu-id="b48a7-185">**Mixed Access Levels.**</span></span> <span data-ttu-id="b48a7-186">Wenn Sie eine Eigenschaft mit Lese-/ Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene angeben, entweder die `Get` oder `Set` Prozedur, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="b48a7-186">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="b48a7-187">Wenn Sie dies tun, muss die Zugriffsebene der Prozedur restriktiver ist als die Zugriffsebene der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b48a7-187">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="b48a7-188">Z. B., wenn die Eigenschaft deklariert ist `Friend`, Sie können deklarieren, die `Set` Prozedur `Private`, aber nicht `Public`.</span><span class="sxs-lookup"><span data-stu-id="b48a7-188">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="b48a7-189">Wenn Sie definieren eine `ReadOnly` oder `WriteOnly` -Eigenschaft, die Eigenschaftenprozedur (`Get` oder `Set`bzw.) stellt alle von der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="b48a7-189">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="b48a7-190">Sie können nicht für eine Prozedur, eine andere Zugriffsebene deklarieren, da es sich bei, der zwei Zugriffsebenen für die Eigenschaft festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="b48a7-190">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="b48a7-191">**Der Rückgabetyp.**</span><span class="sxs-lookup"><span data-stu-id="b48a7-191">**Return Type.**</span></span> <span data-ttu-id="b48a7-192">Die `Property` Anweisung kann deklarieren, den den Datentyp des zurückgegebenen Werts.</span><span class="sxs-lookup"><span data-stu-id="b48a7-192">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="b48a7-193">Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="b48a7-193">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="b48a7-194">Wenn Sie keinen angeben `returntype`, gibt die Eigenschaft `Object`.</span><span class="sxs-lookup"><span data-stu-id="b48a7-194">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="b48a7-195">**-Implementierung.**</span><span class="sxs-lookup"><span data-stu-id="b48a7-195">**Implementation.**</span></span> <span data-ttu-id="b48a7-196">Wenn diese Eigenschaft verwendet die `Implements` -Schlüsselwort, die enthaltende Klasse oder Struktur müssen ein `Implements` Anweisung unmittelbar nach seiner `Class` oder `Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b48a7-196">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="b48a7-197">Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="b48a7-197">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="b48a7-198">Jedoch den Namen, die mit dem eine Schnittstelle definiert die `Property` (in `definedname`) muss nicht der Name dieser Eigenschaft identisch sein (in `name`).</span><span class="sxs-lookup"><span data-stu-id="b48a7-198">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="b48a7-199">Verhalten</span><span class="sxs-lookup"><span data-stu-id="b48a7-199">Behavior</span></span>

- <span data-ttu-id="b48a7-200">**Zurückgeben einer Eigenschaftenprozedur.**</span><span class="sxs-lookup"><span data-stu-id="b48a7-200">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="b48a7-201">Wenn die `Get` oder `Set` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgesetzt, mit der Anweisung nach der Anweisung, die sie aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="b48a7-201">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="b48a7-202">Die `Exit Property` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung einer Eigenschaftenprozedur.</span><span class="sxs-lookup"><span data-stu-id="b48a7-202">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="b48a7-203">Eine beliebige Anzahl von `Exit Property` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Property` und `Return` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b48a7-203">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="b48a7-204">**Der Rückgabewert.**</span><span class="sxs-lookup"><span data-stu-id="b48a7-204">**Return Value.**</span></span> <span data-ttu-id="b48a7-205">Zum Zurückgeben eines Werts aus einer `Get` Verfahren, Sie können entweder weisen Sie den Wert an den Eigenschaftennamen oder nehmen Sie diese in einem `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="b48a7-205">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="b48a7-206">Das folgende Beispiel weist den Rückgabewert an den Eigenschaftennamen `quoteForTheDay` und verwendet dann die `Exit Property` -Anweisung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b48a7-206">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="b48a7-207">Bei Verwendung von `Exit Property` ohne Zuweisen eines Werts zu `name`, `Get` Prozedur gibt den Standardwert für den Datentyp der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="b48a7-207">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="b48a7-208">Die `Return` Anweisung zur gleichen Zeit weist der `Get` Prozedur zurückgeben, Wert und Beenden der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="b48a7-208">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="b48a7-209">Das folgende Beispiel zeigt dies.</span><span class="sxs-lookup"><span data-stu-id="b48a7-209">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="b48a7-210">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b48a7-210">Example</span></span>

<span data-ttu-id="b48a7-211">Das folgende Beispiel deklariert eine Eigenschaft in einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="b48a7-211">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="b48a7-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b48a7-212">See also</span></span>

- [<span data-ttu-id="b48a7-213">Automatisch implementierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b48a7-213">Auto-Implemented Properties</span></span>](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="b48a7-214">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="b48a7-214">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="b48a7-215">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b48a7-215">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="b48a7-216">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b48a7-216">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
- [<span data-ttu-id="b48a7-217">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="b48a7-217">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)
- [<span data-ttu-id="b48a7-218">Default</span><span class="sxs-lookup"><span data-stu-id="b48a7-218">Default</span></span>](../../../visual-basic/language-reference/modifiers/default.md)
