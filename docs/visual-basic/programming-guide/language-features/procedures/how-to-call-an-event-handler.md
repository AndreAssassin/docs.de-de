---
title: 'Vorgehensweise: Ereignis Handler in Visual Basic aufgerufen'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: a9e090e83b180686ccb832aa6efb314c7e0fcc9a
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216615"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Vorgehensweise: Ereignis Handler in Visual Basic aufgerufen

Ein *Ereignis* ist eine Aktion oder ein Vorkommen – z. b. ein Mausklick oder ein Guthaben Limit überschritten –, das von einer Programm Komponente erkannt wird, und für das Sie Code schreiben können, um Antworten zu können. Ein *Ereignishandler* ist der Code, den Sie schreiben, um auf ein Ereignis zu reagieren.

 Ein Ereignishandler in Visual Basic ist eine `Sub` Prozedur. Sie werden jedoch normalerweise nicht auf dieselbe Weise aufgerufen wie andere `Sub` Prozeduren. Stattdessen identifizieren Sie die Prozedur als Handler für das-Ereignis. Hierzu können Sie entweder eine [Handles](../../../language-reference/statements/handles-clause.md) -Klausel und eine [widervents](../../../language-reference/modifiers/withevents.md) -Variable oder eine [AddHandler-Anweisung](../../../language-reference/statements/addhandler-statement.md)verwenden. Die Verwendung `Handles` einer-Klausel ist die Standardmethode zum Deklarieren eines Ereignis Handlers in Visual Basic. Dies ist die Methode, mit der die Ereignishandler von den Designern geschrieben werden, wenn Sie in der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) programmieren. Die `AddHandler` -Anweisung eignet sich zum dynamischen Ereignisse zur Laufzeit.

 Wenn das Ereignis auftritt, ruft Visual Basic automatisch die Ereignishandlerprozedur auf. Jeder Code, der Zugriff auf das Ereignis hat, kann dazu führen, dass er durch Ausführen einer [RaiseEvent-Anweisung](../../../language-reference/statements/raiseevent-statement.md)ausgelöst wird.

 Sie können dem gleichen Ereignis mehr als einen Ereignishandler zuordnen. In einigen Fällen können Sie einen Handler von einem Ereignis trennen. Weitere Informationen finden Sie unter [Ereignisse](../events/index.md).

### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>So wenden Sie einen Ereignishandler mithilfe von Handles und wiwitvents an

1. Stellen Sie sicher, dass das Ereignis mit einer [Ereignis Anweisung](../../../language-reference/statements/event-statement.md)deklariert ist.

2. Deklarieren Sie eine Objekt Variable auf Modul-oder Klassenebene mithilfe des [widervents](../../../language-reference/modifiers/withevents.md) -Schlüssel Worts. Die `As` -Klausel für diese Variable muss die Klasse angeben, die das Ereignis auslöst.

3. Fügen Sie in der Deklaration der Ereignis `Sub` Behandlungs Prozedur eine [Handles](../../../language-reference/statements/handles-clause.md) -Klausel hinzu, die `WithEvents` die Variable und den Ereignis Namen angibt.

4. Wenn das Ereignis auftritt, ruft Visual Basic automatisch die `Sub` Prozedur auf. Der Code kann eine `RaiseEvent` -Anweisung verwenden, um das-Ereignis zu treffen.

     Im folgenden Beispiel wird ein Ereignis und eine `WithEvents` Variable definiert, die auf die-Klasse verweist, die das-Ereignis auslöst. Das Ereignis Behandlungs `Sub` Verfahren verwendet eine `Handles` -Klausel, um die Klasse und das Ereignis anzugeben, die es behandelt.

     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]

### <a name="to-call-an-event-handler-using-addhandler"></a>So greifen Sie einen Ereignishandler mithilfe von AddHandler an

1. Stellen Sie sicher, dass das-Ereignis `Event` mit einer-Anweisung deklariert wird.

2. Führen Sie eine [AddHandler-Anweisung](../../../language-reference/statements/addhandler-statement.md) aus, um die Ereignis `Sub` Behandlungs Prozedur dynamisch mit dem-Ereignis zu verbinden.

3. Wenn das Ereignis auftritt, ruft Visual Basic automatisch die `Sub` Prozedur auf. Der Code kann eine `RaiseEvent` -Anweisung verwenden, um das-Ereignis zu treffen.

     Im folgenden Beispiel wird eine `Sub` Prozedur definiert, die <xref:System.Windows.Forms.Form.Closing> das-Ereignis eines Formulars behandelt. Anschließend wird die `catchClose` Prozedur mithilfe der [AddHandler-Anweisung](../../../language-reference/statements/addhandler-statement.md) als Ereignishandler für <xref:System.Windows.Forms.Form.Closing>verknüpft.

     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]

     Sie können einen Ereignishandler von einem Ereignis trennen, indem Sie die [RemoveHandler-Anweisung](../../../language-reference/statements/removehandler-statement.md)ausführen.

## <a name="see-also"></a>Siehe auch

- [Verfahren](index.md)
- [Sub-Prozeduren](sub-procedures.md)
- [Sub-Anweisung](../../../language-reference/statements/sub-statement.md)
- [AddressOf-Operator](../../../language-reference/operators/addressof-operator.md)
- [Vorgehensweise: Erstellen einer Prozedur](how-to-create-a-procedure.md)
- [Vorgehensweise: Eine Prozedur, die keinen Wert zurückgibt, wird aufgerufen.](how-to-call-a-procedure-that-does-not-return-a-value.md)
