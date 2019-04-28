---
title: Der zugrunde liegende <typename>-Typ der Enumeration ist nicht CLS-kompatibel.
ms.date: 07/20/2015
f1_keywords:
- vbc40032
- bc40032
helpviewer_keywords:
- BC40032
ms.assetid: 32bf1949-fd73-456c-a323-bf1ffe1320ed
ms.openlocfilehash: 636fcc36e7bac52467998dc9c59f14ba1bedead3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774880"
---
# <a name="underlying-type-typename-of-enum-is-not-cls-compliant"></a><span data-ttu-id="cf53d-102">Der zugrunde liegende Typ \<Typename > der Enumeration ist nicht CLS-kompatibel.</span><span class="sxs-lookup"><span data-stu-id="cf53d-102">Underlying type \<typename> of Enum is not CLS-compliant</span></span>
<span data-ttu-id="cf53d-103">Der Datentyp angegeben werden, für diese Enumeration nicht ist Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span><span class="sxs-lookup"><span data-stu-id="cf53d-103">The data type specified for this enumeration is not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS).</span></span> <span data-ttu-id="cf53d-104">Dies ist kein Fehler in der Komponente, da die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] und Visual Basic unterstützt diesen Datentyp.</span><span class="sxs-lookup"><span data-stu-id="cf53d-104">This is not an error within your component, because the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] and Visual Basic support this data type.</span></span> <span data-ttu-id="cf53d-105">Allerdings kann in eine andere Komponente, die in streng CLS-kompatiblem Code geschrieben diesen Datentyp nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cf53d-105">However, another component written in strictly CLS-compliant code might not support this data type.</span></span> <span data-ttu-id="cf53d-106">Eine solche Komponente möglicherweise nicht erfolgreich mit der Komponente interagieren können.</span><span class="sxs-lookup"><span data-stu-id="cf53d-106">Such a component might not be able to interact successfully with your component.</span></span>  
  
 <span data-ttu-id="cf53d-107">Die folgenden Visual Basic-Datentypen sind nicht CLS-kompatibel:</span><span class="sxs-lookup"><span data-stu-id="cf53d-107">The following Visual Basic data types are not CLS-compliant:</span></span>  
  
- [<span data-ttu-id="cf53d-108">SByte-Datentyp</span><span class="sxs-lookup"><span data-stu-id="cf53d-108">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
- [<span data-ttu-id="cf53d-109">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="cf53d-109">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
- [<span data-ttu-id="cf53d-110">ULong-Datentyp</span><span class="sxs-lookup"><span data-stu-id="cf53d-110">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
- [<span data-ttu-id="cf53d-111">UShort-Datentyp</span><span class="sxs-lookup"><span data-stu-id="cf53d-111">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 <span data-ttu-id="cf53d-112">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="cf53d-112">By default, this message is a warning.</span></span> <span data-ttu-id="cf53d-113">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="cf53d-113">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="cf53d-114">**Fehler-ID:** BC40032</span><span class="sxs-lookup"><span data-stu-id="cf53d-114">**Error ID:** BC40032</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cf53d-115">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="cf53d-115">To correct this error</span></span>  
  
- <span data-ttu-id="cf53d-116">Wenn die Komponente nur mit anderen Schnittstellen [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Komponenten oder nicht mit anderen Komponenten verbunden, Sie müssen keine Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="cf53d-116">If your component interfaces only with other [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] components, or does not interface with any other components, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="cf53d-117">Wenn Sie mit einer Komponente, die nicht für geschriebenen anbinden, müssen die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], Sie möglicherweise fest, über Reflektion oder anhand der Dokumentation gibt an, ob sie diesen Datentyp unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cf53d-117">If you are interfacing with a component not written for the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], you might be able to determine, either through reflection or from documentation, whether it supports this data type.</span></span> <span data-ttu-id="cf53d-118">Wenn dies der Fall ist, müssen Sie keine Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="cf53d-118">If it does, you do not need to change anything.</span></span>  
  
- <span data-ttu-id="cf53d-119">Wenn Sie mit einer Komponente verbunden sind, die diesen Datentyp nicht unterstützt, müssen Sie es mit den ähnlichsten CLS-kompatiblen Typ ersetzen.</span><span class="sxs-lookup"><span data-stu-id="cf53d-119">If you are interfacing with a component that does not support this data type, you must replace it with the closest CLS-compliant type.</span></span> <span data-ttu-id="cf53d-120">Anstelle von `UInteger` könnten Sie beispielsweise `Integer` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="cf53d-120">For example, in place of `UInteger` you might be able to use `Integer` if you do not need the value range above 2,147,483,647.</span></span> <span data-ttu-id="cf53d-121">Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long`ersetzen.</span><span class="sxs-lookup"><span data-stu-id="cf53d-121">If you do need the extended range, you can replace `UInteger` with `Long`.</span></span>  
  
- <span data-ttu-id="cf53d-122">Beachten Sie beim Verbinden mit Automatisierungs- oder COM-Objekten, dass einige Typen über andere Datenbreiten als im [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verfügen.</span><span class="sxs-lookup"><span data-stu-id="cf53d-122">If you are interfacing with Automation or COM objects, keep in mind that some types have different data widths than in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="cf53d-123">Zum Beispiel umfasst `uint` in anderen Umgebungen oft 16 Bits.</span><span class="sxs-lookup"><span data-stu-id="cf53d-123">For example, `uint` is often 16 bits in other environments.</span></span> <span data-ttu-id="cf53d-124">Wenn Sie ein 16-Bit-Argument an eine solche Komponente übergeben, deklarieren Sie sie als `UShort` anstelle von `UInteger` in verwaltetem Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="cf53d-124">If you are passing a 16-bit argument to such a component, declare it as `UShort` instead of `UInteger` in your managed Visual Basic code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf53d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf53d-125">See also</span></span>

- [<span data-ttu-id="cf53d-126">Reflektion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cf53d-126">Reflection (Visual Basic)</span></span>](../../programming-guide/concepts/reflection.md)
- [<span data-ttu-id="cf53d-127">Reflexion</span><span class="sxs-lookup"><span data-stu-id="cf53d-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
