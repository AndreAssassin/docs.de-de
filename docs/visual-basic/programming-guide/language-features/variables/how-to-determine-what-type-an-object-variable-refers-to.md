---
title: 'Vorgehensweise: Bestimmen des Typs (Visual Basic) eine Objektvariable verweist'
ms.date: 07/20/2015
helpviewer_keywords:
- TypeOf operator [Visual Basic], determining object variable type
- variables [Visual Basic], object
- object variables [Visual Basic], determining type
ms.assetid: 6f6a138d-58a4-40d1-9f4e-0a3c598eaf81
ms.openlocfilehash: 6499dfce880cc9ce16e5d77887afc0598692f48e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59342868"
---
# <a name="how-to-determine-what-type-an-object-variable-refers-to-visual-basic"></a><span data-ttu-id="338e4-102">Vorgehensweise: Bestimmen des Typs (Visual Basic) eine Objektvariable verweist</span><span class="sxs-lookup"><span data-stu-id="338e4-102">How to: Determine What Type an Object Variable Refers To (Visual Basic)</span></span>
<span data-ttu-id="338e4-103">Eine Objektvariable enthält einen Zeiger auf Daten, die an anderer Stelle gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="338e4-103">An object variable contains a pointer to data that is stored elsewhere.</span></span> <span data-ttu-id="338e4-104">Der Typ der Daten kann während der Laufzeit ändern.</span><span class="sxs-lookup"><span data-stu-id="338e4-104">The type of that data can change during run time.</span></span> <span data-ttu-id="338e4-105">Sie können jederzeit eingehen, verwenden die <xref:System.Type.GetTypeCode%2A> Methode, um den aktuellen Laufzeittyp zu bestimmen oder die [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) um zu ermitteln, ob die aktuelle Laufzeit-Typinformationen mit einem angegebenen Typ kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="338e4-105">At any moment, you can use the <xref:System.Type.GetTypeCode%2A> method to determine the current run-time type, or the [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) to find out if the current run-time type is compatible with a specified type.</span></span>  
  
### <a name="to-determine-the-exact-type-an-object-variable-currently-refers-to"></a><span data-ttu-id="338e4-106">Bezieht sich auf, um zu bestimmen, dass genau eine Objektvariable derzeit eingeben</span><span class="sxs-lookup"><span data-stu-id="338e4-106">To determine the exact type an object variable currently refers to</span></span>  
  
1. <span data-ttu-id="338e4-107">Rufen Sie die Objektvariable, die <xref:System.Object.GetType%2A> Methode zum Abrufen einer <xref:System.Type?displayProperty=nameWithType> Objekt.</span><span class="sxs-lookup"><span data-stu-id="338e4-107">On the object variable, call the <xref:System.Object.GetType%2A> method to retrieve a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
    ```  
    Dim myObject As Object  
    myObject.GetType()  
    ```  
  
2. <span data-ttu-id="338e4-108">Auf der <xref:System.Type?displayProperty=nameWithType> Klasse, rufen Sie die freigegebene Methode <xref:System.Type.GetTypeCode%2A> zum Abrufen der <xref:System.TypeCode> Enumerationswert für den Typ des Objekts.</span><span class="sxs-lookup"><span data-stu-id="338e4-108">On the <xref:System.Type?displayProperty=nameWithType> class, call the shared method <xref:System.Type.GetTypeCode%2A> to retrieve the <xref:System.TypeCode> enumeration value for the object's type.</span></span>  
  
    ```  
    Dim myObject As Object  
    Dim datTyp As Integer = Type.GetTypeCode(myObject.GetType())  
    MsgBox("myObject currently has type code " & CStr(datTyp))  
    ```  
  
     <span data-ttu-id="338e4-109">Sie können testen, die <xref:System.TypeCode> Enumerationswert für Enumerationsmember von Interesse, z. B. sind `Double`.</span><span class="sxs-lookup"><span data-stu-id="338e4-109">You can test the <xref:System.TypeCode> enumeration value against whichever enumeration members are of interest, such as `Double`.</span></span>  
  
### <a name="to-determine-whether-an-object-variables-type-is-compatible-with-a-specified-type"></a><span data-ttu-id="338e4-110">Um zu bestimmen, ob ein Objekt ist Variablentyp kompatibel mit einem angegebenen Typ</span><span class="sxs-lookup"><span data-stu-id="338e4-110">To determine whether an object variable's type is compatible with a specified type</span></span>  
  
-   <span data-ttu-id="338e4-111">Verwenden der `TypeOf` Operator in Kombination mit der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) So testen Sie das Objekt mit einem `TypeOf`... `Is` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="338e4-111">Use the `TypeOf` operator in combination with the [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) to test the object with a `TypeOf`...`Is` expression.</span></span>  
  
    ```  
    If TypeOf objA Is System.Windows.Forms.Control Then  
        MsgBox("objA is compatible with the Control class")  
    End If  
    ```  
  
     <span data-ttu-id="338e4-112">Die `TypeOf`... `Is` gibt `True` Typ ist mit dem angegebenen Typ kompatibel, wenn der Laufzeit des Objekts.</span><span class="sxs-lookup"><span data-stu-id="338e4-112">The `TypeOf`...`Is` expression returns `True` if the object's run-time type is compatible with the specified type.</span></span>  
  
     <span data-ttu-id="338e4-113">Das Kriterium für die Kompatibilität hängt davon ab, ob der angegebene Typ eine Klasse, Struktur oder Schnittstelle ist.</span><span class="sxs-lookup"><span data-stu-id="338e4-113">The criterion for compatibility depends on whether the specified type is a class, structure, or interface.</span></span> <span data-ttu-id="338e4-114">Im Allgemeinen sind die Typen kompatibel, wenn das Objekt vom gleichen Typ wie ist, erbt oder den angegebenen Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="338e4-114">In general, the types are compatible if the object is of the same type as, inherits from, or implements the specified type.</span></span> <span data-ttu-id="338e4-115">Weitere Informationen finden Sie unter [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span><span class="sxs-lookup"><span data-stu-id="338e4-115">For more information, see [TypeOf Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="338e4-116">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="338e4-116">Compiling the Code</span></span>  
 <span data-ttu-id="338e4-117">Beachten Sie, dass der angegebene Typ eine Variable oder einen Ausdruck kann nicht an.</span><span class="sxs-lookup"><span data-stu-id="338e4-117">Note that the specified type cannot be a variable or expression.</span></span> <span data-ttu-id="338e4-118">Es muss den Namen eines definierten Typs, z. B. eine Klasse, Struktur oder Schnittstelle sein.</span><span class="sxs-lookup"><span data-stu-id="338e4-118">It must be the name of a defined type, such as a class, structure, or interface.</span></span> <span data-ttu-id="338e4-119">Hierzu gehören z. B. systeminterne Typen `Integer` und `String`.</span><span class="sxs-lookup"><span data-stu-id="338e4-119">This includes intrinsic types such as `Integer` and `String`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="338e4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="338e4-120">See also</span></span>

- <xref:System.Object.GetType%2A>
- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Type.GetTypeCode%2A>
- <xref:System.TypeCode>
- [<span data-ttu-id="338e4-121">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="338e4-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="338e4-122">Werte von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="338e4-122">Object Variable Values</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [<span data-ttu-id="338e4-123">Object-Datentyp</span><span class="sxs-lookup"><span data-stu-id="338e4-123">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)
