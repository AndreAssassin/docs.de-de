---
title: ExceptionThrown_V1-ETW-Ereignis
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91abd9e6f31380b7e8cd3df1a14aa5c5722901ba
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046513"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="22267-102">ExceptionThrown_V1-ETW-Ereignis</span><span class="sxs-lookup"><span data-stu-id="22267-102">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="22267-103">Dieses Ereignis erfasst Informationen über die ausgelösten Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="22267-103">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="22267-104">Die folgende Tabelle zeigt das Schlüsselwort, unter dem das Ereignis ausgelöst wird, und die Ebene des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="22267-104">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="22267-105">(Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="22267-105">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="22267-106">Schlüsselwort zum Auslösen des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="22267-106">Keyword for raising the event</span></span>|<span data-ttu-id="22267-107">Ebene</span><span class="sxs-lookup"><span data-stu-id="22267-107">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="22267-108">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="22267-108">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="22267-109">Warnung (2)</span><span class="sxs-lookup"><span data-stu-id="22267-109">Warning (2)</span></span>|  
  
 <span data-ttu-id="22267-110">Die folgende Tabelle zeigt die Ereignisinformationen an.</span><span class="sxs-lookup"><span data-stu-id="22267-110">The following table shows event information.</span></span>  
  
|<span data-ttu-id="22267-111">event</span><span class="sxs-lookup"><span data-stu-id="22267-111">Event</span></span>|<span data-ttu-id="22267-112">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="22267-112">Event ID</span></span>|<span data-ttu-id="22267-113">Wird ausgelöst, wenn</span><span class="sxs-lookup"><span data-stu-id="22267-113">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="22267-114">80</span><span class="sxs-lookup"><span data-stu-id="22267-114">80</span></span>|<span data-ttu-id="22267-115">Eine verwaltete Ausnahme wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="22267-115">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="22267-116">In der folgenden Tabelle finden Sie die Ereignisdaten.</span><span class="sxs-lookup"><span data-stu-id="22267-116">The following table shows event data.</span></span>  
  
|<span data-ttu-id="22267-117">Feldname</span><span class="sxs-lookup"><span data-stu-id="22267-117">Field name</span></span>|<span data-ttu-id="22267-118">Datentyp</span><span class="sxs-lookup"><span data-stu-id="22267-118">Data type</span></span>|<span data-ttu-id="22267-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="22267-119">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="22267-120">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="22267-120">Exception Type</span></span>|<span data-ttu-id="22267-121">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="22267-121">win:UnicodeString</span></span>|<span data-ttu-id="22267-122">Typ der Ausnahme, z.B. `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="22267-122">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="22267-123">Ausnahmemeldung</span><span class="sxs-lookup"><span data-stu-id="22267-123">Exception Message</span></span>|<span data-ttu-id="22267-124">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="22267-124">win:UnicodeString</span></span>|<span data-ttu-id="22267-125">Tatsächliche Ausnahmemeldung.</span><span class="sxs-lookup"><span data-stu-id="22267-125">Actual exception message.</span></span>|  
|<span data-ttu-id="22267-126">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="22267-126">EIPCodeThrow</span></span>|<span data-ttu-id="22267-127">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="22267-127">win:Pointer</span></span>|<span data-ttu-id="22267-128">Anweisungszeiger an der Stelle, an der die Ausnahme aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="22267-128">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="22267-129">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="22267-129">ExceptionHR</span></span>|<span data-ttu-id="22267-130">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="22267-130">win:UInt32</span></span>|<span data-ttu-id="22267-131">Ausnahme [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span><span class="sxs-lookup"><span data-stu-id="22267-131">Exception [HRESULT](https://go.microsoft.com/fwlink/?LinkId=179679).</span></span>|  
|<span data-ttu-id="22267-132">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="22267-132">ExceptionFlags</span></span>|<span data-ttu-id="22267-133">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="22267-133">win:UInt16</span></span>|<span data-ttu-id="22267-134">0x01 Hasinnerexception (siehe [CLR-ETW-Ereignisse](clr-etw-events.md) in der Visual Basic-Dokumentation).</span><span class="sxs-lookup"><span data-stu-id="22267-134">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="22267-135">0x02 IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="22267-135">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="22267-136">0x04 Isrethrownexception.</span><span class="sxs-lookup"><span data-stu-id="22267-136">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="22267-137">0x08 Isbeschätedstateexception (gibt an, dass der Prozessstatus beschädigt ist; weitere Informationen finden Sie unter [Behandlung von beschädigten Zustands Ausnahmen](https://go.microsoft.com/fwlink/?LinkId=179681) auf MSDN).</span><span class="sxs-lookup"><span data-stu-id="22267-137">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](https://go.microsoft.com/fwlink/?LinkId=179681) on MSDN).</span></span><br /><br /> <span data-ttu-id="22267-138">0x10 Isclscompliance (eine Ausnahme, die von <xref:System.Exception> abgeleitet ist, ist CLS-kompatibel, andernfalls ist Sie nicht CLS-kompatibel).</span><span class="sxs-lookup"><span data-stu-id="22267-138">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="22267-139">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="22267-139">ClrInstanceID</span></span>|<span data-ttu-id="22267-140">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="22267-140">win:UInt16</span></span>|<span data-ttu-id="22267-141">Eindeutige ID für die Instanz von CLR oder CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="22267-141">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22267-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22267-142">See also</span></span>

- [<span data-ttu-id="22267-143">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="22267-143">CLR ETW Events</span></span>](clr-etw-events.md)
