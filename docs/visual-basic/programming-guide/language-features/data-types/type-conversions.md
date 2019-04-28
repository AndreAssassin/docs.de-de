---
title: Typkonvertierung in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- data types [Visual Basic], changing
- variables [Visual Basic], changing data type
- type conversion [Visual Basic]
- conversions [Visual Basic], data type
- changing data types [Visual Basic]
- data type conversion [Visual Basic]
ms.assetid: 1cdacd21-ba31-4b62-b5be-395e41eeaa17
ms.openlocfilehash: 026b2a250abfac0782feb0946bc50a94f504f7ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61663283"
---
# <a name="type-conversions-in-visual-basic"></a><span data-ttu-id="96f1c-102">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96f1c-102">Type Conversions in Visual Basic</span></span>
<span data-ttu-id="96f1c-103">Das Ändern eines Werts aus einem Datentyp in einen anderen Typ wird als bezeichnet *Konvertierung*.</span><span class="sxs-lookup"><span data-stu-id="96f1c-103">The process of changing a value from one data type to another type is called *conversion*.</span></span> <span data-ttu-id="96f1c-104">Konvertierungen sind entweder *erweiternde* oder *einschränkende*, je nachdem, auf die Datenkapazität, der den verwendeten Typen.</span><span class="sxs-lookup"><span data-stu-id="96f1c-104">Conversions are either *widening* or *narrowing*, depending on the data capacities of the types involved.</span></span> <span data-ttu-id="96f1c-105">Sie sind auch *implizite* oder *explizite*, je nachdem, auf die Syntax im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="96f1c-105">They are also *implicit* or *explicit*, depending on the syntax in the source code.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="96f1c-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="96f1c-106">In This Section</span></span>  
 [<span data-ttu-id="96f1c-107">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="96f1c-107">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 <span data-ttu-id="96f1c-108">Erläutert, Konvertierungen klassifiziert, indem Sie, ob der Zieltyp für die Daten enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="96f1c-108">Explains conversions classified by whether the destination type can hold the data.</span></span>  
  
 [<span data-ttu-id="96f1c-109">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="96f1c-109">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 <span data-ttu-id="96f1c-110">Beschreibt die Konvertierungen, die klassifiziert, indem Sie, ob Visual Basic automatisch ausführt.</span><span class="sxs-lookup"><span data-stu-id="96f1c-110">Discusses conversions classified by whether Visual Basic performs them automatically.</span></span>  
  
 [<span data-ttu-id="96f1c-111">Konvertierungen zwischen Zeichenfolgen und anderen Typen</span><span class="sxs-lookup"><span data-stu-id="96f1c-111">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)  
 <span data-ttu-id="96f1c-112">Veranschaulicht die Konvertierung zwischen Zeichenfolgen und numerischen, `Boolean`, oder Datum/Uhrzeit-Werte.</span><span class="sxs-lookup"><span data-stu-id="96f1c-112">Illustrates converting between strings and numeric, `Boolean`, or date/time values.</span></span>  
  
 [<span data-ttu-id="96f1c-113">Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="96f1c-113">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 <span data-ttu-id="96f1c-114">Zeigt, wie Konvertieren einer `Object` -Variable auf einen anderen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="96f1c-114">Shows how to convert an `Object` variable to any other data type.</span></span>  
  
 [<span data-ttu-id="96f1c-115">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="96f1c-115">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 <span data-ttu-id="96f1c-116">Führt Sie durch den Prozess der Konvertierung zwischen Arrays mit unterschiedlichen Datentypen.</span><span class="sxs-lookup"><span data-stu-id="96f1c-116">Steps you through the process of converting between arrays of different data types.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="96f1c-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="96f1c-117">Related Sections</span></span>  
 [<span data-ttu-id="96f1c-118">Datentypen</span><span class="sxs-lookup"><span data-stu-id="96f1c-118">Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 <span data-ttu-id="96f1c-119">Führt die Visual Basic-Datentypen und beschreibt, wie sie.</span><span class="sxs-lookup"><span data-stu-id="96f1c-119">Introduces the Visual Basic data types and describes how to use them.</span></span>  
  
 [<span data-ttu-id="96f1c-120">Datentypen</span><span class="sxs-lookup"><span data-stu-id="96f1c-120">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)  
 <span data-ttu-id="96f1c-121">Listet die elementare Datentypen, die von Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="96f1c-121">Lists the elementary data types supplied by Visual Basic.</span></span>  
  
 [<span data-ttu-id="96f1c-122">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="96f1c-122">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 <span data-ttu-id="96f1c-123">Beschreibt einige häufig auftretende Probleme können bei der Arbeit mit Datentypen.</span><span class="sxs-lookup"><span data-stu-id="96f1c-123">Discusses some common problems that can arise when working with data types.</span></span>
