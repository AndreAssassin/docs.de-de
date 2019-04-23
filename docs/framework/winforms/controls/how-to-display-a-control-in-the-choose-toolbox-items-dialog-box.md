---
title: 'Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“'
ms.date: 03/30/2017
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: d504ace9e5571246ae0e78e165a7ad2bc23fa481
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085297"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Vorgehensweise: Anzeigen eines Steuerelements im Dialogfeld „Toolboxelemente auswählen“
Beim Entwickeln und Verteilen von Steuerelementen, sollten Sie die Steuerelemente angezeigt werden die **Toolboxelemente** dieses Dialogfeld wird angezeigt, wenn Sie mit der rechten Maustaste die **Toolbox** , und wählen Sie  **Wählen Sie Elemente aus**. Sie können das Steuerelement in diesem Dialogfeld angezeigt werden, mithilfe der Registrierungsvorgang "AssemblyFoldersEx" aktivieren.  
  
### <a name="to-display-your-control-in-the-choose-toolbox-items-dialog-box"></a>Das Steuerelement im Dialogfeld "Toolboxelemente auswählen" angezeigt.  
  
-   Installieren Sie die Steuerelementassembly im globalen Assemblycache. Weitere Informationen finden Sie unter [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)  
  
     - oder -   
  
-   Registrieren Sie Ihr Steuerelement und seine zugehörigen Entwurfszeitassemblys mithilfe der Registrierungsvorgang "AssemblyFoldersEx" ein. "AssemblyFoldersEx" ist ein Registrierungsspeicherort, in dem Drittanbieter Pfade für jede Version des Frameworks speichern, die sie unterstützen. Design-Time-Lösung kann an diesem Registrierungsspeicherort Verweisassemblys suchen Suchen. Das Registrierungsskript kann die Steuerelemente angeben, die in der Toolbox angezeigt werden sollen. Weitere Informationen finden Sie unter [Bereitstellen eines benutzerdefinierten Steuerelements und Entwurfszeitassemblys](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100)).  
  
## <a name="see-also"></a>Siehe auch

- [Dialogfeld „Toolboxelemente auswählen“ (Visual Studio)](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))
- [Bereitstellen eines benutzerdefinierten Steuerelements und während der Entwurfszeit-Assemblys](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ee849818(v=vs.100))
- [Entwickeln von Windows Forms-Steuerelementen zur Entwurfszeit](developing-windows-forms-controls-at-design-time.md)
- [Vorgehensweise: Installieren einer Assembly im globalen Assemblycache](../../app-domains/how-to-install-an-assembly-into-the-gac.md)
- [Exemplarische Vorgehensweise: Automatisches Füllen der Toolbox mit benutzerdefinierten Komponenten](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
