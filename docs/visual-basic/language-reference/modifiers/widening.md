---
title: Widening (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.widening
helpviewer_keywords:
- conversions [Visual Basic], type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- Widening keyword [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
ms.openlocfilehash: d7d43d4f5f931881d5c8b663c719fe7f92559799
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778663"
---
# <a name="widening-visual-basic"></a><span data-ttu-id="02d5c-102">Widening (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02d5c-102">Widening (Visual Basic)</span></span>
<span data-ttu-id="02d5c-103">Gibt an, dass ein Konvertierungsoperator (`CType`) konvertiert Sie eine Klasse oder Struktur in einen Typ, der alle möglichen Werte der ursprünglichen Klasse oder Struktur enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="02d5c-103">Indicates that a conversion operator (`CType`) converts a class or structure to a type that can hold all possible values of the original class or structure.</span></span>  
  
## <a name="converting-with-the-widening-keyword"></a><span data-ttu-id="02d5c-104">Konvertierung mit dem Widening-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="02d5c-104">Converting with the Widening Keyword</span></span>  
 <span data-ttu-id="02d5c-105">Konvertierungsprozedur muss angegeben werden `Public Shared` zusätzlich zu `Widening`.</span><span class="sxs-lookup"><span data-stu-id="02d5c-105">The conversion procedure must specify `Public Shared` in addition to `Widening`.</span></span>  
  
 <span data-ttu-id="02d5c-106">Erweiternde Konvertierungen immer erfolgreich, zur Laufzeit und verursachen keine Daten verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="02d5c-106">Widening conversions always succeed at run time and never incur data loss.</span></span> <span data-ttu-id="02d5c-107">Beispiele sind `Single` zu `Double`, `Char` zu `String`, und einen abgeleiteten Typ in den Basistyp.</span><span class="sxs-lookup"><span data-stu-id="02d5c-107">Examples are `Single` to `Double`, `Char` to `String`, and a derived type to its base type.</span></span> <span data-ttu-id="02d5c-108">Die letzte Konvertierung ist erweiternde, weil der abgeleitete Typ alle Member des Basistyps enthält und daher eine Instanz des Basistyps.</span><span class="sxs-lookup"><span data-stu-id="02d5c-108">This last conversion is widening because the derived type contains all the members of the base type and thus is an instance of the base type.</span></span>  
  
 <span data-ttu-id="02d5c-109">Der konsumierenden Code keine Verwendung `CType` für erweiternde Konvertierungen, auch wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="02d5c-109">The consuming code does not have to use `CType` for widening conversions, even if `Option Strict` is `On`.</span></span>  
  
 <span data-ttu-id="02d5c-110">Die `Widening` -Schlüsselwort kann in diesem Kontext verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="02d5c-110">The `Widening` keyword can be used in this context:</span></span>  
  
 [<span data-ttu-id="02d5c-111">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="02d5c-111">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 <span data-ttu-id="02d5c-112">Definitionen von erweiternde und eingrenzende Konvertierungsoperatoren, z. B. finden Sie unter [Vorgehensweise: Definieren eines Konvertierungsoperators](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="02d5c-112">For example definitions of widening and narrowing conversion operators, see [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02d5c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02d5c-113">See also</span></span>

- [<span data-ttu-id="02d5c-114">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="02d5c-114">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="02d5c-115">Narrowing</span><span class="sxs-lookup"><span data-stu-id="02d5c-115">Narrowing</span></span>](../../../visual-basic/language-reference/modifiers/narrowing.md)
- [<span data-ttu-id="02d5c-116">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="02d5c-116">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="02d5c-117">Vorgehensweise: Definieren eines Operators</span><span class="sxs-lookup"><span data-stu-id="02d5c-117">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)
- [<span data-ttu-id="02d5c-118">CType-Funktion</span><span class="sxs-lookup"><span data-stu-id="02d5c-118">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
- [<span data-ttu-id="02d5c-119">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="02d5c-119">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="02d5c-120">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="02d5c-120">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
