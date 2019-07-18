---
title: Identifizieren von Domänenmodellgrenzen für Microservices
description: Lernen Sie die wesentlichen Grundlagen der Partitionierung einer großen Anwendung in Microservices kennen, um eine stabile Architektur zu erzielen.
ms.date: 09/20/2018
ms.openlocfilehash: aa903e13b20be1084fad60e6fb7bbb1c61403deb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644393"
---
# <a name="identify-domain-model-boundaries-for-each-microservice"></a>Identifizieren von Domänenmodellgrenzen für Microservices

Beim Identifizieren von Modellgrenzen und -größen für die einzelnen Microservices geht es nicht so sehr darum, eine möglichst kleinteilige Gliederung zu finden, wenngleich Sie sich um möglichst kleine Microservices bemühen sollten. Vielmehr geht es darum, dass Sie geleitet von Ihrem Wissen über die Domäne eine möglichst sinnvolle Gliederung vornehmen. Der Schwerpunkt liegt nicht auf der Größe, sondern auf den geschäftlichen Funktionen. Ferner ist für einen bestimmten Bereich der Anwendung aufgrund einer großen Anzahl von Abhängigkeiten möglicherweise eine klare Kohäsion gefordert, sodass nur ein einziger Microservice erstellt werden sollte. Kohäsion stellt eine Möglichkeit der Gliederung oder Gruppierung von Microservices dar. Letztlich sollten Sie die Größe Ihres Microservices immer wieder anpassen, je mehr Wissen über die Domäne Sie erlangen. Die Suche nach der richtigen Größe ist kein einmaliger Vorgang.

