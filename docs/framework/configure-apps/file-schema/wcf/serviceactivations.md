---
title: <serviceActivations>
ms.date: 03/30/2017
ms.assetid: 97e665b6-1c51-410b-928a-9bb42c954ddb
ms.openlocfilehash: fb7c699612ef12aae39aaeadaf170d0e8f2553cd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936447"
---
# <a name="serviceactivations"></a><span data-ttu-id="c5b6f-101">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="c5b6f-101">\<serviceActivations></span></span>

<span data-ttu-id="c5b6f-102">Ein Konfigurationselement, mit dem Sie Einstellungen hinzufügen können, die Aktivierungs Einstellungen für virtuelle Dienste definieren, die Ihren Windows Communication Foundation (WCF)-Dienst Typen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-102">A configuration element that allows you to add settings that define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="c5b6f-103">Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-103">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="c5b6f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="c5b6f-104">\<system.ServiceModel></span></span>\
<span data-ttu-id="c5b6f-105">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="c5b6f-105">\<serviceHostingEnvironment></span></span>\
<span data-ttu-id="c5b6f-106">\<serviceActivations></span><span class="sxs-lookup"><span data-stu-id="c5b6f-106">\<serviceActivations></span></span>

## <a name="syntax"></a><span data-ttu-id="c5b6f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c5b6f-107">Syntax</span></span>

```xml
<serviceHostingEnvironment>
  <serviceActivations>
    <add factory="String"
         service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c5b6f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c5b6f-108">Attributes and Elements</span></span>

<span data-ttu-id="c5b6f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c5b6f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c5b6f-110">Attributes</span></span>

<span data-ttu-id="c5b6f-111">Keine</span><span class="sxs-lookup"><span data-stu-id="c5b6f-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="c5b6f-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5b6f-112">Child Elements</span></span>

|<span data-ttu-id="c5b6f-113">Element</span><span class="sxs-lookup"><span data-stu-id="c5b6f-113">Element</span></span>|<span data-ttu-id="c5b6f-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5b6f-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c5b6f-115">\<add></span><span class="sxs-lookup"><span data-stu-id="c5b6f-115">\<add></span></span>](add-of-serviceactivations.md)|<span data-ttu-id="c5b6f-116">Fügt ein Konfigurationselement hinzu, das die Aktivierung einer Dienstanwendung angibt.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-116">Adds a configuration element that specifies the activation of a service application.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="c5b6f-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c5b6f-117">Parent Elements</span></span>

|<span data-ttu-id="c5b6f-118">Element</span><span class="sxs-lookup"><span data-stu-id="c5b6f-118">Element</span></span>|<span data-ttu-id="c5b6f-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c5b6f-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c5b6f-120">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="c5b6f-120">\<serviceHostingEnvironment></span></span>](servicehostingenvironment.md)|<span data-ttu-id="c5b6f-121">Definiert den Typ, der von der Diensthostumgebung für einen besonderen Transport instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-121">Defines the type the service hosting environment instantiates for a particular transport.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c5b6f-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c5b6f-122">Remarks</span></span>

<span data-ttu-id="c5b6f-123">Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei web.config konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-123">The following example shows how to configure activation settings within your web.config file.</span></span>

```xml
<configuration>
  <system.serviceModel>
    <serviceHostingEnvironment>
      <serviceActivations>
        <add service="GreetingService" />
      </serviceActivations>
    </serviceHostingEnvironment>
  </system.serviceModel>
</configuration>
```

<span data-ttu-id="c5b6f-124">Mit dieser Konfiguration können Sie das GreetingService-Element aktivieren, ohne eine SVC-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-124">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="c5b6f-125">Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-125">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="c5b6f-126">Sie müssen das `web.config`-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-126">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="c5b6f-127">Außerdem `serviceHostingEnvironment` ist ein von MachineToApplication vererbbarer Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-127">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="c5b6f-128">Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-128">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="c5b6f-129">Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-129">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="c5b6f-130">Er erfordert Erweiterungen in der relativeAddress, z. b. svc,. XOML oder. xamlx.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-130">It requires extensions in the relativeAddress i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="c5b6f-131">Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-131">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="c5b6f-132">Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC-Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="c5b6f-132">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5b6f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c5b6f-133">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElementCollection>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
