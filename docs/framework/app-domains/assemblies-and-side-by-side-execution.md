---
title: Assemblys und parallele Ausführung
ms.date: 03/30/2017
helpviewer_keywords:
- side-by-side execution [.NET Framework]
- assemblies [.NET Framework], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa44090e589e7a2a70b8fb7dbd8d5e6967c1ed19
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126637"
---
# <a name="assemblies-and-side-by-side-execution"></a>Assemblys und parallele Ausführung
Als parallele Ausführung wird die Möglichkeit bezeichnet, mehrere Versionen einer Anwendung oder einer Komponente auf demselben Computer zu speichern und auszuführen. Das bedeutet, dass Sie gleichzeitig mehrere Versionen der Common Language Runtime sowie mehrere Versionen von Anwendungen und Komponenten, die eine Version der Common Language Runtime verwenden, gleichzeitig auf demselben Computer ausführen können. Durch die parallele Ausführung können Sie besser steuern, an welche Version einer Komponente eine Anwendung gebunden wird und welche Version der Common Language Runtime eine Anwendung verwendet.  
  
 Die parallele Speicherung und Ausführung verschiedener Versionen derselben Assembly wird durch starke Namen systematisch unterstützt, und es ist integraler Bestandteil der Infrastruktur der Laufzeit. Da die Versionsnummer zur Identität einer Assembly mit starkem Namen gehört, kann die Laufzeit mehrere Versionen derselben Assembly im globalen Assemblycache speichern und diese Assemblys zur Laufzeit laden.  
  
 Obwohl die Laufzeit das Erstellen von parallel ausführbaren Anwendungen unterstützt, werden diese nicht automatisch parallel ausgeführt. Weitere Informationen zur Erstellung von Anwendungen für die parallele Ausführung finden Sie unter [Guidelines for Creating Components for Side-by-Side Execution (Richtlinien für die Erstellung von Komponenten für die parallele Ausführung)](../../../docs/framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).  
  
## <a name="see-also"></a>Siehe auch

- [So sucht Common Language Runtime nach Assemblys](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [Assemblys in der Common Language Runtime (CLR)](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
