---
title: <bypassTrustedAppStrongNames>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- bypassTrustedAppStrongNames element
- strong-named assemblies, loading into trusted application domains
- <bypassTrustedAppStrongNames> element
ms.assetid: 71b2ebf6-3843-41e2-ad52-ffa5cd083a40
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c39d9a1e3da9cccb2f027e9597a6f2272d187ec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179139"
---
# <a name="bypasstrustedappstrongnames-element"></a><span data-ttu-id="ce18b-102">\<bypassTrustedAppStrongNames>-Element</span><span class="sxs-lookup"><span data-stu-id="ce18b-102">\<bypassTrustedAppStrongNames> Element</span></span>
<span data-ttu-id="ce18b-103">Gibt an, ob die Überprüfung von starken Namen für voll vertrauenswürdige Assemblys umgangen, die ein voll vertrauenswürdiges geladen <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="ce18b-103">Specifies whether to bypass the validation of strong names on full-trust assemblies that are loaded into a full-trust <xref:System.AppDomain>.</span></span>  
  
 <span data-ttu-id="ce18b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ce18b-104">\<configuration></span></span>  
<span data-ttu-id="ce18b-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="ce18b-105">\<runtime></span></span>  
<span data-ttu-id="ce18b-106">\<bypassTrustedAppStrongNames></span><span class="sxs-lookup"><span data-stu-id="ce18b-106">\<bypassTrustedAppStrongNames></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce18b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce18b-107">Syntax</span></span>  
  
```xml  
<bypassTrustedAppStrongNames    
   enabled="true|false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ce18b-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ce18b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ce18b-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ce18b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ce18b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="ce18b-110">Attributes</span></span>  
  
|<span data-ttu-id="ce18b-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="ce18b-111">Attribute</span></span>|<span data-ttu-id="ce18b-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce18b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ce18b-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="ce18b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ce18b-114">Gibt an, ob die Bypass-Funktion, die Überprüfung starke Namen für voll vertrauenswürdige Assemblys aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ce18b-114">Specifies whether the bypass feature that avoids validating strong names for full-trust assemblies is enabled.</span></span> <span data-ttu-id="ce18b-115">Wenn dieses Feature aktiviert ist, werden starke Namen nicht auf Richtigkeit überprüft werden, wenn die Assembly geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ce18b-115">When this feature is enabled, strong names are not validated for correctness when the assembly is loaded.</span></span> <span data-ttu-id="ce18b-116">Die Standardeinstellung ist `true`.</span><span class="sxs-lookup"><span data-stu-id="ce18b-116">The default is `true`.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="ce18b-117">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="ce18b-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="ce18b-118">Wert</span><span class="sxs-lookup"><span data-stu-id="ce18b-118">Value</span></span>|<span data-ttu-id="ce18b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce18b-119">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="ce18b-120">Signaturen mit starkem Namen für voll vertrauenswürdige Assemblys werden nicht überprüft werden, wenn die Assemblys in ein voll vertrauenswürdiges geladen werden <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="ce18b-120">Strong-name signatures on full-trust assemblies are not validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="ce18b-121">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="ce18b-121">This is the default.</span></span>|  
|`false`|<span data-ttu-id="ce18b-122">Signaturen mit starkem Namen für voll vertrauenswürdige Assemblys werden überprüft, wenn die Assemblys in ein voll vertrauenswürdiges geladen werden <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="ce18b-122">Strong-name signatures on full-trust assemblies are validated when the assemblies are loaded into a full-trust <xref:System.AppDomain>.</span></span> <span data-ttu-id="ce18b-123">Die Signatur mit starkem Namen wird nur auf Korrektheit der Signatur überprüft. Es wird nicht mit einem anderen starken Namens für eine Übereinstimmung verglichen.</span><span class="sxs-lookup"><span data-stu-id="ce18b-123">The strong-name signature is checked only for signature correctness; it is not compared to another strong name for a match.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ce18b-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce18b-124">Child Elements</span></span>  
 <span data-ttu-id="ce18b-125">Keine</span><span class="sxs-lookup"><span data-stu-id="ce18b-125">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ce18b-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ce18b-126">Parent Elements</span></span>  
  
|<span data-ttu-id="ce18b-127">Element</span><span class="sxs-lookup"><span data-stu-id="ce18b-127">Element</span></span>|<span data-ttu-id="ce18b-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce18b-128">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ce18b-129">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="ce18b-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ce18b-130">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="ce18b-130">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce18b-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce18b-131">Remarks</span></span>  
 <span data-ttu-id="ce18b-132">Das strong-Name-Bypass-Feature vermeidet den zusätzlichen Aufwand Überprüfung der Signatur mit starkem Namen der vollständig vertrauenswürdigen Assemblys.</span><span class="sxs-lookup"><span data-stu-id="ce18b-132">The strong-name bypass feature avoids the overhead of strong-name signature verification of full-trust assemblies.</span></span>  
  
 <span data-ttu-id="ce18b-133">Das Bypass-Feature gilt für jede Assembly, die mit einem starken Namen signiert ist und die folgenden Eigenschaften aufweist:</span><span class="sxs-lookup"><span data-stu-id="ce18b-133">The bypass feature applies to any assembly that is signed with a strong name and that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="ce18b-134">Voll vertrauenswürdig ohne die <xref:System.Security.Policy.StrongName> Beweise (beispielsweise `MyComputer` Zonenbeweis).</span><span class="sxs-lookup"><span data-stu-id="ce18b-134">Fully trusted without the <xref:System.Security.Policy.StrongName> evidence (for example, has `MyComputer` zone evidence).</span></span>  
  
-   <span data-ttu-id="ce18b-135">Geladen in eine voll vertrauenswürdige <xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="ce18b-135">Loaded into a fully trusted <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="ce18b-136">Geladen von einem Speicherort unter der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft von dieser <xref:System.AppDomain></span><span class="sxs-lookup"><span data-stu-id="ce18b-136">Loaded from a location under the <xref:System.AppDomainSetup.ApplicationBase%2A> property of that <xref:System.AppDomain>.</span></span>  
  
-   <span data-ttu-id="ce18b-137">Nicht verzögert signiert</span><span class="sxs-lookup"><span data-stu-id="ce18b-137">Not delay-signed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce18b-138">Wenn die Bypass-Funktion für alle Anwendungen auf dem Computer deaktiviert wurde mithilfe eines Registrierungsschlüssels, hat diese Einstellung keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="ce18b-138">If the bypass feature has been turned off for all applications on the computer by using a registry key, this configuration file setting has no effect.</span></span> <span data-ttu-id="ce18b-139">Weitere Informationen finden Sie unter [Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span><span class="sxs-lookup"><span data-stu-id="ce18b-139">For more information, see [How to: Disable the Strong-Name Bypass Feature](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="ce18b-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce18b-140">Example</span></span>  
 <span data-ttu-id="ce18b-141">Das folgende Beispiel zeigt, wie Sie das Verhalten angeben, das die Signatur mit starkem Namen für voll vertrauenswürdige Assemblys überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="ce18b-141">The following example shows how to specify the behavior that validates the strong-name signature on full-trust assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <bypassTrustedAppStrongNames enabled="false"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce18b-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce18b-142">See also</span></span>

- [<span data-ttu-id="ce18b-143">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="ce18b-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="ce18b-144">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="ce18b-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="ce18b-145">Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion</span><span class="sxs-lookup"><span data-stu-id="ce18b-145">How to: Disable the Strong-Name Bypass Feature</span></span>](../../../../../docs/framework/app-domains/how-to-disable-the-strong-name-bypass-feature.md)
