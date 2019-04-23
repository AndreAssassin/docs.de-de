---
title: <clear> -Element für <listeners> für <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 97b18f9d6baa618b0f535955b232e2119c758b11
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124890"
---
# <a name="clear-element-for-listeners-for-trace"></a>\<clear >-Element für \<Listener > für \<Ablaufverfolgung >
Löscht die `Listeners`-Sammlung für die Ablaufverfolgung.  
  
 \<configuration>  
\<system.diagnostics>  
\<trace>  
\<listeners>  
\<clear>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`system.diagnostics`|Gibt Ablaufverfolgungslistener an, die Meldungen sammeln, speichern und weiterleiten sowie die Ebene, für die ein Ablaufverfolgungsschalter festgelegt ist.|  
|`trace`|Enthält Listener, die Ablaufverfolgungsmeldungen sammeln, speichern und weiterleiten.|  
|`listeners`|Enthält Listener, die sammeln, speichern und Weiterleiten von Nachrichten. Listener leiten die Ablaufverfolgungsausgabe an ein entsprechendes Ziel.|  
  
## <a name="remarks"></a>Hinweise  
 Die `<clear>` -Element entfernt alle Listener aus der `Listeners` -Sammlung für die Ablaufverfolgung. Können Sie die `<clear>` Element vor der Verwendung der `<add>` Element, stellen Sie sicher, dass keine anderen aktiven Listener in der Auflistung vorhanden sind.  
  
 Können Sie löschen die `Listeners` Auflistung programmgesteuert durch Aufrufen der <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> Methode für die <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> Eigenschaft (`System.Diagnostics.Trace.Listeners.Clear()`).  
  
 Dieses Element kann in der Computerkonfigurationsdatei (Machine.config) und der Anwendungskonfigurationsdatei verwendet werden.  
  
> [!NOTE]
>  Die `<clear>` -Element entfernt die <xref:System.Diagnostics.DefaultTraceListener> aus der `Listeners` Auflistung, die Änderung des Verhaltens der <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, und <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> Methoden. Aufrufen einer `Assert` oder `Fail` -Methode führt normalerweise in der Anzeige eines Meldungsfelds. Allerdings das Meldungsfeld wird nicht angezeigt, wenn die <xref:System.Diagnostics.DefaultTraceListener> befindet sich nicht in der `Listeners` Auflistung.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mit der `<clear>` Element vor der Verwendung der `<add>` Element, um den Listener hinzuzufügen `console` auf die `Listeners` -Sammlung für die Ablaufverfolgung.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [Trace and Debug Settings Schema (Schema für Ablaufverfolgungs- und Debugeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [\<remove>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)
- [Trace Listeners (Ablaufverfolgungslistener)](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
