---
title: Assertionen
description: Erfahren Sie, wie Sie mit der Ausdruck "assert" als eine Debugfunktion zum Testen von Ausdrücken in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: c2d97386e87e9b915da490a78fff9aedb9def616
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703217"
---
# <a name="assertions"></a><span data-ttu-id="fa9fa-103">Assertionen</span><span class="sxs-lookup"><span data-stu-id="fa9fa-103">Assertions</span></span>

<span data-ttu-id="fa9fa-104">Die `assert` Ausdruck ist eine Debugfunktion, die Sie verwenden können, um einen Ausdruck zu testen.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="fa9fa-105">Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa9fa-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa9fa-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="fa9fa-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa9fa-107">Remarks</span></span>

<span data-ttu-id="fa9fa-108">Die `assert` Ausdruck weist Typ `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="fa9fa-109">In der vorherigen Syntax *Bedingung* stellt einen booleschen Ausdruck, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="fa9fa-110">Wenn der Ausdruck ergibt `true`, Ausführung wird fortgeführt, nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="fa9fa-111">Ergibt die Auswertung `false`, wird ein Dialogfeld System Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="fa9fa-112">Das Dialogfeld "Fehler" hat einer Beschriftung, die die Zeichenfolge enthält **Assertionsfehler**.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="fa9fa-113">Das Dialogfeld enthält eine stapelüberwachung, die angibt, in der Assertionsfehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="fa9fa-114">Assertionsüberprüfung ist aktiviert, nur beim Kompilieren im Debugmodus befindet. d.h., wenn die Konstante `DEBUG` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="fa9fa-115">Im Projektsystem, standardmäßig die `DEBUG` Konstante wird definiert, in der Debug-Konfiguration jedoch nicht in der Releasekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="fa9fa-116">Der Assertionsfehler kann nicht abgefangen werden, mithilfe von F# Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="fa9fa-117">Die `assert` Funktion löst in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="fa9fa-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fa9fa-118">Example</span></span>

<span data-ttu-id="fa9fa-119">Das folgende Codebeispiel veranschaulicht die Verwendung von der `assert` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="fa9fa-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="fa9fa-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa9fa-120">See also</span></span>

- [<span data-ttu-id="fa9fa-121">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="fa9fa-121">F# Language Reference</span></span>](index.md)