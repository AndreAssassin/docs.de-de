---
title: -errorreport (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /errorreport
helpviewer_keywords:
- -errorreport compiler option [C#]
- errorreport compiler option [C#]
- /errorreport compiler option [C#]
ms.assetid: bd0e7493-b79d-4369-9c3f-ba26ebdfbedf
ms.openlocfilehash: 4797f35a3738955f620fad7a93f8695685d21057
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345091"
---
# <a name="-errorreport-c-compiler-options"></a>-errorreport (C#-Compileroptionen)
Diese Option bietet eine einfache Möglichkeit, einen internen C#-Compilerfehler an Microsoft zu melden.  
  
> [!NOTE]
>  Unter Windows Vista und Windows Server 2008 überschreiben die Einstellungen für die Fehlerberichterstattung, die Sie für Visual Studio festgelegt haben, nicht die Einstellungen, die über Windows-Fehlerberichterstattung (WER) festgelegt wurden. WER-Einstellungen haben immer Vorrang vor Einstellungen für Fehlerberichterstattung in Visual Studio.  
  
## <a name="syntax"></a>Syntax  
  
```console  
-errorreport:{ none | prompt | queue | send }  
```  
  
## <a name="arguments"></a>Argumente  
 **Keine**  
 Berichte zu internen Compilerfehlern werden nicht gesammelt oder an Microsoft gesendet.  
  
 **Eingabeaufforderung**  
 Sie werden aufgefordert, einen Bericht zu senden, wenn Sie einen internen Compilerfehler empfangen. **Aufforderung** ist die Standardeinstellung beim Kompilieren einer Anwendung in der Entwicklungsumgebung.  
  
 **Warteschlange**  
 Der Fehlerbericht wird in die Warteschlange gesetzt. Wenn Sie sich mit Administratoranmeldeinformationen anmelden, können Sie alle Fehler seit dem letzten Login melden. Sie werden nicht aufgefordert, Fehlerberichte mehr als einmal alle drei Tage zu senden. **Warteschlange** ist die Standardeinstellung, wenn Sie eine Anwendung in der Befehlszeile kompilieren.  
  
 **send**  
 Sendet Berichte über interne Compilerfehler automatisch an Microsoft. Wenn Sie diese Option aktivieren, müssen Sie zuerst der Richtlinie zur Datensammlung von Microsoft zustimmen. Beim ersten Mal, wenn Sie **-errorreport:send** auf einem Computer angeben, wird eine Compilermeldung Sie auf eine Website verweisen, die die Microsoft-Richtlinie zur Datensammlung enthält.  
    
## <a name="remarks"></a>Anmerkungen  
 Ein interner Compilerfehler (ICE) entsteht, wenn der Compiler eine Quellcodedatei nicht verarbeiten kann. Tritt ein ICE auf, erzeugt der Compiler keine Ausgabedatei oder eine hilfreiche Diagnose, die Sie verwenden können, um Ihren Code zu beheben.  
  
 In früheren Versionen wurden Sie beim Auftreten eines ICE aufgefordert, sich an den Microsoft-Produktsupport zu wenden, um das Problem zu melden. Mithilfe von **-errorreport** können Sie dem Visual C#-Team ICE-Informationen bereitstellen. Die Fehlerberichte können dabei helfen, zukünftige Compilerversionen zu verbessern.  
  
 Die Fähigkeit eines Benutzers zum Senden von Berichten hängt vom Computer und den Benutzerberechtigungen ab.  
  
 Weitere Informationen zum Fehlerdebugger finden Sie unter [Beschreibung des Dr. Watson für Windows (Drwtsn32.exe)-Tool](https://support.microsoft.com/help/308538/description-of-the-dr--watson-for-windows-drwtsn32-exe-tool).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1. Öffnen Sie die **Eigenschaftenseite** des Projekts. Weitere Informationen finden Sie unter [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2. Klicken Sie auf die Eigenschaftenseite **Erstellen**.  
  
3. Klicken Sie auf die Schaltfläche **Erweitert** .  
  
4. Ändern Sie die Eigenschaft **Bericht für internen Compilerfehler**.  
  
 Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.ErrorReport%2A>.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md)
