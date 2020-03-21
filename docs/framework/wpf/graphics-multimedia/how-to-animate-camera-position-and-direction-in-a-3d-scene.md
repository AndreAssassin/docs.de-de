---
title: 'Gewusst wie: Animieren der Kameraposition und -richtung in 3D-Szenen'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], camera position in 3D scenes
- camera direction [WPF], animating in 3D scenes
- 3D scenes [WPF], animating camera position
- 3D scenes [WPF], animating camera direction
- camera position [WPF], animating in 3D scenes
- animation [WPF], camera direction in 3D scenes
ms.assetid: 480224b7-a5e5-4165-ba7f-ef760ddff94a
ms.openlocfilehash: 5ce94e154cd5aa29b59260f893ec2b63a08db0fc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112209"
---
# <a name="how-to-animate-camera-position-and-direction-in-a-3d-scene"></a><span data-ttu-id="befef-102">Gewusst wie: Animieren der Kameraposition und -richtung in 3D-Szenen</span><span class="sxs-lookup"><span data-stu-id="befef-102">How to: Animate Camera Position and Direction in a 3D Scene</span></span>
<span data-ttu-id="befef-103">Das folgende Beispiel zeigt, wie Sie die Position einer Kamera animieren und die Richtung animieren, in der sie in einer 3D-Szene zeigt.</span><span class="sxs-lookup"><span data-stu-id="befef-103">The following example shows how to animate the position of a camera and animate the direction it is pointing in a 3D scene.</span></span> <span data-ttu-id="befef-104">Dies geschieht, <xref:System.Windows.Media.Animation.Point3DAnimation> <xref:System.Windows.Media.Animation.Vector3DAnimation> indem sie <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> die bzw. <xref:System.Windows.Media.Media3D.PerspectiveCamera>Eigenschaften der verwendet und animiert.</span><span class="sxs-lookup"><span data-stu-id="befef-104">This is done by using <xref:System.Windows.Media.Animation.Point3DAnimation> and <xref:System.Windows.Media.Animation.Vector3DAnimation> to animate the <xref:System.Windows.Media.Media3D.ProjectionCamera.Position%2A> and <xref:System.Windows.Media.Media3D.ProjectionCamera.LookDirection%2A> properties respectively of the <xref:System.Windows.Media.Media3D.PerspectiveCamera>.</span></span> <span data-ttu-id="befef-105">Sie können eine Animation wie diese verwenden, um die Ansicht einer Szene als Reaktion auf ein Ereignis zu ändern.</span><span class="sxs-lookup"><span data-stu-id="befef-105">You might use an animation like this to change the onlooker's view of a scene in response to an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="befef-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="befef-106">Example</span></span>  
 [!code-xaml[Animation3DGallery_snip#PointVector3DAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/Animation3DGallery_snip/CS/PointVector3DAnimationExample.xaml#pointvector3danimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="befef-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="befef-107">See also</span></span>

- <xref:System.Windows.Media.Animation.Vector3DAnimation>
- <xref:System.Windows.Media.Animation.Point3DAnimation>
- [<span data-ttu-id="befef-108">Animieren von Kameraposition und -richtung mithilfe von Keyframes</span><span class="sxs-lookup"><span data-stu-id="befef-108">Animate Camera Position and Direction Using Key Frames</span></span>](how-to-animate-camera-position-and-direction-using-key-frames.md)
- [<span data-ttu-id="befef-109">3D-Grafikübersicht</span><span class="sxs-lookup"><span data-stu-id="befef-109">3D Graphics Overview</span></span>](3-d-graphics-overview.md)
