---
title: End-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.End
- End
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- End keyword [Visual Basic], End statements
- programs [Visual Basic], quitting
- code, exiting
- program termination
- End statement [Visual Basic]
- execution [Visual Basic], stopping
ms.assetid: 0e64467c-0f34-4aab-9ddd-43f8b9d55d90
ms.openlocfilehash: 4fc4fd36fb6b057195e9d8a79eb0a5b3ac9ff95c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832020"
---
# <a name="end-statement"></a><span data-ttu-id="243a4-102">End Statement</span><span class="sxs-lookup"><span data-stu-id="243a4-102">End Statement</span></span>
<span data-ttu-id="243a4-103">Beendet die Ausführung sofort.</span><span class="sxs-lookup"><span data-stu-id="243a4-103">Terminates execution immediately.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="243a4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="243a4-104">Syntax</span></span>  
  
```  
End  
```  
  
## <a name="remarks"></a><span data-ttu-id="243a4-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="243a4-105">Remarks</span></span>  
 <span data-ttu-id="243a4-106">Sie können Platzieren der `End` Anweisung an einer beliebigen Stelle in einer Prozedur zu erzwingen, dass die gesamte Anwendung nicht mehr ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="243a4-106">You can place the `End` statement anywhere in a procedure to force the entire application to stop running.</span></span> <span data-ttu-id="243a4-107">`End` Schließt alle geöffneten mit einer `Open` Anweisung und löscht alle für die Anwendung Variablen.</span><span class="sxs-lookup"><span data-stu-id="243a4-107">`End` closes any files opened with an `Open` statement and clears all the application's variables.</span></span> <span data-ttu-id="243a4-108">Die Anwendung geschlossen wird, sobald es sind keine anderen Programme, die Verweise auf die Objekte enthält und kein Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="243a4-108">The application closes as soon as there are no other programs holding references to its objects and none of its code is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="243a4-109">Die `End` Anweisung abrupt beendet die Ausführung von Code und wird nicht aufgerufen werden. die `Dispose` oder `Finalize` Methode oder eine beliebige andere Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="243a4-109">The `End` statement stops code execution abruptly, and does not invoke the `Dispose` or `Finalize` method, or any other Visual Basic code.</span></span> <span data-ttu-id="243a4-110">Objektverweise, die von anderen Programmen werden ungültig.</span><span class="sxs-lookup"><span data-stu-id="243a4-110">Object references held by other programs are invalidated.</span></span> <span data-ttu-id="243a4-111">Wenn ein `End` -Anweisung innerhalb einer `Try` oder `Catch` Block Steuerelement übergibt die nicht mit der entsprechenden `Finally` Block.</span><span class="sxs-lookup"><span data-stu-id="243a4-111">If an `End` statement is encountered within a `Try` or `Catch` block, control does not pass to the corresponding `Finally` block.</span></span>  
  
 <span data-ttu-id="243a4-112">Die `Stop` Anweisung hält die Ausführung, aber im Gegensatz zu `End`, keine Dateien schließen oder löschen Sie alle Variablen, es sei denn, es in eine kompilierte ausführbare Datei (.exe)-Datei gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="243a4-112">The `Stop` statement suspends execution, but unlike `End`, it does not close any files or clear any variables, unless it is encountered in a compiled executable (.exe) file.</span></span>  
  
 <span data-ttu-id="243a4-113">Da `End` beendet die Anwendung ohne die Teilnahme an Ressourcen, die geöffnet sein können, sollten Sie versuchen, die ordnungsgemäß schließen vor der Verwendung.</span><span class="sxs-lookup"><span data-stu-id="243a4-113">Because `End` terminates your application without attending to any resources that might be open, you should try to close down cleanly before using it.</span></span> <span data-ttu-id="243a4-114">Beispielsweise verfügt die Anwendung aller Formulare zu öffnen, schließen sie die bevor die Steuerung der `End` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="243a4-114">For example, if your application has any forms open, you should close them before control reaches the `End` statement.</span></span>  
  
 <span data-ttu-id="243a4-115">Verwenden Sie `End` sparsam und nur, wenn Sie die Anwendung sofort beenden müssen.</span><span class="sxs-lookup"><span data-stu-id="243a4-115">You should use `End` sparingly, and only when you need to stop immediately.</span></span> <span data-ttu-id="243a4-116">Die normalen Verfahren zum Beenden einer Prozedur ([Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) und [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)) nicht nur das Verfahren ordnungsgemäß beendet, sondern auch dem aufrufenden Code die Möglichkeit, ordnungsgemäß zu beenden.</span><span class="sxs-lookup"><span data-stu-id="243a4-116">The normal ways to terminate a procedure ([Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) and [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)) not only close down the procedure cleanly but also give the calling code the opportunity to close down cleanly.</span></span> <span data-ttu-id="243a4-117">Eine Konsolenanwendung kann z.B. einfach `Return` aus der `Main` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="243a4-117">A console application, for example, can simply `Return` from the `Main` procedure.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="243a4-118">Die `End` Anweisung ruft die <xref:System.Environment.Exit%2A> Methode der <xref:System.Environment> -Klasse in der <xref:System> Namespace.</span><span class="sxs-lookup"><span data-stu-id="243a4-118">The `End` statement calls the <xref:System.Environment.Exit%2A> method of the <xref:System.Environment> class in the <xref:System> namespace.</span></span> <span data-ttu-id="243a4-119"><xref:System.Environment.Exit%2A> benötigen Sie `UnmanagedCode` Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="243a4-119"><xref:System.Environment.Exit%2A> requires that you have `UnmanagedCode` permission.</span></span> <span data-ttu-id="243a4-120">Wenn Sie nicht, führen eine <xref:System.Security.SecurityException> Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="243a4-120">If you do not, a <xref:System.Security.SecurityException> error occurs.</span></span>  
  
 <span data-ttu-id="243a4-121">Wenn ein zusätzliches Schlüsselwort gefolgt [End \<Schlüsselwort >-Anweisung](../../../visual-basic/language-reference/statements/end-keyword-statement.md) kennzeichnet das Ende der Definition der entsprechenden Prozedur oder des Block.</span><span class="sxs-lookup"><span data-stu-id="243a4-121">When followed by an additional keyword, [End \<keyword> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) delineates the end of the definition of the appropriate procedure or block.</span></span> <span data-ttu-id="243a4-122">Z. B. `End Function` beendet die Definition einer `Function` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="243a4-122">For example, `End Function` terminates the definition of a `Function` procedure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="243a4-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="243a4-123">Example</span></span>  
 <span data-ttu-id="243a4-124">Im folgenden Beispiel wird die `End` Anweisung, um die Ausführung von Code zu beenden, wenn der Benutzer es anfordert.</span><span class="sxs-lookup"><span data-stu-id="243a4-124">The following example uses the `End` statement to terminate code execution if the user requests it.</span></span>  
  
 [!code-vb[VbVersHelp60Controls#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVersHelp60Controls/VB/Form1.vb#64)]  
  
## <a name="smart-device-developer-notes"></a><span data-ttu-id="243a4-125">Hinweise für Entwickler intelligente Geräte</span><span class="sxs-lookup"><span data-stu-id="243a4-125">Smart Device Developer Notes</span></span>  
 <span data-ttu-id="243a4-126">Diese Anweisung wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="243a4-126">This statement is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="243a4-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="243a4-127">See also</span></span>

- <xref:System.Security.Permissions.SecurityPermissionFlag>
- [<span data-ttu-id="243a4-128">Stop-Anweisung</span><span class="sxs-lookup"><span data-stu-id="243a4-128">Stop Statement</span></span>](../../../visual-basic/language-reference/statements/stop-statement.md)
- [<span data-ttu-id="243a4-129">End \<Schlüsselwort >-Anweisung</span><span class="sxs-lookup"><span data-stu-id="243a4-129">End \<keyword> Statement</span></span>](../../../visual-basic/language-reference/statements/end-keyword-statement.md)
