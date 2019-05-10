---
title: Namen von deklarierten XML-Elementen und Attributen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: dbe85b456f46c40c9cc9a703b38e11992edd24cf
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598276"
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a><span data-ttu-id="c5a7a-102">Namen von deklarierten XML-Elementen und Attributen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5a7a-102">Names of Declared XML Elements and Attributes (Visual Basic)</span></span>
<span data-ttu-id="c5a7a-103">Dieses Thema enthält die Visual Basic-Richtlinien für die Benennung von XML-Elemente und Attribute im XML-Literale.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-103">This topic provides Visual Basic guidelines for naming XML elements and attributes in XML literals.</span></span>  <span data-ttu-id="c5a7a-104">In einem XML-literal können Sie einen lokalen Namen oder ein qualifizierter Name angeben.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-104">In an XML literal, you can specify a local name or a qualified name.</span></span> <span data-ttu-id="c5a7a-105">Ein qualifizierter Name besteht aus einer XML-Namespacepräfix, einen Doppelpunkt und einem lokalen Namen.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-105">A qualified name consists of an XML namespace prefix, a colon, and a local name.</span></span> <span data-ttu-id="c5a7a-106">Weitere Informationen zu XML-Namespacepräfixe, finden Sie unter [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="c5a7a-106">For more information about XML namespace prefixes, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="rules"></a><span data-ttu-id="c5a7a-107">Regeln</span><span class="sxs-lookup"><span data-stu-id="c5a7a-107">Rules</span></span>  
 <span data-ttu-id="c5a7a-108">Ein lokaler Namen eines Elements oder Attributs in Visual Basic muss die folgenden Regeln entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-108">A local name of an element or attribute in Visual Basic must adhere to the following rules.</span></span>  
  
- <span data-ttu-id="c5a7a-109">Sie können mit einem Namespace beginnen.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-109">It can begin with a namespace.</span></span> <span data-ttu-id="c5a7a-110">Es muss mit einem Buchstaben oder einem Unterstrich beginnen (`_`).</span><span class="sxs-lookup"><span data-stu-id="c5a7a-110">It must begin with an alphabetical character or an underscore (`_`).</span></span>  
  
- <span data-ttu-id="c5a7a-111">Es darf nur Buchstaben, Dezimalziffern, Unterstriche, Punkte (.) und Bindestriche (-).</span><span class="sxs-lookup"><span data-stu-id="c5a7a-111">It must contain only alphabetical characters, decimal digits, underscores, periods (.), and hyphens (-).</span></span>  
  
- <span data-ttu-id="c5a7a-112">Es darf nicht mehr als 1.024 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-112">It must not be more than 1,024 characters long.</span></span>  
  
- <span data-ttu-id="c5a7a-113">Doppelpunkte, die im Namen angezeigt werden. Geben Sie Namespace demarkation an.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-113">Colons that appear in names indicate namespace demarcation.</span></span> <span data-ttu-id="c5a7a-114">Aus diesem Grund können Sie Doppelpunkte, nur für einen XML-Namespace für einen bestimmten Namen zu geben.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-114">Therefore, you can use colons only to specify an XML namespace for a particular name.</span></span>  
  
 <span data-ttu-id="c5a7a-115">Darüber hinaus sollte die folgenden Richtlinien eingehalten werden.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-115">In addition, you should adhere to the following guideline.</span></span>  
  
- <span data-ttu-id="c5a7a-116">Die XML 1.0-Spezifikation reserviert alle Namen, die mit der Zeichenfolge "Xml", der eine Variante der Schreibweise ab.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-116">The XML 1.0 specification reserves all names starting with the string "xml", of any capitalization variation.</span></span> <span data-ttu-id="c5a7a-117">Verwenden Sie daher nicht die Namen für das Element und dem Attributnamen.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-117">Therefore, do not use those names for your element and attribute names.</span></span>  
  
### <a name="name-length-guidelines"></a><span data-ttu-id="c5a7a-118">Richtlinien zur Länge von Namen</span><span class="sxs-lookup"><span data-stu-id="c5a7a-118">Name Length Guidelines</span></span>  
 <span data-ttu-id="c5a7a-119">Ein praktischer Tipp sollte ein Name und die Art des Elements immer noch eindeutig kennzeichnen so kurz wie möglich sein.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-119">As a practical matter, a name should be as short as possible while still clearly identifying the nature of the element.</span></span> <span data-ttu-id="c5a7a-120">Dies verbessert die Lesbarkeit des Codes und die Länge und die Quelldatei Größe reduziert.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-120">This improves the readability of your code and reduces line length and source-file size.</span></span>  
  
 <span data-ttu-id="c5a7a-121">Ihr Name sollte jedoch nicht so kurz sein, dass es nicht angemessen beschrieben werden, das Element oder wie Ihr Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-121">However, your name should not be so short that it does not adequately describe the element or how your code uses it.</span></span> <span data-ttu-id="c5a7a-122">Dies ist wichtig für die Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-122">This is important for the readability of your code.</span></span> <span data-ttu-id="c5a7a-123">Wenn eine andere Person versucht, eine klare Vorstellung davon haben, oder wenn Sie sich an sind viel Zeit nach dessen Erstellung, können die entsprechenden Elementnamen Zeit sparen.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-123">If somebody else is trying to understand it, or if you yourself are looking at it a long time after you wrote it, appropriate element names can save time.</span></span>  
  
## <a name="case-sensitivity-in-names"></a><span data-ttu-id="c5a7a-124">Groß-/Kleinschreibung in Namen</span><span class="sxs-lookup"><span data-stu-id="c5a7a-124">Case Sensitivity in Names</span></span>  
 <span data-ttu-id="c5a7a-125">XML-Elementnamen sind Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-125">XML element names are case sensitive.</span></span> <span data-ttu-id="c5a7a-126">Dies bedeutet, dass wenn Visual Basic-Compiler zwei Namen, die nur die Groß-und Kleinschreibung unterscheiden vergleicht, werden als unterschiedliche Namen interpretiert.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-126">This means that when the Visual Basic compiler compares two names that differ in alphabetical case only, it interprets them as different names.</span></span> <span data-ttu-id="c5a7a-127">Z. B. interpretiert `ABC` und `abc` als Verweise auf verschiedene Elemente.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-127">For example, it interprets `ABC` and `abc` as referring to separate elements.</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="c5a7a-128">XML-Namespaces</span><span class="sxs-lookup"><span data-stu-id="c5a7a-128">XML Namespaces</span></span>  
 <span data-ttu-id="c5a7a-129">Wenn ein XML-Elementliteral erstellen, können Sie das XML-Namespacepräfix für den Elementnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="c5a7a-129">When creating an XML element literal, you can specify the XML namespace prefix for the element name.</span></span> <span data-ttu-id="c5a7a-130">Weitere Informationen finden Sie unter [XML-Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span><span class="sxs-lookup"><span data-stu-id="c5a7a-130">For more information, see [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5a7a-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5a7a-131">See also</span></span>

- [<span data-ttu-id="c5a7a-132">Erstellen von XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c5a7a-132">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [<span data-ttu-id="c5a7a-133">XML-Elementliteral</span><span class="sxs-lookup"><span data-stu-id="c5a7a-133">XML Element Literal</span></span>](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
