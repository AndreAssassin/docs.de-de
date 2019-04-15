---
title: Qualifizieren von .NET-Typen für die Interoperation
ms.date: 03/30/2017
helpviewer_keywords:
- exposing .NET Framework components to COM
- COM interop, qualifying .NET types
- qualifying .NET types for interoperation
- interoperation with unmanaged code, qualifying .NET types
- interoperation with unmanaged code, exposing .NET Framework components
- COM interop, exposing COM components
ms.assetid: 4b8afb52-fb8d-4e65-b47c-fd82956a3cdd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cad67f52a4ca977606d7b5a307868ff129570e6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097976"
---
# <a name="qualifying-net-types-for-interoperation"></a>Qualifizieren von .NET-Typen für die Interoperation
Wenn Sie beabsichtigen, Typen in einer Assembly für eine COM-Anwendung verfügbar zu machen, beachten Sie zur Entwurfszeit die Anforderungen von Com-Interop. Verwaltete Typen (Klassen, Schnittstellen, Strukturen und Enumerationen) lassen sich nahtlos in COM-Typen integrieren, wenn Sie die folgenden Richtlinien einhalten:  
  
-   Klassen sollten Schnittstellen explizit implementieren.  
  
     COM-Interop stellt zwar einen Mechanismus bereit, mit dem automatisch eine Schnittstelle generiert wird, die alle Member einer Klasse und die Member der dazugehörigen Basisklasse enthält, dennoch ist es besser, explizite Schnittstellen bereitzustellen. Die automatisch generierte Schnittstelle wird als Klassenschnittstelle bezeichnet. Informationen zu Richtlinien finden Sie unter [Einführung in die Klassenschnittstelle](com-callable-wrapper.md#introducing-the-class-interface).  
  
     Sie können Visual Basic, C# und C++ verwenden, um Schnittstellendefinitionen in Ihren Code einzuschließen. So müssen Sie nicht die Interface Definition Language (IDL) oder eine ähnliche Sprache verwenden. Einzelheiten zur Syntax finden Sie in der Dokumentation zur Sprache.  
  
-   Verwaltete Typen müssen öffentlich sein.  
  
     Nur öffentliche Typen in einer Assembly werden registriert und in die Typbibliothek exportiert. Dies hat zur Folge, dass nur öffentliche Typen für das COM sichtbar sind.  
  
     Dank verwalteter Typen stehen Funktionen auch in anderem verwaltetem Code zur Verfügung, der möglicherweise nicht für COM verfügbar ist. COM-Clients haben z.B. keinen Zugriff auf parametrisierte Konstruktoren, statische Methoden und Konstantenfelder. Wenn die Runtime Daten in einen Typ hinein und aus einem Typ heraus marshallt, werden diese Daten möglicherweise kopiert oder umgewandelt.  
  
-   Methoden, Eigenschaften, Felder und Ereignisse müssen öffentlich sein.  
  
     Member öffentlicher Typen müssen ebenfalls öffentlich sein, wenn sie im COM sichtbar sein sollen. Sie können die Sichtbarkeit einer Assembly, eines öffentlichen Typs oder öffentlicher Member eines öffentlichen Typs einschränken, indem Sie die Klasse <xref:System.Runtime.InteropServices.ComVisibleAttribute> anwenden. Standardmäßig sind alle öffentlichen Typen und Member sichtbar.  
  
-   Typen müssen über einen öffentlichen Standardkonstruktor verfügen, der sich über das COM aktivieren lässt.  
  
     Verwaltete, öffentliche Typen sind im COM sichtbar. Ohne einen öffentlichen Standardkonstruktor (d.h. einen Konstruktor ohne Argumente) können COM-Clients den Typ nicht erstellen. Wenn er auf andere Art und Weise aktiviert wird, können sie den Typ aber dennoch verwenden.  
  
-   Typen können nicht abstrakt sein.  
  
     Weder COM-Clients noch .NET-Clients können abstrakte Typen erstellen.  
  
 Beim Export eines verwalteten Typs in das COM wird seine Vererbungshierarchie vereinfacht. Auch die Versionsverwaltung läuft bei verwalteten und nicht verwalteten Umgebungen unterschiedlich ab. Im COM verfügbare Typen haben nicht dieselben Versionsverwaltungseigenschaften wie andere verwaltete Typen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.InteropServices.ComVisibleAttribute>
- [Verfügbarmachen von .NET Framework-Komponenten in COM](../../../docs/framework/interop/exposing-dotnet-components-to-com.md)
- [Einführung in die Klassenschnittstelle](com-callable-wrapper.md#introducing-the-class-interface)
- [Anwenden von Interop-Attributen](../../../docs/framework/interop/applying-interop-attributes.md)
- [Verpacken einer Assembly für COM](../../../docs/framework/interop/packaging-an-assembly-for-com.md)
