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
ms.openlocfilehash: 575d44ad9ecf445ba5d4b7fbe47032127ccb33ae
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252732"
---
# <a name="compatsortnlsversion-element"></a><span data-ttu-id="b7a0f-102">\<Compatsortnlsversion >-Element</span><span class="sxs-lookup"><span data-stu-id="b7a0f-102">\<CompatSortNLSVersion> Element</span></span>
<span data-ttu-id="b7a0f-103">Gibt an, dass die Laufzeit Sortierreihenfolgen von Legacyversionen beim Vergleichen von Zeichenfolgen verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-103">Specifies that the runtime should use legacy sort orders when performing string comparisons.</span></span>  
  
<span data-ttu-id="b7a0f-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b7a0f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b7a0f-105">&nbsp;&nbsp;[ **\<Lauf Zeit >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="b7a0f-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="b7a0f-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<CompatSortNLSVersion>**</span><span class="sxs-lookup"><span data-stu-id="b7a0f-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<CompatSortNLSVersion>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a0f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7a0f-107">Syntax</span></span>  
  
```xml  
<CompatSortNLSVersion    
   enabled="4096"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7a0f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b7a0f-108">Attributes and Elements</span></span>  
 <span data-ttu-id="b7a0f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7a0f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="b7a0f-110">Attributes</span></span>  
  
|<span data-ttu-id="b7a0f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="b7a0f-111">Attribute</span></span>|<span data-ttu-id="b7a0f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7a0f-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="b7a0f-113">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="b7a0f-114">Gibt die Gebietsschema-ID an, deren Sortierreihenfolge verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-114">Specifies the locale ID whose sort order is to be used.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="b7a0f-115">Enabled-Attribut</span><span class="sxs-lookup"><span data-stu-id="b7a0f-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="b7a0f-116">Wert</span><span class="sxs-lookup"><span data-stu-id="b7a0f-116">Value</span></span>|<span data-ttu-id="b7a0f-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7a0f-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="b7a0f-118">4096</span><span class="sxs-lookup"><span data-stu-id="b7a0f-118">4096</span></span>|<span data-ttu-id="b7a0f-119">Die Gebietsschema-ID, die eine andere Sortierreihenfolge darstellt.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-119">The locale ID that represents an alternate sort order.</span></span> <span data-ttu-id="b7a0f-120">In diesem Fall stellt 4096 die Sortierreihenfolge der .NET Framework 3,5 und früheren Versionen dar.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-120">In this case, 4096 represents the sort order of the .NET Framework 3.5 and earlier versions.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7a0f-121">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7a0f-121">Child Elements</span></span>  
 <span data-ttu-id="b7a0f-122">Keine</span><span class="sxs-lookup"><span data-stu-id="b7a0f-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7a0f-123">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7a0f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="b7a0f-124">Element</span><span class="sxs-lookup"><span data-stu-id="b7a0f-124">Element</span></span>|<span data-ttu-id="b7a0f-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7a0f-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b7a0f-126">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="b7a0f-127">Enthält Informationen über Laufzeitinitialisierungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7a0f-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7a0f-128">Remarks</span></span>  
 <span data-ttu-id="b7a0f-129">Da Zeichen folgen Vergleichs-, Sortier-und Schreibvorgänge, <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> die von der-Klasse in .NET Framework 4 ausgeführt werden, dem Unicode 5,1-Standard entsprechen, können sich <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> die <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> Ergebnisse von Zeichen folgen Vergleichsmethoden wie und von frühere Versionen des .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-129">Because string comparison, sorting, and casing operations performed by the <xref:System.Globalization.CompareInfo?displayProperty=nameWithType> class in the .NET Framework 4 conform to the Unicode 5.1 standard, the results of string comparison methods such as <xref:System.String.Compare%28System.String%2CSystem.String%29?displayProperty=nameWithType> and <xref:System.String.LastIndexOf%28System.String%29?displayProperty=nameWithType> may differ from previous versions of the .NET Framework.</span></span> <span data-ttu-id="b7a0f-130">Wenn Ihre Anwendung von Legacy Verhalten abhängig ist, können Sie den Zeichen folgen Vergleich und die Sortierregeln, die in der .NET Framework 3,5 und früheren Versionen `<CompatSortNLSVersion>` verwendet werden, wiederherstellen, indem Sie das-Element in die Konfigurationsdatei der Anwendung einschließen.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-130">If your application depends on legacy behavior, you can restore the string comparison and sorting rules used in the .NET Framework 3.5 and earlier versions by including the `<CompatSortNLSVersion>` element in your application's configuration file.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b7a0f-131">Zum Wiederherstellen von Zeichenfolgenvergleichs- und Zeichenfolgensortierregeln von Legacyversionen muss auch die sort00001000.dll-Dynamic Link Library auf dem lokalen System verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-131">Restoring legacy string comparison and sorting rules also requires the sort00001000.dll dynamic link library to be available on the local system.</span></span>  
  
 <span data-ttu-id="b7a0f-132">Sie können Zeichenfolgensortier- und Zeichenfolgenvergleichsregeln von Legacyversionen auch in einer bestimmten Anwendungsdomäne verwenden, indem Sie die Zeichenfolge "NetFx40_Legacy20SortingBehavior" an die <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A>-Methode beim Erstellen der Anwendungsdomäne übergeben.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-132">You can also use legacy string sorting and comparison rules in a specific application domain by passing the string "NetFx40_Legacy20SortingBehavior" to the <xref:System.AppDomainSetup.SetCompatibilitySwitches%2A> method when you create the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7a0f-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7a0f-133">Example</span></span>  
 <span data-ttu-id="b7a0f-134">Im folgenden Beispiel werden zwei <xref:System.String>-Objekte instanziiert und die <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType>-Methode aufgerufen, um sie mithilfe der Konventionen der aktuellen Kultur zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-134">The following example instantiates two <xref:System.String> objects and calls the <xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.StringComparison%29?displayProperty=nameWithType> method to compare them by using the conventions of the current culture.</span></span>  
  
 [!code-csharp[String.BreakingChanges#1](../../../../../samples/snippets/csharp/VS_Snippets_CLR/string.breakingchanges/cs/example1.cs#1)]
 [!code-vb[String.BreakingChanges#1](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR/string.breakingchanges/vb/example1.vb#1)]  
  
 <span data-ttu-id="b7a0f-135">Wenn Sie das Beispiel auf dem .NET Framework 4 ausführen, wird die folgende Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-135">When you run the example on the .NET Framework 4, it displays the following output.</span></span>  
  
```  
sta follows a in the sort order.  
```  
  
 <span data-ttu-id="b7a0f-136">Dies unterscheidet sich vollständig von der Ausgabe, die angezeigt wird, wenn Sie das Beispiel auf dem .NET Framework 3,5 ausführen.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-136">This is completely different from the output that is displayed when you run the example on the .NET Framework 3.5.</span></span>  
  
```  
sta equals a in the sort order.  
```  
  
 <span data-ttu-id="b7a0f-137">Wenn Sie jedoch die folgende Konfigurationsdatei zum Verzeichnis des Beispiels hinzufügen und dann das Beispiel auf dem .NET Framework 4 ausführen, ist die Ausgabe identisch mit der Ausgabe, die im Beispiel erstellt wird, wenn Sie auf der .NET Framework 3,5 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b7a0f-137">However, if you add the following configuration file to the example's directory and then run the example on the .NET Framework 4, the output is identical to that produced by the example when it is run on the .NET Framework 3.5.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <CompatSortNLSVersion enabled="4096"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7a0f-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7a0f-138">See also</span></span>

- [<span data-ttu-id="b7a0f-139">Schema für Laufzeiteinstellungen</span><span class="sxs-lookup"><span data-stu-id="b7a0f-139">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b7a0f-140">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="b7a0f-140">Configuration File Schema</span></span>](../index.md)
