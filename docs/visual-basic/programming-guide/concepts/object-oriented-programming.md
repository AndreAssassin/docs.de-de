---
title: Objektorientierte Programmierung (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 49794de4-64c3-473c-b8ed-fe98835df69c
ms.openlocfilehash: 058d8b932e50f784d4a5cefa9fadfb31953687f0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783512"
---
# <a name="object-oriented-programming-visual-basic"></a>Objektorientierte Programmierung (Visual Basic)

Visual Basic bietet vollständige Unterstützung für objektorientierte Programmierung einschließlich Kapselung, Vererbung und Polymorphie.

 *Kapselung* bedeutet, dass eine Gruppe verwandter Eigenschaften, Methoden sowie anderer Member als eine Einheit bzw. ein Objekt behandelt wird.

 *Vererbung* beschreibt die Fähigkeit, neue Klassen basierend auf einer vorhandenen Klasse zu erstellen.

 *Polymorphismus* bedeutet, dass Sie mehrere Klassen untereinander austauschen können, obwohl jede Klasse dieselben Eigenschaften oder Methoden auf unterschiedliche Art und Weise implementiert.

 In diesem Abschnitt werden die folgenden Konzepte beschrieben:

- [Klassen und Objekte](#classes-and-objects)
  - [Class members (Klassenmember)](#class-members)
    - [Eigenschaften und Felder](#properties-and-fields)
    - [Methoden](#methods)
    - [Konstruktoren](#constructors)
    - [Destruktoren](#destructors)
    - [Ereignisse](#events)
    - [Geschachtelte Klassen](#nested-classes)
  - [Zugriffsmodifizierer und Zugriffsebenen](#access-modifiers-and-access-levels)
    - [Instanziieren von Klassen](#instantiating-classes)
    - [Gemeinsam verwendete Klassen und Member](#shared-classes-and-members)
    - [Anonyme Typen](#anonymous-types)
- [Vererbung](#inheritance)
  - [Überschreiben von Membern](#overriding-members)
- [Schnittstellen](#interfaces)
- [Generika](#generics)
- [Delegaten](#delegates)

## <a name="classes-and-objects"></a>Klassen und Objekte

Die Begriffe *Klasse* und *Objekt* werden manchmal synonym verwendet; genau genommen beschreiben Klassen jedoch den *Typ* von Objekten, während Objekte verwendbare *Instanzen* von Klassen sind. Das Erstellen eines Objekts wird daher als *Instanziierung* bezeichnet. Um auf den Vergleich mit Bauplänen zurückzukommen: Eine Klasse ist ein Bauplan, und ein Objekt ist ein anhand dieses Bauplans errichtetes Gebäude.

So definieren Sie eine Klasse

```vb
Class SampleClass
End Class
```

Visual Basic bietet auch eine light-Version von Klassen *Strukturen* , sind nützlich, wenn müssen Sie ein großes Objektarray erstellen und möchten nicht zu viel Arbeitsspeicher belegen.

So definieren Sie eine Struktur

```vb
Structure SampleStructure
End Structure
```

Weitere Informationen finden Sie unter:

- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)
- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)

### <a name="class-members"></a>Klassenmember

Jede Klasse kann über andere *Klassenmember* verfügen. Diese enthalten Eigenschaften, die Klassendaten beschreiben, Methoden, die Klassenverhalten definieren sowie Ereignisse, die die Kommunikation zwischen verschiedenen Klassen und Objekten bereitstellen.

#### <a name="properties-and-fields"></a>Eigenschaften und Felder

Felder und Eigenschaften stellen die in einem Objekt enthaltenen Informationen dar. Felder sind wie Variablen, sie können direkt gelesen oder festgelegt werden.

So definieren Sie ein Feld

```vb
Class SampleClass
    Public SampleField As String
End Class
```

Eigenschaften verfügen über Get- und Set-Prozeduren, die eine bessere Kontrolle über das Festlegen oder Abrufen von Werten ermöglichen.

Visual Basic können Sie entweder ein privates Feld zum Speichern von den Wert der Eigenschaft erstellen, oder verwenden Sie die so genannte automatisch implementierte Eigenschaften, die dieses Feld automatisch im Hintergrund erstellen und die grundlegende Logik für die Eigenschaftenprozeduren bereitstellen.

So definieren Sie eine automatisch implementierte Eigenschaft

```vb
Class SampleClass
    Public Property SampleProperty as String
End Class
```

Verwenden Sie den folgenden Code, wenn Sie zusätzliche Lese- und Schreibvorgänge für den Eigenschaftswert ausführen müssen, um ein Feld zum Speichern des Eigenschaftswerts zu definieren und die grundlegende Logik zum Speichern und Abrufen bereitzustellen:

```vb
Class SampleClass
    Private m_Sample As String
    Public Property Sample() As String
        Get
            ' Return the value stored in the field.
            Return m_Sample
        End Get
        Set(ByVal Value As String)
            ' Store the value in the field.
            m_Sample = Value
        End Set
    End Property
End Class
```

Die meisten Eigenschaften verfügen über Methoden oder Prozeduren zum Festlegen und Abrufen des Eigenschaftswerts. Sie können jedoch schreib- oder lesegeschützte Eigenschaften erstellen, um zu verhindern, dass die Eigenschaften gelesen oder geändert werden. In Visual Basic können Sie das `ReadOnly`-Schlüsselwort und das `WriteOnly`-Schlüsselwort verwenden. Automatisch implementierte Eigenschaften können jedoch nicht schreib- oder lesegeschützt sein.

Weitere Informationen finden Sie unter:

- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
- [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)
- [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)

#### <a name="methods"></a>Methoden

 Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann.

> [!NOTE]
> In Visual Basic gibt es zwei Möglichkeiten, eine Methode zu erstellen: Wenn die Methode keinen Wert zurückgibt, wird die `Sub`-Anweisung verwendet; andernfalls wird die `Function`-Anweisung verwendet.

So definieren Sie eine Methode einer Klasse:

```vb
Class SampleClass
    Public Function SampleFunc(ByVal SampleParam As String)
        ' Add code here
    End Function
End Class
```

Eine Klasse kann über mehrere Implementierungen oder *Überladungen* der gleichen Methode verfügen, die sich in der Anzahl der Parameter oder Parametertypen unterscheiden.

So überladen Sie eine Methode

```vb
Overloads Sub Display(ByVal theChar As Char)
    ' Add code that displays Char data.
End Sub
Overloads Sub Display(ByVal theInteger As Integer)
    ' Add code that displays Integer data.
End Sub
```

In den meisten Fällen deklarieren Sie eine Methode innerhalb einer Klassendefinition. Visual Basic unterstützt jedoch auch *Erweiterungsmethoden* , mit denen Sie einer vorhandenen Klasse außerhalb der Klasse der eigentlichen Klassendefinition Methoden hinzuzufügen.

Weitere Informationen finden Sie unter:

- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)
- [Erweiterungsmethoden](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)

#### <a name="constructors"></a>Konstruktoren

Konstruktoren sind Klassenmethoden, die automatisch ausgeführt werden, wenn ein Objekt eines bestimmten Typs erstellt wird. Konstruktoren initialisieren normalerweise die Datenmember des neuen Objekts. Konstruktoren können nur einmal während der Erstellung der Klasse ausgeführt werden. Weiterhin wird der Code im Konstruktor immer vor jedem anderen Code in einer Klasse ausgeführt. Sie können jedoch mehrere Konstruktorüberladungen auf die gleiche Weise wie für jede andere Methode erstellen.

So definieren Sie einen Konstruktor für eine Klasse:

```vb
Class SampleClass
    Sub New(ByVal s As String)
        // Add code here.
    End Sub
End Class
```

Weitere Informationen finden Sie unter: [Objektlebensdauer: Wie die Objekte erstellt und zerstört werden](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md).

#### <a name="destructors"></a>Destruktoren

Destruktoren werden zur Zerstörung von Klasseninstanzen verwendet. In .NET Framework verwaltet die Garbage Collection die Speicherbelegung automatisch und gibt Arbeitsspeicher für die verwalteten Objekte in der Anwendung frei. Möglicherweise sind jedoch noch Destruktoren erforderlich, um alle nicht verwalteten Ressourcen zu bereinigen, die von der Anwendung erstellt werden. Es kann nur einen Destruktor für eine Klasse geben.

Weitere Informationen zu Destruktoren und der Garbage Collection in .NET Framework finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).

#### <a name="events"></a>Ereignisse

Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln. Die Klasse, die das Ereignis sendet (oder auslöst), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder verarbeiten), werden als *Abonnenten* bezeichnet. Weitere Informationen zu Ereignissen sowie zu ihrer Auslösung und Behandlung finden Sie unter [Ereignisse](../../../standard/events/index.md).

- Um Ereignisse zu deklarieren, verwenden die [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md).

- Um Ereignisse auszulösen, verwenden Sie die [RaiseEvent-Anweisung](../../../visual-basic/language-reference/statements/raiseevent-statement.md).

- Um Ereignishandler per Deklaration festzulegen, verwenden Sie die [WithEvents](../../../visual-basic/language-reference/modifiers/withevents.md) Anweisung und die [behandelt](../../../visual-basic/language-reference/statements/handles-clause.md) Klausel.

- Damit können dynamisch hinzufügen, entfernen und ändern den Ereignishandler einem Ereignis zugeordneten, verwenden die [AddHandler-Anweisung](../../../visual-basic/language-reference/statements/addhandler-statement.md) und [RemoveHandler-Anweisung](../../../visual-basic/language-reference/statements/removehandler-statement.md) zusammen mit den [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md).

#### <a name="nested-classes"></a>Geschachtelte Klassen

Eine Klasse, die in einer anderen Klasse definiert wird, wird als *geschachtelt* bezeichnet. Standardmäßig ist die geschachtelte Klasse privat.

```vb
Class Container
    Class Nested
    ' Add code here.
    End Class
End Class
```

Um eine Instanz der geschachtelten Klasse zu erstellen, verwenden Sie den Namen der Containerklasse und geben einen Punkt sowie anschließend den Namen der geschachtelten Klasse ein:

```vb
Dim nestedInstance As Container.Nested = New Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a>Zugriffsmodifizierer und Zugriffsebenen

Alle Klassen und Klassenmember können mit *Zugriffsmodifizierern* angeben, welche Zugriffsebene sie für andere Klassen bereitstellen.

Die folgenden Zugriffsmodifizierer sind verfügbar:

|Visual Basic-Modifizierer|Definition|
|---------------------------|----------------|
|[Public](../../../visual-basic/language-reference/modifiers/public.md)|Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.|
|[Private](../../../visual-basic/language-reference/modifiers/private.md)|Auf den Typ oder Member kann nur von Code in der gleichen Klasse zugegriffen werden.|
|[Protected](../../../visual-basic/language-reference/modifiers/protected.md)|Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder in einer abgeleiteten Klasse zugegriffen werden.|
|[Friend](../../../visual-basic/language-reference/modifiers/friend.md)|Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.|
|`Protected Friend`|Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.|

Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

### <a name="instantiating-classes"></a>Instanziieren von Klassen

Um ein Objekt zu erstellen, müssen Sie eine Klasse instanziieren oder eine Klasseninstanz erstellen.

```vb
Dim sampleObject as New SampleClass()
```

Nachdem Sie eine Klasse instanziiert haben, können Sie den Eigenschaften und Feldern der Instanz Werte zuweisen und Klassenmethoden aufrufen.

```vb
' Set a property value.
sampleObject.SampleProperty = "Sample String"
' Call a method.
sampleObject.SampleMethod()
```

Verwenden Sie Objektinitialisierer, um Eigenschaften im Rahmen des Klasseninstanziierungsprozesses Werte zuzuweisen:

```vb
Dim sampleObject = New SampleClass With
    {.FirstProperty = "A", .SecondProperty = "B"}
```

Weitere Informationen finden Sie unter:

- [New-Operator](../../../visual-basic/language-reference/operators/new-operator.md)
- [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)

### <a name="shared-classes-and-members"></a>Gemeinsam verwendete Klassen und Member

 Ein freigegebener Member der Klasse ist eine Eigenschaft, Prozedur oder Feld, das von allen Instanzen einer Klasse gemeinsam verwendet wird.

 So definieren Sie einen freigegebenen Member:

```vb
Class SampleClass
    Public Shared SampleString As String = "Sample String"
End Class
```

 Verwenden Sie den Namen der Klasse für den Zugriff auf den freigegebenen Member, ohne ein Objekt dieser Klasse zu erstellen:

```vb
MsgBox(SampleClass.SampleString)
```

 Freigegebene Module in Visual Basic nur Member freigegeben haben, und können nicht instanziiert werden. Freigegebene Member können nicht auch nicht freigegebene Eigenschaften, Felder oder Methoden zugreifen.

 Weitere Informationen finden Sie unter:

- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)

### <a name="anonymous-types"></a>Anonyme Typen

Mit anonymen Typen können Objekte erstellt werden, ohne eine Klassendefinition für den Datentyp zu schreiben. Stattdessen erzeugt der Compiler eine Klasse. Die Klasse hat keinen verwendbaren Namen und enthält die von Ihnen in der Deklaration des Objekts angegebenen Eigenschaften.

So erstellen Sie eine Instanz eines anonymen Typs

```vb
' sampleObject is an instance of a simple anonymous type.
Dim sampleObject =
    New With {Key .FirstProperty = "A", .SecondProperty = "B"}
```

Weitere Informationen finden Sie unter: [Anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).

## <a name="inheritance"></a>Vererbung

Vererbung ermöglicht die Erstellung neuer Klassen, die in anderen Klassen definiertes Verhalten wieder verwenden, erweitern und ändern. Die Klasse, deren Member vererbt werden, wird *Basisklasse* genannt, und die Klasse, die diese Member erbt, wird *abgeleitete Klasse* genannt. Alle Klassen in Visual Basic erben jedoch implizit von der <xref:System.Object> -Klasse, die .NET-Klassenhierarchie unterstützt und Low-Level-Dienste für alle Klassen bereitstellt.

> [!NOTE]
> Visual Basic unterstützt keine mehrfachvererbung. Sie können also nur eine Basisklasse für eine abgeleitete Klasse angeben.

So erben Sie von einer Basisklasse

```vb
Class DerivedClass
    Inherits BaseClass
End Class
```

Standardmäßig können alle Klassen geerbt werden. Sie können jedoch angeben, dass eine Klasse nicht als Basisklasse verwendet werden darf, oder eine Klasse erstellen, die nur als Basisklasse verwendet werden kann.

So geben Sie an, dass eine Klasse nicht als Basisklasse verwendet werden kann

```vb
NotInheritable Class SampleClass
End Class
```

So geben Sie an, dass eine Klasse nur als Basisklasse verwendet und nicht instanziiert werden kann:

```vb
MustInherit Class BaseClass
End Class
```

Weitere Informationen finden Sie unter:

- [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)
- [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)

### <a name="overriding-members"></a>Überschreiben von Membern

Standardmäßig erbt eine abgeleitete Klasse alle Member von ihrer Basisklasse. Wenn Sie das Verhalten des geerbten Members ändern möchten, müssen Sie diesen überschreiben. Das heißt, Sie können eine neue Implementierung der Methode, der Eigenschaft oder des Ereignisses in der abgeleiteten Klasse definieren.

Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:

|Visual Basic-Modifizierer|Definition|
|---------------------------|----------------|
|[Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)|Ermöglicht das Überschreiben eines Klassenmembers in einer abgeleiteten Klasse.|
|[Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)|Überschreibt einen virtuellen (überschreibbaren) Member, der in der Basisklasse definiert wurde.|
|[NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)|Verhindert das Überschreiben eines Members in einer erbenden Klasse.|
|[MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)|Erfordert das Überschreiben eines Klassenmembers in der abgeleiteten Klasse.|
|[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)|Blendet einen von einer Basisklasse geerbten Member aus.|

## <a name="interfaces"></a>Schnittstellen

Schnittstellen definieren (wie Klassen) einen Satz von Eigenschaften, Methoden und Ereignissen. Im Gegensatz zu Klassen jedoch bieten Schnittstellen keine Implementierung. Sie werden durch Klassen implementiert und als von Klassen unabhängige Entitäten definiert. Eine Schnittstelle stellt insofern einen Vertrag dar, dass eine Klasse, die eine Schnittstelle implementiert, jeden Aspekt dieser Schnittstelle gemäß seiner Definition implementieren muss.

So definieren Sie eine Schnittstelle

```vb
Public Interface ISampleInterface
    Sub DoSomething()
End Interface
```

So implementieren Sie eine Schnittstelle in einer Klasse

```vb
Class SampleClass
    Implements ISampleInterface
    Sub DoSomething
        ' Method implementation.
    End Sub
End Class
```

Weitere Informationen finden Sie unter:

- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)

## <a name="generics"></a>Generics

Klassen, Strukturen, Schnittstellen und Methoden in .NET zählen *Typparameter* , definieren die Typen von Objekten, die sie speichern oder verwenden können. Das einfachste Beispiel für Generics ist eine Auflistung, in der Sie den Typ von Objekten angeben können, die in einer Auflistung gespeichert werden sollen.

So definieren Sie eine generische Klasse

```vb
Class SampleGeneric(Of T)
    Public Field As T
End Class
```

So erstellen Sie eine Instanz einer generischen Klasse

```vb
Dim sampleObject As New SampleGeneric(Of String)
sampleObject.Field = "Sample string"
```

Weitere Informationen finden Sie unter:

- [Generika](../../../standard/generics/index.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)

## <a name="delegates"></a>Delegaten

 Ein *Delegat* ist ein Typ, der eine Methodensignatur definiert. Er kann einen Verweis auf jede Methode bereitstellen, die über eine kompatible Signatur verfügt. Sie können die Methode über den Delegaten aufrufen. Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.

> [!NOTE]
> Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden. Weitere Informationen zur Ereignisbehandlung mit Delegaten finden Sie unter [Ereignisse](../../../standard/events/index.md).

So erstellen Sie einen Delegaten

```vb
Delegate Sub SampleDelegate(ByVal str As String)
```

So erstellen Sie einen Verweis auf eine Methode, die der vom Delegaten angegebenen Signatur entspricht:

```vb
Class SampleClass
    ' Method that matches the SampleDelegate signature.
    Sub SampleSub(ByVal str As String)
        ' Add code here.
    End Sub
    ' Method that instantiates the delegate.
    Sub SampleDelegateSub()
        Dim sd As SampleDelegate = AddressOf SampleSub
        sd("Sample string")
    End Sub
End Class
```

Weitere Informationen finden Sie unter:

- [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Delegate-Anweisung](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)

## <a name="see-also"></a>Siehe auch

- [Visual Basic-Programmierhandbuch](../../../visual-basic/programming-guide/index.md)
