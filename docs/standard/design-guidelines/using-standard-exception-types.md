---
title: Verwenden von Standardausnahmetypen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: KrzysztofCwalina
ms.openlocfilehash: b947c7cce057c060b1ab5054d1227f5703ccbf89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026335"
---
# <a name="using-standard-exception-types"></a><span data-ttu-id="f2b2b-102">Verwenden von Standardausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="f2b2b-102">Using Standard Exception Types</span></span>
<span data-ttu-id="f2b2b-103">Dieser Abschnitt beschreibt die Standardausnahmen, die durch das Framework sowie Details zu ihrer Verwendung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-103">This section describes the standard exceptions provided by the Framework and the details of their usage.</span></span> <span data-ttu-id="f2b2b-104">Die Liste ist keineswegs vollständig.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-104">The list is by no means exhaustive.</span></span> <span data-ttu-id="f2b2b-105">Finden Sie in der .NET Framework-Referenzdokumentation für die Verwendung mit anderen Framework-Ausnahmetypen.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-105">Please refer to the .NET Framework reference documentation for usage of other Framework exception types.</span></span>  
  
## <a name="exception-and-systemexception"></a><span data-ttu-id="f2b2b-106">Ausnahmen und SystemException</span><span class="sxs-lookup"><span data-stu-id="f2b2b-106">Exception and SystemException</span></span>  
 <span data-ttu-id="f2b2b-107">**X DO NOT** auslösen <xref:System.Exception?displayProperty=nameWithType> oder <xref:System.SystemException?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-107">**X DO NOT** throw <xref:System.Exception?displayProperty=nameWithType> or <xref:System.SystemException?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="f2b2b-108">**X DO NOT** catch `System.Exception` oder `System.SystemException` in Frameworkcode, es sei denn, Sie erneut auslösen möchten.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-108">**X DO NOT** catch `System.Exception` or `System.SystemException` in framework code, unless you intend to rethrow.</span></span>  
  
 <span data-ttu-id="f2b2b-109">**X AVOID** abfangen `System.Exception` oder `System.SystemException`, außer bei Ausnahmehandler der obersten Ebene.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-109">**X AVOID** catching `System.Exception` or `System.SystemException`, except in top-level exception handlers.</span></span>  
  
## <a name="applicationexception"></a><span data-ttu-id="f2b2b-110">ApplicationException</span><span class="sxs-lookup"><span data-stu-id="f2b2b-110">ApplicationException</span></span>  
 <span data-ttu-id="f2b2b-111">**X DO NOT** lösen oder eine Ableitung von <xref:System.ApplicationException>.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-111">**X DO NOT** throw or derive from <xref:System.ApplicationException>.</span></span>  
  
## <a name="invalidoperationexception"></a><span data-ttu-id="f2b2b-112">InvalidOperationException</span><span class="sxs-lookup"><span data-stu-id="f2b2b-112">InvalidOperationException</span></span>  
 <span data-ttu-id="f2b2b-113">**✓ DO** Auslösen einer <xref:System.InvalidOperationException> , wenn das Objekt in einem unzulässigen Zustand ist.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-113">**✓ DO** throw an <xref:System.InvalidOperationException> if the object is in an inappropriate state.</span></span>  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a><span data-ttu-id="f2b2b-114">ArgumentException "ArgumentNullException" und ArgumentOutOfRangeException</span><span class="sxs-lookup"><span data-stu-id="f2b2b-114">ArgumentException, ArgumentNullException, and ArgumentOutOfRangeException</span></span>  
 <span data-ttu-id="f2b2b-115">**✓ DO** auslösen <xref:System.ArgumentException> oder einem seiner Untertypen, wenn ungültige Argumente auf einen Member übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-115">**✓ DO** throw <xref:System.ArgumentException> or one of its subtypes if bad arguments are passed to a member.</span></span> <span data-ttu-id="f2b2b-116">Bevorzugen Sie am weitesten abgeleiteten Ausnahmetyp, falls zutreffend.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-116">Prefer the most derived exception type, if applicable.</span></span>  
  
 <span data-ttu-id="f2b2b-117">**✓ DO** legen Sie die `ParamName` Eigenschaft, die beim Auslösen einer die Unterklasse von `ArgumentException`.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-117">**✓ DO** set the `ParamName` property when throwing one of the subclasses of `ArgumentException`.</span></span>  
  
 <span data-ttu-id="f2b2b-118">Diese Eigenschaft stellt den Namen des Parameters, der die Ausnahme ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-118">This property represents the name of the parameter that caused the exception to be thrown.</span></span> <span data-ttu-id="f2b2b-119">Beachten Sie, dass die Eigenschaft mit einer der überladenen Konstruktor festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-119">Note that the property can be set using one of the constructor overloads.</span></span>  
  
 <span data-ttu-id="f2b2b-120">**✓ DO** verwenden `value` für den Namen des Parameters impliziter Wert der Eigenschaftensetter.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-120">**✓ DO** use `value` for the name of the implicit value parameter of property setters.</span></span>  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a><span data-ttu-id="f2b2b-121">"NullReferenceException" IndexOutOfRangeException und AccessViolationException</span><span class="sxs-lookup"><span data-stu-id="f2b2b-121">NullReferenceException, IndexOutOfRangeException, and AccessViolationException</span></span>  
 <span data-ttu-id="f2b2b-122">**X DO NOT** ermöglichen öffentlich aufrufbare APIs explizit oder implizit auslöst <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, oder <xref:System.IndexOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-122">**X DO NOT** allow publicly callable APIs to explicitly or implicitly throw <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, or <xref:System.IndexOutOfRangeException>.</span></span> <span data-ttu-id="f2b2b-123">Diese Ausnahmen sind reserviert und wird von der ausführungs-Engine ausgelöst und in den meisten Fällen einen Fehler hinweisen.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-123">These exceptions are reserved and thrown by the execution engine and in most cases indicate a bug.</span></span>  
  
 <span data-ttu-id="f2b2b-124">Führen Sie Argument überprüfen, um zu vermeiden, diese Ausnahmen auslösen.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-124">Do argument checking to avoid throwing these exceptions.</span></span> <span data-ttu-id="f2b2b-125">Diese Ausnahmen auslösen, stellt Details zur Implementierung der Methode, die sich im Laufe der Zeit ändern kann.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-125">Throwing these exceptions exposes implementation details of your method that might change over time.</span></span>  
  
