---
title: Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- shapes [WPF], about shapes
- basic drawing [WPF]
- vector drawing [WPF], overview
- vectors [WPF], drawing
- Shape objects [WPF]
ms.assetid: 66d7a6d6-e3b6-47bc-8dfe-8a1b26f7d901
ms.openlocfilehash: 1ce0e661d88b7c4d5719c4f11ef0912c5bacb587
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008327"
---
# <a name="shapes-and-basic-drawing-in-wpf-overview"></a><span data-ttu-id="11ee4-102">Übersicht über Formen und die grundlegenden Funktionen zum Zeichnen in WPF</span><span class="sxs-lookup"><span data-stu-id="11ee4-102">Shapes and Basic Drawing in WPF Overview</span></span>
<span data-ttu-id="11ee4-103">Dieses Thema bietet eine Übersicht über das Zeichnen mit <xref:System.Windows.Shapes.Shape> Objekte.</span><span class="sxs-lookup"><span data-stu-id="11ee4-103">This topic gives an overview of how to draw with <xref:System.Windows.Shapes.Shape> objects.</span></span> <span data-ttu-id="11ee4-104">Ein <xref:System.Windows.Shapes.Shape> ist eine Art von <xref:System.Windows.UIElement> , mit der Sie eine Form auf dem Bildschirm zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="11ee4-104">A <xref:System.Windows.Shapes.Shape> is a type of <xref:System.Windows.UIElement> that enables you to draw a shape to the screen.</span></span> <span data-ttu-id="11ee4-105">Da sie UI-Elemente sind <xref:System.Windows.Shapes.Shape> Objekte können verwendet werden, in <xref:System.Windows.Controls.Panel> Elemente und die meisten Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="11ee4-105">Because they are UI elements, <xref:System.Windows.Shapes.Shape> objects can be used inside <xref:System.Windows.Controls.Panel> elements and most controls.</span></span>  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="11ee4-106">bietet mehrere Ebenen für den Zugriff auf Grafiken und Renderingdienste.</span><span class="sxs-lookup"><span data-stu-id="11ee4-106">offers several layers of access to graphics and rendering services.</span></span> <span data-ttu-id="11ee4-107">Auf der obersten Ebene <xref:System.Windows.Shapes.Shape> Objekte sind einfach zu verwenden und bieten viele nützliche Features, z.B. Layout und Teilnahme an der [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Ereignissystem.</span><span class="sxs-lookup"><span data-stu-id="11ee4-107">At the top layer, <xref:System.Windows.Shapes.Shape> objects are easy to use and provide many useful features, such as layout and participation in the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] event system.</span></span>  

<a name="shapes"></a>   
## <a name="shape-objects"></a><span data-ttu-id="11ee4-108">Shape-Objekte</span><span class="sxs-lookup"><span data-stu-id="11ee4-108">Shape Objects</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <span data-ttu-id="11ee4-109">bietet eine Reihe von sofort zu verwendende <xref:System.Windows.Shapes.Shape> Objekte.</span><span class="sxs-lookup"><span data-stu-id="11ee4-109">provides a number of ready-to-use <xref:System.Windows.Shapes.Shape> objects.</span></span>  <span data-ttu-id="11ee4-110">Alle Shape-Objekte erben von der <xref:System.Windows.Shapes.Shape> Klasse.</span><span class="sxs-lookup"><span data-stu-id="11ee4-110">All shape objects inherit from the <xref:System.Windows.Shapes.Shape> class.</span></span> <span data-ttu-id="11ee4-111">Verfügbare Shape-Objekte sind <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, und <xref:System.Windows.Shapes.Rectangle>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-111">Available shape objects include <xref:System.Windows.Shapes.Ellipse>, <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle>.</span></span> <span data-ttu-id="11ee4-112"><xref:System.Windows.Shapes.Shape> Objekte nutzen die folgenden allgemeinen Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="11ee4-112"><xref:System.Windows.Shapes.Shape> objects share the following common properties.</span></span>  
  
- <span data-ttu-id="11ee4-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Beschreibt, wie der Form gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="11ee4-113"><xref:System.Windows.Shapes.Shape.Stroke%2A>: Describes how the shape's outline is painted.</span></span>  
  
- <span data-ttu-id="11ee4-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Beschreibt die Stärke der Form an.</span><span class="sxs-lookup"><span data-stu-id="11ee4-114"><xref:System.Windows.Shapes.Shape.StrokeThickness%2A>: Describes the thickness of the shape's outline.</span></span>  
  
- <span data-ttu-id="11ee4-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Beschreibt, wie das Innere der Form gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="11ee4-115"><xref:System.Windows.Shapes.Shape.Fill%2A>: Describes how the interior of the shape is painted.</span></span>  
  
