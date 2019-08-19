---
title: 'Vorgehensweise: Identifizieren eines Nullable-Typs – C#-Programmierhandbuch'
ms.custom: seodec18
description: Erfahren Sie, wie Sie ermitteln, ob ein Typ ein Nullable-Typ oder eine Instanz eines Nullable-Typs ist.
ms.date: 09/24/2018
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: 43a35874b8c9f52c4b98a93e1217994980e1b223
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567375"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="8325b-103">Vorgehensweise: Identifizieren eines Nullable-Typs (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8325b-103">How to: Identify a nullable type (C# Programming Guide)</span></span>

<span data-ttu-id="8325b-104">Das folgende Beispiel zeigt, wie Sie bestimmen können, ob eine <xref:System.Type?displayProperty=nameWithType>-Instanz einen geschlossenen generischen Nullable-Typ darstellt, d.h. den <xref:System.Nullable%601?displayProperty=nameWithType>-Typ mit einem angegebenen Typparameter `T`:</span><span class="sxs-lookup"><span data-stu-id="8325b-104">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a closed generic nullable type, that is, the <xref:System.Nullable%601?displayProperty=nameWithType> type with a specified type parameter `T`:</span></span>

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

<span data-ttu-id="8325b-105">Wie Sie im Beispiel sehen können, wird der Operator [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) verwendet, um ein <xref:System.Type?displayProperty=nameWithType>-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8325b-105">As the example shows, you use the [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) operator to create a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
<span data-ttu-id="8325b-106">Wenn Sie bestimmen möchten, ob eine Instanz einen Nullable-Typ aufweist, verwenden Sie nicht die <xref:System.Object.GetType%2A?displayProperty=nameWithType>-Methode, um eine <xref:System.Type>-Instanz abzurufen, die mit dem vorangehenden Code überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="8325b-106">If you want to determine whether an instance is of a nullable type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="8325b-107">Wenn Sie die <xref:System.Object.GetType%2A?displayProperty=nameWithType>-Methode in einer Instanz eines Nullable-Typs aufrufen, wird die Instanz in <xref:System.Object> [geschachtelt](using-nullable-types.md#boxing-and-unboxing).</span><span class="sxs-lookup"><span data-stu-id="8325b-107">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable type, the instance is [boxed](using-nullable-types.md#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="8325b-108">Da das Schachteln einer nicht-NULL-Instanz von einem Nullable-Typ dem Schachteln eines Werts des zugrunde liegenden Typs entspricht, gibt <xref:System.Object.GetType%2A> ein <xref:System.Type>-Objekt zurück, das den zugrunde liegenden Typ eines Nullable-Typs darstellt:</span><span class="sxs-lookup"><span data-stu-id="8325b-108">As boxing of a non-null instance of a nullable type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> object that represents the underlying type of a nullable type:</span></span>

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

<span data-ttu-id="8325b-109">Verwenden Sie nicht den Operator [is](../../language-reference/keywords/is.md), um zu ermitteln, ob eine Instanz einem Nullable-Typ entspricht.</span><span class="sxs-lookup"><span data-stu-id="8325b-109">Don't use the [is](../../language-reference/keywords/is.md) operator to determine whether an instance is of a nullable type.</span></span> <span data-ttu-id="8325b-110">Wie im folgenden Beispiel veranschaulicht wird, können Sie die Typen von Instanzen eines Nullable-Typs und den zugrunde liegenden Typ nicht mithilfe des `is`-Operators unterscheiden:</span><span class="sxs-lookup"><span data-stu-id="8325b-110">As the following example shows, you cannot distinguish types of instances of a nullable type and its underlying type with using the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

<span data-ttu-id="8325b-111">Sie können den Code verwenden, der im folgenden Beispiel dargestellt wird, um zu ermitteln, ob eine Instanz einen Nullable-Typ aufweist:</span><span class="sxs-lookup"><span data-stu-id="8325b-111">You can use the code presented in the following example to determine whether an instance is of a nullable type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]
  
## <a name="see-also"></a><span data-ttu-id="8325b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8325b-112">See also</span></span>

- [<span data-ttu-id="8325b-113">Nullable-Typen</span><span class="sxs-lookup"><span data-stu-id="8325b-113">Nullable types</span></span>](index.md)
- [<span data-ttu-id="8325b-114">Using nullable types (Verwenden von Nullable-Typen)</span><span class="sxs-lookup"><span data-stu-id="8325b-114">Using nullable types</span></span>](using-nullable-types.md)
- <xref:System.Nullable.GetUnderlyingType%2A>
