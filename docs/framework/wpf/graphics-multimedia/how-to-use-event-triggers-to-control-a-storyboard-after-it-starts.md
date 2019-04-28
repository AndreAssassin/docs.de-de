---
title: 'Vorgehensweise: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start'
ms.date: 03/30/2017
helpviewer_keywords:
- triggers [WPF], controlling Storyboards
- event triggers [WPF], controlling Storyboards
- Storyboards [WPF], controlling after start
ms.assetid: 3b115594-6a93-4972-b24d-61aa16f1c15f
ms.openlocfilehash: d444349f8bc9236e1d15f484f35b1326c77e2425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769290"
---
# <a name="how-to-use-event-triggers-to-control-a-storyboard-after-it-starts"></a><span data-ttu-id="0e40e-102">Vorgehensweise: Verwenden von Ereignistriggern zum Steuern eines Storyboards nach dessen Start</span><span class="sxs-lookup"><span data-stu-id="0e40e-102">How to: Use Event Triggers to Control a Storyboard After It Starts</span></span>
<span data-ttu-id="0e40e-103">Dieses Beispiel zeigt, wie Sie steuern eine <xref:System.Windows.Media.Animation.Storyboard> nachdem es gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="0e40e-103">This example shows how to control a <xref:System.Windows.Media.Animation.Storyboard> after it starts.</span></span> <span data-ttu-id="0e40e-104">Starten einer <xref:System.Windows.Media.Animation.Storyboard> mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], verwenden Sie <xref:System.Windows.Media.Animation.BeginStoryboard>, das verteilt der Animationen an die Objekte und Eigenschaften, die sie animieren, und klicken Sie dann das Storyboard gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="0e40e-104">To start a <xref:System.Windows.Media.Animation.Storyboard> by using [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], use <xref:System.Windows.Media.Animation.BeginStoryboard>, which distributes the animations to the objects and properties they animate and then starts the storyboard.</span></span> <span data-ttu-id="0e40e-105">Wenn Sie geben <xref:System.Windows.Media.Animation.BeginStoryboard> einen Namen durch Angabe der <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> -Eigenschaft, Sie machen es ein steuerbares Storyboard.</span><span class="sxs-lookup"><span data-stu-id="0e40e-105">If you give <xref:System.Windows.Media.Animation.BeginStoryboard> a name by specifying its <xref:System.Windows.Media.Animation.BeginStoryboard.Name%2A> property, you make it a controllable storyboard.</span></span> <span data-ttu-id="0e40e-106">Sie können das Storyboard dann interaktiv steuern, nachdem es gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="0e40e-106">You can then interactively control the storyboard after it starts.</span></span>  
  
 <span data-ttu-id="0e40e-107">Verwenden Sie die folgenden Storyboard Aktionen zusammen mit <xref:System.Windows.EventTrigger> Objekte zum Steuern eines Storyboards.</span><span class="sxs-lookup"><span data-stu-id="0e40e-107">Use the following storyboard actions together with <xref:System.Windows.EventTrigger> objects to control a storyboard.</span></span>  
  
- <span data-ttu-id="0e40e-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Hält das Storyboard an.</span><span class="sxs-lookup"><span data-stu-id="0e40e-108"><xref:System.Windows.Media.Animation.PauseStoryboard>: Pauses the storyboard.</span></span>  
  
- <span data-ttu-id="0e40e-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Setzt ein angehaltenes Storyboard fort.</span><span class="sxs-lookup"><span data-stu-id="0e40e-109"><xref:System.Windows.Media.Animation.ResumeStoryboard>: Resumes a paused storyboard.</span></span>  
  
- <span data-ttu-id="0e40e-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Ändert die Geschwindigkeit des Storyboards.</span><span class="sxs-lookup"><span data-stu-id="0e40e-110"><xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>: Changes the storyboard speed.</span></span>  
  
- <span data-ttu-id="0e40e-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Setzt ein Storyboard an das Ende seines Füllbereichs, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0e40e-111"><xref:System.Windows.Media.Animation.SkipStoryboardToFill>: Advances a storyboard to the end of its fill period, if it has one.</span></span>  
  
- <span data-ttu-id="0e40e-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Hält das Storyboard an.</span><span class="sxs-lookup"><span data-stu-id="0e40e-112"><xref:System.Windows.Media.Animation.StopStoryboard>: Stops the storyboard.</span></span>  
  
- <span data-ttu-id="0e40e-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Entfernt das Storyboard, das Freigeben von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="0e40e-113"><xref:System.Windows.Media.Animation.RemoveStoryboard>: Removes the storyboard, freeing resources.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e40e-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0e40e-114">Example</span></span>  
 <span data-ttu-id="0e40e-115">Im folgenden Beispiel wird die Aktionen des steuerbaren Storyboards zum interaktiven Steuern eines Storyboards.</span><span class="sxs-lookup"><span data-stu-id="0e40e-115">The following example uses controllable storyboard actions to interactively control a storyboard.</span></span>  
  
 <span data-ttu-id="0e40e-116">**Hinweis**: Ein Beispiel zum Steuern eines Storyboards mithilfe von Code finden Sie unter [steuern Sie ein Storyboard nach es beginnt mithilfe von einem interaktiven Methoden](how-to-control-a-storyboard-after-it-starts.md).</span><span class="sxs-lookup"><span data-stu-id="0e40e-116">**Note:** To see an example of controlling a storyboard by using code, see [Control a Storyboard After It Starts Using Its Interactive Methods](how-to-control-a-storyboard-after-it-starts.md).</span></span>  
  
 [!code-xaml[timingbehaviors_snip#ControlStoryboardExampleUsingWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/timingbehaviors_snip/CSharp/ControlStoryboardExample.xaml#controlstoryboardexampleusingwholepage)]  
  
 <span data-ttu-id="0e40e-117">Weitere Beispiele finden Sie unter den [Beispielsammlung](https://go.microsoft.com/fwlink/?LinkID=159969).</span><span class="sxs-lookup"><span data-stu-id="0e40e-117">For additional examples, see the [Animation Example Gallery](https://go.microsoft.com/fwlink/?LinkID=159969).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e40e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e40e-118">See also</span></span>

- <xref:System.Windows.Media.Animation.ResumeStoryboard>
- <xref:System.Windows.Media.Animation.SetStoryboardSpeedRatio>
- <xref:System.Windows.Media.Animation.SkipStoryboardToFill>
- <xref:System.Windows.Media.Animation.PauseStoryboard>
- <xref:System.Windows.Media.Animation.StopStoryboard>
- <xref:System.Windows.Media.Animation.SeekStoryboard>
- [<span data-ttu-id="0e40e-119">Interaktives Steuern eines Storyboards, nachdem es gestartet wurde</span><span class="sxs-lookup"><span data-stu-id="0e40e-119">Control a Storyboard After It Starts Using Its Interactive Methods</span></span>](how-to-control-a-storyboard-after-it-starts.md)
- [<span data-ttu-id="0e40e-120">Übersicht über Animationen</span><span class="sxs-lookup"><span data-stu-id="0e40e-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="0e40e-121">Übersicht über Storyboards</span><span class="sxs-lookup"><span data-stu-id="0e40e-121">Storyboards Overview</span></span>](storyboards-overview.md)
