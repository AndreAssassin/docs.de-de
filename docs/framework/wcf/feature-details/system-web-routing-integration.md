---
title: System.Web.Routing-Integration
ms.date: 03/30/2017
ms.assetid: 31fe2a4f-5c47-4e5d-8ee1-84c524609d41
ms.openlocfilehash: 3d5c3d7586189e0939fd52bc2b5feac51ae00613
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097511"
---
# <a name="systemwebrouting-integration"></a>System.Web.Routing-Integration
Beim Hosten eines Windows Communication Foundation (WCF)-Diensts in Internet Information Service (IIS) platzieren Sie eine SVC-Datei in das virtuelle Verzeichnis ein. Diese SVC-Datei gibt die zu verwendende Diensthostfactory sowie die Klasse an, die den Dienst implementiert. Bei Anforderungen an den Dienst geben Sie die SVC-Datei im URI an, z. B.: `http://contoso.com/EmployeeServce.svc`. Für Programmierer, die REST-Dienste schreiben, ist dieser Typ von URI nicht optimal. URIs für REST-Dienste geben eine bestimmte Ressource an und verfügen normalerweise nicht über Erweiterungen. Die <xref:System.Web.Routing> -Integrationsfunktion können Sie zum Hosten eines WCF REST-Diensts, der auf URIs ohne Erweiterung reagiert. Weitere Informationen zu routing finden Sie unter [ASP.NET-Routing](https://go.microsoft.com/fwlink/?LinkId=184660).  
  
## <a name="using-systemwebrouting-integration"></a>Verwenden der System.Web.Routing-Integration  
 Für die <xref:System.Web.Routing>-Integrationsfunktion verwenden Sie die <xref:System.ServiceModel.Activation.ServiceRoute>-Klasse, um eine oder mehrere Routen zu erstellen und diese dem <xref:System.Web.Routing.RouteTable>-Objekt in einer Global.asax-Datei hinzuzufügen. Diese Routen geben die relativen URIs an, auf die der Dienst reagiert. Das folgende Beispiel zeigt die dazu erforderliche Vorgehensweise.  
  
```  
<%@ Application Language="C#" %>  
<%@ Import Namespace="System.Web.Routing" %>  
<%@ Import Namespace="System.ServiceModel.Activation" %>  
<%@ Import Namespace="System.ServiceModel.Web " %>  
  
<script RunAt="server">  
    void Application_Start(object sender, EventArgs e)  
    {  
        RegisterRoutes(RouteTable.Routes);  
    }  
  
    private void RegisterRoutes(RouteCollection routes)  
    {  
        routes.Add(new ServiceRoute("Customers", new WebServiceHostFactory(), typeof(Service)));   
   }  
</script>  
```  
  
 Hier werden alle Anforderungen mit einem relativen URI, die mit "Customers" beginnen, an den `Service`-Dienst weitergeleitet.  
  
 In der Datei "Web.config" müssen Sie das `System.Web.Routing.UrlRoutingModule`-Modul hinzufügen, das `runAllManagedModulesForAllRequests`-Attribut auf `true` setzen und dem `UrlRoutingHandler`-Element den `<system.webServer>`-Handler hinzufügen. Dies wird im folgenden Beispiel veranschaulicht.  
  
```xml  
<system.webServer>  
      <modules runAllManagedModulesForAllRequests="true">  
        <add name="UrlRoutingModule" type="System.Web.Routing.UrlRoutingModule, System.Web, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a" />  
      </modules>  
      <handlers>  
        <add name="UrlRoutingHandler" preCondition="integratedMode" verb="*" path="UrlRouting.axd"/>  
      </handlers>  
    </system.webServer>  
```  
  
 Es werden ein Modul und ein Handler geladen, die für das Routing erforderlich sind. Weitere Informationen finden Sie unter [Routing](../../../../docs/framework/wcf/feature-details/routing.md). Außerdem müssen Sie das `aspNetCompatibilityEnabled`-Attribut wie im folgenden Beispiel gezeigt im `true`-Element auf `<serviceHostingEnvironment>` setzen.  
  
```xml  
<system.serviceModel>  
    <serviceHostingEnvironment aspNetCompatibilityEnabled="true"/>  
        <!-- ... -->  
    </system.serviceModel>  
```  
  
 Die Klasse, die den Dienst implementiert, muss die ASP.NET-Kompatibilitätsanforderungen wie im folgenden Beispiel gezeigt aktivieren.  
  
```  
[ServiceContract]  
[AspNetCompatibilityRequirements(RequirementsMode=AspNetCompatibilityRequirementsMode.Allowed)]  
    public class Service  
    {  
        // ...  
    }  
```  
  
## <a name="see-also"></a>Siehe auch

- [WCF-Web-HTTP-Programmiermodell](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
- [ASP.NET-Routing](https://go.microsoft.com/fwlink/?LinkId=184660)
