---
title: COM-Beispielklasse – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
ms.openlocfilehash: d4ea445339057bc65c3597d30a46f46d58b6e696
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595536"
---
# <a name="example-com-class-c-programming-guide"></a>COM-Beispielklasse (C#-Programmierhandbuch)
Das Folgende ist ein Beispiel für eine Klasse, die Sie als COM-Objekt offenlegen würden. Nachdem dieser Code in eine CS-Datei platziert und Ihrem Projekt hinzugefügt wurde, legen Sie die Eigenschaft **für COM-Interop registrieren** auf **TRUE** fest. Weitere Informationen finden Sie unter [Vorgehensweise: Registrieren einer Komponente für COM-Interop](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).
  
 Das Verfügbarmachen von Visual C#-Objekten für COM erfordert die Deklaration einer Klassenschnittstelle, einer Ereignisschnittstelle (wenn dies erforderlich ist) und die Klasse selbst. Klassenmember müssen diesen Regeln folgen, um für COM sichtbar zu sein:  
  
- Die Klasse muss öffentlich sein.  
  
- Eigenschaften, Methoden und Ereignisse müssen öffentlich sein.  
  
- Eigenschaften und Methoden müssen auf der Klassenschnittstelle deklariert werden.  
  
- Ereignisse müssen in der Ereignisschnittstelle deklariert werden.  
  
 Andere öffentliche Member in der Klasse, die nicht in diesen Schnittstellen deklariert sind, werden für COM nicht sichtbar sein, aber für andere .NET Framework-Objekte werden sie sichtbar sein.  
  
 Um Eigenschaften und Methoden für COM verfügbar zu machen, müssen Sie diese auf der Klassenschnittstelle deklarieren, sie mit einem `DispId`-Attribut markieren und sie in der Klasse implementieren. Die Reihenfolge, in der die Elemente in der Schnittstelle deklariert werden, ist die für die COM-Vtable verwendete Reihenfolge.  
  
 Um Ereignisse aus Ihrer Klasse verfügbar zu machen, müssen Sie diese auf der Ereignisschnittstelle deklarieren und sie mit einem `DispId`-Attribut markieren. Die Klasse sollte diese Schnittstelle nicht implementieren.  
  
 Die Klasse implementiert die Klassenschnittstelle. Es kann mehr als eine Schnittstelle implementieren, aber die erste Implementierung ist die Standard-Klassenschnittstelle. Implementieren Sie die Methoden und Eigenschaften hier, die Sie für COM verfügbar gemacht haben. Sie müssen als öffentlich markiert sein und den Deklarationen in der Klassenschnittstelle entsprechen. Deklarieren Sie außerdem die von der Klasse hier ausgelösten Ereignisse. Sie müssen als öffentlich markiert sein und den Deklarationen in der Klassenschnittstelle entsprechen.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuideInterop#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/ExampleCOM.cs#8)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Interoperabilität](../../../csharp/programming-guide/interop/index.md)
- [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp)
