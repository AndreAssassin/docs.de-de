---
title: '##Const-Anweisung (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.#Const
- '#vb.Const'
- '#Const'
helpviewer_keywords:
- '#Const directive'
- conditional compilation [Visual Basic], directives
- Const directive (#Const)
- Visual Basic compiler, compiler directives
- constants [Visual Basic], Const directive
- constants [Visual Basic], declaring
- Const statement [Visual Basic], directive (#Const)
- 'declaring constants [Visual Basic], #const directive'
ms.assetid: 707669e5-23f9-4f17-8622-a0d534429386
ms.openlocfilehash: 5458bbebc6064eb6273b8deb5447b8941e1d233f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842264"
---
# <a name="const-directive"></a><span data-ttu-id="d3266-102">#Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d3266-102">#Const Directive</span></span>
<span data-ttu-id="d3266-103">Definiert Konstanten für bedingte Kompilierung für Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="d3266-103">Defines conditional compiler constants for Visual Basic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3266-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3266-104">Syntax</span></span>  
  
```  
#Const constname = expression  
```  
  
## <a name="parts"></a><span data-ttu-id="d3266-105">Teile</span><span class="sxs-lookup"><span data-stu-id="d3266-105">Parts</span></span>  
 `constname`  
 <span data-ttu-id="d3266-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d3266-106">Required.</span></span> <span data-ttu-id="d3266-107">Die Namen der Konstanten definiert wird.</span><span class="sxs-lookup"><span data-stu-id="d3266-107">Name of the constant being defined.</span></span>  
  
 `expression`  
 <span data-ttu-id="d3266-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d3266-108">Required.</span></span> <span data-ttu-id="d3266-109">Literal, andere Konstanten für bedingte Kompilierung oder eine beliebige Kombination, die alle arithmetische oder logische Operatoren außer enthält `Is`.</span><span class="sxs-lookup"><span data-stu-id="d3266-109">Literal, other conditional compiler constant, or any combination that includes any or all arithmetic or logical operators except `Is`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d3266-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d3266-110">Remarks</span></span>  
 <span data-ttu-id="d3266-111">Bedingte Compilerkonstanten sind immer privat für die Datei, die in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d3266-111">Conditional compiler constants are always private to the file in which they appear.</span></span> <span data-ttu-id="d3266-112">Kann nicht erstellt werden öffentliche Compilerkonstanten mithilfe der `#Const` -Direktive; Sie können diese erstellen, nur in der Benutzeroberfläche oder mit der `/define` -Compileroption.</span><span class="sxs-lookup"><span data-stu-id="d3266-112">You cannot create public compiler constants using the `#Const` directive; you can create them only in the user interface or with the `/define` compiler option.</span></span>  
  
 <span data-ttu-id="d3266-113">Sie können nur Bedingte Compilerkonstanten und Literale in `expression`.</span><span class="sxs-lookup"><span data-stu-id="d3266-113">You can use only conditional compiler constants and literals in `expression`.</span></span> <span data-ttu-id="d3266-114">Verwenden eine standard-Konstante definiert `Const` verursacht einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="d3266-114">Using a standard constant defined with `Const` causes an error.</span></span> <span data-ttu-id="d3266-115">Im Gegensatz dazu können Sie mit definierte Konstanten der `#Const` Schlüsselwort nur für die bedingte Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="d3266-115">Conversely, you can use constants defined with the `#Const` keyword only for conditional compilation.</span></span> <span data-ttu-id="d3266-116">Konstanten können auch nicht definiert sein, bei dem sie einen Wert von aufweisen `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="d3266-116">Constants can also be undefined, in which case they have a value of `Nothing`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3266-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3266-117">Example</span></span>  
 <span data-ttu-id="d3266-118">Dieses Beispiel verwendet die `#Const`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d3266-118">This example uses the `#Const` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="d3266-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3266-119">See also</span></span>

- [<span data-ttu-id="d3266-120">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3266-120">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
- [<span data-ttu-id="d3266-121">#If...Then...#Else-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="d3266-121">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="d3266-122">Const-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d3266-122">Const Statement</span></span>](../../../visual-basic/language-reference/statements/const-statement.md)
- [<span data-ttu-id="d3266-123">Bedingte Kompilierung</span><span class="sxs-lookup"><span data-stu-id="d3266-123">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [<span data-ttu-id="d3266-124">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d3266-124">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
