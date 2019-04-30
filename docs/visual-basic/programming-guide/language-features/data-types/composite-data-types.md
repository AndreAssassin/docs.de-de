---
title: Zusammengesetzte Datentypen (Visual Basic)
ms.date: 04/25/2017
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- classes [Visual Basic], composite types
- types [Visual Basic], composite
ms.assetid: 62970f2e-52c0-4369-8963-613820f1f434
ms.openlocfilehash: ea719b60a6bcd40494666d4923fad296a8ddae70
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61907386"
---
# <a name="composite-data-types-visual-basic"></a><span data-ttu-id="be7f2-102">Zusammengesetzte Datentypen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be7f2-102">Composite Data Types (Visual Basic)</span></span>
<span data-ttu-id="be7f2-103">Zusätzlich zu den bereitgestellten Typen Visual Basic elementarer Datentyp können Sie auch Elemente verschiedener Inhaltstypen erstellen zusammenstellen *zusammengesetzte Datentypen* wie z. B. Klassen, Strukturen und Arrays.</span><span class="sxs-lookup"><span data-stu-id="be7f2-103">In addition to the elementary data types Visual Basic supplies, you can also assemble items of different types to create *composite data types* such as structures, arrays, and classes.</span></span> <span data-ttu-id="be7f2-104">Sie können zusammengesetzte Datentypen von elementare Typen und von anderen zusammengesetzten Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="be7f2-104">You can build composite data types from elementary types and from other composite types.</span></span> <span data-ttu-id="be7f2-105">Beispielsweise können Sie ein Array von Strukturelementen oder eine Struktur mit Array-Elemente definieren.</span><span class="sxs-lookup"><span data-stu-id="be7f2-105">For example, you can define an array of structure elements, or a structure with array members.</span></span>  
  
## <a name="data-types"></a><span data-ttu-id="be7f2-106">Datentypen</span><span class="sxs-lookup"><span data-stu-id="be7f2-106">Data Types</span></span>  
 <span data-ttu-id="be7f2-107">Ein zusammengesetzter Typ unterscheidet sich von dem Datentyp aller zugehörigen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="be7f2-107">A composite type is different from the data type of any of its components.</span></span> <span data-ttu-id="be7f2-108">Z. B. ein Array von `Integer` Elemente weist nicht den `Integer` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="be7f2-108">For example, an array of `Integer` elements is not of the `Integer` data type.</span></span>  
  
 <span data-ttu-id="be7f2-109">Datentyp eines Arrays wird normalerweise dargestellt mithilfe der Elementtyp, Klammern und Kommas nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="be7f2-109">An array data type is normally represented using the element type, parentheses, and commas as necessary.</span></span> <span data-ttu-id="be7f2-110">Z. B. ein eindimensionales Array von `String` als Elemente dargestellt `String()`, und ein zweidimensionales Array von `Boolean` als Elemente dargestellt `Boolean(,)`.</span><span class="sxs-lookup"><span data-stu-id="be7f2-110">For example, a one-dimensional array of `String` elements is represented as `String()`, and a two-dimensional array of `Boolean` elements is represented as `Boolean(,)`.</span></span>  
  
## <a name="structure-types"></a><span data-ttu-id="be7f2-111">Strukturtypen</span><span class="sxs-lookup"><span data-stu-id="be7f2-111">Structure Types</span></span>  
 <span data-ttu-id="be7f2-112">Es gibt keinen universellen Datentyp werden alle vorhandenen Strukturen aus.</span><span class="sxs-lookup"><span data-stu-id="be7f2-112">There is no single data type comprising all structures.</span></span> <span data-ttu-id="be7f2-113">Jede Definition einer Struktur stellt stattdessen einen eindeutigen Datentyp dar, auch wenn zwei Strukturen identischer Elemente in der gleichen Reihenfolge definieren.</span><span class="sxs-lookup"><span data-stu-id="be7f2-113">Instead, each definition of a structure represents a unique data type, even if two structures define identical elements in the same order.</span></span> <span data-ttu-id="be7f2-114">Allerdings berücksichtigt Visual Basic, wenn Sie mindestens zwei Instanzen derselben Struktur erstellen, zu dem gleichen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="be7f2-114">However, if you create two or more instances of the same structure, Visual Basic considers them to be of the same data type.</span></span>  
  
