---
title: <publisherPolicy>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/publisherPolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#publisherPolicy
helpviewer_keywords:
- publisherPolicy element
- container tags, <publisherPolicy> element
- <publisherPolicy> element
ms.assetid: 4613407e-d0a8-4ef2-9f81-a6acb9fdc7d4
ms.openlocfilehash: 89fa8a991cc7d0352eb0a13cdfd3a6063ea468e7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115847"
---
# <a name="publisherpolicy-element"></a>\<publisherPolicy-> Element
Gibt an, ob die Common Language Runtime die Herausgeberrichtlinie anwendet.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) \
&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding**](assemblybinding-element-for-runtime.md) > \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<dependentAssembly >** ](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<publisherPolicy >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<publisherPolicy apply="yes|no"/>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`apply`|Gibt an, ob Herausgeber Richtlinien angewendet werden sollen.|  
  
## <a name="apply-attribute"></a>Attribut anwenden  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`yes`|Wendet Herausgeber Richtlinien an. Dies ist die Standardeinstellung.|  
|`no`|Die Herausgeber Richtlinie wird nicht angewendet.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`assemblyBinding`|Enthält Informationen über die Assemblyversionsumleitung und die Speicherorte von Assemblys.|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`dependentAssembly`|Kapselt die Bindungsrichtlinie und den Assemblyspeicherort für jede Assembly. Verwenden Sie für jede Assembly ein `<dependentAssembly>` Element.|  
|`runtime`|Enthält Informationen über die Assemblybindung und die Garbage Collection.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn ein Komponentenhersteller eine neue Version einer Assembly freigibt, kann der Hersteller eine Herausgeber Richtlinie einschließen, damit Anwendungen, die die alte Version verwenden, nun die neue Version verwenden. Um anzugeben, ob die Herausgeber Richtlinie für eine bestimmte Assembly angewendet werden soll, fügen Sie das **\<publisherPolicy** -Element > in das **\<dependentAssembly->** Element ein.  
  
 Die Standardeinstellung für das **Apply** -Attribut ist " **Yes**". Wenn Sie das **Apply** -Attribut auf **No** festlegen, werden alle vorherigen **Yes** -Einstellungen für eine Assembly überschrieben.  
  
 Die Berechtigung ist erforderlich, damit eine Anwendung die Herausgeber Richtlinie mithilfe der [\<publisherPolicy Apply = "No"/>-](publisherpolicy-element.md) Element in der Anwendungs Konfigurationsdatei explizit ignoriert. Die Berechtigung wird erteilt, indem das <xref:System.Security.Permissions.SecurityPermissionFlag>-Flag für die <xref:System.Security.Permissions.SecurityPermission>festgelegt wird. Weitere Informationen finden Sie unter [Sicherheits Berechtigung für die assemblybindungsumleitung](../../assembly-binding-redirection-security-permission.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Herausgeber Richtlinie für die Assembly deaktiviert, `myAssembly`.  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                                    publicKeyToken="32ab4ba45e0a69a1"  
                                    culture="neutral" />  
            <publisherPolicy apply="no"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Schema für Laufzeiteinstellungen](index.md)
- [Konfigurationsdateischema](../index.md)
- [So sucht Common Language Runtime nach Assemblys](../../../deployment/how-the-runtime-locates-assemblies.md)
- [Umleiten von Assemblyversionen](../../redirect-assembly-versions.md)
