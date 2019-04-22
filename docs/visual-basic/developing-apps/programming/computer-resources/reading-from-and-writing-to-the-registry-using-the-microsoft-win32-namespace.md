---
title: Lesen von der und Schreiben in die Registrierung mithilfe des Microsoft.Win32-Namespaces (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- registry [Visual Basic]
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
ms.openlocfilehash: f958fe9355e8c4e3701996cb33e48bd3e2bd759f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821906"
---
# <a name="reading-from-and-writing-to-the-registry-using-the-microsoftwin32-namespace-visual-basic"></a><span data-ttu-id="0d2b5-102">Lesen von der und Schreiben in die Registrierung mithilfe des Microsoft.Win32-Namespaces (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d2b5-102">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace (Visual Basic)</span></span>
<span data-ttu-id="0d2b5-103">Obwohl `My.Computer.Registry` alle Ihre Basisanforderungen beim Programmieren der Registrierung abdecken soll, können Sie alternativ die Klassen <xref:Microsoft.Win32.Registry> und <xref:Microsoft.Win32.RegistryKey> im <xref:Microsoft.Win32>-Namespace von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-103">Although `My.Computer.Registry` should cover your basic needs when programming against the registry, you can also use the <xref:Microsoft.Win32.Registry> and <xref:Microsoft.Win32.RegistryKey> classes in the <xref:Microsoft.Win32> namespace of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="keys-in-the-registry-class"></a><span data-ttu-id="0d2b5-104">Schlüssel in der Registry-Klasse</span><span class="sxs-lookup"><span data-stu-id="0d2b5-104">Keys in the Registry Class</span></span>  
 <span data-ttu-id="0d2b5-105">Die <xref:Microsoft.Win32.Registry>-Klasse stellt die Basisregistrierungsschlüssel bereit, die für den Zugriff auf Unterschlüssel und deren Werte verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-105">The <xref:Microsoft.Win32.Registry> class supplies the base registry keys that can be used to access subkeys and their values.</span></span> <span data-ttu-id="0d2b5-106">Die Basisschlüssel selbst sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-106">The base keys themselves are read-only.</span></span> <span data-ttu-id="0d2b5-107">In der folgenden Tabelle werden die sieben Schlüssel, die von der <xref:Microsoft.Win32.Registry>-Klasse verfügbar gemacht werden, aufgelistet und beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-107">The following table lists and describes the seven keys exposed by the <xref:Microsoft.Win32.Registry> class.</span></span>  
  
|<span data-ttu-id="0d2b5-108">**Key**</span><span class="sxs-lookup"><span data-stu-id="0d2b5-108">**Key**</span></span>|<span data-ttu-id="0d2b5-109">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0d2b5-109">**Description**</span></span>|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|<span data-ttu-id="0d2b5-110">Definiert die Typen von Dokumenten und die diesen Typen zugeordneten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-110">Defines the types of documents and the properties associated with those types.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|<span data-ttu-id="0d2b5-111">Enthält Informationen zur Hardwarekonfiguration, die nicht spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-111">Contains hardware configuration information that is not user-specific.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|<span data-ttu-id="0d2b5-112">Enthält Informationen über die aktuellen Benutzereinstellungen, z.B. Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-112">Contains information about the current user preferences, such as environmental variables.</span></span>|  
|<xref:Microsoft.Win32.Registry.DynData>|<span data-ttu-id="0d2b5-113">Enthält dynamische Registrierungsdaten, z.B. solche, die von virtuellen Gerätetreibern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-113">Contains dynamic registry data, such as that used by Virtual Device Drivers.</span></span>|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|<span data-ttu-id="0d2b5-114">Enthält fünf Unterschlüssel (Hardware, SAM, Security, Software und System), die die Konfigurationsdaten für den lokalen Computer enthalten.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-114">Contains five subkeys (Hardware, SAM, Security, Software, and System) that hold the configuration data for the local computer.</span></span>|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|<span data-ttu-id="0d2b5-115">Enthält Informationen zur Leistung für Softwarekomponenten.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-115">Contains performance information for software components.</span></span>|  
|<xref:Microsoft.Win32.Registry.Users>|<span data-ttu-id="0d2b5-116">Enthält Informationen zu den Standardeinstellungen für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-116">Contains information about the default user preferences.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="0d2b5-117">Es ist sicherer, Daten in den Schlüssel für den aktuellen Benutzer (<xref:Microsoft.Win32.Registry.CurrentUser>) statt in den Schlüssel für den lokalen Computer (<xref:Microsoft.Win32.Registry.LocalMachine>) zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-117">It is more secure to write data to the current user (<xref:Microsoft.Win32.Registry.CurrentUser>) than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span> <span data-ttu-id="0d2b5-118">Eine Bedingung, die in der Regel als „squatting“ bezeichnet wird, tritt auf, wenn der Schlüssel, den Sie erstellen, zuvor von einem anderen, möglicherweise böswilligen Prozess erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-118">A condition that's typically referred to as "squatting" occurs when the key you are creating was previously created by another, possibly malicious, process.</span></span> <span data-ttu-id="0d2b5-119">Um dies zu vermeiden, verwenden Sie eine Methode, z.B. <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, die `Nothing` zurückgibt, wenn der Schlüssel nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-119">To prevent this from occurring, use a method, such as <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, that returns `Nothing` if the key does not already exist.</span></span>  
  
## <a name="reading-a-value-from-the-registry"></a><span data-ttu-id="0d2b5-120">Lesen eines Werts aus der Registrierung</span><span class="sxs-lookup"><span data-stu-id="0d2b5-120">Reading a Value from the Registry</span></span>  
 <span data-ttu-id="0d2b5-121">Der folgende Code zeigt, wie eine Zeichenfolge aus HKEY_CURRENT_USER gelesen wird.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-121">The following code shows how to read a string from HKEY_CURRENT_USER.</span></span>  
  
 [!code-vb[VbResourceTasks#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#20)]  
  
 <span data-ttu-id="0d2b5-122">Der folgende Code liest, erhöht, und schreibt dann eine Zeichenfolge in HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="0d2b5-122">The following code reads, increments, and then writes a string to HKEY_CURRENT_USER.</span></span>  
  
 [!code-vb[VbResourceTasks#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="0d2b5-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d2b5-123">See also</span></span>

- <xref:System.SystemException>
- <xref:System.ApplicationException>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [<span data-ttu-id="0d2b5-124">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0d2b5-124">Try...Catch...Finally Statement</span></span>](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="0d2b5-125">Lesen aus der und Schreiben in die Registrierung</span><span class="sxs-lookup"><span data-stu-id="0d2b5-125">Reading from and Writing to the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
- [<span data-ttu-id="0d2b5-126">Sicherheit und die Registrierung</span><span class="sxs-lookup"><span data-stu-id="0d2b5-126">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)
