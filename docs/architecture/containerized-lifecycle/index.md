---
title: Einführung in Container und Docker
description: Verschaffen Sie sich einen allgemeinen Überblick der Hauptvorteile beim Einsatz von Docker.
ms.date: 02/15/2019
ms.openlocfilehash: 9ac08a64cd2465b4b88a266c1ec0925f37680bf9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73738173"
---
# <a name="introduction-to-containers-and-docker"></a>Einführung in Container und Docker

*Das Containerisieren ist ein Ansatz in der Softwareentwicklung, bei dem eine Anwendung oder ein Dienst sowie die zugehörigen Abhängigkeiten und Konfigurationen (abstrahiert als Bereitstellungsmanifestdateien) zusammen als Containerimage verpackt werden. Die Containeranwendung kann anschließend als Einheit getestet und als Instanz eines Containerimages für das Hostbetriebssystem bereitgestellt werden.*

So wie das Versenden von Containern es ermöglicht, Güter unabhängig von der enthaltenen Fracht per Schiff, Zug oder LKW zu transportieren, agieren Softwarecontainer als Standardeinheit für Softwarebereitstellung und können verschiedenen Code und verschiedene Abhängigkeiten enthalten. Das Containerisieren von Software auf diese Weise ermöglicht es Entwicklern und IT-Experten, diese ohne oder mit geringfügigen Änderungen in verschiedenen Umgebungen bereitzustellen.

Container isolieren Anwendungen auf einem gemeinsamen Betriebssystem außerdem voneinander. Containeranwendungen werden auf einem Containerhost ausgeführt, der auf dem Betriebssystem (Linux oder Windows) ausgeführt wird. Daher haben Container einen viel geringeren Speicherbedarf als die Images für virtuelle Computer (VM).

Jeder Container kann wie in Abbildung 1-1 gezeigt eine gesamte Webanwendung oder einen gesamten Dienst ausführen. In diesem Beispiel ist Docker-Host ein Containerhost und App1, App2, Svc1 und Svc2 sind die Containeranwendungen oder -dienste.

![Diagramm, das vier Container zeigt, die auf einem virtuellen Computer oder einem Server ausgeführt werden.](./media/index/multiple-containers-single-host.png)

**(Abbildung 1-1)** . Mehrere Container, die auf einem Containerhost ausgeführt werden

Ein weiterer Vorteil, den Containerisierung mit sich bringt, ist die Skalierbarkeit. Ein schnelles Skalieren ist möglich, indem Sie neue Container für kurzfristige Aufgaben erstellen. Aus der Sicht einer Anwendung ähnelt das Instanziieren eines Images (Erstellen eines Containers) dem Instanziieren eines Prozesses wie ein Dienst oder eine Web-App. Für die Zuverlässigkeit beim Ausführen von mehreren Instanzen desselben Images auf mehreren Hostservern sollte jedoch jeder Container (Instanz des Images) auf einem anderen Hostserver oder virtuellen Computer in verschiedenen Fehlerdomänen ausgeführt werden.

Kurz gesagt bieten Container die Vorteile der Isolation, Portabilität, Agilität, Skalierbarkeit und Steuerung des gesamten Workflows des Lebenszyklus der Anwendung. Der wichtigste Vorteil ist die Isolation der Umgebung zwischen Entwicklung und Betrieb (Dev and Ops).

>[!div class="step-by-step"]
>[Nächste](what-is-docker.md)
