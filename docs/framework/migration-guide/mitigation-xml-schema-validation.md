---
title: 'Entschärfung: XML-Schemavalidierung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5c0087412a53177a7c43df838266f6d896c1bd9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220473"
---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="7759e-102">Entschärfung: XML-Schemavalidierung</span><span class="sxs-lookup"><span data-stu-id="7759e-102">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="7759e-103">In [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ermittelt die XSD-Schemavalidierung einen Verstoß gegen die Unique-Einschränkung, wenn ein Verbundschlüssel verwendet wird und ein Schlüssel leer ist.</span><span class="sxs-lookup"><span data-stu-id="7759e-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="7759e-104">Auswirkungen</span><span class="sxs-lookup"><span data-stu-id="7759e-104">Impact</span></span>  
 <span data-ttu-id="7759e-105">Die Auswirkung dieser Änderung sollte minimal sein: In Abhängigkeit der Schemaspezifikation wir ein Schemavalidierungsfehler erwartet, wenn `xsd:unique` mithilfe eines Verbundschlüssels mit einem leeren Schlüssel verletzt wird.</span><span class="sxs-lookup"><span data-stu-id="7759e-105">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="7759e-106">Minderung</span><span class="sxs-lookup"><span data-stu-id="7759e-106">Mitigation</span></span>  
 <span data-ttu-id="7759e-107">Ob ein Schemavalidierungsfehler erkannt wird, wenn ein Verbundschlüssel über einen leeren Schlüssel verfügt, kann konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="7759e-107">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
-   <span data-ttu-id="7759e-108">Angefangen bei den Apps, die auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] abzielen, ist die Ermittlung des Schemavalidierungsfehlers standardmäßig aktiviert. Es ist jedoch möglich, dieses Verhalten abzuwählen, wodurch der Schemavalidierungsfehler nicht ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="7759e-108">Starting with the apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
-   <span data-ttu-id="7759e-109">In unter [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] ausgeführten Apps, die jedoch auf [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] und frühere Versionen abzielen, wird eine Schemavalidierungsfehler nicht standardmäßig ermittelt. Es ist jedoch möglich, dieses Verhalten zu aktivieren, sodass der Schemavalidierungsfehler ermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="7759e-109">In apps that run under the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] but target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="7759e-110">Dieses Verhalten kann mithilfe der Klasse <xref:System.AppContext> konfiguriert werden, um den Wert des Switches `System.Xml.IgnoreEmptyKeySequences` zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7759e-110">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="7759e-111">Da der Standardwert des Switches `false` (leere Schlüsselsequenzen werden nicht ignoriert) lautet, können auf [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] abzielende Apps dieses Verhalten abwählen, indem der folgende Code verwendet wird, um den Wert des Switches auf `true` festzulegen:</span><span class="sxs-lookup"><span data-stu-id="7759e-111">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 <span data-ttu-id="7759e-112">Bei Apps, die auf [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] und frühere Versionen abzielen, ist es möglich, da der Standardwert des Switches `true` (leere Schlüsselsequenzen werden ignoriert) lautet, sicherzustellen, dass ein Verbundschlüssel mit einem leeren Schlüssel einen Schemavalidierungsfehler generiert, indem der folgende Code zum Festlegen des Switchwerts auf `false` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7759e-112">For apps that target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7759e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7759e-113">See also</span></span>

- [<span data-ttu-id="7759e-114">Neuzuweisungsänderungen</span><span class="sxs-lookup"><span data-stu-id="7759e-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
