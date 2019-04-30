---
title: Der in Imports '<qualifiedelementname>' angegebene Namespace oder Typ enthält keine öffentlichen Member oder kann nicht gefunden werden
ms.date: 07/20/2015
f1_keywords:
- bc40056
- vbc40056
helpviewer_keywords:
- BC40056
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
ms.openlocfilehash: 1873c0af7a251afd7754557f5dcb6aed13eb9f11
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918319"
---
# <a name="namespace-or-type-specified-in-the-imports-qualifiedelementname-doesnt-contain-any-public-member-or-cannot-be-found"></a><span data-ttu-id="fb8c9-102">Namespace oder Typ angegeben werden, in Imports'\<qualifizierter_elementname >' enthält keine öffentlichen Member oder wurde nicht gefunden</span><span class="sxs-lookup"><span data-stu-id="fb8c9-102">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found</span></span>

<span data-ttu-id="fb8c9-103">Namespace oder Typ angegeben werden, in Imports'\<qualifizierter_elementname >' enthält keine öffentlichen Member oder wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-103">Namespace or type specified in the Imports '\<qualifiedelementname>' doesn't contain any public member or cannot be found.</span></span> <span data-ttu-id="fb8c9-104">Stellen Sie sicher, dass der Namespace oder der Typ definiert ist und mindestens einen öffentliches Member enthält.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-104">Make sure the namespace or the type is defined and contains at least one public member.</span></span> <span data-ttu-id="fb8c9-105">Stellen Sie sicher, dass der Aliasname keine andere Aliase enthält.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-105">Make sure the alias name doesn't contain other aliases.</span></span>

<span data-ttu-id="fb8c9-106">Ein `Imports` Anweisung gibt ein enthaltendes Element, das entweder nicht gefunden werden kann, oder keine definiert `Public` Member.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-106">An `Imports` statement specifies a containing element that either cannot be found or does not define any `Public` members.</span></span>

<span data-ttu-id="fb8c9-107">Ein *, das Element enthält* -Namespace, Klasse, Struktur, Modul, Schnittstelle oder Enumeration sein kann.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-107">A *containing element* can be a namespace, class, structure, module, interface, or enumeration.</span></span> <span data-ttu-id="fb8c9-108">Das enthaltende Element enthält Member, z. B. Variablen, Prozeduren oder andere Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-108">The containing element contains members, such as variables, procedures, or other containing elements.</span></span>

<span data-ttu-id="fb8c9-109">Importieren von dient zu Ihrem Code, um Namespaces oder Typs auf Member zuzugreifen, ohne sie zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-109">The purpose of importing is to allow your code to access namespace or type members without having to qualify them.</span></span> <span data-ttu-id="fb8c9-110">Ihr Projekt müssen möglicherweise auch einen Verweis auf den Namespace oder Typ hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-110">Your project might also need to add a reference to the namespace or type.</span></span> <span data-ttu-id="fb8c9-111">Weitere Informationen finden Sie unter "Importieren von enthaltenen Elementen" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span><span class="sxs-lookup"><span data-stu-id="fb8c9-111">For more information, see "Importing Containing Elements" in [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).</span></span>

<span data-ttu-id="fb8c9-112">Wenn der Compiler das angegebene Element enthält, nicht finden kann, und klicken Sie dann nicht Verweise aufgelöst werden kann, die sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-112">If the compiler cannot find the specified containing element, then it cannot resolve references that use it.</span></span> <span data-ttu-id="fb8c9-113">Wenn das Element gefunden wird, das Element macht aber keine `Public` Elemente, und klicken Sie dann auf keinen Verweis kann erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-113">If it finds the element but the element does not expose any `Public` members, then no reference can be successful.</span></span> <span data-ttu-id="fb8c9-114">In beiden Fällen ist es ohne Bedeutung für das Element zu importieren.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-114">In either case it is meaningless to import the element.</span></span>

<span data-ttu-id="fb8c9-115">Sollten Sie bedenken, wenn Sie ein enthaltenden Element importieren und weisen Sie einen Importalias zu, klicken Sie dann Sie diesen Importalias nicht verwenden, um ein anderes Element zu importieren.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-115">Keep in mind that if you import a containing element and assign an import alias to it, then you cannot use that import alias to import another element.</span></span> <span data-ttu-id="fb8c9-116">Der folgende Code generiert einen Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-116">The following code generates a compiler error.</span></span>

```vb
Imports winfrm = System.Windows.Forms

' The following statement is INVALID  because it reuses an import alias.

Imports behave = winfrm.Design.Behavior`
```

<span data-ttu-id="fb8c9-117">**Fehler-ID:** BC40056</span><span class="sxs-lookup"><span data-stu-id="fb8c9-117">**Error ID:** BC40056</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="fb8c9-118">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fb8c9-118">To correct this error</span></span>

1. <span data-ttu-id="fb8c9-119">Stellen Sie sicher, dass das enthaltende Element aus Ihrem Projekt möglich ist.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-119">Verify that the containing element is accessible from your project.</span></span>

2. <span data-ttu-id="fb8c9-120">Stellen Sie sicher, dass die Spezifikation des enthaltenden Elements Importalias einen weiteren Importvorgang nicht enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-120">Verify that the specification of the containing element does not include any import alias from another import.</span></span>

3. <span data-ttu-id="fb8c9-121">Stellen Sie sicher, dass das enthaltende Element verfügbar, mindestens eine macht `Public` Member.</span><span class="sxs-lookup"><span data-stu-id="fb8c9-121">Verify that the containing element exposes at least one `Public` member.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb8c9-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb8c9-122">See also</span></span>

- [<span data-ttu-id="fb8c9-123">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="fb8c9-123">Imports Statement (.NET Namespace and Type)</span></span>](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="fb8c9-124">Namespace-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fb8c9-124">Namespace Statement</span></span>](../../../visual-basic/language-reference/statements/namespace-statement.md)
- [<span data-ttu-id="fb8c9-125">Public</span><span class="sxs-lookup"><span data-stu-id="fb8c9-125">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="fb8c9-126">Namespaces in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fb8c9-126">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [<span data-ttu-id="fb8c9-127">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="fb8c9-127">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
