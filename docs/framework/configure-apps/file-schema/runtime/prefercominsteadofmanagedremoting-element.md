---
title: <PreferComInsteadOfManagedRemoting> Element
ms.date: 03/30/2017
helpviewer_keywords:
- <PreferComInsteadOfManagedRemoting> element
- PreferComInsteadOfManagedRemoting element
ms.assetid: a279a42a-c415-4e79-88cf-64244ebda613
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5b0a394500dbea0d557a33ea8d2e169c2c6561f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195669"
---
# <a name="prefercominsteadofmanagedremoting-element"></a><span data-ttu-id="7dd31-102">\<PreferComInsteadOfManagedRemoting >-Element</span><span class="sxs-lookup"><span data-stu-id="7dd31-102">\<PreferComInsteadOfManagedRemoting> Element</span></span>
<span data-ttu-id="7dd31-103">Gibt an, ob die Runtime COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting für alle Aufrufe über Anwendungsdomänengrenzen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dd31-103">Specifies whether the runtime will use COM interop instead of remoting for all calls across application domain boundaries.</span></span>  
  
 <span data-ttu-id="7dd31-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7dd31-104">\<configuration></span></span>  
<span data-ttu-id="7dd31-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="7dd31-105">\<runtime></span></span>  
<span data-ttu-id="7dd31-106">\<PreferComInsteadOfManagedRemoting></span><span class="sxs-lookup"><span data-stu-id="7dd31-106">\<PreferComInsteadOfManagedRemoting></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dd31-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dd31-107">Syntax</span></span>  
  
```xml  
<PreferComInsteadOfManagedRemoting enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dd31-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7dd31-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7dd31-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7dd31-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dd31-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7dd31-110">Attributes</span></span>  
  
|<span data-ttu-id="7dd31-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="7dd31-111">Attribute</span></span>|<span data-ttu-id="7dd31-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dd31-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="7dd31-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="7dd31-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="7dd31-114">Gibt an, ob die Runtime COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting über Anwendungsdomänen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dd31-114">Indicates whether the runtime will use COM interop instead of remoting across application domain boundaries.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="7dd31-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="7dd31-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="7dd31-116">Wert</span><span class="sxs-lookup"><span data-stu-id="7dd31-116">Value</span></span>|<span data-ttu-id="7dd31-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dd31-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="7dd31-118">Die Laufzeit wird Remoting über Anwendungsdomänen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dd31-118">The runtime will use remoting across application domain boundaries.</span></span> <span data-ttu-id="7dd31-119">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="7dd31-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="7dd31-120">Die Runtime wird COM-Interop über Anwendungsdomänengrenzen hinweg verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dd31-120">The runtime will use COM interop across application domain boundaries.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dd31-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dd31-121">Child Elements</span></span>  
 <span data-ttu-id="7dd31-122">Keine</span><span class="sxs-lookup"><span data-stu-id="7dd31-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7dd31-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dd31-123">Parent Elements</span></span>  
  
|<span data-ttu-id="7dd31-124">Element</span><span class="sxs-lookup"><span data-stu-id="7dd31-124">Element</span></span>|<span data-ttu-id="7dd31-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dd31-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7dd31-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="7dd31-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7dd31-127">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="7dd31-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dd31-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7dd31-128">Remarks</span></span>  
 <span data-ttu-id="7dd31-129">Beim Festlegen der `enabled` Attribut `true`, die Laufzeit verhält sich wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7dd31-129">When you set the `enabled` attribute to `true`, the runtime behaves as follows:</span></span>  
  
-   <span data-ttu-id="7dd31-130">Die Runtime ruft nicht [IUnknown:: QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) Schnittstelle, wenn ein [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) Schnittstelle gibt die Domäne über eine COM-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7dd31-130">The runtime does not call [IUnknown::QueryInterface](https://go.microsoft.com/fwlink/?LinkID=144867) for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface when an [IUnknown](https://go.microsoft.com/fwlink/?LinkId=148003) interface enters the domain through a COM interface.</span></span> <span data-ttu-id="7dd31-131">Stattdessen erstellt eine [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) für das Objekt.</span><span class="sxs-lookup"><span data-stu-id="7dd31-131">Instead, it constructs a [Runtime Callable Wrapper](../../../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) around the object.</span></span>  
  
-   <span data-ttu-id="7dd31-132">Die Laufzeit wird E_NOINTERFACE zurückgegeben, wenn er empfängt eine `QueryInterface` rufen Sie für eine [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) Schnittstelle für alle [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW), die in dieser Domäne erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7dd31-132">The runtime returns E_NOINTERFACE when it receives a `QueryInterface` call for an [IManagedObject](../../../../../docs/framework/unmanaged-api/hosting/imanagedobject-interface.md) interface for any [COM Callable Wrapper](../../../../../docs/framework/interop/com-callable-wrapper.md) (CCW) that has been created in this domain.</span></span>  
  
 <span data-ttu-id="7dd31-133">Diese zwei Verhaltensweisen stellen Sie sicher, dass alle Aufrufe über COM-Schnittstellen zwischen verwalteten Objekten über Domänen hinweg Anwendungsverwendung COM- und COM-Interop anstelle von anwendungsdomänenübergreifendem Remoting.</span><span class="sxs-lookup"><span data-stu-id="7dd31-133">These two behaviors ensure that all calls over COM interfaces between managed objects across application domain boundaries use COM and COM interop instead of remoting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dd31-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7dd31-134">Example</span></span>  
 <span data-ttu-id="7dd31-135">Das folgende Beispiel zeigt wie angegeben, dass die Runtime COM verwenden soll, die über Isolationsgrenzen hinweg interop:</span><span class="sxs-lookup"><span data-stu-id="7dd31-135">The following example shows how to specify that the runtime should use COM interop across isolation boundaries:</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <PreferComInsteadOfManagedRemoting enabled="true"/>  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7dd31-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dd31-136">See also</span></span>

- [<span data-ttu-id="7dd31-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="7dd31-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="7dd31-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="7dd31-138">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
