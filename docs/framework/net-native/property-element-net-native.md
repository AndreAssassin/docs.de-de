---
title: <Property>-Element (.net Native)
ms.date: 03/30/2017
ms.assetid: ad4ba56d-3bcb-4c10-ba90-1cc66e2175a1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54daf15c593327bf3255f40f6eb6931ffc8bd3c6
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049313"
---
# <a name="property-element-net-native"></a><span data-ttu-id="5b6df-102">\<Property >-Element (.net Native)</span><span class="sxs-lookup"><span data-stu-id="5b6df-102">\<Property> Element (.NET Native)</span></span>
<span data-ttu-id="5b6df-103">Wendet eine Laufzeitreflektionsrichtlinie auf eine Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="5b6df-103">Applies runtime reflection policy to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b6df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b6df-104">Syntax</span></span>  
  
```xml  
<Property Name="property_name"  
          Browse="policy_type"  
          Dynamic="policy_type"  
          Serialize="policy_type" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b6df-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5b6df-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5b6df-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5b6df-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b6df-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="5b6df-107">Attributes</span></span>  
  
|<span data-ttu-id="5b6df-108">Attribut</span><span class="sxs-lookup"><span data-stu-id="5b6df-108">Attribute</span></span>|<span data-ttu-id="5b6df-109">Attributtyp</span><span class="sxs-lookup"><span data-stu-id="5b6df-109">Attribute type</span></span>|<span data-ttu-id="5b6df-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b6df-110">Description</span></span>|  
|---------------|--------------------|-----------------|  
|`Name`|<span data-ttu-id="5b6df-111">Allgemein</span><span class="sxs-lookup"><span data-stu-id="5b6df-111">General</span></span>|<span data-ttu-id="5b6df-112">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="5b6df-112">Required attribute.</span></span> <span data-ttu-id="5b6df-113">Gibt den Eigenschaftennamen an.</span><span class="sxs-lookup"><span data-stu-id="5b6df-113">Specifies the property name.</span></span>|  
|`Browse`|<span data-ttu-id="5b6df-114">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="5b6df-114">Reflection</span></span>|<span data-ttu-id="5b6df-115">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="5b6df-115">Optional attribute.</span></span> <span data-ttu-id="5b6df-116">Steuert das Abfragen nach Informationen über die Eigenschaft oder das Auflisten der Eigenschaft, aber ermöglicht keinen dynamischen Zugriff zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="5b6df-116">Controls querying for information about or enumerating the property but does not enable any dynamic access at run time.</span></span>|  
|`Dynamic`|<span data-ttu-id="5b6df-117">Spiegelung</span><span class="sxs-lookup"><span data-stu-id="5b6df-117">Reflection</span></span>|<span data-ttu-id="5b6df-118">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="5b6df-118">Optional attribute.</span></span> <span data-ttu-id="5b6df-119">Steuert den Laufzeitzugriff auf die Eigenschaft, um dynamische Programmierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5b6df-119">Controls runtime access to the property to enable dynamic programming.</span></span> <span data-ttu-id="5b6df-120">Diese Richtlinie stellt sicher, dass eine Eigenschaft zur Laufzeit dynamisch festgelegt oder abgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5b6df-120">This policy ensures that a property can be set or retrieved dynamically at run time.</span></span>|  
|`Serialize`|<span data-ttu-id="5b6df-121">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="5b6df-121">Serialization</span></span>|<span data-ttu-id="5b6df-122">Optionales Attribut.</span><span class="sxs-lookup"><span data-stu-id="5b6df-122">Optional attribute.</span></span> <span data-ttu-id="5b6df-123">Steuert den Laufzeitzugriff auf eine Eigenschaft, damit Typinstanzen von Bibliotheken wie dem Newtonsoft JSON-Serialisierungsprogramm serialisiert werden können oder für die Datenbindung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5b6df-123">Controls runtime access to a property to enable type instances to be serialized by libraries such as the Newtonsoft JSON serializer or to be used for data binding.</span></span>|  
  
## <a name="name-attribute"></a><span data-ttu-id="5b6df-124">Namensattribut</span><span class="sxs-lookup"><span data-stu-id="5b6df-124">Name attribute</span></span>  
  
|<span data-ttu-id="5b6df-125">Wert</span><span class="sxs-lookup"><span data-stu-id="5b6df-125">Value</span></span>|<span data-ttu-id="5b6df-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b6df-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b6df-127">*method_name*</span><span class="sxs-lookup"><span data-stu-id="5b6df-127">*method_name*</span></span>|<span data-ttu-id="5b6df-128">Der Eigenschaftenname.</span><span class="sxs-lookup"><span data-stu-id="5b6df-128">The property name.</span></span> <span data-ttu-id="5b6df-129">Der Typ der Eigenschaft wird durch das übergeordnete [\<Type>](type-element-net-native.md)- oder [\<TypeInstantiation>](typeinstantiation-element-net-native.md)-Element definiert.</span><span class="sxs-lookup"><span data-stu-id="5b6df-129">The type of the property is defined by the parent [\<Type>](type-element-net-native.md) or [\<TypeInstantiation>](typeinstantiation-element-net-native.md) element.</span></span>|  
  
## <a name="all-other-attributes"></a><span data-ttu-id="5b6df-130">Alle anderen Attribute</span><span class="sxs-lookup"><span data-stu-id="5b6df-130">All other attributes</span></span>  
  
|<span data-ttu-id="5b6df-131">Wert</span><span class="sxs-lookup"><span data-stu-id="5b6df-131">Value</span></span>|<span data-ttu-id="5b6df-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b6df-132">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5b6df-133">*policy_setting*</span><span class="sxs-lookup"><span data-stu-id="5b6df-133">*policy_setting*</span></span>|<span data-ttu-id="5b6df-134">Die Einstellung, die auf diesen Richtlinientyp für die Eigenschaft angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b6df-134">The setting to apply to this policy type for the property.</span></span> <span data-ttu-id="5b6df-135">Mögliche Werte sind `Auto`, `Excluded`, `Included` und `Required`.</span><span class="sxs-lookup"><span data-stu-id="5b6df-135">Possible values are `Auto`, `Excluded`, `Included`, and `Required`.</span></span> <span data-ttu-id="5b6df-136">Weitere Informationen finden Sie unter [Richtlinieneinstellungen für die Laufzeitanweisung](runtime-directive-policy-settings.md).</span><span class="sxs-lookup"><span data-stu-id="5b6df-136">For more information, see [Runtime Directive Policy Settings](runtime-directive-policy-settings.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b6df-137">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5b6df-137">Child Elements</span></span>  
 <span data-ttu-id="5b6df-138">Keine</span><span class="sxs-lookup"><span data-stu-id="5b6df-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b6df-139">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5b6df-139">Parent Elements</span></span>  
  
|<span data-ttu-id="5b6df-140">Element</span><span class="sxs-lookup"><span data-stu-id="5b6df-140">Element</span></span>|<span data-ttu-id="5b6df-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b6df-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5b6df-142">\<Type></span><span class="sxs-lookup"><span data-stu-id="5b6df-142">\<Type></span></span>](type-element-net-native.md)|<span data-ttu-id="5b6df-143">Wendet die Reflektionsrichtlinie auf einen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="5b6df-143">Applies reflection policy to a type and all its members.</span></span>|  
|[<span data-ttu-id="5b6df-144">\<TypeInstantiation></span><span class="sxs-lookup"><span data-stu-id="5b6df-144">\<TypeInstantiation></span></span>](typeinstantiation-element-net-native.md)|<span data-ttu-id="5b6df-145">Wendet die Reflektionsrichtlinie auf einen konstruierten generischen Typ und alle seine Member an.</span><span class="sxs-lookup"><span data-stu-id="5b6df-145">Applies reflection policy to a constructed generic type and all its members.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b6df-146">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b6df-146">Remarks</span></span>  
 <span data-ttu-id="5b6df-147">Wenn die Richtlinie einer Eigenschaft nicht explizit definiert ist, erbt sie die Laufzeitrichtlinie des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="5b6df-147">If a property's policy is not explicitly defined, it inherits the runtime policy of its parent element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b6df-148">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5b6df-148">Example</span></span>  
 <span data-ttu-id="5b6df-149">Im folgenden Beispiel wird Reflektion zum Instanziieren eines `Book`-Objekts und zum Anzeigen seiner Eigenschaftenwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="5b6df-149">The following example uses reflection to instantiate a `Book` object and display its property values.</span></span> <span data-ttu-id="5b6df-150">Die ursprüngliche Datei default.rd.xml für das Projekt sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="5b6df-150">The original default.rd.xml file for the project appears as follows:</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <Application>  
      <Namespace Name="LibraryApplications"  Browse="Required Public" >  
         <Type Name="Book"   Activate="All" />  
      </Namespace>  
   </Application>  
</Directives>  
```  
  
 <span data-ttu-id="5b6df-151">Die Datei wendet den Wert `All` auf die `Activate`-Richtlinie für die `Book`-Klasse an, die den Zugriff auf Klassenkonstruktoren über Reflektion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="5b6df-151">The file applies the `All` value to the `Activate` policy for the `Book` class, which allows access to class constructors through reflection.</span></span> <span data-ttu-id="5b6df-152">Die `Browse`-Richtlinie für die `Book`-Klasse wird vom übergeordneten Namespace geerbt.</span><span class="sxs-lookup"><span data-stu-id="5b6df-152">The `Browse` policy for the `Book` class is inherited from its parent namespace.</span></span> <span data-ttu-id="5b6df-153">Diese wird auf `Required Public` festgelegt, wodurch Metadaten zur Laufzeit verfügbar werden.</span><span class="sxs-lookup"><span data-stu-id="5b6df-153">This is set to `Required Public`, which makes metadata available at runtime.</span></span>  
  
 <span data-ttu-id="5b6df-154">Der Quellcode für das Beispiel lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="5b6df-154">The following is the source code for the example.</span></span> <span data-ttu-id="5b6df-155">Die `outputBlock` -Variable stellt <xref:Windows.UI.Xaml.Controls.TextBlock> ein-Steuerelement dar.</span><span class="sxs-lookup"><span data-stu-id="5b6df-155">The `outputBlock` variable represents a <xref:Windows.UI.Xaml.Controls.TextBlock> control.</span></span>  
  
 [!code-csharp[ProjectN_Reflection#6](../../../samples/snippets/csharp/VS_Snippets_CLR/projectn_reflection/cs/property1.cs#6)]  
  
 <span data-ttu-id="5b6df-156">Das Kompilieren und Ausführen dieses Beispiels löst jedoch eine [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md)-Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="5b6df-156">However, compiling and executing this example throws a [MissingRuntimeArtifactException](missingruntimeartifactexception-class-net-native.md) exception.</span></span> <span data-ttu-id="5b6df-157">Obwohl wir Metadaten für den `Book`-Typ verfügbar gemacht haben, haben wir keine Implementierungen der Eigenschaftengetter dynamisch zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="5b6df-157">Although we've made metadata for the `Book` type available, we've failed to make the implementations of the property getters available dynamically.</span></span> <span data-ttu-id="5b6df-158">Wir können diesen Fehler auf eine von zwei Arten beheben:</span><span class="sxs-lookup"><span data-stu-id="5b6df-158">We can correct this error by either in one of two ways:</span></span>  
  
- <span data-ttu-id="5b6df-159">Durch Definieren der `Dynamic`-Richtlinie für den `Book`-Typ in dessen [\<Type>](type-element-net-native.md)-Element.</span><span class="sxs-lookup"><span data-stu-id="5b6df-159">by defining the `Dynamic` policy for the `Book` type in its [\<Type>](type-element-net-native.md) element.</span></span>  
  
- <span data-ttu-id="5b6df-160">Durch Hinzufügen eines verschachtelten [\<Property>](property-element-net-native.md)-Elements für jede Eigenschaft, deren Getter wir wie in der folgenden Datei „default.rd.xml“ aufrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="5b6df-160">By adding a nested [\<Property>](property-element-net-native.md) element for each property whose getter we'd like to invoke, as the following default.rd.xml file does.</span></span>  
  
    ```xml  
    <Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
       <Application>  
          <Namespace Name="LibraryApplications"  Browse="Required Public" >  
             <Type Name="Book"   Activate="All" >  
                <Property Name="Title" Dynamic="Required" />  
                <Property Name="Author" Dynamic="Required" />  
                  <Property Name="ISBN" Dynamic="Required" />  
             </Type>  
          </Namespace>  
       </Application>  
    </Directives>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5b6df-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b6df-161">See also</span></span>

- [<span data-ttu-id="5b6df-162">Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))</span><span class="sxs-lookup"><span data-stu-id="5b6df-162">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="5b6df-163">Elemente der Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="5b6df-163">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
- [<span data-ttu-id="5b6df-164">Richtlinieneinstellungen für die Laufzeitanweisung</span><span class="sxs-lookup"><span data-stu-id="5b6df-164">Runtime Directive Policy Settings</span></span>](runtime-directive-policy-settings.md)
