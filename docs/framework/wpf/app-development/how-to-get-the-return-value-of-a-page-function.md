---
title: 'Vorgehensweise: Abrufen des Rückgabewerts einer Seitenfunktion'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- functions [WPF], getting return values of
- page functions [WPF], getting return values of
- return values of page functions [WPF]
- getting [WPF], return values of page functions
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
ms.openlocfilehash: 054ffe16690425e118fcac481b2a5ff63f9450f2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947718"
---
# <a name="how-to-get-the-return-value-of-a-page-function"></a>Vorgehensweise: Abrufen des Rückgabewerts einer Seitenfunktion
In diesem Beispiel wird gezeigt, wie das Ergebnis, das von einer Seitenfunktion zurückgegeben wird, abgerufen wird.  
  
## <a name="example"></a>Beispiel  
 Um das Ergebnis abzurufen, die von einer Seitenfunktion zurückgegeben wird, müssen Sie behandeln <xref:System.Windows.Navigation.PageFunction%601.Return> der Seite "-Funktion, die Sie aufrufen.  
  
 [!code-xaml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Navigation.PageFunction%601>
