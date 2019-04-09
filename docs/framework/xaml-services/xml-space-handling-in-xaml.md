---
title: xml:space-Behandlung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:space attribute
- XAML [XAML Services], white-space processing
- xml:space attribute [XAML Services]
- white-space processing [XAML Services]
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
ms.openlocfilehash: d15bab1ad9234959048fa7b7c3fa2bbbeca5fe6e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193316"
---
# <a name="xmlspace-handling-in-xaml"></a><span data-ttu-id="aa2a4-102">xml:space-Behandlung in XAML</span><span class="sxs-lookup"><span data-stu-id="aa2a4-102">xml:space Handling in XAML</span></span>
<span data-ttu-id="aa2a4-103">Die `xml:space` -Attribut ist ein XML-definiertes Attribut, das das Verhalten der Verarbeitung von signifikanten Leerzeichen in einem Objektelement deklariert.</span><span class="sxs-lookup"><span data-stu-id="aa2a4-103">The `xml:space` attribute is an XML-defined attribute that declares the significant white-space processing behavior within an object element.</span></span> <span data-ttu-id="aa2a4-104">Dieses Verhalten gilt für den gesamten Inhalt (inneren Text), die im Element enthalten, in denen `xml:space` wird deklariert, und auch Bereiche von untergeordneten Elementen.</span><span class="sxs-lookup"><span data-stu-id="aa2a4-104">This behavior is relevant for all content (inner text) contained within the element where `xml:space` is declared, and also scopes to child elements.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="aa2a4-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="aa2a4-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:space="preserve" />  
```  
  
 <span data-ttu-id="aa2a4-106">\- oder –</span><span class="sxs-lookup"><span data-stu-id="aa2a4-106">\- or -</span></span>  
  
```xaml  
<object xml:space="default" />  
```  
  
## <a name="remarks"></a><span data-ttu-id="aa2a4-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aa2a4-107">Remarks</span></span>  
 <span data-ttu-id="aa2a4-108">Die Definition für die `xml:space` -Attribut in XAML, einschließlich der zwei möglichen Werten ergibt sich aus `xml:space` W3C-Spezifikationen für XML als "spezielles Attribut" definiert.</span><span class="sxs-lookup"><span data-stu-id="aa2a4-108">The definition for the `xml:space` attribute in XAML including its two possible values is derived from `xml:space` as defined as a "special attribute" by W3C specifications for XML.</span></span>  
  
 <span data-ttu-id="aa2a4-109">Der Standardwert der `xml:space` -Attribut ist der literale Wert `"default"`.</span><span class="sxs-lookup"><span data-stu-id="aa2a4-109">The default value of the `xml:space` attribute is the literal value `"default"`.</span></span> <span data-ttu-id="aa2a4-110">Für den Wert `"default"`, oder wenn `xml:space` ist nicht angegeben, das Verhalten der signifikanten Leerzeichen Analyse wird die Standardbehandlung verwendet, wie im folgenden Thema beschrieben [White-Space-Verarbeitung in XAML](whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="aa2a4-110">For the value `"default"`, or if `xml:space` is not indicated at all, the behavior of significant white-space parsing is the default handling, as defined in the topic [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
 <span data-ttu-id="aa2a4-111">Geben Sie zum Beibehalten von Leerraum im Elementinhalt Objekt `xml:space="preserve"` für dieses Objektelement.</span><span class="sxs-lookup"><span data-stu-id="aa2a4-111">To preserve white space within object element content, specify `xml:space="preserve"` on that object element.</span></span>  
  
 <span data-ttu-id="aa2a4-112">Bei den meisten Interpretationen der `xml:space` -Attributeffekte und der Wert des Attributs definiert und gelten für untergeordnete Elemente.</span><span class="sxs-lookup"><span data-stu-id="aa2a4-112">Under most interpretations, the `xml:space` attribute effects and the value of the attribute are scoped to child elements.</span></span>  
  
 <span data-ttu-id="aa2a4-113">Eine vollständige Erläuterung der Leerzeichen in XAML verarbeitet, finden Sie unter [White-Space-Verarbeitung in XAML](whitespace-processing-in-xaml.md).</span><span class="sxs-lookup"><span data-stu-id="aa2a4-113">For a complete discussion of white-space processing in XAML, see [White-space processing in XAML](whitespace-processing-in-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa2a4-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa2a4-114">See also</span></span>

- [<span data-ttu-id="aa2a4-115">Leerstellenverarbeitung in XAML</span><span class="sxs-lookup"><span data-stu-id="aa2a4-115">White-space processing in XAML</span></span>](whitespace-processing-in-xaml.md)
- [<span data-ttu-id="aa2a4-116">Übersicht über XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="aa2a4-116">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
