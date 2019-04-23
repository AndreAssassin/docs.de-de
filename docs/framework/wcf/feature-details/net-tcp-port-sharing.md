---
title: Net.TCP-Anschlussfreigabe
ms.date: 03/30/2017
helpviewer_keywords:
- port activation [WCF]
- port sharing [WCF]
ms.assetid: f13692ee-a179-4439-ae72-50db9534eded
ms.openlocfilehash: b04266b15f786e3a5a93ac1e9fff1754c397ccd4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073688"
---
# <a name="nettcp-port-sharing"></a>Net.TCP-Anschlussfreigabe
Windows Communication Foundation (WCF) bietet ein neue TCP-basiertes Netzwerkprotokoll (net.tcp://) für hochleistungskommunikation. WCF stellt auch eine neue Systemkomponente, die Net.TCP-Portfreigabedienst, mit dem net.tcp-Ports für mehrfache Benutzervorgänge freigegeben werden können.  
  
## <a name="background-and-motivation"></a>Hintergrund und Motivation  
 Als das TCP/IP-Protokoll erstmals eingeführt wurde, wurde es nur von einer geringen Anzahl von Anwendungsprotokollen verwendet. TCP/IP verwendete Anschlussnummern, um zwischen Anwendungen zu unterscheiden, indem es jedem Anwendungsprotokoll eine eindeutige 16-bit-Anschlussnummer zuwies. HTTP-Verkehr verwendet heute beispielsweise standardmäßig den TCP-Anschluss 80, SMTP verwendet den TCP-Anschluss 25, und FTP verwendet die TCP-Anschlüsse 20 und 21. Andere Anwendungen, die TCP als Transport verwenden, können eine weitere verfügbare Anschlussnummer wählen, entweder durch Konventionen oder durch formale Standardisierung.  
  
 Die Verwendung von Anschlussnummern zur Unterscheidung zwischen Anwendungen barg Sicherheitsprobleme. Firewalls sind in der Regel so konfiguriert, dass Sie TCP-Verkehr an allen Anschlüssen außer den wenigen wohlbekannten Eingangspunkten blockieren, sodass die Bereitstellung einer Anwendung, die einen Nicht-Standardanschluss verwendet, durch das Vorhandensein firmenspezifischer oder persönlicher Firewalls oft kompliziert oder sogar unmöglich ist. Anwendungen, die über bekannten, bereits zugelassene Standardanschlüsse kommunizieren können, verringern die Angriffsfläche für externe Angriffe. Viele Netzwerkanwendungen verwenden das HTTP-Protokoll, da die meisten Firewalls standardmäßig so konfiguriert sind, dass sie Verkehr am TCP-Anschluss&amp;#160;80 zulassen.  
  
 Das HTTP.SYS-Modell, in dem der Verkehr für viele verschiedene HTTP-Anwendungen als Multiplex über einen einzelnen TCP-Anschluss geleitet wird, ist heute Standard auf der Windows-Plattform. Dies bietet Firewalladministratoren einen gemeinsamen Steuerungspunkt, und bietet zugleich Anwendungsentwicklern die Möglichkeit, die Bereitstellungskosten beim Erstellen neuer Anwendungen, die das Netzwerk verwenden können, zu minimieren.  
  
 Die Möglichkeit, Anschlüsse für mehrere HTTP-Anwendungen freizugeben ist schon lange eine Funktion von Internetinformationsdiensten (Internet Information Services, IIS). Jedoch wurde diese Infrastruktur erst mit der Einführung von HTTP.SYS (dem Kernelmoduslistener des HTTP-Protokolls) durch [!INCLUDE[iis601](../../../../includes/iis601-md.md)] vollständig generalisiert. Tatsächlich ermöglicht HTTP.SYS es beliebigen Benutzerprozessen, die für HTTP-Verkehr vorgesehen TCP-Anschlüsse gemeinsam zu verwenden. Durch diese Fähigkeit können zahlreiche HTTP-Anwendungen auf dem selben physischen Gerät in getrennten, isolierten Prozessen koexistieren und dabei die zum Senden und Empfangen von Verkehr über den TCP-Anschluss 80 erforderliche Netzwerkinfrastruktur gemeinsam verwenden. Der Net.TCP-Portfreigabedienst ermöglicht die gleiche Art der Anschlussfreigabe für net.tcp-Anwendungen.  
  
## <a name="port-sharing-architecture"></a>Architektur der Anschlussfreigabe  
 Die anschlussfreigabearchitektur in WCF umfasst drei Hauptkomponenten:  
  
-   Ein Arbeitsprozess: Jeder Prozess über freigegebener Anschlüsse über net.tcp:// kommuniziert.  
  
-   Der WCF-TCP-Transport: Implementiert das net.tcp://-Protokoll.  
  
-   Der Net.TCP-Portfreigabedienst: Ermöglicht mehreren Arbeitsprozessen, die den gleichen TCP-Port verwenden.  
  
 Der Net.TCP-Portfreigabedienst ist ein Windows-Dienst im Benutzermodus, der net.tcp://-Verbindungen im Namen von Arbeitsprozessen akzeptiert, die sich über ihn verbinden. Wenn eine Socketverbindung ankommt, untersucht der Portfreigabedienst den eingehenden Nachrichtenstrom, um dessen Zieladresse zu erhalten. Basierend auf dieser Adresse kann der Portfreigabedienst den Datenstrom zu der Anwendung weiterleiten, die ihn letztendlich verarbeitet.  
  
 Wenn ein WCF-Dienst, der net.tcp:// anschlussfreigabedienst wird verwendet, ist der WCF-TCP-Transportinfrastruktur nicht direkt einen TCP-Socket im Anwendungsprozess geöffnet werden. Stattdessen registriert die Transportinfrastruktur den Basisadressen-URI (Uniform Resource Identifier) des Dienstes mit dem Net.TCP-Portfreigabedienst und wartet darauf, dass der Portfreigabedienst in ihrem Namen den Eingang von Nachrichten abhört.  Der Portfreigabedienst leitet an den Anwendungsdienst adressierte Nachrichten bei Eingang weiter.  
  
## <a name="installing-port-sharing"></a>Installieren der Anschlussfreigabe  
 Der Net.TCP-Portfreigabedienst steht auf allen Betriebssystemen, die [!INCLUDE[vstecwinfx](../../../../includes/vstecwinfx-md.md)] unterstützen zur Verfügung, aber der Dienst ist nicht standardmäßig aktiviert. Als Sicherheitsmaßnahme muss der Net.TCP-Portfreigabedienst vor der ersten Verwendung manuell von einem Administrator aktiviert werden. Der Net.TCP-Portfreigabedienst stellt Konfigurationsoptionen zur Verfügung, mit denen Sie einige Merkmale der dem Portfreigabedienst gehörenden Netzwerksockets ändern können. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md).  
  
