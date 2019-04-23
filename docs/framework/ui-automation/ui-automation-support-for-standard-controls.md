---
title: Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 3fde9779205ea7d0902ddd99ed192f097a159d2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59221478"
---
# <a name="ui-automation-support-for-standard-controls"></a><span data-ttu-id="79da7-102">Benutzeroberflächenautomatisierungs-Unterstützung für Standardsteuerelemente</span><span class="sxs-lookup"><span data-stu-id="79da7-102">UI Automation Support for Standard Controls</span></span>
> [!NOTE]
>  <span data-ttu-id="79da7-103">Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind.</span><span class="sxs-lookup"><span data-stu-id="79da7-103">This documentation is intended for .NET Framework developers who want to use the managed [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="79da7-104">Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).</span><span class="sxs-lookup"><span data-stu-id="79da7-104">For the latest information about [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], see [Windows Automation API: UI Automation](https://go.microsoft.com/fwlink/?LinkID=156746).</span></span>  
  
 <span data-ttu-id="79da7-105">Dieses Thema enthält Informationen zur [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für Standardsteuerelemente in Anwendungen für die Frameworks [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]und [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="79da7-105">This topic contains information about [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] support for standard controls in applications developed for the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)], and [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] frameworks.</span></span>  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a><span data-ttu-id="79da7-106">WPF-Steuerelemente (Windows Presentation Foundation)</span><span class="sxs-lookup"><span data-stu-id="79da7-106">Windows Presentation Foundation Controls</span></span>  
 <span data-ttu-id="79da7-107">Alle [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] -Steuerelemente, die Informationen enthalten oder Benutzerinteraktionen unterstützen, verfügen über eine vollständige systemeigene Unterstützung für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79da7-107">All [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] control elements that provide information or support for user interaction have full native support for [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="79da7-108">Andere Elemente (wie Bereiche) sind für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="79da7-108">Other elements, such as panels, are not visible to [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span>  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a><span data-ttu-id="79da7-109">Win32-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="79da7-109">Win32 Controls</span></span>  
 <span data-ttu-id="79da7-110">Die meisten [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] -Steuerelemente werden über clientseitige Anbieter in „UIAutomationClientsideProviders.dll“ für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="79da7-110">Most [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="79da7-111">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="79da7-111">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="79da7-112">Vollständige Unterstützung gibt es nur für Steuerelemente von Version 6 von „ComCtrl32.dll“ (ab [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] verfügbar).</span><span class="sxs-lookup"><span data-stu-id="79da7-112">Full support is provided only for controls from version 6 of ComCtrl32.dll (available with [!INCLUDE[TLA#tla_winxp](../../../includes/tlasharptla-winxp-md.md)] and later).</span></span>  
  
 <span data-ttu-id="79da7-113">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="79da7-113">The following controls are supported.</span></span>  
  
|<span data-ttu-id="79da7-114">Klassenname</span><span class="sxs-lookup"><span data-stu-id="79da7-114">Class name</span></span>|<span data-ttu-id="79da7-115">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="79da7-115">Control Type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="79da7-116">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="79da7-116">Button</span></span>|<span data-ttu-id="79da7-117">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="79da7-117">Button</span></span>|  
|<span data-ttu-id="79da7-118">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="79da7-118">Button</span></span>|<span data-ttu-id="79da7-119">RadioButton</span><span class="sxs-lookup"><span data-stu-id="79da7-119">RadioButton</span></span>|  
|<span data-ttu-id="79da7-120">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="79da7-120">Button</span></span>|<span data-ttu-id="79da7-121">Gruppieren</span><span class="sxs-lookup"><span data-stu-id="79da7-121">Group</span></span>|  
|<span data-ttu-id="79da7-122">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="79da7-122">Button</span></span>|<span data-ttu-id="79da7-123">CheckBox</span><span class="sxs-lookup"><span data-stu-id="79da7-123">CheckBox</span></span>|  
|<span data-ttu-id="79da7-124">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="79da7-124">Button</span></span>|<span data-ttu-id="79da7-125">Link</span><span class="sxs-lookup"><span data-stu-id="79da7-125">Hyperlink</span></span>|  
|<span data-ttu-id="79da7-126">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="79da7-126">Button</span></span>|<span data-ttu-id="79da7-127">SplitButton</span><span class="sxs-lookup"><span data-stu-id="79da7-127">SplitButton</span></span>|  
|<span data-ttu-id="79da7-128">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="79da7-128">Button</span></span>|<span data-ttu-id="79da7-129">CheckBox</span><span class="sxs-lookup"><span data-stu-id="79da7-129">CheckBox</span></span>|  
|<span data-ttu-id="79da7-130">ComboBoxEx32</span><span class="sxs-lookup"><span data-stu-id="79da7-130">ComboBoxEx32</span></span>|<span data-ttu-id="79da7-131">ComboBox</span><span class="sxs-lookup"><span data-stu-id="79da7-131">ComboBox</span></span>|  
|<span data-ttu-id="79da7-132">ComboBox</span><span class="sxs-lookup"><span data-stu-id="79da7-132">ComboBox</span></span>|<span data-ttu-id="79da7-133">ComboBox</span><span class="sxs-lookup"><span data-stu-id="79da7-133">ComboBox</span></span>|  
|<span data-ttu-id="79da7-134">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="79da7-134">Edit</span></span>|<span data-ttu-id="79da7-135">Dokument</span><span class="sxs-lookup"><span data-stu-id="79da7-135">Document</span></span>|  
|<span data-ttu-id="79da7-136">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="79da7-136">Edit</span></span>|<span data-ttu-id="79da7-137">Bearbeiten</span><span class="sxs-lookup"><span data-stu-id="79da7-137">Edit</span></span>|  
|<span data-ttu-id="79da7-138">SysLink</span><span class="sxs-lookup"><span data-stu-id="79da7-138">SysLink</span></span>|<span data-ttu-id="79da7-139">Link</span><span class="sxs-lookup"><span data-stu-id="79da7-139">Hyperlink</span></span>|  
|<span data-ttu-id="79da7-140">Statisch</span><span class="sxs-lookup"><span data-stu-id="79da7-140">Static</span></span>|<span data-ttu-id="79da7-141">Text</span><span class="sxs-lookup"><span data-stu-id="79da7-141">Text</span></span>|  
|<span data-ttu-id="79da7-142">Statisch</span><span class="sxs-lookup"><span data-stu-id="79da7-142">Static</span></span>|<span data-ttu-id="79da7-143">Bild</span><span class="sxs-lookup"><span data-stu-id="79da7-143">Image</span></span>|  
|<span data-ttu-id="79da7-144">SysIPAddress32</span><span class="sxs-lookup"><span data-stu-id="79da7-144">SysIPAddress32</span></span>|<span data-ttu-id="79da7-145">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="79da7-145">Custom</span></span>|  
|<span data-ttu-id="79da7-146">SysHeader32</span><span class="sxs-lookup"><span data-stu-id="79da7-146">SysHeader32</span></span>|<span data-ttu-id="79da7-147">Header/HeaderItem</span><span class="sxs-lookup"><span data-stu-id="79da7-147">Header/HeaderItem</span></span>|  
|<span data-ttu-id="79da7-148">SysListView32</span><span class="sxs-lookup"><span data-stu-id="79da7-148">SysListView32</span></span>|<span data-ttu-id="79da7-149">DataGrid</span><span class="sxs-lookup"><span data-stu-id="79da7-149">DataGrid</span></span>|  
|<span data-ttu-id="79da7-150">SysListView32</span><span class="sxs-lookup"><span data-stu-id="79da7-150">SysListView32</span></span>|<span data-ttu-id="79da7-151">Liste</span><span class="sxs-lookup"><span data-stu-id="79da7-151">List</span></span>|  
|<span data-ttu-id="79da7-152">ListBox</span><span class="sxs-lookup"><span data-stu-id="79da7-152">ListBox</span></span>|<span data-ttu-id="79da7-153">Liste</span><span class="sxs-lookup"><span data-stu-id="79da7-153">List</span></span>|  
|<span data-ttu-id="79da7-154">ListBox</span><span class="sxs-lookup"><span data-stu-id="79da7-154">ListBox</span></span>|<span data-ttu-id="79da7-155">ListItem</span><span class="sxs-lookup"><span data-stu-id="79da7-155">ListItem</span></span>|  
|<span data-ttu-id="79da7-156">#32768</span><span class="sxs-lookup"><span data-stu-id="79da7-156">#32768</span></span>|<span data-ttu-id="79da7-157">Menü</span><span class="sxs-lookup"><span data-stu-id="79da7-157">Menu</span></span>|  
|<span data-ttu-id="79da7-158">#32768</span><span class="sxs-lookup"><span data-stu-id="79da7-158">#32768</span></span>|<span data-ttu-id="79da7-159">MenuItem</span><span class="sxs-lookup"><span data-stu-id="79da7-159">MenuItem</span></span>|  
|<span data-ttu-id="79da7-160">msctls_progress32</span><span class="sxs-lookup"><span data-stu-id="79da7-160">msctls_progress32</span></span>|<span data-ttu-id="79da7-161">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="79da7-161">ProgressBar</span></span>|  
|<span data-ttu-id="79da7-162">RichEdit</span><span class="sxs-lookup"><span data-stu-id="79da7-162">RichEdit</span></span>|<span data-ttu-id="79da7-163">Dokument.</span><span class="sxs-lookup"><span data-stu-id="79da7-163">Document.</span></span> <span data-ttu-id="79da7-164">Siehe Hinweis.</span><span class="sxs-lookup"><span data-stu-id="79da7-164">See note.</span></span>|  
|<span data-ttu-id="79da7-165">RichEdit20A</span><span class="sxs-lookup"><span data-stu-id="79da7-165">RichEdit20A</span></span>|<span data-ttu-id="79da7-166">Dokument</span><span class="sxs-lookup"><span data-stu-id="79da7-166">Document</span></span>|  
|<span data-ttu-id="79da7-167">RichEdit20W</span><span class="sxs-lookup"><span data-stu-id="79da7-167">RichEdit20W</span></span>|<span data-ttu-id="79da7-168">Dokument</span><span class="sxs-lookup"><span data-stu-id="79da7-168">Document</span></span>|  
|<span data-ttu-id="79da7-169">RichEdit50W</span><span class="sxs-lookup"><span data-stu-id="79da7-169">RichEdit50W</span></span>|<span data-ttu-id="79da7-170">Dokument</span><span class="sxs-lookup"><span data-stu-id="79da7-170">Document</span></span>|  
|<span data-ttu-id="79da7-171">ScrollBar</span><span class="sxs-lookup"><span data-stu-id="79da7-171">ScrollBar</span></span>|<span data-ttu-id="79da7-172">Slider</span><span class="sxs-lookup"><span data-stu-id="79da7-172">Slider</span></span>|  
|<span data-ttu-id="79da7-173">msctls_trackbar32</span><span class="sxs-lookup"><span data-stu-id="79da7-173">msctls_trackbar32</span></span>|<span data-ttu-id="79da7-174">Slider</span><span class="sxs-lookup"><span data-stu-id="79da7-174">Slider</span></span>|  
|<span data-ttu-id="79da7-175">msctls_updown32</span><span class="sxs-lookup"><span data-stu-id="79da7-175">msctls_updown32</span></span>|<span data-ttu-id="79da7-176">Spinner</span><span class="sxs-lookup"><span data-stu-id="79da7-176">Spinner</span></span>|  
|<span data-ttu-id="79da7-177">msctls_statusbar32</span><span class="sxs-lookup"><span data-stu-id="79da7-177">msctls_statusbar32</span></span>|<span data-ttu-id="79da7-178">StatusBar</span><span class="sxs-lookup"><span data-stu-id="79da7-178">StatusBar</span></span>|  
|<span data-ttu-id="79da7-179">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="79da7-179">SysTabControl32</span></span>|<span data-ttu-id="79da7-180">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="79da7-180">Tab</span></span>|  
|<span data-ttu-id="79da7-181">SysTabControl32</span><span class="sxs-lookup"><span data-stu-id="79da7-181">SysTabControl32</span></span>|<span data-ttu-id="79da7-182">TabItem</span><span class="sxs-lookup"><span data-stu-id="79da7-182">TabItem</span></span>|  
|<span data-ttu-id="79da7-183">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="79da7-183">ToolbarWindow32</span></span>|<span data-ttu-id="79da7-184">ToolBar</span><span class="sxs-lookup"><span data-stu-id="79da7-184">ToolBar</span></span>|  
|<span data-ttu-id="79da7-185">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="79da7-185">ToolbarWindow32</span></span>|<span data-ttu-id="79da7-186">MenuItem</span><span class="sxs-lookup"><span data-stu-id="79da7-186">MenuItem</span></span>|  
|<span data-ttu-id="79da7-187">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="79da7-187">ToolbarWindow32</span></span>|<span data-ttu-id="79da7-188">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="79da7-188">Button</span></span>|  
|<span data-ttu-id="79da7-189">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="79da7-189">ToolbarWindow32</span></span>|<span data-ttu-id="79da7-190">CheckBox</span><span class="sxs-lookup"><span data-stu-id="79da7-190">CheckBox</span></span>|  
|<span data-ttu-id="79da7-191">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="79da7-191">ToolbarWindow32</span></span>|<span data-ttu-id="79da7-192">RadioButton</span><span class="sxs-lookup"><span data-stu-id="79da7-192">RadioButton</span></span>|  
|<span data-ttu-id="79da7-193">ToolbarWindow32</span><span class="sxs-lookup"><span data-stu-id="79da7-193">ToolbarWindow32</span></span>|<span data-ttu-id="79da7-194">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="79da7-194">Separator</span></span>|  
|<span data-ttu-id="79da7-195">tooltips_class32</span><span class="sxs-lookup"><span data-stu-id="79da7-195">tooltips_class32</span></span>|<span data-ttu-id="79da7-196">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="79da7-196">ToolTip</span></span>|  
|<span data-ttu-id="79da7-197">#32774</span><span class="sxs-lookup"><span data-stu-id="79da7-197">#32774</span></span>|<span data-ttu-id="79da7-198">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="79da7-198">ToolTip</span></span>|  
|<span data-ttu-id="79da7-199">ReBarWindow32</span><span class="sxs-lookup"><span data-stu-id="79da7-199">ReBarWindow32</span></span>|<span data-ttu-id="79da7-200">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="79da7-200">Toolbar</span></span>|  
|<span data-ttu-id="79da7-201">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="79da7-201">SysTreeView32</span></span>|<span data-ttu-id="79da7-202">Struktur</span><span class="sxs-lookup"><span data-stu-id="79da7-202">Tree</span></span>|  
|<span data-ttu-id="79da7-203">SysTreeView32</span><span class="sxs-lookup"><span data-stu-id="79da7-203">SysTreeView32</span></span>|<span data-ttu-id="79da7-204">TreeItem</span><span class="sxs-lookup"><span data-stu-id="79da7-204">TreeItem</span></span>|  
  
 <span data-ttu-id="79da7-205">**Hinweis** Das RichEdit-Steuerelement wird nur für mit [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] ausgelieferte Versionen unterstützt (in „RichEd20.dll“ ab Version 3.1 und „MsftEdit.dll“ ab Version 4.1).</span><span class="sxs-lookup"><span data-stu-id="79da7-205">**Note** The RichEdit control is supported only for versions shipped with [!INCLUDE[TLA#tla_winvista](../../../includes/tlasharptla-winvista-md.md)] (in RichEd20.dll version 3.1 and later, and MsftEdit.dll version 4.1 and later).</span></span>  
  
 <span data-ttu-id="79da7-206">Die folgenden Steuerelemente werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="79da7-206">The following controls are not supported.</span></span>  
  
|<span data-ttu-id="79da7-207">Klassenname</span><span class="sxs-lookup"><span data-stu-id="79da7-207">Class name</span></span>|<span data-ttu-id="79da7-208">Steuerelementtyp</span><span class="sxs-lookup"><span data-stu-id="79da7-208">Control type</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="79da7-209">SysAnimate32</span><span class="sxs-lookup"><span data-stu-id="79da7-209">SysAnimate32</span></span>|<span data-ttu-id="79da7-210">Bild</span><span class="sxs-lookup"><span data-stu-id="79da7-210">Image</span></span>|  
|<span data-ttu-id="79da7-211">SysPager</span><span class="sxs-lookup"><span data-stu-id="79da7-211">SysPager</span></span>|<span data-ttu-id="79da7-212">Spinner</span><span class="sxs-lookup"><span data-stu-id="79da7-212">Spinner</span></span>|  
|<span data-ttu-id="79da7-213">SysDateTimePick32</span><span class="sxs-lookup"><span data-stu-id="79da7-213">SysDateTimePick32</span></span>|<span data-ttu-id="79da7-214">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="79da7-214">Custom</span></span>|  
|<span data-ttu-id="79da7-215">SysMonthCal32</span><span class="sxs-lookup"><span data-stu-id="79da7-215">SysMonthCal32</span></span>|<span data-ttu-id="79da7-216">Kalender</span><span class="sxs-lookup"><span data-stu-id="79da7-216">Calendar</span></span>|  
|<span data-ttu-id="79da7-217">MS_WINNOTE</span><span class="sxs-lookup"><span data-stu-id="79da7-217">MS_WINNOTE</span></span>|<span data-ttu-id="79da7-218">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="79da7-218">Tooltip</span></span>|  
|<span data-ttu-id="79da7-219">VBBubble</span><span class="sxs-lookup"><span data-stu-id="79da7-219">VBBubble</span></span>|<span data-ttu-id="79da7-220">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="79da7-220">Tooltip</span></span>|  
|<span data-ttu-id="79da7-221">ScrollBar (wenn als eigenständiges Steuerelement verwendet)</span><span class="sxs-lookup"><span data-stu-id="79da7-221">ScrollBar (when used as a standalone control)</span></span>|<span data-ttu-id="79da7-222">Slider</span><span class="sxs-lookup"><span data-stu-id="79da7-222">Slider</span></span>|  
|<span data-ttu-id="79da7-223">SuperGrid</span><span class="sxs-lookup"><span data-stu-id="79da7-223">SuperGrid</span></span>|<span data-ttu-id="79da7-224">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="79da7-224">Custom</span></span>|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a><span data-ttu-id="79da7-225">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="79da7-225">Windows Forms Controls</span></span>  
 <span data-ttu-id="79da7-226">Windows Forms-Steuerelemente werden verfügbar gemacht, um [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] über clientseitige Anbieter in "UIAutomationClientsideProviders.dll".</span><span class="sxs-lookup"><span data-stu-id="79da7-226">Windows Forms controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] through client-side providers in UIAutomationClientsideProviders.dll.</span></span> <span data-ttu-id="79da7-227">Diese Assembly wird automatisch für die Verwendung mit Benutzeroberflächenautomatisierungs-Clientanwendungen registriert.</span><span class="sxs-lookup"><span data-stu-id="79da7-227">This assembly is automatically registered for use with UI Automation client applications.</span></span>  
  
 <span data-ttu-id="79da7-228">Windows Forms-Steuerelemente, die Sie in der Regel die verwaltete Wrapper für [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] allgemeine Steuerelemente werden von unterstützt [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span><span class="sxs-lookup"><span data-stu-id="79da7-228">Typically, Windows Forms controls that are managed wrappers for [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] common controls are supported by [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)].</span></span> <span data-ttu-id="79da7-229">Die folgenden Steuerelemente werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="79da7-229">The following controls are supported.</span></span>  
  
|<span data-ttu-id="79da7-230">Klassenname</span><span class="sxs-lookup"><span data-stu-id="79da7-230">Class Name</span></span>|  
|----------------|  
|<span data-ttu-id="79da7-231">Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="79da7-231">Button</span></span>|  
|<span data-ttu-id="79da7-232">CheckBox</span><span class="sxs-lookup"><span data-stu-id="79da7-232">CheckBox</span></span>|  
|<span data-ttu-id="79da7-233">CheckedListBox</span><span class="sxs-lookup"><span data-stu-id="79da7-233">CheckedListBox</span></span>|  
|<span data-ttu-id="79da7-234">ColorDialog</span><span class="sxs-lookup"><span data-stu-id="79da7-234">ColorDialog</span></span>|  
|<span data-ttu-id="79da7-235">ComboBox</span><span class="sxs-lookup"><span data-stu-id="79da7-235">ComboBox</span></span>|  
|<span data-ttu-id="79da7-236">FolderBrowser</span><span class="sxs-lookup"><span data-stu-id="79da7-236">FolderBrowser</span></span>|  
|<span data-ttu-id="79da7-237">FontDialog</span><span class="sxs-lookup"><span data-stu-id="79da7-237">FontDialog</span></span>|  
|<span data-ttu-id="79da7-238">GroupBox</span><span class="sxs-lookup"><span data-stu-id="79da7-238">GroupBox</span></span>|  
|<span data-ttu-id="79da7-239">HscrollBar</span><span class="sxs-lookup"><span data-stu-id="79da7-239">HscrollBar</span></span>|  
|<span data-ttu-id="79da7-240">ImageList</span><span class="sxs-lookup"><span data-stu-id="79da7-240">ImageList</span></span>|  
|<span data-ttu-id="79da7-241">Bezeichnung</span><span class="sxs-lookup"><span data-stu-id="79da7-241">Label</span></span>|  
|<span data-ttu-id="79da7-242">ListBox</span><span class="sxs-lookup"><span data-stu-id="79da7-242">ListBox</span></span>|  
|<span data-ttu-id="79da7-243">ListView</span><span class="sxs-lookup"><span data-stu-id="79da7-243">ListView</span></span>|  
|<span data-ttu-id="79da7-244">MainMenu/ContextMenu</span><span class="sxs-lookup"><span data-stu-id="79da7-244">MainMenu/ContextMenu</span></span>|  
|<span data-ttu-id="79da7-245">MonthCalendar</span><span class="sxs-lookup"><span data-stu-id="79da7-245">MonthCalendar</span></span>|  
|<span data-ttu-id="79da7-246">NotifyIcon</span><span class="sxs-lookup"><span data-stu-id="79da7-246">NotifyIcon</span></span>|  
|<span data-ttu-id="79da7-247">OpenFileDialog</span><span class="sxs-lookup"><span data-stu-id="79da7-247">OpenFileDialog</span></span>|  
|<span data-ttu-id="79da7-248">PageSetupDialog</span><span class="sxs-lookup"><span data-stu-id="79da7-248">PageSetupDialog</span></span>|  
|<span data-ttu-id="79da7-249">PrintDialog</span><span class="sxs-lookup"><span data-stu-id="79da7-249">PrintDialog</span></span>|  
|<span data-ttu-id="79da7-250">ProgressBar</span><span class="sxs-lookup"><span data-stu-id="79da7-250">ProgressBar</span></span>|  
|<span data-ttu-id="79da7-251">RadioButton</span><span class="sxs-lookup"><span data-stu-id="79da7-251">RadioButton</span></span>|  
|<span data-ttu-id="79da7-252">RichTextBox</span><span class="sxs-lookup"><span data-stu-id="79da7-252">RichTextBox</span></span>|  
|<span data-ttu-id="79da7-253">SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="79da7-253">SaveFileDialog</span></span>|  
|<span data-ttu-id="79da7-254">ScrollableControl</span><span class="sxs-lookup"><span data-stu-id="79da7-254">ScrollableControl</span></span>|  
|<span data-ttu-id="79da7-255">SoundPlayer</span><span class="sxs-lookup"><span data-stu-id="79da7-255">SoundPlayer</span></span>|  
|<span data-ttu-id="79da7-256">StatusBar</span><span class="sxs-lookup"><span data-stu-id="79da7-256">StatusBar</span></span>|  
|<span data-ttu-id="79da7-257">TabControl/TabPage</span><span class="sxs-lookup"><span data-stu-id="79da7-257">TabControl/TabPage</span></span>|  
|<span data-ttu-id="79da7-258">TextBox</span><span class="sxs-lookup"><span data-stu-id="79da7-258">TextBox</span></span>|  
|<span data-ttu-id="79da7-259">Zeitgeber</span><span class="sxs-lookup"><span data-stu-id="79da7-259">Timer</span></span>|  
|<span data-ttu-id="79da7-260">ToolBar</span><span class="sxs-lookup"><span data-stu-id="79da7-260">Toolbar</span></span>|  
|<span data-ttu-id="79da7-261">QuickInfo</span><span class="sxs-lookup"><span data-stu-id="79da7-261">ToolTip</span></span>|  
|<span data-ttu-id="79da7-262">TrackBar</span><span class="sxs-lookup"><span data-stu-id="79da7-262">TrackBar</span></span>|  
|<span data-ttu-id="79da7-263">TreeView</span><span class="sxs-lookup"><span data-stu-id="79da7-263">TreeView</span></span>|  
|<span data-ttu-id="79da7-264">VscrollBar</span><span class="sxs-lookup"><span data-stu-id="79da7-264">VscrollBar</span></span>|  
|<span data-ttu-id="79da7-265">Webbrowser</span><span class="sxs-lookup"><span data-stu-id="79da7-265">WebBrowser</span></span>|  
  
 <span data-ttu-id="79da7-266">Die folgenden Steuerelemente sind für [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] nur über ihre Unterstützung für [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)]verfügbar.</span><span class="sxs-lookup"><span data-stu-id="79da7-266">The following controls are exposed to [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] only through their support for [!INCLUDE[TLA#tla_aa](../../../includes/tlasharptla-aa-md.md)].</span></span> <span data-ttu-id="79da7-267">Möglicherweise sind nicht alle Funktionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="79da7-267">Some functionality may not be available.</span></span>  
  
|<span data-ttu-id="79da7-268">Steuerelementname</span><span class="sxs-lookup"><span data-stu-id="79da7-268">Control Name</span></span>|  
|------------------|  
|<span data-ttu-id="79da7-269">BindingSource</span><span class="sxs-lookup"><span data-stu-id="79da7-269">BindingSource</span></span>|  
|<span data-ttu-id="79da7-270">DataGrid</span><span class="sxs-lookup"><span data-stu-id="79da7-270">DataGrid</span></span>|  
|<span data-ttu-id="79da7-271">DataGridView</span><span class="sxs-lookup"><span data-stu-id="79da7-271">DataGridView</span></span>|  
|<span data-ttu-id="79da7-272">DataNavigator</span><span class="sxs-lookup"><span data-stu-id="79da7-272">DataNavigator</span></span>|  
|<span data-ttu-id="79da7-273">DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="79da7-273">DomainUpDown</span></span>|  
|<span data-ttu-id="79da7-274">ErrorProvider</span><span class="sxs-lookup"><span data-stu-id="79da7-274">ErrorProvider</span></span>|  
|<span data-ttu-id="79da7-275">FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="79da7-275">FlowLayoutPanel</span></span>|  
|<span data-ttu-id="79da7-276">Formular</span><span class="sxs-lookup"><span data-stu-id="79da7-276">Form</span></span>|  
|<span data-ttu-id="79da7-277">LinkLabel</span><span class="sxs-lookup"><span data-stu-id="79da7-277">LinkLabel</span></span>|  
|<span data-ttu-id="79da7-278">HelpProvider</span><span class="sxs-lookup"><span data-stu-id="79da7-278">HelpProvider</span></span>|  
|<span data-ttu-id="79da7-279">MaskedTextBox</span><span class="sxs-lookup"><span data-stu-id="79da7-279">MaskedTextBox</span></span>|  
|<span data-ttu-id="79da7-280">MenuStrip/ContextMenuStrip</span><span class="sxs-lookup"><span data-stu-id="79da7-280">MenuStrip/ContextMenuStrip</span></span>|  
|<span data-ttu-id="79da7-281">NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="79da7-281">NumericUpDown</span></span>|  
|<span data-ttu-id="79da7-282">Bereich</span><span class="sxs-lookup"><span data-stu-id="79da7-282">Panel</span></span>|  
|<span data-ttu-id="79da7-283">PictureBox</span><span class="sxs-lookup"><span data-stu-id="79da7-283">PictureBox</span></span>|  
|<span data-ttu-id="79da7-284">PrintDocument</span><span class="sxs-lookup"><span data-stu-id="79da7-284">PrintDocument</span></span>|  
|<span data-ttu-id="79da7-285">PrintPreview-Control</span><span class="sxs-lookup"><span data-stu-id="79da7-285">PrintPreview-Control</span></span>|  
|<span data-ttu-id="79da7-286">PrintPreview-Dialog</span><span class="sxs-lookup"><span data-stu-id="79da7-286">PrintPreview-Dialog</span></span>|  
|<span data-ttu-id="79da7-287">PropertyGrid</span><span class="sxs-lookup"><span data-stu-id="79da7-287">PropertyGrid</span></span>|  
|<span data-ttu-id="79da7-288">UserControl</span><span class="sxs-lookup"><span data-stu-id="79da7-288">UserControl</span></span>|  
|<span data-ttu-id="79da7-289">ToolStrip</span><span class="sxs-lookup"><span data-stu-id="79da7-289">ToolStrip</span></span>|  
|<span data-ttu-id="79da7-290">TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="79da7-290">TableLayoutPanel</span></span>|  
|<span data-ttu-id="79da7-291">SplitContainer/SplitterPanel</span><span class="sxs-lookup"><span data-stu-id="79da7-291">SplitContainer/SplitterPanel</span></span>|  
|<span data-ttu-id="79da7-292">Aufteilung</span><span class="sxs-lookup"><span data-stu-id="79da7-292">Splitter</span></span>|  
|<span data-ttu-id="79da7-293">RaftingContainer</span><span class="sxs-lookup"><span data-stu-id="79da7-293">RaftingContainer</span></span>|  
|<span data-ttu-id="79da7-294">StatusStrip</span><span class="sxs-lookup"><span data-stu-id="79da7-294">StatusStrip</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="79da7-295">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79da7-295">See also</span></span>

- [<span data-ttu-id="79da7-296">Steuerelementtypen der Benutzeroberflächenautomatisierung</span><span class="sxs-lookup"><span data-stu-id="79da7-296">UI Automation Control Types</span></span>](../../../docs/framework/ui-automation/ui-automation-control-types.md)
