---
title: "In die Ausgabedatei '<filename>' konnte nicht geschrieben werden: <error>."
ms.date: 07/20/2015
f1_keywords:
- vbc31019
- bc31019
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
ms.openlocfilehash: e0a00c4f57e45d65ff46fb9487a603a67d5a9e5c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64620600"
---
# <a name="unable-to-write-to-output-file-filename-error"></a><span data-ttu-id="b0b7b-102">Beim Schreiben in die Ausgabedatei kann nicht '\<Dateiname >': \<Fehler ></span><span class="sxs-lookup"><span data-stu-id="b0b7b-102">Unable to write to output file '\<filename>': \<error></span></span>
<span data-ttu-id="b0b7b-103">Beim Erstellen der Datei ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-103">There was a problem creating the file.</span></span>  
  
 <span data-ttu-id="b0b7b-104">Eine Ausgabedatei kann nicht zum Schreiben geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-104">An output file cannot be opened for writing.</span></span> <span data-ttu-id="b0b7b-105">Die Datei (oder der Ordner, der die Datei enthält) kann für die Exklusivnutzung durch einen anderen Prozess geöffnet sein, oder sie ist schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-105">The file (or the folder containing the file) may be opened for exclusive use by another process, or it may have its read-only attribute set.</span></span>  
  
 <span data-ttu-id="b0b7b-106">Häufige Situationen, in denen eine Datei exklusiv genutzt wird, sind:</span><span class="sxs-lookup"><span data-stu-id="b0b7b-106">Common situations where a file is opened exclusively are:</span></span>  
  
- <span data-ttu-id="b0b7b-107">Die Anwendung wird bereits ausgeführt und nutzt die Dateien.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-107">The application is already running and using its files.</span></span> <span data-ttu-id="b0b7b-108">Stellen Sie zum Lösen dieses Problems sicher, dass die Anwendung nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-108">To solve this problem, make sure that the application is not running.</span></span>  
  
- <span data-ttu-id="b0b7b-109">Die Datei wurde in einer anderen Anwendung geöffnet.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-109">Another application has opened the file.</span></span> <span data-ttu-id="b0b7b-110">Stellen Sie zum Lösen dieses Problems sicher, dass keine andere Anwendung auf die Dateien zugreift.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-110">To solve this problem, make sure that no other application is accessing the files.</span></span> <span data-ttu-id="b0b7b-111">Es ist nicht immer ersichtlich, welche Anwendung auf Ihre Dateien zugreift; ein Neustart Ihres Computer kann in diesem Fall der einfachste Weg sein, um die Anwendung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-111">It is not always obvious which application is accessing your files; in that case, restarting the computer might be the easiest way to terminate the application.</span></span>  
  
 <span data-ttu-id="b0b7b-112">Es reicht aus, dass eine Projektausgabedatei schreibgeschützt ist, um diese Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-112">If even one of the project output files is marked as read-only, this exception will be thrown.</span></span>  
  
 <span data-ttu-id="b0b7b-113">**Fehler-ID:** BC31019</span><span class="sxs-lookup"><span data-stu-id="b0b7b-113">**Error ID:** BC31019</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b0b7b-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b0b7b-114">To correct this error</span></span>  
  
1. <span data-ttu-id="b0b7b-115">Kompilieren Sie das Programm erneut, um festzustellen, ob der Fehler erneut auftritt.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-115">Compile the program again to see if the error recurs.</span></span>  
  
2. <span data-ttu-id="b0b7b-116">Wenn der Fehler weiterhin auftritt, speichern Sie Ihre Arbeit, und starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-116">If the error continues, save your work and restart Visual Studio.</span></span>  
  
3. <span data-ttu-id="b0b7b-117">Wenn der Fehler weiterhin besteht, starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-117">If the error continues, restart the computer.</span></span>  
  
4. <span data-ttu-id="b0b7b-118">Wenn der Fehler erneut auftritt, installieren Sie Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-118">If the error recurs, reinstall Visual Basic.</span></span>  
  
5. <span data-ttu-id="b0b7b-119">Wenn der Fehler auch nach der erneuten Installation auftritt, informieren Sie den Produktsupport von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-119">If the error persists after reinstallation, notify Microsoft Product Support Services.</span></span>  
  
### <a name="to-check-file-attributes-in-file-explorer"></a><span data-ttu-id="b0b7b-120">So prüfen Sie Dateiattribute im Datei-Explorer</span><span class="sxs-lookup"><span data-stu-id="b0b7b-120">To check file attributes in File Explorer</span></span>  
  
1. <span data-ttu-id="b0b7b-121">Öffnen Sie den gewünschten Ordner.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-121">Open the folder you are interested in.</span></span>  
  
2. <span data-ttu-id="b0b7b-122">Klicken Sie auf die **Ansichten** Symbol, und wählen Sie **Details**.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-122">Click the **Views** icon and choose **Details**.</span></span>  
  
3. <span data-ttu-id="b0b7b-123">Mit der rechten Maustaste in der Kopfzeile der Spalte, und wählen **Attribute** aus der Dropdown-Liste.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-123">Right-click the column header, and choose **Attributes** from the drop-down list.</span></span>  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a><span data-ttu-id="b0b7b-124">So ändern Sie die Attribute einer Datei oder eines Ordners</span><span class="sxs-lookup"><span data-stu-id="b0b7b-124">To change the attributes of a file or folder</span></span>  
  
1. <span data-ttu-id="b0b7b-125">In **Datei-Explorer**mit der rechten Maustaste auf die Datei oder den Ordner, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-125">In **File Explorer**, right-click the file or folder and choose **Properties**.</span></span>  
  
2. <span data-ttu-id="b0b7b-126">In der **Attribute** Teil der **allgemeine** Registerkarte die **schreibgeschützte** Feld.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-126">In the **Attributes** section of the **General** tab, clear the **Read-only** box.</span></span>  
  
3. <span data-ttu-id="b0b7b-127">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0b7b-127">Press **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0b7b-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0b7b-128">See also</span></span>

- [<span data-ttu-id="b0b7b-129">Sprechen Sie mit uns</span><span class="sxs-lookup"><span data-stu-id="b0b7b-129">Talk to Us</span></span>](/visualstudio/ide/talk-to-us)
