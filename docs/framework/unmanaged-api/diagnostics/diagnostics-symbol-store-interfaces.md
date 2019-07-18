---
title: Diagnosesymbolspeicher-Schnittstellen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- diagnostics symbol store interfaces [.NET Framework]
- interfaces [.NET Framework], diagnostics symbol store
- unmanaged interfaces [.NET Framework], diagnostics symbol store
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: f96987d5-e6a5-478b-ac5e-302e16545cce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6fca7359888b8b73b2e1cf709ab708d71abf0db6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787893"
---
# <a name="diagnostics-symbol-store-interfaces"></a>Diagnosesymbolspeicher-Schnittstellen
In diesem Thema wird beschrieben, die nicht verwalteten Schnittstellen, mit denen einen Compiler Symbolinformationen für die Verwendung von einem Debugger zu generieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [IBindingDisplay-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/ibindingdisplay-interface.md)  
 Enthält Methoden, die aktuelle Bindungsinformationen über die ausgeführte Anwendung anzuzeigen.  
  
 [IDebugAutoAttach-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/idebugautoattach-interface.md)  
 Definiert die Schnittstelle an, für eine AutoAttach-Debuggers.  
  
 [INotifyConnection2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifyconnection2-interface.md)  
 Deklariert Methoden, die für das Registrieren und Aufheben der Registrierung eine Benachrichtigung Verbindungsquelle.  
  
 [INotifySink2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifysink2-interface.md)  
 Deklariert Methoden, die für die Senke-Benachrichtigung.  
  
 [INotifySource2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/inotifysource2-interface.md)  
 Deklariert eine Methode zum Festlegen von Benachrichtigung filtern.  
  
 [ISymENCUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymencunmanagedmethod-interface.md)  
 Enthält Informationen für die Funktion bearbeiten und fortfahren.  
  
 [ISymUnmanagedAsyncMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)  
 Diese Schnittstelle ist die Ergänzung lesen [ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md).  
  
 [ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)  
 Ermöglicht die Definition der optionalen Async-Methodeninformationen pro methodensymbol. Müssen mit einer geöffneten-Methode verwenden (d. h. zwischen den Aufrufen der [OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)und [CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)).  
  
 [ISymUnmanagedBinder-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-interface.md)  
 Stellt einen Symbolbinder für nicht verwalteten Code dar.  
  
 [ISymUnmanagedBinder2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)  
 Stellt einen Symbolbinder für nicht verwalteten Code dar, und erweitert die `ISymUnmanagedBinder` Schnittstelle.  
  
 [ISymUnmanagedBinder3-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)  
 Stellt einen Symbolbinder für nicht verwalteten Code dar, und erweitert die `ISymUnmanagedBinder` Schnittstelle.  
  
 [ISymUnmanagedConstant-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 Bietet Zugriff auf nicht verwalteten Konstanten.  
  
 [ISymUnmanagedDispose-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)  
 Gibt nicht verwaltete Ressourcen frei.  
  
 [ISymUnmanagedDocument-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)  
 Stellt ein Dokument dar, auf das von einem Symbolspeicher verwiesen wird.  
  
 [ISymUnmanagedDocumentWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocumentwriter-interface.md)  
 Stellt Methoden zum Schreiben in ein Dokument bereit, auf das ein Symbolspeicher verweist.  
  
 [ISymUnmanagedENCUpdate-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)  
 Stellt Methoden für die Funktion bearbeiten und fortfahren.  
  
 [ISymUnmanagedMethod-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)  
 Stellt eine Methode in den Symbolspeicher.  
  
 [ISymUnmanagedNamespace-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)  
 Stellt einen Namespace dar.  
  
 [ISymUnmanagedReader-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)  
 Stellt einen Symbolreader den Zugriff auf Dokumente, Methoden und Variablen in einem Symbolspeicher dar.  
  
 [ISymUnmanagedReader2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader2-interface.md)  
 Ruft ein Methodenobjekt des Symbolreaders erhält ein Methodentoken und eine Versionsnummer für bearbeiten und kopieren.  
  
 [ISymUnmanagedReaderSymbolSearchInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)  
 Bietet Methoden, die Symbolinformationen für die Suche zu erhalten.  
  
 [ISymUnmanagedScope-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode dar.  
  
 [ISymUnmanagedScope2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope2-interface.md)  
 Stellt einen lexikalischen Gültigkeitsbereich innerhalb einer Methode und erweitert die `ISymUnmanagedScope` Schnittstelle mit Methoden, die Informationen zu definierten Konstanten innerhalb des Bereichs abrufen...  
  
 [ISymUnmanagedSourceServerModule-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsourceservermodule-interface.md)  
 Quelldaten für die Server bereitstellt für ein Modul.  
  
 [ISymUnmanagedSymbolSearchInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)  
 Enthält Methoden, die Informationen zu den Suchpfad zu erhalten.  
  
 [ISymUnmanagedVariable-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 Stellt eine Variable ein, z. B. ein Parameter, eine lokale Variable oder ein Feld dar.  
  
 [ISymUnmanagedWriter-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 Stellt einen Symbolwriter dar und bietet Methoden, um Dokumente, Sequenzpunkte, lexikalischen Gültigkeitsbereiche und Variablen zu definieren.  
  
 [ISymUnmanagedWriter2-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 Stellt einen Symbolwriter dar und bietet Methoden, um Dokumente, Sequenzpunkte, lexikalischen Gültigkeitsbereiche und Variablen zu definieren. Erweitert die `ISymUnmanagedWriter` Schnittstelle.  
  
 [ISymUnmanagedWriter3-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)  
 Stellt einen Symbolwriter dar und bietet Methoden, um Dokumente, Sequenzpunkte, lexikalischen Gültigkeitsbereiche und Variablen zu definieren. Erweitert die `ISymUnmanagedWriter` Schnittstelle.  
  
 [ISymUnmanagedWriter4-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)  
 ISymUnmanagedWriter4-Schnittstelle.  
  
 [ISymUnmanagedWriter5-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)  
 ISymUnmanagedWriter5-Schnittstelle.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Diagnosesymbolspeicher-Enumerationen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-enumerations.md)  
  
 [Diagnosesymbolspeicher-Strukturen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-structures.md)  
  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
