---
title: Methodenparameter – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- methods [C#], parameters
- method parameters [C#]
- parameters [C#]
ms.assetid: 680e39ff-775b-48b0-9f47-4186a5bfc4a1
ms.openlocfilehash: 4011cbd3bc9306b64df87b1fcde48f1f41df8240
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602037"
---
# <a name="method-parameters-c-reference"></a><span data-ttu-id="49cb9-102">Methodenparameter (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="49cb9-102">Method Parameters (C# Reference)</span></span>

<span data-ttu-id="49cb9-103">Parameter, die ohne [in](./in-parameter-modifier.md), [ref](./ref.md) oder [out](./out-parameter-modifier.md) für eine Methode deklariert werden, werden nach Werten an die aufgerufene Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="49cb9-103">Parameters declared for a method without [in](./in-parameter-modifier.md), [ref](./ref.md) or [out](./out-parameter-modifier.md), are passed to the called method by value.</span></span> <span data-ttu-id="49cb9-104">Dieser Wert kann in der Methode geändert werden, aber der geänderte Wert wird nicht gespeichert, wenn die aufrufende Prozedur wieder die Steuerung übernimmt.</span><span class="sxs-lookup"><span data-stu-id="49cb9-104">That value can be changed in the method, but the changed value will not be retained when control passes back to the calling procedure.</span></span> <span data-ttu-id="49cb9-105">Wenn Sie ein Schlüsselwort für einen Methodenparameter verwenden, können Sie dieses Verhalten ändern.</span><span class="sxs-lookup"><span data-stu-id="49cb9-105">By using a method parameter keyword, you can change this behavior.</span></span>  
  
 <span data-ttu-id="49cb9-106">In diesem Abschnitt wird das Schlüsselwort beschrieben, dass Sie verwenden können, wenn Sie Methodenparameter deklarieren.</span><span class="sxs-lookup"><span data-stu-id="49cb9-106">This section describes the keywords you can use when declaring method parameters:</span></span>  
  
- <span data-ttu-id="49cb9-107">Mit [params](./params.md) wird festgelegt, dass für diesen Parameter eine veränderliche Anzahl von Argumenten akzeptiert werden.</span><span class="sxs-lookup"><span data-stu-id="49cb9-107">[params](./params.md) specifies that this parameter may take a variable number of arguments.</span></span>
  
- <span data-ttu-id="49cb9-108">Mit [in](./in-parameter-modifier.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird, jedoch nur von der aufgerufenen Methode gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="49cb9-108">[in](./in-parameter-modifier.md) specifies that this parameter is passed by reference but is only read by the called method.</span></span>
  
- <span data-ttu-id="49cb9-109">Mit [ref](./ref.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird und von der aufgerufenen Methode gelesen oder geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="49cb9-109">[ref](./ref.md) specifies that this parameter is passed by reference and may be read or written by the called method.</span></span>
  
- <span data-ttu-id="49cb9-110">Mit [out](./out-parameter-modifier.md) wird festgelegt, dass dieser Parameter als Verweis übergeben wird und von der aufgerufenen Methode geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="49cb9-110">[out](./out-parameter-modifier.md) specifies that this parameter is passed by reference and is written by the called method.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="49cb9-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49cb9-111">See also</span></span>

- [<span data-ttu-id="49cb9-112">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="49cb9-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="49cb9-113">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="49cb9-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="49cb9-114">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="49cb9-114">C# Keywords</span></span>](./index.md)
