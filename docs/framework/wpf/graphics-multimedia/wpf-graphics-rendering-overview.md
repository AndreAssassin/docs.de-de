---
title: Übersicht über das WPF-Grafikrendering
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rendering
- rendering graphics [WPF]
ms.assetid: 6dec9657-4d8c-4e46-8c54-40fb80008265
ms.openlocfilehash: ea219d653e6f41f9ebeceb8f33803ebb9246d8bb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962860"
---
# <a name="wpf-graphics-rendering-overview"></a>Übersicht über das WPF-Grafikrendering
Das Thema bietet einen Überblick über die visuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Schicht. Der Schwerpunkt liegt auf der Rolle <xref:System.Windows.Media.Visual> der-Klasse für das Rendern von Unterstützung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] im Modell.  

<a name="role_of_visual_object"></a>   
## <a name="role-of-the-visual-object"></a>Rolle des visuellen Objekts  
 Die <xref:System.Windows.Media.Visual> -Klasse ist die Basis Abstraktion, von <xref:System.Windows.FrameworkElement> der jedes Objekt abgeleitet wird. Sie dient auch als Einstiegspunkt zum Schreiben neuer Steuerelemente [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und kann in vielerlei Hinsicht als Fensterhandle (HWND) im Win32-Anwendungsmodell betrachtet werden.  
  
 Bei <xref:System.Windows.Media.Visual> dem Objekt handelt es [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sich um ein Kern Objekt, dessen primäre Rolle die Unterstützung von Rendering bereitstellt. Steuerelemente der Benutzeroberfläche, <xref:System.Windows.Controls.Button> z <xref:System.Windows.Controls.TextBox>. b. und <xref:System.Windows.Media.Visual> , werden von der-Klasse abgeleitet und zum Speichern ihrer Renderingdaten verwendet. Das <xref:System.Windows.Media.Visual> -Objekt bietet Unterstützung für:  
  
- Ausgabe Anzeige: Rendern des beibehaltenen, serialisierten Zeichnungs Inhalts eines visuellen Elements.  
  
- Beziehen Ausführen von Transformationen in einem visuellen Element.  
  
- Clipping Bereitstellen von Clipping-Regions Unterstützung für ein visuelles Element.  
  
- Treffer Tests: Bestimmen, ob eine Koordinate oder Geometrie innerhalb der Grenzen eines visuellen Elements enthalten ist.  
  
- Begrenzungsfeld Berechnungen: Bestimmen des umgebenden Rechtecks eines visuellen Elements.  
  
 Das <xref:System.Windows.Media.Visual> -Objekt beinhaltet jedoch keine Unterstützung für nicht-Renderingfeatures, wie z. b.:  
  
- Ereignisbehandlung  
  
- Layout  
  
- Stile  
  
- Datenbindung  
  
- Globalisierung  
  
 <xref:System.Windows.Media.Visual>wird als öffentliche abstrakte Klasse verfügbar gemacht, von der untergeordnete Klassen abgeleitet werden müssen. Die folgende Abbildung zeigt die Hierarchie der visuellen Objekte, die in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügbar gemacht werden.  
  
 ![Diagramm der vom Visual-Objekt abgeleiteten Klassen](./media/wpf-graphics-rendering-overview/classes-derived-visual-object.png)    
  
### <a name="drawingvisual-class"></a>DrawingVisual-Klasse  
 <xref:System.Windows.Media.DrawingVisual> Ist eine vereinfachte Zeichnungs Klasse, die zum Rendering von Formen, Bildern oder Text verwendet wird. Diese Klasse wird als einfach angesehen, da sie keine Layout- oder Ereignisbehandlung bereitstellt, was die Laufzeitleistung verbessert. Aus diesem Grund sind Zeichnungen für Hintergründe und ClipArt ideal. <xref:System.Windows.Media.DrawingVisual> Kann verwendet werden, um ein benutzerdefiniertes visuelles Objekt zu erstellen. Weitere Informationen finden Sie unter [Verwenden von DrawingVisual-Objekten](using-drawingvisual-objects.md).  
  
### <a name="viewport3dvisual-class"></a>Viewport3DVisual-Klasse  
 Stellt eine Brücke zwischen 2D- <xref:System.Windows.Media.Visual> und <xref:System.Windows.Media.Media3D.Visual3D> -Objekten bereit. <xref:System.Windows.Media.Media3D.Viewport3DVisual> Die <xref:System.Windows.Media.Media3D.Visual3D> -Klasse ist die Basisklasse für alle visuellen 3D-Elemente. Erfordert, dass Sie einen <xref:System.Windows.Media.Media3D.Viewport3DVisual.Camera%2A> -Wert und einen <xref:System.Windows.Media.Media3D.Viewport3DVisual.Viewport%2A> -Wert definieren. <xref:System.Windows.Media.Media3D.Viewport3DVisual> Die Kamera ermöglicht die Anzeige der Szene. Der Anzeigebereich legt fest, wo die Projektion auf der 2D-Fläche zuordnet. Weitere Informationen über 3D in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] finden Sie unter [Übersicht über 3D-Grafiken](3-d-graphics-overview.md).  
  
### <a name="containervisual-class"></a>ContainerVisual-Klasse  
 Die <xref:System.Windows.Media.ContainerVisual> -Klasse wird als Container für eine Auflistung von <xref:System.Windows.Media.Visual> -Objekten verwendet. Die <xref:System.Windows.Media.DrawingVisual> -Klasse wird von <xref:System.Windows.Media.ContainerVisual> der-Klasse abgeleitet, sodass Sie eine Auflistung visueller Objekte enthalten kann.  
  
### <a name="drawing-content-in-visual-objects"></a>Zeichnungsinhalt in visuellen Objekten  
 Ein <xref:System.Windows.Media.Visual> -Objekt speichert seine Renderdaten als eine **Vektorgrafik Anweisungs Liste**. Jedes Element in der Anweisungsliste stellt einen Satz von Grafikdaten einer niedrigeren Ebene und dazugehörige Ressourcen in einem serialisierten Format dar. Es gibt vier verschiedene Typen von Renderingdaten, die Zeichnungsinhalt enthalten können.  
  
|Zeichnungsinhaltstyp|Beschreibung|  
|--------------------------|-----------------|  
|Vektorgrafik|Stellt Vektorgrafik Daten und alle zugeordneten <xref:System.Windows.Media.Brush> - <xref:System.Windows.Media.Pen> und-Informationen dar.|  
|Bild|Stellt ein Bild innerhalb eines von <xref:System.Windows.Rect>definierten Bereichs dar.|  
|Glyphe|Stellt eine Zeichnung dar, die <xref:System.Windows.Media.GlyphRun>eine rendert, bei der es sich um eine Sequenz von Symbolen aus einer angegebenen Schriftart Ressource handelt. So wird Text dargestellt.|  
|Video|Stellt eine Zeichnung dar, die Video rendert.|  
  
 Mit <xref:System.Windows.Media.DrawingContext> dem können Sie eine <xref:System.Windows.Media.Visual> mit visuellen Inhalten auffüllen. Wenn Sie die Draw <xref:System.Windows.Media.DrawingContext> -Befehle eines-Objekts verwenden, speichern Sie tatsächlich eine Reihe von Renderingdaten, die später vom Grafiksystem verwendet werden. Sie werden nicht in Echtzeit auf den Bildschirm gezeichnet.  
  
 Wenn Sie ein [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelement erstellen, z. <xref:System.Windows.Controls.Button>b. ein, generiert das Steuerelement implizit Rendering-Daten für das Zeichnen. Beispielsweise <xref:System.Windows.Controls.Button> bewirkt das Festlegen <xref:System.Windows.Controls.ContentControl.Content%2A> der-Eigenschaft von, dass das-Steuerelement eine Renderingdarstellung eines Symbols speichert.  
  
 Ein <xref:System.Windows.Media.Visual> beschreibt seinen Inhalt als ein oder mehrere <xref:System.Windows.Media.Drawing> -Objekte, die <xref:System.Windows.Media.DrawingGroup>in einem enthalten sind. <xref:System.Windows.Media.DrawingGroup> Außerdem werden Deck Kraft Masken, Transformationen, Bitmapeffekte und andere Vorgänge beschrieben, die auf den Inhalt angewendet werden. <xref:System.Windows.Media.DrawingGroup>Vorgänge werden in der folgenden Reihenfolge angewendet, wenn der Inhalt <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>gerendert <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>wird <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>:, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.Transform%2A> <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>,, und dann.  
  
 Die folgende Abbildung zeigt die Reihenfolge, <xref:System.Windows.Media.DrawingGroup> in der Vorgänge während der Renderingsequenz angewendet werden.  
  
 ![DrawingGroup-Reihenfolge der Vorgänge](./media/graphcismm-drawinggroup-order.png "graphcismm_drawinggroup_order")  
Reihenfolge der DrawingGroup-Vorgänge  
  
 Weitere Informationen finden Sie unter [Übersicht über Zeichnungsobjekte](drawing-objects-overview.md).  
  
#### <a name="drawing-content-at-the-visual-layer"></a>Zeichnungsinhalt auf Ebene des visuellen Objekts  
 Sie können niemals direkt instanziieren <xref:System.Windows.Media.DrawingContext>. Sie können jedoch einen Zeichnungs Kontext von bestimmten Methoden abrufen, <xref:System.Windows.Media.DrawingGroup.Open%2A?displayProperty=nameWithType> z. b. und <xref:System.Windows.Media.DrawingVisual.RenderOpen%2A?displayProperty=nameWithType>. Im folgenden Beispiel wird ein <xref:System.Windows.Media.DrawingContext> aus einem <xref:System.Windows.Media.DrawingVisual> abgerufen und zum Zeichnen eines Rechtecks verwendet.  
  
 [!code-csharp[drawingvisualsample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingVisualSample/CSharp/Window1.xaml.cs#101)]
 [!code-vb[drawingvisualsample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DrawingVisualSample/visualbasic/window1.xaml.vb#101)]  
  
#### <a name="enumerating-drawing-content-at-the-visual-layer"></a>Auflisten des Zeichnungsinhalts auf der Ebene eines visuellen Objekts  
 Zusätzlich zu den anderen Verwendungsmöglichkeiten <xref:System.Windows.Media.Drawing> stellen-Objekte auch ein Objektmodell für das Auflisten des Inhalts <xref:System.Windows.Media.Visual>von bereit.  
  
> [!NOTE]
> Wenn Sie den Inhalt der Visualisierung auflisten, rufen Sie <xref:System.Windows.Media.Drawing> Objekte ab, und nicht die zugrunde liegende Darstellung der Renderingdaten als Liste von Vektorgrafik Anweisungs Listen.  
  
 Im folgenden Beispiel wird die <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> <xref:System.Windows.Media.Visual> -Methode verwendet, <xref:System.Windows.Media.DrawingGroup> um den Wert eines abzurufen und ihn aufzulisten.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
<a name="how_visual_objects_are_used_to_build_controls"></a>   
## <a name="how-visual-objects-are-used-to-build-controls"></a>Verwenden von visuellen Objekten zum Erstellen von Steuerelementen  
 Viele der Objekte in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bestehen aus anderen visuellen Objekten, d.h., sie können unterschiedliche Hierarchien von untergeordneten Objekten enthalten. Viele Benutzeroberflächenelemente in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], z.B. Steuerelemente, bestehen aus mehreren visuellen Objekten, die unterschiedliche Typen von Renderingelementen darstellen. Das <xref:System.Windows.Controls.Button> -Steuerelement kann beispielsweise eine Reihe anderer-Objekte enthalten, <xref:Microsoft.Windows.Themes.ClassicBorderDecorator>einschließlich <xref:System.Windows.Controls.ContentPresenter>, und <xref:System.Windows.Controls.TextBlock>.  
  
 Der folgende Code zeigt ein <xref:System.Windows.Controls.Button> im Markup definiertes Steuerelement.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet1)]  
  
 Wenn Sie die visuellen Objekte auflisten, die das Standard <xref:System.Windows.Controls.Button> Steuerelement bilden, finden Sie die unten dargestellte Hierarchie von visuellen Objekten:  
  
 ![Diagramm der visuellen Strukturhierarchie](./media/wpf-graphics-rendering-overview/visual-object-diagram.gif) 
  
 Das <xref:System.Windows.Controls.Button> -Steuerelement <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> enthält ein-Element, das wiederum ein <xref:System.Windows.Controls.ContentPresenter> -Element enthält. Das <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> -Element ist für das Zeichnen eines Rahmens und eines Hintergrunds <xref:System.Windows.Controls.Button>für das verantwortlich. Das <xref:System.Windows.Controls.ContentPresenter> -Element ist dafür verantwortlich, den Inhalt <xref:System.Windows.Controls.Button>von anzuzeigen. In diesem Fall enthält das <xref:System.Windows.Controls.ContentPresenter> -Element ein <xref:System.Windows.Controls.TextBlock> -Element, da Sie Text anzeigen. Die Tatsache, dass <xref:System.Windows.Controls.Button> das Steuerelement <xref:System.Windows.Controls.ContentPresenter> einen verwendet, bedeutet, dass der Inhalt durch andere Elemente dargestellt werden kann <xref:System.Windows.Controls.Image> , z. b. eine oder <xref:System.Windows.Media.EllipseGeometry>eine Geometrie, z. b. ein.  
  
### <a name="control-templates"></a>Steuerelementvorlagen  
 Der Schlüssel zur Erweiterung eines Steuer Elements in eine Hierarchie von Steuerelementen ist <xref:System.Windows.Controls.ControlTemplate>die. Eine Steuerelementvorlage gibt die visuelle Standardhierarchie für ein Steuerelement an. Wenn Sie explizit auf ein Steuerelement verweisen, verweisen Sie implizit auf dessen visuelle Hierarchie. Sie können die Standardwerte für eine Steuerelementvorlage überschreiben, um eine angepasste visuelle Darstellung für ein Steuerelement zu erstellen. Beispielsweise können Sie den Wert für die Hintergrundfarbe des <xref:System.Windows.Controls.Button> -Steuer Elements so ändern, dass ein linearer Farbverlaufs Farbwert anstelle eines voll tonfarbwerts verwendet wird. Weitere Informationen finden Sie unter [Button-Stile und Vorlagen](../controls/button-styles-and-templates.md).  
  
 Ein Benutzeroberflächen Element, z. b <xref:System.Windows.Controls.Button> . ein-Steuerelement, enthält mehrere Vektorgrafik Anweisungs Listen, die die gesamte Renderingdefinition eines-Steuer Elements beschreiben. Der folgende Code zeigt ein <xref:System.Windows.Controls.Button> im Markup definiertes Steuerelement.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet2)]  
  
 Wenn Sie die Listen der visuellen Objekte und der Vektorgrafik Anweisung auflisten, die das <xref:System.Windows.Controls.Button> Steuerelement enthalten, finden Sie die unten dargestellte Hierarchie von Objekten:  
  
 ![Diagramm der visuellen Struktur und des Renderings von Daten](./media/wpf-graphics-rendering-overview/visual-tree-rendering-data.png)  
  
 Das <xref:System.Windows.Controls.Button> -Steuerelement <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> enthält ein-Element, das wiederum ein <xref:System.Windows.Controls.ContentPresenter> -Element enthält. Das <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> -Element ist für das Zeichnen aller einzelnen Grafikelemente verantwortlich, die den Rahmen und den Hintergrund einer Schaltfläche bilden. Das <xref:System.Windows.Controls.ContentPresenter> -Element ist dafür verantwortlich, den Inhalt <xref:System.Windows.Controls.Button>von anzuzeigen. In diesem Fall enthält das <xref:System.Windows.Controls.ContentPresenter> -Element ein <xref:System.Windows.Controls.Image> -Element, da Sie ein Bild anzeigen.  
  
 Es gibt mehrere Dinge im Zusammenhang mit der Hierarchie von visuellen Objekten und Anweisungslisten für Vektorgrafiken zu beachten:  
  
- Die Reihenfolge in der Hierarchie stellt die Renderingreihenfolge der Zeichnungsinformationen dar. Aus dem visuellen Stammelement werden untergeordnete Elemente von links nach rechts und von oben nach unten durchlaufen. Wenn ein Element über visuelle untergeordnete Elemente verfügt, werden diese vor den gleichgeordneten Elementen des Elements durchlaufen.  
  
- Nicht Blattknoten Elemente in der Hierarchie, wie z <xref:System.Windows.Controls.ContentPresenter>. b., werden verwendet, um untergeordnete Elemente zu enthalten – Sie enthalten keine Anweisungs Listen.  
  
- Wenn ein visuelles Element eine Anweisungsliste für Vektorgrafiken und visuelle untergeordnete Elemente enthält, wird die Anweisungsliste im übergeordneten visuellen Element vor Zeichnungen in einem der untergeordneten visuellen Objekte gerendert.  
  
- Die Elemente in der Anweisungsliste für Vektorgrafiken werden von links nach rechts gerendert.  
  
<a name="visual_tree"></a>   
## <a name="visual-tree"></a>Visuelle Struktur  
 Die visuelle Struktur enthält alle visuellen Elemente, die in der Benutzeroberfläche einer Anwendung verwendet werden. Da ein visuelles Element persistent gespeicherte Zeichnungsinformationen enthält, können Sie sich die visuelle Struktur als Szenengraph vorstellen, der alle Renderinginformationen enthält, die erforderlich sind, um die Ausgabe auf dem Anzeigegerät zu erstellen. Diese Struktur ist die Ansammlung aller visuellen Elemente, die direkt von der Anwendung im Code oder im Markup erstellt werden. Die visuelle Struktur enthält auch alle visuellen Elemente, die von der Vorlagenerweiterung der Elemente, wie z.B. Steuerelemente und Datenobjekte, erstellt werden.  
  
 Der folgende Code zeigt ein <xref:System.Windows.Controls.StackPanel> -Element, das in Markup definiert ist.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet3](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet3)]  
  
 Wenn Sie die visuellen Objekte auflisten möchten, aus denen das <xref:System.Windows.Controls.StackPanel> -Element im Markup Beispiel besteht, finden Sie die unten dargestellte Hierarchie von visuellen Objekten:  
  
 ![Diagramm der visuellen Strukturhierarchie](./media/wpf-graphics-rendering-overview/visual-tree-hierarchy.gif)  
  
