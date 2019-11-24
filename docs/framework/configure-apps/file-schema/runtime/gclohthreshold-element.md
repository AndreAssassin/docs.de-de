---
title: GCLOHThreshold element
ms.date: 11/20/2019
helpviewer_keywords:
- GCLOHThreshold element
- <GCLOHThreshold> element
ms.openlocfilehash: d72dc9d27984f60dfb6296217263ce8b176093c6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74451323"
---
# <a name="gclohthreshold-element"></a><span data-ttu-id="2b4c4-102">GCLOHThreshold element</span><span class="sxs-lookup"><span data-stu-id="2b4c4-102">GCLOHThreshold element</span></span>

<span data-ttu-id="2b4c4-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span><span class="sxs-lookup"><span data-stu-id="2b4c4-103">Specifies the threshold size, in bytes, that causes the garbage collector to put objects on the large object heap (LOH).</span></span>

<span data-ttu-id="2b4c4-104">[\<configuration>](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2b4c4-104">[\<configuration>](../configuration-element.md)</span></span>\
<span data-ttu-id="2b4c4-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="2b4c4-105">&nbsp;&nbsp;[\<runtime>](runtime-element.md)</span></span>\
<span data-ttu-id="2b4c4-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold></span><span class="sxs-lookup"><span data-stu-id="2b4c4-106">&nbsp;&nbsp;&nbsp;&nbsp;\<GCLOHThreshold></span></span>

## <a name="syntax"></a><span data-ttu-id="2b4c4-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b4c4-107">Syntax</span></span>

```xml
<GCLOHThreshold
   enabled="nnnn"/>
```

## <a name="attributes"></a><span data-ttu-id="2b4c4-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="2b4c4-108">Attributes</span></span>

|<span data-ttu-id="2b4c4-109">Attribut</span><span class="sxs-lookup"><span data-stu-id="2b4c4-109">Attribute</span></span>|<span data-ttu-id="2b4c4-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b4c4-110">Description</span></span>|
|---------------|-----------------|
|`enabled`|<span data-ttu-id="2b4c4-111">Erforderliches Attribut.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-111">Required attribute.</span></span><br /><br /><span data-ttu-id="2b4c4-112">Specifies the threshold size that causes objects to go on the large object heap.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-112">Specifies the threshold size that causes objects to go on the large object heap.</span></span>|

### <a name="enabled-attribute"></a><span data-ttu-id="2b4c4-113">enabled attribute</span><span class="sxs-lookup"><span data-stu-id="2b4c4-113">enabled attribute</span></span>

|<span data-ttu-id="2b4c4-114">Wert</span><span class="sxs-lookup"><span data-stu-id="2b4c4-114">Value</span></span>|<span data-ttu-id="2b4c4-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b4c4-115">Description</span></span>|
|-----------|-----------------|
|`nnnn`|<span data-ttu-id="2b4c4-116">The threshold size, in bytes, that causes objects to go on the large object heap.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-116">The threshold size, in bytes, that causes objects to go on the large object heap.</span></span>|

## <a name="child-elements"></a><span data-ttu-id="2b4c4-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b4c4-117">Child elements</span></span>

<span data-ttu-id="2b4c4-118">Keine</span><span class="sxs-lookup"><span data-stu-id="2b4c4-118">None.</span></span>

## <a name="parent-elements"></a><span data-ttu-id="2b4c4-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2b4c4-119">Parent elements</span></span>

|<span data-ttu-id="2b4c4-120">Element</span><span class="sxs-lookup"><span data-stu-id="2b4c4-120">Element</span></span>|<span data-ttu-id="2b4c4-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2b4c4-121">Description</span></span>|
|-------------|-----------------|
|`configuration`|<span data-ttu-id="2b4c4-122">Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`runtime`|<span data-ttu-id="2b4c4-123">Enthält Informationen über die Assemblybindung und die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-123">Contains information about assembly binding and garbage collection.</span></span>|

## <a name="remarks"></a><span data-ttu-id="2b4c4-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b4c4-124">Remarks</span></span>

<span data-ttu-id="2b4c4-125">This setting was introduced in .NET Framework 4.8.</span><span class="sxs-lookup"><span data-stu-id="2b4c4-125">This setting was introduced in .NET Framework 4.8.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b4c4-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b4c4-126">See also</span></span>

- [<span data-ttu-id="2b4c4-127">Run-time settings schema</span><span class="sxs-lookup"><span data-stu-id="2b4c4-127">Run-time settings schema</span></span>](index.md)
- [<span data-ttu-id="2b4c4-128">Konfigurationsdateischema</span><span class="sxs-lookup"><span data-stu-id="2b4c4-128">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="2b4c4-129">Grundlagen der Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="2b4c4-129">Fundamentals of garbage collection</span></span>](../../../../standard/garbage-collection/fundamentals.md)
- [<span data-ttu-id="2b4c4-130">NET Core run-time config options for GC</span><span class="sxs-lookup"><span data-stu-id="2b4c4-130">NET Core run-time config options for GC</span></span>](../../../../core/run-time-config/garbage-collector.md)
