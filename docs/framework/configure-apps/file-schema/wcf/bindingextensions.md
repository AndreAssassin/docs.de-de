---
title: <bindingExtensions>
ms.date: 03/30/2017
ms.assetid: 8373f94d-d095-486f-8f1e-4ac2f72b58c7
ms.openlocfilehash: ed55701e45d8580e37cf4776de6b9c5241e0548c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673472"
---
# <a name="bindingextensions"></a><span data-ttu-id="132ca-101">\<bindingExtensions></span><span class="sxs-lookup"><span data-stu-id="132ca-101">\<bindingExtensions></span></span>
<span data-ttu-id="132ca-102">Dieser Abschnitt aktiviert die Verwendung einer benutzerdefinierten Bindung für eine Computer- oder Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="132ca-102">This section enables the use of a user defined binding from a machine or application configuration file.</span></span> <span data-ttu-id="132ca-103">Sie können eine benutzerdefinierte Bindung zur Auflistung hinzufügen, indem Sie das `add`-Schlüsselwort verwenden und das `type`-Attribut des Elements auf eine benutzerdefinierte Bindung sowie das `name`-Attribut auf den Namen der benutzerdefinierten Bindung festlegen.</span><span class="sxs-lookup"><span data-stu-id="132ca-103">You can add a user defined binding to this collection by using the `add` keyword, and setting the `type` attribute of the element to a user defined binding, as well as the `name` attribute to the name of the user defined binding.</span></span>  
  
 <span data-ttu-id="132ca-104">Bindungserweiterungen ermöglichen es dem Benutzer, benutzerdefinierte Bindungen als Teil einer Endpunktkonfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="132ca-104">Binding extensions enable the user to create user-defined bindings for use as part an endpoint configuration.</span></span> <span data-ttu-id="132ca-105">Eine Bindungserweiterung ist ein Typ, der die abstrakte Klasse <xref:System.ServiceModel.Channels.Binding> implementiert.</span><span class="sxs-lookup"><span data-stu-id="132ca-105">Programmatically, a binding extension is a type that implements the abstract class <xref:System.ServiceModel.Channels.Binding>.</span></span>  
  
 <span data-ttu-id="132ca-106">Im folgenden Beispiel werden das `add`-Element sowie das `name`-Attribut zum Hinzufügen einer Bindungserweiterung zum `bindingElementExtensions`-Abschnitt der Konfigurationsdatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="132ca-106">The following example uses the `add` element, as well as the `name` attribute to add a binding extension to the `bindingElementExtensions` section of the configuration file.</span></span>  
  
```xml  
<system.serviceModel>
  <extensions>
    <bindingExtensions>
      <add name="MyBinding"
           type="Microsoft.ServiceModel.Samples.MyBinding, MyBinding,
                 Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />
    </bindingExtensions>
  </extensions>
</system.serviceModel>
```  
  
 <span data-ttu-id="132ca-107">Zum Hinzufügen von Konfigurationsmöglichkeiten zum Element, muss der Benutzer ein `bindingSection`-Element schreiben und registrieren.</span><span class="sxs-lookup"><span data-stu-id="132ca-107">To add configuration abilities to the element, the user needs to write and register a `bindingSection` element.</span></span> <span data-ttu-id="132ca-108">Weitere Informationen dazu finden Sie in der <xref:System.Configuration>-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="132ca-108">For more information on this, see the <xref:System.Configuration> documentation.</span></span>  
  
 <span data-ttu-id="132ca-109">Nachdem das Element und sein Konfigurationstyp definiert wurden, kann die Erweiterung wie im folgenden Beispiel dargestellt als Teil eines Endpunkts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="132ca-109">After the element and its configuration type are defined, the extension can be used as part of an endpoint as shown in the following example.</span></span>  
  
```xml  
<services>
  <service name="MyService">
    <endpoint address="myAddress"
              binding="MyBinding" />
  </service>
</services>
```  
  
## <a name="see-also"></a><span data-ttu-id="132ca-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="132ca-110">See also</span></span>

- [<span data-ttu-id="132ca-111">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="132ca-111">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
