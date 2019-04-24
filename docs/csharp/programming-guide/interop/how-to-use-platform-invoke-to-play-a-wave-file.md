---
title: 'Vorgehensweise: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- platform invoke, sound files
- interoperability [C#], playing WAV files using pinvoke
- wav files
- .wav files
ms.assetid: f7f62f53-e026-4c40-b221-3a26adb0c2c5
ms.openlocfilehash: 29c36bd0494879b66674cf3a3c404fdaf3908f59
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59323810"
---
# <a name="how-to-use-platform-invoke-to-play-a-wave-file-c-programming-guide"></a><span data-ttu-id="bbf8c-102">Vorgehensweise: Verwenden eines Plattformaufrufs zum Wiedergeben einer Wavedatei (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="bbf8c-102">How to: Use Platform Invoke to Play a Wave File (C# Programming Guide)</span></span>
<span data-ttu-id="bbf8c-103">In folgendem C#-Codebeispiel wird die Verwendung von Plattformaufrufdiensten zum Abspielen einer Audiodatei im Waveformat im Windows-Betriebssystem veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bbf8c-103">The following C# code example illustrates how to use platform invoke services to play a wave sound file on the Windows operating system.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bbf8c-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bbf8c-104">Example</span></span>  
 <span data-ttu-id="bbf8c-105">In diesem Beispielcode wird `DllImport` verwendet, um den Einstiegspunkt der `PlaySound`-Methode von `winmm.dll` als `Form1 PlaySound()` zu importieren.</span><span class="sxs-lookup"><span data-stu-id="bbf8c-105">This example code uses `DllImport` to import `winmm.dll`'s `PlaySound` method entry point as `Form1 PlaySound()`.</span></span> <span data-ttu-id="bbf8c-106">Das Beispiel hat ein einfaches Windows-Formular mit einer Schaltfläche.</span><span class="sxs-lookup"><span data-stu-id="bbf8c-106">The example has a simple Windows Form with a button.</span></span> <span data-ttu-id="bbf8c-107">Wenn Sie auf die Schaltfläche klicken, öffnet sich das Windows-Standarddialogfeld <xref:System.Windows.Forms.OpenFileDialog>, von wo aus Sie eine Datei zur Wiedergabe öffnen können.</span><span class="sxs-lookup"><span data-stu-id="bbf8c-107">Clicking the button opens a standard windows <xref:System.Windows.Forms.OpenFileDialog> dialog box so that you can open a file to play.</span></span> <span data-ttu-id="bbf8c-108">Wenn Sie eine Wavedatei auswählen, wird diese mit der `PlaySound()`-Methode der Bibliothek `winmm.dll` wiedergegeben.</span><span class="sxs-lookup"><span data-stu-id="bbf8c-108">When a wave file is selected, it is played by using the `PlaySound()` method of the `winmm.dll` library.</span></span> <span data-ttu-id="bbf8c-109">Weitere Informationen zu dieser Methode finden Sie unter [Verwenden der Funktion „PlaySound“ mit Wave-Audiodateien](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span><span class="sxs-lookup"><span data-stu-id="bbf8c-109">For more information about this method, see [Using the PlaySound function with Waveform-Audio Files](https://docs.microsoft.com/windows/desktop/multimedia/using-playsound-to-play-waveform-audio-files).</span></span> <span data-ttu-id="bbf8c-110">Suchen Sie nach einer Datei und wählen Sie eine aus, die über eine WAV-Erweiterung verfügt, und klicken Sie anschließend auf **Öffnen**, um die WAVE-Datei mit einem Plattformaufruf wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="bbf8c-110">Browse and select a file that has a .wav extension, and then click **Open** to play the wave file by using platform invoke.</span></span> <span data-ttu-id="bbf8c-111">Der vollständige Pfad der ausgewählten Datei wird in einem Textfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bbf8c-111">A text box shows the full path of the file selected.</span></span>  
  
 <span data-ttu-id="bbf8c-112">Das Dialogfeld **Open Files** (Dateien öffnen) wird so gefiltert, dass es nur Dateien mit WAV-Erweiterung anzeigt werden. Dazu werden folgende Filtereinstellungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="bbf8c-112">The **Open Files** dialog box is filtered to show only files that have a .wav extension through the filter settings:</span></span>  
  
 [!code-csharp[csProgGuideInterop#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#5)]  
  
 [!code-csharp[csProgGuideInterop#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bbf8c-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="bbf8c-113">Compiling the Code</span></span>  
  
### <a name="to-compile-the-code"></a><span data-ttu-id="bbf8c-114">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="bbf8c-114">To compile the code</span></span>  
  
1. <span data-ttu-id="bbf8c-115">Erstellen Sie in Visual Studio ein neuen Windows-Anwendungsprojekt mit C# und nennen Sie es **WinSound**.</span><span class="sxs-lookup"><span data-stu-id="bbf8c-115">Create a new C# Windows Application project in Visual Studio and name it **WinSound**.</span></span>  
  
2. <span data-ttu-id="bbf8c-116">Kopieren Sie den oben stehenden Code, und fügen Sie diesen über dem Inhalt der `Form1.cs`-Datei ein.</span><span class="sxs-lookup"><span data-stu-id="bbf8c-116">Copy the code above, and paste it over the contents of the `Form1.cs` file.</span></span>  
  
3. <span data-ttu-id="bbf8c-117">Kopieren Sie folgenden Code und fügen Sie ihn in der `Form1.Designer.cs`-Datei in der `InitializeComponent()`-Methode ein, und zwar immer nach vorhandenem Code.</span><span class="sxs-lookup"><span data-stu-id="bbf8c-117">Copy the following code, and paste it in the `Form1.Designer.cs` file, in the `InitializeComponent()` method, after any existing code.</span></span>  
  
     [!code-csharp[csProgGuideInterop#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/WinSound.cs#4)]  
  
4. <span data-ttu-id="bbf8c-118">Kompilieren Sie den Code, und führen Sie diesen aus.</span><span class="sxs-lookup"><span data-stu-id="bbf8c-118">Compile and run the code.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="bbf8c-119">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bbf8c-119">.NET Framework Security</span></span>  
 <span data-ttu-id="bbf8c-120">Weitere Informationen finden Sie unter [Sicherheit in .NET](../../../standard/security/index.md).</span><span class="sxs-lookup"><span data-stu-id="bbf8c-120">For more information, see [Security in .NET](../../../standard/security/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbf8c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbf8c-121">See also</span></span>

- [<span data-ttu-id="bbf8c-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bbf8c-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="bbf8c-123">Überblick über die Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="bbf8c-123">Interoperability Overview</span></span>](../../../csharp/programming-guide/interop/interoperability-overview.md)
- [<span data-ttu-id="bbf8c-124">Genauere Betrachtung von Plattformaufrufen</span><span class="sxs-lookup"><span data-stu-id="bbf8c-124">A Closer Look at Platform Invoke</span></span>](../../../framework/interop/consuming-unmanaged-dll-functions.md#a-closer-look-at-platform-invoke)
- [<span data-ttu-id="bbf8c-125">Marshallen von Daten mit Plattformaufruf</span><span class="sxs-lookup"><span data-stu-id="bbf8c-125">Marshaling Data with Platform Invoke</span></span>](../../../framework/interop/marshaling-data-with-platform-invoke.md)
