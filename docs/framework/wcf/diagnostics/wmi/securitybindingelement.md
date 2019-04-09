---
title: SecurityBindingElement
ms.date: 03/30/2017
ms.assetid: ef93b6e6-3524-48a8-94d3-c8837f1872f9
ms.openlocfilehash: 1d367d0c5d14e6e75539dd2b20cdffcf2b34963d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153854"
---
# <a name="securitybindingelement"></a>SecurityBindingElement
SecurityBindingElement  
  
## <a name="syntax"></a>Syntax  
  
```csharp
class SecurityBindingElement : BindingElement  
{  
  string DefaultAlgorithmSuite;  
  boolean IncludeTimestamp;  
  string KeyEntropyMode;  
  LocalServiceSecuritySettings LocalServiceSecuritySettings;  
  string MessageSecurityVersion;  
  string SecurityHeaderLayout;  
};  
```  
  
## <a name="methods"></a>Methoden  
 Die SecurityBindingElement-Klasse definiert keine Methoden.  
  
## <a name="properties"></a>Eigenschaften  
 Die SecurityBindingElement-Klasse verfügt über die folgenden Eigenschaften:  
  
### <a name="defaultalgorithmsuite"></a>DefaultAlgorithmSuite  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Gibt die Algorithmen an, die mit der Bindung verwendet werden sollen.  
  
### <a name="includetimestamp"></a>IncludeTimestamp  
 Datentyp: Boolesch  
  
 Zugriffstyp: Schreibgeschützt  
  
 Ein boolescher Wert, der angibt, ob jede Nachricht einen Timestamp enthält.  
  
### <a name="keyentropymode"></a>KeyEntropyMode  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Entropiequelle zum Erstellen von Schlüsseln.  
  
### <a name="localservicesecuritysettings"></a>LocalServiceSecuritySettings  
 Datentyp: LocalServiceSecuritySettings  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die bindungsspezifischen Sicherheitseigenschaften für den lokalen Dienst.  
  
### <a name="messagesecurityversion"></a>MessageSecurityVersion  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die für Nachrichtensicherheit verwendete Version.  
  
### <a name="securityheaderlayout"></a>SecurityHeaderLayout  
 Datentyp: string (Zeichenfolge)  
  
 Zugriffstyp: Schreibgeschützt  
  
 Die Reihenfolge der Elemente im Sicherheitsheader für diese Bindung.  
  
## <a name="requirements"></a>Anforderungen  
  
|MOF|Deklariert in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Namespace|Definiert in root\ServiceModel|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Channels.SecurityBindingElement>
