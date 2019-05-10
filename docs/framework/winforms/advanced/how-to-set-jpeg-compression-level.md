---
title: 'Vorgehensweise: Festlegen der JPEG-Komprimierungsebene'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], changing encoder parameters
- JPEG images [Windows Forms], setting quality level
ms.assetid: 4b9a74e3-9504-43c1-9f28-ace651d0772e
ms.openlocfilehash: 1b325c0cb8fe9da4b198d19164c73af9b1609973
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626139"
---
# <a name="how-to-set-jpeg-compression-level"></a><span data-ttu-id="9e244-102">Vorgehensweise: Festlegen der JPEG-Komprimierungsebene</span><span class="sxs-lookup"><span data-stu-id="9e244-102">How to: Set JPEG Compression Level</span></span>
<span data-ttu-id="9e244-103">Möglicherweise möchten Sie die Parameter eines Bilds ändern, wenn Sie das Bild auf einem Datenträger speichern, um dadurch die Dateigröße zu minimieren oder die Qualität zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="9e244-103">You may want to modify the parameters of an image when you save the image to disk to minimize the file size or improve its quality.</span></span> <span data-ttu-id="9e244-104">Sie können die Qualität eines JPEG-Bilds anpassen, indem Sie seine Komprimierungsebene ändern.</span><span class="sxs-lookup"><span data-stu-id="9e244-104">You can adjust the quality of a JPEG image by modifying its compression level.</span></span> <span data-ttu-id="9e244-105">Zum Angeben der Komprimierungsebene beim Speichern eines JPEG-Bilds müssen Sie erstellen eine <xref:System.Drawing.Imaging.EncoderParameters> -Objekt und übergeben Sie sie an der <xref:System.Drawing.Image.Save%2A> Methode der <xref:System.Drawing.Image> Klasse.</span><span class="sxs-lookup"><span data-stu-id="9e244-105">To specify the compression level when you save a JPEG image, you must create an <xref:System.Drawing.Imaging.EncoderParameters> object and pass it to the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class.</span></span> <span data-ttu-id="9e244-106">Initialisieren der <xref:System.Drawing.Imaging.EncoderParameters> Objekt so, dass die It verfügt über ein Array, das eine besteht <xref:System.Drawing.Imaging.EncoderParameter>.</span><span class="sxs-lookup"><span data-stu-id="9e244-106">Initialize the <xref:System.Drawing.Imaging.EncoderParameters> object so that it has an array that consists of one <xref:System.Drawing.Imaging.EncoderParameter>.</span></span> <span data-ttu-id="9e244-107">Bei der Erstellung der <xref:System.Drawing.Imaging.EncoderParameter>, geben Sie die <xref:System.Drawing.Imaging.Encoder.Quality> Encoder und die gewünschte Komprimierungsebene.</span><span class="sxs-lookup"><span data-stu-id="9e244-107">When you create the <xref:System.Drawing.Imaging.EncoderParameter>, specify the <xref:System.Drawing.Imaging.Encoder.Quality> encoder, and the desired compression level.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e244-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9e244-108">Example</span></span>  
 <span data-ttu-id="9e244-109">Der folgende Beispielcode erstellt eine <xref:System.Drawing.Imaging.EncoderParameter> -Objekt und drei JPEG-Bilder gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9e244-109">The following example code creates an <xref:System.Drawing.Imaging.EncoderParameter> object and saves three JPEG images.</span></span> <span data-ttu-id="9e244-110">Jedes JPEG-Bild wird mit einer anderen Qualitätsstufe gespeichert, durch Ändern der `long` übergebenen Wert die <xref:System.Drawing.Imaging.EncoderParameter> Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="9e244-110">Each JPEG image is saved with a different quality level, by modifying the `long` value passed to the <xref:System.Drawing.Imaging.EncoderParameter> constructor.</span></span> <span data-ttu-id="9e244-111">Die Qualitätsstufe 0 steht für die höchste, die Qualitätsstufe 100 für die niedrigste Komprimierung.</span><span class="sxs-lookup"><span data-stu-id="9e244-111">A quality level of 0 corresponds to the greatest compression, and a quality level of 100 corresponds to the least compression.</span></span>  
  
