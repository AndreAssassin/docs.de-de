---
title: 'Vorgehensweise: Festlegen des Titels eines Fensters einer Seite'
ms.date: 03/30/2017
helpviewer_keywords:
- windows [WPF], setting title from a page
- title of window [WPF], setting from a page
- pages [WPF], setting window title from
ms.assetid: fecf0d19-3eb6-4f8c-a44f-ff1b6f2b34b3
ms.openlocfilehash: 55444de6c61107979307b94910ba944e7001cf9e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054002"
---
# <a name="how-to-set-the-title-of-a-window-from-a-page"></a>Vorgehensweise: Festlegen des Titels eines Fensters einer Seite
Dieses Beispiel veranschaulicht die legen Sie des Titels des Fensters in der ein <xref:System.Windows.Controls.Page> gehostet wird.  
  
## <a name="example"></a>Beispiel  
 Eine Seite kann ändern Sie den Titel des Fensters, das sie durch Festlegen von hostet die <xref:System.Windows.Controls.Page.WindowTitle%2A> -Eigenschaft wie folgt:  
  
 [!code-xaml[HOWTONavigationSnippets#SetPageWindowTitleXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/SetWindowTitlePage.xaml#setpagewindowtitlexaml)]  
  
> [!NOTE]
>  Festlegen der <xref:System.Windows.Controls.Page.Title%2A> Eigenschaft einer Seite ändert sich nicht auf den Wert der der Titel des Fensters. Stattdessen <xref:System.Windows.Controls.Page.Title%2A> gibt Sie den Namen eines Eintrags für die Seite im Navigationsverlauf.
