---
title: xml:lang-Behandlung in XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: 3af85f298f7581146b5ecc8a559b185f1a01e54c
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919996"
---
# <a name="xmllang-handling-in-xaml"></a><span data-ttu-id="6a571-102">xml:lang-Behandlung in XAML</span><span class="sxs-lookup"><span data-stu-id="6a571-102">xml:lang Handling in XAML</span></span>
<span data-ttu-id="6a571-103">Das `xml:lang` -Attribut ist ein [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]-definiertes Attribut, das die Informationen zur Sprache und Kultur für ein Element in XML deklariert.</span><span class="sxs-lookup"><span data-stu-id="6a571-103">The `xml:lang` attribute is an [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]-defined attribute that declares the language and culture information for an element in XML.</span></span> <span data-ttu-id="6a571-104">Das Attribut weist in XAML dieselbe Bedeutung auf, es müssen jedoch einige zusätzliche Aspekte berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="6a571-104">This same meaning of the attribute persists in XAML; however, some additional considerations apply.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="6a571-105">Verwendung von XAML-Attributen</span><span class="sxs-lookup"><span data-stu-id="6a571-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object xml:lang="rfc3066lang" />  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="6a571-106">XAML-Werte</span><span class="sxs-lookup"><span data-stu-id="6a571-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6a571-107">*rfc3066lang*</span><span class="sxs-lookup"><span data-stu-id="6a571-107">*rfc3066lang*</span></span>|<span data-ttu-id="6a571-108">Eine vom [RFC 3066](https://go.microsoft.com/fwlink/?LinkId=132454) -Standard abgeleitete Zeichenfolge, die entweder eine Sprache oder eine Kombination von Sprache-Region kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="6a571-108">A string that is derived from the [RFC 3066](https://go.microsoft.com/fwlink/?LinkId=132454) standard and identifies either a language or a language-region.</span></span> <span data-ttu-id="6a571-109">In letzterem Fall werden Sprache und Region durch einen einzelnen Bindestrich getrennt.</span><span class="sxs-lookup"><span data-stu-id="6a571-109">When it is the latter, the language and region are separated by a single hyphen.</span></span> <span data-ttu-id="6a571-110">Weitere Informationen zu den Werten und zum Format finden Sie unter <xref:System.Windows.Markup.XmlLanguage> .</span><span class="sxs-lookup"><span data-stu-id="6a571-110">See <xref:System.Windows.Markup.XmlLanguage> for more information about the values and format.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6a571-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a571-111">Remarks</span></span>  
 <span data-ttu-id="6a571-112">Die Definition für das `xml:lang`-Attribut in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] wird von `xml:lang` abgeleitet, das vom World Wide Web Consortium (W3C) für [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)]als "spezielles Attribut" definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6a571-112">The definition for the `xml:lang` attribute in [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] is derived from `xml:lang` as defined as a "special attribute" by the World Wide Web Consortium (W3C) for [!INCLUDE[TLA2#tla_xml](../../../includes/tla2sharptla-xml-md.md)].</span></span> <span data-ttu-id="6a571-113">Informationen zu Sprache und Kultur werden von Elementen je nach deren Implementierung möglicherweise unterschiedlich verarbeitet. Es gibt jedoch keine [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] -Standardverarbeitung für das `xml:lang` -Attribut.</span><span class="sxs-lookup"><span data-stu-id="6a571-113">Language and culture information is potentially processed in different ways by elements, depending on their implementations; however, there is no default [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing of the `xml:lang` attribute.</span></span>  
  
 <span data-ttu-id="6a571-114">Der Standardwert des `xml:lang` -Attributs ist eine leere Zeichenfolge auf Attributebene.</span><span class="sxs-lookup"><span data-stu-id="6a571-114">The default value of the `xml:lang` attribute is an empty string at the attribute level.</span></span>  
  
 <span data-ttu-id="6a571-115">Die `xml:lang` -Attributeffekte und der Wert des Attributs werden im Allgemeinen in untergeordneten Elementen bewahrt, wenn sie von Systemen interpretiert werden, die auf `xml:lang` -Werte einwirken.</span><span class="sxs-lookup"><span data-stu-id="6a571-115">The `xml:lang` attribute effects and the value of the attribute are generally perpetuated to child elements, when interpreted by systems that act on `xml:lang` values.</span></span>  
  
 <span data-ttu-id="6a571-116">Bei der Interpretation von XAML-Writern von XAML-Diensten des .NET Frameworks kann ein `xml:lang` -Wert <xref:System.Windows.Markup.XmlLanguage> - oder <xref:System.Globalization.CultureInfo> -Objekte in der zugrunde liegenden Objektdarstellung erstellen. Dieses Verhalten hängt jedoch davon ab, ob der für `xml:lang` angegebene Wert eine gültige Ausführung für diese Klassen ist.</span><span class="sxs-lookup"><span data-stu-id="6a571-116">When interpreted by XAML writers of .NET Framework XAML Services, an `xml:lang` value can create <xref:System.Windows.Markup.XmlLanguage> or <xref:System.Globalization.CultureInfo> objects in the underlying object representation; however, that behavior depends on whether the value specified for `xml:lang` is a valid construction for those classes.</span></span>  
  
 <span data-ttu-id="6a571-117">Frameworks können zwischen den vom Framework definierten Eigenschaften und der Bedeutung der `xml:lang` in XML durch Anwenden von <xref:System.Windows.Markup.XmlLangPropertyAttribute> auf die Eigenschaft entsprechende Zuordnungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="6a571-117">Frameworks can create associations between framework-defined properties and the meaning of `xml:lang` in XML by applying <xref:System.Windows.Markup.XmlLangPropertyAttribute> to the property.</span></span>  
  
## <a name="wpf-usage-nodes"></a><span data-ttu-id="6a571-118">Hinweise zur WPF-Verwendung</span><span class="sxs-lookup"><span data-stu-id="6a571-118">WPF Usage Nodes</span></span>  
 <span data-ttu-id="6a571-119">Für Elemente, die abgeleitete Klassen von <xref:System.Windows.FrameworkElement> oder <xref:System.Windows.FrameworkContentElement>darstellen, können Sie die entsprechende <xref:System.Windows.FrameworkElement.Language%2A> -Abhängigkeitseigenschaft anstelle des `xml:lang` -Attributs verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a571-119">For elements that are derived classes of <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement>, you can use the equivalent <xref:System.Windows.FrameworkElement.Language%2A> dependency property instead of the `xml:lang` attribute.</span></span> <span data-ttu-id="6a571-120">Die <xref:System.Windows.FrameworkElement.Language%2A> -Eigenschaft verwendet standardmäßig „en-US“, wenn sie nicht anderweitig festgelegt wird. Dies erfolgt entweder über die Eigenschaft oder durch die Verarbeitung des `xml:lang` -Attributs.</span><span class="sxs-lookup"><span data-stu-id="6a571-120">By default, the <xref:System.Windows.FrameworkElement.Language%2A> property uses "en-US" if it is not otherwise set, either through the property or through processing the `xml:lang` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a571-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a571-121">See also</span></span>

- [<span data-ttu-id="6a571-122">Globalisierung für WPF</span><span class="sxs-lookup"><span data-stu-id="6a571-122">Globalization for WPF</span></span>](../wpf/advanced/globalization-for-wpf.md)
