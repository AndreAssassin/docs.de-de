---
title: XML-Value-Eigenschaft (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 46f81e39686da30270cd67edeb4c9f2d43e048b3
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592004"
---
# <a name="xml-value-property-visual-basic"></a><span data-ttu-id="f0987-102">XML-Value-Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0987-102">XML Value Property (Visual Basic)</span></span>

<span data-ttu-id="f0987-103">Bietet Zugriff auf den Wert des ersten Elements einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="f0987-103">Provides access to the value of the first element of a collection of <xref:System.Xml.Linq.XElement> objects.</span></span>

## <a name="syntax"></a><span data-ttu-id="f0987-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0987-104">Syntax</span></span>

```vb
object.Value
```

## <a name="parts"></a><span data-ttu-id="f0987-105">Teile</span><span class="sxs-lookup"><span data-stu-id="f0987-105">Parts</span></span>

|<span data-ttu-id="f0987-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f0987-106">Term</span></span>|<span data-ttu-id="f0987-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f0987-107">Definition</span></span>|  
|---|---|  
|`object`|<span data-ttu-id="f0987-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f0987-108">Required.</span></span> <span data-ttu-id="f0987-109">Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="f0987-109">Collection of <xref:System.Xml.Linq.XElement> objects.</span></span>|  

## <a name="return-value"></a><span data-ttu-id="f0987-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f0987-110">Return Value</span></span>

 <span data-ttu-id="f0987-111">Eine `String`, die den Wert des ersten Elements der Auflistung enthält, oder `Nothing`, wenn die Auflistung leer ist.</span><span class="sxs-lookup"><span data-stu-id="f0987-111">A `String` that contains the value of the first element of the collection, or `Nothing` if the collection is empty.</span></span>

## <a name="remarks"></a><span data-ttu-id="f0987-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0987-112">Remarks</span></span>

 <span data-ttu-id="f0987-113">Die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft erleichtert den Zugriff auf den Wert des ersten Elements in einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="f0987-113">The <xref:System.Xml.Linq.XElement.Value%2A> property makes it easy to access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="f0987-114">Diese Eigenschaft prüft zunächst, ob die Auflistung mindestens ein-Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="f0987-114">This property first checks whether the collection contains at least one object.</span></span> <span data-ttu-id="f0987-115">Wenn die Auflistung leer ist, gibt diese Eigenschaft `Nothing` zurück.</span><span class="sxs-lookup"><span data-stu-id="f0987-115">If the collection is empty, this property returns `Nothing`.</span></span> <span data-ttu-id="f0987-116">Andernfalls gibt diese Eigenschaft den Wert der <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft des ersten Elements in der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="f0987-116">Otherwise, this property returns the value of the <xref:System.Xml.Linq.XElement.Value%2A> property of the first element in the collection.</span></span>

> [!NOTE]
> <span data-ttu-id="f0987-117">Wenn Sie mit dem Bezeichner "\@" auf den Wert eines XML-Attributs zugreifen, wird der Attribut Wert als `String` zurückgegeben, und Sie müssen die <xref:System.Xml.Linq.XAttribute.Value%2A>-Eigenschaft nicht explizit angeben.</span><span class="sxs-lookup"><span data-stu-id="f0987-117">When you access the value of an XML attribute using the '\@' identifier, the attribute value is returned as a `String` and you do not need to explicitly specify the <xref:System.Xml.Linq.XAttribute.Value%2A> property.</span></span>

 <span data-ttu-id="f0987-118">Wenn Sie auf andere Elemente in einer Auflistung zugreifen möchten, können Sie die XML-Erweiterungsindexer-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0987-118">To access other elements in a collection, you can use the XML extension indexer property.</span></span> <span data-ttu-id="f0987-119">Weitere Informationen finden Sie unter [Extension Indexer-Eigenschaft](extension-indexer-property.md).</span><span class="sxs-lookup"><span data-stu-id="f0987-119">For more information, see [Extension Indexer Property](extension-indexer-property.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="f0987-120">Vererbung</span><span class="sxs-lookup"><span data-stu-id="f0987-120">Inheritance</span></span>

 <span data-ttu-id="f0987-121">Die meisten Benutzer müssen nicht <xref:System.Collections.Generic.IEnumerable%601> implementieren, weshalb dieser Abschnitt ignoriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="f0987-121">Most users will not have to implement <xref:System.Collections.Generic.IEnumerable%601>, and can therefore ignore this section.</span></span>

 <span data-ttu-id="f0987-122">Die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft ist eine Erweiterungs Eigenschaft für Typen, die `IEnumerable(Of XElement)` implementieren.</span><span class="sxs-lookup"><span data-stu-id="f0987-122">The <xref:System.Xml.Linq.XElement.Value%2A> property is an extension property for types that implement `IEnumerable(Of XElement)`.</span></span> <span data-ttu-id="f0987-123">Die Bindung dieser Erweiterungs Eigenschaft ähnelt der Bindung von Erweiterungs Methoden: Wenn ein Typ eine der Schnittstellen implementiert und eine Eigenschaft mit dem Namen "Value" definiert, hat diese Eigenschaft Vorrang vor der Erweiterungs Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f0987-123">The binding of this extension property is like the binding of extension methods: if a type implements one of the interfaces and defines a property that has the name "Value", that property has precedence over the extension property.</span></span> <span data-ttu-id="f0987-124">Das heißt, dass diese <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft überschrieben werden kann, indem eine neue Eigenschaft in einer Klasse definiert wird, die `IEnumerable(Of XElement)` implementiert.</span><span class="sxs-lookup"><span data-stu-id="f0987-124">In other words, this <xref:System.Xml.Linq.XElement.Value%2A> property can be overridden by defining a new property in a class that implements `IEnumerable(Of XElement)`.</span></span>

## <a name="example"></a><span data-ttu-id="f0987-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0987-125">Example</span></span>

 <span data-ttu-id="f0987-126">Im folgenden Beispiel wird gezeigt, wie die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft verwendet wird, um auf den ersten Knoten in einer Auflistung von <xref:System.Xml.Linq.XElement>-Objekten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f0987-126">The following example shows how to use the <xref:System.Xml.Linq.XElement.Value%2A> property to access the first node in a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="f0987-127">Im Beispiel wird die-Eigenschaft der untergeordneten-Achse verwendet, um die Auflistung aller untergeordneten Knoten mit dem Namen `phone` zu erhalten, die sich im `contact`-Objekt befinden</span><span class="sxs-lookup"><span data-stu-id="f0987-127">The example uses the child axis property to get the collection of all child nodes named `phone` that are in the `contact` object.</span></span>

 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]

 <span data-ttu-id="f0987-128">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f0987-128">This code displays the following text:</span></span>

 `Phone number: 206-555-0144`

