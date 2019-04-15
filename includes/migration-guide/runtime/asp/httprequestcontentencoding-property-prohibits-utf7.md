---
ms.openlocfilehash: 668d047d3247d64cb1400d4a9ea6887795fa0d44
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235228"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a><span data-ttu-id="e962e-101">HttpRequest.ContentEncoding-Eigenschaft verhindert UTF7</span><span class="sxs-lookup"><span data-stu-id="e962e-101">HttpRequest.ContentEncoding property prohibits UTF7</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e962e-102">Details</span><span class="sxs-lookup"><span data-stu-id="e962e-102">Details</span></span>|<span data-ttu-id="e962e-103">Ab .NET Framework 4.5 ist die UTF-7-Codierung in <xref:System.Web.HttpRequest?displayProperty=name>-Texten nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="e962e-103">Beginning in .NET Framework 4.5, UTF-7 encoding is prohibited in <xref:System.Web.HttpRequest?displayProperty=name>s' bodies.</span></span> <span data-ttu-id="e962e-104">Teilweise treten bei Daten für Anwendungen, die von eingehenden UTF-7-Daten abhängen, Decodierungsprobleme auf.</span><span class="sxs-lookup"><span data-stu-id="e962e-104">Data for applications that depend on incoming UTF-7 data will not decode properly in some cases.</span></span>|
|<span data-ttu-id="e962e-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="e962e-105">Suggestion</span></span>|<span data-ttu-id="e962e-106">Im Idealfall sollten Anwendungen aktualisiert verwenden, damit sie die UTF-7-Codierung in <xref:System.Web.HttpRequest?displayProperty=name> nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="e962e-106">Ideally, applications should be updated to not use UTF-7 encoding in <xref:System.Web.HttpRequest?displayProperty=name>s.</span></span> <span data-ttu-id="e962e-107">Alternativ kann das Legacyverhalten mithilfe des <code>aspnet:AllowUtf7RequestContentEncoding</code>-Attributs des [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md)-Elements wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e962e-107">Alternatively, legacy behavior can be restored by using the <code>aspnet:AllowUtf7RequestContentEncoding</code> attribute of the [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md) element.</span></span>|
|<span data-ttu-id="e962e-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="e962e-108">Scope</span></span>|<span data-ttu-id="e962e-109">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e962e-109">Edge</span></span>|
|<span data-ttu-id="e962e-110">Version</span><span class="sxs-lookup"><span data-stu-id="e962e-110">Version</span></span>|<span data-ttu-id="e962e-111">4.5</span><span class="sxs-lookup"><span data-stu-id="e962e-111">4.5</span></span>|
|<span data-ttu-id="e962e-112">Typ</span><span class="sxs-lookup"><span data-stu-id="e962e-112">Type</span></span>|<span data-ttu-id="e962e-113">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="e962e-113">Runtime</span></span>|
|<span data-ttu-id="e962e-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="e962e-114">Affected APIs</span></span>|<ul><li><xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
