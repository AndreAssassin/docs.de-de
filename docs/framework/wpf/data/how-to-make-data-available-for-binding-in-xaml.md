---
title: 'Vorgehensweise: Bereitstellen von Daten für die Bindung in XAML'
ms.date: 01/29/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
ms.openlocfilehash: 2d51f06da31482c46b04d1eb86172c3eda246c20
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010305"
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a><span data-ttu-id="7252f-102">Vorgehensweise: Bereitstellen von Daten für die Bindung in XAML</span><span class="sxs-lookup"><span data-stu-id="7252f-102">How to: Make Data Available for Binding in XAML</span></span>
<span data-ttu-id="7252f-103">In diesem Thema wird erläutert, verschiedene Möglichkeiten, können Sie Daten verfügbar machen für die Bindung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]– je nach den Anforderungen Ihrer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7252f-103">This topic discusses various ways you can make data available for binding in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], depending on the needs of your application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7252f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7252f-104">Example</span></span>  
 <span data-ttu-id="7252f-105">Wenn Sie haben eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekt aus binden möchten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], eine Möglichkeit, Sie können das Objekt verfügbar machen, für die Bindung bezieht sich auf ihn als eine Ressource definieren und ihm eine `x:Key`.</span><span class="sxs-lookup"><span data-stu-id="7252f-105">If you have a [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] object you would like to bind to from [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], one way you can make the object available for binding is to define it as a resource and give it an `x:Key`.</span></span> <span data-ttu-id="7252f-106">Im folgenden Beispiel, Sie haben eine `Person` Objekt mit einer Zeichenfolgeneigenschaft, die mit dem Namen `PersonName`.</span><span class="sxs-lookup"><span data-stu-id="7252f-106">In the following example, you have a `Person` object with a string property named `PersonName`.</span></span> <span data-ttu-id="7252f-107">Die `Person` Objekt (in der Zeile, die markiert dargestellt, enthält die `<src>` Element) wird definiert, in dem Namespace namens `SDKSample`.</span><span class="sxs-lookup"><span data-stu-id="7252f-107">The `Person` object (in the line shown highlighted that contains the `<src>` element) is defined in the namespace called `SDKSample`.</span></span>  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 <span data-ttu-id="7252f-108">Anschließend können Sie binden die <xref:System.Windows.Controls.TextBlock> Steuerelement auf das Objekt im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], wie die hervorgehobene Zeile enthält die `<TextBlock>` Element zeigt.</span><span class="sxs-lookup"><span data-stu-id="7252f-108">You can then bind the <xref:System.Windows.Controls.TextBlock> control to the object in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], as the highlighted line that contains the `<TextBlock>` element shows.</span></span> 
  
 <span data-ttu-id="7252f-109">Alternativ können Sie die <xref:System.Windows.Data.ObjectDataProvider> -Klasse, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7252f-109">Alternatively, you can use the <xref:System.Windows.Data.ObjectDataProvider> class, as in the following example:</span></span>  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 <span data-ttu-id="7252f-110">Sie definieren die Bindung die gleiche Weise, wie die hervorgehobene Zeile mit der `<TextBlock>` Element zeigt.</span><span class="sxs-lookup"><span data-stu-id="7252f-110">You define the binding the same way, as the highlighted line that contains the `<TextBlock>` element shows.</span></span>  
  
 <span data-ttu-id="7252f-111">In diesem Beispiel ist das Ergebnis ist identisch: Sie haben eine <xref:System.Windows.Controls.TextBlock> mit dem Textinhalt `Joe`.</span><span class="sxs-lookup"><span data-stu-id="7252f-111">In this particular example, the result is the same: you have a <xref:System.Windows.Controls.TextBlock> with the text content `Joe`.</span></span> <span data-ttu-id="7252f-112">Allerdings die <xref:System.Windows.Data.ObjectDataProvider> -Klasse enthält Funktionen, z. B. die Möglichkeit zum Binden an das Ergebnis einer Methode.</span><span class="sxs-lookup"><span data-stu-id="7252f-112">However, the <xref:System.Windows.Data.ObjectDataProvider> class provides functionality such as the ability to bind to the result of a method.</span></span> <span data-ttu-id="7252f-113">Sie können auch mithilfe der <xref:System.Windows.Data.ObjectDataProvider> Klasse, wenn Sie die Funktionalität benötigen, bietet.</span><span class="sxs-lookup"><span data-stu-id="7252f-113">You can choose to use the <xref:System.Windows.Data.ObjectDataProvider> class if you need the functionality it provides.</span></span>  
  
 <span data-ttu-id="7252f-114">Jedoch, wenn Sie auf ein Objekt binden, die bereits erstellt wurde, müssen Sie legen die `DataContext` im Code, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7252f-114">However, if you are binding to an object that has already been created, you need to set the `DataContext` in code, as in the following example.</span></span>  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 <span data-ttu-id="7252f-115">Für den Zugriff auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung der <xref:System.Windows.Data.XmlDataProvider> Klasse, finden Sie unter [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span><span class="sxs-lookup"><span data-stu-id="7252f-115">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.XmlDataProvider> class, see [Bind to XML Data Using an XMLDataProvider and XPath Queries](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).</span></span> <span data-ttu-id="7252f-116">Für den Zugriff auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung der <xref:System.Windows.Data.ObjectDataProvider> Klasse, finden Sie unter [Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span><span class="sxs-lookup"><span data-stu-id="7252f-116">To access [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data for binding using the <xref:System.Windows.Data.ObjectDataProvider> class, see [Bind to XDocument, XElement, or LINQ for XML Query Results](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).</span></span>  
  
 <span data-ttu-id="7252f-117">Informationen zu viele Möglichkeiten, die Sie können angeben, die Daten, die Sie möchten binden, finden Sie [angeben der Bindungsquelle](how-to-specify-the-binding-source.md).</span><span class="sxs-lookup"><span data-stu-id="7252f-117">For information about many ways you can specify the data you are binding to, see [Specify the Binding Source](how-to-specify-the-binding-source.md).</span></span> <span data-ttu-id="7252f-118">Weitere Informationen welche Arten von Daten an Sie gebunden werden können und die Implementierungsweise einer eigenen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekte für die Bindung, finden Sie unter [Übersicht über Bindungsquellen](binding-sources-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7252f-118">For information about what types of data you can bind to or how to implement your own [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] objects for binding, see [Binding Sources Overview](binding-sources-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7252f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7252f-119">See also</span></span>

- [<span data-ttu-id="7252f-120">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="7252f-120">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="7252f-121">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="7252f-121">How-to Topics</span></span>](data-binding-how-to-topics.md)
