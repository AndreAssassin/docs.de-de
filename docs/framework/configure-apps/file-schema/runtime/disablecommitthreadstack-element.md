---
title: <disableCommitThreadStack>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCommitThreadStack
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCommitThreadStack
helpviewer_keywords:
- <disableCommitThreadStack> element
- disableCommitThreadStack element
ms.assetid: 3559d46a-7640-4c72-9a11-7e980768929e
ms.openlocfilehash: 8aefb8a20d6a95c5b8062d0c03dcb28a3557ca3d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73117473"
---
# <a name="disablecommitthreadstack-element"></a><span data-ttu-id="881e7-102">\<disablecommitthreadstack > Element</span><span class="sxs-lookup"><span data-stu-id="881e7-102">\<disableCommitThreadStack> Element</span></span>
<span data-ttu-id="881e7-103">Gibt an, ob beim Starten eines Threads für den vollständigen Threadstapel ein Commit ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="881e7-103">Specifies whether the full thread stack is committed when a thread is started.</span></span>  
  
<span data-ttu-id="881e7-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="881e7-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="881e7-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="881e7-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="881e7-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<disablecommitthreadstack >**</span><span class="sxs-lookup"><span data-stu-id="881e7-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCommitThreadStack>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="881e7-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="881e7-107">Syntax</span></span>  
  
```xml  
<disableCommitThreadStack enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="881e7-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="881e7-108">Attributes and Elements</span></span>  
 <span data-ttu-id="881e7-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="881e7-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="881e7-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="881e7-110">Attributes</span></span>  
  
|<span data-ttu-id="881e7-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="881e7-111">Attribute</span></span>|<span data-ttu-id="881e7-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="881e7-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="881e7-113">enabled</span><span class="sxs-lookup"><span data-stu-id="881e7-113">enabled</span></span>|<span data-ttu-id="881e7-114">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="881e7-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="881e7-115">Gibt an, ob das Standardverhalten, beim Starten des Threads den gesamten Threadstapel zu commiten, deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="881e7-115">Specifies whether committing the full thread stack on thread startup (the default behavior) is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="881e7-116">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="881e7-116">enabled Attribute</span></span>  
  
|<span data-ttu-id="881e7-117">Wert</span><span class="sxs-lookup"><span data-stu-id="881e7-117">Value</span></span>|<span data-ttu-id="881e7-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="881e7-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="881e7-119">0</span><span class="sxs-lookup"><span data-stu-id="881e7-119">0</span></span>|<span data-ttu-id="881e7-120">Das Standardverhalten der Common Language Runtime, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen, ist nicht deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="881e7-120">Do not disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
|<span data-ttu-id="881e7-121">1</span><span class="sxs-lookup"><span data-stu-id="881e7-121">1</span></span>|<span data-ttu-id="881e7-122">Das Standardverhalten der Common Language Runtime, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen, ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="881e7-122">Disable the default behavior of the common language runtime, which is to commit the full thread stack when a thread is started.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="881e7-123">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="881e7-123">Child Elements</span></span>  
 <span data-ttu-id="881e7-124">Keine</span><span class="sxs-lookup"><span data-stu-id="881e7-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="881e7-125">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="881e7-125">Parent Elements</span></span>  
  
|<span data-ttu-id="881e7-126">Element</span><span class="sxs-lookup"><span data-stu-id="881e7-126">Element</span></span>|<span data-ttu-id="881e7-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="881e7-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="881e7-128">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="881e7-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="881e7-129">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="881e7-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="881e7-130">Hinweise</span><span class="sxs-lookup"><span data-stu-id="881e7-130">Remarks</span></span>  
 <span data-ttu-id="881e7-131">Das Standardverhalten der Common Language Runtime ist, beim Starten eines Threads einen Commit für den vollständigen Threadstapel auszuführen.</span><span class="sxs-lookup"><span data-stu-id="881e7-131">The default behavior of the common language runtime is to commit the full thread stack when a thread is started.</span></span> <span data-ttu-id="881e7-132">Wenn eine große Anzahl von Threads auf einem Server erstellt werden muss, der nur über begrenzten Arbeitsspeicher verfügt, und der Großteil dieser Threads nur sehr wenig Stapelspeicher verwenden wird, ist die Leistung des Servers möglicherweise besser, wenn die Common Language Runtime nicht sofort einen Commit für den vollständigen Threadstapel ausführt, wenn ein Thread gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="881e7-132">If a large number of threads must be created on a server that has limited memory, and most of those threads will use very little stack space, the server might perform better if the common language runtime does not commit the full thread stack immediately when a thread is started.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="881e7-133">Nicht verwaltete Hosts können das `STARTUP_DISABLE_COMMITTHREADSTACK` -Startflag in der [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) -Enumeration verwenden, um das gleiche Ergebnis zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="881e7-133">Unmanaged hosts can use the `STARTUP_DISABLE_COMMITTHREADSTACK` startup flag in the [STARTUP_FLAGS](../../../unmanaged-api/hosting/startup-flags-enumeration.md) enumeration to accomplish the same result.</span></span>  
  
## <a name="example"></a><span data-ttu-id="881e7-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="881e7-134">Example</span></span>  
 <span data-ttu-id="881e7-135">Das folgende Beispiel zeigt, wie Sie das Standardverhalten der Common Language Runtime deaktivieren, die während des Threadstarts einen Commit für den vollständigen Threadstapel ausführen soll.</span><span class="sxs-lookup"><span data-stu-id="881e7-135">The following example shows how to disable the default behavior of the common language runtime, which is to commit the full thread stack on thread startup.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCommitThreadStack enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="881e7-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="881e7-136">See also</span></span>

- [<span data-ttu-id="881e7-137">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="881e7-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="881e7-138">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="881e7-138">Configuration File Schema</span></span>](../index.md)