## <a name="tuples"></a><span data-ttu-id="be7f2-115">Tupel</span><span class="sxs-lookup"><span data-stu-id="be7f2-115">Tuples</span></span>

<span data-ttu-id="be7f2-116">Ein Tupel ist eine einfache Struktur, die zwei oder mehr Felder enthält, deren Typen vordefiniert sind.</span><span class="sxs-lookup"><span data-stu-id="be7f2-116">A tuple is a lightweight structure that contains two or more fields whose types are predefined.</span></span> <span data-ttu-id="be7f2-117">Tupel werden ab Visual Basic 2017 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="be7f2-117">Tuples are supported starting with Visual Basic 2017.</span></span> <span data-ttu-id="be7f2-118">Tupel werden am häufigsten verwendet, um mehrere Werte aus einem Methodenaufruf zurückgeben, ohne dass Argumente als Verweis übergeben, oder Packen die zurückgegebenen Felder in einer mehr Heavyweight-Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="be7f2-118">Tuples are most commonly used to return multiple values from a single method call without having to pass arguments by reference or packaging the returned fields in a more heavy-weight class or structure.</span></span> <span data-ttu-id="be7f2-119">Finden Sie unter den [Tupel](tuples.md) Themas Weitere Informationen zu Tupeln.</span><span class="sxs-lookup"><span data-stu-id="be7f2-119">See the [Tuples](tuples.md) topic for more information on tuples.</span></span>

## <a name="array-types"></a><span data-ttu-id="be7f2-120">Arraytypen</span><span class="sxs-lookup"><span data-stu-id="be7f2-120">Array Types</span></span>  
 <span data-ttu-id="be7f2-121">Es gibt keinen universellen Datentyp, der alle Arrays aus.</span><span class="sxs-lookup"><span data-stu-id="be7f2-121">There is no single data type comprising all arrays.</span></span> <span data-ttu-id="be7f2-122">Der Datentyp, der eine bestimmte Instanz eines Arrays wird durch Folgendes bestimmt:</span><span class="sxs-lookup"><span data-stu-id="be7f2-122">The data type of a particular instance of an array is determined by the following:</span></span>  
  
- <span data-ttu-id="be7f2-123">Die Tatsache, dass ein array</span><span class="sxs-lookup"><span data-stu-id="be7f2-123">The fact of being an array</span></span>  
  
- <span data-ttu-id="be7f2-124">Der Rang (Anzahl der Dimensionen) des Arrays</span><span class="sxs-lookup"><span data-stu-id="be7f2-124">The rank (number of dimensions) of the array</span></span>  
  
- <span data-ttu-id="be7f2-125">Der Elementtyp des Arrays</span><span class="sxs-lookup"><span data-stu-id="be7f2-125">The element type of the array</span></span>  
  
 <span data-ttu-id="be7f2-126">Die Länge einer bestimmten Dimension ist vor allem nicht Teil der Datentyp der Instanz.</span><span class="sxs-lookup"><span data-stu-id="be7f2-126">In particular, the length of a given dimension is not part of the instance's data type.</span></span> <span data-ttu-id="be7f2-127">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="be7f2-127">The following example illustrates this.</span></span>  
  
