---
title: 'Vorgehensweise: Definieren von abstrakten Eigenschaften – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: ef19b80e7f4c32830aabfcf1ad595348c2107228
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599994"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a><span data-ttu-id="9b161-102">Vorgehensweise: Definieren von abstrakten Eigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9b161-102">How to: Define Abstract Properties (C# Programming Guide)</span></span>
<span data-ttu-id="9b161-103">Das folgende Beispiel veranschaulicht, wie Sie [abstrakte](../../../csharp/language-reference/keywords/abstract.md) Eigenschaften definieren:</span><span class="sxs-lookup"><span data-stu-id="9b161-103">The following example shows how to define [abstract](../../../csharp/language-reference/keywords/abstract.md) properties.</span></span> <span data-ttu-id="9b161-104">Eine abstrakte Eigenschaftendeklaration stellt keine Implementierung des Eigenschaftenaccessors bereit, sondern deklariert, dass die Klasse Eigenschaften unterstützt, die Accessorenimplementierung jedoch abgeleiteten Klassen überlässt.</span><span class="sxs-lookup"><span data-stu-id="9b161-104">An abstract property declaration does not provide an implementation of the property accessors -- it declares that the class supports properties, but leaves the accessor implementation to derived classes.</span></span> <span data-ttu-id="9b161-105">Das folgende Beispiel veranschaulicht das Implementieren von abstrakten Eigenschaften, die von einer Basisklasse geerbt wurden.</span><span class="sxs-lookup"><span data-stu-id="9b161-105">The following example demonstrates how to implement the abstract properties inherited from a base class.</span></span>  
  
 <span data-ttu-id="9b161-106">Dieses Beispiel besteht aus drei Dateien, von denen jede einzeln kompiliert wird, und auf die daraus entstehende Assembly von der nächsten Kompilierung verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9b161-106">This sample consists of three files, each of which is compiled individually and its resulting assembly is referenced by the next compilation:</span></span>  
  
- <span data-ttu-id="9b161-107">abstractshape.cs: die `Shape`-Klasse, die eine abstrakte `Area`-Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="9b161-107">abstractshape.cs: the `Shape` class that contains an abstract `Area` property.</span></span>  
  
- <span data-ttu-id="9b161-108">shapes.cs: die Unterklassen der `Shape`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="9b161-108">shapes.cs: The subclasses of the `Shape` class.</span></span>  
  
- <span data-ttu-id="9b161-109">shapetest.cs: ein Testprogramm zum Anzeigen der Bereiche einiger von `Shape` abgeleiteter Objekte.</span><span class="sxs-lookup"><span data-stu-id="9b161-109">shapetest.cs: A test program to display the areas of some `Shape`-derived objects.</span></span>  
  
 <span data-ttu-id="9b161-110">Verwenden Sie den folgenden Befehl, um das Beispiel zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="9b161-110">To compile the example, use the following command:</span></span>  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 <span data-ttu-id="9b161-111">Dadurch wird die ausführbare Datei „shapetest.exe“ erstellt.</span><span class="sxs-lookup"><span data-stu-id="9b161-111">This will create the executable file shapetest.exe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b161-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b161-112">Example</span></span>  
 <span data-ttu-id="9b161-113">Diese Datei deklariert die `Shape`-Klasse, die die `Area`-Eigenschaft des Typs `double` enthält.</span><span class="sxs-lookup"><span data-stu-id="9b161-113">This file declares the `Shape` class that contains the `Area` property of the type `double`.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
- <span data-ttu-id="9b161-114">Modifizierer der Eigenschaft sind in der Deklaration der Eigenschaft selbst platziert.</span><span class="sxs-lookup"><span data-stu-id="9b161-114">Modifiers on the property are placed on the property declaration itself.</span></span> <span data-ttu-id="9b161-115">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="9b161-115">For example:</span></span>  
  
    ```csharp  
    public abstract double Area  
    ```  
  
- <span data-ttu-id="9b161-116">Wenn Sie eine abstrakte Eigenschaft deklarieren (z.B. `Area` in diesem Beispiel), geben Sie lediglich an, welche Eigenschaftenaccessoren verfügbar sind, implementieren diese jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="9b161-116">When declaring an abstract property (such as `Area` in this example), you simply indicate what property accessors are available, but do not implement them.</span></span> <span data-ttu-id="9b161-117">In diesem Beispiel ist nur ein [get](../../../csharp/language-reference/keywords/get.md)-Accessor verfügbar, die Eigenschaft ist also schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="9b161-117">In this example, only a [get](../../../csharp/language-reference/keywords/get.md) accessor is available, so the property is read-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b161-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b161-118">Example</span></span>  
 <span data-ttu-id="9b161-119">Der folgende Code zeigt drei Unterklassen von `Shape` und wie sie die `Area`-Eigenschaft überschreiben, um ihre eigene Implementierung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9b161-119">The following code shows three subclasses of `Shape` and how they override the `Area` property to provide their own implementation.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="9b161-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b161-120">Example</span></span>  
 <span data-ttu-id="9b161-121">Der folgende Code zeigt ein Testprogramm, das eine Reihe abgeleiteter `Shape`-Objekte erstellt und deren Bereiche ausdruckt.</span><span class="sxs-lookup"><span data-stu-id="9b161-121">The following code shows a test program that creates a number of `Shape`-derived objects and prints out their areas.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="9b161-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b161-122">See also</span></span>

- [<span data-ttu-id="9b161-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9b161-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="9b161-124">Klassen und Strukturen</span><span class="sxs-lookup"><span data-stu-id="9b161-124">Classes and Structs</span></span>](../../../csharp/programming-guide/classes-and-structs/index.md)
- [<span data-ttu-id="9b161-125">Abstrakte und versiegelte Klassen und Klassenmember</span><span class="sxs-lookup"><span data-stu-id="9b161-125">Abstract and Sealed Classes and Class Members</span></span>](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="9b161-126">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9b161-126">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="9b161-127">Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="9b161-127">How to: Create and Use Assemblies Using the Command Line</span></span>](../concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
