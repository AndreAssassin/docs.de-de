---
title: In der Protokolldatei kann nicht geschrieben werden, weil dies dazu führen würde, dass sie den MaximumSize-Wert überschreitet.
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_FileExceedsMaximumSize
ms.assetid: 61747a9c-e460-424b-a365-73cdba9dd428
ms.openlocfilehash: 587b35282c7e78da1fdf4ccf9d08214e5665119c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022557"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-cause-it-to-exceed-maximumsize-value"></a>In der Protokolldatei kann nicht geschrieben werden, weil dies dazu führen würde, dass sie den MaximumSize-Wert überschreitet.
Die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Klasse konnte aus folgendem Grund nicht in die Protokolldatei schreiben:  
  
- Die Größe der Protokolldatei (in Bytes) ist größer als der Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> -Eigenschaft.  
  
     - und -  
  
- Der Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> -Eigenschaft ist <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Archivieren Sie die vorhandenen Protokolle, und entfernen Sie diese vom Computer, damit das <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> -Objekt neue Protokolle erstellen kann.  
  
2. Ändern Sie den Wert der <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A> -Eigenschaft, um größere Protokolle zuzulassen.  
  
3. Legen Sie die <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> -Eigenschaft auf <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> fest, um Nachrichten ohne Warnung zu verwerfen, wenn das Protokoll zu groß ist.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.MaxFileSize%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [My.Application.Log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [My.Application.Info.DirectoryPath](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