## <a name="example"></a><span data-ttu-id="f0987-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f0987-129">Example</span></span>

 <span data-ttu-id="f0987-130">Im folgenden Beispiel wird gezeigt, wie Sie den Wert eines XML-Attributs aus einer Auflistung von <xref:System.Xml.Linq.XAttribute>-Objekten erhalten.</span><span class="sxs-lookup"><span data-stu-id="f0987-130">The following example shows how to get the value of an XML attribute from a collection of <xref:System.Xml.Linq.XAttribute> objects.</span></span> <span data-ttu-id="f0987-131">Im Beispiel wird die Eigenschaft Attribut Achse verwendet, um den Wert des `type`-Attributs für alle `phone`-Elemente anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f0987-131">The example uses the attribute axis property to display the value of the `type` attribute for all of the `phone` elements.</span></span>

 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]

 <span data-ttu-id="f0987-132">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f0987-132">This code displays the following text:</span></span>

 ```console
 home
 work
```

## <a name="see-also"></a><span data-ttu-id="f0987-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0987-133">See also</span></span>

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="f0987-134">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="f0987-134">XML Axis Properties</span></span>](index.md)
- [<span data-ttu-id="f0987-135">XML-Literale</span><span class="sxs-lookup"><span data-stu-id="f0987-135">XML Literals</span></span>](../xml-literals/index.md)
- [<span data-ttu-id="f0987-136">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f0987-136">Creating XML in Visual Basic</span></span>](../../programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="f0987-137">Erweiterungsmethoden</span><span class="sxs-lookup"><span data-stu-id="f0987-137">Extension Methods</span></span>](../../programming-guide/language-features/procedures/extension-methods.md)
- [<span data-ttu-id="f0987-138">Erweiterungsindexereigenschaft</span><span class="sxs-lookup"><span data-stu-id="f0987-138">Extension Indexer Property</span></span>](extension-indexer-property.md)
- [<span data-ttu-id="f0987-139">Untergeordnete XML-Achseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="f0987-139">XML Child Axis Property</span></span>](xml-child-axis-property.md)
- [<span data-ttu-id="f0987-140">XML-Attributachseneigenschaft</span><span class="sxs-lookup"><span data-stu-id="f0987-140">XML Attribute Axis Property</span></span>](xml-attribute-axis-property.md)
