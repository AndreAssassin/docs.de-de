---
title: Gespeicherte CLR-Prozeduren
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: 9b31d93c1ebc0af9aa8e41b3a4c328af62da7e23
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230810"
---
# <a name="clr-stored-procedures"></a>Gespeicherte CLR-Prozeduren
Gespeicherte Prozeduren sind Routinen, die nicht in skalaren Ausdrücken verwendet werden können. Sie können tabellarische Ergebnisse und Meldungen an den Client zurückgeben, DDL-Anweisungen (Data Definition Language – Datendefinitionssprache) und DML-Anweisungen (Data Manipulation Language – Datenbearbeitungssprache) aufrufen und Ausgabeparameter zurückgeben.  
  
> [!NOTE]
>  Microsoft Visual Basic unterstützt Ausgabeparameter nicht in derselben Weise wie Microsoft Visual C#. Sie müssen angeben, dass der Parameter als Verweis übergeben, und wenden Sie die \<Out() >-Attribut einen Output-Parameter, wie im folgenden dargestellt:  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
Weitere Informationen finden Sie unter der Version von [SQL Server-Dokumentation](/sql) für die Version von SQL Server, die Sie verwenden.
  
 **SQL Server-Dokumentation**

1. [Gespeicherte CLR-Prozeduren](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von SQL Server 2005-Objekte In verwaltetem Code](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/6s0s2at1(v=vs.90))
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
