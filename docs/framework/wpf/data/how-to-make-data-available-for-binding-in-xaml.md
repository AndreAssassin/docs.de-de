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
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>Vorgehensweise: Bereitstellen von Daten für die Bindung in XAML
In diesem Thema wird erläutert, verschiedene Möglichkeiten, können Sie Daten verfügbar machen für die Bindung in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]– je nach den Anforderungen Ihrer Anwendung.  
  
## <a name="example"></a>Beispiel  
 Wenn Sie haben eine [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekt aus binden möchten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], eine Möglichkeit, Sie können das Objekt verfügbar machen, für die Bindung bezieht sich auf ihn als eine Ressource definieren und ihm eine `x:Key`. Im folgenden Beispiel, Sie haben eine `Person` Objekt mit einer Zeichenfolgeneigenschaft, die mit dem Namen `PersonName`. Die `Person` Objekt (in der Zeile, die markiert dargestellt, enthält die `<src>` Element) wird definiert, in dem Namespace namens `SDKSample`.  
  
 [!code-xaml[SimpleBinding#Instantiation](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Anschließend können Sie binden die <xref:System.Windows.Controls.TextBlock> Steuerelement auf das Objekt im [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], wie die hervorgehobene Zeile enthält die `<TextBlock>` Element zeigt. 
  
 Alternativ können Sie die <xref:System.Windows.Data.ObjectDataProvider> -Klasse, wie im folgenden Beispiel gezeigt:  
  
 [!code-xaml[ObjectDataProvider}](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml?highlight=10-14,42)]  
  
 Sie definieren die Bindung die gleiche Weise, wie die hervorgehobene Zeile mit der `<TextBlock>` Element zeigt.  
  
 In diesem Beispiel ist das Ergebnis ist identisch: Sie haben eine <xref:System.Windows.Controls.TextBlock> mit dem Textinhalt `Joe`. Allerdings die <xref:System.Windows.Data.ObjectDataProvider> -Klasse enthält Funktionen, z. B. die Möglichkeit zum Binden an das Ergebnis einer Methode. Sie können auch mithilfe der <xref:System.Windows.Data.ObjectDataProvider> Klasse, wenn Sie die Funktionalität benötigen, bietet.  
  
 Jedoch, wenn Sie auf ein Objekt binden, die bereits erstellt wurde, müssen Sie legen die `DataContext` im Code, wie im folgenden Beispiel gezeigt.  
  
 [!code-csharp[ADODataSet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 Für den Zugriff auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung der <xref:System.Windows.Data.XmlDataProvider> Klasse, finden Sie unter [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md). Für den Zugriff auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten für die Bindung der <xref:System.Windows.Data.ObjectDataProvider> Klasse, finden Sie unter [Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).  
  
 Informationen zu viele Möglichkeiten, die Sie können angeben, die Daten, die Sie möchten binden, finden Sie [angeben der Bindungsquelle](how-to-specify-the-binding-source.md). Weitere Informationen welche Arten von Daten an Sie gebunden werden können und die Implementierungsweise einer eigenen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Objekte für die Bindung, finden Sie unter [Übersicht über Bindungsquellen](binding-sources-overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
