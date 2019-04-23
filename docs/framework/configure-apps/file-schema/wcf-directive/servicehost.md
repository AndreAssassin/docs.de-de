---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: 3102ae8d8c28be43883eeaff6c4f829b355384a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111396"
---
# <a name="servicehost"></a>\@ServiceHost
Ordnet die Factory zu, die zum Generieren des Diensthosts mit dem zu hostenden Dienst verwendet wird, sowie andere Programmieraspekte, die für den Zugriff und die Kompilierung des in der SVC-Datei enthaltenen Hostingcodes erforderlich sind.  
  
## <a name="syntax"></a>Syntax  
  
```  
<% @ServiceHost   
Service = "Service, ServiceNamespace"   
Factory = "Factory, FactoryNamespace"  
Debug = "Debug"  
Language = "Language"   
CodeBehind = "CodeBehind"%>  
```  
  
## <a name="attributes"></a>Attribute  
  
#### <a name="service"></a>Dienst  
 Der CLR-Typname des gehosteten Diensts. Dabei sollte es sich um einen qualifizierten Namen eines Typs handeln, der mindestens einen Dienstkontakt implementiert.  
  
#### <a name="factory"></a>Factory  
 Der CLR-Typname der Diensthostfactory, der zum Instanziieren des Diensthosts verwendet wird. Dieses Attribut ist optional. Falls nicht angegeben, wird die Standard-<xref:System.ServiceModel.Activation.ServiceHostFactory> verwendet, die eine Instanz von <xref:System.ServiceModel.ServiceHost> zurückgibt.  
  
#### <a name="debug"></a>Debug  
 Gibt an, ob der Windows Communication Foundation (WCF)-Dienst mit Debugsymbolen kompiliert werden soll. `true` Wenn der WCF-Dienst mit Debugsymbolen kompiliert werden soll; andernfalls `false`.  
  
#### <a name="language"></a>Sprache  
 Gibt die Sprache zum Kompilieren des gesamten Inlinecodes in der Datei (SVC) an. Die Werte können jede von .NET unterstützte Sprache darstellen, darunter C#, VB und JS, die sich jeweils auf C#, Visual Basic .NET und JScript .NET beziehen. Dieses Attribut ist optional.  
  
#### <a name="codebehind"></a>CodeBehind  
 Gibt die Quelldatei an, die den XML-Webdienst implementiert, wenn sich die Klasse, die den XML-Webdienst implementiert, nicht in derselben Datei befindet und nicht in eine Assembly kompiliert oder im Verzeichnis \Bin gespeichert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die <xref:System.ServiceModel.ServiceHost> verwendet, um den Dienst zu hosten ist ein Aspekt der Erweiterbarkeit innerhalb des Programmiermodells von Windows Communication Foundation (WCF). Ein Factorymuster wird zum Instanziieren von <xref:System.ServiceModel.ServiceHost> verwendet, da es sich möglicherweise um einen polymorphen Typ handelt, der von der Hostumgebung nicht direkt instanziiert werden sollte.  
  
 Die Standardimplementierung verwendet <xref:System.ServiceModel.Activation.ServiceHostFactory>, um eine Instanz von <xref:System.ServiceModel.ServiceHost> zu erstellen. Aber Sie können Ihre eigene Factory (eine, die den abgeleiteten Host zurückgibt) Geben Sie dazu die CLR-Typnamen Ihrer Factoryimplementierung in der [ \@ServiceHost](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) Richtlinie.  
  
 Damit Sie eigene benutzerdefinierte Diensthostfactory statt der standardfactory verwenden, geben Sie einfach den Typnamen in der [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) Richtlinie wie folgt:  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 Halten Sie die Factoryimplementierungen so einfach wie möglich. Falls die benutzerdefinierte Logik umfassend ist, kann der Code einfacher wiederverwendet werden, wenn Sie diese Logik im Host und nicht in der Factory platzieren.  
  
 Beispielsweise, um einen AJAX-fähigen Endpunkt für aktivieren `MyService`, geben Sie die <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> für den Wert des der `Factory` -Attribut anstelle des standardmäßigen <xref:System.ServiceModel.Activation.ServiceHostFactory>in der [ @ServiceHost ](../../../../../docs/framework/configure-apps/file-schema/wcf-directive/servicehost.md) als die Richtlinie Im folgenden Beispiel gezeigt.  
  
## <a name="example"></a>Beispiel  
  
```  
<% @ServiceHost   
Service="MyService"  
Language="C#"  
Debug="true"  
Factory="WebScriptServiceHostFactory"  
%>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Benutzerdefinierter Diensthost](../../../../../docs/framework/wcf/samples/custom-service-host.md)
