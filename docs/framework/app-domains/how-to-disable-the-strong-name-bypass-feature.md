---
title: 'Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion'
ms.date: 03/30/2017
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, loading into trusted application domains
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 86fc35ae20211bd32a21d60b7313074361aef671
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59296172"
---
# <a name="how-to-disable-the-strong-name-bypass-feature"></a><span data-ttu-id="5e893-102">Vorgehensweise: Deaktivieren der Strong-Name-Bypass-Funktion</span><span class="sxs-lookup"><span data-stu-id="5e893-102">How to: Disable the Strong-Name Bypass Feature</span></span>
<span data-ttu-id="5e893-103">Ab .NET Framework Version 3.5 Service Pack 1 (SP1) werden Signaturen mit starkem Namen nicht überprüft, wenn ein Assembly in ein vollständig vertrauenswürdiges <xref:System.AppDomain>-Objekt geladen wird, wie etwa die Standard-<xref:System.AppDomain> für die `MyComputer`-Zone.</span><span class="sxs-lookup"><span data-stu-id="5e893-103">Starting with the .NET Framework version 3.5 Service Pack 1 (SP1), strong-name signatures are not validated when an assembly is loaded into a full-trust <xref:System.AppDomain> object, such as the default <xref:System.AppDomain> for the `MyComputer` zone.</span></span> <span data-ttu-id="5e893-104">Dies wird Strong-Name-Bypass-Funktion genannt.</span><span class="sxs-lookup"><span data-stu-id="5e893-104">This is referred to as the strong-name bypass feature.</span></span> <span data-ttu-id="5e893-105">In einer vollständig vertrauenswürdigen Umgebung sind Forderungen nach <xref:System.Security.Permissions.StrongNameIdentityPermission> für signierte, vollständig vertrauenswürdige Assemblys immer erfolgreich, unabhängig von deren Signatur.</span><span class="sxs-lookup"><span data-stu-id="5e893-105">In a full-trust environment, demands for <xref:System.Security.Permissions.StrongNameIdentityPermission> always succeed for signed, full-trust assemblies regardless of their signature.</span></span> <span data-ttu-id="5e893-106">Einzige Einschränkung ist die Tatsache, dass die Assembly vollständig vertrauenswürdig sein muss, da deren Zone vollständig vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="5e893-106">The only restriction is that the assembly must be fully trusted because its zone is fully trusted.</span></span> <span data-ttu-id="5e893-107">Da der starke Name unter diesen Bedingungen kein bestimmender Faktor ist, gibt es auch keinen Grund, ihn zu validieren.</span><span class="sxs-lookup"><span data-stu-id="5e893-107">Because the strong name is not a determining factor under these conditions, there is no reason for it to be validated.</span></span> <span data-ttu-id="5e893-108">Das Umgehen der Validierung einer Signatur mit starkem Namen führt zu deutlichen Verbesserungen in der Leistung.</span><span class="sxs-lookup"><span data-stu-id="5e893-108">Bypassing the validation of strong-name signatures provides significant performance improvements.</span></span>  
  
 <span data-ttu-id="5e893-109">Die Bypass-Funktion gilt für alle vollständig vertrauenswürdigen Assemblys, die nicht verzögert signiert wurden, und die in eine vollständig vertrauenswürdige <xref:System.AppDomain> aus einem von der <xref:System.AppDomainSetup.ApplicationBase%2A>-Eigenschaft angegebenen Verzeichnis geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="5e893-109">The bypass feature applies to any full-trust assembly that is not delay-signed and that is loaded into any full-trust <xref:System.AppDomain> from the directory specified by its <xref:System.AppDomainSetup.ApplicationBase%2A> property.</span></span>  
  
 <span data-ttu-id="5e893-110">Sie können die Bypass-Funktion für alle Anwendungen auf einem Computer deaktivieren, indem Sie einen Wert für den Registrierungsschlüssel festlegen.</span><span class="sxs-lookup"><span data-stu-id="5e893-110">You can override the bypass feature for all applications on a computer by setting a registry key value.</span></span> <span data-ttu-id="5e893-111">Sie können die Einstellung für eine einzelne Anwendung deaktivieren, indem Sie eine Anwendungskonfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="5e893-111">You can override the setting for a single application by using an application configuration file.</span></span> <span data-ttu-id="5e893-112">Sie können die Bypass-Funktion nicht für eine einzelne Anwendung wiederherstellen, wenn sie vom Registrierungsschlüssel deaktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="5e893-112">You cannot reinstate the bypass feature for a single application if it has been disabled by the registry key.</span></span>  
  
 <span data-ttu-id="5e893-113">Wenn Sie die Bypass-Funktion deaktivieren, wird der starke Name nur auf Korrektheit geprüft. Er wird nicht auf <xref:System.Security.Permissions.StrongNameIdentityPermission> geprüft.</span><span class="sxs-lookup"><span data-stu-id="5e893-113">When you override the bypass feature, the strong name is validated only for correctness; it is not checked for a <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span></span> <span data-ttu-id="5e893-114">Wenn Sie einen bestimmten starken Namen überprüfen möchten, müssen Sie diesen Test separat durchführen.</span><span class="sxs-lookup"><span data-stu-id="5e893-114">If you want to confirm a specific strong name, you have to perform that check separately.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5e893-115">Ob Sie die Möglichkeit haben, die Validierung eines starken Namens zu erzwingen, hängt vom Registrierungsschlüssel ab, wie in folgender Prozedur beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5e893-115">The ability to force strong-name validation depends on a registry key, as described in the following procedure.</span></span> <span data-ttu-id="5e893-116">Wenn eine Anwendung unter einem Konto ausgeführt wird, dass keine ACL-Berechtigung (Access Control List) hat, um auf diesen Registrierungsschlüssel zuzugreifen, ist diese Einstellung unwirksam.</span><span class="sxs-lookup"><span data-stu-id="5e893-116">If an application is running under an account that does not have access control list (ACL) permission to access that registry key, the setting is ineffective.</span></span> <span data-ttu-id="5e893-117">Sie müssen sicherstellen, dass die ACL-Rechte für diesen Schlüssel so konfiguriert sind, dass er für alle Assemblys gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="5e893-117">You must ensure that ACL rights are configured for this key so that it can be read for all assemblies.</span></span>  
  
