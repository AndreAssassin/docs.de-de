---
title: Allgemeine Attribute (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
ms.openlocfilehash: e001c9a637d2e5e34e77158704e4ad81d6973a50
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58834539"
---
# <a name="common-attributes-visual-basic"></a>Allgemeine Attribute (Visual Basic)
Dieses Thema beschreibt die Attribute, die am häufigsten in Visual Basic-Programmen verwendet werden.  
  
-   [Globale Attribute](#Global)  
  
-   [Obsolete-Attribut](#Obsolete)  
  
-   [Conditional-Attribut](#Conditional)  
  
-   [Aufufrerinfoattribute](#CallerInfo)  
  
-   [Visual Basic-Attribute](#VB)  
  
## <a name="Global"></a> Globale Attribute  
 Die meisten Attribute werden auf spezifische Sprachelemente wie Klassen oder Methoden angewendet. Einige Attribute sind jedoch global – sie gelten für eine gesamte Assembly oder ein Modul. Zum Beispiel kann das <xref:System.Reflection.AssemblyVersionAttribute>-Attribut zum Einbetten von Versionsinformationen in eine Assembly verwendet werden. Diese sieht wie folgt aus:  
  
```vb  
<Assembly: AssemblyVersion("1.0.0.0")>  
```  
  
 Globale Attribute befinden sich im Quellcode nach allen auf oberster Ebene `Imports` Anweisungen und vor jeglichen Deklarationen Typ-, Modul- oder -Namespace. Globale Attribute können in mehreren Quelldateien auftreten, jedoch müssen die Dateien in einem einzigen Kompilierungsdurchlauf kompiliert werden. Für Visual Basic-Projekten werden globale Attribute in der Regel in der AssemblyInfo.vb-Datei abgelegt (die Datei wird automatisch erstellt, wenn Sie ein Projekt in Visual Studio erstellen).  
  
 Assemblyattribute sind Werte, die Informationen zu einer Assembly bereitstellen. Sie werden in die folgenden Kategorien eingeteilt:  
  
-   Attribute für Assemblyidentitäten  
  
-   Informationsattribute  
  
-   Attribute für Assemblymanifeste.  
  
### <a name="assembly-identity-attributes"></a>Attribute für Assemblyidentitäten  
 Drei Attribute bestimmen mit einem starken Namen (falls zutreffend) die Identität einer Assembly: „name“, „version“ und „culture“. Diese Attribute bilden den vollständigen Namen der Assembly und sind erforderlich, wenn im Code auf sie verwiesen wird. Mit Attributen können die Version und Kultur einer Assembly festgelegt werden. Allerdings wird der name-Wert vom Compiler, der Visual Studio-IDE im [Dialogfeld „Assemblyinformationen“](/visualstudio/ide/reference/assembly-information-dialog-box) oder dem Assemblylinker (Al.exe) festgelegt, wenn die Assembly erstellt wird. Die geschieht auf Grundlage der Datei, die das Assemblymanifest enthält. Das Attribut <xref:System.Reflection.AssemblyFlagsAttribute> gibt an, ob mehrere Kopien der Assembly parallel bestehen können.  
  
 In der folgenden Tabelle werden die Identitätsattribute aufgeführt.  
  
|Attribut|Zweck|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName>|Beschreibt vollständig die Identität einer Assembly|  
|<xref:System.Reflection.AssemblyVersionAttribute>|Gibt die Version einer Assembly an|  
|<xref:System.Reflection.AssemblyCultureAttribute>|Gibt an, welche Kultur die Assembly unterstützt.|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|Gibt an, ob eine Assembly die parallele Ausführung auf demselben Computer, im selben Prozess oder in derselben Anwendungsdomäne unterstützt|  
  
### <a name="informational-attributes"></a>Informationsattribute  
 Mit Informationsattributen können Sie zusätzliche Firmen- oder Produktinformationen für eine Assembly bereitstellen. Die folgende Tabelle zeigt die Informationsattribute, die im Namespace <xref:System.Reflection?displayProperty=nameWithType> definiert werden.  
  
|Attribut|Zweck|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute>|Definiert ein benutzerdefiniertes Attribut, das den Produktnamen für ein Assemblymanifest angibt|  
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Marke für ein Assemblymanifest angibt|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Informationsversion für ein Assemblymanifest angibt|  
|<xref:System.Reflection.AssemblyCompanyAttribute>|Definiert ein benutzerdefiniertes Attribut, das einen Firmennamen für ein Assemblymanifest angibt|  
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Definiert ein benutzerdefiniertes Attribut, das ein Copyright für ein Assemblymanifest angibt|  
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Weist den Compiler an, eine spezifische Versionsnummer für die Win32-Dateiversionsressource zu verwenden|  
|<xref:System.CLSCompliantAttribute>|Gibt an, ob die Assembly mit der Common Language Specification (CLS) kompatibel ist|  
  
### <a name="assembly-manifest-attributes"></a>Attribute für Assemblymanifeste  
 Sie können Attribute für Assemblymanifeste verwenden, um Informationen im Assemblymanifest bereitzustellen. Dies schließt Titel, Beschreibung, Standardalias und Konfiguration ein. Die folgende Tabelle zeigt die Attribute für Assemblymanifeste, die im Namespace <xref:System.Reflection?displayProperty=nameWithType> definiert werden.  
  
|Attribut|Zweck|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute>|Definiert ein benutzerdefiniertes Attribut, das einen Assemblytitel für ein Assemblymanifest angibt|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Assemblybeschreibung für ein Assemblymanifest angibt|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Definiert ein benutzerdefiniertes Attribut, das eine Assemblykonfiguration (z.B. Retail oder Debug) für ein Assemblymanifest angibt|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Definiert einen benutzerfreundlichen Standardalias für ein Assemblymanifest|  
  
## <a name="Obsolete"></a> Obsolete-Attribut  
 Das `Obsolete`-Attribut markiert eine Programmentität als eine, die nicht mehr zur Verwendung empfohlen wird. Jede Verwendung einer Entität, die als veraltet markiert ist, generiert anschließend eine Warnung oder einen Fehler, je nachdem, wie das Attribut konfiguriert ist. Zum Beispiel:  
  
```vb  
<System.Obsolete("use class B")>   
Class A  
    Sub Method()  
    End Sub  
End Class  
  
Class B  
    <System.Obsolete("use NewMethod", True)>   
    Sub OldMethod()  
    End Sub  
  
    Sub NewMethod()  
    End Sub  
End Class  
```  
  
 Dieses Beispiel zeigt, wie das `Obsolete`-Attribut auf die `A`-Klasse und die `B.OldMethod`-Methode angewendet wird. Da das zweite Argument des Attributkonstruktors, das auf `B.OldMethod` angewendet wurde, auf `true` festgelegt wird, verursacht diese Methode einen Compilerfehler. Die Verwendung der `A`-Klasse erzeugt hingegen nur eine Warnung. Wenn Sie `B.NewMethod` aufrufen, werden weder Warnungen noch Fehler erzeugt.  
  
 Die Zeichenfolge, die als erstes Argument für den Attributkonstruktor bereitgestellt wurde, wird als Teil der Warnung oder des Fehlers angezeigt. Wenn Sie es mit den vorherigen Definitionen verwenden, generiert der folgende Code zwei Warnungen und einen Fehler:  
  
```vb  
' Generates 2 warnings:  
' Dim a As New A  
' Generate no errors or warnings:  
  
Dim b As New B  
b.NewMethod()  
  
' Generates an error, terminating compilation:  
' b.OldMethod()  
```  
  
 Es werden zwei Warnungen für die Klasse `A` generiert: eine für die Deklaration des Klassenverweises und eine für den Klassenkonstruktor.  
  
 Das `Obsolete`-Attribut kann ohne Argumente verwendet werden, jedoch ist das Einschließen einer Erklärung, warum das Element veraltet ist und was demnach verwendet werden soll, empfohlen.  
  
 Das `Obsolete`-Attribut ist ein Attribut zur einmaligen Nutzung und kann auf jede Entität angewendet werden, die Attribute zulässt. `Obsolete` ist ein Alias für <xref:System.ObsoleteAttribute>.  
  
## <a name="Conditional"></a> Conditional-Attribut  
 Das `Conditional`-Attribut macht die Ausführung einer Methode abhängig von einem Vorverarbeitungsbezeichner. Das `Conditional`-Attribut ist ein Alias für <xref:System.Diagnostics.ConditionalAttribute> und kann auf eine Methode oder Attributklasse angewendet werden.  
  
 In diesem Beispiel wird `Conditional` auf eine Methode angewendet, um die Anzeige programmspezifischer Diagnoseinformationen zu aktivieren oder zu deaktivieren.  
  
```vb  
#Const TRACE_ON = True  
Imports System  
Imports System.Diagnostics  
Module TestConditionalAttribute  
    Public Class Trace  
        <Conditional("TRACE_ON")>   
        Public Shared Sub Msg(ByVal msg As String)  
            Console.WriteLine(msg)  
        End Sub  
  
    End Class  
  
    Sub Main()  
        Trace.Msg("Now in Main...")  
        Console.WriteLine("Done.")  
    End Sub  
End Module  
```  
  
 Wenn der `TRACE_ON`-Bezeichner nicht definiert ist, wird keine Ablaufverfolgungsausgabe angezeigt.  
  
 Das `Conditional`-Attribut wird oft zusammen mit dem `DEBUG`-Bezeichner verwendet, um die Ablaufverfolgung und Protokollierung von Features zum Debuggen von Builds, jedoch nicht in Releasebuilds, wie folgt zu aktivieren:  
  
```vb  
<Conditional("DEBUG")>   
Shared Sub DebugMethod()  
  
End Sub  
```  
  
 Wenn eine als bedingt gekennzeichnete Methode aufgerufen wird, bestimmt das Vorhandensein oder Fehlen des angegebenen Vorverarbeitungssymbols, ob der Aufruf eingeschlossen oder ausgelassen wird. Wenn das Symbol definiert ist, wird der Aufruf einbezogen; andernfalls wird der Aufruf ausgelassen. Die Verwendung von `Conditional` ist eine sauberere, elegantere und auch weniger fehleranfällige Alternative zum Einschließen von Methoden innerhalb von `#if…#endif`-Blöcken, z.B.:  
  
```vb  
#If DEBUG Then  
    Sub ConditionalMethod()  
    End Sub  
#End If  
```  
  
 Eine bedingte Methode muss eine Methode in einer Klassen- oder Stukturdeklaration sein und darf keinen Rückgabewert besitzen.  
  
### <a name="using-multiple-identifiers"></a>Verwenden mehrerer Bezeichner  
 Wenn eine Methode mehrere `Conditional`-Attribute besitzt, wird ein Aufruf an die Methode eingeschlossen, wenn mindestens eines der bedingten Symbole definiert ist (anders gesagt, sind die Symbole durch Verwendung des OR-Operators logisch miteinander verknüpft). In diesem Beispiel führt das Vorhandensein von `A` oder `B` zu einem Methodenaufruf:  
  
```vb  
<Conditional("A"), Conditional("B")>   
Shared Sub DoIfAorB()  
  
End Sub  
```  
  
 Um den Effekt der logischen Verknüpfung von Symbolen durch den AND-Operator zu erzielen, können Sie serielle bedingte Methoden definieren. Zum Beispiel wird die zweite Methode unten nur ausgeführt, wenn jeweils `A` und `B` definiert sind:  
  
```vb  
<Conditional("A")>   
Shared Sub DoIfA()  
    DoIfAandB()  
End Sub  
  
<Conditional("B")>   
Shared Sub DoIfAandB()  
    ' Code to execute when both A and B are defined...  
End Sub  
```  
  
### <a name="using-conditional-with-attribute-classes"></a>Verwenden von Conditional mit Attributklassen  
 Das `Conditional`-Attribut kann auch auf die Definition einer Attributklasse angewendet werden. In diesem Beispiel wird das benutzerdefinierte Attribut `Documentation` den Metadaten nur dann Informationen hinzufügen, wenn DEBUG definiert ist.  
  
```vb  
<Conditional("DEBUG")>   
Public Class Documentation  
    Inherits System.Attribute  
    Private text As String  
    Sub New(ByVal doc_text As String)  
        text = doc_text  
    End Sub  
End Class  
  
Class SampleClass  
    ' This attribute will only be included if DEBUG is defined.  
    <Documentation("This method displays an integer.")>   
    Shared Sub DoWork(ByVal i As Integer)  
        System.Console.WriteLine(i)  
    End Sub  
End Class  
```  
  
## <a name="CallerInfo"></a> Aufufrerinfoattribute  
 Mithilfe der Aufrufer-Informationsattribute können Sie Informationen zum Aufrufer einer Methode abrufen. Sie können den Dateipfad des Quellcodes, die Zeilennummer im Quellcode und den Membernamen des Aufrufers abrufen.  
  
 Um diese Memberaufruferinformationen zu erhalten, verwenden Sie die Attribute, die auf optionale Parameter angewendet werden. Jeder optionale Parameter gibt einen Standardwert an. In der folgenden Tabelle sind die Aufrufer-Informationsattribute angegeben, die im <xref:System.Runtime.CompilerServices?displayProperty=nameWithType>-Namespace definiert sind:  
  
|Attribut|Beschreibung|Typ|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|Vollständiger Pfad der Quelldatei, die den Aufrufer enthält. Dies ist der Pfad zum Zeitpunkt der Kompilierung.|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|Zeilennummer in der Quelldatei, in der die Methode aufgerufen wird|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|Der Methoden- oder Eigenschaftenname des Aufrufers Weitere Informationen finden Sie unter [Aufruferinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).|`String`|  
  
 Weitere Informationen zu den aufruferinformationsattributen finden Sie unter [Aufruferinformationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).  
  
## <a name="VB"></a> Visual Basic-Attribute  
 Die folgende Tabelle enthält die Attribute, die in Visual Basic spezifisch sind.  
  
|Attribut|Zweck|  
|---------------|-------------|  
|<xref:Microsoft.VisualBasic.ComClassAttribute>|Gibt der Compiler, dass die Klasse als COM-Objekt verfügbar gemacht werden soll.|  
|<xref:Microsoft.VisualBasic.HideModuleNameAttribute>|Ermöglicht die Modulmember zugegriffen werden nur die Zugriffsberechtigungen für das Modul benötigt.|  
|<xref:Microsoft.VisualBasic.VBFixedStringAttribute>|Gibt die Größe einer Zeichenfolge fester Länge in einer Struktur für die Verwendung mit ein- und Ausgabe-Datei an Funktionen.|  
|<xref:Microsoft.VisualBasic.VBFixedArrayAttribute>|Gibt die Größe der ein Array fester Größe in einer Struktur für die Verwendung mit ein- und Ausgabe-Datei an Funktionen.|  
  
### <a name="comclassattribute"></a>COMClassAttribute  
 Verwendung `COMClassAttribute` zum Vereinfachen der Erstellung von COM-Komponenten von Visual Basic. COM-Objekte unterscheiden sich erheblich von .NET Framework-Assemblys und ohne `COMClassAttribute`, müssen Sie eine Reihe von Schritten, um ein COM-Objekt in Visual Basic zu generieren. Für Klassen mit gekennzeichnet `COMClassAttribute`, der Compiler viele dieser Schritte automatisch durchführt.  
  
### <a name="hidemodulenameattribute"></a>HideModuleNameAttribute  
 Verwendung `HideModuleNameAttribute` können Modulmember zugegriffen werden kann, indem nur die Zugriffsberechtigungen für das Modul benötigt.  
  
### <a name="vbfixedstringattribute"></a>VBFixedStringAttribute  
 Verwendung `VBFixedStringAttribute` zu erzwingen, dass Visual Basic zum Erstellen einer Zeichenfolge fester Länge. Zeichenfolgen mit variabler Länge in der Standardeinstellung sind, und dieses Attribut ist nützlich, wenn Sie Zeichenfolgen in Dateien zu speichern. Der folgende Code veranschaulicht dies:  
  
```vb  
Structure Worker  
    ' The runtime uses VBFixedString to determine   
    ' if the field should be written out as a fixed size.  
    <VBFixedString(10)> Public LastName As String  
    <VBFixedString(7)> Public Title As String  
    <VBFixedString(2)> Public Rank As String  
End Structure  
```  
  
### <a name="vbfixedarrayattribute"></a>VBFixedArrayAttribute  
 Verwendung `VBFixedArrayAttribute` Arrays deklarieren, die eine feste Größe sind. Sind z. B. Visual Basic-Zeichenfolgen Arrays mit variabler Länge in der Standardeinstellung. Dieses Attribut ist nützlich, bei der Serialisierung oder Schreiben von Daten in Dateien.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection>
- <xref:System.Attribute>
- [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)
- [Attribute](../../../../standard/attributes/index.md)
- [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md) (Zugreifen auf Attribute mithilfe der Reflektion (Visual Basic))
