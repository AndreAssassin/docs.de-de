---
title: Imports-Anweisung - XML-Namespace (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImportsXmlns
helpviewer_keywords:
- XML namespace [Visual Basic], importing
- imports [Visual Basic]
- Imports statement [Visual Basic]
- namespaces [Visual Basic], importing
ms.assetid: 1f4d50a6-08c7-4c2e-8206-ccae35fcd1b4
ms.openlocfilehash: 97d08113a37477add9d770b0a680c303fe7e3040
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841406"
---
# <a name="imports-statement-xml-namespace"></a><span data-ttu-id="34e56-102">Imports-Anweisung (XML-Namespace)</span><span class="sxs-lookup"><span data-stu-id="34e56-102">Imports Statement (XML Namespace)</span></span>
<span data-ttu-id="34e56-103">Importiert die XML-Namespacepräfixe für XML-Literale und XML-Achseneigenschaften.</span><span class="sxs-lookup"><span data-stu-id="34e56-103">Imports XML namespace prefixes for use in XML literals and XML axis properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34e56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34e56-104">Syntax</span></span>  
  
```  
Imports <xmlns:xmlNamespacePrefix = "xmlNamespaceName">  
```  
  
## <a name="parts"></a><span data-ttu-id="34e56-105">Teile</span><span class="sxs-lookup"><span data-stu-id="34e56-105">Parts</span></span>  
 `xmlNamespacePrefix`  
 <span data-ttu-id="34e56-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="34e56-106">Optional.</span></span> <span data-ttu-id="34e56-107">Die Zeichenfolge, die durch die XML-Elemente und Attribute verweisen auf `xmlNamespaceName`.</span><span class="sxs-lookup"><span data-stu-id="34e56-107">The string by which XML elements and attributes can refer to `xmlNamespaceName`.</span></span> <span data-ttu-id="34e56-108">Wenn kein `xmlNamespacePrefix` wird angegeben, wird der importierte XML-Namespace der XML-Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="34e56-108">If no `xmlNamespacePrefix` is supplied, the imported XML namespace is the default XML namespace.</span></span> <span data-ttu-id="34e56-109">Ein gültiger XML-Bezeichner muss sein.</span><span class="sxs-lookup"><span data-stu-id="34e56-109">Must be a valid XML identifier.</span></span> <span data-ttu-id="34e56-110">Weitere Informationen finden Sie unter [Namen von deklarierten XML-Elementen und Attributen](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="34e56-110">For more information, see [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md).</span></span>  
  
 `xmlNamespaceName`  
 <span data-ttu-id="34e56-111">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="34e56-111">Required.</span></span> <span data-ttu-id="34e56-112">Die Zeichenfolge, die Identifizieren des XML-Namespace importiert wird.</span><span class="sxs-lookup"><span data-stu-id="34e56-112">The string identifying the XML namespace being imported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="34e56-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="34e56-113">Remarks</span></span>  
 <span data-ttu-id="34e56-114">Können Sie die `Imports` Anweisung, um globale XML-Namespaces definieren, mit denen Sie mit XML-Literale und XML-Achseneigenschaften oder als Parameter übergeben, um die `GetXmlNamespace` Operator.</span><span class="sxs-lookup"><span data-stu-id="34e56-114">You can use the `Imports` statement to define global XML namespaces that you can use with XML literals and XML axis properties, or as parameters passed to the `GetXmlNamespace` operator.</span></span> <span data-ttu-id="34e56-115">(Informationen zur Verwendung der `Imports` Anweisung, um einen Alias zu importieren, die, in dem Typnamen verwendet werden, in Ihrem Code verwendet werden können, finden Sie unter [Imports-Anweisung (.NET-Namespace und Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) Die Syntax zum Deklarieren eines XML-Namespaces mithilfe der `Imports` -Anweisung ist identisch mit der Syntax, die im XML-Format verwendet.</span><span class="sxs-lookup"><span data-stu-id="34e56-115">(For information about using the `Imports` statement to import an alias that can be used where type names are used in your code, see [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).) The syntax for declaring an XML namespace by using the `Imports` statement is identical to the syntax used in XML.</span></span> <span data-ttu-id="34e56-116">Aus diesem Grund können Sie eine Namespacedeklaration aus einer XML-Datei kopieren und verwenden Sie ihn in ein `Imports` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="34e56-116">Therefore, you can copy a namespace declaration from an XML file and use it in an `Imports` statement.</span></span>  
  
 <span data-ttu-id="34e56-117">XML-Namespacepräfixe sind nützlich, wenn Sie wiederholt auf XML-Elemente erstellen, die aus dem gleichen Namespace sind möchten.</span><span class="sxs-lookup"><span data-stu-id="34e56-117">XML namespace prefixes are useful when you want to repeatedly create XML elements that are from the same namespace.</span></span> <span data-ttu-id="34e56-118">Das XML-Namespacepräfix deklariert, mit der `Imports` Anweisung ist global, in dem Sinne, dass sie auf den gesamten Code in der Datei verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="34e56-118">The XML namespace prefix declared with the `Imports` statement is global in the sense that it is available to all code in the file.</span></span> <span data-ttu-id="34e56-119">Sie können es verwenden, wenn Sie XML-Elementliteralen und beim Zugriff auf XML-Achseneigenschaften erstellen.</span><span class="sxs-lookup"><span data-stu-id="34e56-119">You can use it when you create XML element literals and when you access XML axis properties.</span></span> <span data-ttu-id="34e56-120">Weitere Informationen finden Sie unter [XML-Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) und [XML-Achseneigenschaften](../../../visual-basic/language-reference/xml-axis/index.md).</span><span class="sxs-lookup"><span data-stu-id="34e56-120">For more information, see [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md) and [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/index.md).</span></span>  
  
 <span data-ttu-id="34e56-121">Wenn Sie einen globalen XML-Namespace ohne ein Namespacepräfix zu definieren (z. B. `Imports <xmlns="http://SomeNameSpace>"`), diesen Namespace gilt den XML-Standardnamespace.</span><span class="sxs-lookup"><span data-stu-id="34e56-121">If you define a global XML namespace without a namespace prefix (for example, `Imports <xmlns="http://SomeNameSpace>"`), that namespace is considered the default XML namespace.</span></span> <span data-ttu-id="34e56-122">Der XML-Standardnamespace wird verwendet, für alle XML-Elementliteralen oder XML-Attribut-Achseneigenschaften, die nicht explizit einen Namespace angeben.</span><span class="sxs-lookup"><span data-stu-id="34e56-122">The default XML namespace is used for any XML element literals or XML attribute axis properties that do not explicitly specify a namespace.</span></span> <span data-ttu-id="34e56-123">Der Standardnamespace wird auch verwendet werden, wenn der angegebene Namespace der leere Namespace ist (d. h. `xmlns=""`).</span><span class="sxs-lookup"><span data-stu-id="34e56-123">The default namespace is also used if the specified namespace is the empty namespace (that is, `xmlns=""`).</span></span> <span data-ttu-id="34e56-124">Der XML-Standardnamespace gilt nicht, um XML-Attribute im XML-Literalen oder XML-Attribut-Achseneigenschaften, die nicht mit einen Namespace verfügen.</span><span class="sxs-lookup"><span data-stu-id="34e56-124">The default XML namespace does not apply to XML attributes in XML literals or to XML attribute axis properties that do not have a namespace.</span></span>  
  
 <span data-ttu-id="34e56-125">XML-Namespaces, die in einem XML-literal definiert werden die aufgerufen werden, *lokale XML-Namespaces*, haben Vorrang vor XML-Namespaces, die von definiert sind die `Imports` -Anweisung als global.</span><span class="sxs-lookup"><span data-stu-id="34e56-125">XML namespaces that are defined in an XML literal, which are called *local XML namespaces*, take precedence over XML namespaces that are defined by the `Imports` statement as global.</span></span> <span data-ttu-id="34e56-126">XML-Namespaces, die von definiert sind die `Imports` Anweisung haben Vorrang vor XML-Namespaces, die für ein Visual Basic-Projekt importiert.</span><span class="sxs-lookup"><span data-stu-id="34e56-126">XML namespaces that are defined by the `Imports` statement take precedence over XML namespaces imported for a Visual Basic project.</span></span> <span data-ttu-id="34e56-127">Wenn ein XML-Literal einen XML-Namespace definiert ist, gilt dieses lokale Namespace nicht für eingebettete Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="34e56-127">If an XML literal defines an XML namespace, that local namespace does not apply to embedded expressions.</span></span>  
  
 <span data-ttu-id="34e56-128">Globale XML-Namespaces, gelten dieselben Regeln einschränken und die Definition als .NET Framework-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="34e56-128">Global XML namespaces follow the same scoping and definition rules as .NET Framework namespaces.</span></span> <span data-ttu-id="34e56-129">Sie können daher einschließen einer `Imports` Anweisung, um einen globalen XML-Namespace definieren an einer beliebigen Stelle auf der Sie einen .NET Framework-Namespace importieren können.</span><span class="sxs-lookup"><span data-stu-id="34e56-129">As a result, you can include an `Imports` statement to define a global XML namespace anywhere you can import a .NET Framework namespace.</span></span> <span data-ttu-id="34e56-130">Dies schließt sowohl Codedateien und importierten Namespaces auf Projektebene.</span><span class="sxs-lookup"><span data-stu-id="34e56-130">This includes both code files and project-level imported namespaces.</span></span> <span data-ttu-id="34e56-131">Weitere Informationen zu importierten Namespaces auf Projektebene, finden Sie unter [Seite "Verweise", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="34e56-131">For information about project-level imported namespaces, see [References Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="34e56-132">Jede Quelldatei kann eine beliebige Anzahl von enthalten `Imports` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="34e56-132">Each source file can contain any number of `Imports` statements.</span></span> <span data-ttu-id="34e56-133">Diese müssen führen Sie die Option-Deklarationen, z. B. die `Option Strict` -Anweisung, und sie müssen vor stehen Programmierung Elementdeklarationen, z. B. `Module` oder `Class` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="34e56-133">These must follow option declarations, such as the `Option Strict` statement, and they must precede programming element declarations, such as `Module` or `Class` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34e56-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34e56-134">Example</span></span>  
 <span data-ttu-id="34e56-135">Das folgende Beispiel importiert eine XML-Standardnamespace und ein XML-Namespace identifiziert, mit dem Präfix `ns`.</span><span class="sxs-lookup"><span data-stu-id="34e56-135">The following example imports a default XML namespace and an XML namespace identified with the prefix `ns`.</span></span> <span data-ttu-id="34e56-136">Anschließend erstellt es ein XML-Literale, die beide Namespaces verwenden.</span><span class="sxs-lookup"><span data-stu-id="34e56-136">It then creates XML literals that use both namespaces.</span></span>  
  
 [!code-vb[VbXMLSamples#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/Module1.vb#45)]  
  
 <span data-ttu-id="34e56-137">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="34e56-137">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns="http://DefaultNamespace"   
          xmlns:ns="http://NewNamespace">  
  <ns:innerElement></ns:innerElement>  
  <siblingElement></siblingElement>  
  <innerElement />  
</ns:outer>  
```  
  
## <a name="example"></a><span data-ttu-id="34e56-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34e56-138">Example</span></span>  
 <span data-ttu-id="34e56-139">Das folgende Beispiel importiert die XML-Namespacepräfix `ns`.</span><span class="sxs-lookup"><span data-stu-id="34e56-139">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="34e56-140">Anschließend erstellt es ein XML-literal, das das Namespacepräfix verwendet, und zeigt die endgültige Form des Elements an.</span><span class="sxs-lookup"><span data-stu-id="34e56-140">It then creates an XML literal that uses the namespace prefix and displays the element's final form.</span></span>  
  
 [!code-vb[VbXMLSamples#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples10.vb#22)]  
  
 <span data-ttu-id="34e56-141">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="34e56-141">This code displays the following text:</span></span>  
  
```xml  
<ns:outer xmlns:ns="http://SomeNamespace">  
  <ns:middle xmlns:ns="http://NewNamespace">  
    <ns:inner1 />  
    <inner2 xmlns="http://SomeNamespace" />  
  </ns:middle>  
</ns:outer>  
```  
  
 <span data-ttu-id="34e56-142">Beachten Sie, dass der Compiler das XML-Namespacepräfix über ein globales Präfix in eine lokale Präfixdefinition konvertiert.</span><span class="sxs-lookup"><span data-stu-id="34e56-142">Notice that the compiler converted the XML namespace prefix from a global prefix to a local prefix definition.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34e56-143">Beispiel</span><span class="sxs-lookup"><span data-stu-id="34e56-143">Example</span></span>  
 <span data-ttu-id="34e56-144">Das folgende Beispiel importiert die XML-Namespacepräfix `ns`.</span><span class="sxs-lookup"><span data-stu-id="34e56-144">The following example imports the XML namespace prefix `ns`.</span></span> <span data-ttu-id="34e56-145">Anschließend wird mit dem Namespacepräfix ein XML-Literal erstellt und auf den ersten untergeordneten Knoten mit dem qualifizierten Namen `ns:name` zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="34e56-145">It then uses the prefix of the namespace to create an XML literal and access the first child node with the qualified name `ns:name`.</span></span>  
  
 [!code-vb[VbXMLSamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples8.vb#19)]  
  
 <span data-ttu-id="34e56-146">Durch diesen Code wird folgender Text angezeigt:</span><span class="sxs-lookup"><span data-stu-id="34e56-146">This code displays the following text:</span></span>  
  
 `Patrick Hines`  
  
## <a name="see-also"></a><span data-ttu-id="34e56-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34e56-147">See also</span></span>

- [<span data-ttu-id="34e56-148">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="34e56-148">XML Element Literal</span></span>](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [<span data-ttu-id="34e56-149">XML-Achseneigenschaften</span><span class="sxs-lookup"><span data-stu-id="34e56-149">XML Axis Properties</span></span>](../../../visual-basic/language-reference/xml-axis/index.md)
- [<span data-ttu-id="34e56-150">Namen von deklarierten XML-Elementen und Attributen</span><span class="sxs-lookup"><span data-stu-id="34e56-150">Names of Declared XML Elements and Attributes</span></span>](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
- [<span data-ttu-id="34e56-151">GetXmlNamespace-Operator</span><span class="sxs-lookup"><span data-stu-id="34e56-151">GetXmlNamespace Operator</span></span>](../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)
