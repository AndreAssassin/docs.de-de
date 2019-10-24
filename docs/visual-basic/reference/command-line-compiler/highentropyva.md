---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
ms.openlocfilehash: 203380bbe2b2828e159ee36d795b6cd4a24e2917
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775657"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="505ff-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="505ff-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="505ff-103">Gibt an, ob eine ausführbare 64-Bit-Datei oder eine ausführbare Datei, die von der [-Plattform: anycpu-](../../../visual-basic/reference/command-line-compiler/platform.md) Compileroption gekennzeichnet ist, eine hohe Entropie Address Space Layout Randomization (ASLR) unter</span><span class="sxs-lookup"><span data-stu-id="505ff-103">Indicates whether a 64-bit executable or an executable that's marked by the [-platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="505ff-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="505ff-104">Syntax</span></span>  
  
```console  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="505ff-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="505ff-105">Arguments</span></span>  
 <span data-ttu-id="505ff-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="505ff-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="505ff-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="505ff-107">Optional.</span></span> <span data-ttu-id="505ff-108">Die Option ist standardmäßig deaktiviert, oder wenn Sie `-highentropyva-` angeben.</span><span class="sxs-lookup"><span data-stu-id="505ff-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="505ff-109">Wenn Sie `-highentropyva` oder `-highentropyva+` angeben, ist die Option auf ON festgelegt.</span><span class="sxs-lookup"><span data-stu-id="505ff-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="505ff-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="505ff-110">Remarks</span></span>  
 <span data-ttu-id="505ff-111">Wenn Sie diese Option angeben, können kompatible Versionen des Windows-Kernels ein höheres Maß an Entropie verwenden, wenn der Kernel das Adressraum Layout eines Prozesses als Teil von ASLR anordnet.</span><span class="sxs-lookup"><span data-stu-id="505ff-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="505ff-112">Wenn der Kernel ein höheres Maß an Entropie verwendet, kann den Arbeitsspeicher Bereichen wie Stapeln und Heaps eine größere Anzahl von Adressen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="505ff-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="505ff-113">Daher ist es schwieriger, den Ort eines bestimmten Speicherbereichs zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="505ff-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="505ff-114">Wenn die Option auf ON festgelegt ist, müssen die ausführbare Zieldatei und alle Module, von denen Sie abhängig ist, Zeiger Werte verarbeiten können, die größer als 4 Gigabyte (GB) sind, wenn diese Module als 64-Bit-Prozesse ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="505ff-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="505ff-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="505ff-115">See also</span></span>

- [<span data-ttu-id="505ff-116">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="505ff-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="505ff-117">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="505ff-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