- <span data-ttu-id="11ee4-116">Dateneigenschaften zum Angeben von Koordinaten und Eckpunkten, gemessen in geräteunabhängigen Pixeln.</span><span class="sxs-lookup"><span data-stu-id="11ee4-116">Data properties to specify coordinates and vertices, measured in device-independent pixels.</span></span>  
  
 <span data-ttu-id="11ee4-117">Da sie von abgeleitet <xref:System.Windows.UIElement>, Shape-Objekte in Bereichen und den meisten Steuerelementen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="11ee4-117">Because they derive from <xref:System.Windows.UIElement>, shape objects can be used inside panels and most controls.</span></span> <span data-ttu-id="11ee4-118">Die <xref:System.Windows.Controls.Canvas> Bereich ist eine besonders gute Wahl für das Erstellen von komplexen Zeichnungen, da es die absolute Positionierung der untergeordneten Objekte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="11ee4-118">The <xref:System.Windows.Controls.Canvas> panel is a particularly good choice for creating complex drawings because it supports absolute positioning of its child objects.</span></span>  
  
 <span data-ttu-id="11ee4-119">Die <xref:System.Windows.Shapes.Line> -Klasse können Sie eine Linie zwischen zwei Punkten zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="11ee4-119">The <xref:System.Windows.Shapes.Line> class enables you to draw a line between two points.</span></span> <span data-ttu-id="11ee4-120">Das folgende Beispiel zeigt verschiedene Arten, wie Zeilenkoordinaten und Stricheigenschaften angegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="11ee4-120">The following example shows several ways to specify line coordinates and stroke properties.</span></span>  
  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 [!code-cpp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/cpp/VS_Snippets_Wpf/ShapesProcedural/CPP/ShapesProcedural.cpp#shapesproceduralline)]
 [!code-csharp[shapesprocedural#ShapesProceduralLine](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapesProcedural/Csharp/ShapesProcedural.cs#shapesproceduralline)]
 [!code-vb[shapesprocedural#ShapesProceduralLine](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ShapesProcedural/VisualBasic/ShapesProceduralVB.vb#shapesproceduralline)]  
  
 <span data-ttu-id="11ee4-121">Die folgende Abbildung zeigt die gerenderte <xref:System.Windows.Shapes.Line>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-121">The following image shows the rendered <xref:System.Windows.Shapes.Line>.</span></span>  
  
 <span data-ttu-id="11ee4-122">![Liniendarstellung](./media/shape-ovw-line2.gif "shape_ovw_line2")</span><span class="sxs-lookup"><span data-stu-id="11ee4-122">![Line illustration](./media/shape-ovw-line2.gif "shape_ovw_line2")</span></span>  
  
 <span data-ttu-id="11ee4-123">Obwohl die <xref:System.Windows.Shapes.Line> Klasse bietet einen <xref:System.Windows.Shapes.Shape.Fill%2A> -Eigenschaft, diese Einstellung hat keine Auswirkungen, da eine <xref:System.Windows.Shapes.Line> ist kein Bereich.</span><span class="sxs-lookup"><span data-stu-id="11ee4-123">Although the <xref:System.Windows.Shapes.Line> class does provide a <xref:System.Windows.Shapes.Shape.Fill%2A> property, setting it has no effect because a <xref:System.Windows.Shapes.Line> has no area.</span></span>  
  
 <span data-ttu-id="11ee4-124">Eine weitere allgemeine Form ist die <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-124">Another common shape is the <xref:System.Windows.Shapes.Ellipse>.</span></span>  <span data-ttu-id="11ee4-125">Erstellen Sie eine <xref:System.Windows.Shapes.Ellipse> durch die Definition der Form <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="11ee4-125">Create an <xref:System.Windows.Shapes.Ellipse> by defining the shape's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span> <span data-ttu-id="11ee4-126">Um einen Kreis zu zeichnen, geben Sie eine <xref:System.Windows.Shapes.Ellipse> , deren <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Werte gleich sind.</span><span class="sxs-lookup"><span data-stu-id="11ee4-126">To draw a circle, specify an <xref:System.Windows.Shapes.Ellipse> whose <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> values are equal.</span></span>  
  
 [!code-xaml[ShapeOverviews#ShapesOVW1](~/samples/snippets/csharp/VS_Snippets_Wpf/ShapeOverviews/CS/Window1.xaml#shapesovw1)]  
  
 [!code-csharp[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/CSharp/SetBackgroundColorOfShapeExample.cs#setbackgroundcolorofshapecodeexamplewholepage)]
 [!code-vb[brushesmiscsnippets_procedural_snip#SetBackgroundColorOfShapeCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesMiscSnippets_procedural_snip/visualbasic/setbackgroundcolorofshapeexample.vb#setbackgroundcolorofshapecodeexamplewholepage)]  
  
 <span data-ttu-id="11ee4-127">Die folgende Abbildung zeigt ein Beispiel eines gerenderten <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-127">The following image shows an example of a rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="11ee4-128">![Ellipsendarstellung](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span><span class="sxs-lookup"><span data-stu-id="11ee4-128">![Ellipse illustration](./media/shape-ovw-ellipse2.png "shape_ovw_ellipse2")</span></span>  
  
<a name="paths"></a>   
## <a name="using-paths-and-geometries"></a><span data-ttu-id="11ee4-129">Verwenden von Pfaden und Geometrien</span><span class="sxs-lookup"><span data-stu-id="11ee4-129">Using Paths and Geometries</span></span>  
 <span data-ttu-id="11ee4-130">Die <xref:System.Windows.Shapes.Path> Klasse ermöglicht Ihnen, Kurven und komplexe Formen zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="11ee4-130">The <xref:System.Windows.Shapes.Path> class enables you to draw curves and complex shapes.</span></span> <span data-ttu-id="11ee4-131">Diese Kurven und Formen werden mithilfe von beschrieben <xref:System.Windows.Media.Geometry> Objekte.</span><span class="sxs-lookup"><span data-stu-id="11ee4-131">These curves and shapes are described using <xref:System.Windows.Media.Geometry> objects.</span></span> <span data-ttu-id="11ee4-132">Verwenden einer <xref:System.Windows.Shapes.Path>, erstellen Sie eine <xref:System.Windows.Media.Geometry> und verwenden sie zum Festlegen der <xref:System.Windows.Shapes.Path> des Objekts <xref:System.Windows.Shapes.Path.Data%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11ee4-132">To use a <xref:System.Windows.Shapes.Path>, you create a <xref:System.Windows.Media.Geometry> and use it to set the <xref:System.Windows.Shapes.Path> object's <xref:System.Windows.Shapes.Path.Data%2A> property.</span></span>  
  
 <span data-ttu-id="11ee4-133">Es gibt eine Vielzahl von <xref:System.Windows.Media.Geometry> Objekte zur Auswahl.</span><span class="sxs-lookup"><span data-stu-id="11ee4-133">There are a variety of <xref:System.Windows.Media.Geometry> objects to choose from.</span></span> <span data-ttu-id="11ee4-134">Die <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, und <xref:System.Windows.Media.EllipseGeometry> Klassen beschreiben relativ einfache Formen.</span><span class="sxs-lookup"><span data-stu-id="11ee4-134">The <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.RectangleGeometry>, and <xref:System.Windows.Media.EllipseGeometry> classes describe relatively simple shapes.</span></span> <span data-ttu-id="11ee4-135">Erstellen Sie eine komplexere Formen oder Kurven zu erstellen, verwenden Sie eine <xref:System.Windows.Media.PathGeometry>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-135">To create more complex shapes or create curves, use a <xref:System.Windows.Media.PathGeometry>.</span></span>  
  
<a name="pathgeometry"></a>   
### <a name="pathgeometry-and-pathsegments"></a><span data-ttu-id="11ee4-136">PathGeometry und PathSegments</span><span class="sxs-lookup"><span data-stu-id="11ee4-136">PathGeometry and PathSegments</span></span>  
 <span data-ttu-id="11ee4-137"><xref:System.Windows.Media.PathGeometry> -Objekte bestehen aus einem oder mehreren <xref:System.Windows.Media.PathFigure> Objekten; jedes <xref:System.Windows.Media.PathFigure> stellt eine andere "Abbildung" oder Form dar.</span><span class="sxs-lookup"><span data-stu-id="11ee4-137"><xref:System.Windows.Media.PathGeometry> objects are comprised of one or more <xref:System.Windows.Media.PathFigure> objects; each <xref:System.Windows.Media.PathFigure> represents a different "figure" or shape.</span></span> <span data-ttu-id="11ee4-138">Jede <xref:System.Windows.Media.PathFigure> selbst besteht aus einer oder mehreren <xref:System.Windows.Media.PathSegment> Objekte, von denen jedes einen verknüpften Abschnitt der Figur oder Form darstellt.</span><span class="sxs-lookup"><span data-stu-id="11ee4-138">Each <xref:System.Windows.Media.PathFigure> is itself comprised of one or more <xref:System.Windows.Media.PathSegment> objects, each representing a connected portion of the figure or shape.</span></span> <span data-ttu-id="11ee4-139">Segmenttypen beinhalten Folgendes: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, und <xref:System.Windows.Media.ArcSegment>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-139">Segment types include the following: <xref:System.Windows.Media.LineSegment>, <xref:System.Windows.Media.BezierSegment>, and <xref:System.Windows.Media.ArcSegment>.</span></span>  
  
 <span data-ttu-id="11ee4-140">Im folgenden Beispiel eine <xref:System.Windows.Shapes.Path> zum Zeichnen einer quadratischen Bezierkurve verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="11ee4-140">In the following example, a <xref:System.Windows.Shapes.Path> is used to draw a quadratic Bezier curve.</span></span>  
  
 [!code-xaml[geometrysample#34](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 <span data-ttu-id="11ee4-141">Die folgende Abbildung zeigt die gerenderte Form.</span><span class="sxs-lookup"><span data-stu-id="11ee4-141">The following image shows the rendered shape.</span></span>  
  
 <span data-ttu-id="11ee4-142">![Pfaddarstellung](./media/shape-ovw-path2.gif "shape_ovw_path2")</span><span class="sxs-lookup"><span data-stu-id="11ee4-142">![Path illustration](./media/shape-ovw-path2.gif "shape_ovw_path2")</span></span>  
  
 <span data-ttu-id="11ee4-143">Weitere Informationen zu <xref:System.Windows.Media.PathGeometry> und die andere <xref:System.Windows.Media.Geometry> finden Sie unter den [Übersicht über die Geometrie](geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="11ee4-143">For more information about <xref:System.Windows.Media.PathGeometry> and the other <xref:System.Windows.Media.Geometry> classes, see the [Geometry Overview](geometry-overview.md).</span></span>  
  
<a name="pathdatastring"></a>   
### <a name="xaml-abbreviated-syntax"></a><span data-ttu-id="11ee4-144">Abgekürzte Syntax in XAML</span><span class="sxs-lookup"><span data-stu-id="11ee4-144">XAML Abbreviated Syntax</span></span>  
 <span data-ttu-id="11ee4-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], Sie können auch eine besondere abgekürzte Syntax verwenden, um zu beschreiben eine <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-145">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], you may also use a special abbreviated syntax to describe a <xref:System.Windows.Shapes.Path>.</span></span> <span data-ttu-id="11ee4-146">Im folgenden Beispiel wird abgekürzte Syntax verwendet, um eine komplexe Form zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="11ee4-146">In the following example, abbreviated syntax is used to draw a complex shape.</span></span>  
  
```xaml  
      <Path Stroke="DarkGoldenRod" StrokeThickness="3"   
Data="M 100,200 C 100,25 400,350 400,175 H 280" />  
```  
  
 <span data-ttu-id="11ee4-147">Die folgende Abbildung zeigt einen gerenderten <xref:System.Windows.Shapes.Path>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-147">The following image shows a rendered <xref:System.Windows.Shapes.Path>.</span></span>  
  
 <span data-ttu-id="11ee4-148">![Pfaddarstellung](./media/shape-ovw-path.PNG "Shape_ovw_path")</span><span class="sxs-lookup"><span data-stu-id="11ee4-148">![Path illustration](./media/shape-ovw-path.PNG "shape_ovw_path")</span></span>  
  
 <span data-ttu-id="11ee4-149">Die <xref:System.Windows.Shapes.Path.Data%2A> -Attributzeichenfolge beginnt mit dem "Moveto"-Befehl, angegeben durch M, der einen Startpunkt für den Pfad im Koordinatensystem der richtet die <xref:System.Windows.Controls.Canvas>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-149">The <xref:System.Windows.Shapes.Path.Data%2A> attribute string begins with the "moveto" command, indicated by M, which establishes a start point for the path in the coordinate system of the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="11ee4-150"><xref:System.Windows.Shapes.Path> -Datenparameter unterscheiden Groß-/Kleinschreibung beachtet.</span><span class="sxs-lookup"><span data-stu-id="11ee4-150"><xref:System.Windows.Shapes.Path> data parameters are case-sensitive.</span></span> <span data-ttu-id="11ee4-151">Der Großbuchstabe M gibt eine absolute Position für den neuen aktuellen Punkt.</span><span class="sxs-lookup"><span data-stu-id="11ee4-151">The capital M indicates an absolute location for the new current point.</span></span> <span data-ttu-id="11ee4-152">Ein kleingeschriebenes m würde relative Koordinaten angeben.</span><span class="sxs-lookup"><span data-stu-id="11ee4-152">A lowercase m would indicate relative coordinates.</span></span> <span data-ttu-id="11ee4-153">Das erste Segment ist ein kubische Bezier-Kurve ab (100,200) und endet (400,175), Punkte (100,25) und (400,350) steuern gezeichneten mit den beiden.</span><span class="sxs-lookup"><span data-stu-id="11ee4-153">The first segment is a cubic Bezier curve beginning at (100,200) and ending at (400,175), drawn using the two control points (100,25) and (400,350).</span></span> <span data-ttu-id="11ee4-154">Dieses Segment wird angegeben, mit dem Befehl "C" in der <xref:System.Windows.Shapes.Path.Data%2A> Attribut-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="11ee4-154">This segment is indicated by the C command in the <xref:System.Windows.Shapes.Path.Data%2A> attribute string.</span></span> <span data-ttu-id="11ee4-155">Ein großes C gibt erneut einen absoluten Pfad an. Ein kleingeschriebenes c würde einen relativen Pfad angeben.</span><span class="sxs-lookup"><span data-stu-id="11ee4-155">Again, the capital C indicates an absolute path; the lowercase c would indicate a relative path.</span></span>  
  
 <span data-ttu-id="11ee4-156">Das zweite Segment beginnt mit einem absoluten horizontalen „Lineto“-Befehl H, der eine Linie vom vorherigen untergeordneten Endpunkt (400,175) zu einem neuen Endpunkt (280,175) zeichnet.</span><span class="sxs-lookup"><span data-stu-id="11ee4-156">The second segment begins with an absolute horizontal "lineto" command H, which specifies a line drawn from the preceding subpath's endpoint (400,175) to a new endpoint (280,175).</span></span> <span data-ttu-id="11ee4-157">Da es sich um einen horizontalen "Lineto"-Befehl handelt, wird der angegebene Wert ist eine *x*-koordinieren.</span><span class="sxs-lookup"><span data-stu-id="11ee4-157">Because it is a horizontal "lineto" command, the value specified is an *x*-coordinate.</span></span>  
  
 <span data-ttu-id="11ee4-158">Die vollständige Pfadsyntax finden Sie unter den <xref:System.Windows.Shapes.Path.Data%2A> Verweis und [Erstellen einer Form mithilfe von PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span><span class="sxs-lookup"><span data-stu-id="11ee4-158">For the complete path syntax, see the <xref:System.Windows.Shapes.Path.Data%2A> reference and [Create a Shape by Using a PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).</span></span>  
  
<a name="fillpaint"></a>   
## <a name="painting-shapes"></a><span data-ttu-id="11ee4-159">Zeichnen von Formen</span><span class="sxs-lookup"><span data-stu-id="11ee4-159">Painting Shapes</span></span>  
 <span data-ttu-id="11ee4-160"><xref:System.Windows.Media.Brush> Objekte werden verwendet, um das Zeichnen einer Form <xref:System.Windows.Shapes.Shape.Stroke%2A> und <xref:System.Windows.Shapes.Shape.Fill%2A>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-160"><xref:System.Windows.Media.Brush> objects are used to paint a shape's <xref:System.Windows.Shapes.Shape.Stroke%2A> and <xref:System.Windows.Shapes.Shape.Fill%2A>.</span></span> <span data-ttu-id="11ee4-161">Im folgenden Beispiel wird der Strich und Füllung des ein <xref:System.Windows.Shapes.Ellipse> angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="11ee4-161">In the following example, the stroke and fill of an <xref:System.Windows.Shapes.Ellipse> are specified.</span></span> <span data-ttu-id="11ee4-162">Beachten Sie, dass Pinseleigenschaften entweder ein Schlüsselwort oder einen hexadezimalen Farbwert werden können.</span><span class="sxs-lookup"><span data-stu-id="11ee4-162">Note that valid input for brush properties can be either a keyword or hexadecimal color value.</span></span> <span data-ttu-id="11ee4-163">Weitere Informationen über verfügbare Farbschlüsselwörter finden Sie unter Eigenschaften der <xref:System.Windows.Media.Colors> -Klasse in der <xref:System.Windows.Media> Namespace.</span><span class="sxs-lookup"><span data-stu-id="11ee4-163">For more information about available color keywords, see properties of the <xref:System.Windows.Media.Colors> class in the <xref:System.Windows.Media> namespace.</span></span>  
  
```xaml
<Canvas Background="LightGray">   
   <Ellipse  
      Canvas.Top="50"  
      Canvas.Left="50"  
      Fill="#FFFFFF00"  
      Height="75"  
      Width="75"  
      StrokeThickness="5"  
      Stroke="#FF0000FF"/>  
</Canvas>  
```  
  
 <span data-ttu-id="11ee4-164">Die folgende Abbildung zeigt die gerenderte <xref:System.Windows.Shapes.Ellipse>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-164">The following image shows the rendered <xref:System.Windows.Shapes.Ellipse>.</span></span>  
  
 <span data-ttu-id="11ee4-165">![Eine Ellipse](./media/shape-ovw-ellipsefill.PNG "Shape_ovw_ellipsefill")</span><span class="sxs-lookup"><span data-stu-id="11ee4-165">![An ellipse](./media/shape-ovw-ellipsefill.PNG "shape_ovw_ellipsefill")</span></span>  
  
 <span data-ttu-id="11ee4-166">Alternativ können Sie Eigenschaftenelement-Syntax verwenden, erstellen Sie explizit eine <xref:System.Windows.Media.SolidColorBrush> Objekt, das die Form mit einer Volltonfarbe zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="11ee4-166">Alternatively, you can use property element syntax to explicitly create a <xref:System.Windows.Media.SolidColorBrush> object to paint the shape with a solid color.</span></span>  
  
```xaml
<!-- This polygon shape uses pre-defined color values for its Stroke and  
     Fill properties.   
     The SolidColorBrush's Opacity property affects the fill color in   
     this case by making it slightly transparent (opacity of 0.4) so   
     that it blends with any underlying color. -->  
  
<Polygon  
    Points="300,200 400,125 400,275 300,200"  
    Stroke="Purple"   
    StrokeThickness="2">  
    <Polygon.Fill>  
       <SolidColorBrush Color="Blue" Opacity="0.4"/>  
    </Polygon.Fill>  
</Polygon>  
```  
  
 <span data-ttu-id="11ee4-167">Die folgende Abbildung zeigt die gerenderte Form.</span><span class="sxs-lookup"><span data-stu-id="11ee4-167">The following illustration shows the rendered shape.</span></span>  
  
 <span data-ttu-id="11ee4-168">![SolidColorBrush-Darstellung](./media/shape-ovw-solidcolorbrush.PNG "Shape_ovw_solidcolorbrush")</span><span class="sxs-lookup"><span data-stu-id="11ee4-168">![SolidColorBrush illustration](./media/shape-ovw-solidcolorbrush.PNG "shape_ovw_solidcolorbrush")</span></span>  
  
 <span data-ttu-id="11ee4-169">Sie können die Kontur oder Fläche einer Form auch mit Farbverläufen, Bildern, Mustern und mehr zeichnen.</span><span class="sxs-lookup"><span data-stu-id="11ee4-169">You can also paint a shape's stroke or fill with gradients, images, patterns, and more.</span></span> <span data-ttu-id="11ee4-170">Weitere Informationen finden Sie unter den [Zeichnen mit Volltonfarben und Farbverläufen](painting-with-solid-colors-and-gradients-overview.md).</span><span class="sxs-lookup"><span data-stu-id="11ee4-170">For more information, see the [Painting with Solid Colors and Gradients Overview](painting-with-solid-colors-and-gradients-overview.md).</span></span>  
  
<a name="stretchableshapessection"></a>   
## <a name="stretchable-shapes"></a><span data-ttu-id="11ee4-171">Gestreckte Formen</span><span class="sxs-lookup"><span data-stu-id="11ee4-171">Stretchable Shapes</span></span>  
 <span data-ttu-id="11ee4-172">Die <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, und <xref:System.Windows.Shapes.Rectangle> Klassen, die alle verfügen über eine <xref:System.Windows.Shapes.Shape.Stretch%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11ee4-172">The <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Shapes.Polygon>, <xref:System.Windows.Shapes.Polyline>, and <xref:System.Windows.Shapes.Rectangle> classes all have a <xref:System.Windows.Shapes.Shape.Stretch%2A> property.</span></span> <span data-ttu-id="11ee4-173">Diese Eigenschaft bestimmt, wie eine <xref:System.Windows.Shapes.Shape> Inhalte des-Objekts (das zu zeichnende Form) ist Füllbereich der <xref:System.Windows.Shapes.Shape> Layoutbereich des Objekts.</span><span class="sxs-lookup"><span data-stu-id="11ee4-173">This property determines how a <xref:System.Windows.Shapes.Shape> object's contents (the shape to be drawn) is stretched to fill the <xref:System.Windows.Shapes.Shape> object's layout space.</span></span> <span data-ttu-id="11ee4-174">Ein <xref:System.Windows.Shapes.Shape> des Objekts ist die Menge des Speicherplatzes der <xref:System.Windows.Shapes.Shape> zugeordnet durch das Layoutsystem aufgrund einer expliziten <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Einstellung oder aufgrund von dessen <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> und <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="11ee4-174">A <xref:System.Windows.Shapes.Shape> object's layout space is the amount of space the <xref:System.Windows.Shapes.Shape> is allocated by the layout system, because of either an explicit <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> setting or because of its <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> and <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> settings.</span></span> <span data-ttu-id="11ee4-175">Weitere Informationen zu Layouts in Windows Presentation Foundation, finden Sie unter [Layout](../advanced/layout.md) Übersicht.</span><span class="sxs-lookup"><span data-stu-id="11ee4-175">For additional information on layout in Windows Presentation Foundation, see [Layout](../advanced/layout.md) overview.</span></span>  
  
 <span data-ttu-id="11ee4-176">Die Stretch-Eigenschaft nimmt einen der folgenden Werte an:</span><span class="sxs-lookup"><span data-stu-id="11ee4-176">The Stretch property takes one of the following values:</span></span>  
  
- <span data-ttu-id="11ee4-177"><xref:System.Windows.Media.Stretch.None>: Die <xref:System.Windows.Shapes.Shape> Inhalt des Objekts werden nicht gestreckt.</span><span class="sxs-lookup"><span data-stu-id="11ee4-177"><xref:System.Windows.Media.Stretch.None>: The <xref:System.Windows.Shapes.Shape> object's contents are not stretched.</span></span>  
  
- <span data-ttu-id="11ee4-178"><xref:System.Windows.Media.Stretch.Fill>: Die <xref:System.Windows.Shapes.Shape> Inhalte des-Objekts werden gestreckt, um den Layoutbereich auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="11ee4-178"><xref:System.Windows.Media.Stretch.Fill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to fill its layout space.</span></span>  <span data-ttu-id="11ee4-179">Das Seitenverhältnis wird nicht beibehalten.</span><span class="sxs-lookup"><span data-stu-id="11ee4-179">Aspect ratio is not preserved.</span></span>  
  
- <span data-ttu-id="11ee4-180"><xref:System.Windows.Media.Stretch.Uniform>: Die <xref:System.Windows.Shapes.Shape> Inhalte des-Objekts werden gestreckt, so weit wie möglich ist, um den Layoutbereich auszufüllen und gleichzeitig die ursprünglichen Seitenverhältnisse beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="11ee4-180"><xref:System.Windows.Media.Stretch.Uniform>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched as much as possible to fill its layout space while preserving its original aspect ratio.</span></span>  
  
- <span data-ttu-id="11ee4-181"><xref:System.Windows.Media.Stretch.UniformToFill>: Die <xref:System.Windows.Shapes.Shape> Inhalte des-Objekts werden gestreckt, um den Layoutbereich vollständig auszufüllen, während gleichzeitig die ursprünglichen Seitenverhältnisse beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="11ee4-181"><xref:System.Windows.Media.Stretch.UniformToFill>: The <xref:System.Windows.Shapes.Shape> object's contents are stretched to completely fill its layout space while preserving its original aspect ratio.</span></span>  
  
 <span data-ttu-id="11ee4-182">Beachten Sie, dass bei einem <xref:System.Windows.Shapes.Shape> Inhalte des-Objekts werden gestreckt, die <xref:System.Windows.Shapes.Shape> -Objekts nach dem Strecken gezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="11ee4-182">Note that, when a <xref:System.Windows.Shapes.Shape> object's contents are stretched, the <xref:System.Windows.Shapes.Shape> object's outline is painted after the stretching.</span></span>  
  
 <span data-ttu-id="11ee4-183">Im folgenden Beispiel eine <xref:System.Windows.Shapes.Polygon> , die zum Zeichnen eines sehr kleinen Dreiecks von (0,0) bis (0,1) bis (1,1) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="11ee4-183">In the following example, a <xref:System.Windows.Shapes.Polygon> is used to draw a very small triangle from (0,0) to (0,1) to (1,1).</span></span> <span data-ttu-id="11ee4-184">Die <xref:System.Windows.Shapes.Polygon> des Objekts <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> auf 100 festgelegt sind und die Stretch-Eigenschaft auf Fill festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="11ee4-184">The <xref:System.Windows.Shapes.Polygon> object's <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> are set to 100, and its stretch property is set to Fill.</span></span> <span data-ttu-id="11ee4-185">Daher die <xref:System.Windows.Shapes.Polygon> Inhalt des Objekts (das Dreieck) werden gestreckt, um den größeren Bereich auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="11ee4-185">As a result, the <xref:System.Windows.Shapes.Polygon> object's contents (the triangle) are stretched to fill the larger space.</span></span>  
  
```xaml
<Polygon  
  Points="0,0 0,1 1,1"  
  Fill="Blue"  
  Width="100"  
  Height="100"  
  Stretch="Fill"  
  Stroke="Black"  
  StrokeThickness="2" />  
```

```csharp
PointCollection myPointCollection = new PointCollection();  
myPointCollection.Add(new Point(0,0));  
myPointCollection.Add(new Point(0,1));  
myPointCollection.Add(new Point(1,1));  
  
Polygon myPolygon = new Polygon();  
myPolygon.Points = myPointCollection;  
myPolygon.Fill = Brushes.Blue;  
myPolygon.Width = 100;  
myPolygon.Height = 100;  
myPolygon.Stretch = Stretch.Fill;  
myPolygon.Stroke = Brushes.Black;  
myPolygon.StrokeThickness = 2;  
```

<a name="transforms"></a>   
## <a name="transforming-shapes"></a><span data-ttu-id="11ee4-186">Transformieren von Formen</span><span class="sxs-lookup"><span data-stu-id="11ee4-186">Transforming Shapes</span></span>  
 <span data-ttu-id="11ee4-187">Die <xref:System.Windows.Media.Transform> -Klasse bietet die Möglichkeit zur Transformation von Formen in einem zweidimensionalen Raum.</span><span class="sxs-lookup"><span data-stu-id="11ee4-187">The <xref:System.Windows.Media.Transform> class provides the means to transform shapes in a two-dimensional plane.</span></span>  <span data-ttu-id="11ee4-188">Die verschiedenen Typen von Transformation beinhalten Drehung (<xref:System.Windows.Media.RotateTransform>), Skalierung (<xref:System.Windows.Media.ScaleTransform>), Neigung (<xref:System.Windows.Media.SkewTransform>), und die Übersetzung (<xref:System.Windows.Media.TranslateTransform>).</span><span class="sxs-lookup"><span data-stu-id="11ee4-188">The different types of transformation include rotation (<xref:System.Windows.Media.RotateTransform>), scale (<xref:System.Windows.Media.ScaleTransform>), skew (<xref:System.Windows.Media.SkewTransform>), and translation (<xref:System.Windows.Media.TranslateTransform>).</span></span>  
  
 <span data-ttu-id="11ee4-189">Eine allgemeine Transformation einer Form ist die Drehung.</span><span class="sxs-lookup"><span data-stu-id="11ee4-189">A common transform to apply to a shape is a rotation.</span></span>  <span data-ttu-id="11ee4-190">Um eine Form zu drehen, erstellen Sie eine <xref:System.Windows.Media.RotateTransform> , und geben Sie die <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-190">To rotate a shape, create a <xref:System.Windows.Media.RotateTransform> and specify its <xref:System.Windows.Media.RotateTransform.Angle%2A>.</span></span> <span data-ttu-id="11ee4-191">Ein <xref:System.Windows.Media.RotateTransform.Angle%2A> 45 dreht das Element um 45 Grad im Uhrzeigersinn; ein Winkel von 90 Dreht das Element um 90 Grad im Uhrzeigersinn gedreht; und so weiter.</span><span class="sxs-lookup"><span data-stu-id="11ee4-191">An <xref:System.Windows.Media.RotateTransform.Angle%2A> of 45 rotates the element 45 degrees clockwise; an angle of 90 rotates the element 90 degrees clockwise; and so on.</span></span> <span data-ttu-id="11ee4-192">Legen Sie die <xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> Eigenschaften sollten Sie den Punkt zu steuern, den das Element gedreht wird.</span><span class="sxs-lookup"><span data-stu-id="11ee4-192">Set the <xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> properties if you want to control the point about which the element is rotated.</span></span> <span data-ttu-id="11ee4-193">Diese Eigenschaftswerte werden im Koordinatenraum des transformierten Elements ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="11ee4-193">These property values are expressed in the coordinate space of the element being transformed.</span></span> <span data-ttu-id="11ee4-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> und <xref:System.Windows.Media.RotateTransform.CenterY%2A> haben Standardwerte von 0 (null).</span><span class="sxs-lookup"><span data-stu-id="11ee4-194"><xref:System.Windows.Media.RotateTransform.CenterX%2A> and <xref:System.Windows.Media.RotateTransform.CenterY%2A> have default values of zero.</span></span> <span data-ttu-id="11ee4-195">Wenden Sie schließlich die <xref:System.Windows.Media.RotateTransform> auf das Element.</span><span class="sxs-lookup"><span data-stu-id="11ee4-195">Finally, apply the <xref:System.Windows.Media.RotateTransform> to the element.</span></span> <span data-ttu-id="11ee4-196">Wenn Sie nicht, dass die Transformation auf das Layout auswirken möchten, legen Sie der Form des <xref:System.Windows.UIElement.RenderTransform%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11ee4-196">If you don't want the transform to affect layout, set the shape's <xref:System.Windows.UIElement.RenderTransform%2A> property.</span></span>  
  
 <span data-ttu-id="11ee4-197">Im folgenden Beispiel eine <xref:System.Windows.Media.RotateTransform> wird verwendet, um eine Form um 45 Grad zur oberen linken Ecke (0,0) drehen.</span><span class="sxs-lookup"><span data-stu-id="11ee4-197">In the following example, a <xref:System.Windows.Media.RotateTransform> is used to rotate a shape 45 degrees about the shape's top left corner (0,0).</span></span>  
  
 [!code-xaml[transformssample#14](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#14)]  
  
 <span data-ttu-id="11ee4-198">Im nächsten Beispiel eine andere Form um 45 Grad gedreht wird, aber dieses Mal wird sie über den Punkt (25,50) gedreht.</span><span class="sxs-lookup"><span data-stu-id="11ee4-198">In the next example, another shape is rotated 45 degrees, but this time it's rotated about the point (25,50).</span></span>  
  
 [!code-xaml[transformssample#15](~/samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/RotateTransformExample.xaml#15)]  
  
 <span data-ttu-id="11ee4-199">In der folgenden Abbildung werden die Ergebnisse der Anwendung der zwei Transformationen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="11ee4-199">The following illustration shows the results of applying the two transforms.</span></span>  
  
 <span data-ttu-id="11ee4-200">![45-Grad-Drehungen mit unterschiedlichen Mittelpunkten](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span><span class="sxs-lookup"><span data-stu-id="11ee4-200">![45 degree rotations with different center points](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")</span></span>  
  
 <span data-ttu-id="11ee4-201">In den vorherigen Beispielen wurde eine einzelne Transformation auf jedes Shape-Objekt angewendet.</span><span class="sxs-lookup"><span data-stu-id="11ee4-201">In the previous examples, a single transform was applied to each shape object.</span></span> <span data-ttu-id="11ee4-202">Verwenden Sie zum Anwenden mehrerer Transformationen auf eine Form (oder andere Elemente der Benutzeroberfläche) eine <xref:System.Windows.Media.TransformGroup>.</span><span class="sxs-lookup"><span data-stu-id="11ee4-202">To apply multiple transforms to a shape (or any other UI element), use a <xref:System.Windows.Media.TransformGroup>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11ee4-203">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11ee4-203">See also</span></span>

- [<span data-ttu-id="11ee4-204">2D-Grafiken und Bildverarbeitung</span><span class="sxs-lookup"><span data-stu-id="11ee4-204">2D Graphics and Imaging</span></span>](../advanced/optimizing-performance-2d-graphics-and-imaging.md)
- [<span data-ttu-id="11ee4-205">Übersicht über das Zeichnen mit Volltonfarben und Farbverläufen</span><span class="sxs-lookup"><span data-stu-id="11ee4-205">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
- [<span data-ttu-id="11ee4-206">Übersicht über Geometrien</span><span class="sxs-lookup"><span data-stu-id="11ee4-206">Geometry Overview</span></span>](geometry-overview.md)
- [<span data-ttu-id="11ee4-207">Exemplarische Vorgehensweise: Walkthrough: My first WPF desktop application (Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung)</span><span class="sxs-lookup"><span data-stu-id="11ee4-207">Walkthrough: My first WPF desktop application</span></span>](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
- [<span data-ttu-id="11ee4-208">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="11ee4-208">Animation Overview</span></span>](animation-overview.md)
