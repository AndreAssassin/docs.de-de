---
title: 'Gewusst wie: Aktivieren von WebRequest zur Verwendung eines Proxys für die Internetkommunikation'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 63c0ef2c-44b5-4c54-9804-ba0b9b001ac7
ms.openlocfilehash: 8b38973e4cb2c83ce32b8a08e54d828a8eeef879
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73039541"
---
# <a name="how-to-enable-a-webrequest-to-use-a-proxy-to-communicate-with-the-internet"></a>Gewusst wie: Aktivieren von WebRequest zur Verwendung eines Proxys für die Internetkommunikation

In diesem Beispiel wird eine globale Proxyinstanz erstellt, die es jedem <xref:System.Net.WebRequest> ermöglicht, einen Proxy zu verwenden, um mit dem Internet zu kommunizieren. Im Beispiel wird davon ausgegangen, dass der Proxyserver `webproxy` heißt und auf Port 80 kommuniziert, dem Standard-HTTP-Port.

## <a name="example"></a>Beispiel

```csharp
var proxyObject = new WebProxy("http://webproxy:80/");
GlobalProxySelection.Select = proxyObject;
```

```vb
Dim proxyObject As New WebProxy("http://webproxy:80/")
GlobalProxySelection.Select = proxyObject
```

## <a name="compiling-the-code"></a>Kompilieren des Codes

Dieses Beispiel erfordert Folgendes:

- Eine [`using`-Anweisung](../../csharp/language-reference/keywords/using-directive.md) in C# für den Namespace **System.Net**
- Eine [`Imports`-Anweisung](../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) in Visual Basic für den Namespace **System.Net**

## <a name="see-also"></a>Weitere Informationen

- [Using Application Protocols (Verwenden von Anwendungsprotokollen)](using-application-protocols.md)
- [Accessing the Internet Through a Proxy (Zugreifen auf das Internet über einen Proxy)](accessing-the-internet-through-a-proxy.md)
