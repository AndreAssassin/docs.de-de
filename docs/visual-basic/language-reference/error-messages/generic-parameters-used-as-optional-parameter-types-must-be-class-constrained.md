---
title: Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.
ms.date: 07/20/2015
f1_keywords:
- vbc32124
- bc32124
helpviewer_keywords:
- BC32124
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
ms.openlocfilehash: 9b0293472f5eda74c2bf8fb215e15ae5cf8d8b98
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58813898"
---
# <a name="generic-parameters-used-as-optional-parameter-types-must-be-class-constrained"></a><span data-ttu-id="2f6c4-102">Generische Parameter, die als optionale Parametertypen verwendet werden, müssen eine Klassenbeschränkung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2f6c4-102">Generic parameters used as optional parameter types must be class constrained</span></span>
<span data-ttu-id="2f6c4-103">Eine Prozedur ist mit einem optionalen Parameter deklariert, die einen Typparameter verwendet, der nicht zu einem Referenztyp eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="2f6c4-103">A procedure is declared with an optional parameter that uses a type parameter that is not constrained to be a reference type.</span></span>  
  
 <span data-ttu-id="2f6c4-104">Sie müssen immer einen Standardwert für jeden optionalen Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="2f6c4-104">You must always supply a default value for each optional parameter.</span></span> <span data-ttu-id="2f6c4-105">Wenn der Parameter eines Verweistyps ist, muss der optionale Wert `Nothing`, dies ist ein gültiger Wert für jeden Referenztyp.</span><span class="sxs-lookup"><span data-stu-id="2f6c4-105">If the parameter is of a reference type, the optional value must be `Nothing`, which is a valid value for any reference type.</span></span> <span data-ttu-id="2f6c4-106">Wenn der Parameter einen Werttyp ist, muss dieses Typs jedoch ein elementarer Datentyp, der von Visual Basic vordefiniert sein.</span><span class="sxs-lookup"><span data-stu-id="2f6c4-106">However, if the parameter is of a value type, that type must be an elementary data type predefined by Visual Basic.</span></span> <span data-ttu-id="2f6c4-107">Dies ist da ein zusammengesetzten Werttyp, z. B. eine benutzerdefinierte Struktur, die keinen gültigen Standardwert verfügt.</span><span class="sxs-lookup"><span data-stu-id="2f6c4-107">This is because a composite value type, such as a user-defined structure, has no valid default value.</span></span>  
  
 <span data-ttu-id="2f6c4-108">Wenn Sie einen Typparameter für einen optionalen Parameter verwenden, müssen Sie sicherstellen, dass es ein Verweistyp, vermeiden Sie die Möglichkeit, einen Werttyp besitzt keinen gültigen Standardwert handelt.</span><span class="sxs-lookup"><span data-stu-id="2f6c4-108">When you use a type parameter for an optional parameter, you must guarantee that it is of a reference type to avoid the possibility of a value type with no valid default value.</span></span> <span data-ttu-id="2f6c4-109">Dies bedeutet, Sie müssen dem Typparameter einschränken, entweder mit der `Class` Schlüsselwort oder mit dem Namen einer bestimmten Klasse.</span><span class="sxs-lookup"><span data-stu-id="2f6c4-109">This means you must constrain the type parameter either with the `Class` keyword or with the name of a specific class.</span></span>  
  
 <span data-ttu-id="2f6c4-110">**Fehler-ID:** BC32124</span><span class="sxs-lookup"><span data-stu-id="2f6c4-110">**Error ID:** BC32124</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2f6c4-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="2f6c4-111">To correct this error</span></span>  
  
-   <span data-ttu-id="2f6c4-112">Einschränken Sie den Typparameter nur den Verweistyp akzeptiert, oder verwenden Sie es nicht für den optionalen Parameter.</span><span class="sxs-lookup"><span data-stu-id="2f6c4-112">Constrain the type parameter to accept only a reference type, or do not use it for the optional parameter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f6c4-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f6c4-113">See also</span></span>

- [<span data-ttu-id="2f6c4-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2f6c4-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="2f6c4-115">Typliste</span><span class="sxs-lookup"><span data-stu-id="2f6c4-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
- [<span data-ttu-id="2f6c4-116">Class-Anweisung</span><span class="sxs-lookup"><span data-stu-id="2f6c4-116">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="2f6c4-117">Optionale Parameter</span><span class="sxs-lookup"><span data-stu-id="2f6c4-117">Optional Parameters</span></span>](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [<span data-ttu-id="2f6c4-118">Strukturen</span><span class="sxs-lookup"><span data-stu-id="2f6c4-118">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="2f6c4-119">Nothing</span><span class="sxs-lookup"><span data-stu-id="2f6c4-119">Nothing</span></span>](../../../visual-basic/language-reference/nothing.md)
