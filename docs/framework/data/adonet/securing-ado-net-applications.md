---
title: Sichern von ADO.NET-Anwendungen
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: d4c9c21f4d1f4a08ca6d676ee7b4c9e80709ba19
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963118"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="ffc7d-102">Sichern von ADO.NET-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="ffc7d-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="ffc7d-103">Beim Schreiben von sicheren ADO.NET-Anwendungen gilt es nicht nur, häufige Fallstricke bei der Codierung zu umgehen, wie die Nichtvalidierung von Benutzereingaben.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="ffc7d-104">Eine Anwendung, die auf Daten zugreift, verfügt über viele mögliche Schwachstellen, über die ein Hacker vertrauliche Daten abrufen, manipulieren oder vernichten kann.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="ffc7d-105">Es ist daher unerlässlich, alle Sicherheitsaspekte zu verstehen, und zwar beginnend bei der Erstellung von Gefahrenmodellen während des Anwendungsentwurfs bis hin zur eigentlichen Bereitstellung der Anwendung und ihrem laufenden Betrieb.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="ffc7d-106">.NET Framework bietet eine Reihe nützlicher Klassen, Dienste und Tools zum Sichern und Verwalten von Datenbankanwendungen.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="ffc7d-107">Die Common Language Runtime (CLR) bietet eine typsichere Umgebung für die Ausführung von Code mit Codezugriffssicherheit (Code Access Security, CAS), um die Berechtigungen für verwalteten Code weiter einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="ffc7d-108">Die Beachtung von Codierungspraktiken für einen sicheren Datenzugriff hilft, den Schaden zu begrenzen, den ein potenzieller Angreifer verursachen kann.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="ffc7d-109">Das Schreiben von sicherem Code schützt jedoch nicht vor selbst zu verantwortenden Sicherheitslücken beim Arbeiten mit nicht verwalteten Ressourcen, wie Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="ffc7d-110">Die meisten Serverdatenbanken, wie SQL Server, verfügen über eigene Sicherheitssysteme, die bei korrekter Implementierung für mehr Sicherheit sorgen.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="ffc7d-111">Aber auch Datenquellen mit einem robusten Sicherheitssystem können zum Angriffsopfer werden, wenn sie nicht ordnungsgemäß konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ffc7d-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ffc7d-112">In This Section</span></span>  
 [<span data-ttu-id="ffc7d-113">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ffc7d-113">Security Overview</span></span>](../../../../docs/framework/data/adonet/security-overview.md)  
 <span data-ttu-id="ffc7d-114">Enthält Empfehlungen für das Entwerfen sicherer ADO.NET-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="ffc7d-115">Sicherer Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="ffc7d-115">Secure Data Access</span></span>](../../../../docs/framework/data/adonet/secure-data-access.md)  
 <span data-ttu-id="ffc7d-116">Beschreibt das Arbeiten mit Daten aus einer gesicherten Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="ffc7d-117">Sichere Clientanwendungen</span><span class="sxs-lookup"><span data-stu-id="ffc7d-117">Secure Client Applications</span></span>](../../../../docs/framework/data/adonet/secure-client-applications.md)  
 <span data-ttu-id="ffc7d-118">Enthält Überlegungen zum Thema Sicherheit für Clientanwendungen.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="ffc7d-119">Codezugriffssicherheit und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ffc7d-119">Code Access Security and ADO.NET</span></span>](../../../../docs/framework/data/adonet/code-access-security.md)  
 <span data-ttu-id="ffc7d-120">Beschreibt, wie CAS zum Schutz von ADO.NET-Code beitragen kann.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="ffc7d-121">Erläutert außerdem das Arbeiten mit teilweiser Vertrauenswürdigkeit.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="ffc7d-122">Datenschutz und -sicherheit</span><span class="sxs-lookup"><span data-stu-id="ffc7d-122">Privacy and Data Security</span></span>](../../../../docs/framework/data/adonet/privacy-and-data-security.md)  
 <span data-ttu-id="ffc7d-123">Beschreibt Verschlüsselungsmöglichkeiten für ADO.NET-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ffc7d-124">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ffc7d-124">Related Sections</span></span>  
 [<span data-ttu-id="ffc7d-125">SQL Server Security (SQL Server-Sicherheit)</span><span class="sxs-lookup"><span data-stu-id="ffc7d-125">SQL Server Security</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-security.md)  
 <span data-ttu-id="ffc7d-126">Beschreibt SQL Server-Sicherheitsfunktionen aus Entwicklersicht.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="ffc7d-127">Überlegungen zur Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ffc7d-127">Security Considerations</span></span>](../../../../docs/framework/data/adonet/ef/security-considerations.md)  
 <span data-ttu-id="ffc7d-128">Beschreibt Sicherheitsfunktionen für Entity Framework-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="ffc7d-129">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ffc7d-129">Security</span></span>](../../../standard/security/index.md)  
 <span data-ttu-id="ffc7d-130">Enthält Links zu Themen, in denen alle Aspekte der Sicherheit in .NET beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="ffc7d-131">[Sicherheitstools](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="ffc7d-131">[Security Tools](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="ffc7d-132">.NET Framework-Tools zum Sichern und Verwalten von Sicherheitsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="ffc7d-133">[Ressourcen für das Erstellen sicherer Anwendungen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="ffc7d-133">[Resources for Creating Secure Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="ffc7d-134">Enthält Links zu Themen zum Erstellen sicherer Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="ffc7d-135">Sicherheitsbibliographie</span><span class="sxs-lookup"><span data-stu-id="ffc7d-135">Security Bibliography</span></span>](/visualstudio/ide/security-bibliography)  
 <span data-ttu-id="ffc7d-136">Enthält Links zu externen Ressourcen, die online und in Druckversion verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ffc7d-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc7d-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffc7d-137">See also</span></span>

- [<span data-ttu-id="ffc7d-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ffc7d-138">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="ffc7d-139">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="ffc7d-139">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
