---
title: Anpassen der verfügbaren Objekte in "My" (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
ms.assetid: 4e8279c2-ed5b-4681-8903-8a6671874000
ms.openlocfilehash: bb3f8eb2e8b1cf5bce364fc4b3ce0587769bb5f9
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775211"
---
# <a name="customizing-which-objects-are-available-in-my-visual-basic"></a>Anpassen der verfügbaren Objekte in "My" (Visual Basic)

In diesem Thema wird beschrieben, wie Sie steuern können, welche `My` Objekte aktiviert werden, indem Sie die `_MYTYPE` bedingte Kompilierungs Konstante Ihres Projekts festlegen. Die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) von Visual Studio hält die `_MYTYPE` bedingte Kompilierungs Konstante für ein Projekt synchron mit dem Projekttyp.  
  
## <a name="predefined-_mytype-values"></a>Vordefinierte \_MYTYPE Werte  

Sie müssen die `/define`-Compileroption verwenden, um die `_MYTYPE` bedingte Kompilierungs Konstante festzulegen. Wenn Sie einen eigenen Wert für die `_MYTYPE` Konstante angeben, müssen Sie den Zeichen folgen Wert in Sequenzen mit umgekehrtem Schrägstrich/Anführungszeichen (\\ ") einschließen. Beispielsweise können Sie Folgendes verwenden:  
  
```console  
/define:_MYTYPE=\"WindowsForms\"  
```  
  
 Diese Tabelle zeigt, wie die Konstante für die `_MYTYPE` bedingte Kompilierung für mehrere Projekttypen auf festgelegt ist.  
  
|Projekttyp:|\_MYTYPE Wert|  
|------------------|--------------------|  
|Klassenbibliothek|Windows|  
|Konsolenanwendung|TS|  
|Web|Kamera|  
|Websteuer Element Bibliothek|WebControl|  
|Windows-Anwendung|WindowsForms|  
|Windows-Anwendung, wenn Sie mit benutzerdefinierten `Sub Main` beginnen|"Windowsformswithcustomsubmain"|  
|Windows-Steuerelement Bibliothek|Windows|  
|Windows-Dienst|TS|  
|Empty|Leer|  
  
> [!NOTE]
> Bei allen Zeichen folgen vergleichen mit bedingter Kompilierung wird die Groß-/Kleinschreibung beachtet, unabhängig davon, wie die `Option Compare` Anweisung festgelegt wird  
  
## <a name="dependent-_my-compilation-constants"></a>Abhängige \_MY Kompilierungs Konstanten  

Die `_MYTYPE` bedingte Kompilierungs Konstante steuert wiederum die Werte mehrerer anderer `_MY` Kompilierungs Konstanten:  
  
|\_MYTYPE|\_MYAPPLICATIONTYPE|\_MYCOMPUTERTYPE|\_MYFORMS|\_MYUSERTYPE|\_MYWEBSERVICES|  
|--------------|-------------------------|----------------------|---------------|------------------|---------------------|  
|TS|TS|Windows|Nicht definiert|Windows|true|  
|Zollunion|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|  
|Leer|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|Nicht definiert|  
|Kamera|Nicht definiert|Kamera|false|Kamera|false|  
|WebControl|Nicht definiert|Kamera|false|Kamera|true|  
|"Windows" oder ""|Windows|Windows|Nicht definiert|Windows|true|  
|WindowsForms|WindowsForms|Windows|true|Windows|true|  
|"Windowsformswithcustomsubmain"|TS|Windows|true|Windows|true|  
  
 Standardmäßig werden nicht definierte Konstanten für bedingte Kompilierung in `FALSE` aufgelöst. Sie können Werte für die nicht definierten Konstanten angeben, wenn Sie das Projekt kompilieren, um das Standardverhalten zu überschreiben.  
  
> [!NOTE]
> Wenn `_MYTYPE` auf "Custom" festgelegt ist, enthält das Projekt den `My`-Namespace, enthält jedoch keine-Objekte. Wenn Sie jedoch `_MYTYPE` auf "Empty" festlegen, wird verhindert, dass der Compiler den `My`-Namespace und seine Objekte hinzufügt.  
  
 Diese Tabelle beschreibt die Auswirkungen der vordefinierten Werte der `_MY` Kompilierungs Konstanten.  
  
|Konstante|Bedeutung|  
|--------------|-------------|  
|`_MYAPPLICATIONTYPE`|Aktiviert `My.Application`, wenn die Konstante "Console", "Windows" oder "WindowsForms" ist:<br /><br /> -Die Konsolenversion wird von <xref:Microsoft.VisualBasic.ApplicationServices.ConsoleApplicationBase> abgeleitet. und verfügt über weniger Mitglieder als die "Windows"-Version.<br />-Die "Windows"-Version wird von <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase> abgeleitet und verfügt über weniger Mitglieder als die Version "Windows Forms".<br />-Die Version von "WindowsForms" von `My.Application` wird von <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> abgeleitet. Wenn die `TARGET` Konstante als "winexe" definiert ist, enthält die-Klasse eine `Sub Main`-Methode.|  
|`_MYCOMPUTERTYPE`|Aktiviert `My.Computer`, wenn die Konstante "Web" oder "Windows" ist:<br /><br /> -Die "Web"-Version wird von <xref:Microsoft.VisualBasic.Devices.ServerComputer> abgeleitet und verfügt über weniger Mitglieder als die "Windows"-Version.<br />-Die "Windows"-Version von `My.Computer` wird von <xref:Microsoft.VisualBasic.Devices.Computer> abgeleitet.|  
|`_MYFORMS`|Aktiviert `My.Forms`, wenn die Konstante `TRUE` ist.|  
|`_MYUSERTYPE`|Aktiviert `My.User`, wenn die Konstante "Web" oder "Windows" ist:<br /><br /> -Die "Web"-Version von `My.User` wird der Benutzeridentität der aktuellen HTTP-Anforderung zugeordnet.<br />-Die "Windows"-Version von `My.User` wird dem aktuellen Prinzipal des Threads zugeordnet.|  
|`_MYWEBSERVICES`|Aktiviert `My.WebServices`, wenn die Konstante `TRUE` ist.|  
|`_MYTYPE`|Aktiviert `My.Log`, `My.Request` und `My.Response`, wenn die Konstante "Web" ist.|  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.Logging.Log>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [Merkmale von "My" auf Grundlage des Projekttyps](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
- [Bedingte Kompilierung](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
- [-define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
- [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.Request-Objekt](../../../visual-basic/language-reference/objects/my-request-object.md)
- [My.Response-Objekt](../../../visual-basic/language-reference/objects/my-response-object.md)
- [My.WebServices-Objekt](../../../visual-basic/language-reference/objects/my-webservices-object.md)
