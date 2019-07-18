---
title: Anbietermanifestspezifikation
ms.date: 03/30/2017
ms.assetid: bb450b47-8951-4f99-9350-26f05a4d4e46
ms.openlocfilehash: 9ae528105119241e05be5182db418312c4120112
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422720"
---
# <a name="provider-manifest-specification"></a>Anbietermanifestspezifikation
In diesem Abschnitt wird erläutert, wie ein Datenspeicheranbieter die Typen und Funktionen im Datenspeicher unterstützen kann.  
  
 Entitätsdienste werden unabhängig von einem bestimmten Datenspeicheranbieter ausgeführt. Datenanbieter können jedoch explizit definieren, wie Modelle, Zuordnungen und Abfragen mit einem zugrunde liegenden Datenspeicher interagieren. Ohne eine Abstraktionsebene zielen Entitätsdienste lediglich auf einen bestimmten Datenspeicher oder einen Datenanbieter ab.  
  
 Vom Anbieter unterstützte Typen werden direkt oder indirekt von der zugrunde liegende Datenbank unterstützt. Bei diesen Typen muss es sich nicht unbedingt um die genauen Speichertypen handeln, sondern um die Typen, die der Anbieter für die Unterstützung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwendet. Anbieter-/Speichertypen werden mit den EDM (Entity Data Model)-Begriffen beschrieben.  
  
 Die Parameter und Rückgabetypen für die vom Datenspeicher unterstützten Funktionen werden in EDM-Begriffen angegeben.  
  
## <a name="requirements"></a>Anforderungen  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] und der Datenspeicher müssen in der Lage sein, Daten in bekannten Typen ohne Datenverlust oder Abschneiden in beide Richtungen zu übergeben.  
  
 Das Anbietermanifest muss zur Entwurfszeit von Tools geladen werden können, ohne eine Verbindung mit dem Datenspeicher öffnen zu müssen.  
  
 Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] trifft sensibler, aber möglicherweise nicht der zugrunde liegenden Datenspeicher. Wenn EDM-Artefakte (z. B. Bezeichner und Typnamen) im Manifest definiert und verwendet werden, muss auf die Groß- und Kleinschreibung in [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] geachtet werden. Wenn das Anbietermanifest Datenspeicherelemente enthält, bei denen die Groß-/Kleinschreibung beachtet werden muss, muss diese im Anbietermanifest beibehalten werden.  
  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] erfordert für alle Datenanbieter ein Anbietermanifest. Wenn Sie versuchen, einen Anbieter zu verwenden, die nicht über kein Anbietermanifest mit der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], Sie erhalten eine Fehlermeldung.  
  
 In der folgenden Tabelle werden die Arten von Ausnahmen beschrieben, die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] auslöst, wenn durch Anbieterinteraktion Ausnahmen auftreten:  
  
|Problem|Ausnahme|  
|-----------|---------------|  
|Der Anbieter unterstützt GetProviderManifest in DbProviderServices nicht.|ProviderIncompatibleException|  
|Fehlendes Anbietermanifest: Beim Versuch, das Anbietermanifest abzurufen, gibt der Anbieter `null` zurück.|ProviderIncompatibleException|  
|Ungültiges Anbietermanifest: Beim Versuch, das Anbietermanifest abzurufen, gibt der Anbieter ungültiges XML zurück.|ProviderIncompatibleException|  
  
## <a name="scenarios"></a>Szenarien  
 Ein Anbieter sollte die folgenden Szenarien unterstützen:  
  
### <a name="writing-a-provider-with-symmetric-type-mapping"></a>Schreiben eines Anbieters mit symmetrischer Typzuordnung  
 Sie können einen Anbieter für Schreiben der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] , in denen eine EDM-Typ, unabhängig von der zuordnungsrichtung jeder Speichertyp zugeordnet. Bei Anbietertypen mit einer sehr einfachen Zuordnung, die EDM-Typen entsprechen, können Sie eine symmetrische Lösung verwenden, da das Typsystem einfach ist oder den EDM-Typen entspricht.  
  
 Sie können die Einfachheit der Domäne nutzen und ein statisches deklaratives Anbietermanifest erstellen.  
  
 Sie schreiben eine XML-Datei mit zwei Abschnitten:  
  
