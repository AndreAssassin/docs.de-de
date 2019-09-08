---
title: Anpassung von Feeds (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, feeds
- WCF Data Services, Atom protocol
- Atom Publishing Protocol [WCF Data Services]
- WCF Data Services, customizing feeds
ms.assetid: 0d1a39bc-6462-4683-bd7d-e74e0fd28a85
ms.openlocfilehash: b4ea05b0112af4c1dcb6308a08ab3b31c586fbe8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790863"
---
# <a name="feed-customization-wcf-data-services"></a>Anpassung von Feeds (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)][!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] verwendet, um Daten als-Feed verfügbar zu machen. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]unterstützt sowohl Atom-als auch JavaScript Object Notation (JSON)-Formate für Datenfeeds. Wenn Sie einen Atom-Feed verwenden [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] , stellt eine Standardmethode zum Serialisieren von Daten (z. b. Entitäten und Beziehungen) in ein XML-Format bereit, das in den Text der HTTP-Nachricht aufgenommen werden kann. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]definiert eine standardmäßige Entitäts Eigenschafts Zuordnung zwischen den Daten, die in Entitäten und Atom-Elementen enthalten sind. Weitere Informationen finden [Sie unter odata: Atom-](https://go.microsoft.com/fwlink/?LinkID=185794)Format.  
  
 In Ihrem Anwendungsszenario ist es möglicherweise erforderlich, dass die vom Datendienst zurückgegebenen Eigenschaftendaten benutzerdefiniert serialisiert werden anstatt im Standardfeedformat. Mit [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]können Sie die Serialisierung in einem Datenfeed anpassen, damit Eigenschaften einer Entität nicht verwendeten Elementen und Attributen eines Eintrags oder benutzerdefinierten Elementen eines Eintrags im Feed zugeordnet werden können.  
  
> [!NOTE]
> Die Feedanpassung wird nur für Atom-Feeds unterstützt. Benutzerdefinierte Feeds werden nicht zurückgegeben, wenn das JSON (JavaScript Object Notation)-Format für den zurückgegebenen Feed angefordert wird.  
  
 Mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] können Sie eine alternative Entitätseigenschaftszuordnung für eine Atom-Nutzlast definieren, indem Sie Attribute manuell auf Entitätstypen im Datenmodell anwenden. Der Datenquellenanbieter des Datendiensts bestimmt, wie diese Attribute angewendet werden.  
  