### <a name="to-disable-the-strong-name-bypass-feature-for-all-applications"></a><span data-ttu-id="5e893-118">So können Sie die Strong-Name-Bypass-Funktion für alle Anwendungen deaktivieren</span><span class="sxs-lookup"><span data-stu-id="5e893-118">To disable the strong-name bypass feature for all applications</span></span>  
  
-   <span data-ttu-id="5e893-119">Erstellen Sie auf 32-Bit-Computern einen DWORD-Eintrag mit einem Wert von 0 (null) mit dem Namen `AllowStrongNameBypass` unter dem Schlüssel „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework“ in der Registrierung des Systems.</span><span class="sxs-lookup"><span data-stu-id="5e893-119">On 32-bit computers, in the system registry, create a DWORD entry with a value of 0 named `AllowStrongNameBypass` under the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
-   <span data-ttu-id="5e893-120">Erstellen Sie auf 64-Bit-Computern einen DWORD-Eintrag mit einem Wert von 0 (null) mit dem Namen `AllowStrongNameBypass` unter den Schlüsseln „HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework“ und „HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework“ in der Registrierung des Systems.</span><span class="sxs-lookup"><span data-stu-id="5e893-120">On 64-bit computers, in the system registry, create a DWORD entry with a value of 0 named `AllowStrongNameBypass` under the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework and HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework keys.</span></span>  
  
### <a name="to-disable-the-strong-name-bypass-feature-for-a-single-application"></a><span data-ttu-id="5e893-121">So können Sie die Strong-Name-Bypass-Funktion für eine Anwendung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="5e893-121">To disable the strong-name bypass feature for a single application</span></span>  
  
1. <span data-ttu-id="5e893-122">Öffnen oder erstellen Sie die Anwendungskonfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5e893-122">Open or create the application configuration file.</span></span>  
  
     <span data-ttu-id="5e893-123">Weitere Informationen zu dieser Datei finden Sie im Abschnitt zu Anwendungskonfigurationsdateien unter [Configuring Apps (Konfigurationsdateien)](../../../docs/framework/configure-apps/index.md).</span><span class="sxs-lookup"><span data-stu-id="5e893-123">For more information about this file, see the Application Configuration Files section in [Configuring Apps](../../../docs/framework/configure-apps/index.md).</span></span>  
  
2. <span data-ttu-id="5e893-124">Fügen Sie folgenden Eintrag hinzu:</span><span class="sxs-lookup"><span data-stu-id="5e893-124">Add the following entry:</span></span>  
  
    ```xml  
    <configuration>  
      <runtime>  
        <bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 <span data-ttu-id="5e893-125">Sie können die Bypass-Funktion für die Anwendung wieder aktivieren, indem Sie die Einstellung der Konfigurationsdatei entfernen oder das Attribut auf „TRUE“ festlegen.</span><span class="sxs-lookup"><span data-stu-id="5e893-125">You can restore the bypass feature for the application by removing the configuration file setting or by setting the attribute to "true".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e893-126">Sie können die Überprüfung von starken Namen für eine Anwendung nur dann aktivieren oder deaktivieren, wenn die Bypass-Funktion auf dem Computer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5e893-126">You can turn strong-name validation on and off for an application only if the bypass feature is enabled for the computer.</span></span> <span data-ttu-id="5e893-127">Wenn die Bypass-Funktion auf dem Computer deaktiviert wurde, werden starke Namen für alle Anwendungen überprüft, und Sie können die Überprüfung nicht für eine einzelne Anwendung umgehen.</span><span class="sxs-lookup"><span data-stu-id="5e893-127">If the bypass feature has been turned off for the computer, strong names are validated for all applications and you cannot bypass validation for a single application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e893-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e893-128">See also</span></span>

- [<span data-ttu-id="5e893-129">Sn.exe (Strong Name-Tool)</span><span class="sxs-lookup"><span data-stu-id="5e893-129">Sn.exe (Strong Name Tool)</span></span>](../../../docs/framework/tools/sn-exe-strong-name-tool.md)
- [<span data-ttu-id="5e893-130">\<bypassTrustedAppStrongNames>-Element</span><span class="sxs-lookup"><span data-stu-id="5e893-130">\<bypassTrustedAppStrongNames> Element</span></span>](../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md)
- [<span data-ttu-id="5e893-131">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="5e893-131">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