[Sam Newman](https://samnewman.io/), ein anerkannter Befürworter von Microservices und Autor von [Microservices: Konzeption und Design](https://samnewman.io/books/building_microservices/), weist darauf hin, dass Microservices auf Basis des bereits vorgestellten Konzepts von Kontextgrenzen (Teil des domänengesteuertes Designs) konzipiert und entworfen werden sollten. Eine Kontextgrenze kann aus mehreren physischen Diensten bestehen, aber nicht umgekehrt.

Ein Domänenmodell mit bestimmten Domänenentitäten kommt in einer konkreten Kontextgrenze oder in einem konkreten Microservice zum Tragen. Eine Kontextgrenze schränkt die Anwendbarkeit eines Domänenmodells ein und vermittelt den Mitgliedern des Entwicklerteams ein klares und einheitliches Verständnis davon, welche Teile kohäsiv sein müssen und welche unabhängig voneinander entwickelt werden können. Dieselben Ziele gelten für Microservices.

Ein weiterer Faktor, der Ihre Entwurfsentscheidung beeinflusst, ist das [Gesetz von Conway](https://en.wikipedia.org/wiki/Conway%27s_law), das besagt, dass eine Anwendung die sozialen Grenzen der Organisation widerspiegelt, die sie erstellt. Manchmal verhält es sich jedoch genau umgekehrt: Die Organisation eines Unternehmens wird durch die Software bestimmt. Möglicherweise müssen Sie das Gesetz von Conway umkehren und die Grenzen, in Anlehnung an Beratungsergebnisse hinsichtlich der Geschäftsprozesse, entsprechend der gewünschten Organisation Ihres Unternehmens definieren.

Um Kontextgrenzen zu identifizieren, können Sie ein DDD-Muster (Domain Driven Design) verwenden, das als [Kontextzuordnungsmuster](https://www.infoq.com/articles/ddd-contextmapping) bezeichnet wird. Bei der Kontextzuordnung geht es um die Identifizierung von verschiedenen Kontexten und deren Grenzen in der Anwendung. Üblicherweise werden für jedes kleine Subsystem ein eigener Kontext und eine eigene Grenze definiert. Dabei stellt die Kontextzuordnung ein Mittel zum Definieren und Verdeutlichen der Grenzen zwischen Domänen dar. Eine Kontextgrenze ist autonom, enthält die Details einer einzelnen Domäne, wie etwa die Domänenentitäten, und definiert Integrationsverträge mit anderen Kontextgrenzen. Dies ist mit der Definition eines Microservice vergleichbar: Ein Microservice ist autonom, implementiert bestimmte Domänenfunktionen und muss Schnittstellen bereitstellen. Daher sind Kontextzuordnung und das Konzept der Kontextgrenze gute Methoden für die Identifizierung der Domänenmodellgrenzen von Microservices.

Beim Entwickeln einer großen Anwendung werden Sie erkennen, wie das Domänenmodell fragmentiert werden kann – ein Domänenexperte aus der Katalogdomäne wird Entitäten in Katalog- und Bestandsdomänen anders nennen als beispielsweise ein Versanddomänenexperte. Die Benutzerdomänenentität weist beispielsweise bei einem CRM-Experten, der alle Details zum Kunden speichern möchte, eine andere Größe und Attributzahl auf, als bei einem Bestelldomänenexperten, der nur bestimmte Kundendaten benötigt. Es ist sehr schwierig, alle Domänenbegriffe über alle Domänen in einer großen Anwendung hinweg eindeutig zu definieren. Das Wichtigste ist jedoch, dass Sie nicht versuchen sollten, die Begriffe zu vereinheitlichen. Akzeptieren Sie die Unterschiede und die Vielfalt, die jede Domäne einbringt. Wenn Sie versuchen, für die gesamte Anwendung eine einheitliche Datenbank zu entwickeln, führt der Versuch, ein einheitliches Vokabular zu erstellen, zu merkwürdigen Begriffen, die für keinen der vielen Domänenexperten richtig klingen. Daher helfen (in Form von Microservices implementierte) Kontextgrenzen bei der Klärung, an welchen Stellen bestimmte Domänenbegriffe verwendet werden können und an welchen Stellen das System aufgeteilt und zusätzliche Kontextgrenzen mit anderen Domänen erstellt werden müssen.

Sie wissen, dass Sie die richtigen Grenzen und Größen für die einzelnen Kontextgrenzen und Domänenmodelle gefunden haben, wenn wenige starke Beziehungen zwischen Domänenmodellen vorhanden sind und Sie beim Durchführen typischer Anwendungsvorgänge keine Informationen aus mehreren Domänenmodellen zusammenführen müssen.

Die vielleicht beste Antwort auf die Frage, wie groß ein Domänenmodell für einzelne Microservices sein muss, ist folgende: Es sollte autonome, möglichst isolierte Kontextgrenzen aufweisen und Ihnen die Arbeit ohne ständiges Wechseln zu anderen Kontexten (Modellen anderer Microservices) ermöglichen. Abbildung 4-10 zeigt, wie für mehrere Microservices (mehrere Kontextgrenzen) je nach Anforderungen der einzelnen, in Ihrer Anwendung identifizierten Domänen eigene Modelle und Entitäten definiert werden können.

![Entitäten in verschiedenen Modellgrenzen (Kontextgrenzen), wobei die gleiche Entität je nach Kontextgrenze als „Benutzer“, „Käufer“, „Zahler“ und „Kunden“ angezeigt wird](./media/image10.png)

**Abbildung 4-10**. Identifizieren von Entitäten und Microservice-Modellgrenzen

In Abbildung 4-10 ist ein Beispielszenario für ein System zur Verwaltung von Onlinekonferenzen dargestellt. Basierend auf Domänen, die Domänenexperten für Sie definiert haben, haben Sie verschiedene Kontextgrenzen identifiziert, die als Microservices implementiert werden können. Wie Sie sehen, sind einige Entitäten nur in einem Microservicemodell vorhanden, wie etwa „Zahlungen“ im Microservice „Zahlungen“. Diese lassen sich einfach implementieren.

Es können jedoch auch Entitäten vorhanden sein, die eine andere Form aufweisen, jedoch dieselbe Identität über die verschiedenen Domänenmodelle aus den verschiedenen Microservices hinweg teilen. So lässt sich beispielsweise die Entität „Benutzer“ im Microservice „Konferenzenmanagement“ identifizieren. Dieser Benutzer mit dieser Identität wird im Microservice „Bestellungen“ als „Käufer“ bzw. im Microservice „Zahlung“ als „Zahlender“ und im Microservice „Kundenservice“ als „Kunde“ bezeichnet. Grund dafür ist, dass ein Benutzer je nach der von den einzelnen Domänenexperten verwendeten [ubiquitären Sprache](https://martinfowler.com/bliki/UbiquitousLanguage.html) eine unterschiedliche Perspektive mit unterschiedlichen Attributen aufweisen kann. Die Benutzerentität im Microservicemodell „Konferenzenmanagement“ enthält möglicherweise die meisten der Attribute mit persönlichen Daten. Dieser Benutzer benötigt als „Zahlender“ im Microservice „Zahlung“ oder als „Kunde“ im Microservice „Kundenservice“ möglicherweise nicht dieselben Attribute.

Ein ähnliches Konzept ist in Abbildung 4-11 dargestellt.

![Wenn Sie in herkömmliches Datenmodell auf verschiedene Kontextgrenzen aufteilen, können Sie verschiedene Entitäten mit der gleichen Identität einrichten (ein Käufer ist gleichzeitig ein Benutzer), die in den einzelnen Kontextgrenzen unterschiedliche Attribute aufweisen.](./media/image11.png)

**Abbildung 4-11**. Zerlegen von herkömmlichen Datenmodellen in mehrere Domänenmodelle

Wie Sie sehen, ist der Benutzer im Microservicemodell „Konferenzenmanagement“ als Entität „Benutzer“ und im Microservice „Preise“ als Entität „Käufer“ mit jeweils anderen Attributen oder Details vorhanden. Nicht für jeden Microservice bzw. für jede Kontextgrenze sind alle Daten einer Benutzerentität erforderlich. Welche Daten erforderlich sind, hängt von dem zu lösenden Problem oder vom Kontext ab. Im Microservicemodell „Preise“ werden beispielsweise Adresse und Name des Benutzers nicht benötigt, sondern nur die ID (als Identität) und der Status, was sich bei der Preisgestaltung für die Lizenzen pro Käufer auf Rabatte auswirkt.

Die Entität „Lizenz“ hat zwar in allen Domänenmodellen denselben Namen, weist jedoch unterschiedliche Attribute auf. „Lizenz“ nutzt „Identität“ basierend auf derselben ID wie „Benutzer“ und „Käufer“.

Grundsätzlich gibt es in verschiedenen Diensten (Domänen), die alle die Identität eines Benutzers gemeinsam verwenden, ein gemeinsames Konzept eines Benutzers. In den einzelnen Domänenmodellen werden jedoch möglicherweise zusätzliche oder andere Details zur Benutzerentität verwendet. Daher muss es eine Möglichkeit geben, eine Benutzerentität aus einer Domäne (einem Microservice) einer anderen zuzuordnen.

Es hat verschiedene Vorteile, eine Benutzerentität nicht mit derselben Anzahl von Attributen in allen Domänen zu verwenden. Ein Vorteil ist der, dass weniger Duplikate vorhanden sind, sodass Microservicemodelle nur über die tatsächlich benötigten Daten verfügen. Ein weiterer Vorteil besteht darin, dass ein Mastermicroservice vorhanden ist, der pro Entität einen bestimmten Datentyp aufweist, sodass Updates und Abfragen für diesen Datentyp nur von diesem Microservice unterstützt werden.

>[!div class="step-by-step"]
>[Zurück](distributed-data-management.md)
>[Weiter](direct-client-to-microservice-communication-versus-the-api-gateway-pattern.md)
