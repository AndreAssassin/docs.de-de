---
title: Kontextabhängiges global-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: 1c0177c52e21ae60477a283085a2893e2e067c54
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633480"
---
# <a name="global-c-reference"></a>global (C#-Referenz)

Wenn das Kontextschlüsselwort `global` dem [Operator „::“](../operators/namespace-alias-qualifer.md) vorangestellt ist, verweist es auf den globalen Namespace. Dabei handelt es sich um den Standardnamespace für alle C#-Programme, der ansonsten unbenannt ist. Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des globalen Namespacealias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie mit dem Kontextschlüsselwort `global` angegeben wird, dass die Klasse `TestApp` im globalen Namespace definiert ist:

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a>Siehe auch

- [Namespaces](../../programming-guide/namespaces/index.md)
