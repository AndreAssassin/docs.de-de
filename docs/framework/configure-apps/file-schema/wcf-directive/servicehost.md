---
title: '@ServiceHost'
ms.date: 03/30/2017
ms.assetid: 96ba6967-00f2-422f-9aa7-15de4d33ebf3
ms.openlocfilehash: a56fb1bb9395425222347914fe3f4c17f1a451b7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920339"
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
 Gibt an, ob der Windows Communication Foundation (WCF)-Dienst mit Debugsymbolen kompiliert werden soll. `true`, wenn der WCF-Dienst mit Debugsymbolen kompiliert werden soll. `false`andernfalls.  
  
#### <a name="language"></a>Sprache  
 Gibt die Sprache zum Kompilieren des gesamten Inlinecodes in der Datei (SVC) an. Die Werte können jede von .NET unterstützte Sprache darstellen, darunter C#, VB und JS, die sich jeweils auf C#, Visual Basic .NET und JScript .NET beziehen. Dieses Attribut ist optional.  
  
#### <a name="codebehind"></a>CodeBehind  
 Gibt die Quelldatei an, die den XML-Webdienst implementiert, wenn sich die Klasse, die den XML-Webdienst implementiert, nicht in derselben Datei befindet und nicht in eine Assembly kompiliert oder im Verzeichnis \Bin gespeichert wurde.  
  
## <a name="remarks"></a>Hinweise  
 Der <xref:System.ServiceModel.ServiceHost> , der zum Hosten des Diensts verwendet wird, ist ein Erweiterbarkeits Punkt innerhalb des Windows Communication Foundation (WCF)-Programmiermodells. Ein Factorymuster wird zum Instanziieren von <xref:System.ServiceModel.ServiceHost> verwendet, da es sich möglicherweise um einen polymorphen Typ handelt, der von der Hostumgebung nicht direkt instanziiert werden sollte.  
  
 Die Standardimplementierung verwendet <xref:System.ServiceModel.Activation.ServiceHostFactory>, um eine Instanz von <xref:System.ServiceModel.ServiceHost> zu erstellen. Sie können jedoch eine eigene Factory bereitstellen (eine, die den abgeleiteten Host zurückgibt), indem Sie den CLR-Typnamen Ihrer Factory-Implementierung in der [ \@Service Host](servicehost.md) -Direktive angeben.  
  
 Wenn Sie anstelle der Standardfactory eine eigene benutzerdefinierte Diensthostfactory verwenden möchten, geben Sie einfach den [@ServiceHost](servicehost.md) Typnamen in der Direktive wie folgt an:  
  
```xml  
<% @ServiceHost Factory="DerivedFactory" Service="MyService" %>  
```  
  
 Halten Sie die Factoryimplementierungen so einfach wie möglich. Falls die benutzerdefinierte Logik umfassend ist, kann der Code einfacher wiederverwendet werden, wenn Sie diese Logik im Host und nicht in der Factory platzieren.  
  
 Wenn Sie z. b. einen AJAX-aktivierten `MyService`Endpunkt für aktivieren <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> möchten, geben Sie den `Factory` für den Wert des Attributs <xref:System.ServiceModel.Activation.ServiceHostFactory>anstelle des Standard [@ServiceHost](servicehost.md) Werts in der-Direktive an, wie im folgenden Beispiel gezeigt.  
  
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

- [Benutzerdefinierter Diensthost](../../../wcf/samples/custom-service-host.md)
