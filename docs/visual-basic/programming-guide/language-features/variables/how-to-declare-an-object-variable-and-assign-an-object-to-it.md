---
title: 'Vorgehensweise: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: fb6411efc190dce335422369a8d2bbff564b9523
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58819670"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="87640-102">Vorgehensweise: Deklarieren einer Objektvariablen und Zuweisen eines entsprechenden Objekts in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="87640-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>
<span data-ttu-id="87640-103">Sie deklarieren eine Variable, der die [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) durch Angabe `As Object` in eine [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="87640-103">You declare a variable of the [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="87640-104">Sie können ein Objekt auf eine solche Variable zuweisen, platzieren Sie das Objekt hinter dem Gleichheitszeichen (`=`) in einer Zuweisung-Anweisung oder Initialisierung-Klausel.</span><span class="sxs-lookup"><span data-stu-id="87640-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87640-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87640-105">Example</span></span>  
 <span data-ttu-id="87640-106">Das folgende Beispiel deklariert eine `Object` -Variable und weist dieser aktuellen Instanz.</span><span class="sxs-lookup"><span data-stu-id="87640-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 <span data-ttu-id="87640-107">Sie können die Deklaration und Zuweisung kombinieren, durch die Variable als Teil der Deklaration initialisieren.</span><span class="sxs-lookup"><span data-stu-id="87640-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="87640-108">Das folgende Beispiel entspricht dem vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="87640-108">The following example is equivalent to the preceding example.</span></span>  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="87640-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="87640-109">Compiling the Code</span></span>  
 <span data-ttu-id="87640-110">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="87640-110">This example requires:</span></span>  
  
-   <span data-ttu-id="87640-111">Einen Verweis auf den <xref:System>-Namespace</span><span class="sxs-lookup"><span data-stu-id="87640-111">A reference to the <xref:System> namespace.</span></span>  
  
-   <span data-ttu-id="87640-112">Eine Klasse, Struktur oder Modul, in dem Platzieren der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="87640-112">A class, structure, or module in which to put the `Dim` statement.</span></span>  
  
-   <span data-ttu-id="87640-113">Eine Prozedur, in dem die zuweisungsanweisung abgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="87640-113">A procedure in which to put the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87640-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87640-114">See also</span></span>

- [<span data-ttu-id="87640-115">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="87640-115">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="87640-116">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="87640-116">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="87640-117">Deklaration von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="87640-117">Object Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [<span data-ttu-id="87640-118">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="87640-118">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="87640-119">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="87640-119">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="87640-120">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="87640-120">Local Type Inference</span></span>](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="87640-121">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="87640-121">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
