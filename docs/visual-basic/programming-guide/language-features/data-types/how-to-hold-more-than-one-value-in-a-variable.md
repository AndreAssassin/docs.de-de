---
title: 'Vorgehensweise: Enthalten mehr als einen Wert in einer Variablen (Visual Basic)'
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
ms.openlocfilehash: 8d07a34a98303f9d220dba0a3c955120b421340e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054200"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="8e1d9-102">Vorgehensweise: Enthalten mehr als einen Wert in einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8e1d9-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>

<span data-ttu-id="8e1d9-103">Eine Variable enthält mehr als einen Wert, wenn Sie Sie als einen zusammen *gesetzten Datentyp*deklarieren.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>

<span data-ttu-id="8e1d9-104">Zusammen [gesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) umfassen Strukturen, Arrays und Klassen.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-104">[Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="8e1d9-105">Eine Variable eines zusammengesetzten Datentyps kann eine Kombination aus elementaren Datentypen und anderen zusammengesetzten Typen enthalten.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="8e1d9-106">Strukturen und Klassen können sowohl Code als auch Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-106">Structures and classes can hold code as well as data.</span></span>

## <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="8e1d9-107">So speichern Sie mehr als einen Wert in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="8e1d9-107">To hold more than one value in a variable</span></span>

1. <span data-ttu-id="8e1d9-108">Bestimmen Sie den zusammengesetzten Datentyp, den Sie für die Variable verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-108">Determine what composite data type you want to use for your variable.</span></span>

2. <span data-ttu-id="8e1d9-109">Wenn der zusammengesetzte Datentyp nicht bereits definiert ist, definieren Sie ihn so, dass er von der Variablen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>

    - <span data-ttu-id="8e1d9-110">Definieren Sie eine Struktur mit einer [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8e1d9-110">Define a structure with a [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md).</span></span>

    - <span data-ttu-id="8e1d9-111">Definieren Sie ein Array mit einer [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8e1d9-111">Define an array with a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

    - <span data-ttu-id="8e1d9-112">Definieren Sie eine Klasse mit einer [Class-Anweisung](../../../../visual-basic/language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8e1d9-112">Define a class with a [Class Statement](../../../../visual-basic/language-reference/statements/class-statement.md).</span></span>

3. <span data-ttu-id="8e1d9-113">Deklarieren Sie die Variable `Dim` mit einer-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-113">Declare your variable with a `Dim` statement.</span></span>

4. <span data-ttu-id="8e1d9-114">Befolgen Sie den Variablennamen mit `As` einer-Klausel.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-114">Follow the variable name with an `As` clause.</span></span>

5. <span data-ttu-id="8e1d9-115">Befolgen Sie `As` das-Schlüsselwort mit dem Namen des entsprechenden zusammengesetzten Datentyps.</span><span class="sxs-lookup"><span data-stu-id="8e1d9-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="8e1d9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e1d9-116">See also</span></span>

- [<span data-ttu-id="8e1d9-117">Datentypen</span><span class="sxs-lookup"><span data-stu-id="8e1d9-117">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8e1d9-118">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="8e1d9-118">Type Characters</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [<span data-ttu-id="8e1d9-119">Zusammengesetzte Datentypen</span><span class="sxs-lookup"><span data-stu-id="8e1d9-119">Composite Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [<span data-ttu-id="8e1d9-120">Strukturen</span><span class="sxs-lookup"><span data-stu-id="8e1d9-120">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="8e1d9-121">Arrays</span><span class="sxs-lookup"><span data-stu-id="8e1d9-121">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="8e1d9-122">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="8e1d9-122">Objects and Classes</span></span>](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="8e1d9-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="8e1d9-123">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
