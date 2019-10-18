---
ms.openlocfilehash: 2872c5909b382e01fdd231019a12970caa3b77d2
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72526748"
---
## <a name="installation-instructions---visual-studio-installer"></a><span data-ttu-id="7a009-101">Installationsanweisungen: Visual Studio-Installer</span><span class="sxs-lookup"><span data-stu-id="7a009-101">Installation instructions - Visual Studio Installer</span></span>

<span data-ttu-id="7a009-102">Es gibt zwei verschiedene Möglichkeiten, das **.NET Compiler Platform SDK** im **Visual Studio-Installer** zu finden:</span><span class="sxs-lookup"><span data-stu-id="7a009-102">There are two different ways to find the **.NET Compiler Platform SDK** in the **Visual Studio Installer**:</span></span>

### <a name="install-using-the-visual-studio-installer---workloads-view"></a><span data-ttu-id="7a009-103">Installation mithilfe des Visual Studio-Installers: Workloads im Überblick</span><span class="sxs-lookup"><span data-stu-id="7a009-103">Install using the Visual Studio Installer - Workloads view</span></span>

<span data-ttu-id="7a009-104">Das .NET Compiler Platform SDK wird nicht automatisch als Teil der Workload „Visual Studio-Extensionentwicklung“ ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="7a009-104">The .NET Compiler Platform SDK is not automatically selected as part of the Visual Studio extension development workload.</span></span> <span data-ttu-id="7a009-105">Sie müssen sie als optionale Komponente auswählen.</span><span class="sxs-lookup"><span data-stu-id="7a009-105">You must select it as an optional component.</span></span>

1. <span data-ttu-id="7a009-106">Führen Sie den **Visual Studio-Installer** aus.</span><span class="sxs-lookup"><span data-stu-id="7a009-106">Run **Visual Studio Installer**</span></span>
1. <span data-ttu-id="7a009-107">Klicken Sie auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="7a009-107">Select **Modify**</span></span>
1. <span data-ttu-id="7a009-108">Aktivieren Sie die Workload **Visual Studio-Extensionentwicklung**.</span><span class="sxs-lookup"><span data-stu-id="7a009-108">Check the **Visual Studio extension development** workload.</span></span>
1. <span data-ttu-id="7a009-109">Öffnen Sie den Knoten **Visual Studio-Extensionentwicklung** in der Zusammenfassungsstruktur.</span><span class="sxs-lookup"><span data-stu-id="7a009-109">Open the **Visual Studio extension development** node in the summary tree.</span></span>
1. <span data-ttu-id="7a009-110">Aktivieren Sie das Kontrollkästchen für das **.NET Compiler Platform SDK**.</span><span class="sxs-lookup"><span data-stu-id="7a009-110">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="7a009-111">Sie finden es an letzter Stelle unter den optionalen Komponenten.</span><span class="sxs-lookup"><span data-stu-id="7a009-111">You'll find it last under the optional components.</span></span>

<span data-ttu-id="7a009-112">Optional können Sie einstellen, dass der **DGML-Editor** Diagramme in der Schnellansicht anzeigt:</span><span class="sxs-lookup"><span data-stu-id="7a009-112">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="7a009-113">Öffnen Sie den Knoten **Einzelne Komponenten** in der Zusammenfassungsstruktur.</span><span class="sxs-lookup"><span data-stu-id="7a009-113">Open the **Individual components** node in the summary tree.</span></span>
1. <span data-ttu-id="7a009-114">Aktivieren Sie das Kontrollkästchen für den **DGML-Editor**.</span><span class="sxs-lookup"><span data-stu-id="7a009-114">Check the box for **DGML editor**</span></span>

### <a name="install-using-the-visual-studio-installer---individual-components-tab"></a><span data-ttu-id="7a009-115">Installation mithilfe des Visual Studio-Installers: Registerkarte „Einzelne Komponenten“</span><span class="sxs-lookup"><span data-stu-id="7a009-115">Install using the Visual Studio Installer - Individual components tab</span></span>

1. <span data-ttu-id="7a009-116">Führen Sie den **Visual Studio-Installer** aus.</span><span class="sxs-lookup"><span data-stu-id="7a009-116">Run **Visual Studio Installer**</span></span>
1. <span data-ttu-id="7a009-117">Klicken Sie auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="7a009-117">Select **Modify**</span></span>
1. <span data-ttu-id="7a009-118">Klicken Sie auf die Registerkarte **Einzelne Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="7a009-118">Select the **Individual components** tab</span></span>
1. <span data-ttu-id="7a009-119">Aktivieren Sie das Kontrollkästchen für das **.NET Compiler Platform SDK**.</span><span class="sxs-lookup"><span data-stu-id="7a009-119">Check the box for **.NET Compiler Platform SDK**.</span></span> <span data-ttu-id="7a009-120">Sie finden es an oberster Stelle im Abschnitt **Compiler, Buildtools und Laufzeiten**.</span><span class="sxs-lookup"><span data-stu-id="7a009-120">You'll find it at the top under the **Compilers, build tools, and runtimes** section.</span></span>

<span data-ttu-id="7a009-121">Optional können Sie einstellen, dass der **DGML-Editor** Diagramme in der Schnellansicht anzeigt:</span><span class="sxs-lookup"><span data-stu-id="7a009-121">Optionally, you'll also want the **DGML editor** to display graphs in the visualizer:</span></span>

1. <span data-ttu-id="7a009-122">Aktivieren Sie das Kontrollkästchen für den **DGML-Editor**.</span><span class="sxs-lookup"><span data-stu-id="7a009-122">Check the box for **DGML editor**.</span></span> <span data-ttu-id="7a009-123">Sie finden es im Abschnitt **Codetools**.</span><span class="sxs-lookup"><span data-stu-id="7a009-123">You'll find it under the **Code tools** section.</span></span>
