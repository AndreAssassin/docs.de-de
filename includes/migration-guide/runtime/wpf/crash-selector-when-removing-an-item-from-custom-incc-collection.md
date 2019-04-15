---
ms.openlocfilehash: a573a78109036b87201b53f72aa8dba6755e7a21
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236585"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Selektor stürzt ab, wenn ein Element aus einer benutzerdefinierten INCC-Sammlung entfernt wird

|   |   |
|---|---|
|Details|<code>T:System.InvalidOperationException</code> kann in folgendem Szenario auftreten:<ul><li>Das ItemsSource-Element für <code>T:System.Windows.Controls.Primitives.Selector</code> ist eine Sammlung mit einer benutzerdefinierten Implementierung von <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>Das ausgewählte Element wird aus der Sammlung entfernt.</li><li><code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> weist den Wert <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code>=–1 auf, der eine unbekannte Position angibt.</li></ul>Die Aufrufliste der Ausnahme beginnt bei „System.Windows.Threading.Dispatcher.VerifyAccess()“ in „System.Windows.DependencyObject.GetValue(DependencyProperty dp)“ in „System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element)“. Diese Ausnahme kann in .NET Framework 4.5 auftreten, wenn die Anwendung über mehr als einen Dispatcher-Thread verfügt. In .NET Framework 4.7 kann diese Ausnahme auch bei Anwendungen mit einem einzelnen Dispatcher-Thread ausgelöst werden. Dieses Problem wurde in .NET Framework 4.7.1 behoben.|
|Vorschlag|Upgrade auf .NET Framework 4.7.1|
|Bereich|Gering|
|Version|4.7|
|Typ|Laufzeit|
