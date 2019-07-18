---
title: x:Members-Anweisung
ms.date: 03/30/2017
ms.assetid: 155b393d-3b49-4c5a-8c9e-b3d9893af4e4
ms.openlocfilehash: d23e6b459af932e0a6f69309f26a1cce70a9d256
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938891"
---
# <a name="xmembers-directive"></a>x:Members-Anweisung
Enthält eine Menge von Elementen, die im Markup definiert sind und die für die X: Class des übergeordneten Elements gelten.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```  
<object x:Class="className">  
  <x:Members>  
    oneOrMoreMembers  
  </x:Members  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`className`|Der Name der Sicherungsklasse oder partiellen Klasse für die XAML-Produktion. Siehe Hinweise.|  
|`oneOrMoreMembers`|Eine oder mehrere Object-Elemente, die Memberdefinitionen darstellen. In der Regel sind diese `x:Property` Objektelemente. Siehe Hinweise.|  
  
## <a name="remarks"></a>Hinweise  
 In der .NET Framework-XAML-Dienste-Implementierung, ist keine Sicherungsklasse oder die zugrunde liegende Implementierung des Schnittstellenmembers für `x:Members`. `x:Members` ist ein spezieller XAML-Element, das als Element in einem beliebigen vorhanden sein kann. In einem XAML-Knotenstream `x:Members` wird dargestellt, wie ein Element mit dem Namen `Members`, über die XAML-Namespace der XAML-Sprache. Das Element `Members` enthält eine schreibgeschützte generische Liste von `Member` Objekte. In typischen Markup werden die einzelnen Mitglieder als angegeben `x:Property` Eigenschaftenelemente. `x:Property` ist kein genauerer Typ speziell für die Eigenschaften von Typen und lässt sich `x:Member`. Weitere Informationen finden Sie unter [X: Property-Anweisung](x-property-directive.md).  
  
 Damit eine praktische Verwendung von `x:Members` als Mittel zum Angeben von Memberdefinitionen in Markup unterstützt wird, müssen die Member einer Klasse zugeordnet sein, die geändert werden kann. Das beabsichtigte Modell besteht darin, dass `x:Members` als ein Member eines Typs vorhanden ist, der eine `x:Class` angibt. Der Mechanismus zum Zuordnen von Typen und Membern oder zum Erstellen von dynamischen Memberdefinitionen wird jedoch auf der Ebene der .NET Framework-XAML-Dienste nicht unterstützt. Dies wird von einzelnen Frameworks übernommen, die Anwendungsmodelle haben, die Memberdefinitionen von XAML unterstützen. In der Regel sind, damit dieses Feature unterstützt wird, MSBUILD-Buildvorgänge erforderlich, die XAML als Markup kompilieren und es als CodeBehind integrieren oder reine Von-XAML-Assemblys generieren.  
  
## <a name="xmembers-for-windows-workflow-foundation"></a>X: Members für Windows Workflow Foundation  
 Für Windows Workflow Foundation `x:Members` enthält die Elemente von einer benutzerdefinierten Aktivität vollständig in XAML oder XAML-definierte dynamische Member für einen Aktivitäts-Designer mit CodeBehind. `x:Class` muss auch für das Stammelement der XAML-Produktion angegeben werden. Dies ist keine Anforderung auf der Ebene der .NET Framework-XAML-Dienste, wird jedoch eine Anforderung, wenn die XAML-Produktion von MSBUILD-Buildvorgängen geladen wird, die benutzerdefinierte Aktivitäten und Windows Workflow Foundation-XAML im Allgemeinen unterstützen. `x:Members` muss das erste untergeordnete Element im Markup der Object-Element, das deklariert die `x:Class`.