- Eine Liste der hinsichtlich des "EDM-Äquivalents" eines Speichertyps oder einer Funktion ausgedrückten Anbietertypen. Speichertypen verfügen über äquivalente EDM-Typen. Speicherfunktionen verfügen über entsprechende EDM-Funktionen. So ist "varchar" z. B. ein SQL Server-Typ, der entsprechende EDM-Typ ist jedoch "string".  
  
- Eine Liste der vom Anbieter unterstützen Funktionen, wobei die Parameter und Rückgabetypen mit EDM-Begriffen ausgedrückt werden.  
  
### <a name="writing-a-provider-with-asymmetric-type-mapping"></a>Schreiben eines Anbieters mit asymmetrischer Typzuordnung  
 Wenn Sie einen Datenspeicheranbieter für [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] schreiben, unterscheidet sich die EDM-Anbieter-Typzuordnung für einige Typen möglicherweise von der Anbieter-EDM-Typzuordnung. So wird beispielsweise "unbounded EDM PrimitiveTypeKind.String" möglicherweise "nvarchar (4000)" für den Anbieter zugeordnet, während "nvarchar (4000)" dem Typ "EDM PrimitiveTypeKind.String(MaxLength=4000)" zugeordnet wird.  
  
 Sie schreiben eine XML-Datei mit zwei Abschnitten:  
  
- Eine Liste von Anbietertypen in EDM-Begriffen ausgedrückt, und definieren die Zuordnung für beide Richtungen: EDM-Anbieter und Anbieter-EDM.  
  
- Eine Liste der vom Anbieter unterstützen Funktionen, wobei die Parameter und Rückgabetypen mit EDM-Begriffen ausgedrückt werden.  
  
