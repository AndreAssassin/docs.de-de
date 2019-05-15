---
title: Checked und Unchecked – C#-Referenz
ms.custom: seodec18
ms.date: 05/15/2018
helpviewer_keywords:
- operators [C#], checked and unchecked
- exceptions [C#], overflow checking
- checked statement [C#]
- overflow checking [C#]
- unchecked statement [C#]
- statements [C#], checked and unchecked
ms.assetid: a84bc877-2c7f-4396-8735-1ce97c42f35e
ms.openlocfilehash: 3378cffc1dcee7bb12705704e66b7fdd287105fb
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592992"
---
# <a name="checked-and-unchecked-c-reference"></a><span data-ttu-id="5694e-102">Checked und Unchecked (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="5694e-102">Checked and Unchecked (C# Reference)</span></span>
<span data-ttu-id="5694e-103">C#-Anweisungen könnten entweder in einem geprüften oder nicht geprüften Kontext (checked oder unchecked) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5694e-103">C# statements can execute in either checked or unchecked context.</span></span> <span data-ttu-id="5694e-104">In einem überprüften Kontext löst der arithmetische Überlauf eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="5694e-104">In a checked context, arithmetic overflow raises an exception.</span></span> <span data-ttu-id="5694e-105">In einem nicht aktivierten Kontext wird der arithmetische Überlauf ignoriert und das Ergebnis gekürzt, indem alle höherwertigen Bits verworfen werden, die nicht in den Zieltyp passen.</span><span class="sxs-lookup"><span data-stu-id="5694e-105">In an unchecked context, arithmetic overflow is ignored and the result is truncated by discarding any high-order bits that don't fit in the destination type.</span></span>  
  
- <span data-ttu-id="5694e-106">[checked](checked.md) Gibt einen geprüften Kontext an.</span><span class="sxs-lookup"><span data-stu-id="5694e-106">[checked](checked.md) Specify checked context.</span></span>  
  
- <span data-ttu-id="5694e-107">[unchecked](unchecked.md) Gibt einen ungeprüften Kontext an.</span><span class="sxs-lookup"><span data-stu-id="5694e-107">[unchecked](unchecked.md) Specify unchecked context.</span></span>  
  
 <span data-ttu-id="5694e-108">Die folgenden Vorgänge sind von der Überlaufüberprüfung betroffen:</span><span class="sxs-lookup"><span data-stu-id="5694e-108">The following operations are affected by the overflow checking:</span></span>  
  
- <span data-ttu-id="5694e-109">Ausdrücke, die die folgenden vordefinierten Operatoren für ganzzahlige Typen verwenden:</span><span class="sxs-lookup"><span data-stu-id="5694e-109">Expressions using the following predefined operators on integral types:</span></span>  
  
     <span data-ttu-id="5694e-110">`++`, `--`, unäres `-`, `+`, `-`, `*`, `/`</span><span class="sxs-lookup"><span data-stu-id="5694e-110">`++`, `--`, unary `-`, `+`, `-`, `*`, `/`</span></span>  
  
- <span data-ttu-id="5694e-111">Explizite numerische Konvertierungen zwischen ganzzahligen Typen oder von `float` oder `double` in einen integralen Typ.</span><span class="sxs-lookup"><span data-stu-id="5694e-111">Explicit numeric conversions between integral types, or from `float` or `double` to an integral type.</span></span>  
  
 <span data-ttu-id="5694e-112">Wenn weder `checked` noch `unchecked` festgelegt ist, wird der Standardkontext für nicht konstante Ausdrücke (Ausdrücke, die zur Laufzeit ausgewertet werden) vom Wert der Compileroption [-checked](../compiler-options/checked-compiler-option.md) definiert.</span><span class="sxs-lookup"><span data-stu-id="5694e-112">If neither `checked` nor `unchecked` is specified, the default context for non-constant expressions (expressions that are evaluated at run time) is defined by the value of the [-checked](../compiler-options/checked-compiler-option.md) compiler option.</span></span> <span data-ttu-id="5694e-113">Standardmäßig ist der Wert dieser Option nicht festgelegt, und arithmetische Operationen werden in einem nicht geprüften Kontext ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5694e-113">By default the value of that option is unset and arithmetic operations are executed in an unchecked context.</span></span>
 
 <span data-ttu-id="5694e-114">Für konstante Ausdrücke (Ausdrücke, die zur Kompilierzeit vollständig ausgewertet werden können) ist der Standardkontext immer geprüft.</span><span class="sxs-lookup"><span data-stu-id="5694e-114">For constant expressions (expressions that can be fully evaluated at compile time), the default context is always checked.</span></span> <span data-ttu-id="5694e-115">Überläufe, die während der Auswertung des Ausdrucks zur Kompilierzeit auftreten, führen zu Kompilierzeitfehlern, wenn der konstante Ausdruck nicht explizit in einen ungeprüften Kontext gebracht wird.</span><span class="sxs-lookup"><span data-stu-id="5694e-115">Unless a constant expression is explicitly placed in an unchecked context, overflows that occur during the compile-time evaluation of the expression cause compile-time errors.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5694e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5694e-116">See also</span></span>

- [<span data-ttu-id="5694e-117">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="5694e-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5694e-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="5694e-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5694e-119">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5694e-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="5694e-120">Anweisungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="5694e-120">Statement Keywords</span></span>](statement-keywords.md)
