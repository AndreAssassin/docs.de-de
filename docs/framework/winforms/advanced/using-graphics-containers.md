---
title: Verwenden von Grafikcontainern
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766154"
---
# <a name="using-graphics-containers"></a>Verwenden von Grafikcontainern
Ein <xref:System.Drawing.Graphics> Objekt bietet Methoden, wie z. B. <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, und <xref:System.Drawing.Graphics.DrawString%2A> für die Anzeige von Vektorgrafiken, Rasterbilder und Text. Ein <xref:System.Drawing.Graphics> Objekt verfügt auch über mehrere Eigenschaften, die beeinflussen, die Qualität und die Ausrichtung der Elemente, die gezeichnet werden. Beispielsweise bestimmt die Glättung Mode-Eigenschaft an, ob Antialiasing auf Linien und Kurven angewendet wird, und die Welt Transformationseigenschaft wirkt sich auf die Position und Drehung der Elemente, die gezeichnet werden.  
  
 Ein <xref:System.Drawing.Graphics> Objekt jeweiligen Ausgabegeräts zugeordnet ist. Bei Verwendung einer <xref:System.Drawing.Graphics> Objekt, das in einem Fenster, zeichnen die <xref:System.Drawing.Graphics> -Objekt bezieht sich auch mit dem jeweiligen Fenster.  
  
 Ein <xref:System.Drawing.Graphics> Objekt kann betrachtet werden als Container, da sie einen Satz von Eigenschaften enthält, die Zeichnung zu beeinflussen, und klicken Sie mit gerätespezifischen Informationen verknüpft ist. Sie können einen sekundären Container in einem vorhandenen erstellen <xref:System.Drawing.Graphics> -Objekt durch Aufrufen der <xref:System.Drawing.Graphics.BeginContainer%2A> -Methode dieses <xref:System.Drawing.Graphics> Objekt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Verwalten des Zustands eines Graphics-Objekts](managing-the-state-of-a-graphics-object.md)  
 Beschreibt, wie verwalten Sie Einstellungen von Quality, Clippingbereichs und Transformationen von einem <xref:System.Drawing.Graphics> Objekt.  
  
 [Verwenden geschachtelter Grafikcontainer](using-nested-graphics-containers.md)  
 Zeigt, wie Sie Container verwenden, um die Steuerung des Status des der <xref:System.Drawing.Graphics> Objekt.
