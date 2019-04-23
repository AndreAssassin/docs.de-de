---
title: Clrver.exe (CLR-Versionstool)
ms.date: 03/30/2017
helpviewer_keywords:
- Clrver.exe
- CLR Version tool
ms.assetid: cbc2ee86-bdc8-4a65-a8f1-ba23bce3a699
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 28ac90eadcc7a13fe946aabf17973ebc602c9d4a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084595"
---
# <a name="clrverexe-clr-version-tool"></a><span data-ttu-id="b54a0-102">Clrver.exe (CLR-Versionstool)</span><span class="sxs-lookup"><span data-stu-id="b54a0-102">Clrver.exe (CLR Version Tool)</span></span>
<span data-ttu-id="b54a0-103">Das CLR-Versionstool (Clrver.exe) führt alle installierten Versionen der Common Language Runtime (CLR) auf dem Computer auf.</span><span class="sxs-lookup"><span data-stu-id="b54a0-103">The CLR Version tool (Clrver.exe) reports all the installed versions of the common language runtime (CLR) on the computer.</span></span>  
  
 <span data-ttu-id="b54a0-104">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="b54a0-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="b54a0-105">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b54a0-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="b54a0-106">Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="b54a0-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="b54a0-107">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="b54a0-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b54a0-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="b54a0-108">Syntax</span></span>  
  
```  
clrver [option]  
```  
  
## <a name="options"></a><span data-ttu-id="b54a0-109">Optionen</span><span class="sxs-lookup"><span data-stu-id="b54a0-109">Options</span></span>  
  
|<span data-ttu-id="b54a0-110">Option</span><span class="sxs-lookup"><span data-stu-id="b54a0-110">Option</span></span>|<span data-ttu-id="b54a0-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b54a0-111">Description</span></span>|  
|------------|-----------------|  
|`-all`|<span data-ttu-id="b54a0-112">Zeigt alle Prozesse auf dem Computer an, die die CLR verwenden.</span><span class="sxs-lookup"><span data-stu-id="b54a0-112">Displays all processes on the computer that are using the CLR.</span></span>|  
|*<span data-ttu-id="b54a0-113">pid</span><span class="sxs-lookup"><span data-stu-id="b54a0-113">pid</span></span>*|<span data-ttu-id="b54a0-114">Zeigt die Versionen der CLR an, die von dem Prozess verwendet werden, der über angegebene Prozess-ID (PID) aufweist.</span><span class="sxs-lookup"><span data-stu-id="b54a0-114">Displays the version(s) of the CLR used by the process that has the specified process ID (PID).</span></span>|  
|`-?`|<span data-ttu-id="b54a0-115">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="b54a0-115">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b54a0-116">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="b54a0-116">Remarks</span></span>  
 <span data-ttu-id="b54a0-117">Wenn Sie "Clrver.exe" ohne Optionen aufrufen, werden alle installierten CLR-Versionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b54a0-117">If you call Clrver.exe with no options, it displays all installed CLR versions.</span></span> <span data-ttu-id="b54a0-118">Wenn Sie eine PID für einen anderen Benutzer angeben, müssen Sie über Administratorberechtigungen verfügen, um die Versionsinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b54a0-118">If you specify a PID for another user, you must have administrative permissions to obtain the version information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b54a0-119">Unter Windows Vista (und höher) werden die Berechtigungen eines Benutzers von der Benutzerkontensteuerung (User Account Control, UAC) bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b54a0-119">In Windows Vista and later, User Account Control (UAC) determines the privileges of a user.</span></span> <span data-ttu-id="b54a0-120">Als Mitglied der integrierten Administratorgruppe sind Ihnen zwei Zugriffstoken für die Laufzeit zugewiesen: ein Standardbenutzertoken und ein Administratorzugriffstoken.</span><span class="sxs-lookup"><span data-stu-id="b54a0-120">If you are a member of the Built-in Administrators group, you are assigned two run-time access tokens: a standard user access token and an administrator access token.</span></span> <span data-ttu-id="b54a0-121">Standardmäßig verwenden Sie die Standardbenutzerrolle.</span><span class="sxs-lookup"><span data-stu-id="b54a0-121">By default, you are in the standard user role.</span></span> <span data-ttu-id="b54a0-122">Um Code ausführen zu können, der Administratorberechtigungen erfordert, müssen Sie zuerst Ihre Berechtigungen von Standardbenutzer auf Administrator erhöhen.</span><span class="sxs-lookup"><span data-stu-id="b54a0-122">To execute code that requires administrative permission, you must first elevate your privileges from standard user to administrator.</span></span> <span data-ttu-id="b54a0-123">Dazu starten Sie die Eingabeaufforderung, indem Sie mit der rechten Maustaste auf das Symbol für die Eingabeaufforderung klicken und angeben, dass Sie die Anwendung als Administrator ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="b54a0-123">You can do this when you start the command prompt by right-clicking the command prompt icon and indicating that you want to run as an administrator.</span></span>  
  
 <span data-ttu-id="b54a0-124">Der Versuch, die CLR-Version für SYSTEM-, LOCAL SERVICE- und NETWORK SERVICE-Prozesse zu bestimmen, führt zu einer Meldung, die besagt, dass die PID nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b54a0-124">Attempting to determine the CLR version for SYSTEM, LOCAL SERVICE, and NETWORK SERVICE processes results in a message indicating that the PID doesn't exist.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="b54a0-125">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b54a0-125">Examples</span></span>  
 <span data-ttu-id="b54a0-126">Mit dem folgenden Befehl werden alle Versionen der CLR angezeigt, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="b54a0-126">The following command displays all the versions of the CLR installed on the computer.</span></span>  
  
 `clrver`  
  
 <span data-ttu-id="b54a0-127">Mit dem folgenden Befehl wird die Version der CLR angezeigt, die von Prozess 128 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b54a0-127">The following command displays the version of the CLR used by process 128.</span></span>  
  
 `clrver 128`  
  
 <span data-ttu-id="b54a0-128">Der folgende Befehl zeigt alle verwalteten Prozesse und die Version der CLR, die sie verwenden, an.</span><span class="sxs-lookup"><span data-stu-id="b54a0-128">The following command displays all the managed processes and the version of the CLR they are using.</span></span>  
  
 `Clrver -all`  
  
## <a name="see-also"></a><span data-ttu-id="b54a0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b54a0-129">See also</span></span>

- [<span data-ttu-id="b54a0-130">Tools</span><span class="sxs-lookup"><span data-stu-id="b54a0-130">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="b54a0-131">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="b54a0-131">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
