---
ms.openlocfilehash: e600b8249096eecb13f63ea00343a771a8c12b60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804075"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="240b8-101">HtmlTextWriter rendert das Element `<br/>` nicht ordnungsgemäß</span><span class="sxs-lookup"><span data-stu-id="240b8-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="240b8-102">Details</span><span class="sxs-lookup"><span data-stu-id="240b8-102">Details</span></span>|<span data-ttu-id="240b8-103">Ab .NET Framework 4.6 fügt der Aufruf von <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> und <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> mit einem <code>&lt;BR /&gt;</code>-Element ordnungsgemäß nur ein (anstatt zwei) <code>&lt;BR /&gt;</code> ein.</span><span class="sxs-lookup"><span data-stu-id="240b8-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a <code>&lt;BR /&gt;</code> element will correctly insert only one <code>&lt;BR /&gt;</code> (instead of two)</span></span>|
|<span data-ttu-id="240b8-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="240b8-104">Suggestion</span></span>|<span data-ttu-id="240b8-105">Wenn eine App vom zusätzlichen <code>&lt;BR /&gt;</code>-Tag abhängig ist, sollte <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> ein zweites Mal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="240b8-105">If an app depended on the extra <code>&lt;BR /&gt;</code> tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="240b8-106">Beachten Sie, das sich diese Verhaltensänderung nur auf Apps mit der Zielplattform .NET Framework 4.6 oder höher auswirkt. Eine weitere Möglichkeit ist daher die Ausrichtung auf eine vorherige Version von .NET Framework, mit der das alte Verhalten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="240b8-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>|
|<span data-ttu-id="240b8-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="240b8-107">Scope</span></span>|<span data-ttu-id="240b8-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="240b8-108">Edge</span></span>|
|<span data-ttu-id="240b8-109">Version</span><span class="sxs-lookup"><span data-stu-id="240b8-109">Version</span></span>|<span data-ttu-id="240b8-110">4.6</span><span class="sxs-lookup"><span data-stu-id="240b8-110">4.6</span></span>|
|<span data-ttu-id="240b8-111">Typ</span><span class="sxs-lookup"><span data-stu-id="240b8-111">Type</span></span>|<span data-ttu-id="240b8-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="240b8-112">Retargeting</span></span>|
|<span data-ttu-id="240b8-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="240b8-113">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|
