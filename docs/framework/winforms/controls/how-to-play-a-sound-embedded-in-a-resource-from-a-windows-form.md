---
title: 'Vorgehensweise: Wiedergeben eines in einer Ressource aus Windows Forms eingebetteten Sounds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sounds [Windows Forms], playing from resources
- resources [Windows Forms], playing sounds
- playing sounds [Windows Forms], from resources
- SoundPlayer class [Windows Forms], playing sounds from resources
ms.assetid: 7d148bb6-8a1e-47d7-a08d-35828d2e688f
ms.openlocfilehash: 49235f9cb035c5a09c26b427f855fc00e818fe1c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913353"
---
# <a name="how-to-play-a-sound-embedded-in-a-resource-from-a-windows-form"></a><span data-ttu-id="0083f-102">Vorgehensweise: Wiedergeben eines in einer Ressource aus Windows Forms eingebetteten Sounds</span><span class="sxs-lookup"><span data-stu-id="0083f-102">How to: Play a Sound Embedded in a Resource from a Windows Form</span></span>
<span data-ttu-id="0083f-103">Sie können die <xref:System.Media.SoundPlayer> Klasse zum Abspielen eines Sounds aus einer eingebetteten Ressource.</span><span class="sxs-lookup"><span data-stu-id="0083f-103">You can use the <xref:System.Media.SoundPlayer> class to play a sound from an embedded resource.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0083f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0083f-104">Example</span></span>  
 [!code-csharp[System.Windows.Forms.Sound#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Sound/CS/soundtestform.cs#10)]
 [!code-vb[System.Windows.Forms.Sound#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Sound/VB/soundtestform.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0083f-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0083f-105">Compiling the Code</span></span>  
 <span data-ttu-id="0083f-106">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0083f-106">This example requires:</span></span>  
  
 <span data-ttu-id="0083f-107">Importieren der <xref:System.Media?displayProperty=nameWithType> Namespace.</span><span class="sxs-lookup"><span data-stu-id="0083f-107">Importing the <xref:System.Media?displayProperty=nameWithType> namespace.</span></span>  
  
 <span data-ttu-id="0083f-108">Die Sounddatei wird als eingebettete Ressource in das Projekt aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="0083f-108">Including the sound file as an embedded resource in your project.</span></span>  
  
 <span data-ttu-id="0083f-109">„\<AssemblyName>“ wird durch den Namen der Assembly ersetzt, in die die Sounddatei eingebettet ist.</span><span class="sxs-lookup"><span data-stu-id="0083f-109">Replacing "\<AssemblyName>" with the name of the assembly in which the sound file is embedded.</span></span> <span data-ttu-id="0083f-110">Das Suffix „.dll“ wird nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="0083f-110">Do not include the ".dll" suffix.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0083f-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0083f-111">See also</span></span>

- <xref:System.Media.SoundPlayer>
- [<span data-ttu-id="0083f-112">Vorgehensweise: Wiedergabe von Sound in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0083f-112">How to: Play a Sound from a Windows Form</span></span>](how-to-play-a-sound-from-a-windows-form.md)
- [<span data-ttu-id="0083f-113">Vorgehensweise: Schleife ein wiedergegebenen Sounds in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0083f-113">How to: Loop a Sound Playing on a Windows Form</span></span>](how-to-loop-a-sound-playing-on-a-windows-form.md)
