---
title: Verwenden des verwalteten HTML-Dokumentobjektmodells
ms.date: 03/30/2017
helpviewer_keywords:
- managed HTML DOM
ms.assetid: a017dd5c-cd7b-47e4-952c-f4f54cb48409
ms.openlocfilehash: fe84cabfaabdc14c7dec6cb69653d41b4c6f6416
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65590167"
---
# <a name="using-the-managed-html-document-object-model"></a><span data-ttu-id="0b100-102">Verwenden des verwalteten HTML-Dokumentobjektmodells</span><span class="sxs-lookup"><span data-stu-id="0b100-102">Using the Managed HTML Document Object Model</span></span>
<span data-ttu-id="0b100-103">Das verwaltete HTML Document Object Model (DOM) bietet es sich um einen Wrapper, die basierend auf .NET Framework für die HTML-Klassen, die von Internet Explorer verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="0b100-103">The managed HTML document object model (DOM) provides a wrapper based on the .NET Framework for the HTML classes exposed by Internet Explorer.</span></span> <span data-ttu-id="0b100-104">Verwenden Sie diese Klassen zum Bearbeiten von HTML-Seiten gehostet werden, der <xref:System.Windows.Forms.WebBrowser> -Steuerelement, oder um neue Seiten vom Anfang zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b100-104">Use these classes to manipulate HTML pages hosted in the <xref:System.Windows.Forms.WebBrowser> control, or to build new pages from the beginning.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b100-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0b100-105">In This Section</span></span>  
 [<span data-ttu-id="0b100-106">Vorgehensweise: Zugriff auf das verwaltete HTML-Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="0b100-106">How to: Access the Managed HTML Document Object Model</span></span>](how-to-access-the-managed-html-document-object-model.md)  
 <span data-ttu-id="0b100-107">Beschreibt, wie Sie eine gültige Instanz des erhalten <xref:System.Windows.Forms.HtmlDocument> aus einer Windows Forms-Anwendung oder ein <xref:System.Windows.Forms.UserControl> in Internet Explorer gehostet.</span><span class="sxs-lookup"><span data-stu-id="0b100-107">Describes how to obtain a valid instance of <xref:System.Windows.Forms.HtmlDocument> from either a Windows Forms application or a <xref:System.Windows.Forms.UserControl> hosted in Internet Explorer.</span></span>  
  
 [<span data-ttu-id="0b100-108">Vorgehensweise: Zugreifen auf den HTML-Quellcode im verwalteten HTML-Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="0b100-108">How to: Access the HTML Source in the Managed HTML Document Object Model</span></span>](how-to-access-the-html-source-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="0b100-109">Beschreibt, wie Sie die ursprüngliche, nicht modifiziertes HTML-Quelle zu erhalten, und wie Sie die "live"-Quelle zu erhalten, die den aktuellen Zustand des DOM widerspiegelt</span><span class="sxs-lookup"><span data-stu-id="0b100-109">Describes how to obtain the original, unmodified HTML source, and how to obtain the "live" source that reflects the current state of the DOM.</span></span>  
  
 [<span data-ttu-id="0b100-110">Vorgehensweise: Ändern von Formaten eines Elements im verwalteten HTML-Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="0b100-110">How to: Change Styles on an Element in the Managed HTML Document Object Model</span></span>](how-to-change-styles-on-an-element-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="0b100-111">Beschreibt die Formate bearbeiten, die zur Steuerung der visuellen Darstellung von Elementen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0b100-111">Describes how to manipulate styles, which are used to control the visual display of elements.</span></span>  
  
 [<span data-ttu-id="0b100-112">Zugreifen auf Frames im verwalteten HTML-Dokumentobjektmodell</span><span class="sxs-lookup"><span data-stu-id="0b100-112">Accessing Frames in the Managed HTML Document Object Model</span></span>](accessing-frames-in-the-managed-html-document-object-model.md)  
 <span data-ttu-id="0b100-113">Beschreibt, welche Frames und Framesets sind und wie Sie den Zugriff auf das DOM eines Rahmens.</span><span class="sxs-lookup"><span data-stu-id="0b100-113">Describes what frames and framesets are, and how to access the DOM of a frame.</span></span>  
  
 [<span data-ttu-id="0b100-114">Zugreifen auf nicht verfügbar gemachte Member des verwalteten HTML-Dokumentobjektmodells</span><span class="sxs-lookup"><span data-stu-id="0b100-114">Accessing Unexposed Members on the Managed HTML Document Object Model</span></span>](accessing-unexposed-members-on-the-managed-html-document-object-model.md)  
 <span data-ttu-id="0b100-115">Beschreibt, wie Member des zugrunde liegenden DOM zuzugreifen, die nicht über eine verwaltete Entsprechung verfügen.</span><span class="sxs-lookup"><span data-stu-id="0b100-115">Describes how to access members of the underlying DOM that do not have a managed equivalent.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0b100-116">Referenz</span><span class="sxs-lookup"><span data-stu-id="0b100-116">Reference</span></span>  
 <xref:System.Windows.Forms.HtmlDocument>  
  
 <xref:System.Windows.Forms.HtmlElement>  
  
 <xref:System.Windows.Forms.HtmlWindow>  
  
## <a name="related-sections"></a><span data-ttu-id="0b100-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="0b100-117">Related Sections</span></span>  
 [<span data-ttu-id="0b100-118">WebBrowser-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0b100-118">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)  
