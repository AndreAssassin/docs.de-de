---
title: So bestimmen, ob ein .NET Standard-Objekt serialisierbar ist.
description: Zeigt, wie Sie bestimmen, ob ein .NET Standard-Typ zur Laufzeit serialisiert werden kann.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196e99ab1f1a0baae53c6a1dc295b135e36fbfe0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018753"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="ad210-103">So bestimmen, ob ein .NET Standard-Objekt serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="ad210-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="ad210-104">.NET Standard ist eine Spezifikation, die definiert die Typen und Member, die in bestimmten .NET-Implementierungen vorhanden sein müssen, die diese Version des Standards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ad210-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="ad210-105">Allerdings werden .NET Standard nicht definiert, ob ein Typ serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ad210-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="ad210-106">In .NET Standard-Bibliothek definierten Typen sind nicht gekennzeichnet, mit der <xref:System.SerializableAttribute> Attribut.</span><span class="sxs-lookup"><span data-stu-id="ad210-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="ad210-107">Stattdessen können sich bestimmte Implementierungen von .NET, z.B. .NET Framework und .NET Core, um zu bestimmen, ob ein bestimmter Typ serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="ad210-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="ad210-108">Wenn Sie einer Bibliothek, das als Ziel .NET Standard entwickelt haben, kann Ihre Bibliothek von jeder .NET Implementierung verwendet werden, die .NET Standard unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ad210-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="ad210-109">Das heißt, Sie im Voraus wissen können, ob ein bestimmter Typ serialisierbar ist. Sie können nur bestimmen, ob es zur Laufzeit serialisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="ad210-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="ad210-110">Können Sie bestimmen, ob ein Objekt serialisierbar ist, zur Laufzeit durch Abrufen des Werts der der <xref:System.Type.IsSerializable> Eigenschaft eine <xref:System.Type> -Objekt, Typ des Objekts darstellt.</span><span class="sxs-lookup"><span data-stu-id="ad210-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="ad210-111">Im folgenden Beispiel wird eine Implementierung.</span><span class="sxs-lookup"><span data-stu-id="ad210-111">The following example provides one implementation.</span></span> <span data-ttu-id="ad210-112">Definiert eine `IsSerializable(Object)` -Erweiterungsmethode, der angibt, ob ein <xref:System.Object> Instanz serialisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ad210-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="ad210-113">Sie können dann ein Objekt übergeben, an die Methode, um festzustellen, ob es kann serialisiert und in der aktuellen.NET-Implementierung, wie im folgenden Beispiel gezeigt deserialisiert:</span><span class="sxs-lookup"><span data-stu-id="ad210-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="ad210-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad210-114">See also</span></span>

- [<span data-ttu-id="ad210-115">Binäre Serialisierung</span><span class="sxs-lookup"><span data-stu-id="ad210-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
