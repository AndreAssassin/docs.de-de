---
title: "\"Is\" erfordert Operanden, die Verweistypen haben. Dieser Operand hat jedoch den Werttyp \"<typename>\"."
ms.date: 07/20/2015
f1_keywords:
- bc30020
- vbc30020
helpviewer_keywords:
- BC30020
ms.assetid: 228afebd-1203-4bd3-8d7a-c5c56f3cedc4
ms.openlocfilehash: b828de196a12128a9f34ee1f9ff1e57fee22c687
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58843850"
---
# <a name="is-requires-operands-that-have-reference-types-but-this-operand-has-the-value-type-typename"></a><span data-ttu-id="93141-102">'Is"erfordert Operanden mit Referenztypen, aber dieser Operand hat den Werttyp"\<Typname >'</span><span class="sxs-lookup"><span data-stu-id="93141-102">'Is' requires operands that have reference types, but this operand has the value type '\<typename>'</span></span>
<span data-ttu-id="93141-103">Die `Is` Vergleichsoperator bestimmt, ob zwei Objektvariablen auf dieselbe Instanz verweisen.</span><span class="sxs-lookup"><span data-stu-id="93141-103">The `Is` comparison operator determines whether two object variables refer to the same instance.</span></span> <span data-ttu-id="93141-104">Dieser Vergleich ist für Werttypen nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="93141-104">This comparison is not defined for value types.</span></span>  
  
 <span data-ttu-id="93141-105">**Fehler-ID:** BC30020</span><span class="sxs-lookup"><span data-stu-id="93141-105">**Error ID:** BC30020</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="93141-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="93141-106">To correct this error</span></span>  
  
-   <span data-ttu-id="93141-107">Verwenden Sie den entsprechenden arithmetischen Vergleichsoperator oder `Like` Operator, um zwei Werttypen vergleichen.</span><span class="sxs-lookup"><span data-stu-id="93141-107">Use the appropriate arithmetic comparison operator or the `Like` operator to compare two value types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93141-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93141-108">See also</span></span>

- [<span data-ttu-id="93141-109">Is-Operator</span><span class="sxs-lookup"><span data-stu-id="93141-109">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="93141-110">Like-Operator</span><span class="sxs-lookup"><span data-stu-id="93141-110">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="93141-111">Vergleichsoperatoren</span><span class="sxs-lookup"><span data-stu-id="93141-111">Comparison Operators</span></span>](../../../visual-basic/language-reference/operators/comparison-operators.md)
