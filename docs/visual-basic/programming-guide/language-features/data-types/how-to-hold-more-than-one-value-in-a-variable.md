---
title: 'Vorgehensweise: Ablegen von mehr als einen Wert in einer Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: e2e1648ea508ecdd744adb8d2a4f7fdbc1e586c4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906489"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="0f125-102">Vorgehensweise: Ablegen von mehr als einen Wert in einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f125-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>
<span data-ttu-id="0f125-103">Eine Variable enthält mehr als einen Wert aus, wenn Sie vom deklariert eine *zusammengesetzten Datentyp*.</span><span class="sxs-lookup"><span data-stu-id="0f125-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>  
  
 <span data-ttu-id="0f125-104">[Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) enthalten Klassen, Strukturen und Arrays.</span><span class="sxs-lookup"><span data-stu-id="0f125-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="0f125-105">Eine Variable einen zusammengesetzten Datentyp aufweisen, kann eine Kombination von elementare Datentypen und andere zusammengesetzten Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0f125-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="0f125-106">Strukturen und Klassen können sowohl Code als auch Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="0f125-106">Structures and classes can hold code as well as data.</span></span>  
  
### <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="0f125-107">Um mehr als einen Wert in einer Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0f125-107">To hold more than one value in a variable</span></span>  
  
1. <span data-ttu-id="0f125-108">Bestimmen des Typs, zusammengesetzte Datenelemente für die Variable verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0f125-108">Determine what composite data type you want to use for your variable.</span></span>  
  
2. <span data-ttu-id="0f125-109">Falls bereits nicht der zusammengesetzten Datentyp definiert ist, definieren sie, damit die Variable verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f125-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>  
  
    - <span data-ttu-id="0f125-110">Definieren Sie eine Struktur mit einem [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0f125-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>  
  
    - <span data-ttu-id="0f125-111">Definieren Sie ein Array mit einem [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0f125-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
    - <span data-ttu-id="0f125-112">Definieren einer Klasse mit einem [Class-Anweisung](../../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0f125-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>  
  
3. <span data-ttu-id="0f125-113">Deklarieren Sie die Variable mit einem `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="0f125-113">Declare your variable with a `Dim` statement.</span></span>  
  
4. <span data-ttu-id="0f125-114">Gehen Sie vor dem Variablennamen ein `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="0f125-114">Follow the variable name with an `As` clause.</span></span>  
  
5. <span data-ttu-id="0f125-115">Führen Sie die `As` Schlüsselwort mit dem Namen des entsprechenden zusammengesetzten-Datentyps.</span><span class="sxs-lookup"><span data-stu-id="0f125-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f125-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f125-116">See also</span></span>

- [<span data-ttu-id="0f125-117">Datentypen</span><span class="sxs-lookup"><span data-stu-id="0f125-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0f125-118">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="0f125-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="0f125-119">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="0f125-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="0f125-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="0f125-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="0f125-121">Arrays</span><span class="sxs-lookup"><span data-stu-id="0f125-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="0f125-122">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="0f125-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="0f125-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="0f125-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
