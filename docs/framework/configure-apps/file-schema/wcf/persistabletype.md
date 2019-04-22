---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 939a29e90ee21e94ccb78842d6f7224e9a6288d0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083737"
---
# <a name="persistabletype"></a><span data-ttu-id="ec0ca-101">\<persistableType></span><span class="sxs-lookup"><span data-stu-id="ec0ca-101">\<persistableType></span></span>
<span data-ttu-id="ec0ca-102">Gibt alle dauerhaften Typen an.</span><span class="sxs-lookup"><span data-stu-id="ec0ca-102">Specifies all the persistable types.</span></span>  
  
 <span data-ttu-id="ec0ca-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="ec0ca-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="ec0ca-104">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="ec0ca-104">\<comContracts></span></span>  
<span data-ttu-id="ec0ca-105">\<comContract></span><span class="sxs-lookup"><span data-stu-id="ec0ca-105">\<comContract></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec0ca-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec0ca-106">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a><span data-ttu-id="ec0ca-107">Typ</span><span class="sxs-lookup"><span data-stu-id="ec0ca-107">Type</span></span>  
 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec0ca-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ec0ca-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ec0ca-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ec0ca-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec0ca-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ec0ca-110">Attributes</span></span>  
  
|<span data-ttu-id="ec0ca-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ec0ca-111">Attribute</span></span>|<span data-ttu-id="ec0ca-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec0ca-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ec0ca-113">id</span><span class="sxs-lookup"><span data-stu-id="ec0ca-113">id</span></span>|<span data-ttu-id="ec0ca-114">Ein erforderliches Attribut, das eine Zeichenfolge enthält, die einen eindeutigen Bezeichner für einen dauerhaften Typ angibt.</span><span class="sxs-lookup"><span data-stu-id="ec0ca-114">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="ec0ca-115">Name</span><span class="sxs-lookup"><span data-stu-id="ec0ca-115">name</span></span>|<span data-ttu-id="ec0ca-116">Ein optionales Attribut, das eine Zeichenfolge enthält, die den Namen des dauerhaften Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="ec0ca-116">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ec0ca-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ec0ca-117">Child Elements</span></span>  
 <span data-ttu-id="ec0ca-118">Keiner</span><span class="sxs-lookup"><span data-stu-id="ec0ca-118">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ec0ca-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ec0ca-119">Parent Elements</span></span>  
  
|<span data-ttu-id="ec0ca-120">Element</span><span class="sxs-lookup"><span data-stu-id="ec0ca-120">Element</span></span>|<span data-ttu-id="ec0ca-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec0ca-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec0ca-122">\<persistableTypes></span><span class="sxs-lookup"><span data-stu-id="ec0ca-122">\<persistableTypes></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/persistabletypes.md)|<span data-ttu-id="ec0ca-123">Eine Auflistung von `persistableType`-Elementen.</span><span class="sxs-lookup"><span data-stu-id="ec0ca-123">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ec0ca-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec0ca-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [<span data-ttu-id="ec0ca-125">\<comContracts></span><span class="sxs-lookup"><span data-stu-id="ec0ca-125">\<comContracts></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)
- [<span data-ttu-id="ec0ca-126">Integrieren von COM+-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ec0ca-126">Integrating with COM+ Applications</span></span>](../../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="ec0ca-127">Vorgehensweise: Konfigurieren von COM+-Diensteinstellungen</span><span class="sxs-lookup"><span data-stu-id="ec0ca-127">How to: Configure COM+ Service Settings</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-configure-com-service-settings.md)
