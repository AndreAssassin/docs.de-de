---
title: Fehler beim Lesen von Feldern mit Trennzeichen. Doppelte Anführungszeichen sind kein zulässiges Trennzeichen, wenn „EscapeQuotes“ auf „True“ festgelegt ist.
ms.date: 07/20/2015
f1_keywords:
- vbrTextFieldParser_IllegalDelimiter
ms.assetid: ab8a0c3a-b89c-4617-9e31-7e81f5dca433
ms.openlocfilehash: bc19fc7496b31eabca6dabedf212c89d6f5450d3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61819274"
---
# <a name="unable-to-read-delimited-fields-because-a-double-quote-is-not-a-legal-delimiter-when-escapequotes-is-set-to-true"></a><span data-ttu-id="18bc1-102">Fehler beim Lesen von Feldern mit Trennzeichen. Doppelte Anführungszeichen sind kein zulässiges Trennzeichen, wenn „EscapeQuotes“ auf „True“ festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="18bc1-102">Unable to read delimited fields because a double quote is not a legal delimiter when EscapeQuotes is set to True</span></span>
<span data-ttu-id="18bc1-103">Der `TextFieldParser` kann nicht aus der Datei lesen, weil ein Anführungszeichen (") als Trennzeichen angegeben wurde und `EscapeQuotes` auf `True`festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="18bc1-103">The `TextFieldParser` cannot read from the file because a quotation mark (") has been supplied as the delimiter and `EscapeQuotes` is set to `True`.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="18bc1-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="18bc1-104">To correct this error</span></span>  
  
- <span data-ttu-id="18bc1-105">Legen Sie `EscapeQuotes` auf `False` fest.</span><span class="sxs-lookup"><span data-stu-id="18bc1-105">Set `EscapeQuotes` to `False`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18bc1-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18bc1-106">See also</span></span>

- [<span data-ttu-id="18bc1-107">TextFieldParser.SetDelimiters-Methode</span><span class="sxs-lookup"><span data-stu-id="18bc1-107">TextFieldParser.SetDelimiters Method</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.SetDelimiters%2A)
- [<span data-ttu-id="18bc1-108">TextFieldParser.Delimiters Property</span><span class="sxs-lookup"><span data-stu-id="18bc1-108">TextFieldParser.Delimiters Property</span></span>](xref:Microsoft.VisualBasic.FileIO.TextFieldParser.Delimiters%2A)
- [<span data-ttu-id="18bc1-109">Vorgehensweise: Lesen aus durch Trennzeichen getrennten Textdateien</span><span class="sxs-lookup"><span data-stu-id="18bc1-109">How to: Read From Comma-Delimited Text Files</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)
- [<span data-ttu-id="18bc1-110">TextFieldParser-Objekt</span><span class="sxs-lookup"><span data-stu-id="18bc1-110">TextFieldParser Object</span></span>](../../visual-basic/language-reference/objects/textfieldparser-object.md)
