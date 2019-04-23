---
title: 'Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer'
ms.date: 04/07/2017
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3355841298e039652eb81918eac98186c1a1f833
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182116"
---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a><span data-ttu-id="f6dfa-102">Entschärfung: Serialisierung von Steuerzeichen mit dem DataContractJsonSerializer</span><span class="sxs-lookup"><span data-stu-id="f6dfa-102">Mitigation: Serialization of Control Characters with the DataContractJsonSerializer</span></span>

<span data-ttu-id="f6dfa-103">Für Apps von .NET Framework 4.7 an hat sich die Serialisierung von Steuerzeichen mit dem <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> geändert und entspricht nun ECMAScript V6 und V8.</span><span class="sxs-lookup"><span data-stu-id="f6dfa-103">Starting with the .NET Framework 4.7, the way in which control characters are serialized with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> has changed to conform to ECMAScript V6 and V8.</span></span> 
 
## <a name="impact"></a><span data-ttu-id="f6dfa-104">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="f6dfa-104">Impact</span></span>

<span data-ttu-id="f6dfa-105">In .NET Framework 4.6.2 und früheren Versionen serialisierte der <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> einige besondere Steuerzeichen, wie etwa `\b`, `\f` und `\t` nicht in einer Weise, die mit den ECMAScript V6- und V8-Standards kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="f6dfa-105">In the .NET framework 4.6.2 and earlier versions, the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> did not serialize some special control characters, such as `\b`, `\f`, and `\t`, in a way that was compatible with the ECMAScript V6 and V8 standards.</span></span>

<span data-ttu-id="f6dfa-106">Für Apps mit Zielversionen von .NET Framework ab .NET Framework 4.7 ist die Serialisierung dieser Steuerzeichen mit ECMAScript V6 und V8 kompatibel.</span><span class="sxs-lookup"><span data-stu-id="f6dfa-106">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, serialization of these control characters is compatible with ECMAScript V6 and V8.</span></span> <span data-ttu-id="f6dfa-107">Dies betrifft die folgenden APIs:</span><span class="sxs-lookup"><span data-stu-id="f6dfa-107">The following APIs are affected:</span></span>

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a><span data-ttu-id="f6dfa-108">Minderung</span><span class="sxs-lookup"><span data-stu-id="f6dfa-108">Mitigation</span></span>

<span data-ttu-id="f6dfa-109">Für Apps mit Zielversionen von .NET Framework ab .NET Framework 4.7 ist dieses Verhalten standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f6dfa-109">For apps that target versions of the .NET Framework starting with the .NET Framework 4.7, this behavior is enabled by default.</span></span>

<span data-ttu-id="f6dfa-110">Wenn dieses Verhalten unerwünscht ist, können Sie sich gegen diese Funktion entscheiden, indem Sie dem Abschnitt `<runtime>` der app.config- oder web.config-Datei die folgende Zeile hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f6dfa-110">If this behavior is not desirable, you can opt out of this feature by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a><span data-ttu-id="f6dfa-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6dfa-111">See also</span></span>

- [<span data-ttu-id="f6dfa-112">Änderungen der Neuzuweisungen in .NET Framework 4.7</span><span class="sxs-lookup"><span data-stu-id="f6dfa-112">Retargeting Changes in the .NET Framework 4.7</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)
