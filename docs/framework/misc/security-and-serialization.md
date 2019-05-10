---
title: Sicherheit und Serialisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, serialization
- serialization, security
- secure coding, serialization
- security [.NET Framework], serialization
ms.assetid: b921bc94-bd3a-4c91-9ede-2c8d4f78ea9a
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c275e7179daf0dfdf2dda8bf364a4682565f28a6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596730"
---
# <a name="security-and-serialization"></a><span data-ttu-id="1be30-102">Sicherheit und Serialisierung</span><span class="sxs-lookup"><span data-stu-id="1be30-102">Security and Serialization</span></span>
<span data-ttu-id="1be30-103">Da bei Serialisierung die Möglichkeit besteht, dass anderer Code Objektinstanzdaten anzeigen oder ändern kann, auf die andernfalls nicht zugegriffen werden könnte, wird für Code, der Serialisierung ausführt, eine spezielle Berechtigung benötigt: <xref:System.Security.Permissions.SecurityPermission> mit angegebenem <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> -Flag.</span><span class="sxs-lookup"><span data-stu-id="1be30-103">Because serialization can allow other code to see or modify object instance data that would otherwise be inaccessible, a special permission is required of code performing serialization: <xref:System.Security.Permissions.SecurityPermission> with the <xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter> flag specified.</span></span> <span data-ttu-id="1be30-104">Entsprechend der Standardrichtlinie bedeutet dies, dass diese Berechtigung nicht für aus dem Internet heruntergeladenen Code oder Code aus einem Intranet erteilt wird. Diese Berechtigung wird nur für Code auf dem lokalen Computer erteilt.</span><span class="sxs-lookup"><span data-stu-id="1be30-104">Under default policy, this permission is not given to Internet-downloaded or intranet code; only code on the local computer is granted this permission.</span></span>  
  
 <span data-ttu-id="1be30-105">Normalerweise werden alle Felder einer Objektinstanz serialisiert. Das heißt, dass die Daten in den serialisierten Daten für die Instanz dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="1be30-105">Normally, all fields of an object instance are serialized, meaning that data is represented in the serialized data for the instance.</span></span> <span data-ttu-id="1be30-106">Code mit der Fähigkeit zum Interpretieren des Formats kann die Datenwerte unabhängig davon bestimmen, wie auf den Member zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="1be30-106">It is possible for code that can interpret the format to determine what the data values are, independent of the accessibility of the member.</span></span> <span data-ttu-id="1be30-107">Ähnliches gilt für Deserialisierung. Dabei werden Daten aus der serialisierten Darstellung extrahiert, und der Objektzustand wird direkt festgelegt, wiederum ohne Beachtung der Zugriffsregeln.</span><span class="sxs-lookup"><span data-stu-id="1be30-107">Similarly, deserialization extracts data from the serialized representation and sets object state directly, again irrespective of accessibility rules.</span></span>  
  
 <span data-ttu-id="1be30-108">Jedes Objekt, das sicherheitsrelevante Daten enthalten kann, sollte nach Möglichkeit als nicht serialisierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1be30-108">Any object that could contain security-sensitive data should be made nonserializable, if possible.</span></span> <span data-ttu-id="1be30-109">Wenn ein Objekt serialisierbar sein muss, sollten die Felder, die vertrauliche Daten enthalten, als nicht serialisierbar festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="1be30-109">If it must be serializable, try to make specific fields that hold sensitive data nonserializable.</span></span> <span data-ttu-id="1be30-110">Wenn dies nicht möglich ist, müssen Sie berücksichtigen, dass diese Daten für jeglichen Code verfügbar gemacht werden, der die Berechtigung zum Serialisieren hat. Stellen Sie daher sicher, dass kein bösartiger Code diese Berechtigung erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="1be30-110">If this cannot be done, be aware that this data will be exposed to any code that has permission to serialize, and make sure that no malicious code can get this permission.</span></span>  
  
 <span data-ttu-id="1be30-111">Die <xref:System.Runtime.Serialization.ISerializable> -Schnittstelle ist nur zur Verwendung durch die Serialisierungsinfrastruktur vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="1be30-111">The <xref:System.Runtime.Serialization.ISerializable> interface is intended for use only by the serialization infrastructure.</span></span> <span data-ttu-id="1be30-112">Ist sie aber nicht geschützt ist, kann sie vertrauliche Informationen freigeben.</span><span class="sxs-lookup"><span data-stu-id="1be30-112">However, if unprotected, it can potentially release sensitive information.</span></span> <span data-ttu-id="1be30-113">Wenn Sie benutzerdefinierte Serialisierung bereitstellen, indem Sie **ISerializable**implementieren, müssen Sie die folgenden Vorsichtsmaßnahmen treffen:</span><span class="sxs-lookup"><span data-stu-id="1be30-113">If you provide custom serialization by implementing **ISerializable**, make sure you take the following precautions:</span></span>  
  
- <span data-ttu-id="1be30-114">Die <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> -Methode muss explizit geschützt werden, indem Sie entweder die **SecurityPermission** mit der **SerializationFormatter** -Berechtigung fordern oder sicherstellen, dass über die Methodenausgabe keine vertraulichen Informationen freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1be30-114">The <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> method should be explicitly secured either by demanding the **SecurityPermission** with **SerializationFormatter** permission specified or by making sure that no sensitive information is released with the method output.</span></span> <span data-ttu-id="1be30-115">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1be30-115">For example:</span></span>  
  
    ```vb  
    Public Overrides<SecurityPermissionAttribute(SecurityAction.Demand, SerializationFormatter := True)>  _  
    Sub GetObjectData(info As SerializationInfo, context As StreamingContext)  
    End Sub  
    ```  
  
    ```csharp  
    [SecurityPermissionAttribute(SecurityAction.Demand,SerializationFormatter   
    =true)]  
    public override void GetObjectData(SerializationInfo info,   
    StreamingContext context)  
    {  
    }  
    ```  
  
- <span data-ttu-id="1be30-116">Der spezielle Konstruktor, der für die Serialisierung verwendet wird, muss außerdem eine sorgfältige Überprüfung von Eingabe ausführen und entweder geschützt oder privat sein, um Missbrauch durch bösartigen Code zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1be30-116">The special constructor used for serialization should also perform thorough input validation and should be either protected or private to help protect against misuse by malicious code.</span></span> <span data-ttu-id="1be30-117">Außerdem sollte der Konstruktor dieselben Sicherheitsüberprüfungen und Berechtigungen erzwingen, die erforderlich sind, um eine Instanz einer solchen Klasse auf andere Weise zu erhalten, beispielsweise explizites Erstellen der Klasse oder indirektes Erstellen der Klasse über eine Factory.</span><span class="sxs-lookup"><span data-stu-id="1be30-117">It should enforce the same security checks and permissions required to obtain an instance of such a class by any other means, such as explicitly creating the class or indirectly creating it through some kind of factory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1be30-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1be30-118">See also</span></span>

- [<span data-ttu-id="1be30-119">Richtlinien für das Schreiben von sicherem Code</span><span class="sxs-lookup"><span data-stu-id="1be30-119">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
