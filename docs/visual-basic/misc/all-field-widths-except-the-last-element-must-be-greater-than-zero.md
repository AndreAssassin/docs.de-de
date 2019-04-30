---
title: Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_FieldWidthsMustPositive
ms.assetid: 41d8c661-a749-4c89-be56-905c6e7c3c9d
ms.openlocfilehash: 806dcef7b7a29afa8804a581659023c817662434
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940659"
---
# <a name="all-field-widths-except-the-last-element-must-be-greater-than-zero"></a><span data-ttu-id="10693-102">Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="10693-102">All field widths, except the last element, must be greater than zero</span></span>
<span data-ttu-id="10693-103">Alle Feldbreiten (außer beim letzten Element) müssen größer als 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="10693-103">All field widths, except the last element, must be greater than zero.</span></span> <span data-ttu-id="10693-104">Ein Feld mit einer Breite unter oder gleich 0 (null) im letzten Element bedeutet, dass die Länge des letzten Felds variabel ist.</span><span class="sxs-lookup"><span data-stu-id="10693-104">A field width less than or equal to zero in the last element indicates the last field is of variable length.</span></span>  
  
 <span data-ttu-id="10693-105">Der Vorgang ist fehlgeschlagen, da die Feldbreite eines anderen Elements, das nicht das letzte Element ist, auf 0 (null) oder kleiner festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="10693-105">The operation has failed because a field width other than the last element is set to zero or less.</span></span> <span data-ttu-id="10693-106">Eine Feldbreite, die kleiner oder gleich 0 (null) ist, kann als letztes Element verwendet werden, um anzugeben, dass dass die Länge des letzten Felds variabel ist. Sie kann jedoch nicht als ein anderes Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="10693-106">A field width less than or equal to zero can be used as the last element to indicate that the last field is of variable length, but it cannot be used as any other element.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="10693-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="10693-107">To correct this error</span></span>  
  
- <span data-ttu-id="10693-108">Legen Sie die Feldbreite auf die richtige Länge fest.</span><span class="sxs-lookup"><span data-stu-id="10693-108">Set the field width to the correct length.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10693-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10693-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetFieldWidths%2A?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.FieldWidths>
- [<span data-ttu-id="10693-110">Vorgehensweise: Lesen aus einer Textdatei mit fester Breite</span><span class="sxs-lookup"><span data-stu-id="10693-110">How to: Read From Fixed-width Text Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)
- [<span data-ttu-id="10693-111">TextFieldParser-Objekt</span><span class="sxs-lookup"><span data-stu-id="10693-111">TextFieldParser Object</span></span>](../../visual-basic/language-reference/objects/textfieldparser-object.md)
