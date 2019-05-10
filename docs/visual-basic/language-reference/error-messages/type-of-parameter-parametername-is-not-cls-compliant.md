---
title: Der Typ des <parametername>-Parameters ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40028
- bc40028
helpviewer_keywords:
- BC40028
ms.assetid: dfa1f6f9-bb88-44ad-b85f-149144363d41
ms.openlocfilehash: a719b3f1cbd972e79d057730ac1d89e5d91d97e5
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664311"
---
# <a name="type-of-parameter-parametername-is-not-cls-compliant"></a><span data-ttu-id="1b039-102">Typ des Parameters "\<Parametername >' ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="1b039-102">Type of parameter '\<parametername>' is not CLS-compliant</span></span>
<span data-ttu-id="1b039-103">Eine Prozedur wird als markiert `<CLSCompliant(True)>` deklariert jedoch einen Parameter mit einem Typ mit der Kennzeichnung `<CLSCompliant(False)>`, nicht markiert ist oder nicht geeignet ist, da es sich um einen nicht kompatiblen Typ handelt.</span><span class="sxs-lookup"><span data-stu-id="1b039-103">A procedure is marked as `<CLSCompliant(True)>` but declares a parameter with a type that is marked as `<CLSCompliant(False)>`, is not marked, or does not qualify because it is a noncompliant type.</span></span>  
  
 <span data-ttu-id="1b039-104">Damit eine Prozedur mit [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS) kompatibel ist, darf sie ausschließlich CLS-kompatible Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="1b039-104">For a procedure to be compliant with the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), it must use only CLS-compliant types.</span></span> <span data-ttu-id="1b039-105">Dies gilt für die Parametertypen, den Rückgabetyp und die Typen all ihrer lokalen Variablen.</span><span class="sxs-lookup"><span data-stu-id="1b039-105">This applies to the types of the parameters, the return type, and the types of all its local variables.</span></span>  
  
 <span data-ttu-id="1b039-106">Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="1b039-106">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="1b039-107">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="1b039-107">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="1b039-108">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="1b039-108">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="1b039-109">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="1b039-109">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="1b039-110">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="1b039-110">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="1b039-111">Wenn Sie das <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant` -Parameter des Attributs auf `True` oder `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1b039-111">When you apply the <xref:System.CLSCompliantAttribute> to a programming element, you set the attribute's `isCompliant` parameter to either `True` or `False` to indicate compliance or noncompliance.</span></span> <span data-ttu-id="1b039-112">Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="1b039-112">There is no default for this parameter, and you must supply a value.</span></span>  
  
 <span data-ttu-id="1b039-113">Wenn Sie das <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.</span><span class="sxs-lookup"><span data-stu-id="1b039-113">If you do not apply the <xref:System.CLSCompliantAttribute> to an element, it is considered to be noncompliant.</span></span>  
  
 <span data-ttu-id="1b039-114">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="1b039-114">By default, this message is a warning.</span></span> <span data-ttu-id="1b039-115">Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="1b039-115">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="1b039-116">**Fehler-ID:** BC40028</span><span class="sxs-lookup"><span data-stu-id="1b039-116">**Error ID:** BC40028</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1b039-117">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1b039-117">To correct this error</span></span>  
  
- <span data-ttu-id="1b039-118">Wenn die Prozedur einen Parameter dieses bestimmten Typs akzeptieren muss, entfernen Sie die <xref:System.CLSCompliantAttribute>.</span><span class="sxs-lookup"><span data-stu-id="1b039-118">If the procedure must take a parameter of this particular type, remove the <xref:System.CLSCompliantAttribute>.</span></span> <span data-ttu-id="1b039-119">Die Prozedur kann nicht CLS-kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="1b039-119">The procedure cannot be CLS-compliant.</span></span>  
  
- <span data-ttu-id="1b039-120">Wenn die Prozedur CLS-kompatibel sein muss, ändern Sie den Typ dieses Parameters in den ähnlichsten CLS-kompatiblen Typ.</span><span class="sxs-lookup"><span data-stu-id="1b039-120">If the procedure must be CLS-compliant, change the type of this parameter to the closest CLS-compliant type.</span></span> <span data-ttu-id="1b039-121">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="1b039-121">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="1b039-122">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="1b039-122">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="1b039-123">Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen.</span><span class="sxs-lookup"><span data-stu-id="1b039-123">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="1b039-124">Zum Beispiel umfasst `int` in anderen Umgebungen oft 16 Bits.</span><span class="sxs-lookup"><span data-stu-id="1b039-124">For example, `int` is often 16 bits in other environments.</span></span> <span data-ttu-id="1b039-125">Wenn Sie eine 16-Bit-Ganzzahl in eine solche Komponente akzeptieren, deklarieren Sie sie als `Short` anstelle von `Integer` in verwaltetem Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="1b039-125">If you are accepting a 16-bit integer from such a component, declare it as `Short` instead of `Integer` in your managed Visual Basic code.</span></span>