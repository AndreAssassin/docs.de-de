---
title: ICorDebugRegisterSet2::GetRegistersAvailable-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::GetRegistersAvailable
helpviewer_keywords:
- GetRegistersAvailable method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
- ICorDebugRegisterSet2::GetRegistersAvailable method [.NET Framework debugging]
ms.assetid: f3ed344b-0d3a-44e8-8000-2a97e0805a2c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1522d643a69c47eec03770a8f51756dd4250075a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782823"
---
# <a name="icordebugregisterset2getregistersavailable-method"></a><span data-ttu-id="00406-102">ICorDebugRegisterSet2::GetRegistersAvailable-Methode</span><span class="sxs-lookup"><span data-stu-id="00406-102">ICorDebugRegisterSet2::GetRegistersAvailable Method</span></span>
<span data-ttu-id="00406-103">Ruft ein Array von Bytes, die eine Bitmap der die verfügbaren Register bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="00406-103">Gets an array of bytes that provides a bitmap of the available registers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00406-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00406-104">Syntax</span></span>  
  
```  
HRESULT GetRegistersAvailable (  
    [in] ULONG32 numChunks,  
    [out, size_is(numChunks)] BYTE availableRegChunks[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00406-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="00406-105">Parameters</span></span>  
 `numChunks`  
 <span data-ttu-id="00406-106">[in] Die Größe des `availableRegChunks`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="00406-106">[in] The size of the `availableRegChunks` array.</span></span>  
  
 `availableRegChunks`  
 <span data-ttu-id="00406-107">[out] Ein Array von Bytes, von denen jedes Bit eines Registers entspricht.</span><span class="sxs-lookup"><span data-stu-id="00406-107">[out] An array of bytes, each bit of which corresponds to a register.</span></span> <span data-ttu-id="00406-108">Wenn ein Register verfügbar ist, wird die entsprechende Bit des Registers festgelegt.</span><span class="sxs-lookup"><span data-stu-id="00406-108">If a register is available, the register's corresponding bit is set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00406-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00406-109">Remarks</span></span>  
 <span data-ttu-id="00406-110">Die Werte der CorDebugRegister-Enumeration angeben, die Register anderer Mikroprozessoren wird.</span><span class="sxs-lookup"><span data-stu-id="00406-110">The values of the CorDebugRegister enumeration specify the registers of different microprocessors.</span></span> <span data-ttu-id="00406-111">Die oberen fünf Bits der einzelnen Werte werden der Index der `availableRegChunks` Bytearray.</span><span class="sxs-lookup"><span data-stu-id="00406-111">The upper five bits of each value are the index into the `availableRegChunks` array of bytes.</span></span> <span data-ttu-id="00406-112">Die unteren drei Bits der einzelnen Werte identifizieren die Bitposition innerhalb des indizierten Byte.</span><span class="sxs-lookup"><span data-stu-id="00406-112">The lower three bits of each value identify the bit position within the indexed byte.</span></span> <span data-ttu-id="00406-113">Erhält eine `CorDebugRegister` Wert, der angibt, ein bestimmtes Register, die Position des Registers in der Maske wird wie folgt bestimmt:</span><span class="sxs-lookup"><span data-stu-id="00406-113">Given a `CorDebugRegister` value that specifies a particular register, the register's position in the mask is determined as follows:</span></span>  
  
1. <span data-ttu-id="00406-114">Extrahieren Sie Index benötigt Zugriff auf die richtige Byte in den `availableRegChunks` Array:</span><span class="sxs-lookup"><span data-stu-id="00406-114">Extract the index needed to access the correct byte in the `availableRegChunks` array:</span></span>  
  
     <span data-ttu-id="00406-115">`CorDebugRegister` Wert >> 3</span><span class="sxs-lookup"><span data-stu-id="00406-115">`CorDebugRegister` value >> 3</span></span>  
  
2. <span data-ttu-id="00406-116">Extrahieren Sie die Bitposition innerhalb des indizierten Byte, wobei das niederwertigste Bit von Bit 0 (null) ist:</span><span class="sxs-lookup"><span data-stu-id="00406-116">Extract the bit position within the indexed byte, where bit zero is the least significant bit:</span></span>  
  
     <span data-ttu-id="00406-117">`CorDebugRegister` Wert & 7</span><span class="sxs-lookup"><span data-stu-id="00406-117">`CorDebugRegister` value & 7</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00406-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00406-118">Requirements</span></span>  
 <span data-ttu-id="00406-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00406-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00406-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00406-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00406-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00406-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00406-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00406-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00406-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00406-123">See also</span></span>

- [<span data-ttu-id="00406-124">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00406-124">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="00406-125">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00406-125">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