## <a name="provider-manifest-discoverability"></a>Ermittelbarkeit des Anbietermanifests  
 Das Manifest wird indirekt von mehreren Komponententypen der Entitätsdienste (z. B. Tools oder Abfrage) verwendet. Die direktere Nutzung erfolgt jedoch für die Metadaten mithilfe des Metadaten-Ladeprogramms des Datenspeichers.  
  
 ![dfb3d02b&#45;7a8c&#45;4d51&#45;ac5a&#45;a73d8aa145e6](../../../../../docs/framework/data/adonet/ef/media/dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6.gif "dfb3d02b-7a8c-4d51-ac5a-a73d8aa145e6")  
  
 Anbieter können jedoch unterschiedliche Speicher oder unterschiedliche Versionen des gleichen Speichers unterstützen. Daher muss ein Anbieter für jeden unterstützten Datenspeicher ein anderes Manifest melden.  
  
### <a name="provider-manifest-token"></a>Anbietermanifesttoken  
 Beim Öffnen einer Datenspeicherverbindung kann der Anbieter Informationen abfragen, um das richtige Manifest zurückzugeben. Dies kann in Offlineszenarien unmöglich sein, in denen entweder die Verbindungsinformationen nicht zur Verfügung stehen oder keine Verbindung mit dem Datenspeicher hergestellt werden kann. Identifizieren Sie das Manifest mit dem `ProviderManifestToken`-Attribut des `Schema`-Elements in der SSDL-Datei. Es gibt kein erforderliches Format für dieses Attribut. Der Anbieter wählt die Mindestinformationen aus, die erforderlich sind, um ein Manifest zu identifizieren, ohne eine Verbindung mit dem Speicher zu öffnen.  
  
 Zum Beispiel:  
  
```xml  
<Schema Namespace="Northwind" Provider="System.Data.SqlClient" ProviderManifestToken="2005" xmlns:edm="http://schemas.microsoft.com/ado/2006/04/edm/ssdl" xmlns="http://schemas.microsoft.com/ado/2006/04/edm/ssdl">  
```  
  
## <a name="provider-manifest-programming-model"></a>Programmiermodell für das Anbietermanifest  
 Anbieter werden von <xref:System.Data.Common.DbXmlEnabledProviderManifest> abgeleitet, sodass die Manifeste deklarativ angegeben werden können. In der folgenden Abbildung wird die Klassenhierarchie eines Anbieters dargestellt:  
  
 ![None](../../../../../docs/framework/data/adonet/ef/media/d541eba3-2ee6-4cd1-88f5-89d0b2582a6c.gif "d541eba3-2ee6-4cd1-88f5-89d0b2582a6c")  
  
### <a name="discoverability-api"></a>Ermittelbarkeits-API  
 Das Anbietermanifest wird vom Speichermetadaten-Ladeprogramm (StoreItemCollection) entweder über eine Datenspeicherverbindung oder mit einem Anbietermanifesttoken geladen.  
  
#### <a name="using-a-data-store-connection"></a>Verwenden einer Datenspeicherverbindung  
 Wenn die datenspeicherverbindung verfügbar ist, rufen Sie <xref:System.Data.Common.DbProviderServices.GetProviderManifestToken%2A?displayProperty=nameWithType> um das Token zurückzugeben, die an der <xref:System.Data.Common.DbProviderServices.GetProviderManifest%2A> Methode, die zurückgibt <xref:System.Data.Common.DbProviderManifest>. Diese Methode delegiert zur Implementierung des Anbieters `GetDbProviderManifestToken`.  
  
```csharp
public string GetProviderManifestToken(DbConnection connection);  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
#### <a name="using-a-provider-manifest-token"></a>Verwenden eines Anbietermanifesttokens  
 Für das Offlineszenario wird das Token der SSDL-Darstellung ausgewählt. SSDL ermöglicht das Festlegen eines ProviderManifestToken (finden Sie unter [Schema-Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl) Informationen). Wenn beispielsweise eine Verbindung nicht geöffnet werden kann, verfügt SSDL über ein Anbietermanifesttoken, das Informationen über das Manifest angibt.  
  
```  
public DbProviderManifest GetProviderManifest(string manifestToken);  
```  
  
### <a name="provider-manifest-schema"></a>Anbietermanifestschema  
 Das Schema der für die einzelnen Anbieter definierten Informationen beinhaltet die statischen Informationen, die von Metadaten genutzt werden:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema elementFormDefault="qualified"  
   xmlns:xs="http://www.w3.org/2001/XMLSchema"  
   targetNamespace="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest"  
   xmlns:pm="http://schemas.microsoft.com/ado/2006/04/edm/providermanifest">  
  
  <xs:element name="ProviderManifest">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Types" type="pm:TTypes" minOccurs="1" maxOccurs="1" />  
        <xs:element name="Functions" type="pm:TFunctions" minOccurs="0" maxOccurs="1"/>  
      </xs:sequence>  
      <xs:attribute name="Namespace" type="xs:string" use="required"/>  
    </xs:complexType>  
  </xs:element>  
  <xs:complexType name="TVersion">  
    <xs:attribute name="Major" type="xs:int" use="required" />  
    <xs:attribute name="Minor" type="xs:int" use="required" />  
    <xs:attribute name="Build" type="xs:int" use="required" />  
    <xs:attribute name="Revision" type="xs:int" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TIntegerFacetDescription">  
    <xs:attribute name="Minimum" type="xs:int" use="optional" />  
    <xs:attribute name="Maximum" type="xs:int" use="optional" />  
    <xs:attribute name="DefaultValue" type="xs:int" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TBooleanFacetDescription">  
    <xs:attribute name="DefaultValue" type="xs:boolean" use="optional" />  
    <xs:attribute name="Constant" type="xs:boolean" default="true" />  
  </xs:complexType>  
  
  <xs:complexType name="TDateTimeFacetDescription">  
    <xs:attribute name="Constant" type="xs:boolean" default="false" />  
  </xs:complexType>  
  
  <xs:complexType name="TFacetDescriptions">  
    <xs:choice maxOccurs="unbounded">  
      <xs:element name="Precision" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Scale" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="MaxLength" minOccurs="0" maxOccurs="1" type="pm:TIntegerFacetDescription"/>  
      <xs:element name="Unicode" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
      <xs:element name="FixedLength" minOccurs="0" maxOccurs="1" type="pm:TBooleanFacetDescription"/>  
    </xs:choice>  
  </xs:complexType>  
  
  <xs:complexType name="TType">  
    <xs:sequence>  
      <xs:element name="FacetDescriptions" type="pm:TFacetDescriptions" minOccurs="0" maxOccurs="1"/>  
    </xs:sequence>  
    <xs:attribute name="Name" type="xs:string" use="required"/>  
    <xs:attribute name="PrimitiveTypeKind" type="pm:TPrimitiveTypeKind" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TTypes">  
    <xs:sequence>  
      <xs:element name="Type" type="pm:TType" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:attributeGroup name="TFacetAttribute">  
    <xs:attribute name="Precision" type="xs:int" use="optional"/>  
    <xs:attribute name="Scale" type="xs:int" use="optional"/>  
    <xs:attribute name="MaxLength" type="xs:int" use="optional"/>  
    <xs:attribute name="Unicode" type="xs:boolean" use="optional"/>  
    <xs:attribute name="FixedLength" type="xs:boolean" use="optional"/>  
  </xs:attributeGroup>  
  
  <xs:complexType name="TFunctionParameter">  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
    <xs:attribute name="Mode" type="pm:TParameterDirection" use="required" />  
  </xs:complexType>  
  
  <xs:complexType name="TReturnType">  
    <xs:attribute name="Type" type="xs:string" use="required" />  
    <xs:attributeGroup ref="pm:TFacetAttribute" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunction">  
    <xs:choice minOccurs="0" maxOccurs ="unbounded">  
      <xs:element name ="ReturnType" type="pm:TReturnType" minOccurs="0" maxOccurs="1" />  
      <xs:element name="Parameter" type="pm:TFunctionParameter" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:choice>  
    <xs:attribute name="Name" type="xs:string" use="required" />  
    <xs:attribute name="Aggregate" type="xs:boolean" use="optional" />  
    <xs:attribute name="BuiltIn" type="xs:boolean" use="optional" />  
    <xs:attribute name="StoreFunctionName" type="xs:string" use="optional" />  
    <xs:attribute name="NiladicFunction" type="xs:boolean" use="optional" />  
    <xs:attribute name="ParameterTypeSemantics" type="pm:TParameterTypeSemantics" use="optional" default="AllowImplicitConversion" />  
  </xs:complexType>  
  
  <xs:complexType name="TFunctions">  
    <xs:sequence>  
      <xs:element name="Function" type="pm:TFunction" minOccurs="0" maxOccurs="unbounded"/>  
    </xs:sequence>  
  </xs:complexType>  
  
  <xs:simpleType name="TPrimitiveTypeKind">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="Binary"/>  
      <xs:enumeration value="Boolean"/>  
      <xs:enumeration value="Byte"/>  
      <xs:enumeration value="Decimal"/>  
      <xs:enumeration value="DateTime"/>  
      <xs:enumeration value="Time"/>  
      <xs:enumeration value="DateTimeOffset"/>          
      <xs:enumeration value="Double"/>  
      <xs:enumeration value="Guid"/>  
      <xs:enumeration value="Single"/>  
      <xs:enumeration value="SByte"/>  
      <xs:enumeration value="Int16"/>  
      <xs:enumeration value="Int32"/>  
      <xs:enumeration value="Int64"/>  
      <xs:enumeration value="String"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterDirection">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="In"/>  
      <xs:enumeration value="Out"/>  
      <xs:enumeration value="InOut"/>  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:simpleType name="TParameterTypeSemantics">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="ExactMatchOnly" />  
      <xs:enumeration value="AllowImplicitPromotion" />  
      <xs:enumeration value="AllowImplicitConversion" />  
    </xs:restriction>  
  </xs:simpleType>  
</xs:schema>  
```  
  
#### <a name="types-node"></a>Typknoten  
 Der Typknoten des Anbietermanifests enthält Informationen über die Typen, die vom Datenspeicher oder Anbieter systemeigen unterstützt werden.  
  
##### <a name="type-node"></a>Typknoten  
 Jeder Typknoten definiert einen Anbietertyp mit EDM-Begriffen. Der Typknoten beschreibt den Namen des Anbietertyps, Informationen über den Modelltyp, dem er zugeordnet wird, und die Facets, mit denen die Typzuordnung beschrieben wird.  
  
 Um diese Typinformationen im Anbietermanifest auszudrücken, muss jede TypeInformation-Deklaration mehrere Facetbeschreibungen für die einzelnen Typen definieren:  
  
|Attributname|Datentyp|Erforderlich|Standardwert|Beschreibung|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|Name|Zeichenfolge|Ja|n/v|Anbieterspezifischer Datentypname|  
|PrimitiveTypeKind|PrimitiveTypeKind|Ja|n/v|EDM-Typenname|  
  
###### <a name="function-node"></a>Funktionsknoten  
 Jede Funktion definiert eine einzelne, über den Anbieter verfügbare Funktion.  
  
|Attributname|Datentyp|Erforderlich|Standardwert|Beschreibung|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|Name|Zeichenfolge|Ja|n/v|Bezeichner/Name der Funktion|  
|ReturnType|Zeichenfolge|Nein|Void|Der EDM-Rückgabetyp der Funktion|  
|Aggregat|Boolesch|Nein|False|"True", wenn es sich bei der Funktion um eine Aggregatfunktion handelt.|  
|BuiltIn|Boolesch|Nein|True|"True", wenn die Funktion in den Datenspeicher integriert ist.|  
|StoreFunctionName|Zeichenfolge|Nein|\<Name>|Funktionsname im Datenspeicher.  Ermöglicht eine Umleitungsebene für Funktionsnamen.|  
|NiladicFunction|Boolesch|Nein|False|"True", wenn die Funktion keine Parameter erfordert und ohne Parameter aufgerufen wird.|  
|ParameterType<br /><br /> Semantik|ParameterSemantics|Nein|AllowImplicit<br /><br /> Umwandeln|Hiermit kann ausgewählt werden, wie die Abfragepipeline mit Parametertypersetzung umgehen soll:<br /><br /> -   ExactMatchOnly<br />-AllowImplicitPromotion<br />-AllowImplicitConversion|  
  
 **Parameterknoten**  
  
 Jede Funktion verfügt über eine Auflistung von einem oder mehreren Parameterknoten.  
  
|Attributname|Datentyp|Erforderlich|Standardwert|Beschreibung|  
|--------------------|---------------|--------------|-------------------|-----------------|  
|Name|Zeichenfolge|Ja|n/v|Bezeichner/Name des Parameters.|  
|Typ|Zeichenfolge|Ja|n/v|Der EDM-Typ des Parameters.|  
|Modus|Parameter<br /><br /> Richtung|Ja|n/v|Richtung des Parameters:<br /><br /> -in<br />-out<br />-inout|  
  
##### <a name="namespace-attribute"></a>Namespace-Attribut  
 Jeder Datenspeicheranbieter muss einen Namespace oder eine Gruppe von Namespaces für die im Manifest definierten Informationen definieren. Dieser Namespace kann in Entity SQL-Abfragen verwendet werden, um Namen von Funktionen und Typen aufzulösen. Zum Beispiel: SqlServer. Dieser Namespace muss sich vom kanonischen Namespace "EDM" unterscheiden, der von den Entitätsdiensten für Standardfunktionen definiert wird, die von Entity SQL-Abfragen unterstützt werden sollen.  
  
## <a name="see-also"></a>Siehe auch

- [Schreiben eines Entity Framework-Datenanbieters](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
