---
title: <UseSmallInternalThreadStacks>-Element
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 70113d98c5a4ab41700f6c9842dba89e2b49c297
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489328"
---
# <a name="usesmallinternalthreadstacks-element"></a>\<UseSmallInternalThreadStacks >-Element
Fordert an, dass die common Language Runtime (CLR) Speicher reduzieren verwenden, indem Sie explizite Stapelgrößen angeben, wenn es sich um bestimmte Threads, die sie intern verwendet erstellt, statt die standardmäßige Stapelgröße für diese Threads.  
  
 \<Configuration >-Element  
\<Common Language Runtime >-Element  
\<UseSmallInternalThreadStacks >-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|enabled|Erforderliches Attribut.<br /><br /> Gibt an, ob anfordern, die die CLR explizite Stapelgrößen anstelle der Standardstapelgröße Wenn es sich um bestimmte Threads erstellt, die intern verwendet. Die explizite Stapelgrößen sind kleiner als die Standardstapelgröße 1 MB.|  
  
## <a name="enabled-attribute"></a>Enabled-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|true|Fordern Sie explizite Stapelgrößen an.|  
|False|Verwenden Sie die standardmäßige Stapelgröße. Dies ist die Standardeinstellung für .NET Framework 4.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Konfigurationselement wird verwendet, weniger virtuelle Arbeitsspeicher verwenden, in einem Prozess, anfordern, da die Größe der expliziten Threads, die die CLR für die internen Threads verwendet werden, wenn die Anforderung berücksichtigt wird, kleiner als die Standardgröße ist.  
  
> [!IMPORTANT]
>  Dieses Element ist eine Anforderung an die CLR, anstatt eine zwingende Voraussetzung nicht erfüllt. In .NET Framework 4, wird die Anforderung nur für die X86 berücksichtigt Architektur. Dieses Element möglicherweise vollständig in zukünftigen Versionen der CLR ignoriert, oder durch explizite Stapelgrößen, die immer für den ausgewählten internen Threads verwendet werden ersetzt.  
  
 Angeben, dass dieses Konfigurationselement Klassen Zuverlässigkeit für kleinere virtueller Arbeitsspeicher verwenden, wenn die CLR die Anforderung berücksichtigt, da kleinere Stapel möglicherweise Stack vornehmen könnten eher überläuft.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie anfordern, dass die CLR mit explizite Stapel für bestimmte Threads Größen, die intern verwendet wird.  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
