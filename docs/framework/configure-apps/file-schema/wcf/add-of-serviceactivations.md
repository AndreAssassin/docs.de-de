---
title: <add> von <serviceActivations>
ms.date: 03/30/2017
ms.assetid: e5b01fc8-ee84-48b7-95fd-95ab54fa871f
ms.openlocfilehash: 2a3ba6d41059a480fe610254c0407df16d149e3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61701462"
---
# <a name="add-of-serviceactivations"></a><span data-ttu-id="cfe4f-102">\<Hinzufügen > der \<ServiceActivations ></span><span class="sxs-lookup"><span data-stu-id="cfe4f-102">\<add> of \<serviceActivations></span></span>

<span data-ttu-id="cfe4f-103">Ein Konfigurationselement, das können Sie virtuelle dienstaktivierungseinstellungen zu definieren, die die Windows Communication Foundation (WCF) Diensttypen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-103">A configuration element that allows you to define virtual service activation settings that map to your Windows Communication Foundation (WCF) service types.</span></span> <span data-ttu-id="cfe4f-104">Auf diese Weise können Sie in WAS/IIS gehostete Dienste ohne eine SVC-Datei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-104">This makes it possible to activate services hosted in WAS/IIS without an .svc file.</span></span>

<span data-ttu-id="cfe4f-105">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="cfe4f-105">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="cfe4f-106">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="cfe4f-106">\<serviceHostingEnvironment></span></span>

## <a name="syntax"></a><span data-ttu-id="cfe4f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="cfe4f-107">Syntax</span></span>

```xml
<serviceHostingEnvironment>
    <serviceActivations>
      <add factory="String"
           service="String" />
  </serviceActivations>
</serviceHostingEnvironment>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="cfe4f-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="cfe4f-108">Attributes and Elements</span></span>

<span data-ttu-id="cfe4f-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-109">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="cfe4f-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="cfe4f-110">Attributes</span></span>

|<span data-ttu-id="cfe4f-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="cfe4f-111">Attribute</span></span>|<span data-ttu-id="cfe4f-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfe4f-112">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="cfe4f-113">factory</span><span class="sxs-lookup"><span data-stu-id="cfe4f-113">factory</span></span>|<span data-ttu-id="cfe4f-114">Eine Zeichenfolge, die den CLR-Typnamen der Factory angibt, die ein Dienstaktivierungselement generiert.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-114">A string that specifies the CLR type name of the factory that generates a service activation element.</span></span>|
|<span data-ttu-id="cfe4f-115">service</span><span class="sxs-lookup"><span data-stu-id="cfe4f-115">service</span></span>|<span data-ttu-id="cfe4f-116">Der ServiceType, der den Dienst implementiert (entweder der vollqualifizierte Typname oder der kurze Typname, falls im Ordner "App_Code" enthalten).</span><span class="sxs-lookup"><span data-stu-id="cfe4f-116">The ServiceType that implements the service (either the full qualified Typename or the short Typename (when it is placed in the App_Code folder).</span></span>|
|<span data-ttu-id="cfe4f-117">relativeAddress</span><span class="sxs-lookup"><span data-stu-id="cfe4f-117">relativeAddress</span></span>|<span data-ttu-id="cfe4f-118">Die relative Adresse innerhalb der aktuellen IIS-Anwendung, z. B. "Service.svc".</span><span class="sxs-lookup"><span data-stu-id="cfe4f-118">The relative address within the current IIS application - for example "Service.svc".</span></span> <span data-ttu-id="cfe4f-119">In WCF 4.0 muss diese relative Adresse eine der gültigen Dateierweiterungen (.svc, .xamlx, …) enthalten. Für relativeUrl muss keine physische Datei vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-119">In WCF 4.0 this relative address has to contain one of the known file extensions (.svc, .xamlx, ...). No physical file has to exist for the relativeUrl</span></span>|

### <a name="child-elements"></a><span data-ttu-id="cfe4f-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cfe4f-120">Child Elements</span></span>

<span data-ttu-id="cfe4f-121">Keine</span><span class="sxs-lookup"><span data-stu-id="cfe4f-121">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="cfe4f-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="cfe4f-122">Parent Elements</span></span>

|<span data-ttu-id="cfe4f-123">Element</span><span class="sxs-lookup"><span data-stu-id="cfe4f-123">Element</span></span>|<span data-ttu-id="cfe4f-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cfe4f-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="cfe4f-125">\<serviceHostingEnvironment></span><span class="sxs-lookup"><span data-stu-id="cfe4f-125">\<serviceHostingEnvironment></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|<span data-ttu-id="cfe4f-126">Ein Konfigurationsabschnitt, der Aktivierungseinstellungen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-126">A configuration section that describes activation settings.</span></span>|

## <a name="remarks"></a><span data-ttu-id="cfe4f-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cfe4f-127">Remarks</span></span>

<span data-ttu-id="cfe4f-128">Im folgenden Beispiel wird gezeigt, wie Aktivierungseinstellungen innerhalb der Datei web.config konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-128">The following example shows how to configure activation settings within your web.config file.</span></span>

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

<span data-ttu-id="cfe4f-129">Mit dieser Konfiguration können Sie das GreetingService-Element aktivieren, ohne eine SVC-Datei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-129">Using this configuration, you can activate the GreetingService without using an .svc file.</span></span>

<span data-ttu-id="cfe4f-130">Beachten Sie, dass es sich bei `<serviceHostingEnvironment>` um eine Konfiguration auf Anwendungsebene handelt.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-130">Note that `<serviceHostingEnvironment>` is an application level configuration.</span></span> <span data-ttu-id="cfe4f-131">Sie müssen das `web.config`-Element, das die Konfiguration enthält, unter dem Stammelement der virtuellen Anwendung platzieren.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-131">You have to place the `web.config` containing the configuration under the root of the virtual Application.</span></span> <span data-ttu-id="cfe4f-132">Darüber hinaus `serviceHostingEnvironment` ist ein MachineToApplication-vererbbarer Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-132">In addition, `serviceHostingEnvironment` is a machineToApplication inheritable section.</span></span> <span data-ttu-id="cfe4f-133">Wenn Sie einen einzelnen Dienst im Stammelement des Computers registrieren, erbt jeder Dienst in der Anwendung diesen Dienst.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-133">If you register a single service in the root of the machine, every service in the application will inherit this service.</span></span>

<span data-ttu-id="cfe4f-134">Die konfigurationsbasierte Aktivierung unterstützt sowohl die Aktivierung über http als auch über ein anderes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-134">Configuration-based activation supports activation over both http and non-http protocol.</span></span> <span data-ttu-id="cfe4f-135">Sie erfordert Erweiterungen im der RelativeAddress, z. B. .svc, .xoml oder xamlx.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-135">It requires extensions in the relativeAddress, i.e. .svc, .xoml or .xamlx.</span></span> <span data-ttu-id="cfe4f-136">Sie können den bekannten buildProviders eigene Erweiterungen zuordnen, die Ihnen dann ermöglichen, den Dienst über eine beliebige Erweiterung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-136">You can map your own extensions to the know buildProviders, which will then enable you to activate service over any extension.</span></span> <span data-ttu-id="cfe4f-137">Bei einem Konflikt überschreibt der Abschnitt `<serviceActivations>` die SVC-Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="cfe4f-137">Upon conflict, the `<serviceActivations>` section overrides .svc registrations.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfe4f-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cfe4f-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.ServiceActivationElement>
- <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>
- <xref:System.ServiceModel.ServiceHostingEnvironment>
