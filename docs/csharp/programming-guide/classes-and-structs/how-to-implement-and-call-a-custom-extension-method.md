---
title: 'Vorgehensweise: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- extension methods [C#], implementing and calling
ms.assetid: 7dab2a56-cf8e-4a47-a444-fe610a02772a
ms.openlocfilehash: 2d3f6ec66a13638f0106537ad8b21bff801a53b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59303335"
---
# <a name="how-to-implement-and-call-a-custom-extension-method-c-programming-guide"></a>Vorgehensweise: Implementieren und Aufrufen einer benutzerdefinierten Erweiterungsmethode (C#-Programmierhandbuch)
In diesem Artikel wird das Implementieren Ihrer eigenen Erweiterungsmethoden für jeden .NET-Typ behandelt. Der Clientcode kann Ihre Erweiterungsmethoden verwenden, wenn ein Verweis auf die DLL, die die Methoden enthält, und eine [using](../../../csharp/language-reference/keywords/using-directive.md)-Direktive hinzugefügt werden, die den Namespace angibt, in dem die Erweiterungsmethoden definiert sind.  
  
## <a name="to-define-and-call-the-extension-method"></a>So definieren Sie die Erweiterungsmethode und rufen Sie auf  
  
1. Definieren Sie eine statische [Klasse](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md), die die Erweiterungsmethode enthalten soll.  
  
     Die Klasse muss für den Clientcode sichtbar sein. Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
2. Implementieren Sie die Erweiterungsmethode als statische Methode mit mindestens die gleichen Sichtbarkeit wie die enthaltende Klasse.  
  
3. Der erste Parameter der Methode gibt den Typ an, auf den die Methode angewendet wird. Ihm muss ein [this](../../../csharp/language-reference/keywords/this.md)-Modifizierer vorangehen.  
  
4. Fügen Sie im aufrufenden Code eine `using`-Direktive hinzu, um den [Namespace](../../../csharp/language-reference/keywords/namespace.md) anzugeben, der die Erweiterungsklassemethode enthält.  
  
5. Rufen Sie die Methoden auf, als wären sie Instanzmethoden für den Typ.  
  
     Beachten Sie, dass der erste Parameter nicht durch einen Aufruf von Code angegeben wird, da er den Typ darstellt, auf den der Operator angewendet wird, und der Compiler bereits den Typ des Objekts kennt. Sie müssen nur Argumente für Parameter 2 bis `n` bereitstellen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Erweiterungsmethode namens `WordCount` in der `CustomExtensions.StringExtension`-Klasse implementiert. Die Methode wird auf die <xref:System.String>-Klasse angewendet, die als erster Methodenparameter angegeben wird. Der `CustomExtensions`-Namespace wird in den Anwendungsnamespace importiert, und die Methode wird in der `Main`-Methode aufgerufen.  
  
 [!code-csharp[csProgGuideExtensionMethods#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Kopieren Sie diesen Code, und fügen Sie ihn in ein Visual C#-Konsolenanwendungsprojekt ein, das in Visual Studio erstellt wurde, um den Code auszuführen. Standardmäßig wird dieses Projekt mit Version 3.5 von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] verwendet und verfügt über einen Verweis auf „System.Core.dll“ und eine `using`-Anweisung für „System.Linq“. Wenn mindestens eine dieser Anforderungen im Projekt nicht vorhanden sind, können Sie sie manuell hinzufügen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Erweiterungsmethoden enthalten keine speziellen Sicherheitslücken. Sie können nicht dazu verwendet werden, die Identität vorhandener Methoden für einen Typ anzunehmen, da alle Namenskonflikte zugunsten der Instanz oder eine statische Methode gelöst werden, die der Typ selbst definiert. Erweiterungsmethoden können in der erweiterten Klasse nicht auf private Daten zugreifen.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Erweiterungsmethoden](../../../csharp/programming-guide/classes-and-structs/extension-methods.md)
- [LINQ (Language Integrated Query)](../../../csharp/linq/linq-in-csharp.md)
- [Statische Klassen und statische Klassenmember](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md)
- [protected](../../../csharp/language-reference/keywords/protected.md)
- [internal](../../../csharp/language-reference/keywords/internal.md)
- [public](../../../csharp/language-reference/keywords/public.md)
- [this](../../../csharp/language-reference/keywords/this.md)
- [namespace](../../../csharp/language-reference/keywords/namespace.md)
