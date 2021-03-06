---
title: Einschränkung der referenziellen Integrität
ms.date: 03/30/2017
ms.assetid: 3d3ba44b-4302-40d8-a7a9-62932e0395e5
ms.openlocfilehash: ad35df7bcca62ffdbc3842b0817b22c5482a3d4d
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738372"
---
# <a name="referential-integrity-constraint"></a>Einschränkung der referenziellen Integrität
Eine *Einschränkung der referenziellen Integrität* im Entity Data Model (EDM) ähnelt einer Einschränkung der referenziellen Integrität in einer relationalen Datenbank. Auf dieselbe Weise, wie eine Spalte (oder Spalten) einer Datenbanktabelle auf den Primärschlüssel einer anderen Tabelle verweisen kann, kann eine [Eigenschaft](property.md) (oder Eigenschaften) eines [Entitäts Typs](entity-type.md) auf den [Entitäts Schlüssel](entity-key.md) eines anderen Entitäts Typs verweisen. Der Entitätstyp, auf den verwiesen wird, wird als *Prinzipal Ende* der Einschränkung bezeichnet. Der Entitätstyp, der auf das Prinzipal Ende verweist, wird als *abhängiges Ende* der Einschränkung bezeichnet.  
  
 Eine Einschränkung der referenziellen Integrität wird als Teil einer Zuordnung [zwischen zwei](association-type.md) Entitäts Typen definiert. Die Definition für eine Einschränkung der referenziellen Integrität gibt die folgenden Informationen an:  
  
- Das Prinzipalende der Einschränkung. (Ein Entitätstyp, auf dessen Entitätsschlüssel durch das abhängige Ende verwiesen wird.)  
  
- Den Entitätsschlüssel des Prinzipalendes.  
  
- Das abhängige Ende der Einschränkung. (Ein Entitätstyp, der über eine Eigenschaft oder Eigenschaften verfügt, die auf den Entitätsschlüssel des Prinzipalendes verweisen.)  
  
- Die verweisende Eigenschaft oder Eigenschaften des abhängigen Endes.  
  
 Mit Einschränkungen der referenziellen Integrität im EDM soll sichergestellt werden, dass gültige Zuordnungen immer vorhanden sind. Weitere Informationen finden Sie unter [Fremdschlüssel Eigenschaft](foreign-key-property.md).  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `WrittenBy` und `PublishedBy`. Der `Book`-Entitätstyp verfügt über die Eigenschaft `PublisherId`, die auf den Entitätsschlüssel des `Publisher`-Entitätstyps verweist, wenn Sie eine Einschränkung der referenziellen Integrität für die `PublishedBy`-Zuordnung definieren.  
  
 ![Ref-Einschränkung](./media/referential-integrity-constraint/reference-constraint-model.gif "Beispiel eines referenziellen Einschränkungs Modells")  
  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert eine Einschränkung der referenziellen Integrität für die oben im konzeptionellen Modell gezeigte `PublishedBy`-Zuordnung.  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
