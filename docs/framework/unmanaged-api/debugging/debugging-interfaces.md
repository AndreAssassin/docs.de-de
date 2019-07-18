---
title: Debugschnittstellen
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff589285d81a3febf887bba976b62a9ae4a573c8
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025946"
---
# <a name="debugging-interfaces"></a>Debugschnittstellen
In diesem Abschnitt werden die unverwalteten Schnittstellen beschrieben, die das Debuggen eines Programms behandeln, das in der Common Language Runtime (CLR) ausgeführt wird.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [ICLRDataEnumMemoryRegions-Schnittstelle](iclrdataenummemoryregions-interface.md)\
 Stellt eine Methode bereit, um Speicherbereiche aufzulisten, die von Aufrufern angegeben werden.  
  
 [ICLRDataEnumMemoryRegionsCallback-Schnittstelle](iclrdataenummemoryregionscallback-interface.md)\
 Stellt eine Rückrufmethode für `EnumMemoryRegions` bereit, um an den Debugger das Ergebnis eines Versuchs zu melden, einen angegebenen Speicherbereich aufzulisten.  
  
 [ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)\
 Stellt Methoden für die Interaktion mit einem Ziel-CLR-Prozess bereit.  
  
 [ICLRDataTarget2-Schnittstelle](iclrdatatarget2-interface.md)\
 Eine Unterklasse von `ICLRDataTarget`, wird von der Datenzugriffsdienstebene zum Bearbeiten virtueller Speicherbereiche im Zielprozess verwendet.  
  
 [ICLRDataTarget3-Schnittstelle](iclrdatatarget3-interface.md)\
 Eine Unterklasse von [ICLRDataTarget2](iclrdatatarget2-interface.md) , Zugriff auf Informationen über die Ausnahme bereitstellt.  
  
 [ICLRDebugging-Schnittstelle](iclrdebugging-interface.md)\
 Stellt Methoden bereit, die das Laden und Entladen von Modulen für Debuggingzwecke behandeln.  
  
 [ICLRDebuggingLibraryProvider-Schnittstelle](iclrdebugginglibraryprovider-interface.md)\
 Enthält die [ProvideLibrary-Methode](iclrdebugginglibraryprovider-providelibrary-method.md) Methode, die eine Bibliotheksanbieter-Rückrufschnittstelle, die common Language Runtime versionsspezifische Debugbibliotheken abruft zu suchen und zu laden, auf Anforderung ermöglicht.  
  
 [ICLRMetadataLocator-Schnittstelle](iclrmetadatalocator-interface.md)\
 Schnittstelle, mit der die Datenzugriffsdienstebene Metadaten von Assemblys in einem Zielprozess sucht.  
  
 [ICorDebug-Schnittstelle](icordebug-interface.md)\
 Stellt Methoden bereit, mit denen Entwickler Anwendungen in der CLR-Umgebung debuggen können.  
  
 [ICorDebugAppDomain-Schnittstelle](icordebugappdomain-interface.md)\
 Stellt Methoden zum Debuggen von Anwendungsdomänen bereit.  
  
 [ICorDebugAppDomain2-Schnittstelle](icordebugappdomain2-interface.md)\
 Stellt Methoden bereit, um mit Arrays, Zeigern, Funktionszeigern und ByRef-Typen zu arbeiten. Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`-Schnittstelle.  
  
 [ICorDebugAppDomain3-Schnittstelle](icordebugappdomain3-interface.md)\
 Stellt Methoden zum Arbeiten mit der Windows-Runtime-Typen in einer Anwendungsdomäne bereit. Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`- und `ICorDebugAppDomain2`-Schnittstellen.  
  
 [ICorDebugAppDomain4-Schnittstelle](icordebugappdomain4-interface.md)\
 Erweitert logisch die [ICorDebugAppDomain](icordebugappdomain-interface.md) Schnittstelle, um ein verwaltetes Objekt über einen COM callable Wrapper abzurufen.  
  
 [ICorDebugAppDomainEnum-Schnittstelle](icordebugappdomainenum-interface.md)\
 Stellt eine Methode bereit, die eine angegebene Anzahl von `ICorDebugAppDomain`-Werten zurückgibt, beginnend mit der nächsten Position in der Enumeration.  
  
 [ICorDebugArrayValue-Schnittstelle](icordebugarrayvalue-interface.md)\
 Eine Unterklasse von `ICorDebugHeapValue`, die ein eindimensionales oder mehrdimensionales Array darstellt.  
  
 [ICorDebugAssembly-Schnittstelle](icordebugassembly-interface.md)\
 Stellt eine Assembly dar.  
  
 [ICorDebugAssembly2-Schnittstelle](icordebugassembly2-interface.md)\
 Stellt eine Assembly dar. Diese Schnittstelle ist eine Erweiterung der `ICorDebugAssembly`-Schnittstelle.  
  
 [ICorDebugAssembly3-Schnittstelle](icordebugassembly3-interface.md)\
 Erweitert logisch die [ICorDebugAssembly](icordebugassembly-interface.md) Schnittstelle, um die Container-Assemblys und der darin enthaltenen Assemblys unterstützen. **Nur .NET Native verfügbar.**  
  
 [ICorDebugAssemblyEnum-Schnittstelle](icordebugassemblyenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugAssembly`-Arrays auf.  
  
 [ICorDebugBlockingObjectEnum-Schnittstelle](icordebugblockingobjectenum-interface.md)\
 Stellt einen Enumerator bereit, eine Liste der [CorDebugBlockingObject](cordebugblockingobject-structure.md) Strukturen.  
  
 [ICorDebugBoxValue-Schnittstelle](icordebugboxvalue-interface.md)\
 Eine Unterklasse von `ICorDebugHeapValue`, die ein geschachteltes Wertklassenobjekt darstellt.  
  
 [ICorDebugBreakpoint-Schnittstelle](icordebugbreakpoint-interface.md)\
 Stellt einen Haltepunkt in einer Funktion oder einen Beobachtungspunkt für einen Wert dar.  
  
 [ICorDebugBreakpointEnum-Schnittstelle](icordebugbreakpointenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugBreakpoint`-Arrays auf.  
  
 [ICorDebugChain-Schnittstelle](icordebugchain-interface.md)\
 Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.  
  
 [ICorDebugChainEnum-Schnittstelle](icordebugchainenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugChain`-Arrays auf.  
  
 [ICorDebugClass-Schnittstelle](icordebugclass-interface.md)\
 Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann. Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.  
  
 [ICorDebugClass2-Schnittstelle](icordebugclass2-interface.md)\
 Stellt eine generische Klasse oder eine Klasse mit einem Methodenparameter des Typs <xref:System.Type> dar. Diese Schnittstelle erweitert `ICorDebugClass`.  
  
 [ICorDebugCode-Schnittstelle](icordebugcode-interface1.md)\
 Stellt ein Segment von Microsoft Intermediate Language (MSIL)-Code oder nativem Code dar.  
  
 [ICorDebugCode2-Schnittstelle](icordebugcode2-interface.md)\
 Stellt Methoden bereit, die die Fähigkeiten von `ICorDebugCode` erweitern.  
  
 [ICorDebugCode3-Schnittstelle](icordebugcode3-interface.md)\
 Stellt eine Methode, die erweitert [ICorDebugCode](icordebugcode-interface1.md) und [ICorDebugCode2](icordebugcode2-interface.md) um Informationen zu einem verwalteten Rückgabewert bereitzustellen.  
  
 [ICorDebugCode4-Schnittstelle](icordebugcode4-interface.md)\
 Stellt eine Methode, die einen Debugger zum Aufzählen von die lokalen Variablen und Argumente in einer Funktion ermöglicht.  
  
 [ICorDebugCodeEnum-Schnittstelle](icordebugcodeenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugCode`-Arrays auf.  
  
 [ICorDebugComObjectValue-Schnittstelle](icordebugcomobjectvalue-interface.md)\
 Stellt Methoden bereit, um zwischengespeicherte Schnittstellenobjekte abzurufen.  
  
 [ICorDebugContext-Schnittstelle](icordebugcontext-interface.md)\
 Stellt ein Kontextobjekt dar. Diese Schnittstelle wurde noch nicht implementiert.  
  
 [ICorDebugController-Schnittstelle](icordebugcontroller-interface.md)\
 Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.  
  
 [ICorDebugDataTarget-Schnittstelle](icordebugdatatarget-interface.md)\
 Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.  
  
 [ICorDebugDataTarget2-Schnittstelle](icordebugdatatarget2-interface.md)\
 Erweitert logisch die [ICorDebugDataTarget](icordebugdatatarget-interface.md) Schnittstelle. **Nur .NET Native verfügbar.**  
  
 [ICorDebugDataTarget3-Schnittstelle](icordebugdatatarget3-interface.md)\
 Erweitert logisch die [ICorDebugDataTarget](icordebugdatatarget-interface.md) Schnittstelle, um Informationen zu geladenen Modulen bereitzustellen. **Nur .NET Native verfügbar.**  
  
 [ICorDebugDebugEvent-Schnittstelle](icordebugdebugevent-interface.md)\
 Definiert die Basisschnittstelle, von der alle `ICorDebug` Debug-Ereignisse abgeleitet werden. **Nur .NET Native verfügbar.**  
  
 [ICorDebugEditAndContinueErrorInfo-Schnittstelle](icordebugeditandcontinueerrorinfo-interface.md)\
 Veraltet. Verwenden Sie diese Schnittstelle nicht.  
  
 [ICorDebugEditAndContinueSnapshot-Schnittstelle](icordebugeditandcontinuesnapshot-interface.md)\
 Veraltet. Verwenden Sie diese Schnittstelle nicht.  
  
 [ICorDebugEnum-Schnittstelle](icordebugenum-interface1.md)\
 Dient als abstrakte Basisschnittstelle für das Debuggen von Enumeratoren.  
  
 [ICorDebugErrorInfoEnum-Schnittstelle](icordebugerrorinfoenum-interface.md)\
 Veraltet. Verwenden Sie diese Schnittstelle nicht.  
  
 [ICorDebugEval-Schnittstelle](icordebugeval-interface.md)\
 Stellt Methoden bereit, mit denen der Debugger Code innerhalb des Kontexts des gedebuggten Codes ausführen kann.  
  
 [ICorDebugEval2-Schnittstelle](icordebugeval2-interface.md)\
 Erweitert `ICorDebugEval`, um generische Typen zu unterstützen.  
  
 [ICorDebugExceptionDebugEvent-Schnittstelle](icordebugexceptiondebugevent-interface.md)\
 Erweitert die [ICorDebugDebugEvent](icordebugdebugevent-interface.md) Schnittstelle, um die Unterstützung von Ausnahmeereignissen. **Nur .NET Native verfügbar.**  
  
 [ICorDebugExceptionObjectCallStackEnum-Schnittstelle](icordebugexceptionobjectcallstackenum-interface.md)\
 Stellt einen Enumerator für Aufruflisteninformationen bereit, die in einem Ausnahmeobjekt eingebettet sind.  
  
 [ICorDebugExceptionObjectValue-Schnittstelle](icordebugexceptionobjectvalue-interface.md)\
 Erweitert die [ICorDebugObjectValue](icordebugobjectvalue-interface.md) Schnittstelle, um Stapelüberwachungsinformationen von einem verwalteten Ausnahmeobjekt bereitzustellen.  
  
 [ICorDebugFrame-Schnittstelle](icordebugframe-interface.md)\
 Stellt einen Rahmen auf dem aktuellen Stapel dar.  
  
 [ICorDebugFrameEnum-Schnittstelle](icordebugframeenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugFrame`-Arrays auf.  
  
 [ICorDebugFunction-Schnittstelle](icordebugfunction-interface1.md)\
 Stellt eine verwaltete Funktion oder Methode dar.  
  
 [ICorDebugFunction2-Schnittstelle](icordebugfunction2-interface.md)\
 Erweitert `ICorDebugFunction` logisch, um schrittweises Nur mein Code-Debuggen zu unterstützen.  
  
 [ICorDebugFunction3-Schnittstelle](icordebugfunction3-interface.md)\
 Erweitert logisch die [ICorDebugFunction](icordebugfunction-interface1.md) Schnittstelle, um Zugriff auf Code aus einer ReJIT-Anfrage zu bieten.  
  
 [ICorDebugFunctionBreakpoint-Schnittstelle](icordebugfunctionbreakpoint-interface.md)\
 Erweitert `ICorDebugBreakpoint`, um Haltepunkte innerhalb von Funktionen zu unterstützen.  
  
 [ICorDebugGCReferenceEnum-Schnittstelle](icordebuggcreferenceenum-interface.md)\
 Stellt einen Enumerator für Objekte bereit, die der Garbage Collection übergeben werden.  
  
 [ICorDebugGenericValue-Schnittstelle](icordebuggenericvalue-interface.md)\
 Eine Unterklasse von `ICorDebugValue`, die für alle Werte gilt. Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.  
  
 [ICorDebugGuidToTypeEnum-Schnittstelle](icordebugguidtotypeenum-interface.md)\
 Stellt einen Enumerator für ein Objekt bereit, das GUIDs und die entsprechenden `ICorDebugType`-Objekte zuordnet.  
  
 [ICorDebugHandleValue-Schnittstelle](icordebughandlevalue-interface.md)\
 Eine Unterklasse von `ICorDebugReferenceValue`, die einen Verweiswert darstellt, für den der Debugger einen Handle zur Garbage Collection erstellt hat.  
  
 [ICorDebugHeapEnum-Schnittstelle](icordebugheapenum-interface.md)\
 Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit.  
  
 [ICorDebugHeapSegmentEnum-Schnittstelle](icordebugheapsegmentenum-interface.md)\
 Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit.  
  
 [ICorDebugHeapValue-Schnittstelle](icordebugheapvalue-interface.md)\
 Eine Unterklasse von `ICorDebugValue`, die ein Objekt darstellt, das vom Garbage Collector der CLR gesammelt wurde.  
  
 [ICorDebugHeapValue2-Schnittstelle](icordebugheapvalue2-interface1.md)\
 Eine Erweiterung von `ICorDebugHeapValue`, die Laufzeithandles unterstützt.  
  
 [ICorDebugHeapValue3-Schnittstelle](icordebugheapvalue3-interface.md)\
 Macht die Bildschirmsperreigenschaften von Objekten verfügbar.  
  
 [ICorDebugILCode-Schnittstelle](icordebugilcode-interface.md)\
 Stellt ein Segment aus Intermediate Language (IL)-Code dar.  
  
 [ICorDebugILCode2-Schnittstelle](icordebugilcode2-interface.md)\
 Erweitert logisch die [ICorDebugILCode](icordebugilcode-interface.md) -Schnittstelle um Methoden, die das Token für die lokale Variablensignatur von einer Funktion zurückgeben und, Zuordnen des Profilers instrumentierte intermediate Language (IL) offsets ursprünglichen IL-Methode versetzt.  
  
 [ICorDebugILFrame-Schnittstelle](icordebugilframe-interface.md)\
 Stellt einen Stapelrahmen des MSIL-Codes dar.  
  
 [ICorDebugILFrame2-Schnittstelle](icordebugilframe2-interface.md)\
 Eine logische Erweiterung von `ICorDebugILFrame`.  
  
 [ICorDebugILFrame3-Schnittstelle](icordebugilframe3-interface.md)\
 Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt.  
  
 [ICorDebugILFrame4-Schnittstelle](icordebugilframe4-interface.md)\
 Bietet Methoden, mit denen Sie auf lokale Variablen und Code in einem Stapelrahmen aus Intermediate Language (IL)-Code zugreifen können. Ein Parameter legt fest, ob der Debugger Zugang zu Variablen und Code erhält, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden.  
  
 [ICorDebugInstanceFieldSymbol-Schnittstelle](icordebuginstancefieldsymbol-interface.md)\
 Stellt die Debugsymbolinformationen für ein Instanzfeld dar. **Nur .NET Native verfügbar.**  
  
 [ICorDebugInternalFrame-Schnittstelle](icordebuginternalframe-interface.md)\
 Identifiziert Rahmentypen für den Debugger.  
  
 [ICorDebugInternalFrame2-Schnittstelle](icordebuginternalframe2-interface.md)\
 Enthält Informationen zu internen Frames, u. a. Stapeladresse und Position in Bezug auf [ICorDebugFrame](icordebugframe-interface.md) Objekte.  
  
 [ICorDebugLoadedModule-Schnittstelle](icordebugloadedmodule-interface.md)\
 Stellt Informationen zu einem geladenen Modul bereit. **Nur .NET Native verfügbar.**  
  
 [ICorDebugManagedCallback-Schnittstelle](icordebugmanagedcallback-interface.md)\
 Stellt Methoden zum Verarbeiten von Debuggerrückrufen zur Verfügung.  
  
 [ICorDebugManagedCallback2-Schnittstelle](icordebugmanagedcallback2-interface.md)\
 Stellt Methoden bereit, um Debugger-Ausnahmebehandlung und Assistenten für verwaltetes Debuggen (MDA) zu unterstützen. `ICorDebugManagedCallback2` ist eine logische Erweiterung von `ICorDebugManagedCallback`.  
  
 [ICorDebugManagedCallback3-Schnittstelle](icordebugmanagedcallback3-interface.md)\
 Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.  
  
 [ICorDebugMDA-Schnittstelle](icordebugmda-interface.md)\
 Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.  
  
 [ICorDebugMemoryBuffer-Schnittstelle](icordebugmemorybuffer-interface.md)\
 Stellt einen In-Memory-Puffer dar. **Nur .NET Native verfügbar.**  
  
 [ICorDebugMergedAssemblyRecord-Schnittstelle](icordebugmergedassemblyrecord-interface.md)\
 Enthält Informationen zu einer zusammengeführten Assembly. **Nur .NET Native verfügbar.**  
  
 [ICorDebugMetaDataLocator-Schnittstelle](icordebugmetadatalocator-interface.md)\
 Stellt Metadateninformationen für den Debugger bereit.  
  
 [ICorDebugModule-Schnittstelle](icordebugmodule-interface.md)\
 Stellt ein CLR-Modul dar, das entweder eine ausführbare Datei oder eine Dynamic-Link Library (DLL) ist.  
  
 [ICorDebugModule2-Schnittstelle](icordebugmodule2-interface.md)\
 Fungiert als logische Erweiterung von `ICorDebugModule`.  
  
 [ICorDebugModule3-Schnittstelle](icordebugmodule3-interface.md)\
 Erstellt einen Symbolreader für ein dynamisches Modul.  
  
 [ICorDebugModuleBreakpoint-Schnittstelle](icordebugmodulebreakpoint-interface.md)\
 Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Module zu ermöglichen.  
  
 [ICorDebugModuleDebugEvent-Schnittstelle](icordebugmoduledebugevent-interface.md)\
 Erweitert die [ICorDebugDebugEvent](icordebugdebugevent-interface.md) -Schnittstelle zur Unterstützung der Ereignisse auf Modulebene. **Nur .NET Native verfügbar.**  
  
 [ICorDebugModuleEnum-Schnittstelle](icordebugmoduleenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugModule`-Arrays auf.  
  
 [ICorDebugMutableDataTarget-Schnittstelle](icordebugmutabledatatarget-interface.md)\
 Erweitert die [ICorDebugDataTarget](icordebugdatatarget-interface.md) Schnittstelle, um änderbare Datenziele zu unterstützen.  
  
 [ICorDebugNativeFrame-Schnittstelle](icordebugnativeframe-interface.md)\
 Eine spezielle Implementierung von `ICorDebugFrame`, die für systemeigene Rahmen verwendet wird.  
  
 [ICorDebugNativeFrame2-Schnittstelle](icordebugnativeframe2-interface.md)\
 Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.  
  
 [ICorDebugObjectEnum-Schnittstelle](icordebugobjectenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet Objektarrays anhand ihrer relativen virtuellen Adresse (RVA) auf.  
  
 [ICorDebugObjectValue-Schnittstelle](icordebugobjectvalue-interface.md)\
 Eine Unterklasse von `ICorDebugValue`, die einen Wert darstellt, der ein Objekt enthält.  
  
 [ICorDebugObjectValue2-Schnittstelle](icordebugobjectvalue2-interface.md)\
 Erweitert `ICorDebugObjectValue`, um Vererbung und Überschreibungen zu unterstützen.  
  
 [ICorDebugProcess-Schnittstelle](icordebugprocess-interface.md)\
 Stellt einen Prozess dar, der verwalteten Code ausführt.  
  
 [ICorDebugProcess2-Schnittstelle](icordebugprocess2-interface1.md)\
 Eine logische Erweiterung von `ICorDebugProcess`.  
  
 [ICorDebugProcess3-Schnittstelle](icordebugprocess3-interface.md)\
 Steuert benutzerdefinierte Debuggerbenachrichtigungen.

 [ICorDebugProcess4-Schnittstelle](icordebugprocess4-interface.md)\
 Bietet Unterstützung für die Out-of ausführungssteuerung Prozess.
  
 [ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)\
 Erweitert die [ICorDebugProcess](icordebugprocess-interface.md) -Schnittstelle zur Unterstützung von Zugriff auf den verwalteten Heap, um Informationen zum Garbagecollection verwalteten Objekte bereitzustellen und zu bestimmen, ob ein Debugger Bilder aus der Anwendung lädt die lokale Cache für systemeigene Images.  
  
 [ICorDebugProcess6-Schnittstelle](icordebugprocess6-interface.md)\
 Erweitert logisch die [ICorDebugProcess](icordebugprocess-interface.md) Schnittstelle zum Aktivieren von Funktionen wie z. B. der Decodierung verwalteter Debug-Ereignisse, die in systemeigenen Ausnahme-Debug-Ereignisse und das Teilen virtueller Module codiert sind. **Nur .NET Native verfügbar.**  
  
 [ICorDebugProcess7-Schnittstelle](icordebugprocess7-interface.md)\
 Bietet eine Methode, die den Debugger so konfiguriert, dass speicherinterne Metadatenaktualisierungen im Zielprozess behandelt werden.  
  
 [ICorDebugProcess8-Schnittstelle](icordebugprocess8-interface.md)\
 Erweitert logisch die [ICorDebugProcess](icordebugprocess-interface.md) Schnittstelle zum Aktivieren oder deaktivieren bestimmte Arten von [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) ausnahmerückrufen.  
  
 [ICorDebugProcessEnum-Schnittstelle](icordebugprocessenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugProcess`-Arrays auf.  
  
 [ICorDebugReferenceValue-Schnittstelle](icordebugreferencevalue-interface.md)\
 Eine Unterklasse von `ICorDebugValue`, die Verweistypen unterstützt.  
  
 [ICorDebugRegisterSet-Schnittstelle](icordebugregisterset-interface.md)\
 Stellt die Register dar, die auf dem Computer verfügbar sind, auf dem der Code derzeit ausgeführt wird.  
  
 [ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)\
 Erweitert die Fähigkeiten von `ICorDebugRegisterSet` für Hardwareplattformen mit mehr als 64 Registern.  
  
 [ICorDebugRemote-Schnittstelle](icordebugremote-interface.md)\
 Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.  
  
 [ICorDebugRemoteTarget-Schnittstelle](icordebugremotetarget-interface.md)\
 Stellt Methoden bereit, die Ihnen ermöglichen, Silverlight-basierte Anwendungen in der CLR-Umgebung debuggen zu können.  
  
 [ICorDebugRuntimeUnwindableFrame-Schnittstelle](icordebugruntimeunwindableframe-interface.md)\
 Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.  
  
 [ICorDebugStackWalk-Schnittstelle](icordebugstackwalk-interface.md)\
 Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.  
  
 [ICorDebugStaticFieldSymbol-Schnittstelle](icordebugstaticfieldsymbol-interface.md)\
 Stellt die Debugsymbolinformationen für ein statisches Feld dar. **Nur .NET Native verfügbar.**  
  
 [ICorDebugStepper-Schnittstelle](icordebugstepper-interface.md)\
 Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.  
  
 [ICorDebugStepper2-Schnittstelle](icordebugstepper2-interface1.md)\
 Bietet Unterstützung für Nur mein Code-Debuggen.  
  
 [ICorDebugStepperEnum-Schnittstelle](icordebugstepperenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugStepper`-Arrays auf.  
  
 [ICorDebugStringValue-Schnittstelle](icordebugstringvalue-interface.md)\
 Eine Unterklasse von `ICorDebugHeapValue`, die für Zeichenfolgenwerte gilt.  
  
 [ICorDebugSymbolProvider-Schnittstelle](icordebugsymbolprovider-interface.md)\
 Stellt Methoden bereit, die zum Abrufen von Debugsymbolinformationen verwendet werden können. **Nur .NET Native verfügbar.**  
  
 [ICorDebugSymbolProvider2-Schnittstelle](icordebugsymbolprovider2-interface.md)\
 Erweitert logisch die [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen. **Nur .NET Native verfügbar.**  
  
 [ICorDebugThread-Schnittstelle](icordebugthread-interface.md)\
 Stellt einen Thread in einem Prozess dar. Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.  
  
 [ICorDebugThread2-Schnittstelle](icordebugthread2-interface.md)\
 Fungiert als logische Erweiterung von `ICorDebugThread`.  
  
 [ICorDebugThread3-Schnittstelle](icordebugthread3-interface.md)\
 Stellt den Einstiegspunkt für die [ICorDebugStackWalk](icordebugstackwalk-interface.md) und entsprechende Schnittstellen.  
  
 [ICorDebugThread4-Schnittstelle](icordebugthread4-interface.md)\
 Stellt Informationen zur Threadblockierung bereit.  
  
 [ICorDebugThreadEnum-Schnittstelle](icordebugthreadenum-interface1.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugThread`-Arrays auf.  
  
 [ICorDebugType-Schnittstelle](icordebugtype-interface.md)\
 Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann. Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.  
  
 [ICorDebugType2-Schnittstelle](icordebugtype2-interface.md)\
 Erweitert die [ICorDebugType](icordebugtype-interface.md) Schnittstelle, um die Typ-ID von einem Basistyp oder einen komplexen Typ auf (Benutzerdefiniert) abzurufen.  
  
 [ICorDebugTypeEnum-Schnittstelle](icordebugtypeenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugType`-Arrays auf.  
  
 [ICorDebugUnmanagedCallback-Schnittstelle](icordebugunmanagedcallback-interface.md)\
 Stellt eine Benachrichtigung über systemeigene Ereignisse bereit, die sich nicht direkt auf die Common Language Runtime beziehen.  
  
 [ICorDebugValue](icordebugvalue-interface.md)\
 Stellt einen Lese- oder Schreibwert in dem Prozess dar, der gedebuggt wird.  
  
 [ICorDebugValue2](icordebugvalue2-interface.md)\
 Erweitert `ICorDebugValue`, um `ICorDebugType` zu unterstützen.  
  
 [ICorDebugValue3-Schnittstelle](icordebugvalue3-interface.md)\
 Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays bereitzustellen, die größer als 2 GB sind.  
  
 [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\
 Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Werte zu ermöglichen.  
  
 [ICorDebugValueEnum](icordebugvalueenum-interface.md)\
 Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugValue`-Arrays auf.  
  
 [ICorDebugVariableHome-Schnittstelle](icordebugvariablehome-interface.md)\
 Stellt eine lokale Variable oder ein Argument einer Funktion.  
  
 [ICorDebugVariableHomeEnum-Schnittstelle](icordebugvariablehomeenum-interface.md)\
 Stellt einen Enumerator für die lokalen Variablen und Argumente in einer Funktion an.  
  
 [ICorDebugVariableSymbol-Schnittstelle](icordebugvariablesymbol-interface.md)\
 Ruft Debugsymbolinformationen für eine Variable ab. **Nur .NET Native verfügbar.**  
  
 [ICorDebugVirtualUnwinder-Schnittstelle](icordebugvirtualunwinder-interface.md)\
 Stellt Methoden bereit, um die Stapelentladung zu unterstützen. **Nur .NET Native verfügbar.**  
  
 [ICorPublish-Schnittstelle](icorpublish-interface.md)\
 Fungiert als allgemeine Schnittstelle für die Veröffentlichungsprozesse.  
  
 [ICorPublishAppDomain-Schnittstelle](icorpublishappdomain-interface.md)\
 Stellt Informationen zu einer Anwendungsdomäne dar und bereit.  
  
 [ICorPublishAppDomainEnum-Schnittstelle](icorpublishappdomainenum-interface.md)\
 Stellt Methoden bereit, die eine Auflistung von `ICorPublishAppDomain`-Objekten traversieren, die gerade innerhalb eines Prozesses vorhanden sind.  
  
 [ICorPublishEnum-Schnittstelle](icorpublishenum-interface.md)\
 Fungiert als abstrakte Basis für die Veröffentlichung von Enumeratoren.  
  
 [ICorPublishProcess-Schnittstelle](icorpublishprocess-interface.md)\
 Stellt Methoden bereit, die auf Informationen über einen Prozess zugreifen.  
  
 [ICorPublishProcessEnum-Schnittstelle](icorpublishprocessenum-interface.md)\
 Stellt Methoden bereit, die eine Auflistung von `ICorPublishProcess`-Objekten traversieren.  

 [ISOSDacInterface-Schnittstelle](isosdacinterface-interface.md)\
 Stellt Hilfsmethoden bereit, um den Zugriff auf Daten aus `SOS`.

 [IXCLRDataMethodDefinition-Schnittstelle](ixclrdatamethoddefinition-interface.md)\
 Stellt Methoden zum Abfragen von Informationen zu einer Methodendefinition.
 
 [IXCLRDataMethodInstance-Schnittstelle](ixclrdatamethodinstance-interface.md)\
 Stellt Methoden zum Abfragen von Informationen zu einer Methodeninstanz bereit.
 
 [IXCLRDataModule-Schnittstelle](ixclrdatamodule-interface.md)\
 Stellt Methoden zum Abfragen von Informationen zu einem geladenen Modul bereit.
 
 [IXCLRDataProcess-Schnittstelle](ixclrdataprocess-interface.md)\
 Stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Debuggen von Co-Klassen](debugging-coclasses.md)\
 [Debuggen von globalen statischen Funktionen](debugging-global-static-functions.md)\
 [Debugenumerationen](debugging-enumerations.md)\
 [Debuggen von Strukturen](debugging-structures.md)\
