---
title: Erweitern von Metadaten mithilfe von Attributen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- metadata, extending
- attributes [.NET Framework], metadata
- elements [.NET Framework], attributes
- common language runtime, attributes
- annotating programming elements
- keyword-like descriptive declarations
- runtime, attributes
- extending metadata
ms.assetid: 30386922-1e00-4602-9ebf-526b271a8b87
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a31082604048e71ebc7581b36857a8bfbd333c2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61969792"
---
# <a name="extending-metadata-using-attributes"></a>Erweitern von Metadaten mithilfe von Attributen
Die Common Language Runtime (CLR) ermöglicht Ihnen, schlüsselwortähnliche beschreibende Deklarationen (sogenannte Attribute) hinzuzufügen, um Programmierelemente wie Typen, Felder, Methoden und Eigenschaften mit Anmerkungen zu versehen. Beim Kompilieren von Code für die Laufzeit wird dieser in die Microsoft Intermediate Language (MSIL) konvertiert und mit den vom Compiler generierten Metadaten in einer PE-Datei (Portable Executable) abgelegt. Mit Attributen können Sie Metadaten weitere beschreibende Informationen hinzufügen, die mit Reflexionsdiensten zur Laufzeit extrahiert werden können. Der Compiler erstellt Attribute, wenn Sie Instanzen spezieller Klassen deklarieren, die von <xref:System.Attribute?displayProperty=nameWithType> abgeleitet werden.   
  
 In .NET Framework werden Attribute aus unterschiedlichen Gründen eingesetzt und zur Lösung verschiedener Probleme verwendet. Attribute beschreiben das Serialisieren von Daten, legen Eigenschaften zum Erzwingen von Sicherheit fest und beschränken Optimierungen durch den JIT-Compiler (Just-In-Time), sodass auch weiterhin ein einfaches Debuggen des Codes möglich ist. Außerdem können Attribute auch einen Dateinamen oder den Verfasser von Code aufzeichnen oder  während der Entwicklung von Formularen die Sichtbarkeit von Steuerelementen und Membern steuern.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Anwenden von Attributen](../../../docs/standard/attributes/applying-attributes.md)|In diesem Abschnitt wird die Anwendung eines Attributs auf ein Codeelement beschrieben.|  
|[Verfassen von benutzerdefinierten Attributen](../../../docs/standard/attributes/writing-custom-attributes.md)|Beschreibt, wie benutzerdefinierte Attributklassen entworfen werden.|  
|[Abrufen von Informationen aus Attributen](../../../docs/standard/attributes/retrieving-information-stored-in-attributes.md)|Beschreibt, wie benutzerdefinierte Attribute für Code abgerufen werden, der in den Ausführungskontext geladen wird.|  
|[Metadaten und selbstbeschreibende Komponenten](../../../docs/standard/metadata-and-self-describing-components.md)|Dieser Abschnitt enthält  eine Übersicht über Metadaten und beschreibt ihre Implementierung in einer .NET Framework-PE-Datei (Portable Executable).|  
|[Vorgehensweise: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) (Gewusst wie: Laden von Assemblys in den auf Reflektion beschränkten Kontext)|Erläutert das Abrufen benutzerdefinierter Attributinformationen in den ausschließlich reflektionsbezogenen Kontext.|  
  
## <a name="reference"></a>Referenz  
 <xref:System.Attribute?displayProperty=nameWithType>
