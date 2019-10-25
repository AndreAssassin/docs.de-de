---
title: Verwaltete Debugger – .NET Core
description: Eine Übersicht über die verwalteten Debugger in Visual Studio und Visual Studio Code.
author: sdmaclea
ms.author: stmaclea
ms.date: 08/05/2019
ms.openlocfilehash: 3741011d22ab6c4240b7f88a9ab790ea61ecd0d2
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/12/2019
ms.locfileid: "72303647"
---
# <a name="net-core-managed-debuggers"></a><span data-ttu-id="da1fc-103">Verwaltete Debugger in .NET Core</span><span class="sxs-lookup"><span data-stu-id="da1fc-103">.NET Core managed debuggers</span></span>

<span data-ttu-id="da1fc-104">Mithilfe von Debuggern können Programme angehalten oder Schritt für Schritt ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="da1fc-104">Debuggers allow programs to be paused or executed step-by-step.</span></span> <span data-ttu-id="da1fc-105">Nach dem Anhalten kann der aktuelle Status des Prozesses angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="da1fc-105">When paused, the current state of the process can be viewed.</span></span> <span data-ttu-id="da1fc-106">Indem Sie wesentliche Abschnitte schrittweise durchlaufen, erhalten Sie einen Einblick in Ihren Code und die Gründe für das erzeugte Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="da1fc-106">By stepping through key sections, you gain understanding of your code and why it produces the result that it does.</span></span>

<span data-ttu-id="da1fc-107">Microsoft stellt in **Visual Studio** und **Visual Studio Code** Debugger für verwalteten Code bereit.</span><span class="sxs-lookup"><span data-stu-id="da1fc-107">Microsoft provides debuggers for managed code in **Visual Studio** and **Visual Studio Code**.</span></span>

## <a name="visual-studio-managed-debugger"></a><span data-ttu-id="da1fc-108">Verwalteter Debugger von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="da1fc-108">Visual Studio managed debugger</span></span>

<span data-ttu-id="da1fc-109">**Visual Studio**  ist eine integrierte Entwicklungsumgebung, die den umfassendsten Debugger bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="da1fc-109">**Visual Studio** is an integrated development environment with the most comprehensive debugger available.</span></span> <span data-ttu-id="da1fc-110">Visual Studio ist eine hervorragende Wahl für Entwickler, die unter Windows arbeiten.</span><span class="sxs-lookup"><span data-stu-id="da1fc-110">Visual Studio is an excellent choice for developers working on Windows.</span></span>

- [<span data-ttu-id="da1fc-111">Tutorial: Debuggen einer .NET Core-Anwendung unter Windows mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="da1fc-111">Tutorial - Debugging a .NET Core application on Windows with Visual Studio</span></span>](../tutorials/debugging-with-visual-studio.md)

<span data-ttu-id="da1fc-112">Obwohl Visual Studio eine Windows-Anwendung ist, können hiermit auch Linux- und macOS-Apps remote debuggt werden.</span><span class="sxs-lookup"><span data-stu-id="da1fc-112">While Visual Studio is a Windows application, it can still be used to debug Linux and macOS apps remotely.</span></span>

- [<span data-ttu-id="da1fc-113">Debuggen einer .NET Core-Anwendung unter Linux/OS X mit Visual Studio</span><span class="sxs-lookup"><span data-stu-id="da1fc-113">Debugging a .NET Core application on Linux/OSX with Visual Studio</span></span>](https://github.com/Microsoft/MIEngine/wiki/Offroad-Debugging-of-.NET-Core-on-Linux---OSX-from-Visual-Studio)

 <span data-ttu-id="da1fc-114">Für das Debuggen von ASP.NET Core-Apps gelten leicht abweichende Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="da1fc-114">Debugging ASP.NET Core apps require slightly different instructions.</span></span>

- [<span data-ttu-id="da1fc-115">Debuggen von ASP.NET-Apps in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="da1fc-115">Debug ASP.NET Core apps in Visual Studio</span></span>](/visualstudio/debugger/how-to-enable-debugging-for-aspnet-applications#debug-aspnet-core-apps)

## <a name="visual-studio-code-managed-debugger"></a><span data-ttu-id="da1fc-116">Verwalteter Debugger von Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="da1fc-116">Visual Studio Code managed debugger</span></span>

<span data-ttu-id="da1fc-117">**Visual Studio Code** ist ein einfacher Code-Editor für alle Plattformen.</span><span class="sxs-lookup"><span data-stu-id="da1fc-117">**Visual Studio Code** is a lightweight cross-platform code editor.</span></span> <span data-ttu-id="da1fc-118">Er nutzt die gleiche Implementierung des .NET Core-Debuggers wie Visual Studio, jedoch mit einer vereinfachten Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="da1fc-118">It uses the same .NET Core debugger implementation as Visual Studio, but with a simplified user interface.</span></span>

- [<span data-ttu-id="da1fc-119">Tutorial: Debuggen einer .NET Core-Anwendung mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="da1fc-119">Tutorial - Debugging a .NET Core application with Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md#debug)
- [<span data-ttu-id="da1fc-120">Debuggen in Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="da1fc-120">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/docs/editor/debugging)
