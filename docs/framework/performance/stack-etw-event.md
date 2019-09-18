---
title: ETW-Stapelereignis
ms.date: 03/30/2017
helpviewer_keywords:
- stack event [.NET Framework]
- ETW, stack event (CLR)
ms.assetid: f612fa5b-4b62-4593-a19e-85c9b1018dce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5dc23f5105b589d5b74c9ea6b7f40b84c2b04e6a
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046157"
---
# <a name="stack-etw-event"></a><span data-ttu-id="90389-102">ETW-Stapelereignis</span><span class="sxs-lookup"><span data-stu-id="90389-102">Stack ETW Event</span></span>
<span data-ttu-id="90389-103">Das Stapelereignis sollte in Verbindung mit anderen Ereignissen verwendet werden, um Stapelüberwachungen zu generieren, nachdem ein Ereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="90389-103">The stack event should be used in conjunction with other events to generate stack traces after an event is raised.</span></span> <span data-ttu-id="90389-104">Es wird protokolliert, wann der Laufzeitanbieter aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="90389-104">It is logged when the runtime provider is enabled.</span></span> <span data-ttu-id="90389-105">Dieses Ereignis hat eine hohe Frequenz, da es ausgelöst wird, wenn ein anderes Laufzeitereignis ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="90389-105">This is a very high frequency event, because it is raised whenever another runtime event is raised.</span></span> <span data-ttu-id="90389-106">Aus diesem Grund wird empfohlen, dass Sie dieses Ereignis mit Vorsicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="90389-106">For this reason, we recommend that you use this event with caution.</span></span>  
  
 <span data-ttu-id="90389-107">Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.</span><span class="sxs-lookup"><span data-stu-id="90389-107">The following table shows the keyword and level.</span></span> <span data-ttu-id="90389-108">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="90389-108">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="90389-109">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="90389-109">Keyword for raising the event</span></span>|<span data-ttu-id="90389-110">Ebene</span><span class="sxs-lookup"><span data-stu-id="90389-110">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="90389-111">`StackKeyword` (0x40000000)</span><span class="sxs-lookup"><span data-stu-id="90389-111">`StackKeyword` (0x40000000)</span></span>|<span data-ttu-id="90389-112">LogAlways(0)</span><span class="sxs-lookup"><span data-stu-id="90389-112">LogAlways(0)</span></span>|  
  
 <span data-ttu-id="90389-113">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="90389-113">The following table shows the event information.</span></span>  
  
|<span data-ttu-id="90389-114">event</span><span class="sxs-lookup"><span data-stu-id="90389-114">Event</span></span>|<span data-ttu-id="90389-115">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="90389-115">Event ID</span></span>|<span data-ttu-id="90389-116">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="90389-116">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`CLRStackWalk`|<span data-ttu-id="90389-117">82</span><span class="sxs-lookup"><span data-stu-id="90389-117">82</span></span>|<span data-ttu-id="90389-118">In Verbindung mit anderen Ereignissen zum Generieren von Stapelüberwachungen nach einem Ereignis.</span><span class="sxs-lookup"><span data-stu-id="90389-118">In conjunction with other events to generate stack traces following an event.</span></span>|  
  
 <span data-ttu-id="90389-119">Die folgende Tabelle zeigt die Ereignisdaten an.</span><span class="sxs-lookup"><span data-stu-id="90389-119">The following table shows the event data.</span></span>  
  
|<span data-ttu-id="90389-120">Feldname</span><span class="sxs-lookup"><span data-stu-id="90389-120">Field name</span></span>|<span data-ttu-id="90389-121">Datentyp</span><span class="sxs-lookup"><span data-stu-id="90389-121">Data Type</span></span>|<span data-ttu-id="90389-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="90389-122">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="90389-123">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="90389-123">ClrInstanceID</span></span>|<span data-ttu-id="90389-124">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="90389-124">win:Uint16</span></span>|<span data-ttu-id="90389-125">URI.</span><span class="sxs-lookup"><span data-stu-id="90389-125">Unique runtime identifier.</span></span>|  
|<span data-ttu-id="90389-126">Reserved1</span><span class="sxs-lookup"><span data-stu-id="90389-126">Reserved1</span></span>|<span data-ttu-id="90389-127">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="90389-127">win:UInt8</span></span>|<span data-ttu-id="90389-128">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="90389-128">Reserved.</span></span>|  
|<span data-ttu-id="90389-129">Reserved2</span><span class="sxs-lookup"><span data-stu-id="90389-129">Reserved2</span></span>|<span data-ttu-id="90389-130">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="90389-130">win:UInt8</span></span>|<span data-ttu-id="90389-131">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="90389-131">Reserved.</span></span>|  
|<span data-ttu-id="90389-132">FrameCount</span><span class="sxs-lookup"><span data-stu-id="90389-132">FrameCount</span></span>|<span data-ttu-id="90389-133">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="90389-133">win:UInt32</span></span>|<span data-ttu-id="90389-134">Die Anzahl von Frames in der Stapelüberwachung.</span><span class="sxs-lookup"><span data-stu-id="90389-134">The number of frames in the stack trace.</span></span>|  
|<span data-ttu-id="90389-135">Stapel</span><span class="sxs-lookup"><span data-stu-id="90389-135">Stack</span></span>|<span data-ttu-id="90389-136">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="90389-136">win:Pointer</span></span>|<span data-ttu-id="90389-137">Anweisungszeigerspalten.</span><span class="sxs-lookup"><span data-stu-id="90389-137">Columns of instruction pointers.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="90389-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90389-138">See also</span></span>

- [<span data-ttu-id="90389-139">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="90389-139">CLR ETW Events</span></span>](clr-etw-events.md)
