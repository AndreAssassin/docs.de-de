---
title: Unsicherer Code und Zeiger – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- security [C#], type safety
- C# language, unsafe code
- type safety [C#]
- unsafe keyword [C#]
- unsafe code [C#]
- C# language, pointers
- pointers [C#], about pointers
ms.assetid: b0fcca10-a92d-4f2a-835b-b0ccae6739ee
ms.openlocfilehash: 9f4e74e1e8fa71d1492a10162191822c1edfb635
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64608039"
---
# <a name="unsafe-code-and-pointers-c-programming-guide"></a><span data-ttu-id="93c1c-102">Unsicherer Code und Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="93c1c-102">Unsafe Code and Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="93c1c-103">Um Typsicherheit und Sicherheit zu gewährleisten, unterstützt C# standardmäßig keine Zeigerarithmetik.</span><span class="sxs-lookup"><span data-stu-id="93c1c-103">To maintain type safety and security, C# does not support pointer arithmetic, by default.</span></span> <span data-ttu-id="93c1c-104">Sie können jedoch das [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Schlüsselwort verwenden, um einen unsicheren Kontext zu definieren, in dem Zeiger verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="93c1c-104">However, by using the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, you can define an unsafe context in which pointers can be used.</span></span> <span data-ttu-id="93c1c-105">Weitere Informationen über Zeiger finden Sie unter [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="93c1c-105">For more information about pointers, see the topic [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="93c1c-106">In der Common Language Runtime (CLR) wird unsicherer Code als „nicht überprüfbarer Code“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="93c1c-106">In the common language runtime (CLR), unsafe code is referred to as unverifiable code.</span></span> <span data-ttu-id="93c1c-107">Unsicherer Code in C# ist nicht unbedingt gefährlich, es handelt sich dabei lediglich um einen Code, dessen Sicherheit nicht durch die CLR überprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="93c1c-107">Unsafe code in C# is not necessarily dangerous; it is just code whose safety cannot be verified by the CLR.</span></span> <span data-ttu-id="93c1c-108">Die CLR wird daher nur unsicheren Code ausführen, wenn sie sich in einer voll vertrauenswürdigen Assembly befindet.</span><span class="sxs-lookup"><span data-stu-id="93c1c-108">The CLR will therefore only execute unsafe code if it is in a fully trusted assembly.</span></span> <span data-ttu-id="93c1c-109">Wenn Sie unsicheren Code verwenden, liegt es in Ihrer Verantwortung, dafür zu sorgen, dass Ihr Code keine Sicherheitsrisiken oder Zeigerfehler enthält.</span><span class="sxs-lookup"><span data-stu-id="93c1c-109">If you use unsafe code, it is your responsibility to ensure that your code does not introduce security risks or pointer errors.</span></span>  
  
## <a name="unsafe-code-overview"></a><span data-ttu-id="93c1c-110">Übersicht über unsicheren Code</span><span class="sxs-lookup"><span data-stu-id="93c1c-110">Unsafe Code Overview</span></span>  
 <span data-ttu-id="93c1c-111">Unsicherer Code verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="93c1c-111">Unsafe code has the following properties:</span></span>  
  
- <span data-ttu-id="93c1c-112">Methoden, Typen und Codeblöcke können als unsicher definiert werden.</span><span class="sxs-lookup"><span data-stu-id="93c1c-112">Methods, types, and code blocks can be defined as unsafe.</span></span>  
  
- <span data-ttu-id="93c1c-113">In manchen Fällen kann unsicherer Code die Leistung einer Anwendung erhöhen, indem die Überprüfung von Arraygrenzen entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="93c1c-113">In some cases, unsafe code may increase an application's performance by removing array bounds checks.</span></span>  
  
- <span data-ttu-id="93c1c-114">Unsicherer Code ist erforderlich, wenn Sie native Funktionen aufrufen, die Zeiger erfordern.</span><span class="sxs-lookup"><span data-stu-id="93c1c-114">Unsafe code is required when you call native functions that require pointers.</span></span>  
  
- <span data-ttu-id="93c1c-115">Die Verwendung von unsicherem Code führt zu Sicherheits- und Stabilitätsrisiken.</span><span class="sxs-lookup"><span data-stu-id="93c1c-115">Using unsafe code introduces security and stability risks.</span></span>  
  
- <span data-ttu-id="93c1c-116">Damit unsicherer Code in C# kompiliert werden kann, muss die Anwendung mit [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="93c1c-116">In order for C# to compile unsafe code, the application must be compiled with [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md).</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="93c1c-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="93c1c-117">Related Sections</span></span>  
 <span data-ttu-id="93c1c-118">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="93c1c-118">For more information, see:</span></span>  
  
- [<span data-ttu-id="93c1c-119">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="93c1c-119">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
  
- [<span data-ttu-id="93c1c-120">Puffer fester Größe</span><span class="sxs-lookup"><span data-stu-id="93c1c-120">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)  
  
- [<span data-ttu-id="93c1c-121">Vorgehensweise: Verwenden von Zeigern zum Kopieren eines Bytearrays</span><span class="sxs-lookup"><span data-stu-id="93c1c-121">How to: Use Pointers to Copy an Array of Bytes</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-use-pointers-to-copy-an-array-of-bytes.md)  
  
- [<span data-ttu-id="93c1c-122">unsafe</span><span class="sxs-lookup"><span data-stu-id="93c1c-122">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="93c1c-123">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="93c1c-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="93c1c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93c1c-124">See also</span></span>

- [<span data-ttu-id="93c1c-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="93c1c-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
