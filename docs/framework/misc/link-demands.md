---
title: Verknüpfungsaufrufe
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3bde5b18437cc9890f660f018e81582a4d708d2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910920"
---
# <a name="link-demands"></a><span data-ttu-id="6ceb7-102">Verknüpfungsaufrufe</span><span class="sxs-lookup"><span data-stu-id="6ceb7-102">Link Demands</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="6ceb7-103">Ein Linkaufruf (Verknüpfungsaufruf) bewirkt eine Sicherheitsüberprüfung während der Just-In-Time-Kompilierung, wobei nur die direkt aufrufende Assembly Ihres Codes überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-103">A link demand causes a security check during just-in-time compilation and checks only the immediate calling assembly of your code.</span></span> <span data-ttu-id="6ceb7-104">Das Verlinken erfolgt, wenn der Code an einen Typverweis, einschließlich Funktionszeigerverweise und Methodenaufrufe, gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-104">Linking occurs when your code is bound to a type reference, including function pointer references and method calls.</span></span> <span data-ttu-id="6ceb7-105">Hat die aufrufende Assembly keine ausreichende Berechtigung, Ihren Code zu verlinken, ist der Link unzulässig, und beim Laden und Ausführen des Codes wird eine Laufzeitausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-105">If the calling assembly does not have sufficient permission to link to your code, the link is not allowed and a runtime exception is thrown when the code is loaded and run.</span></span> <span data-ttu-id="6ceb7-106">Linkaufrufe können in Klassen, die von Ihrem Code erben, überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-106">Link demands can be overridden in classes that inherit from your code.</span></span>  
  
 <span data-ttu-id="6ceb7-107">Beachten Sie, dass bei diesem Typ von Forderung kein vollständiger Stackwalk durchgeführt wird und der Code weiterhin anfällig für Täuschungsmanöver ist.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-107">Note that a full stack walk is not performed with this type of demand and that your code is still susceptible to luring attacks.</span></span> <span data-ttu-id="6ceb7-108">Wenn eine Methode in Assembly a z. b. durch einen Link Aufruf geschützt ist, wird ein direkter Aufrufer in Assembly b basierend auf den Berechtigungen von Assembly b ausgewertet.  Der Link Aufruf wertet jedoch keine Methode in Assembly C aus, wenn er die Methode in Assembly a mithilfe der-Methode in Assembly B indirekt aufruft. Der Link Aufruf gibt nur die Berechtigungen an, die direkte Aufrufer in der unmittelbaren aufrufenden Assembly zum Verknüpfen mit dem Code benötigen.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-108">For example, if a method in assembly A is protected by a link demand, a direct caller in assembly B is evaluated based on the permissions of Assembly B.  However, the link demand will not evaluate a method in assembly C if it indirectly calls the method in assembly A using the method in assembly B. The link demand specifies only the permissions direct callers in the immediate calling assembly must have to link to your code.</span></span> <span data-ttu-id="6ceb7-109">Er gibt nicht die Berechtigungen an, die alle Aufrufer haben müssen, um Ihren Code auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-109">It does not specify the permissions all callers must have to run your code.</span></span>  
  
 <span data-ttu-id="6ceb7-110">Die Stackwalkmodifizierer <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> und <xref:System.Security.CodeAccessPermission.PermitOnly%2A> haben keinen Einfluss auf die Auswertung von Linkaufrufen.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-110">The <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A>, and <xref:System.Security.CodeAccessPermission.PermitOnly%2A> stack walk modifiers do not affect the evaluation of link demands.</span></span>  <span data-ttu-id="6ceb7-111">Da Linkaufrufe keinen Stackwalk ausführen, haben die Stackwalkmodifizierer keinen Einfluss auf Linkaufrufe.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-111">Because link demands do not perform a stack walk, the stack walk modifiers have no effect on link demands.</span></span>  
  
 <span data-ttu-id="6ceb7-112">Wenn auf eine durch einen Link Aufruf geschützte Methode über [Reflektion](../../../docs/framework/reflection-and-codedom/reflection.md)zugegriffen wird, überprüft ein Link Aufruf den unmittelbaren Aufrufer des Codes, auf den über Reflektion zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-112">If a method protected by a link demand is accessed through [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md), then a link demand checks the immediate caller of the code accessed through reflection.</span></span> <span data-ttu-id="6ceb7-113">Dies gilt sowohl für Methodenerkennungen als auch Methodenaufrufe, die über Reflektion ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-113">This is true both for method discovery and for method invocation performed using reflection.</span></span> <span data-ttu-id="6ceb7-114">Angenommen, Code verwendet Reflektion, um ein <xref:System.Reflection.MethodInfo> -Objekt zurückzugeben, das eine durch einen Link Aufruf geschützte Methode darstellt, und übergibt dieses **MethodInfo** -Objekt dann an einen anderen Code, der das-Objekt verwendet, um die ursprüngliche Methode aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-114">For example, suppose code uses reflection to return a <xref:System.Reflection.MethodInfo> object representing a method protected by a link demand and then passes that **MethodInfo** object to some other code that uses the object to invoke the original method.</span></span> <span data-ttu-id="6ceb7-115">In diesem Fall erfolgt die Überprüfung des Link Bedarfs zweimal: einmal für den Code, der das **MethodInfo** -Objekt zurückgibt, und einmal für den Code, der es aufruft.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-115">In this case the link demand check occurs twice: once for the code that returns the **MethodInfo** object and once for the code that invokes it.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ceb7-116">Ein Linkaufruf, der für einen statischen Klassenkonstruktor durchgeführt wird, schützt diesen Konstruktor nicht, da statische Konstruktoren vom System außerhalb des Codeausführungspfades der Anwendung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-116">A link demand performed on a static class constructor does not protect the constructor because static constructors are called by the system, outside the application's code execution path.</span></span> <span data-ttu-id="6ceb7-117">Dies hat zur Folge, dass ein Linkaufruf, wenn er auf eine ganze Klasse angewendet wird, einen statischen Konstruktor nicht schützen kann, obwohl er der Rest der Klasse schützt.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-117">As a result, when a link demand is applied to an entire class, it cannot protect access to a static constructor, although it does protect the rest of the class.</span></span>  
  
 <span data-ttu-id="6ceb7-118">Im folgenden Codefragment wird deklarativ angegeben, dass sämtlicher Code mit einer Verlinkung zur `ReadData`-Methode die `CustomPermission`-Berechtigung haben muss.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-118">The following code fragment declaratively specifies that any code linking to the `ReadData` method must have the `CustomPermission` permission.</span></span> <span data-ttu-id="6ceb7-119">Diese Berechtigung ist eine hypothetische benutzerdefinierte Berechtigung und nicht in .NET Framework vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-119">This permission is a hypothetical custom permission and does not exist in the .NET Framework.</span></span> <span data-ttu-id="6ceb7-120">Die Anforderung erfolgt durch Übergeben eines **SecurityAction. LinkDemand** -Flags an den `CustomPermissionAttribute`.</span><span class="sxs-lookup"><span data-stu-id="6ceb7-120">The demand is made by passing a **SecurityAction.LinkDemand** flag to the `CustomPermissionAttribute`.</span></span>  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function    
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6ceb7-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ceb7-121">See also</span></span>

- [<span data-ttu-id="6ceb7-122">Attribute</span><span class="sxs-lookup"><span data-stu-id="6ceb7-122">Attributes</span></span>](../../standard/attributes/index.md)
- [<span data-ttu-id="6ceb7-123">Codezugriffssicherheit</span><span class="sxs-lookup"><span data-stu-id="6ceb7-123">Code Access Security</span></span>](../../../docs/framework/misc/code-access-security.md)
