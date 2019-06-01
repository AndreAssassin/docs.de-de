---
title: <CompatSortNLSVersion>-Element
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- <CompatSortNLSVersion> element
- CompatSortNLSVersion element
ms.assetid: 782cc82e-83f7-404a-80b7-6d3061a8b6e3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f6aef46db47f881d6a15cc1e58d46219a80194b0
ms.sourcegitcommit: 518e7634b86d3980ec7da5f8c308cc1054daedb7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2019
ms.locfileid: "66456448"
---
# <a name="compatsortnlsversion-element"></a><span data-ttu-id="a1569-102">\<CompatSortNLSVersion >-Element</span><span class="sxs-lookup"><span data-stu-id="a1569-102">\<CompatSortNLSVersion> Element</span></span>
<span data-ttu-id="a1569-103">Gibt an, dass die Laufzeit Sortierreihenfolgen von Legacyversionen beim Vergleichen von Zeichenfolgen verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="a1569-103">Specifies that the runtime should use legacy sort orders when performing string comparisons.</span></span>  
  
 <span data-ttu-id="a1569-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a1569-104">\<configuration></span></span>  
<span data-ttu-id="a1569-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="a1569-105">\<runtime></span></span>  
<span data-ttu-id="a1569-106">\<CompatSortNLSVersion >-Element</span><span class="sxs-lookup"><span data-stu-id="a1569-106">\<CompatSortNLSVersion> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1569-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1569-107">Syntax</span></span>  
  
```xml  
<CompatSortNLSVersion    
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a1569-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a1569-108">Attributes and Elements</span></span>  
 <span data-ttu-id="a1569-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a1569-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a1569-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="a1569-110">Attributes</span></span>  
  
|<span data-ttu-id="a1569-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="a1569-111">Attribute</span></span>|<span data-ttu-id="a1569-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1569-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="a1569-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="a1569-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="a1569-114">Gibt die Gebietsschema-ID an, deren Sortierreihenfolge verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1569-114">Specifies the locale ID whose sort order is to be used.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="a1569-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="a1569-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="a1569-116">Wert</span><span class="sxs-lookup"><span data-stu-id="a1569-116">Value</span></span>|<span data-ttu-id="a1569-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1569-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1569-118">4096</span><span class="sxs-lookup"><span data-stu-id="a1569-118">4096</span></span>|<span data-ttu-id="a1569-119">Die Gebietsschema-ID, die eine andere Sortierreihenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="a1569-119">The locale ID that represents an alternate sort order.</span></span> <span data-ttu-id="a1569-120">In diesem Fall stellt 4096 die Sortierreihenfolge von [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] und früheren Versionen dar.</span><span class="sxs-lookup"><span data-stu-id="a1569-120">In this case, 4096 represents the sort order of the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] and earlier versions.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a1569-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1569-121">Child Elements</span></span>  
 <span data-ttu-id="a1569-122">Keine</span><span class="sxs-lookup"><span data-stu-id="a1569-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a1569-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a1569-123">Parent Elements</span></span>  
  
|<span data-ttu-id="a1569-124">Element</span><span class="sxs-lookup"><span data-stu-id="a1569-124">Element</span></span>|<span data-ttu-id="a1569-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1569-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a1569-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="a1569-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="a1569-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="a1569-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1569-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1569-128">Remarks</span></span>  
 <span data-ttu-id="a1569-129">Da Zeichenfolge vergleichen, Sortieren und Schreibweise Vorgänge, durch ausgeführt die <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> Klasse in .NET Framework 4 entsprechen dem Unicode 5.1-standard, die Ergebnisse der Methoden zum Zeichenfolgenvergleich wie z. B. <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> und <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> weicht möglicherweise von frühere Versionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a1569-129">Because string comparison, sorting, and casing operations performed by the <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> class in the .NET Framework 4 conform to the Unicode 5.1 standard, the results of string comparison methods such as <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> and <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> may differ from previous versions of the .NET Framework.</span></span> <span data-ttu-id="a1569-130">Wenn Ihre Anwendung von Legacyverhalten abhängig ist, können Sie die Regeln für den Vergleich und die Sortierung von Zeichenfolgen aus [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] und früheren Versionen wiederherstellen, indem Sie das `<CompatSortNLSVersion>`-Element in der Konfigurationsdatei der Anwendung angeben.</span><span class="sxs-lookup"><span data-stu-id="a1569-130">If your application depends on legacy behavior, you can restore the string comparison and sorting rules used in the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] and earlier versions by including the `<CompatSortNLSVersion>` element in your application's configuration file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a1569-131">Zum Wiederherstellen von Zeichenfolgenvergleichs- und Zeichenfolgensortierregeln von Legacyversionen muss auch die sort00001000.dll-Dynamic Link Library auf dem lokalen System verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="a1569-131">Restoring legacy string comparison and sorting rules also requires the sort00001000.dll dynamic link library to be available on the local system.</span></span>  
  
 <span data-ttu-id="a1569-132">Sie können Zeichenfolgensortier- und Zeichenfolgenvergleichsregeln von Legacyversionen auch in einer bestimmten Anwendungsdomäne verwenden, indem Sie die Zeichenfolge "NetFx40_Legacy20SortingBehavior" an die <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A>-Methode beim Erstellen der Anwendungsdomäne übergeben.</span><span class="sxs-lookup"><span data-stu-id="a1569-132">You can also use legacy string sorting and comparison rules in a specific application domain by passing the string "NetFx40_Legacy20SortingBehavior" to the <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> method when you create the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1569-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a1569-133">Example</span></span>  
 <span data-ttu-id="a1569-134">Im folgenden Beispiel werden zwei <xref:System.String>-Objekte instanziiert und die <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType>-Methode aufgerufen, um sie mithilfe der Konventionen der aktuellen Kultur zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="a1569-134">The following example instantiates two <xref:System.String> objects and calls the <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method to compare them by using the conventions of the current culture.</span></span>  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 <span data-ttu-id="a1569-135">Wenn Sie das Beispiel für die .NET Framework 4 ausführen, wird die folgende Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1569-135">When you run the example on the .NET Framework 4, it displays the following output.</span></span>  
  
```  
sta follows a in the sort order.  
```  
  
 <span data-ttu-id="a1569-136">Diese unterscheidet sich vollkommen von der Ausgabe, die bei Ausführung des Beispiels unter [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)] angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a1569-136">This is completely different from the output that is displayed when you run the example on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```  
sta equals a in the sort order.  
```  
  
 <span data-ttu-id="a1569-137">Wenn Sie die folgende Konfigurationsdatei im Verzeichnis des Beispiels hinzufügen und dann das Beispiel, auf .NET Framework 4 ausführen, die Ausgabe ist jedoch identisch, die durch das Beispiel erstellt wird, wenn er ausgeführt wird, die [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a1569-137">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4, the output is identical to that produced by the example when it is run on the [!INCLUDE[net_v35_short](../../../../../includes/net-v35-short-md.md)].</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1569-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1569-138">See also</span></span>

- [<span data-ttu-id="a1569-139">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="a1569-139">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="a1569-140">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="a1569-140">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
