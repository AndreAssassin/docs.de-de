---
title: Ablaufverfolgungslistener
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Listener object types
- listeners
- Trace class, listeners
- trace listeners, about trace listeners
- Listeners collection
- trace listeners
- tracing [.NET Framework], trace listeners
- logs, trace listeners
ms.assetid: 444b0d33-67ea-4c36-9e94-79c50f839025
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 752a6a5f9608aa260f192ee3e9e0709b7a10e27e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71052284"
---
# <a name="trace-listeners"></a>Ablaufverfolgungslistener
Wenn Sie mit **Trace**, **Debug** und <xref:System.Diagnostics.TraceSource> arbeiten, müssen Sie einen Mechanismus zum Sammeln und Aufzeichnen der gesendeten Meldungen einrichten. Ablaufverfolgungsmeldungen werden von *Listenern* empfangen. Der Zweck eines Listeners ist das Sammeln, Speichern und Weiterleiten von Ablaufverfolgungsmeldungen. Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel, beispielsweise ein Protokoll, ein Fenster oder eine Textdatei.  
  
 Listener stehen für die Klassen **Debug**, **Trace** und <xref:System.Diagnostics.TraceSource> zur Verfügung, von denen jede ihre Ausgabe an eine Vielzahl von Listenerobjekten senden kann. Im Folgenden werden die häufig verwendeten vordefinierten Listener aufgeführt:  
  
- Ein <xref:System.Diagnostics.TextWriterTraceListener> leitet die Ausgabe zu einer Instanz der <xref:System.IO.TextWriter>-Klasse oder zu einer beliebigen <xref:System.IO.Stream>-Klasse um. Das Schreiben in die Konsole oder in eine Datei ist auch möglich, da diese <xref:System.IO.Stream>-Klassen sind.  
  
- Ein <xref:System.Diagnostics.EventLogTraceListener> leitet die Ausgabe zu einem Ereignisprotokoll um.  
  
- Ein <xref:System.Diagnostics.DefaultTraceListener> gibt die Nachrichten **Write** und **WriteLine** an die **OutputDebugString**- und die **Debugger.Log**-Methode aus. Dies führt in Visual Studio dazu, dass die Debugging-Meldungen im Ausgabefenster angezeigt werden. **Fail** und fehlgeschlagene **Assert**-Meldungen werden auch an die **OutputDebugString**-Windows-API und die **Debugger.Log**-Methode ausgegeben, und darüber hinaus wird auch ein Meldungsfenster angezeigt. Dieses Verhalten ist das Standardverhalten für Meldungen von **Debug** und **Trace**, da **DefaultTraceListener** automatisch in jeder `Listeners`-Auflistung enthalten ist und es sich dabei um den einzigen automatisch eingebundenen Listener handelt.  
  
- Ein <xref:System.Diagnostics.ConsoleTraceListener> leitet eine Ablaufverfolgungs- oder Debuggingausgabe an die Standardausgabe oder den Standardfehlerstream weiter.  
  
- Ein <xref:System.Diagnostics.DelimitedListTraceListener> leitet eine Ablaufverfolgungs- oder Debuggingausgabe an einen Textwriter, z. B. einen Streamwriter, oder an einen Stream, z. B. einen Dateistream, weiter. Die Ablaufverfolgungsausgabe liegt in einem Textformat mit Trennzeichen vor, das das durch die <xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>-Eigenschaft angegebene Trennzeichen verwendet.  
  
- Ein <xref:System.Diagnostics.XmlWriterTraceListener> leitet die Ablaufverfolgungs- oder Debuggingausgabe als XML-codierte Daten an einen <xref:System.IO.TextWriter> oder einen <xref:System.IO.Stream>, wie z. B. einen <xref:System.IO.FileStream>, weiter.  
  
 Wenn neben <xref:System.Diagnostics.DefaultTraceListener> jeder Listener die Ausgabe von **Debug**, **Trace** und <xref:System.Diagnostics.TraceSource> empfangen soll, müssen Sie diese der `Listeners`-Auflistung hinzufügen. Weitere Informationen finden Sie unter [Vorgehensweise: Ablaufverfolgungslistener [erstellen und initialisieren](how-to-create-and-initialize-trace-listeners.md) und Gewusst wie: Verwenden von TraceSource und Filtern mit](how-to-use-tracesource-and-filters-with-trace-listeners.md)Ablaufverfolgungslistenern Alle Listener in der **Listeners**-Auflistung erhalten die gleichen Meldungen aus den Ablaufverfolgungsausgabemethoden. Nehmen wir beispielsweise an, dass Sie zwei Listener einrichten: **TextWriterTraceListener** und **EventLogTraceListener**. Jeder Listener empfängt die gleiche Meldung. Der Listener **TextWriterTraceListener** leitet seine Ausgabe an einen Datenstrom weiter, und der Listener **EventLogTraceListener** leitet seine Ausgabe an ein Ereignisprotokoll weiter.  
  
 Das folgende Beispiel zeigt, wie die Ausgabe an die **Listeners**-Auflistung gesendet wird.  
  
```vb  
' Use this example when debugging.  
Debug.WriteLine("Error in Widget 42")  
' Use this example when tracing.  
Trace.WriteLine("Error in Widget 42")  
```  
  
```csharp  
// Use this example when debugging.  
System.Diagnostics.Debug.WriteLine("Error in Widget 42");  
// Use this example when tracing.  
System.Diagnostics.Trace.WriteLine("Error in Widget 42");  
```  
  
 „Debug“ und „Trace“ nutzen die gleiche **Listeners**-Auflistung. Wenn Sie also der **Debug.Listeners**-Auflistung in Ihrer Anwendung ein Listenerobjekt hinzufügen, wird dieses auch der **Trace.Listeners**-Auflistung hinzugefügt.  
  
 Das folgende Beispiel zeigt, wie ein Listener verwendet wird, um Ablaufverfolgungsinformationen an eine Konsole zu senden:  
  
```vb  
Trace.Listeners.Clear()  
Trace.Listeners.Add(New TextWriterTraceListener(Console.Out))  
```  
  
```csharp  
System.Diagnostics.Trace.Listeners.Clear();  
System.Diagnostics.Trace.Listeners.Add(  
   new System.Diagnostics.TextWriterTraceListener(Console.Out));  
```  
  
## <a name="developer-defined-listeners"></a>Entwicklerdefinierte Listener  
 Sie können eigene Listener durch Erben von der **TraceListener**-Basisklasse definieren und die dazugehörigen Methoden mit benutzerdefinierten Methoden überschreiben. Weitere Informationen zum Erstellen entwicklerdefinierter Listener finden Sie unter <xref:System.Diagnostics.TraceListener> in der Referenz zu .NET Framework.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TraceListener>
- [Ablaufverfolgung und Instrumentieren von Anwendungen](tracing-and-instrumenting-applications.md)
- [Ablaufverfolgungsschalter](trace-switches.md)
