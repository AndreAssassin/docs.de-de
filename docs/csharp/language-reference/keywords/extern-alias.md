---
title: extern-Alias – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 09d1247c51f0e600973840cfef2d3b396d9bf0d0
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2019
ms.locfileid: "72520286"
---
# <a name="extern-alias-c-reference"></a>extern-Alias (C#-Referenz)
Sie müssen möglicherweise auf zwei Versionen von Assemblys verweisen, die denselben vollqualifizierten Namen besitzen. Beispielsweise müssen Sie möglicherweise zwei oder mehr Versionen einer Assembly in derselben Anwendung verwenden. Indem Sie einen externen Assemblyalias verwenden, können die Namespaces jeder Assembly in Namespaces auf Stammebene, benannt durch den Alias, umschlossen werden, was es ihnen ermöglicht, von derselben Datei verwendet zu werden.  
  
> [!NOTE]
> Das [extern](./extern.md)-Schlüsselwort dient außerdem als Methodenmodifizierer, der eine Methode deklariert, die in nicht verwaltetem Code geschrieben wurde.  
  
 Um auf zwei Assemblys mit demselben vollqualifizierten Typnamen zu verweisen, muss ein Alias in einer Befehlszeile wie folgt angegeben werden:  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 Dies erstellt die externen Aliase `GridV1` und `GridV2`. Um diese Aliase aus einem Programm heraus zu verwenden, verweisen Sie mithilfe des `extern`-Schlüsselworts auf sie. Beispiel:  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 Jede externe Aliasdeklaration führt einen zusätzlichen Namespace auf Stammebene ein, parallel zum (aber nicht innerhalb des) globalen Namespace. Daher kann mithilfe des vollqualifizierten Namens, der als Stamm des entsprechenden Namespacealias dient, auf Typen jeder Assembly eindeutig verwiesen werden.  
  
 Im vorherigen Beispiel wäre `GridV1::Grid` das Steuerelement von `grid.dll`, und `GridV2::Grid` wäre das Steuerelement von `grid20.dll`.  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](./index.md)
- [:: Operator](../operators/namespace-alias-qualifier.md)
- [-reference (C#-Compileroptionen)](../compiler-options/reference-compiler-option.md)
