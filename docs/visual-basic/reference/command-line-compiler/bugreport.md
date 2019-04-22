---
title: -bugreport
ms.date: 03/08/2018
helpviewer_keywords:
- -bugreport compiler option [Visual Basic]
- bugreport compiler option [Visual Basic]
- /bugreport compiler option [Visual Basic]
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
ms.openlocfilehash: e7b4ebc58b6fe9850b92ef945cb0d715e4369efe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820910"
---
# <a name="-bugreport"></a><span data-ttu-id="572ae-102">-bugreport</span><span class="sxs-lookup"><span data-stu-id="572ae-102">-bugreport</span></span>
<span data-ttu-id="572ae-103">Erstellt eine Datei, die Sie verwenden können, wenn Sie einen Fehlerbericht einzureichen.</span><span class="sxs-lookup"><span data-stu-id="572ae-103">Creates a file that you can use when you file a bug report.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="572ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="572ae-104">Syntax</span></span>  
  
```  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="572ae-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="572ae-105">Arguments</span></span>  
  
|<span data-ttu-id="572ae-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="572ae-106">Term</span></span>|<span data-ttu-id="572ae-107">Definition</span><span class="sxs-lookup"><span data-stu-id="572ae-107">Definition</span></span>|  
|---|---|  
|`file`|<span data-ttu-id="572ae-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="572ae-108">Required.</span></span> <span data-ttu-id="572ae-109">Der Name der Datei, die den Problembericht enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="572ae-109">The name of the file that will contain your bug report.</span></span> <span data-ttu-id="572ae-110">Schließen Sie den Dateinamen in Anführungszeichen (""), wenn der Name ein Leerzeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="572ae-110">Enclose the file name in quotation marks (" ") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="572ae-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="572ae-111">Remarks</span></span>  
 <span data-ttu-id="572ae-112">Die folgende Informationen wird hinzugefügt, um `file`:</span><span class="sxs-lookup"><span data-stu-id="572ae-112">The following information is added to `file`:</span></span>  
  
-   <span data-ttu-id="572ae-113">Eine Kopie aller Quellcodedateien in der Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="572ae-113">A copy of all source-code files in the compilation.</span></span>  
  
-   <span data-ttu-id="572ae-114">Eine Liste der in der Kompilierung verwendeten Compileroptionen.</span><span class="sxs-lookup"><span data-stu-id="572ae-114">A list of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="572ae-115">Versionsinformationen zu Compiler, common Language Runtime und Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="572ae-115">Version information about your compiler, common language runtime, and operating system.</span></span>  
  
-   <span data-ttu-id="572ae-116">Compilerausgabe, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="572ae-116">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="572ae-117">Eine Beschreibung des Problems, für die Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="572ae-117">A description of the problem, for which you are prompted.</span></span>  
  
-   <span data-ttu-id="572ae-118">Eine Beschreibung Ihres das Problem Vorschlags muss behoben werden, für die Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="572ae-118">A description of how you think the problem should be fixed, for which you are prompted.</span></span>  
  
 <span data-ttu-id="572ae-119">Da eine Kopie aller Quellcodedateien in enthalten ist `file`, möglicherweise möchten Sie den (vermuteten) Codefehler im kürzestmöglichen Programm zu reproduzieren.</span><span class="sxs-lookup"><span data-stu-id="572ae-119">Because a copy of all source-code files is included in `file`, you may want to reproduce the (suspected) code defect in the shortest possible program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="572ae-120">Die `-bugreport` Option erzeugt eine Datei, die möglicherweise vertrauliche Informationen enthält.</span><span class="sxs-lookup"><span data-stu-id="572ae-120">The `-bugreport` option produces a file that contains potentially sensitive information.</span></span> <span data-ttu-id="572ae-121">Dies schließt die aktuelle Uhrzeit, die Version des Compilers, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Version, Betriebssystemversion, Benutzername, die Befehlszeilenargumente, klicken Sie mit der der Compiler ausgeführt wurde, werden alle Quellcode, und die binäre Form eines auf die Assembly verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="572ae-121">This includes current time, compiler version, [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] version, OS version, user name, the command-line arguments with which the compiler was run, all source code, and the binary form of any referenced assembly.</span></span> <span data-ttu-id="572ae-122">Diese Option kann zugegriffen werden, durch die Angabe von Befehlszeilenoptionen in der Datei "Web.config" für eine serverseitige Kompilierung einer [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] Anwendung.</span><span class="sxs-lookup"><span data-stu-id="572ae-122">This option can be accessed by specifying command-line options in the Web.config file for a server-side compilation of an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] application.</span></span> <span data-ttu-id="572ae-123">Um dies zu vermeiden, ändern Sie die Datei "Machine.config", um Benutzer an der Kompilierung auf dem Server verweigern.</span><span class="sxs-lookup"><span data-stu-id="572ae-123">To prevent this, modify the Machine.config file to disallow users from compiling on the server.</span></span>  
  
 <span data-ttu-id="572ae-124">Wenn diese Option verwendet wird, mit `-errorreport:prompt`, `-errorreport:queue`, oder `-errorreport:send`, und Ihre Anwendung findet einen interner Compilerfehler, die Informationen in `file` an die Microsoft Corporation gesendet.</span><span class="sxs-lookup"><span data-stu-id="572ae-124">If this option is used with `-errorreport:prompt`, `-errorreport:queue`, or `-errorreport:send`, and your application encounters an internal compiler error, the information in `file` is sent to Microsoft Corporation.</span></span> <span data-ttu-id="572ae-125">Diese Informationen helfen Microsoft-Techniker, die die Ursache des Fehlers zu identifizieren und die nächste Version von Visual Basic zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="572ae-125">That information will help Microsoft engineers identify the cause of the error and may help improve the next release of Visual Basic.</span></span> <span data-ttu-id="572ae-126">Standardmäßig ist keine Informationen an Microsoft gesendet.</span><span class="sxs-lookup"><span data-stu-id="572ae-126">By default, no information is sent to Microsoft.</span></span> <span data-ttu-id="572ae-127">Allerdings beim Kompilieren einer Anwendungs mithilfe von `-errorreport:queue`, die standardmäßig aktiviert ist, sammelt die Anwendung ihre Fehlerberichte.</span><span class="sxs-lookup"><span data-stu-id="572ae-127">However, when you compile an application by using `-errorreport:queue`, which is enabled by default, the application collects its error reports.</span></span> <span data-ttu-id="572ae-128">Anschließend bei der Administrator des Computers, zeigt das Berichterstattungssystem Fehler ein Popup-Fenster, die es den Administrator ermöglicht, die an Microsoft, die Fehlerberichte weitergeleitet, die seit der Anmeldung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="572ae-128">Then, when the computer's administrator logs in, the error reporting system displays a pop-up window that enables the administrator to forward to Microsoft any error reports that occurred since the logon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="572ae-129">Die `/bugreport` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="572ae-129">The `/bugreport` option is not available from within the Visual Studio development environment; it is available only when you compile from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="572ae-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="572ae-130">Example</span></span>  
 <span data-ttu-id="572ae-131">Im folgende Beispiel wird kompiliert `T2.vb` und setzt alle für die Fehlerberichterstattung Informationen in der Datei `Problem.txt`.</span><span class="sxs-lookup"><span data-stu-id="572ae-131">The following example compiles `T2.vb` and puts all bug-reporting information in the file `Problem.txt`.</span></span>  
  
```  
vbc -bugreport:problem.txt t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="572ae-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="572ae-132">See also</span></span>

- [<span data-ttu-id="572ae-133">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="572ae-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="572ae-134">-debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="572ae-134">-debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)
- [<span data-ttu-id="572ae-135">-errorreport</span><span class="sxs-lookup"><span data-stu-id="572ae-135">-errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)
- [<span data-ttu-id="572ae-136">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="572ae-136">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- <span data-ttu-id="572ae-137">[TrustLevel-Element für SecurityPolicy ((ASP.NET Einstellungsschema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="572ae-137">[trustLevel Element for securityPolicy (ASP.NET Settings Schema)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/as399f0x(v=vs.100))</span></span>