```csharp  
private void VaryQualityLevel()  
    {  
        // Get a bitmap. The using statement ensures objects  
        // are automatically disposed from memory after use.  
        using (Bitmap bmp1 = new Bitmap(@"C:\TestPhoto.jpg"))  
        {  
            ImageCodecInfo jpgEncoder = GetEncoder(ImageFormat.Jpeg);  
  
            // Create an Encoder object based on the GUID  
            // for the Quality parameter category.  
            System.Drawing.Imaging.Encoder myEncoder =  
                System.Drawing.Imaging.Encoder.Quality;  
  
            // Create an EncoderParameters object.  
            // An EncoderParameters object has an array of EncoderParameter  
            // objects. In this case, there is only one  
            // EncoderParameter object in the array.  
            EncoderParameters myEncoderParameters = new EncoderParameters(1);  
  
            EncoderParameter myEncoderParameter = new EncoderParameter(myEncoder, 50L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"c:\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters);  
  
            myEncoderParameter = new EncoderParameter(myEncoder, 100L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters);  
  
            // Save the bitmap as a JPG file with zero quality level compression.  
            myEncoderParameter = new EncoderParameter(myEncoder, 0L);  
            myEncoderParameters.Param[0] = myEncoderParameter;  
            bmp1.Save(@"C:\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters);  
        }  
    }  
```  
  
```vb  
Private Sub VaryQualityLevel()  
    ' Get a bitmap. The Using statement ensures objects  
    ' are automatically disposed from memory after use.  
    Using bmp1 As New Bitmap("C:\test\TestPhoto.jpg")  
        Dim jpgEncoder As ImageCodecInfo = GetEncoder(ImageFormat.Jpeg)  
  
        ' Create an Encoder object based on the GUID  
        ' for the Quality parameter category.  
        Dim myEncoder As System.Drawing.Imaging.Encoder = System.Drawing.Imaging.Encoder.Quality  
  
        ' Create an EncoderParameters object.  
        ' An EncoderParameters object has an array of EncoderParameter  
        ' objects. In this case, there is only one  
        ' EncoderParameter object in the array.  
        Dim myEncoderParameters As New EncoderParameters(1)  
  
        Dim myEncoderParameter As New EncoderParameter(myEncoder, 50L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("c:\test\TestPhotoQualityFifty.jpg", jpgEncoder, myEncoderParameters)  
  
        myEncoderParameter = New EncoderParameter(myEncoder, 100L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityHundred.jpg", jpgEncoder, myEncoderParameters)  
  
        ' Save the bitmap as a JPG file with zero quality level compression.  
        myEncoderParameter = New EncoderParameter(myEncoder, 0L)  
        myEncoderParameters.Param(0) = myEncoderParameter  
        bmp1.Save("C:\test\TestPhotoQualityZero.jpg", jpgEncoder, myEncoderParameters)  
    End Using  
End Sub  
```  
  
```csharp  
private ImageCodecInfo GetEncoder(ImageFormat format)  
{  
    ImageCodecInfo[] codecs = ImageCodecInfo.GetImageDecoders();  
    foreach (ImageCodecInfo codec in codecs)  
    {  
        if (codec.FormatID == format.Guid)  
        {  
            return codec;  
        }  
    }  
    return null;  
}  
```  
  
```vb  
Private Function GetEncoder(ByVal format As ImageFormat) As ImageCodecInfo  
  
    Dim codecs As ImageCodecInfo() = ImageCodecInfo.GetImageDecoders()  
    Dim codec As ImageCodecInfo  
    For Each codec In codecs  
        If codec.FormatID = format.Guid Then  
            Return codec  
        End If  
    Next codec  
    Return Nothing  
  
End Function  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9e244-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="9e244-112">Compiling the Code</span></span>  
 <span data-ttu-id="9e244-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9e244-113">This example requires:</span></span>  
  
- <span data-ttu-id="9e244-114">Eine Windows Forms-Anwendung</span><span class="sxs-lookup"><span data-stu-id="9e244-114">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="9e244-115">Ein <xref:System.Windows.Forms.PaintEventArgs>, d.h. ein Parameter vom <xref:System.Windows.Forms.PaintEventHandler>.</span><span class="sxs-lookup"><span data-stu-id="9e244-115">A <xref:System.Windows.Forms.PaintEventArgs>, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
- <span data-ttu-id="9e244-116">Eine Bilddatei mit dem Namen `TestPhoto.jpg`, die unter **c:\\** gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="9e244-116">An image file that is named `TestPhoto.jpg` and located at **c:\\**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e244-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9e244-117">See also</span></span>

- [<span data-ttu-id="9e244-118">Vorgehensweise: Ermitteln der von einem Encoder unterstützten Parameter</span><span class="sxs-lookup"><span data-stu-id="9e244-118">How to: Determine the Parameters Supported by an Encoder</span></span>](how-to-determine-the-parameters-supported-by-an-encoder.md)
- [<span data-ttu-id="9e244-119">Typen von Bitmaps</span><span class="sxs-lookup"><span data-stu-id="9e244-119">Types of Bitmaps</span></span>](types-of-bitmaps.md)
- [<span data-ttu-id="9e244-120">Verwenden von Bildencodern und -decodern in Managed GDI+</span><span class="sxs-lookup"><span data-stu-id="9e244-120">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
