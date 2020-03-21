---
title: 'Gewusst wie: Anwenden von Emissive Material auf ein 3D-Objekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- EmissiveMaterial [WPF], applying to 3D objects
- 3D objects [WPF], applying EmissiveMaterial
ms.assetid: fd442cc2-5adc-487a-ba70-e45ed54bb3b4
ms.openlocfilehash: bf32b41ec2410c01ad137ec0ca9311f7c2b70061
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112153"
---
# <a name="how-to-apply-emissive-material-to-a-3d-object"></a>Gewusst wie: Anwenden von Emissive Material auf ein 3D-Objekt
Das folgende Beispiel zeigt, wie Sie <xref:System.Windows.Media.Media3D.EmissiveMaterial> einem vorhandenen Material Farbe hinzufügen, die der Farbe des Pinsels des EmissiveMaterials entspricht. Der folgende <xref:System.Windows.Media.Media3D.DiffuseMaterial> Code <xref:System.Windows.Media.Media3D.EmissiveMaterial> wird angezeigt und in Kombination angewendet, um dem Erscheinungsbild des DiffuseMaterials Blau hinzuzufügen.  
  
 [!code-xaml[3DGallery_snip#EmmisiveMaterialAnimationExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emmisivematerialanimationexampleinline1)]  
  
 Im Verfahrenscode:  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexampleinline1)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexampleinline1)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das gesamte Beispiel in XAML.  
  
 [!code-xaml[3DGallery_snip#EmissiveMaterialExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_snip/CS/EmissiveMaterialExample.xaml#emissivematerialexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Unten ist das gesamte Beispiel im Verfahrenscode.  
  
 [!code-csharp[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/3DGallery_procedural_snip/CSharp/EmissiveMaterialExample.cs#emissivematerialcodeexamplewholepage)]
 [!code-vb[3DGallery_procedural_snip#EmissiveMaterialCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/3DGallery_procedural_snip/visualbasic/emissivematerialexample.vb#emissivematerialcodeexamplewholepage)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Erstellen einer 3D-Szene](how-to-create-a-3-d-scene.md)
- [3D-Grafikübersicht](3-d-graphics-overview.md)
- [Animieren von Materialeigenschaften in einer 3D-Szene](how-to-animate-material-properties-in-a-3-d-scene.md)
- [Anwenden von Material auf die Vorder- und Rückseite eines 3D-Objekts](how-to-apply-material-to-the-front-and-back-of-a-3-d-object.md)
