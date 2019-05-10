---
title: 'Vorgehensweise: Hinzufügen eines benutzerdefinierten Speicherorts zum Dialogfeld „Datei“'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Custom Place to dialog box
- adding Custom Place to dialog box
- CustomPlaces collection
ms.assetid: 63f6469b-59cd-40f6-9e61-8b5831856780
ms.openlocfilehash: 129ebed6d0a2b075020e635c8463536f97629d2f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624104"
---
# <a name="how-to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="3e6fe-102">Vorgehensweise: Hinzufügen eines benutzerdefinierten Speicherorts zum Dialogfeld „Datei“</span><span class="sxs-lookup"><span data-stu-id="3e6fe-102">How To: Add a Custom Place to a File Dialog Box</span></span>
<span data-ttu-id="3e6fe-103">In [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] befindet sich in den Standarddialogfeldern zum Öffnen und Schließen auf der linken Seite ein Bereich mit der Bezeichnung **Linkfavoriten**.</span><span class="sxs-lookup"><span data-stu-id="3e6fe-103">The default open and save dialog boxes on [!INCLUDE[wiprlhext](../../../../includes/wiprlhext-md.md)] have an area on the left side of the dialog box titled **Favorite Links**.</span></span> <span data-ttu-id="3e6fe-104">Dieser Bereich wird als „Benutzerdefinierte Speicherorte“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3e6fe-104">This area is called custom places.</span></span> <span data-ttu-id="3e6fe-105">Die <xref:System.Windows.Forms.OpenFileDialog> und <xref:System.Windows.Forms.SaveFileDialog> Klassen können Sie Ordner zum Hinzufügen der <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="3e6fe-105">The <xref:System.Windows.Forms.OpenFileDialog> and <xref:System.Windows.Forms.SaveFileDialog> classes allow you to add folders to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3e6fe-106">In der Reihenfolge für einen benutzerdefinierten Speicherort angezeigt werden die <xref:System.Windows.Forms.OpenFileDialog> oder <xref:System.Windows.Forms.SaveFileDialog>, <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> Eigenschaft muss festgelegt werden, um `true` (Standard).</span><span class="sxs-lookup"><span data-stu-id="3e6fe-106">In order for a custom place to appear in the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog>, the <xref:System.Windows.Forms.FileDialog.AutoUpgradeEnabled%2A> property must be set to `true` (the default).</span></span>  
  
### <a name="to-add-a-custom-place-to-a-file-dialog-box"></a><span data-ttu-id="3e6fe-107">So fügen Sie dem Dialogfeld „Datei“ einen benutzerdefinierten Speicherort hinzu</span><span class="sxs-lookup"><span data-stu-id="3e6fe-107">To add a custom place to a file dialog box</span></span>  
  
- <span data-ttu-id="3e6fe-108">Fügen Sie einen Pfad, eine GUID für bekannte Ordner oder ein <xref:System.Windows.Forms.FileDialogCustomPlace> -Objekt an die <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> Sammlung im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="3e6fe-108">Add a path, a Known Folder GUID, or a <xref:System.Windows.Forms.FileDialogCustomPlace> object to the <xref:System.Windows.Forms.FileDialog.CustomPlaces%2A> collection of the dialog box.</span></span>  
  
     <span data-ttu-id="3e6fe-109">Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Pfad hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="3e6fe-109">The following code example shows how to add a path:</span></span>  
  
    ```vb  
    OpenFileDialog1.CustomPlaces.Add("C:\MyCustomPlace")  
    ```  
  
    ```csharp  
    openFileDialog1.CustomPlaces.Add("C:\\MyCustomPlace");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3e6fe-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e6fe-110">See also</span></span>

- <xref:System.Windows.Forms.FileDialog>
- <xref:System.Windows.Forms.FileDialogCustomPlacesCollection.Add%2A?displayProperty=nameWithType>
- [<span data-ttu-id="3e6fe-111">GUIDs von bekannten Ordnern für benutzerdefinierte Speicherorte im Dateidialogfeld</span><span class="sxs-lookup"><span data-stu-id="3e6fe-111">Known Folder GUIDs for File Dialog Custom Places</span></span>](known-folder-guids-for-file-dialog-custom-places.md)
