---
title: Netzwerkablaufverfolgung in .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- debugging [.NET Framework], network tracing
- methods, network tracing
- Networking
- trace enabled debugging
- network tracing, about network tracing
- network tracing
- network, network tracing
- traffic tracing
- tracing [.NET Framework], network
- deploying applications [.NET Framework], network traffic
- capturing network traffic
- Internet, network tracing
- Network Resources
- output, network tracing
- method invocations
ms.assetid: e993b7c3-087f-45d8-9c02-9dded936d804
ms.openlocfilehash: 45ec7b83824777c594b966a38d2b7fcd4f63b596
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221188"
---
# <a name="network-tracing-in-the-net-framework"></a>Netzwerkablaufverfolgung in .NET Framework
Die Netzwerkablaufverfolgung im .NET Framework bietet Zugriff auf Informationen über den Aufruf von Methoden sowie Informationen zu dem von einer Anwendung generierten Netzwerkdatenverkehr. Dies ist nützlich für das Debuggen bei der Anwendungsentwicklung und für die Analyse von bereitgestellten Anwendungen. Die bei der Netzwerkablaufverfolgung ausgegebenen Informationen können für verschiedene Szenarien bei der Entwicklung und in Produktionsumgebungen angepasst werden.  
  
 Um die Netzwerkablaufverfolgung in .NET Framework zu aktivieren, müssen Sie ein Ziel für die Ausgabe der Ablaufverfolgung auswählen und Konfigurationseinstellungen für die Ablaufverfolgung entweder der Anwendungs- oder der Computerkonfigurationsdatei hinzufügen. Beschreibungen von Konfigurationsdateien und ihrer Verwendung finden Sie unter [Konfigurationsdateien](../../../docs/framework/configure-apps/index.md). Informationen zur Aktivierung der Netzwerkablaufverfolgung finden Sie unter [Aktivieren der Netzwerkablaufverfolgung](../../../docs/framework/network-programming/enabling-network-tracing.md). Informationen zu den Einstellungen, die Sie der Konfigurationsdatei hinzufügen müssen, finden Sie unter [Vorgehensweise: Konfigurieren der Netzwerkablaufverfolgung](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).  
  
 Wenn die Ablaufverfolgung aktiviert ist, können Sie Ablaufverfolgungsinformationen sammeln, die von **System.Net**-Klassen ausgegeben werden. Member der Netzwerklassen, die Ablaufverfolgungsinformationen generieren, enthalten den folgenden Text im Abschnitt "Hinweise" ihrer .NET Framework-Klassenbibliotheksdokumentation:  
  
> [!NOTE]
>  Dieser Member gibt Ablaufverfolgungsinformationen aus, wenn Sie die Netzwerkablaufverfolgung in der Anwendung aktivieren. Weitere Informationen finden Sie unter "Netzwerkablaufverfolgung".  
  
## <a name="see-also"></a>Siehe auch

- [Aktivieren der Netzwerkablaufverfolgung](../../../docs/framework/network-programming/enabling-network-tracing.md)
- [Vorgehensweise: Konfigurieren der Netzwerkablaufverfolgung](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)
- [Interpretieren von Netzwerkablaufverfolgung](../../../docs/framework/network-programming/interpreting-network-tracing.md)
- [Ablaufverfolgung und Instrumentieren von Anwendungen](../../../docs/framework/debug-trace-profile/tracing-and-instrumenting-applications.md)
