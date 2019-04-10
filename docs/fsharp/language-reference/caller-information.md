---
title: Aufruferinformationen
description: Beschreibt die Attribute "Callerinfo"-Argument zu verwenden, um von einer Methode memberaufruferinformationen zu erhalten.
ms.date: 04/25/2017
ms.openlocfilehash: 13092df453b684d3ed4a93c842ea49c066157cb6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59316153"
---
# <a name="caller-information"></a>Aufruferinformationen

Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen. Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen. Diese Informationen sind zum Verfolgen, Debuggen und Erstellen von Diagnosetools sehr nützlich.

Um diese Informationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden, von denen jeder einen Standardwert besitzt. Die folgende Tabelle enthält die Aufrufer-Informationsattribute, die definiert sind die ["System.Runtime.CompilerServices"](/dotnet/api/system.runtime.compilerservices) Namespace:

|Attribut|Beschreibung|Typ|
|---------|-----------|----|
|[CallerFilePath](/dotnet/api/system.runtime.compilerservices.callerfilepathattribute)|Vollständiger Pfad der Quelldatei, die den Aufrufer enthält. Dies ist der Dateipfad zum Zeitpunkt der Kompilierung.|`String`
|[CallerLineNumber](/dotnet/api/system.runtime.compilerservices.callerlinenumberattribute)|Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird.|`Integer`|
|[CallerMemberName](/dotnet/api/system.runtime.compilerservices.callermembernameattribute)|Der Methoden- oder Eigenschaftenname des Aufrufers. Finden Sie im Abschnitt "Elementnamen" weiter unten in diesem Thema.|`String`|

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie diese Attribute verwenden können, um einen Aufrufer zu verfolgen.

```fsharp
open System.Diagnostics
open System.Runtime.CompilerServices
open System.Runtime.InteropServices

type Tracer() =
    member __.DoTrace(message: string,
                      [<CallerMemberName; Optional; DefaultParameterValue("")>] memberName: string,
                      [<CallerFilePath; Optional; DefaultParameterValue("")>] path: string,
                      [<CallerLineNumber; Optional; DefaultParameterValue(0)>] line: int) =
        Trace.WriteLine(sprintf "Message: %s" message)
        Trace.WriteLine(sprintf "Member name: %s" memberName)
        Trace.WriteLine(sprintf "Source file path: %s" path)
        Trace.WriteLine(sprintf "Source line number: %d" line)
```

## <a name="remarks"></a>Hinweise

Attribute "callerinfo" können nur auf optionale Parameter angewendet werden. Der Aufrufer-Informationsattribute dazu führen, dass den Compiler den richtigen Wert für jeden optionalen Parameter, die mit einem Aufrufer-Informationsattribute-Attribut versehen zu schreiben.

Aufrufer-Informationswerte werden zur Kompilierzeit als Literale in Intermediate Language (IL) ausgegeben. Im Gegensatz zu die Ergebnisse der [StackTrace](/dotnet/api/system.diagnostics.stacktrace) -Eigenschaft für Ausnahmen, die Ergebnisse nicht durch verbergen beeinflusst.

Sie können die optionalen Argumente explizit angeben, um die Aufruferinformationen zu steuern oder auszublenden.

## <a name="member-names"></a>Membernamen

Können Sie die [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) Attribut, um zu vermeiden, den Namen des Members als Angabe einer `String` Argument an die aufgerufene Methode. Mit diesem Verfahren, umgehen Sie das Problem, die Umgestaltung mit Umbenennung ändern nicht die `String` Werte. Dieser Vorteil ist für die folgenden Aufgaben besonders hilfreich:

* Verwenden der Ablaufverfolgung und der Diagnoseprogramme
* Implementieren der ["INotifyPropertyChanged"](/dotnet/api/system.componentmodel.inotifypropertychanged) -Schnittstelle beim Binden von Daten. Diese Schnittstelle ermöglicht es der Eigenschaft eines Objekts, ein gebundenes Steuerelement über die Änderung der Eigenschaft zu benachrichtigen, damit das Steuerelement die aktualisierten Informationen anzeigen kann. Ohne die [ `CallerMemberName` ](/dotnet/api/system.runtime.compilerservices.callermembernameattribute) -Attribut, müssen Sie den Eigenschaftennamen als Literal angeben.

Im folgende Diagramm sind die Membernamen aufgeführt, die zurückgegeben werden, wenn Sie das CallerMemberName-Attribut verwenden.

|Aufrufe erfolgen in|Ergebnis des Membernamens|
|-------------------|------------------|
|Methode, Eigenschaft oder Ereignis|Der Name der Methode, der Eigenschaft oder des Ereignisses, aus dem bzw. aus der der Aufruf stammt.|
|Konstruktor|Die Zeichenfolge ".ctor"|
|Statischer Konstruktor|Die Zeichenfolge ".cctor"|
|Destruktor|Die Zeichenfolge "Finalize"|
|Benutzerdefinierte Operatoren oder Konvertierungen|Der generierte Name für den Member, beispielsweise "op_Addition".|
|Attributkonstruktor|Der Name des Members, auf den das Attribut angewendet wird. Wenn das Attribut ein beliebiges Element in einem Member ist (z. B. ein Parameter, ein Rückgabewert oder ein generischer Typparameter), wird als Ergebnis der Name des Members ausgegeben, der diesem Element zugeordnet ist.|
|Kein enthaltender Member (z. B. auf Assemblyebene oder Attribute, die auf Typen angewendet werden)|Der Standardwert des optionalen Parameters.|

## <a name="see-also"></a>Siehe auch

- [Attribute](attributes.md)
- [Benannte Argumente](parameters-and-arguments.md#named-arguments)
- [Optionale Parameter](parameters-and-arguments.md#optional-parameters)
