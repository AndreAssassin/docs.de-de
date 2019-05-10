---
title: Problembehandlung für geerbte Ereignishandler in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting events [Visual Basic]
- inherited events [Visual Basic]
- troubleshooting Visual Basic, event handlers
- event handling, troubleshooting
- event handlers, troubleshooting
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
ms.openlocfilehash: f2ddef64ca02ca7c96c6c906f5ee79e3cf99dece
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64604063"
---
# <a name="troubleshooting-inherited-event-handlers-in-visual-basic"></a>Problembehandlung für geerbte Ereignishandler in Visual Basic
Dieses Thema enthält allgemeine Probleme, die bei Ereignishandlern in geerbten Komponenten auftreten.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="code-in-event-handler-executes-twice-for-every-call"></a>Code im Ereignishandler wird zweimal für jeden Aufruf ausgeführt.  
  
- Ein geerbten Ereignishandler dürfen keine [behandelt](../../../../visual-basic/language-reference/statements/handles-clause.md) Klausel. Die Methode in der Basisklasse ist bereits mit dem Ereignis verknüpft und wird entsprechend ausgelöst. Entfernen Sie die `Handles` Klausel aus der geerbten Methode.  
  
     [!code-vb[VbVbalrEvents#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#32)]  
  
- Wenn die geerbte Methode keine `Handles` -Schlüsselwort, stellen Sie sicher, dass Ihr Code keine zusätzlichen [AddHandler-Anweisung](../../../../visual-basic/language-reference/statements/addhandler-statement.md) oder zusätzliche Methoden, die das gleiche Ereignis zu behandeln.  
  
## <a name="see-also"></a>Siehe auch

- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
