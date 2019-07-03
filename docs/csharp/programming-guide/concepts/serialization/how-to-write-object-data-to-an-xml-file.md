---
title: 'Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei (C#)'
ms.date: 07/20/2015
ms.assetid: 7681eb98-703d-4005-a369-26a7bca0f894
ms.openlocfilehash: 77d3a45f6213bc390e0b3da0d30cfbc55235b1d1
ms.sourcegitcommit: a8d3504f0eae1a40bda2b06bd441ba01f1631ef0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2019
ms.locfileid: "67170235"
---
# <a name="how-to-write-object-data-to-an-xml-file-c"></a><span data-ttu-id="477fd-102">Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="477fd-102">How to: Write Object Data to an XML File (C#)</span></span>
<span data-ttu-id="477fd-103">Dieses Beispiel verwendet die <xref:System.Xml.Serialization.XmlSerializer>-Klasse, um das Objekt aus einer Klasse in eine XML-Datei zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="477fd-103">This example writes the object from a class to an XML file using the <xref:System.Xml.Serialization.XmlSerializer> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="477fd-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="477fd-104">Example</span></span>  
  
```csharp  
public class XMLWrite  
{  
  
   static void Main(string[] args)  
    {  
        WriteXML();  
    }  
  
    public class Book  
    {  
        public String title;   
    }  
  
    public static void WriteXML()  
    {  
        Book overview = new Book();  
        overview.title = "Serialization Overview";  
        System.Xml.Serialization.XmlSerializer writer =   
            new System.Xml.Serialization.XmlSerializer(typeof(Book));  
  
        var path = Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments) + "//SerializationOverview.xml";  
        System.IO.FileStream file = System.IO.File.Create(path);  
  
        writer.Serialize(file, overview);  
        file.Close();  
    }  
}  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="477fd-105">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="477fd-105">Compiling the Code</span></span>  
 <span data-ttu-id="477fd-106">Die zu serialisierende Klasse muss über einen öffentlichen Konstruktor ohne Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="477fd-106">The class being serialized must have a public constructor without parameters.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="477fd-107">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="477fd-107">Robust Programming</span></span>  
 <span data-ttu-id="477fd-108">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="477fd-108">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="477fd-109">Die zu serialisierende Klasse verfügt nicht über einen öffentlichen, parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="477fd-109">The class being serialized does not have a public, parameterless constructor.</span></span>  
  
- <span data-ttu-id="477fd-110">Die Datei ist bereits vorhanden und schreibgeschützt (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="477fd-110">The file exists and is read-only (<xref:System.IO.IOException>).</span></span>  
  
- <span data-ttu-id="477fd-111">Der Pfad ist zu lang (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="477fd-111">The path is too long (<xref:System.IO.PathTooLongException>).</span></span>  
  
- <span data-ttu-id="477fd-112">Der Datenträger ist voll (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="477fd-112">The disk is full (<xref:System.IO.IOException>).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="477fd-113">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="477fd-113">.NET Framework Security</span></span>  
 <span data-ttu-id="477fd-114">Mit diesem Beispiel wird eine neue Datei erstellt, wenn diese noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="477fd-114">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="477fd-115">Wenn eine Anwendung eine Datei erstellen muss, benötigt sie eine `Create`-Berechtigung für den Ordner.</span><span class="sxs-lookup"><span data-stu-id="477fd-115">If an application needs to create a file, that application needs `Create` access for the folder.</span></span> <span data-ttu-id="477fd-116">Wenn die Datei bereits vorhanden ist, benötigt die Anwendung lediglich die Berechtigung für den `Write`-Zugriff, also eine geringere Berechtigung.</span><span class="sxs-lookup"><span data-stu-id="477fd-116">If the file already exists, the application needs only `Write` access, a lesser privilege.</span></span> <span data-ttu-id="477fd-117">Aus Sicherheitsgründen sollte die Datei nach Möglichkeit erst im Verlauf der Bereitstellung erstellt werden. Außerdem sollte nur die `Read`-Berechtigung für eine einzelne Datei erteilt werden (anstatt `Create`-Berechtigungen für den gesamten Ordner zu gewähren).</span><span class="sxs-lookup"><span data-stu-id="477fd-117">Where possible, it is more secure to create the file during deployment, and only grant `Read` access to a single file, rather than `Create` access for a folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="477fd-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="477fd-118">See also</span></span>

- <xref:System.IO.StreamWriter>
- [<span data-ttu-id="477fd-119">Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="477fd-119">How to: Read Object Data from an XML File (C#)</span></span>](../../../../csharp/programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="477fd-120">Serialisierung (C#)</span><span class="sxs-lookup"><span data-stu-id="477fd-120">Serialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/serialization/index.md)
