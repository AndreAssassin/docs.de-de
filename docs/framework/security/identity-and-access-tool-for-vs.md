---
title: Identitäts- und Zugriffs-Tool für Visual Studio 2012
ms.date: 03/30/2017
ms.assetid: 87b8f8f2-4074-44fd-9fd6-08278e877390
author: BrucePerlerMS
ms.openlocfilehash: 999b85576c52d065075cad105c3212c1b034084f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626036"
---
# <a name="identity-and-access-tool-for-visual-studio-2012"></a><span data-ttu-id="928f7-102">Identitäts- und Zugriffs-Tool für Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="928f7-102">Identity and Access Tool for Visual Studio 2012</span></span>
<span data-ttu-id="928f7-103">In diesem Thema wird das neue Identitäts- und Zugriffs-Tool für Visual Studio 11 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="928f7-103">This topic describes the new Identity and Access Tool for Visual Studio 11.</span></span> <span data-ttu-id="928f7-104">Sie können dieses Tool von folgender URL herunterladen: <https://go.microsoft.com/fwlink/?LinkID=245849> oder direkt aus Visual Studio 11 durch Suchen nach "Identität" direkt im Erweiterungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="928f7-104">You can download this tool from the following URL: <https://go.microsoft.com/fwlink/?LinkID=245849> or directly from within Visual Studio 11 by searching for "identity" directly in the Extensions Manager.</span></span>  
  
 <span data-ttu-id="928f7-105">Das Identitäts- und Zugriffs-Tool für Visual Studio 11 bietet eine vereinfachte Entwicklungserfahrung mit folgenden Vorteilen:</span><span class="sxs-lookup"><span data-stu-id="928f7-105">The Identity and Access Tool for Visual Studio 11 delivers a dramatically simplified development-time experience with the following highlights:</span></span>  
  
- <span data-ttu-id="928f7-106">Mithilfe des neuen Tools können Sie Webanwendungsprojekttypen für die Entwicklung und IIS Express als Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="928f7-106">Using the new tool, you can develop using web applications project types and target IIS express.</span></span>  
  
- <span data-ttu-id="928f7-107">Anders als bei der pauschalen Authentifizierung können Sie mit dem neuen Tool die lokale Startseitenbereich-Discovery-Seite bzw. den Controller (oder einen anderen Endpunkt, der für die Authentifizierungserfahrung innerhalb der Anwendung zuständig ist) angeben. WIF konfiguriert dann alle nicht authentifizierten Anforderungen für diesen Endpunkt, anstatt sie an den STS umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="928f7-107">Unlike with the blanket protection-only authentication, with the new tool, you can specify your local home realm discovery page/controller (or any other endpoint handling the authentication experience within your application) and WIF will configure all unauthenticated requests to go there, instead of redirecting them to the STS.</span></span>  
  
- <span data-ttu-id="928f7-108">Das Tool enthält einen Test-Sicherheitstokendienst (STS), der auf dem lokalen Computer ausgeführt wird, wenn Sie eine Debugsitzung starten.</span><span class="sxs-lookup"><span data-stu-id="928f7-108">The tool includes a test Security Token Service (STS) which runs on your local machine when you launch a debug session.</span></span> <span data-ttu-id="928f7-109">Daher müssen Sie keine benutzerdefinierten STS-Projekte mehr erstellen und ändern, um die Ansprüche abzurufen, die Sie zum Testen der Anwendungen benötigen.</span><span class="sxs-lookup"><span data-stu-id="928f7-109">Therefore, you no longer need to create custom STS projects and tweak them in order to get the claims you need to test your applications.</span></span> <span data-ttu-id="928f7-110">Die Anspruchstypen und -werte sind vollständig anpassbar.</span><span class="sxs-lookup"><span data-stu-id="928f7-110">The claim types and values are fully customizable.</span></span>  
  
- <span data-ttu-id="928f7-111">Sie können allgemeine Einstellungen direkt über die Benutzeroberfläche des Tools ändern, ohne die Datei web.config zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="928f7-111">You can modify common settings directly via the tool’s UI, without the need to edit web.config.</span></span>  
  
- <span data-ttu-id="928f7-112">Sie können den Verbund mit Active Directory-Verbunddiensten (AD FS) 2.0 (oder mit anderen WS-Verbund-Anbietern) in nur einem Bildschirm erstellen.</span><span class="sxs-lookup"><span data-stu-id="928f7-112">You can establish federation with Active Directory Federation Services (AD FS) 2.0 (or other WS-Federation providers) in a single screen.</span></span>  
  
- <span data-ttu-id="928f7-113">Das Tool nutzt die Funktionen von Windows Azure Access Control Service (ACS) mit einer einfachen Liste mit Kontrollkästchen für alle Identitätsanbieter, die Sie verwenden möchten: Facebook, Google, Live ID, Yahoo!, OpenID-Anbieter und WS-Verbund-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="928f7-113">The tool leverages Windows Azure Access Control Service (ACS) capabilities with a simple list of checkboxes for all the identity providers that you want to use: Facebook, Google, Live ID, Yahoo!, any OpenID provider, and any WS-Federation provider.</span></span> <span data-ttu-id="928f7-114">Wählen Sie die Identitätsanbieter aus, klicken Sie auf "OK", und drücken Sie F5. Daraufhin werden die Anwendung und ACS automatisch konfiguriert und die Testanwendung ist ACS-fähig.</span><span class="sxs-lookup"><span data-stu-id="928f7-114">Select your identity providers, click OK, then F5, and both your application and ACS will be automatically configured and your test application will be ACS-aware.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="928f7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="928f7-115">See also</span></span>

- [<span data-ttu-id="928f7-116">WIF-Features</span><span class="sxs-lookup"><span data-stu-id="928f7-116">WIF Features</span></span>](../../../docs/framework/security/wif-features.md)
