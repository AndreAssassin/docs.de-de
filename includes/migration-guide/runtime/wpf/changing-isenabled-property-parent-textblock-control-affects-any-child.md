---
ms.openlocfilehash: 38dd0b33202b8e8f1708ebec689333bd5367c93f
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857566"
---
### <a name="changing-the-isenabled-property-of-the-parent-of-a-textblock-control-affects-any-child-controls"></a>Das Ändern der IsEnabled-Eigenschaft des übergeordneten Elements eines TextBlock-Steuerelements wirkt sich auf alle untergeordneten Steuerelemente aus

|   |   |
|---|---|
|Details|Ab .NET Framework 4.6.2 wirkt sich das Ändern der <xref:System.Windows.UIElement.IsEnabled?displayProperty=name>-Eigenschaft eines übergeordneten Elements eines <xref:System.Windows.Controls.TextBlock?displayProperty=name>-Steuerelements auf alle untergeordneten Steuerelemente (z.B. Links und Schaltflächen) des <xref:System.Windows.Controls.TextBlock?displayProperty=name>-Steuerelements aus. In .NET Framework 4.6.1 und früher zeigten Steuerelemente innerhalb von <xref:System.Windows.Controls.TextBlock?displayProperty=name> nicht immer den Status der <xref:System.Windows.UIElement.IsEnabled?displayProperty=name>-Eigenschaft des übergeordneten <xref:System.Windows.Controls.TextBlock?displayProperty=name>-Elements an.|
|Vorschlag|Keine Diese Änderung entspricht dem erwarteten Verhalten für Steuerelemente innerhalb eines <xref:System.Windows.Controls.TextBlock?displayProperty=name>-Steuerelements.|
|Bereich|Gering|
|Version|4.6.2|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Windows.UIElement.IsEnabled?displayProperty=nameWithType></li></ul>|

