---
title: 'Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten'
ms.date: 03/30/2017
ms.assetid: a6c5bf6e-064a-4f77-b74c-76b3a5dec309
ms.openlocfilehash: bbe40ec448bef5f62d4182d96f82c6308639e27f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033799"
---
# <a name="how-to-make-entities-serializable"></a><span data-ttu-id="3ade5-102">Vorgehensweise: Aktivieren der Serialisierbarkeit von Entitäten</span><span class="sxs-lookup"><span data-stu-id="3ade5-102">How to: Make Entities Serializable</span></span>
<span data-ttu-id="3ade5-103">Sie können die Serialisierbarkeit von Entitäten aktivieren, wenn Sie den Code generieren.</span><span class="sxs-lookup"><span data-stu-id="3ade5-103">You can make entities serializable when you generate your code.</span></span> <span data-ttu-id="3ade5-104">Entitätsklassen werden mit dem <xref:System.Runtime.Serialization.DataContractAttribute>-Attribut und Spalten mit dem <xref:System.Runtime.Serialization.DataMemberAttribute>-Attribut ergänzt.</span><span class="sxs-lookup"><span data-stu-id="3ade5-104">Entity classes are decorated with the <xref:System.Runtime.Serialization.DataContractAttribute> attribute, and columns with the <xref:System.Runtime.Serialization.DataMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="3ade5-105">Können Entwickler mithilfe von Visual Studio die [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] für diesen Zweck.</span><span class="sxs-lookup"><span data-stu-id="3ade5-105">Developers using Visual Studio can use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for this purpose.</span></span>  
  
 <span data-ttu-id="3ade5-106">Wenn Sie das SQLMetal-Befehlszeilentool verwenden, verwenden Sie die **/serialization** -Option mit der `unidirectional` Argument.</span><span class="sxs-lookup"><span data-stu-id="3ade5-106">If you are using the SQLMetal command-line tool, use the **/serialization** option with the `unidirectional` argument.</span></span> <span data-ttu-id="3ade5-107">Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="3ade5-107">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ade5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ade5-108">Example</span></span>  
 <span data-ttu-id="3ade5-109">Die folgenden SQLMetal-Befehlszeilen erzeugen Dateien, die serialisierbare Entitäten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3ade5-109">The following SQLMetal command lines produce files that have serializable entities.</span></span>  
  
```  
sqlmetal /code:nwserializable.vb /language:vb "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
```  
sqlmetal /code:nwserializable.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize /serialization:unidirectional  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ade5-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ade5-110">See also</span></span>

- [<span data-ttu-id="3ade5-111">Serialisierung</span><span class="sxs-lookup"><span data-stu-id="3ade5-111">Serialization</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/serialization.md)
- [<span data-ttu-id="3ade5-112">Erstellen des Objektmodells</span><span class="sxs-lookup"><span data-stu-id="3ade5-112">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