```  
Dim arrayA( ) As Byte = New Byte(12) {}  
Dim arrayB( ) As Byte = New Byte(100) {}  
Dim arrayC( ) As Short = New Short(100) {}  
Dim arrayD( , ) As Short  
Dim arrayE( , ) As Short = New Short(4, 10) {}  
```  
  
 <span data-ttu-id="be7f2-128">Im vorherigen Beispiel Arrayvariablen `arrayA` und `arrayB` gelten die gleichen Datentyp sein – `Byte()` –, obwohl sie mit unterschiedlicher Länge initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="be7f2-128">In the preceding example, array variables `arrayA` and `arrayB` are considered to be of the same data type — `Byte()` — even though they are initialized to different lengths.</span></span> <span data-ttu-id="be7f2-129">Variablen `arrayB` und `arrayC` sind nicht vom gleichen Typ, da sich die Elementtypen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="be7f2-129">Variables `arrayB` and `arrayC` are not of the same type because their element types are different.</span></span> <span data-ttu-id="be7f2-130">Variablen `arrayC` und `arrayD` sind Sie nicht den gleichen Typ aufweisen, da ihre Ränge unterschiedlich sind.</span><span class="sxs-lookup"><span data-stu-id="be7f2-130">Variables `arrayC` and `arrayD` are not of the same type because their ranks are different.</span></span> <span data-ttu-id="be7f2-131">Variablen `arrayD` und `arrayE` vom gleichen Typ – `Short(,)` , da ihr Rang und Elementtypen identisch, obwohl sind `arrayD` wurde noch nicht initialisiert.</span><span class="sxs-lookup"><span data-stu-id="be7f2-131">Variables `arrayD` and `arrayE` have the same type — `Short(,)` — because their ranks and element types are the same, even though `arrayD` is not yet initialized.</span></span>  
  
 <span data-ttu-id="be7f2-132">Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="be7f2-132">For more information on arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="class-types"></a><span data-ttu-id="be7f2-133">Klassentypen</span><span class="sxs-lookup"><span data-stu-id="be7f2-133">Class Types</span></span>  
 <span data-ttu-id="be7f2-134">Es gibt keinen universellen Datentyp, der alle Klassen aus.</span><span class="sxs-lookup"><span data-stu-id="be7f2-134">There is no single data type comprising all classes.</span></span> <span data-ttu-id="be7f2-135">Obwohl eine Klasse von einer anderen Klasse erben kann, ist jeweils ein separates Data.</span><span class="sxs-lookup"><span data-stu-id="be7f2-135">Although one class can inherit from another class, each is a separate data type.</span></span> <span data-ttu-id="be7f2-136">Mehrere Instanzen derselben Klasse sind von den gleichen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="be7f2-136">Multiple instances of the same class are of the same data type.</span></span> <span data-ttu-id="be7f2-137">Wenn Sie eine Klassenvariable-Instanz zu einem anderen zuweisen, werden nicht nur verfügen sie über den gleichen Datentyp aufweisen, sie auf die gleiche Instanz der Klasse im Arbeitsspeicher verweisen.</span><span class="sxs-lookup"><span data-stu-id="be7f2-137">If you assign one class instance variable to another, not only do they have the same data type, they point to the same class instance in memory.</span></span>  
  
 <span data-ttu-id="be7f2-138">Weitere Informationen über Klassen finden Sie unter [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span><span class="sxs-lookup"><span data-stu-id="be7f2-138">For more information on classes, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be7f2-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be7f2-139">See also</span></span>

- [<span data-ttu-id="be7f2-140">Datentypen</span><span class="sxs-lookup"><span data-stu-id="be7f2-140">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [<span data-ttu-id="be7f2-141">Elementare Datentypen</span><span class="sxs-lookup"><span data-stu-id="be7f2-141">Elementary Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [<span data-ttu-id="be7f2-142">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be7f2-142">Generic Types in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="be7f2-143">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="be7f2-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="be7f2-144">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="be7f2-144">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="be7f2-145">Strukturen</span><span class="sxs-lookup"><span data-stu-id="be7f2-145">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="be7f2-146">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="be7f2-146">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="be7f2-147">Vorgehensweise: Ablegen mehrerer Werte in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="be7f2-147">How to: Hold More Than One Value in a Variable</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-hold-more-than-one-value-in-a-variable.md)