### <a name="rendering-order"></a>Renderingreihenfolge  
 Die visuelle Struktur bestimmt die Renderingreihenfolge der visuellen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] und Zeichnungsobjekte. Die Reihenfolge des Durchlaufs beginnt mit dem visuellen Stammelement, das der oberste Knoten in der visuellen Struktur ist. Die untergeordnete Elemente des visuellen Stammelements werden von links nach rechts durchlaufen. Wenn ein visuelles Objekt über untergeordnete Elemente verfügt, werden seine untergeordneten Elemente vor den gleichgeordneten visuellen Elementen durchlaufen. Dies bedeutet, dass der Inhalt eines untergeordneten visuellen Objekts vor dem Inhalt des visuellen Objekts selbst gerendert wird.  
  
 ![Diagramm der visuellen Struktur-Rendering-Reihenfolge](./media/wpf-graphics-rendering-overview/visual-tree-rendering-order.gif) 
  
### <a name="root-visual"></a>Visuelles Stammobjekt  
 Das **visuelle Stammobjekt** ist das oberste Element in der Hierarchie einer visuellen Struktur. In den meisten Anwendungen ist die Basisklasse der visuellen Stamm Visualisierung entweder <xref:System.Windows.Window> oder <xref:System.Windows.Navigation.NavigationWindow>. Wenn Sie jedoch visuelle Objekte in einer Win32-Anwendung hosten, ist das visuelle Stammobjekt das oberste visuelle Objekt, das Sie im Win32-Fenster hosten. Weitere Informationen finden Sie unter [Tutorial: Hosting von visuellen Objekten in einer Win32](tutorial-hosting-visual-objects-in-a-win32-application.md)-Anwendung.  
  
