---
title: 'Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- strong-named assemblies, compile-time references
- compile-time assembly referencing
- assemblies [.NET Framework], strong-named
- assembly binding, strong-named
ms.assetid: 4c6a406a-b5eb-44fa-b4ed-4e95bb95a813
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 281cfa6507d293658e436a95a5ded0174154a13c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301021"
---
# <a name="how-to-reference-a-strong-named-assembly"></a>Vorgehensweise: Verweisen auf eine Assembly mit starkem Namen
Beim Verweisen auf Typen oder Ressourcen in einer Assembly mit starkem Namen handelt es sich in der Regel um einen transparenten Prozess. Sie können den Verweis zur Kompilierzeit (frühes Binden) oder zur Runtime vornehmen.  
  
 Ein Verweis zur Kompilierzeit tritt auf, wenn Sie den Compiler darauf hinweisen, dass Ihre Assembly explizit auf eine andere Assembly verweist. Beim Verweisen zur Kompilierzeit ruft der Compiler automatisch den öffentlichen Schlüssel der Zielassembly mit starkem Namen ab und platziert ihn in der Assemblyreferenz der Assembly, die aktuell kompiliert wird.  
  
> [!NOTE]
>  Eine Assembly mit starkem Namen kann nur Typen aus anderen Assemblys mit starkem Namen verwenden. Andernfalls ist die Sicherheit der Assembly mit starkem Namen beeinträchtigt.  
  
### <a name="to-make-a-compile-time-reference-to-a-strong-named-assembly"></a>So verweisen Sie zur Kompilierzeit auf eine Assembly mit starkem Namen  
  
1. Geben Sie an der Eingabeaufforderung folgenden Befehl ein:  
  
     \<*Compilerbefehl*> **/reference:**\<*Assemblyname*>  
  
     In diesem Befehl ist der *Compilerbefehl* der Befehl für die Sprache, die Sie verwenden, und *Assemblyname* ist der Name der Assembly mit starkem Namen, auf die verwiesen wird. Sie können auch andere Compileroptionen verwenden, z.B. die Option **/t:library** zum Erstellen einer Bibliothekassembly.  
  
 Im folgenden Beispiel wird eine Assembly namens `myAssembly.dll` erstellt, die auf eine Assembly mit starkem Namen namens `myLibAssembly.dll` aus einem Codemodul namens `myAssembly.cs` verweist.  
  
```  
csc /t:library myAssembly.cs /reference:myLibAssembly.dll  
```  
  
### <a name="to-make-a-run-time-reference-to-a-strong-named-assembly"></a>So verweisen Sie zur Runtime auf eine Assembly mit starkem Namen  
  
1. Wenn Sie zur Runtime auf eine Assembly mit starkem Namen verweisen (z.B. mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>- oder <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>-Methode), müssen Sie den Anzeigenamen der referenzierten Assembly mit starkem Namen verwenden. Die Syntax eines Anzeigenamens lautet wie folgt:  
  
     \<*Assemblyname*>**,** \<*Versionsnummer*>**,** \<*Kultur*>**,** \<*öffentliches Schlüsseltoken*>  
  
     Beispiel:  
  
    ```  
    myDll, Version=1.1.0.0, Culture=en, PublicKeyToken=03689116d3a4ae33   
    ```  
  
     In diesem Beispiel ist `PublicKeyToken` die hexadezimale Form des öffentlichen Schlüsseltokens. Wenn kein Kulturwert vorhanden ist, verwenden Sie `Culture=neutral`.  
  
 Im folgenden Codebeispiel wird gezeigt, wie Sie diese Informationen mit der <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>-Methode verwenden.  
  
 [!code-cpp[Assembly.Load1#3](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.Load1/CPP/load2.cpp#3)]
 [!code-csharp[Assembly.Load1#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.Load1/CS/load2.cs#3)]
 [!code-vb[Assembly.Load1#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.Load1/VB/load2.vb#3)]  
  
 Sie können das Hexadezimalformat des öffentlichen Schlüssels und des öffentlichen Schlüsseltokens für eine bestimmte Assembly mithilfe des folgenden Befehls [Strong Name (Sn.exe)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) ausgeben:  
  
 **sn -Tp \<** *Assembly* **>**  
  
 Wenn Sie eine öffentliche Schlüsseldatei haben, können Sie stattdessen den folgenden Befehl verwenden. Beachten Sie aber den Unterschied bei der Groß- und Kleinschreibung bei der Befehlszeilenoption:  
  
 **sn -tp \<** *öffentliche Schlüsseldatei* **>**  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
