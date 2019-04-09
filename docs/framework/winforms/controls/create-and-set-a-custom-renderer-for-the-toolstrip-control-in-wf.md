---
title: 'Vorgehensweise: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: d8a85edf8c001b19191fdfd74d1f9ebdf87024ab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195487"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="36bbf-102">Vorgehensweise: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="36bbf-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<xref:System.Windows.Forms.ToolStrip> <span data-ttu-id="36bbf-103">Steuerelemente ermöglichen die einfache Unterstützung von Designs und Stilen.</span><span class="sxs-lookup"><span data-stu-id="36bbf-103">controls give easy support to themes and styles.</span></span> <span data-ttu-id="36bbf-104">Sie können die vollkommen benutzerdefinierte Aussehen und Verhalten (Aussehen und Verhalten) erreichen, indem Sie die Einstellung der <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> Eigenschaft oder das <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> Eigenschaft, um einen benutzerdefinierten Renderer.</span><span class="sxs-lookup"><span data-stu-id="36bbf-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="36bbf-105">Sie können jedes einzelne Renderer zuweisen <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, oder <xref:System.Windows.Forms.StatusStrip> -Steuerelement, oder Sie können die <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> Eigenschaft, um alle Objekte durch Festlegen der <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> Eigenschaft <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="36bbf-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> <span data-ttu-id="36bbf-106">Gibt <xref:System.Windows.Forms.ToolStripRenderMode.Custom> nur, wenn der Wert des <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> nicht `null`.</span><span class="sxs-lookup"><span data-stu-id="36bbf-106">returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="36bbf-107">Erstellen ein benutzerdefiniertes Renderers</span><span class="sxs-lookup"><span data-stu-id="36bbf-107">To create a custom renderer</span></span>  
  
1.  <span data-ttu-id="36bbf-108">Erweitern Sie die <xref:System.Windows.Forms.ToolStripRenderer> Klasse.</span><span class="sxs-lookup"><span data-stu-id="36bbf-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2.  <span data-ttu-id="36bbf-109">Implementieren Sie den gewünschten benutzerdefinierten Renderer, durch das Überschreiben die entsprechenden *auf...*</span><span class="sxs-lookup"><span data-stu-id="36bbf-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="36bbf-110">Member</span><span class="sxs-lookup"><span data-stu-id="36bbf-110">members</span></span>  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)   
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="36bbf-111">Um den benutzerdefinierten Renderer zum aktuellen Renderer</span><span class="sxs-lookup"><span data-stu-id="36bbf-111">To set the custom renderer to be the current renderer</span></span>  
  
1.  <span data-ttu-id="36bbf-112">Um den benutzerdefinierten Renderer für eine <xref:System.Windows.Forms.ToolStrip>legen die <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> Eigenschaft, um den benutzerdefinierten Renderer.</span><span class="sxs-lookup"><span data-stu-id="36bbf-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2.  <span data-ttu-id="36bbf-113">Oder legen Sie den benutzerdefinierten Renderer für alle <xref:System.Windows.Forms.ToolStrip> in Ihrer Anwendung enthaltenen Klassen: Legen Sie die <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> Eigenschaft auf den benutzerdefinierten Renderer und legen die <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> Eigenschaft <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span><span class="sxs-lookup"><span data-stu-id="36bbf-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="36bbf-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36bbf-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="36bbf-115">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="36bbf-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="36bbf-116">Architektur des ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="36bbf-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="36bbf-117">Zusammenfassung der ToolStrip-Technologie</span><span class="sxs-lookup"><span data-stu-id="36bbf-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
