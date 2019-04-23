---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: 30084143949d2243fd310448c52e6b861505ad66
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191249"
---
# <a name="getcustomui"></a><span data-ttu-id="80f74-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="80f74-102">GetCustomUI</span></span>
<span data-ttu-id="80f74-103">Vom PresentationHost.exe abzurufenden benutzerdefinierte Status- und Fehlermeldungen vom Host aufgerufen, wenn es sich bei implementiert.</span><span class="sxs-lookup"><span data-stu-id="80f74-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80f74-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="80f74-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="80f74-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="80f74-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="80f74-106">[out] Ein Zeiger auf die Assembly mit dem Host bereitgestellte tasksequenzstatus-Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="80f74-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="80f74-107">[out] Der Name der Klasse an, die Benutzeroberfläche für den Host bereitgestellter Status, vorzugsweise einen [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] -Datei mit <xref:System.Windows.Controls.Page> Element der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="80f74-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="80f74-108">Diese Klasse befindet sich in der Assembly, die angegebenen `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="80f74-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="80f74-109">[out] Ein Zeiger auf die Assembly, die die Benutzeroberfläche für den Host angegebene Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="80f74-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="80f74-110">[out] Der Name der Klasse, die der Host angegebene Benutzer ist Schnittstelle, von denen vorzugsweise eine XAML-Datei mit <xref:System.Windows.Controls.Page> Element der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="80f74-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="80f74-111">Diese Klasse befindet sich in der Assembly, die angegebenen `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="80f74-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="80f74-112">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="80f74-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="80f74-113">HRESULT: Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="80f74-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="80f74-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="80f74-114">Remarks</span></span>  
 <span data-ttu-id="80f74-115">Eine hostanwendung möglicherweise ein bestimmtes Design, dem die PresentationHost.exe standardmäßigen Benutzeroberflächen von nicht entspricht.</span><span class="sxs-lookup"><span data-stu-id="80f74-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="80f74-116">Wenn dies der Fall ist, kann die hostanwendung implementieren [GetCustomUI](getcustomui.md) Status- und Benutzeroberflächen für PresentationHost.exe zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="80f74-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="80f74-117">Rufen Sie PresentationHost.exe wird immer [GetCustomUI](getcustomui.md) vor der Verwendung der standardmäßigen Benutzeroberflächen.</span><span class="sxs-lookup"><span data-stu-id="80f74-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="80f74-118">Diese Funktion wird einmal während der Initialisierung von PresentationHost aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="80f74-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80f74-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80f74-119">See also</span></span>

- [<span data-ttu-id="80f74-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="80f74-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
