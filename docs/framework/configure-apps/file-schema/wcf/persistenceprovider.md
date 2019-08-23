---
title: <persistenceProvider>
ms.date: 03/30/2017
ms.assetid: a37049c5-a7ea-4519-94f2-912eeb010380
ms.openlocfilehash: 4fc9e1332effc51e183a84cf2d3653357277d2ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934140"
---
# <a name="persistenceprovider"></a><span data-ttu-id="2cb19-101">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="2cb19-101">\<persistenceProvider></span></span>
<span data-ttu-id="2cb19-102">Gibt den Typ der zu verwendenden Persistenzanbieterimplementierung sowie das Timeout für Persistenzvorgänge an.</span><span class="sxs-lookup"><span data-stu-id="2cb19-102">Specifies the type of the persistence provider implementation to use, as well as the time-out to use for persistence operations.</span></span>  
  
 <span data-ttu-id="2cb19-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2cb19-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="2cb19-104">\<behaviors></span><span class="sxs-lookup"><span data-stu-id="2cb19-104">\<behaviors></span></span>  
<span data-ttu-id="2cb19-105">\<serviceBehaviors></span><span class="sxs-lookup"><span data-stu-id="2cb19-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="2cb19-106">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2cb19-106">\<behavior></span></span>  
<span data-ttu-id="2cb19-107">\<persistenceProvider></span><span class="sxs-lookup"><span data-stu-id="2cb19-107">\<persistenceProvider></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cb19-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="2cb19-108">Syntax</span></span>  
  
```xml  
<persistenceProvider persistenceOperationTimeout="TimeSpan"
                     type="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2cb19-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2cb19-109">Attributes and Elements</span></span>  
 <span data-ttu-id="2cb19-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2cb19-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2cb19-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="2cb19-111">Attributes</span></span>  
  
|<span data-ttu-id="2cb19-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="2cb19-112">Attribute</span></span>|<span data-ttu-id="2cb19-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cb19-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2cb19-114">persistenceOperationTimeout</span><span class="sxs-lookup"><span data-stu-id="2cb19-114">persistenceOperationTimeout</span></span>|<span data-ttu-id="2cb19-115">Ein <xref:System.TimeSpan>-Wert, der das Timeout angibt, das für Persistenzvorgänge verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2cb19-115">A <xref:System.TimeSpan> value that specifies the time-out used for persistence operations.</span></span> <span data-ttu-id="2cb19-116">Der Standardwert ist "00:00:30".</span><span class="sxs-lookup"><span data-stu-id="2cb19-116">The default is "00:00:30".</span></span>|  
|<span data-ttu-id="2cb19-117">Typ</span><span class="sxs-lookup"><span data-stu-id="2cb19-117">type</span></span>|<span data-ttu-id="2cb19-118">Eine Zeichenfolge, die den Typ der zu verwendenden Persistenz-Providerfactory angibt.</span><span class="sxs-lookup"><span data-stu-id="2cb19-118">A string that specifies the type of the persistence provider factory to use.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2cb19-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cb19-119">Child Elements</span></span>  
 <span data-ttu-id="2cb19-120">Keine</span><span class="sxs-lookup"><span data-stu-id="2cb19-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2cb19-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2cb19-121">Parent Elements</span></span>  
  
|<span data-ttu-id="2cb19-122">Element</span><span class="sxs-lookup"><span data-stu-id="2cb19-122">Element</span></span>|<span data-ttu-id="2cb19-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cb19-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2cb19-124">\<behavior></span><span class="sxs-lookup"><span data-stu-id="2cb19-124">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="2cb19-125">Gibt ein Verhaltenselement an.</span><span class="sxs-lookup"><span data-stu-id="2cb19-125">Specifies a behavior element.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cb19-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2cb19-126">Remarks</span></span>  
 <span data-ttu-id="2cb19-127">Dieses Element gibt den Persistenz-Provider an, der verwendet werden soll, um den Zustand eines WCF-Dienstes zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="2cb19-127">This element specifies the persistence provider to be used to serialize the state of a WCF service.</span></span> <span data-ttu-id="2cb19-128">Es sollte zusammen mit der `wsHttpContextBinding` verwendet werden, die Zustandsinformationen in HTTP-Headern übergibt.</span><span class="sxs-lookup"><span data-stu-id="2cb19-128">It should be used together with the `wsHttpContextBinding` which passes state information in HTTP headers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cb19-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cb19-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PersistenceProviderElement>
- <xref:System.ServiceModel.Persistence.PersistenceProvider>
