---
title: Übersicht über Bindungsquellen
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], binding sources
- data binding [WPF], binding source
- binding sources [WPF]
ms.assetid: 2df2cd11-6aac-4bdf-ab7b-ea5f464cd5ca
ms.openlocfilehash: 72ef84cb53c6eff1fc2fb9459b40e780869243a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62023779"
---
# <a name="binding-sources-overview"></a>Übersicht über Bindungsquellen
Bei der Datenbindung verweist das Bindungsquellenobjekt auf das Objekt, aus dem Sie Daten abrufen. In diesem Thema werden die Objekttypen vorgestellt, die als Bindungsquelle verwendet werden können.  

<a name="binding_sources"></a>   
## <a name="binding-source-types"></a>Typen von Bindungsquellen  
 Bei der Datenbindung in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] werden die folgenden Typen von Bindungsquellen unterstützt:  
  
|Bindungsquelle|Beschreibung|  
|--------------------|-----------------|  
|[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Objekte|Sie können eine Bindung an die öffentlichen Eigenschaften, Untereigenschaften und Indexer aller [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]-Objekte herstellen. Die Bindungs-Engine verwendet die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Reflektion, um die Werte der Eigenschaften abzurufen. Sie können auch Objekte, die implementieren <xref:System.ComponentModel.ICustomTypeDescriptor> oder über einen registrierten <xref:System.ComponentModel.TypeDescriptionProvider> funktionieren auch mit der Bindungs-Engine.<br /><br /> Weitere Informationen zum Implementieren einer Klasse, die als Bindungsquelle dienen kann, finden Sie weiter unten in diesem Thema unter [Implementieren einer Klasse als Bindungsquelle](#classes).|  
|Dynamische Objekte|Sie können an verfügbare Eigenschaften und Indexer eines Objekts, das implementiert binden die <xref:System.Dynamic.IDynamicMetaObjectProvider> Schnittstelle. Wenn Sie auf den Member im Code zugreifen können, kann daran eine Bindung erfolgen. Wenn Sie z. B. mithilfe eines dynamischen Objekts auf einen Member im Code über `someObjet.AProperty` zugreifen können, können Sie durch Festlegen des Bindungspfads auf `AProperty` eine Bindung herstellen.|  
|[!INCLUDE[TLA#tla_adonet](../../../../includes/tlasharptla-adonet-md.md)]-Objekte|Sie können an binden [!INCLUDE[TLA2#tla_adonet](../../../../includes/tla2sharptla-adonet-md.md)] Objekte, z. B. <xref:System.Data.DataTable>. Die [!INCLUDE[TLA2#tla_adonet](../../../../includes/tla2sharptla-adonet-md.md)] <xref:System.Data.DataView> implementiert die <xref:System.ComponentModel.IBindingList> -Schnittstelle, die änderungsbenachrichtigungen bereitstellt, die die Bindungs-Engine überwacht.|  
|[!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]-Objekte|Sie binden und führen Sie `XPath` Abfragen für ein <xref:System.Xml.XmlNode>, <xref:System.Xml.XmlDocument>, oder <xref:System.Xml.XmlElement>. Eine bequeme Möglichkeit, Zugriff auf [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten, die Bindungsquelle im Markup ist die Verwendung einer <xref:System.Windows.Data.XmlDataProvider> Objekt. Weitere Informationen finden Sie unter [Binden an XML-Daten mithilfe von XMLDataProvider und XPath-Abfragen](how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).<br /><br /> Sie können auch zum Binden einer <xref:System.Xml.Linq.XElement> oder <xref:System.Xml.Linq.XDocument>, oder binden Sie an die Ergebnisse der Abfragen, die auf Objekte dieser Typen ausführen, indem Sie mit LINQ to XML. Ist eine bequeme Möglichkeit, LINQ to XML auf XML-Daten verwenden, die die Bindungsquelle im Markup ist die Verwendung einer <xref:System.Windows.Data.ObjectDataProvider> Objekt. Weitere Informationen finden Sie unter [Binden an XDocument, XElement oder LINQ für XML-Abfrageergebnisse](how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md).|  
|<xref:System.Windows.DependencyObject>-Objekte|Können Sie Bindung mit Abhängigkeitseigenschaften aller <xref:System.Windows.DependencyObject>. Ein Beispiel finden Sie unter [Binden der Eigenschaften von zwei Steuerelementen](how-to-bind-the-properties-of-two-controls.md).|  
  
<a name="classes"></a>   
## <a name="implementing-a-class-for-the-binding-source"></a>Implementieren einer Klasse als Bindungsquelle  
 Sie können eigene Bindungsquellen erstellen. In diesem Abschnitt erfahren Sie, wie Sie eine Klasse als Bindungsquelle implementieren.  
  
### <a name="providing-change-notifications"></a>Bereitstellen von Änderungsbenachrichtigungen  
 Wenn Sie entweder verwenden <xref:System.Windows.Data.BindingMode.OneWay> oder <xref:System.Windows.Data.BindingMode.TwoWay> Bindung (da Sie möchten Ihre [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] aktualisieren, wenn die Eigenschaften der Bindungsquelle dynamisch zu ändern), müssen Sie einen geeigneten Benachrichtigungsmechanismus implementieren. Die empfohlene Methode ist für die [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] oder die dynamische Klasse zum Implementieren der <xref:System.ComponentModel.INotifyPropertyChanged> Schnittstelle. Weitere Informationen finden Sie unter [Implementieren von Benachrichtigungen bei Eigenschaftenänderungen](how-to-implement-property-change-notification.md).  
  
 Bei der Erstellung einer [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] -Objekt, das nicht implementiert <xref:System.ComponentModel.INotifyPropertyChanged>, und klicken Sie dann Sie dafür sorgen, Ihr eigenes Benachrichtigungssystem dass müssen, um sicherzustellen, dass die in einer Bindung verwendeten Daten immer aktuell sind. Sie können Änderungsbenachrichtigungen bereitstellen, indem Sie das `PropertyChanged`-Muster für jede Eigenschaft unterstützen, für die Änderungsbenachrichtigungen ausgegeben werden sollen. Um dieses Muster zu unterstützen, definieren Sie für jede Eigenschaft ein *Name_der_EigenschaftChanged*-Ereignis, wobei *Name_der_Eigenschaft* der Name der jeweiligen Eigenschaft ist. Dieses Ereignis wird bei jeder Änderung der Eigenschaft ausgelöst.  
  
 Wenn die Bindungsquelle einen dieser Benachrichtigungsmechanismen implementiert, erfolgt die Aktualisierung des Ziels automatisch. Wenn aus irgendeinem Grund, der die Bindungsquelle nicht die richtige Eigenschaft bietet Benachrichtigungen geändert, müssen Sie die Option zum Verwenden der <xref:System.Windows.Data.BindingExpression.UpdateTarget%2A> Methode, um die Zieleigenschaft explizit aktualisieren.  
  
### <a name="other-characteristics"></a>Weitere Merkmale  
 In der folgenden Liste finden Sie weitere zu beachtende Punkte:  
  
- Wenn Sie das Objekt mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] erstellen möchten, muss die Klasse über einen Standardkonstruktor verfügen. In einigen [!INCLUDE[TLA2#tla_net](../../../../includes/tla2sharptla-net-md.md)] Sprachen wie z. B. C#, der Standardkonstruktor für Sie erstellt werden kann.  
  
- Die als Bindungsquelleigenschaften für eine Bindung verwendeten Eigenschaften müssen öffentliche Eigenschaften der Klasse sein. Explizit definierte Schnittstelleneigenschaften sowie geschützte, private, interne und virtuelle Eigenschaften können nicht für eine Bindung herangezogen werden.  
  
- An öffentliche Felder kann keine Bindung erfolgen.  
  
- Der in der Klasse deklarierte Eigenschaftentyp ist der an die Bindung übergebene Typ. Allerdings wird der letztendlich in der Bindung verwendete Typ durch die Eigenschaft des Bindungsziels und nicht durch die Bindungsquelleigenschaft bestimmt. Falls sich die Typen unterscheiden, können Sie ggf. einen Konverter erstellen, der vorgibt, wie die benutzerdefinierte Eigenschaft anfänglich an die Bindung übergeben wird. Weitere Informationen finden Sie unter <xref:System.Windows.Data.IValueConverter>.  
  
<a name="objects"></a>   
## <a name="using-entire-objects-as-a-binding-source"></a>Verwenden von gesamten Objekten als Bindungsquelle  
 Sie können das gesamte Objekt als Bindungsquelle verwenden. Sie können eine Bindungsquelle angeben, mit der <xref:System.Windows.Data.Binding.Source%2A> oder <xref:System.Windows.FrameworkElement.DataContext%2A> -Eigenschaft, und geben Sie dann auf eine leere Bindungsdeklaration: `{Binding}`. Diese Vorgehensweise eignet sich zum Beispiel für Szenarien, bei denen die Bindung an „string“-Objekte, an Objekte mit mehreren relevanten Eigenschaften oder an Auflistungsobjekte erfolgt. Ein Beispiel für die Bindung an ein gesamtes Auflistungsobjekt finden Sie unter [Verwenden des Master/Detail-Musters mit hierarchischen Daten](how-to-use-the-master-detail-pattern-with-hierarchical-data.md).  
  
 Beachten Sie, dass Sie ggf. benutzerdefinierte Logik anwenden müssen, damit die Daten für die gebundene Zieleigenschaft sinnvoll sind. Die benutzerdefinierte Logik möglicherweise im Formular für einen benutzerdefinierten Konverter (falls es sich um eine typkonvertierung standardmäßig nicht vorhanden ist) oder ein <xref:System.Windows.DataTemplate>. Weitere Informationen zu Konvertern finden Sie im Abschnitt „Datenkonvertierung“ in der [Übersicht über die Datenbindung](data-binding-overview.md). Weitere Informationen zu Datenvorlagen finden Sie in der [Übersicht über Datenvorlagen](data-templating-overview.md).  
  
<a name="collections"></a>   
## <a name="using-collection-objects-as-a-binding-source"></a>Verwenden von Auflistungsobjekten als Bindungsquelle  
 Häufig handelt es sich bei dem Objekt, das Sie verwenden möchten, um eine Auflistung benutzerdefinierter Objekte. Jedes Objekt fungiert als Quelle für eine Instanz einer wiederholten Bindung. So verfügen Sie vielleicht über eine `CustomerOrders`-Auflistung mit `CustomerOrder`-Objekten, die wiederholt von Ihrer Anwendung durchlaufen wird, um festzustellen, wie viele Bestellungen mit welchen Daten vorhanden sind.  
  
 Sie können jede Auflistung, die implementiert Auflisten der <xref:System.Collections.IEnumerable> Schnittstelle. Allerdings um dynamische Bindungen einzurichten, sodass einfügungen oder löschungen in der Sammlung aktualisieren die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] automatisch die Sammlung implementieren muss die <xref:System.Collections.Specialized.INotifyCollectionChanged> Schnittstelle. Diese Schnittstelle macht ein Ereignis verfügbar, das bei jeder Änderung der zugrunde liegenden Auflistung ausgelöst werden muss.  
  
 Die <xref:System.Collections.ObjectModel.ObservableCollection%601> Klasse ist die integrierte Implementierung einer datenauflistung, die verfügbar macht die <xref:System.Collections.Specialized.INotifyCollectionChanged> Schnittstelle. Die einzelnen Datenobjekte in der Auflistung müssen die zuvor beschriebenen Anforderungen erfüllen. Ein Beispiel finden Sie unter [Erstellen und Binden an ObservableCollection](how-to-create-and-bind-to-an-observablecollection.md). Bevor Sie eine eigene Auflistung implementieren, erwägen Sie <xref:System.Collections.ObjectModel.ObservableCollection%601> oder einer vorhandenen Sammlung Klassen, z. B. <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ObjectModel.Collection%601>, und <xref:System.ComponentModel.BindingList%601>, a.  
  
 WPF wird nie direkt an eine Auflistung gebunden. Wenn Sie eine Auflistung als Bindungsquelle angeben, wird WPF an die Standardansicht der Auflistung gebunden. Weitere Informationen zu Standardansichten finden Sie in der [Übersicht über die Datenbindung](data-binding-overview.md).  
  
 Wenn Sie ein erweitertes Szenario haben, und Sie Ihre eigene Auflistung implementieren möchten, sollten Sie verwenden die <xref:System.Collections.IList> Schnittstelle. <xref:System.Collections.IList> enthält eine nicht generische Auflistung von Objekten, die einzeln nach Index zugegriffen werden kann, die Leistung verbessern kann.  
  
<a name="permissions"></a>   
## <a name="permission-requirements-in-data-binding"></a>Berechtigungsanforderungen bei der Datenbindung  
 Bei der Datenbindung muss die Vertrauensebene der Anwendung beachtet werden. Die folgende Tabelle enthält eine Übersicht über die Eigenschaftstypen, mit denen in einer Anwendung, die mit voller oder teilweiser Vertrauenswürdigkeit ausgeführt wird, eine Bindung hergestellt werden kann:  
  
|Eigenschaftentyp<br /><br /> (alle Zugriffsmodifizierer)|Dynamische Objekteigenschaft|Dynamische Objekteigenschaft|CLR-Eigenschaft|CLR-Eigenschaft|Abhängigkeitseigenschaft|Abhängigkeitseigenschaft|  
|------------------------------------------------|-----------------------------|-----------------------------|------------------|------------------|-------------------------|-------------------------|  
|**Vertrauensebene**|**Volle Vertrauenswürdigkeit**|**Teilweise Vertrauenswürdigkeit**|**Volle Vertrauenswürdigkeit**|**Teilweise Vertrauenswürdigkeit**|**Volle Vertrauenswürdigkeit**|**Teilweise Vertrauenswürdigkeit**|  
|Öffentliche Klasse|Ja|Ja|Ja|Ja|Ja|Ja|  
|Nicht öffentliche Klasse|Ja|Nein|Ja|Nein|Ja|Ja|  
  
 In dieser Tabelle werden die folgenden wichtigen Punkte bezüglich der bei der Datenbindung erforderlichen Berechtigungen beschrieben:  
  
- Bei [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]-Eigenschaften funktioniert die Datenbindung, solange die Bindungs-Engine mittels Reflektion auf die Bindungsquelleigenschaft zugreifen kann. Andernfalls wird von der Bindungs-Engine eine Warnung ausgegeben, dass die Eigenschaft nicht gefunden wurde. In diesem Fall wird der Fallbackwert bzw. der Standardwert (sofern verfügbar) verwendet.  
  
- Sie können eine Bindung an Eigenschaften für dynamische Objekte herstellen, die zur Kompilier- oder Laufzeit definiert werden.  
  
- Eine Bindung an Abhängigkeitseigenschaften ist immer möglich.  
  
 Die erforderlichen Berechtigungen für [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]-Bindungen sind ähnlich. In einer teilweise vertrauenswürdigen Sandbox <xref:System.Windows.Data.XmlDataProvider> schlägt fehl, wenn sie nicht über die Berechtigungen zum Zugriff auf die angegebenen Daten verfügt.  
  
 Objekte mit einem anonymen Typ sind intern. Eine Bindung an Eigenschaften anonymer Typen kann nur bei der Ausführung mit voller Vertrauenswürdigkeit hergestellt werden. Weitere Informationen zu anonymen Typen finden Sie unter [Anonyme Typen (C#-Programmierhandbuch)](~/docs/csharp/programming-guide/classes-and-structs/anonymous-types.md) oder [Anonyme Typen (Visual Basic)](~/docs/visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
 Weitere Informationen zur Sicherheit bei teilweiser Vertrauenswürdigkeit finden Sie unter [WPF-Sicherheit mit teilweiser Vertrauenswürdigkeit](../wpf-partial-trust-security.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Data.ObjectDataProvider>
- <xref:System.Windows.Data.XmlDataProvider>
- [Angeben der Bindungsquelle](how-to-specify-the-binding-source.md)
- [Übersicht zur Datenbindung](data-binding-overview.md)
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
- [Übersicht über WPF-Datenbindung mit LINQ to XML](/visualstudio/designers/wpf-data-binding-with-linq-to-xml-overview)
- [Datenbindung](../advanced/optimizing-performance-data-binding.md)
