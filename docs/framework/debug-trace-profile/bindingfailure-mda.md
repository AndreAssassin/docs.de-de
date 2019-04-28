---
title: bindingFailure-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- binding failure
- binding, failures
- MDAs (managed debugging assistants), binding failures
- assemblies [.NET Framework], binding failures
- managed debugging assistants (MDAs), binding failures
- BindingFailure MDA
ms.assetid: 26ada5af-175c-4576-931a-9f07fa1723e9
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1e904d452b9f4a1b172d35984b752c0d97228338
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61875081"
---
# <a name="bindingfailure-mda"></a>bindingFailure-MDA

Der `bindingFailure`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn das Laden einer Assembly fehlschlägt.

## <a name="symptoms"></a>Symptome

Es wurde versucht, eine Assembly mithilfe eines statischen Verweises oder einer der Ladeprogrammmethoden wie <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> oder <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType> zu laden. Die Assembly wird nicht geladen, und es wird eine <xref:System.IO.FileNotFoundException>- bzw. <xref:System.IO.FileLoadException>-Ausnahme ausgelöst.

## <a name="cause"></a>Ursache

Ein Bindungsfehler tritt auf, wenn eine Assembly nicht durch die Common Language Runtime geladen werden kann. Ein Bindungsfehler kann das Ergebnis einer der folgenden Situationen sein:

- Die Common Language Runtime (CLR) kann die angeforderte Assembly nicht finden. Es gibt viele Ursachen dafür. Beispielsweise ist die Assembly nicht installiert, oder die Anwendung wurde nicht ordnungsgemäß zum Finden der Assembly konfiguriert.

- Häufig treten Probleme beim Übergeben eines Typs an eine andere Anwendungsdomäne auf. Dazu muss die CLR die Assembly mit diesem Typ in die andere Anwendungsdomäne laden. Wenn die andere Anwendungsdomäne anders konfiguriert ist als die ursprüngliche Anwendungsdomäne, kann die CLR die Assembly unter Umständen nicht laden. Zum Beispiel verfügen die beiden Anwendungsdomänen möglicherweise über unterschiedliche <xref:System.AppDomain.BaseDirectory%2A>-Eigenschaftswerte.

- Die angeforderte Assembly ist beschädigt, oder es handelt sich nicht um eine Assembly.

- Der Programmcode, der die Assembly zu laden versucht, verfügt nicht über die richtigen Sicherheitsberechtigungen für den Codezugriff zum Laden von Assemblys.

- Den Benutzeranmeldeinformationen sind nicht die erforderlichen Berechtigungen zum Lesen der Datei zugeordnet.

## <a name="resolution"></a>Auflösung

Der erste Schritt ist zu ermitteln, warum die CLR keine Bindung der angeforderten Assembly durchführen konnte. Es gibt viele Ursachen, warum die CLR die angeforderte Assembly nicht gefunden hat bzw. nicht laden konnte (siehe die im Abschnitt „Ursache“ aufgeführten Szenarios). Die folgenden Aktionen werden empfohlen, um die Ursache des Bindungsfehlers zu ermitteln:

- Bestimmen Sie die Ursache, indem Sie die vom `bindingFailure`-MDA bereitgestellten Daten auswerten:

  - Starten Sie [Fuslogvw.exe (Assembly Binding Log Viewer)](../../../docs/framework/tools/fuslogvw-exe-assembly-binding-log-viewer.md), um die bei der Assemblybindung erzeugten Fehlerprotokolle anzuzeigen.

  - Stellen Sie fest, ob sich die Assembly am angegebenen Speicherort befindet. Im Fall der <xref:System.Reflection.Assembly.LoadFrom%2A>- und <xref:System.Reflection.Assembly.LoadFile%2A>-Methoden kann der angeforderte Speicherort leicht ermittelt werden. Im Fall der <xref:System.Reflection.Assembly.Load%2A>-Methode, bei der die Bindung mithilfe der Assemblyidentität erfolgt, müssen Sie nach Assemblys mit dieser Identität in der Überprüfungspfadeigenschaft <xref:System.AppDomain.BaseDirectory%2A> der Anwendungsdomäne und im globalen Assemblycache suchen.

- Beheben Sie die Fehlerursache in Abhängigkeit vom Ergebnis der Ursachensuche. Mögliche Vorgehensweisen zum Lösen des Problems:

  - Installieren Sie die angeforderte Assembly im globalen Assemblycache, und rufen Sie die <xref:System.Reflection.Assembly.Load%2A>-Methode, um die Assembly nach Identität zu laden.

  - Kopieren Sie die angeforderte Assembly in das Anwendungsverzeichnis, und rufen Sie die <xref:System.Reflection.Assembly.Load%2A>-Methode auf, um die Assembly nach Identität zu laden.

  - Konfigurieren Sie die Anwendungsdomäne mit dem Bindungsfehler so um, dass sie den Pfad zur Assembly enthält. Ändern Sie dazu entweder die <xref:System.AppDomain.BaseDirectory%2A>-Eigenschaft, oder fügen Sie private Überprüfungspfade hinzu.

  - Ändern Sie die Zugriffssteuerungsliste der Datei, damit diese vom angemeldeten Benutzer gelesen werden kann.

## <a name="effect-on-the-runtime"></a>Auswirkungen auf die Laufzeit

Dieser MDA hat keine Auswirkungen auf die CLR. Es werden nur Daten über Bindungsfehler bereitgestellt.

## <a name="output"></a>Output

Der MDA meldet die Assembly, die nicht geladen wurde, den angeforderten Pfad und/oder den Anzeigenamen, den Bindungskontext, die Anwendungsdomäne für den angeforderten Ladevorgang und die Fehlerursache.

Die Angaben zu Anzeigename oder angefordertem Pfad sind möglicherweise leer, wenn diese Daten der CLR nicht zur Verfügung standen. Wenn der fehlgeschlagene Aufruf ein Aufruf der <xref:System.Reflection.Assembly.Load%2A>-Methode war, konnte die CLR wahrscheinlich den Anzeigenamen der Assembly nicht ermitteln.

## <a name="configuration"></a>Konfiguration

```xml
<mdaConfig>
  <assistants>
    <bindingFailure />
  </assistants>
</mdaConfig>
```

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird eine Situation veranschaulicht, die zum Aktivieren dieses MDA führen kann:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.Reflection;
namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            // This call attempts to load a nonexistent assembly.
            // The call will throw a System.IO.FileNotFound exception
            // and cause the activation of the bindingFailure MDA
            // if it is registered.
            Assembly.Load("NonExistentAssembly");
        }
    }
}
```

## <a name="see-also"></a>Siehe auch

- [Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
