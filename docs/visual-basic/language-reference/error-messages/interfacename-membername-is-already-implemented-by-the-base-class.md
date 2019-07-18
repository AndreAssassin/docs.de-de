---
title: "'<interfacename>. <membername>'wird bereits implementiert durch die Basisklasse'<baseclassname>'. Die erneute Implementierung von <type> davon ausgegangen, dass"
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 5943eff5fa7e68da9905e3e589eea264c06943c1
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593315"
---
# <a name="interfacenamemembername-is-already-implemented-by-the-base-class-baseclassname-re-implementation-of-type-assumed"></a>'\<Schnittstellenname >. \<Membername >' ist bereits in der Basisklasse implementiert\<Basisklassenname >'. Die erneute Implementierung von \<Typ > davon ausgegangen, dass
Eine Eigenschaft, Prozedur oder das Ereignis in einer abgeleiteten Klasse verwendet eine `Implements` -Klausel für einen Schnittstellenmember, die bereits in der Basisklasse implementiert wird.  
  
 Ein Schnittstellenmember, der von seiner Basisklasse implementiert wird, kann von einer abgeleiteten Klasse erneut implementiert werden. Dieser Vorgang ist nicht identisch mit dem Überschreiben der Basisklassenimplementierung. Weitere Informationen finden Sie unter [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 Standardmäßig ist diese Meldung eine Warnung. Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42015  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Wenn Sie beabsichtigen, den Schnittstellenmember erneut zu implementieren, müssen Sie keine Maßnahme ergreifen. Code in der abgeleiteten Klasse greift auf die neu Member aus, es sei denn, Sie verwenden die `MyBase` Schlüsselwort, um die Implementierung der Basisklasse zugreifen.  
  
- Wenn Sie keine erneute Implementierung des Schnittstellenmembers beabsichtigen, entfernen Sie die `Implements` -Klausel aus der Deklaration der Eigenschaft, Prozedur oder des Ereignisses.  
  
## <a name="see-also"></a>Siehe auch

- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
