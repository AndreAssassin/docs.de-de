---
title: <typename> erweitert den Zugriff der Basis-<type> außerhalb der Assembly und kann daher nicht von <basetypename> '<type>' erben.
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: dc979a66c73fdf15a4349a003680156e0ce27ed3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61764360"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="30d7e-102">'\<Typname >' kann nicht von erben \<Typ > '\<Basistypname >' erweitert den Zugriff der Basis \<Typ > außerhalb der Assembly</span><span class="sxs-lookup"><span data-stu-id="30d7e-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="30d7e-103">Eine Klasse oder Schnittstelle erbt von einer Basisklasse oder Schnittstelle weist jedoch eine weniger restriktive Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="30d7e-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="30d7e-104">Z. B. eine `Public` Schnittstelle erbt von einer `Friend` -Schnittstelle, oder ein `Protected` Klasse erbt von einer `Private` Klasse.</span><span class="sxs-lookup"><span data-stu-id="30d7e-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="30d7e-105">Dies stellt die Basisklasse oder Schnittstelle, um nach den gewünschten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="30d7e-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="30d7e-106">**Fehler-ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="30d7e-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="30d7e-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="30d7e-107">To correct this error</span></span>  
  
- <span data-ttu-id="30d7e-108">Ändern Sie die Zugriffsebene der abgeleiteten Klasse oder Schnittstelle, die mindestens so restriktiv wie der Basisklasse oder Schnittstelle sein.</span><span class="sxs-lookup"><span data-stu-id="30d7e-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="30d7e-109">- oder - </span><span class="sxs-lookup"><span data-stu-id="30d7e-109">-or-</span></span>  
  
- <span data-ttu-id="30d7e-110">Wenn Sie die weniger restriktive Zugriffsebene benötigen, entfernen Sie die `Inherits` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="30d7e-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="30d7e-111">Sie können nicht von einem eingeschränkteren Basisklasse oder Schnittstelle erben.</span><span class="sxs-lookup"><span data-stu-id="30d7e-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d7e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30d7e-112">See also</span></span>

- [<span data-ttu-id="30d7e-113">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="30d7e-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="30d7e-114">Interface-Anweisung</span><span class="sxs-lookup"><span data-stu-id="30d7e-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="30d7e-115">Inherits-Anweisung</span><span class="sxs-lookup"><span data-stu-id="30d7e-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="30d7e-116">Zugriffsebenen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="30d7e-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