## <a name="using-nettcp-port-sharing-in-an-application"></a>Verwenden der Net.tcp-Anschlussfreigabe in einer Anwendung  
 Die einfachste Möglichkeit zum net.tcp://-Anschlussfreigabe in der WCF-Anwendung zu verwenden ist, einen Dienst mit verfügbar machen die <xref:System.ServiceModel.NetTcpBinding> und die anschließende Aktivieren des Net.TCP-Portfreigabedienst mithilfe der <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> Eigenschaft.  
  
 Weitere Informationen hierzu finden Sie unter [Vorgehensweise: Konfigurieren ein WCF-Diensts für die Portfreigabe](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md).  
  
## <a name="security-implications-of-port-sharing"></a>Sicherheitsauswirkungen der Anschlussfreigabe  
 Obwohl der Net.TCP-Portfreigabedienst eine Verarbeitungsschicht zwischen Anwendungen und dem Netzwerk bereitstellt, sollten Anwendungen, die die Anschlussfreigabe nutzen, zusätzlich so gesichert werden, als würden sie das Netzwerk direkt überwachen. Insbesondere sollten Anwendungen, die die Anschlussfreigabe nutzen, die Prozessprivilegien auswerten, unter denen sie ausgeführt werden. Ziehen Sie in Betracht, die Anwendung unter dem integrierten Netzwerkdienstkonto auszuführen, das mit der minimalen Gruppe der zur Netzwerkkommunikation erforderlichen Privilegien ausgeführt wird.  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren des Net.TCP-Portfreigabediensts](../../../../docs/framework/wcf/feature-details/configuring-the-net-tcp-port-sharing-service.md)
- [Hosting](../../../../docs/framework/wcf/feature-details/hosting.md)
- [Vorgehensweise: Konfigurieren eines WCF-Diensts für die Portfreigabe](../../../../docs/framework/wcf/feature-details/how-to-configure-a-wcf-service-to-use-port-sharing.md)
- [Vorgehensweise: Aktivieren des Net.TCP-Portfreigabediensts](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md)
