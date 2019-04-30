---
title: ICorDebugThread2::GetConnectionID-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetConnectionID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetConnectionID
helpviewer_keywords:
- ICorDebugThread2::GetConnectionID method [.NET Framework debugging]
- GetConnectionID method [.NET Framework debugging]
ms.assetid: 9c76b587-f941-4fa1-8b86-f3494fb10c8e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7d51e21eab4ac1edc81b58171e5382ada170a57f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946337"
---
# <a name="icordebugthread2getconnectionid-method"></a><span data-ttu-id="f0256-102">ICorDebugThread2::GetConnectionID-Methode</span><span class="sxs-lookup"><span data-stu-id="f0256-102">ICorDebugThread2::GetConnectionID Method</span></span>
<span data-ttu-id="f0256-103">Ruft den Bezeichner der Verbindung für dieses ICorDebugThread2-Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="f0256-103">Gets the connection identifier for this ICorDebugThread2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0256-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0256-104">Syntax</span></span>  
  
```  
HRESULT GetConnectionID (  
    [out] CONNID *pdwConnectionId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0256-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0256-105">Parameters</span></span>  
 `pdwConnectionId`  
 <span data-ttu-id="f0256-106">[out] Ein `CONNID` , die den Bezeichner der Verbindung darstellt.</span><span class="sxs-lookup"><span data-stu-id="f0256-106">[out] A `CONNID` that represents the connection identifier.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0256-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0256-107">Remarks</span></span>  
 <span data-ttu-id="f0256-108">Die `GetConnectionID` Methode gibt 0 (null), in der `pdwConnectionId` -Parameters, wenn dieser Thread nicht Teil einer Verbindung ist.</span><span class="sxs-lookup"><span data-stu-id="f0256-108">The `GetConnectionID` method returns zero in the `pdwConnectionId` parameter, if this thread is not part of a connection.</span></span>  
  
 <span data-ttu-id="f0256-109">Wenn dieser Thread auf eine Instanz von Microsoft SQL Server 2005 Analysis Services (SSAS), besteht die `CONNID` ordnet einen Serverprozessbezeichner (SPID).</span><span class="sxs-lookup"><span data-stu-id="f0256-109">If this thread is connected to an instance of Microsoft SQL Server 2005 Analysis Services (SSAS), the `CONNID` maps to a server process identifier (SPID).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0256-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0256-110">Requirements</span></span>  
 <span data-ttu-id="f0256-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0256-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0256-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0256-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0256-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0256-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0256-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0256-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
