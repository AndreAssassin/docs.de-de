---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 43415d9eac5e61f42006aecb3248dec9811eb3e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758131"
---
# <a name="transactedbatching"></a><span data-ttu-id="6ee75-101">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="6ee75-101">\<transactedBatching></span></span>

<span data-ttu-id="6ee75-102">Gibt an, ob Transaktionsbatching für Empfangsvorgänge unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="6ee75-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="6ee75-103">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="6ee75-103">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="6ee75-104">\<behaviors>\\</span><span class="sxs-lookup"><span data-stu-id="6ee75-104">\<behaviors>\\</span></span>
<span data-ttu-id="6ee75-105">\<endpointBehaviors>\\</span><span class="sxs-lookup"><span data-stu-id="6ee75-105">\<endpointBehaviors>\\</span></span>
<span data-ttu-id="6ee75-106">\<behavior>\\</span><span class="sxs-lookup"><span data-stu-id="6ee75-106">\<behavior>\\</span></span>
<span data-ttu-id="6ee75-107">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="6ee75-107">\<transactedBatching></span></span>

## <a name="syntax"></a><span data-ttu-id="6ee75-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ee75-108">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6ee75-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6ee75-109">Attributes and Elements</span></span>

<span data-ttu-id="6ee75-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6ee75-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="6ee75-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="6ee75-111">Attributes</span></span>

|<span data-ttu-id="6ee75-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="6ee75-112">Attribute</span></span>|<span data-ttu-id="6ee75-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ee75-113">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="6ee75-114">Eine ganze Zahl, die die maximale Anzahl an Empfangsvorgängen angibt, die in einer Transaktion zusammengefasst werden können.</span><span class="sxs-lookup"><span data-stu-id="6ee75-114">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="6ee75-115">Der Standard ist 0.</span><span class="sxs-lookup"><span data-stu-id="6ee75-115">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="6ee75-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ee75-116">Child Elements</span></span>

<span data-ttu-id="6ee75-117">Keine</span><span class="sxs-lookup"><span data-stu-id="6ee75-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="6ee75-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6ee75-118">Parent Elements</span></span>

|<span data-ttu-id="6ee75-119">Element</span><span class="sxs-lookup"><span data-stu-id="6ee75-119">Element</span></span>|<span data-ttu-id="6ee75-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ee75-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6ee75-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="6ee75-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="6ee75-122">Gibt ein Endpunktverhalten an.</span><span class="sxs-lookup"><span data-stu-id="6ee75-122">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6ee75-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ee75-123">Remarks</span></span>

<span data-ttu-id="6ee75-124">Ein Transport, der für Transaktionsbatchingversuche konfiguriert ist, um verschiedene Empfangsvorgänge in einer Transaktion zusammenzufassen.</span><span class="sxs-lookup"><span data-stu-id="6ee75-124">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="6ee75-125">Dadurch wird der relativ große Aufwand für das Erstellen und Übergeben einer Transaktion bei jedem Empfangsvorgang vermieden.</span><span class="sxs-lookup"><span data-stu-id="6ee75-125">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="6ee75-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ee75-126">Example</span></span>

<span data-ttu-id="6ee75-127">Im folgenden Beispiel wird gezeigt, wie einem Dienst das transaktive Batchverarbeitungsverhalten in einer Konfigurationsdatei hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="6ee75-127">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <behaviors>
    <endpointBehaviors>
      <behavior name="endpointBehavior">
        <transactedBatching maxBatchSize="10" />
      </behavior>
    </endpointBehaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="true" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

## <a name="see-also"></a><span data-ttu-id="6ee75-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ee75-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