> [!IMPORTANT]
> Wenn Sie benutzerdefinierte Feeds definieren, müssen Sie gewährleisten, dass alle Entitätseigenschaften, für die benutzerdefinierte Zuordnungen definiert wurden, in der Projektion enthalten sind. Wenn eine zugeordnete Entitätseigenschaft nicht in der Projektion enthalten ist, könnten Datenverluste auftreten. Weitere Informationen finden Sie unter [Abfrage Projektionen](query-projections-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-the-entity-framework-provider"></a>Anpassen von Feeds mit dem Entity Framework-Anbieter  
 Das mit dem [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-Anbieter verwendete Datenmodell wird in der EDMX-Datei als XML dargestellt. In diesem Fall werden dem `EntityType`-Element und dem `Property`-Element, die Entitätstypen und Eigenschaften im Datenmodell darstellen, die Attribute hinzugefügt, die benutzerdefinierte Feeds definieren. Diese Feed-Anpassungs Attribute sind nicht in [ \[MC-CSDL\]definiert: Format](https://go.microsoft.com/fwlink/?LinkId=159072)der konzeptionellen Schema Definitionsdatei. Dies ist das Format, [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] das der Anbieter zum Definieren des Datenmodells verwendet. Daher müssen Sie Feedanpassungsattribute in einem bestimmten Schemanamespace deklarieren, der als `m="http://schemas.microsoft.com/ado/2007/08/dataservices/metadata"` definiert wird. Das folgende XML-Fragment zeigt auf die `Property`-Elemente des `Products`-Entitätstyps angewendete Feedanpassungsattribute, die die Eigenschaften `ProductName`, `ReorderLevel` und `UnitsInStock` definieren.  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedAttributes](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/northwind.csdl#edmfeedattributes)]  
  
 Diese Attribute erzeugen den folgenden benutzerdefinierten Datenfeed für die `Products`-Entitätenmenge. Im benutzerdefinierten Datenfeed wird der `ProductName`-Eigenschaftswert im `author`-Element und als `ProductName`-Eigenschaftselement angezeigt, und die `UnitsInStock`-Eigenschaft wird in einem benutzerdefinierten Element mit einem eigenen eindeutigen Namespace und mit der `ReorderLevel`-Eigenschaft als Attribut angezeigt:  
  
 [!code-xml[Astoria Custom Feeds#EdmFeedResultProduct](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/edmfeedresult.xml#edmfeedresultproduct)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen von Feeds mit dem Entity Framework](how-to-customize-feeds-with-ef-provider-wcf-data-services.md)-Anbieter.  
  
> [!NOTE]
> Da Erweiterungen des Datenmodells nicht vom Entity Designer unterstützt werden, müssen Sie die XML-Datei, die das Datenmodell enthält, manuell ändern. Weitere Informationen über die EDMX-Datei, die von den Entity Data Model Tools generiert wird, finden Sie unter Übersicht über die [EDMX-Datei (Entity Framework)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)).  
  
### <a name="custom-feed-attributes"></a>Benutzerdefinierte Feedattribute  
 In der folgenden Tabelle werden die XML-Attribute angezeigt, die Feeds anpassen, die Sie der konzeptionellen Schemadefinitionssprache (CSDL) hinzufügen können, die das Datenmodell definiert. Diese Attribute entsprechen den Eigenschaften des mit dem Reflektionsanbieter verwendeten <xref:System.Data.Services.Common.EntityPropertyMappingAttribute>.  
  
|Attributname|Beschreibung|  
|--------------------|-----------------|  
|`FC_ContentKind`|Gibt den Inhaltstyp an. Die folgenden Schlüsselwörter definieren Syndication-Inhaltstypen.<br /><br /> `text:`Der Eigenschafts Wert wird im Feed als Text angezeigt.<br /><br /> `html:`Der Eigenschafts Wert wird im Feed als HTML angezeigt.<br /><br /> `xhtml:`Der Eigenschafts Wert wird im Feed als XML-formatierter HTML-Code angezeigt.<br /><br /> Diese Schlüsselwörter entsprechen den Werten der mit dem Reflexionsanbieter verwendeten <xref:System.Data.Services.Common.SyndicationTextContentKind>-Enumeration.<br /><br /> Dieses Attribut wird nicht unterstützt, wenn das `FC_NsPrefix`-Attribut und das `FC_NsUri`-Attribut verwendet werden.<br /><br /> Wenn Sie den Wert `xhtml` für das `FC_ContentKind`-Attribut angeben, müssen Sie sicherstellen, dass der Eigenschaftswert ordnungsgemäß formatiertes XML enthält. Der Datendienst gibt den Wert zurück, ohne irgendwelche Transformationen auszuführen. Sie müssen auch sicherstellen, dass alle XML-Elementpräfixe im zurückgegebenen XML einen Namespace-URI und ein Präfix haben, die im zugeordneten Feed definiert sind.|  
|`FC_KeepInContent`|Gibt an, dass der Eigenschaftswert, auf den verwiesen wird, sowohl im Inhaltsabschnitt des Feeds als auch im zugeordneten Speicherort enthalten sein soll. Gültige Werte sind `true` und `false`. Um den resultierenden Feed abwärts kompatibel mit früheren Versionen von [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]zu machen, geben Sie den `true` Wert an, um sicherzustellen, dass der Wert im Inhalts Abschnitt des Feeds enthalten ist.|  
|`FC_NsPrefix`|Das Namespacepräfix des XML-Elements in einer Nicht-Syndication-Zuordnung. Dieses Attribut muss zusammen mit dem `FC_NsUri`-Attribut und kann nicht zusammen mit dem `FC_ContentKind`-Attribut verwendet werden.|  
|`FC_NsUri`|Der Namespace-URI des XML-Elements in einer Nicht-Syndication-Zuordnung. Dieses Attribut muss zusammen mit dem `FC_NsPrefix`-Attribut und kann nicht zusammen mit dem `FC_ContentKind`-Attribut verwendet werden.|  
|`FC_SourcePath`|Der Pfad der Eigenschaft der Entität, für die diese Feedzuordnungsregel gilt. Dieses Attribut wird nur unterstützt, wenn es in einem `EntityType`-Element verwendet wird.<br /><br /> Die <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A>-Eigenschaft kann nicht direkt auf einen komplexen Typ verweisen. Für komplexe Typen müssen Sie einen Pfadausdruck verwenden, in dem Eigenschaftennamen durch einen umgekehrten Schrägstrich (`/`) getrennt werden. Die folgenden Werte sind z. b. für einen Entitätstyp `Person` mit einer ganzzahligen Eigenschaft `Age` und einer komplexen Eigenschaft zulässig.<br /><br /> `Address`:<br /><br /> `Age`<br /><br /> `Address/Street`<br /><br /> Die <xref:System.Data.Services.Common.EntityPropertyMappingAttribute.SourcePath%2A>-Eigenschaft kann nicht auf einen Wert festgelegt werden, der ein Leerzeichen oder ein anderes Zeichen enthält, das in einem Eigenschaftennamen ungültig ist.|  
|`FC_TargetPath`|Der Name des Zielelements des resultierenden Feeds zum Zuordnen der Eigenschaft. Dieses Element kann ein von der Atom-Spezifikation definiertes Element oder ein benutzerdefiniertes Element sein.<br /><br /> Die folgenden Schlüsselwörter sind vordefinierte Syndication Zielpfad-Werte, die auf bestimmte Positionen in einem [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Feed zeigen.<br /><br /> `SyndicationAuthorEmail:`Das `atom:email` untergeordnete-Element `atom:author` des-Elements.<br /><br /> `SyndicationAuthorName:`Das `atom:name` untergeordnete-Element `atom:author` des-Elements.<br /><br /> `SyndicationAuthorUri:`Das `atom:uri` untergeordnete-Element `atom:author` des-Elements.<br /><br /> `SyndicationContributorEmail:`Das `atom:email` untergeordnete-Element `atom:contributor` des-Elements.<br /><br /> `SyndicationContributorName:`Das `atom:name` untergeordnete-Element `atom:contributor` des-Elements.<br /><br /> `SyndicationContributorUri:`Das `atom:uri` untergeordnete-Element `atom:contributor` des-Elements.<br /><br /> `SyndicationCustomProperty:`Ein benutzerdefiniertes Eigenschaften Element. Bei der Zuordnung zu einem benutzerdefinierten Element muss das Ziel ein Pfadausdruck sein, in dem geschachtelte Elemente durch einen umgekehrten Schrägstrich (`/`) getrennt und Attribute durch ein kaufmännisches Und-Zeichen (`@`) angegeben werden. Im folgenden Beispiel ordnet die Zeichenfolge `UnitsInStock/@ReorderLevel` einen Eigenschaftswert dem Attribut `ReorderLevel` auf dem untergeordneten Element `UnitsInStock` des Stammeintragselements zu.<br /><br /> `<Property Name="ReorderLevel" Type="Int16"               m:FC_TargetPath="UnitsInStock/@ReorderLevel"               m:FC_NsPrefix="Northwind"               m:FC_NsUri="http://schemas.examples.microsoft.com/dataservices"               m:FC_KeepInContent="false"               />`<br /><br /> Wenn das Ziel ein benutzerdefinierter Elementname ist, müssen das `FC_NsPrefix`-Attribut und das `FC_NsUri`-Attribut ebenfalls angegeben werden.<br /><br /> `SyndicationPublished:`Das `atom:published` Element.<br /><br /> `SyndicationRights:`Das `atom:rights` Element.<br /><br /> `SyndicationSummary:`Das `atom:summary` Element.<br /><br /> `SyndicationTitle:`Das `atom:title` Element.<br /><br /> `SyndicationUpdated:`Das `atom:updated` Element.<br /><br /> Diese Schlüsselwörter entsprechen den Werten der mit dem Reflexionsanbieter verwendeten <xref:System.Data.Services.Common.SyndicationItemProperty>-Enumeration.|  
  
> [!NOTE]
> Bei Attributnamen und -werten muss die Groß-/Kleinschreibung beachtet werden. Attribute können entweder nur auf das `EntityType`-Element oder auf ein oder mehrere `Property`-Elemente angewendet werden.  
  
## <a name="customizing-feeds-with-the-reflection-provider"></a>Anpassen von Feeds mit dem Reflektionsanbieter  
 Zum Anpassen von Feeds für ein mit dem Reflektionsanbieter implementiertes Datenmodell fügen Sie den Klassen, die Entitätstypen im Datenmodell darstellen, eine oder mehrere Instanzen des <xref:System.Data.Services.Common.EntityPropertyMappingAttribute>-Attributs hinzu. Die Eigenschaften der <xref:System.Data.Services.Common.EntityPropertyMappingAttribute>-Klasse entsprechen den Feedanpassungsattributen, die im vorherigen Abschnitt beschrieben werden. Nachfolgend ein Beispiel für die Deklaration des `Order`-Typs, wobei die benutzerdefinierte Feedzuordnung für beide Eigenschaften definiert ist.  
  
> [!NOTE]
> Das Datenmodell für dieses Beispiel wird im Thema [Gewusst wie: Erstellen Sie einen Datendienst mithilfe des reflektionsanbieters](create-a-data-service-using-rp-wcf-data-services.md).  
  
 [!code-csharp[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customorderfeed)]
 [!code-vb[Astoria Custom Feeds#CustomOrderFeed](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customorderfeed)]  
  
 Diese Attribute erzeugen den folgenden benutzerdefinierten Datenfeed für die `Orders`-Entitätenmenge. In diesem angepassten Feed wird der `OrderId` `Customer` `Customer` `title` -Eigenschafts`entry` Wert nur im-Element von angezeigt, und der-Eigenschafts Wert wird im- Elementundals-EigenschaftsElementangezeigt:`author`  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResult](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresult.xml#iqueryablefeedresult)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Anpassen von Feeds mit dem reflektionsanbieter](how-to-customize-feeds-with-the-reflection-provider-wcf-data-services.md).  
  
## <a name="customizing-feeds-with-a-custom-data-service-provider"></a>Anpassen von Feeds mithilfe eines benutzerdefinierten Datendienstanbieters  
 Die Feedanpassung für ein Datenmodell, das durch die Verwendung eines benutzerdefinierten Datendienstanbieters definiert ist, wird für einen Ressourcentyp definiert, indem das <xref:System.Data.Services.Providers.ResourceType.AddEntityPropertyMappingAttribute%2A> auf dem <xref:System.Data.Services.Providers.ResourceType> aufgerufen wird, der einen Entitätstyp im Datenmodell darstellt. Weitere Informationen finden Sie unter [benutzerdefinierte Daten Dienstanbieter](custom-data-service-providers-wcf-data-services.md).  
  
## <a name="consuming-custom-feeds"></a>Verwenden von benutzerdefinierten Feeds  
 Wenn die Anwendung einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] -Feed direkt verwendet, muss Sie alle angepassten Elemente und Attribute im zurückgegebenen Feed verarbeiten können. Wenn Sie benutzerdefinierte Feeds im Datenmodell unabhängig vom Datendienstanbieter implementiert haben, gibt der `$metadata`-Endpunkt benutzerdefinierte Feedinformationen als benutzerdefinierte Feedattribute in der vom Datendienst zurückgegebenen CSDL zurück. Wenn Sie das Dialogfeld **Dienstverweis hinzufügen** oder das Tool [DataSvcUtil. exe](wcf-data-service-client-utility-datasvcutil-exe.md) zum Generieren von Client Datendienst Klassen verwenden, werden die angepassten Feed-Attribute verwendet, um sicherzustellen, dass Anforderungen und Antworten an den Datendienst ordnungsgemäß verarbeitet werden.  
  
## <a name="feed-customization-considerations"></a>Überlegungen zur Feedanpassung  
 Beim Definieren von benutzerdefinierten Feedzuordnungen sollten Sie Folgendes betrachten.  
  
- Der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Client behandelt zugeordnete Elemente in einem Feed als leer, wenn Sie nur Leerraum enthalten. Aus diesem Grund werden zugeordnete Elemente, die nur Leerzeichen enthalten, auf dem Client nicht mit demselben Leerraum materialisiert. Wenn Sie diesen Leerraum auf dem Client beibehalten möchten, müssen Sie im Feed `KeepInContext` - `true` Zuordnungsattribut den Wert von auf festlegen.  
  
## <a name="versioning-requirements"></a>Versionsanforderungen  
 Die Feedanpassung hat die folgenden Anforderungen an die [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Protokollversion:  
  
- Die Feedanpassung erfordert, dass der Client und der Datendienst Version 2.0 des [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-Protokolls und höhere Versionen unterstützt.  
  
 Weitere Informationen finden Sie unter [Data Service Versioning](data-service-versioning-wcf-data-services.md).  
  
## <a name="see-also"></a>Siehe auch

- [Reflektionsanbieter](reflection-provider-wcf-data-services.md)
- [Entity Framework-Anbieter](entity-framework-provider-wcf-data-services.md)
