---
title: Elemente der Laufzeitanweisung
ms.date: 03/30/2017
ms.assetid: 3fe5848c-ecd7-4136-970b-8e48d250bde6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bf692ff93a575858d1d1a89346611cb9c5957b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59137812"
---
# <a name="runtime-directive-elements"></a>Elemente der Laufzeitanweisung
Das Dateiformat der Laufzeitanweisungen (rd.xml) unterstützt die folgenden Laufzeitanweisungselemente. Eine hierarchische Darstellung finden Sie unter [Runtime Directives (rd.xml) Configuration File Reference (Verweis auf die Konfigurationsdatei der Laufzeitanweisungen (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md).  
  
 [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)  
 Wendet die Laufzeitreflektionsrichtlinie auf alle von der Anwendung verwendeten Typen an und dient als Container für anwendungsweite Typen und Typmember, deren Metadaten für die Reflektion zur Laufzeit verfügbar sind. Dies ist ein untergeordnetes Element des [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)-Elements.  
  
 [\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an. Dies ist ein untergeordnetes Element der [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)- und [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Elemente.  
  
 [\<AttributeImplies>](../../../docs/framework/net-native/attributeimplies-element-net-native.md)  
 Wenn die enthaltende [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)-Anweisung ein Attribut ist, wird eine Laufzeitrichtlinie auf Codeelemente angewendet, auf die dieses Attribut angewendet wird.  
  
 [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)  
 Das Stammelement in jeder Laufzeitanweisungsdatei für [!INCLUDE[net_native](../../../includes/net-native-md.md)]. Die untergeordneten Elemente sind [\<Application>](../../../docs/framework/net-native/application-element-net-native.md) und [\<Library>](../../../docs/framework/net-native/library-element-net-native.md).  
  
 [\<Event>](../../../docs/framework/net-native/event-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf ein Ereignis an. Dies ist ein untergeordnetes Element der [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- und [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Elemente.  
  
 [\<Field>](../../../docs/framework/net-native/field-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf ein Feld an. Dies ist ein untergeordnetes Element der [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- und [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Elemente.  
  
 [\<GenericParameter>](../../../docs/framework/net-native/genericparameter-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf den Parametertyp eines generischen Typs oder einer generischen Methode an.  
  
 [\<ImpliesType>](../../../docs/framework/net-native/impliestype-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf einen Typ an, wenn diese Richtlinie auf den enthaltenden Typ oder die enthaltende Methode angewendet wurde.  
  
 [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf alle Typen in einer Assembly an. Dies ist ein untergeordnetes Element der [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)- und [\<Library>](../../../docs/framework/net-native/library-element-net-native.md)-Elemente.  
  
 [\<Method>](../../../docs/framework/net-native/method-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf eine Methode an. Dies ist ein untergeordnetes Element der [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- und [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Elemente.  
  
 [\<MethodInstantiation>](../../../docs/framework/net-native/methodinstantiation-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf eine konstruierte generische Methode an. Dies ist ein untergeordnetes Element der [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- und [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Elemente.  
  
 [\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf alle Typen in einem Namespace an.  
  
 [\<Parameter>](../../../docs/framework/net-native/parameter-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf den Typ des Arguments an, das an eine Methode übergeben wird.  
  
 [\<Property>](../../../docs/framework/net-native/property-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf eine Eigenschaft an. Dies ist ein untergeordnetes Element der [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)- und [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Elemente.  
  
 [\<Subtypes>](../../../docs/framework/net-native/subtypes-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf alle vom enthaltenden Typ geerbten Klassen an.  
  
 [\<Type>](../../../docs/framework/net-native/type-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf einen Typ an.  
  
 [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf einen konstruierten generischen Typ an.  
  
 [\<TypeParameter>](../../../docs/framework/net-native/typeparameter-element-net-native.md)  
 Wendet eine Laufzeitrichtlinie auf den Typ an, der durch ein <xref:System.Type>-Argument, das an eine Methode übergeben wird, dargestellt wird.  
  
## <a name="see-also"></a>Siehe auch

- [„rd.xml“-Konfigurationsdateireferenz](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