## <a name="stackoverflowexception"></a><span data-ttu-id="f2b2b-126">StackOverflowException</span><span class="sxs-lookup"><span data-stu-id="f2b2b-126">StackOverflowException</span></span>  
 <span data-ttu-id="f2b2b-127">**X DO NOT** explizit auslösen <xref:System.StackOverflowException>.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-127">**X DO NOT** explicitly throw <xref:System.StackOverflowException>.</span></span> <span data-ttu-id="f2b2b-128">Die Ausnahme sollte nur von der CLR explizit ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-128">The exception should be explicitly thrown only by the CLR.</span></span>  
  
 <span data-ttu-id="f2b2b-129">**X DO NOT** catch `StackOverflowException`.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-129">**X DO NOT** catch `StackOverflowException`.</span></span>  
  
 <span data-ttu-id="f2b2b-130">Es ist nahezu unmöglich, verwalteten Code schreiben, der bei beliebigen Stapelüberläufe konsistent bleibt.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-130">It is almost impossible to write managed code that remains consistent in the presence of arbitrary stack overflows.</span></span> <span data-ttu-id="f2b2b-131">Mithilfe von Tests um zu verschieben, dass klar definierte stellen Stapelüberläufe anstatt aus beliebigen Stapelüberläufe zurückziehen, wird von die nicht verwalteten Teilen der CLR konsistent bleiben.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-131">The unmanaged parts of the CLR remain consistent by using probes to move stack overflows to well-defined places rather than by backing out from arbitrary stack overflows.</span></span>  
  
## <a name="outofmemoryexception"></a><span data-ttu-id="f2b2b-132">OutOfMemoryException</span><span class="sxs-lookup"><span data-stu-id="f2b2b-132">OutOfMemoryException</span></span>  
 <span data-ttu-id="f2b2b-133">**X DO NOT** explizit auslösen <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-133">**X DO NOT** explicitly throw <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="f2b2b-134">Diese Ausnahme wird nur von der CLR-Infrastruktur ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-134">This exception is to be thrown only by the CLR infrastructure.</span></span>  
  
## <a name="comexception-sehexception-and-executionengineexception"></a><span data-ttu-id="f2b2b-135">ComException, ExecutionEngineException und SEHException-Ausnahme</span><span class="sxs-lookup"><span data-stu-id="f2b2b-135">ComException, SEHException, and ExecutionEngineException</span></span>  
 <span data-ttu-id="f2b2b-136">**X DO NOT** explizit auslösen <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, und <xref:System.Runtime.InteropServices.SEHException>.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-136">**X DO NOT** explicitly throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, and <xref:System.Runtime.InteropServices.SEHException>.</span></span> <span data-ttu-id="f2b2b-137">Diese Ausnahmen werden nur von der CLR-Infrastruktur ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="f2b2b-137">These exceptions are to be thrown only by the CLR infrastructure.</span></span>  
  
 <span data-ttu-id="f2b2b-138">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="f2b2b-138">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f2b2b-139">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="f2b2b-139">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b2b-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2b2b-140">See also</span></span>

- [<span data-ttu-id="f2b2b-141">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f2b2b-141">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="f2b2b-142">Entwurfsrichtlinien für Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="f2b2b-142">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)
