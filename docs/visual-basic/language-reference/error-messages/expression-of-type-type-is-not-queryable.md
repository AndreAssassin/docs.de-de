---
title: Ein Ausdruck vom Typ <type> kann nicht abgefragt werden
ms.date: 07/20/2015
f1_keywords:
- bc36593
- vbc36593
helpviewer_keywords:
- BC36593
ms.assetid: 6f1f5860-bf97-4885-9ebb-bc87d028095c
ms.openlocfilehash: 121c0a95a3a6bb695d9c73347c733cba215a0de4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304154"
---
# <a name="expression-of-type-type-is-not-queryable"></a>Ein Ausdruck vom Typ \<Typs > kann nicht abgefragt werden
Ein Ausdruck vom Typ \<Typs > kann nicht abgefragt werden. Stellen Sie sicher, dass eine Assembly und/oder Namespaceimport importieren keine für den LINQ-Anbieter fehlt.  
  
 Abfragbare Typen werden definiert, der <xref:System.Linq>, <xref:System.Data.Linq>, und <xref:System.Xml.Linq> Namespaces. Importieren Sie eine oder mehrere dieser Namespaces zur LINQ-Abfragen auszuführen.  
  
 Die <xref:System.Linq> Namespace können Sie Abfrageobjekte wie z. B. Sammlungen und Arrays mithilfe von LINQ.  
  
 Die <xref:System.Data.Linq> -Namespace ermöglicht Ihnen, ADO.NET Datasets und SQL Server-Datenbanken mithilfe von LINQ abzufragen.  
  
 Die <xref:System.Xml.Linq> Namespace können Sie XML-Abfrage mithilfe von LINQ und XML-Features in Visual Basic verwenden.  
  
 **Fehler-ID:** BC36593  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Hinzufügen einer `Import` -Anweisung für die <xref:System.Linq>, <xref:System.Data.Linq>, oder <xref:System.Xml.Linq> Namespace Ihrer Codedatei. Sie können auch Namespaces für Ihr Projekt importieren, mit der **Verweise** auf der Seite im Projekt-Designer (**Mein Projekt**).  
  
2. Stellen Sie sicher, dass des Typs, den Sie identifiziert haben, wie die Quelle der Abfrage ein abfragbarer Typ ist. D. h. einen Typ, der implementiert <xref:System.Collections.Generic.IEnumerable%601> oder <xref:System.Linq.IQueryable%601>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Linq>
- <xref:System.Data.Linq>
- <xref:System.Xml.Linq>
- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../visual-basic/programming-guide/language-features/linq/index.md)
- [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)
- [Verweise und die Imports-Anweisung](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [Seite „Verweise“, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/references-page-project-designer-visual-basic)
