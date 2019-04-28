---
title: -Subsystemversion (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /subsystemversion compiler option [Visual Basic]
- -subsystemversion compiler option [Visual Basic]
- subsystemversion compiler option [Visual Basic]
ms.assetid: 08be22b2-f447-4cd3-8203-120b1b920b54
ms.openlocfilehash: 0eca7918e5e4b8702858f972003faef1274e56e3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61796240"
---
# <a name="-subsystemversion-visual-basic"></a><span data-ttu-id="0ebf9-102">-Subsystemversion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ebf9-102">-subsystemversion (Visual Basic)</span></span>

<span data-ttu-id="0ebf9-103">Gibt die Mindestversion des Subsystems an, das die erzeugte ausführbare Datei ausführen kann. Dabei bestimmt sie die Version von Windows, auf der die ausführbare Datei ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-103">Specifies the minimum version of the subsystem on which the generated executable file can run, thereby determining the versions of Windows on which the executable file can run.</span></span> <span data-ttu-id="0ebf9-104">In den meisten Fällen stellt diese Option sicher, dass die ausführbare Datei bestimmte Sicherheitsfunktionen nutzt, die nicht in älteren Versionen von Windows verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-104">Most commonly, this option ensures that the executable file can leverage particular security features that aren’t available with older versions of Windows.</span></span>

> [!NOTE]
> <span data-ttu-id="0ebf9-105">Verwenden Sie zum Angeben des Subsystems die Compileroption [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0ebf9-105">To specify the subsystem itself, use the [-target](../../../csharp/language-reference/compiler-options/target-compiler-option.md) compiler option.</span></span>

## <a name="syntax"></a><span data-ttu-id="0ebf9-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ebf9-106">Syntax</span></span>

```vb
-subsystemversion:major.minor
```

## <a name="parameters"></a><span data-ttu-id="0ebf9-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ebf9-107">Parameters</span></span>

`major.minor`

<span data-ttu-id="0ebf9-108">Die mindestens erforderliche Version des Subsystems wird in einer Punktschreibweise für Haupt- und Nebenversionen ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-108">The minimum required version of the subsystem, as expressed in a dot notation for major and minor versions.</span></span> <span data-ttu-id="0ebf9-109">Beispielsweise können Sie angeben, dass eine Anwendung nicht unter einem Betriebssystem, das älter als Windows 7 ist, ausgeführt werden kann,wenn Sie den Werte dieser Option auf 6.01 festlegen, wie es in der Tabelle in diesem Thema zu einem späteren Zeitpunkt beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-109">For example, you can specify that an application can't run on an operating system that's older than Windows 7 if you set the value of this option to 6.01, as the table later in this topic describes.</span></span> <span data-ttu-id="0ebf9-110">Sie müssen die Werte für `major` und `minor` als ganze Zahl angeben.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-110">You must specify the values for `major` and `minor` as integers.</span></span>

<span data-ttu-id="0ebf9-111">Führende Nullen in der Version `minor` ändern die Version nicht, jedoch nachfolgende Nullen.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-111">Leading zeroes in the `minor` version don't change the version, but trailing zeroes do.</span></span> <span data-ttu-id="0ebf9-112">6.1 und 6.01 verweisen z.B. auf die gleiche Version, aber 6.10 verweist auf eine andere Version.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-112">For example, 6.1 and 6.01 refer to the same version, but 6.10 refers to a different version.</span></span> <span data-ttu-id="0ebf9-113">Es wird empfohlen, die Nebenversion in Form von zwei Ziffern auszudrücken, um Verwechslungen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-113">We recommend expressing the minor version as two digits to avoid confusion.</span></span>

## <a name="remarks"></a><span data-ttu-id="0ebf9-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0ebf9-114">Remarks</span></span>

<span data-ttu-id="0ebf9-115">Die folgende Tabelle enthält allgemeine Subsystemversionen von Windows.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-115">The following table lists common subsystem versions of Windows.</span></span>

|<span data-ttu-id="0ebf9-116">Windows-Version</span><span class="sxs-lookup"><span data-stu-id="0ebf9-116">Windows version</span></span>|<span data-ttu-id="0ebf9-117">Subsystemversion</span><span class="sxs-lookup"><span data-stu-id="0ebf9-117">Subsystem version</span></span>|
|---------------------|-----------------------|
|<span data-ttu-id="0ebf9-118">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="0ebf9-118">Windows 2000</span></span>|<span data-ttu-id="0ebf9-119">5.00</span><span class="sxs-lookup"><span data-stu-id="0ebf9-119">5.00</span></span>|
|<span data-ttu-id="0ebf9-120">Windows XP</span><span class="sxs-lookup"><span data-stu-id="0ebf9-120">Windows XP</span></span>|<span data-ttu-id="0ebf9-121">5.01</span><span class="sxs-lookup"><span data-stu-id="0ebf9-121">5.01</span></span>|
|<span data-ttu-id="0ebf9-122">Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="0ebf9-122">Windows Server 2003</span></span>|<span data-ttu-id="0ebf9-123">5.02</span><span class="sxs-lookup"><span data-stu-id="0ebf9-123">5.02</span></span>|
|<span data-ttu-id="0ebf9-124">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="0ebf9-124">Windows Vista</span></span>|<span data-ttu-id="0ebf9-125">6.00</span><span class="sxs-lookup"><span data-stu-id="0ebf9-125">6.00</span></span>|
|<span data-ttu-id="0ebf9-126">Windows 7</span><span class="sxs-lookup"><span data-stu-id="0ebf9-126">Windows 7</span></span>|<span data-ttu-id="0ebf9-127">6.01</span><span class="sxs-lookup"><span data-stu-id="0ebf9-127">6.01</span></span>|
|<span data-ttu-id="0ebf9-128">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="0ebf9-128">Windows Server 2008</span></span>|<span data-ttu-id="0ebf9-129">6.01</span><span class="sxs-lookup"><span data-stu-id="0ebf9-129">6.01</span></span>|
|[!INCLUDE[win8](~/includes/win8-md.md)]|<span data-ttu-id="0ebf9-130">6.02</span><span class="sxs-lookup"><span data-stu-id="0ebf9-130">6.02</span></span>|

## <a name="default-values"></a><span data-ttu-id="0ebf9-131">Standardwerte</span><span class="sxs-lookup"><span data-stu-id="0ebf9-131">Default values</span></span>

<span data-ttu-id="0ebf9-132">Der Standardwert der Compileroption **-subsystemversion** hängt von den Bedingungen in der folgenden Liste ab:</span><span class="sxs-lookup"><span data-stu-id="0ebf9-132">The default value of the **-subsystemversion** compiler option depends on the conditions in the following list:</span></span>

- <span data-ttu-id="0ebf9-133">Der Standardwert ist 6,02, wenn jede Compileroption in der folgenden Liste festgelegt ist:</span><span class="sxs-lookup"><span data-stu-id="0ebf9-133">The default value is 6.02 if any compiler option in the following list is set:</span></span>

  - [<span data-ttu-id="0ebf9-134">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="0ebf9-134">-target:appcontainerexe</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)

  - [<span data-ttu-id="0ebf9-135">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="0ebf9-135">-target:winmdobj</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)

  - [<span data-ttu-id="0ebf9-136">-platform:arm</span><span class="sxs-lookup"><span data-stu-id="0ebf9-136">-platform:arm</span></span>](../../../visual-basic/reference/command-line-compiler/platform.md)

- <span data-ttu-id="0ebf9-137">Beim Verwenden von MSBuild ist der Standardwert 6,00, indem Sie [!INCLUDE[net_v45](~/includes/net-v45-md.md)] als Ziel setzen, und Sie haben keine der Compileroptionen festgelegt, die zuvor in der Liste angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-137">The default value is 6.00 if you're using MSBuild, you're targeting [!INCLUDE[net_v45](~/includes/net-v45-md.md)], and you haven't set any of the compiler options that were specified earlier in this list.</span></span>

- <span data-ttu-id="0ebf9-138">Der Standardwert ist 4,00, wenn keine der vorherigen Bedingungen TRUE ist.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-138">The default value is 4.00 if none of the previous conditions is true.</span></span>

## <a name="setting-this-option"></a><span data-ttu-id="0ebf9-139">Festlegen dieser Option</span><span class="sxs-lookup"><span data-stu-id="0ebf9-139">Setting this option</span></span>

<span data-ttu-id="0ebf9-140">Festlegen der **- Subsystemversion** -Compileroption in Visual Studio müssen Sie die VBPROJ-Datei zu öffnen und geben Sie einen Wert für die `SubsystemVersion` Eigenschaft in der MSBuild-XML.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-140">To set the **-subsystemversion** compiler option in Visual Studio, you must open the .vbproj file and specify a value for the `SubsystemVersion` property in the MSBuild XML.</span></span> <span data-ttu-id="0ebf9-141">Diese Option kann nicht in der Visual Studio-IDE festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0ebf9-141">You can't set this option in the Visual Studio IDE.</span></span> <span data-ttu-id="0ebf9-142">Weitere Informationen finden Sie unter „Standardwerte“ weiter oben in diesem Thema oder unter [Häufige MSBuild-Projekteigenschaften](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="0ebf9-142">For more information, see "Default values" earlier in this topic or [Common MSBuild Project Properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="see-also"></a><span data-ttu-id="0ebf9-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0ebf9-143">See also</span></span>

- [<span data-ttu-id="0ebf9-144">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0ebf9-144">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)

- [<span data-ttu-id="0ebf9-145">MSBuild-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0ebf9-145">MSBuild Properties</span></span>](/visualstudio/msbuild/msbuild-properties)
