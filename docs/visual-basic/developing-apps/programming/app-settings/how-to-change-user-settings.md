---
title: 'Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
ms.openlocfilehash: 05c95026d061918b38cf301209afefa9498e33bf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820970"
---
# <a name="how-to-change-user-settings-in-visual-basic"></a><span data-ttu-id="6b878-102">Vorgehensweise: Ändern von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b878-102">How to: Change User Settings in Visual Basic</span></span>
<span data-ttu-id="6b878-103">Sie können eine Benutzereinstellung ändern, indem Sie der Einstellung der Eigenschaft auf dem `My.Settings`-Objekt einen neuen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6b878-103">You can change a user setting by assigning a new value to the setting's property on the `My.Settings` object.</span></span>  
  
 <span data-ttu-id="6b878-104">Das `My.Settings`-Objekt macht jede Einstellung als Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6b878-104">The `My.Settings` object exposes each setting as a property.</span></span> <span data-ttu-id="6b878-105">Der Eigenschaftenname ist identisch mit dem Einstellungsnamen, und der Eigenschaftentyp entspricht dem Typ der Einstellung.</span><span class="sxs-lookup"><span data-stu-id="6b878-105">The property name is the same as the setting name, and the property type is the same as the setting type.</span></span> <span data-ttu-id="6b878-106">Der **Gültigkeitsbereich** einer Einstellung bestimmt, ob die Eigenschaft schreibgeschützt ist: Die Eigenschaft für eine Bereichseinstellung für die **Anwendung** ist schreibgeschützt, während die Eigenschaft für eine Bereichseinstellung für den **Benutzer** nicht schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="6b878-106">The setting's **Scope** determines if the property is read-only: The property for an **Application**-scope setting is read-only, while the property for a **User**-scope setting is read-write.</span></span> <span data-ttu-id="6b878-107">Weitere Informationen finden Sie unter [My.Settings-Objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span><span class="sxs-lookup"><span data-stu-id="6b878-107">For more information, see [My.Settings Object](../../../../visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b878-108">Obwohl Sie die Werte der Einstellungen für den Benutzerbereich zur Laufzeit ändern und speichern können, sind die Einstellungen für den Anwendungsbereich schreibgeschützt und können nicht programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6b878-108">Although you can change and save the values of user-scope settings at run time, application-scope settings are read-only and cannot be changed programmatically.</span></span> <span data-ttu-id="6b878-109">Sie können die Einstellungen für den Anwendungsbereich nur ändern, wenn Sie die Anwendung mithilfe des **Projekt-Designers** erstellen, oder indem Sie die Anwendungskonfigurationsdatei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6b878-109">You can change application-scope settings when you create the application by using the **Project Designer** or by editing the application's configuration file.</span></span> <span data-ttu-id="6b878-110">Weitere Informationen finden Sie unter [Verwalten von Anwendungseinstellungen (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span><span class="sxs-lookup"><span data-stu-id="6b878-110">For more information, see [Managing Application Settings (.NET)](/visualstudio/ide/managing-application-settings-dotnet).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b878-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b878-111">Example</span></span>  
 <span data-ttu-id="6b878-112">In diesem Beispiel wird der Wert der `Nickname`-Benutzereinstellung geändert.</span><span class="sxs-lookup"><span data-stu-id="6b878-112">This example changes the value of the `Nickname` user setting.</span></span>  
  
 [!code-vb[VbVbalrMyResources#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#7)]  
  
 <span data-ttu-id="6b878-113">Damit dieses Beispiel funktioniert, muss Ihre Anwendung eine `Nickname`-Benutzereinstellung vom Typ `String` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6b878-113">For this example to work, your application must have a `Nickname` user setting, of type `String`.</span></span>  
  
 <span data-ttu-id="6b878-114">Die Anwendung speichert die Benutzereinstellungen beim Herunterfahren der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6b878-114">The application saves the user settings when the application shuts down.</span></span> <span data-ttu-id="6b878-115">Um die Einstellungen sofort zu speichern, rufen Sie die `My.Settings.Save`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="6b878-115">To save the settings immediately, call the `My.Settings.Save` method.</span></span> <span data-ttu-id="6b878-116">Weitere Informationen finden Sie unter [Vorgehensweise: Beibehalten von Benutzereinstellungen](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span><span class="sxs-lookup"><span data-stu-id="6b878-116">For more information, see [How to: Persist User Settings in Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b878-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b878-117">See also</span></span>

- [<span data-ttu-id="6b878-118">My.Settings-Objekt</span><span class="sxs-lookup"><span data-stu-id="6b878-118">My.Settings Object</span></span>](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [<span data-ttu-id="6b878-119">Vorgehensweise: Lesen von Anwendungseinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b878-119">How to: Read Application Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [<span data-ttu-id="6b878-120">Vorgehensweise: Beibehalten von Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b878-120">How to: Persist User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [<span data-ttu-id="6b878-121">Vorgehensweise: Erstellen von Eigenschaftenrastern für Benutzereinstellungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b878-121">How to: Create Property Grids for User Settings in Visual Basic</span></span>](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [<span data-ttu-id="6b878-122">Verwalten von Anwendungseinstellungen (.NET)</span><span class="sxs-lookup"><span data-stu-id="6b878-122">Managing Application Settings (.NET)</span></span>](/visualstudio/ide/managing-application-settings-dotnet)
