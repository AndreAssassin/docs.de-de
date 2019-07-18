---
title: Erweitern von ServiceHost und der Dienstmodellebene
ms.date: 03/30/2017
helpviewer_keywords:
- extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
ms.openlocfilehash: 9e08b5b7b11848262d2cb7b6ed5715799d597889
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991769"
---
# <a name="extending-servicehost-and-the-service-model-layer"></a>Erweitern von ServiceHost und der Dienstmodellebene
Die Dienstmodellebene ist dafür verantwortlich, eingehende Nachrichten aus den zugrunde liegenden Kanälen abzufangen, sie in Methodenaufrufe per Anwendungscode zu übersetzen und die Ergebnisse zurück an den Aufrufer zu senden. Dienstmodellerweiterungen ändern bzw. implementieren Ausführungs- oder Kommunikationsverhalten und Funktionen wie Verteileroptionen, benutzerdefiniertes Verhalten, Nachrichten- oder Parameterinterceptoren und andere Erweiterbarkeitsfunktionen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Erweitern von Clients](../../../../docs/framework/wcf/extending/extending-clients.md)  
 Beschreibt die Schnittstellen, die die Client-Runtime abfangen und bearbeiten können, sowie die Klassen, in die Sie Ihre benutzerdefinierten Erweiterungen in Clientanwendungen einfügen können. Sie können beispielsweise eine benutzerdefinierte Clientnachrichtenprotokollierung, benutzerdefinierte Nachrichtenserialisierung usw. durchführen.  
  
 [Erweitern von Verteilern](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 Beschreibt die Schnittstellen, die die Dienst-Runtime abfangen und bearbeiten können, sowie die Klassen, in die Sie Ihre benutzerdefinierten Erweiterungen in Dienstanwendungen einfügen können. Sie können beispielsweise eine benutzerdefinierte Dienstprotokollierung, eine Nachrichtenvalidierung aufseiten des Dienstes, einen benutzerdefinierten Versand usw. durchführen.  
  
 [Erweiterbare Objekte](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 Beschreibt die fünf erweiterbaren Objekte und das <xref:System.ServiceModel.IExtensibleObject%601>-Muster. Das erweiterbare Objektmuster wird verwendet, um entweder vorhandene Laufzeitklassen um neue Funktionen zu erweitern oder um einem Objekt neue Zustandsfunktionen hinzuzufügen. Erweiterungen, die einem der erweiterbaren Objekte zugeordnet sind, ermöglichen es Verhalten in verschiedenen Phasen der Verarbeitung, auf gemeinsam verwendete Zustände und Funktionen zuzugreifen, die an ein zugängliches und allgemeines erweiterbares Objekt angefügt sind.  
  
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 Zum Ändern von Einstellungen auf, oder fügen Sie die Erweiterungen in der WCF-Laufzeit, verwenden Sie Verhalten. WCF umfasst vom System implementierte Verhalten zum Steuern von Einschränkungen, Instanzen und anderen Dienst- und Vorgangsaspekten. Dieser Abschnitt beschreibt, wie Sie Ihre eigenen benutzerdefinierten Verhalten erstellen und sie programmatisch bzw. mit Konfigurationsdateien verfügbar machen können.  
  
 [Erweitern des Hosting mit ServiceHostFactory](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 Beschreibt, wie Sie <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> erweitern und die <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType>-Klassen verwenden können, um die Hostumgebung anzupassen.  
  
## <a name="reference"></a>Referenz  
  
## <a name="related-sections"></a>Verwandte Abschnitte