### <a name="relationship-to-the-logical-tree"></a>Beziehung zur logischen Struktur  
 Die logische Struktur in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt die Elemente einer Anwendung zur Laufzeit dar. Obwohl Sie die Struktur nicht direkt bearbeiten, ist diese Ansicht der Anwendung nützlich, um die Vererbung von Eigenschaften und das Ereignisrouting nachzuvollziehen. Anders als <xref:System.Windows.Documents.ListItem>bei der visuellen Struktur kann die logische Struktur nicht visuelle Datenobjekte, wie z. b., darstellen. In vielen Fällen ist die logische Struktur eng an die Markupdefinitionen einer Anwendung angelehnt. Der folgende Code zeigt ein <xref:System.Windows.Controls.DockPanel> -Element, das in Markup definiert ist.  
  
 [!code-xaml[VisualsOverview#VisualsOverviewSnippet5](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml#visualsoverviewsnippet5)]  
  
 Wenn Sie die logischen Objekte auflisten möchten, aus denen das <xref:System.Windows.Controls.DockPanel> -Element im Markup Beispiel besteht, finden Sie die unten dargestellte Hierarchie von logischen Objekten:  
  
 Struktur ![Diagramm](./media/tree1-wcp.gif "Tree1_wcp")  
Diagramm der logischen Struktur  
  
 Die visuelle Struktur und die logische Struktur werden mit dem aktuellen Satz von Anwendungselementen synchronisiert und spiegeln dabei alle Hinzufügungen, Löschungen oder Änderungen von Elementen wider. Die Strukturen liefern jedoch verschiedene Ansichten der Anwendung. Anders als bei der visuellen Struktur, erweitert die logische Struktur nicht das- <xref:System.Windows.Controls.ContentPresenter> Element eines Steuer Elements. Dies bedeutet, dass keine direkte 1:1-Entsprechung zwischen einer logischen Struktur und einer visuellen Struktur für den gleichen Satz von Objekten vorhanden ist. Tatsächlich führt das Aufrufen der- <xref:System.Windows.LogicalTreeHelper.GetChildren%2A> Methode des **LogicalTreeHelper** -Objekts und der-Methode des **VisualTreeHelper** -Objekts, die das gleiche- <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> Element wie ein-Parameter verwendet, zu unterschiedlichen Ergebnissen.  
  
 Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](../advanced/trees-in-wpf.md).  
  
### <a name="viewing-the-visual-tree-with-xamlpad"></a>Anzeigen der visuellen Struktur mit XamlPad  
 Das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Tool XamlPad bietet eine Option zum Anzeigen und Durchsuchen der visuellen Struktur, die dem aktuell definierten [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]-Inhalt entspricht. Klicken Sie auf die Schaltfläche **Visuelle Struktur anzeigen** der Menüleiste, um die visuelle Struktur anzuzeigen. Im Folgenden wird die Erweiterung des [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]-Inhalts in Knoten in der visuellen Struktur im Panel **Visueller Struktur-Explorer**-Bereich in XamlPad veranschaulicht:  
  
 ![Visueller Struktur-Explorer-Bereich in XamlPad](./media/wpf-graphics-rendering-overview/visual-tree-explorer.png)  

 Beachten Sie, <xref:System.Windows.Controls.Label>dass <xref:System.Windows.Controls.TextBox>die Steuer <xref:System.Windows.Controls.Button> Elemente, und jeweils eine separate visuelle Objekthierarchie im **Visual Tree Explorer** -Panel von XamlPad anzeigen. Dies liegt daran [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , dass Steuer <xref:System.Windows.Controls.ControlTemplate> Elemente über einen verfügen, der die visuelle Struktur dieses Steuer Elements enthält. Wenn Sie explizit auf ein Steuerelement verweisen, verweisen Sie implizit auf dessen visuelle Hierarchie.  
  
### <a name="profiling-visual-performance"></a>Erstellung von visuellen Leistungsprofilen  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] stellt eine Suite von Leistungsprofilerstellungstools bereit, mit deren Hilfe Sie das Laufzeitverhalten der Anwendung analysieren und die Typen der anwendbaren Leistungsoptimierungen bestimmen können. Das Visual Profiler-Tool bietet eine umfassende grafische Sicht der Leistungsdaten, indem diese direkt der visuellen Struktur der Anwendung zugeordnet werden. In diesem Screenshot verschafft Ihnen der Abschnitt **CPU-Auslastung** von Visual Profiler eine genaue Aufschlüsselung der Nutzung von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Diensten eines Objekts, z.B. Rendering und Layout.  
  
 ![Visual Profiler-Anzeige Ausgabe](./media/wpfperf-visualprofiler-04.png "WPFPerf_VisualProfiler_04")  
Visual Profiler-Anzeigeausgabe  
  
<a name="visual_rendering_behavior"></a>   
## <a name="visual-rendering-behavior"></a>Verhalten des visuellen Renderings  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verfügt über Funktionen, die das Renderingverhalten visueller Objekte beeinflussen: Retained Mode-Grafiken, Vektorgrafiken und geräteunabhängige Grafiken.  
  
### <a name="retained-mode-graphics"></a>Retained Mode-Grafiken  
 Einer der Schlüssel zum Verständnis der Rolle des visuellen Objekts ist der Unterschied zwischen Grafiksystemen mit **Direktmodus** und **Retained Mode**. Eine standardmäßige Win32-Anwendung, die auf GDI oder GDI+ basiert, verwendet ein Grafiksystem mit unmittelbaren Modus. Das heißt, dass die Anwendung für das Neuzeichnen des Teils des Clientbereichs verantwortlich ist, der aufgrund einer Aktion, z.B. Änderung der Größe eines Fensters, oder eines Objekts, dessen visuelle Darstellung geändert wird, ungültig ist.  
  
 ![Diagramm der Win32-Renderingsequenz](./media/wpf-graphics-rendering-overview/win32-rendering-squence.png)  
  
 Im Gegensatz dazu verwendet [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] ein System mit Retained Mode. Dies bedeutet, dass Objekte, die eine visuelle Darstellung haben, einen Satz serialisierter Zeichnungsdaten definieren. Nachdem die Zeichnungsdaten definiert wurden, ist das System für alle Repaint-Anforderungen zum Rendern der Anwendungsobjekte verantwortlich. Auch zur Laufzeit können Sie Anwendungsobjekte ändern oder erstellen und das System weiterhin auf Zeichnungsanforderungen reagieren lassen. Die Leistungsstärke eines Grafiksystems mit Retained Mode ist darauf zurückzuführen, dass Zeichnungsinformationen stets in einem serialisierten Zustand von der Anwendung gespeichert werden, die Verantwortung für das Rendering aber dem System überlassen wird. Das folgende Diagramm zeigt, wie die Anwendung [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] auf Zeichnungsanforderungen reagieren lässt.  
  
 ![Diagramm der WPF-Renderingsequenz](./media/wpf-graphics-rendering-overview/wpf-rendering-sequence.png)  

#### <a name="intelligent-redrawing"></a>Intelligentes Neuzeichnen  
 Einer der größten Vorteile bei der Verwendung von Grafiken mit dem Retained Mode besteht darin, dass [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] effizient optimieren kann, was in der Anwendung neu gezeichnet werden muss. Auch wenn Sie über eine komplexe Szene mit unterschiedlicher Deckkraft verfügen, müssen Sie im Allgemeinen nicht für besondere Zwecke Code zum Neuzeichnen optimieren. Vergleichen Sie dies mit der Win32-Programmierung, bei der Sie viele Ressourcen in die Optimierung Ihrer Anwendung durch Minimierung des Neuzeichnungaufwands im Aktualisierungsbereich investieren können. Ein Beispiel für den Typ der Komplexität in Verbindung mit der Optimierung der Neuzeichnung in Win32-Anwendungen finden Sie unter [Neuzeichnen im Aktualisierungsbereich](/windows/desktop/gdi/redrawing-in-the-update-region).  
  
### <a name="vector-graphics"></a>Vektorgrafiken  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet **Vektorgrafiken** als Renderingdatenformat. Vektorgrafiken – darunter Scalable Vector Graphics (SVG), Windows-Metadateien (WMF) und TrueType-Schriftarten – speichern Renderingdaten und übertragen sie als Liste von Anweisungen, die beschreiben, wie ein Bild mit Grafikprimitiven neu erstellt wird. TrueType-Schriftarten beispielsweise sind Umrissschriftarten, die einen Satz von Linien, Kurven und Befehlen anstelle eines Arrays von Pixeln beschreiben. Einer der wichtigsten Vorteile von Vektorgrafiken ist die Möglichkeit, auf eine beliebige Größe und Auflösung zu skalieren.  
  
 Im Gegensatz zu Vektorgrafiken speichern Bitmapgrafiken Renderingdaten als pixelweise Darstellung eines Bilds, die bereits für eine bestimmte Auflösung gerendert ist. Einer der wichtigsten Unterschiede zwischen Bitmap- und Vektorgrafikformaten ist die Originaltreue in Bezug auf das ursprüngliche Bild. Wenn beispielsweise die Größe eines Quellbilds geändert wird, strecken Bitmapgrafiksysteme das Bild, während Vektorgrafiksysteme das Bild skalieren und dabei die Bildtreue beibehalten.  
  
 Die folgende Abbildung zeigt ein Quellbild, dessen Größe um 300 % geändert wurde. Beachten Sie die Verzerrungen, die angezeigt werden, wenn das Quellbild als Bitmap-Grafik gestreckt und nicht als Vektorgrafikbild skaliert wird.  
  
 ![Unterschiede zwischen Raster- und Vektorgrafiken](./media/wpf-graphics-rendering-overview/raster-vector-differences.png)  
  
 Das folgende Markup zeigt zwei <xref:System.Windows.Shapes.Path> definierte Elemente. Das zweite Element verwendet einen <xref:System.Windows.Media.ScaleTransform> , um die Größe der Zeichnungs Anweisungen des ersten Elements um 300% zu ändern. Beachten Sie, dass die Zeichnungs Anweisungen <xref:System.Windows.Shapes.Path> in den Elementen unverändert bleiben.  
  
 [!code-xaml[VectorGraphicsSnippets#VectorGraphicsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/VectorGraphicsSnippets/CS/PageOne.xaml#vectorgraphicssnippet1)]  
  
### <a name="about-resolution-and-device-independent-graphics"></a>Info zu auflösungs- und geräteunabhängiger Grafik  
 Zwei Systemfaktoren bestimmen die Größe von Text und Grafiken auf dem Bildschirm: Auflösung und DPI. Die Auflösung beschreibt die Anzahl der Pixel, die auf dem Bildschirm angezeigt werden. Mit höherer Auflösung werden Pixel kleiner und lassen Grafiken und Text kleiner erscheinen. Eine Grafik, die auf einem Monitor mit 1024 x 768 angezeigt wird, erscheint viel kleiner, wenn die Auflösung in 1600 x 1200 geändert wird.  
  
 Die andere Systemeinstellung, DPI, beschreibt die Größe eines Bildschirmzolls in Pixeln. Die meisten Windows-Systeme verfügen über den dpi-Wert 96, was bedeutet, dass ein Bildschirm Zoll 96 Pixel ist. Durch Erhöhen der DPI-Einstellung wird der Bildschirmzoll größer, durch Verringern des DPI-Werts wird der Bildschirmzoll kleiner. Das bedeutet, dass ein Bildschirmzoll nicht die gleiche Größe wie ein realer Zoll hat; auf den meisten System trifft dies wahrscheinlich zu. Wenn Sie den DPI-Wert erhöhen, werden mit DPI kompatible Grafiken und Text größer, da Sie den Bildschirmzoll vergrößert haben. Durch Erhöhen des DPI-Werts kann sich die Lesbarkeit von Text, besonders in hoher Auflösung, verbessern.  
  
 Nicht alle Programme sind DPI-kompatibel: Einige verwenden Hardwarepixel als primäre Maßeinheit. Eine Änderung des DPI-Systemwerts hat keine Auswirkungen auf diese Anwendungen. Viele andere Clientanwendungen verwenden Einheiten, die mit DPI kompatibel sind, um Schriftgrade zu beschreiben, aber verwenden Pixel, um alles andere zu beschreiben. Ein zu großer oder zu kleiner DPI-Wert kann zu Layoutproblemen für diese Anwendungen führen, da der Text der Anwendungen mit der DPI-Einstellung skaliert wird, während dies bei den Anwendungen der Benutzeroberfläche nicht der Fall ist. Das Problem wurde für mit [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] entwickelte Anwendungen gelöst.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] unterstützt die automatische Skalierung mit geräteunabhängigen Pixeln als primärer Maßeinheit anstelle von Hardwarepixeln. Grafiken und Text skalieren ordnungsgemäß ohne zusätzlichen Eingriff seitens des Entwicklers der Anwendung. Die folgende Abbildung veranschaulicht anhand eines Beispiels, wie [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Text und -Grafiken mit unterschiedlichen DPI-Einstellungen angezeigt werden.  
  
 ![Grafiken und Text mit unterschiedlichen dpi-Einstellungen](./media/graphicsmm-dpi-setting-examples.png "graphicsmm_dpi_setting_examples")  
Grafiken und Text mit unterschiedlichen DPI-Einstellungen  
  
<a name="visualtreehelper_class"></a>   
## <a name="visualtreehelper-class"></a>VisualTreeHelper-Klasse  
 Bei <xref:System.Windows.Media.VisualTreeHelper> der-Klasse handelt es sich um eine statische Hilfsklasse, die Funktionen auf niedriger Ebene für die Programmierung auf visueller Objektebene bereitstellt, die in sehr spezifischen Szenarien nützlich ist, z. b. das Entwickeln von benutzerdefinierten Steuerelementen mit hoher Leistung In den meisten Fällen bieten die Framework- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Objekte auf höherer Ebene, <xref:System.Windows.Controls.Canvas> wie <xref:System.Windows.Controls.TextBlock>z. b. und, eine größere Flexibilität und Benutzerfreundlichkeit.  
  
### <a name="hit-testing"></a>Treffertests  
 Die <xref:System.Windows.Media.VisualTreeHelper> -Klasse stellt Methoden für Treffer Tests für visuelle Objekte bereit, wenn die standardmäßige Treffer Testunterstützung nicht Ihren Anforderungen entspricht. Sie können die <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> Methoden in der <xref:System.Windows.Media.VisualTreeHelper> -Klasse verwenden, um zu bestimmen, ob sich ein Geometrie-oder Punkt Koordinaten Wert innerhalb der Grenze eines angegebenen Objekts befindet, z. b. ein Steuerelement oder ein grafisches Element. Sie können beispielsweise mit Treffertests bestimmen, ob ein Mausklick innerhalb des umschließenden Rechtecks eines Objekts innerhalb der Geometrie eines Kreises liegt. Außerdem können Sie angeben, dass die standardmäßige Implementierung des Treffertests Ihre eigenen benutzerdefinierten Treffertestberechnungen überschreibt.  
  
 Weitere Informationen zu Treffertests finden Sie unter [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md).  
  
### <a name="enumerating-the-visual-tree"></a>Auflisten der visuellen Struktur  
 Die <xref:System.Windows.Media.VisualTreeHelper> -Klasse stellt Funktionen zum Auflisten der Elemente einer visuellen Struktur bereit. Rufen Sie zum Abrufen eines übergeordneten <xref:System.Windows.Media.VisualTreeHelper.GetParent%2A> Elements die-Methode auf. Um ein untergeordnetes Element oder einen direkt Nachfolger eines visuellen Objekts abzurufen, rufen Sie <xref:System.Windows.Media.VisualTreeHelper.GetChild%2A> die-Methode auf. Diese Methode gibt ein <xref:System.Windows.Media.Visual> untergeordnetes Element des übergeordneten Elements am angegebenen Index zurück.  
  
 Im folgenden Beispiel wird veranschaulicht, wie Sie alle Nachfolgerelemente eines visuellen Objekts auflisten. Diese Methode können Sie verwenden, wenn Sie alle Renderinginformationen einer Hierarchie von visuellen Objekten serialisieren möchten.  
  
 [!code-csharp[VisualsOverview#101](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#101)]
 [!code-vb[VisualsOverview#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#101)]  
  
 In den meisten Fällen ist die logische Struktur eine sinnvollere Darstellung der Elemente in einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung. Obwohl Sie die logische Struktur nicht ändern, ist diese Ansicht der Anwendung nützlich, um die Vererbung von Eigenschaften und das Ereignisrouting nachzuvollziehen. Anders als <xref:System.Windows.Documents.ListItem>bei der visuellen Struktur kann die logische Struktur nicht visuelle Datenobjekte, wie z. b., darstellen. Weitere Informationen über die logische Struktur finden Sie unter [Strukturen in WPF](../advanced/trees-in-wpf.md).  
  
 Die <xref:System.Windows.Media.VisualTreeHelper> -Klasse stellt Methoden zum Zurückgeben des umgebenden Rechtecks von visuellen Objekten bereit. Sie können das umgebende Rechteck eines visuellen Objekts zurückgeben, indem Sie <xref:System.Windows.Media.VisualTreeHelper.GetContentBounds%2A>aufrufen. Sie können das umgebende Rechteck aller Nachfolger eines visuellen Objekts, einschließlich des visuellen Objekts selbst, durch Aufrufen <xref:System.Windows.Media.VisualTreeHelper.GetDescendantBounds%2A>von zurückgeben. Der folgende Code zeigt, wie Sie das umschließende Rechteck des visuellen Objekts und aller Nachfolgerknoten berechnen.  
  
 [!code-csharp[VisualsOverview#102](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#102)]
 [!code-vb[VisualsOverview#102](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#102)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Media.Visual>
- <xref:System.Windows.Media.VisualTreeHelper>
- <xref:System.Windows.Media.DrawingVisual>
- [2D-Grafiken und Bildverarbeitung](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
- [Verwenden von DrawingVisual-Objekten](using-drawingvisual-objects.md)
- [Tutorial: Hosting von visuellen Objekten in einer Win32-Anwendung](tutorial-hosting-visual-objects-in-a-win32-application.md)
- [Optimieren der WPF-Anwendungsleistung](../advanced/optimizing-wpf-application-performance.md)
