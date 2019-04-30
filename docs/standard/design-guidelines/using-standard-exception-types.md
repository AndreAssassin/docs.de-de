---
title: Verwenden von Standardausnahmetypen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- throwing exceptions, standard types
- catching exceptions
- exceptions, catching
- exceptions, throwing
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
author: KrzysztofCwalina
ms.openlocfilehash: b947c7cce057c060b1ab5054d1227f5703ccbf89
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62026335"
---
# <a name="using-standard-exception-types"></a>Verwenden von Standardausnahmetypen
Dieser Abschnitt beschreibt die Standardausnahmen, die durch das Framework sowie Details zu ihrer Verwendung bereitgestellt. Die Liste ist keineswegs vollständig. Finden Sie in der .NET Framework-Referenzdokumentation für die Verwendung mit anderen Framework-Ausnahmetypen.  
  
## <a name="exception-and-systemexception"></a>Ausnahmen und SystemException  
 **X DO NOT** auslösen <xref:System.Exception?displayProperty=nameWithType> oder <xref:System.SystemException?displayProperty=nameWithType>.  
  
 **X DO NOT** catch `System.Exception` oder `System.SystemException` in Frameworkcode, es sei denn, Sie erneut auslösen möchten.  
  
 **X AVOID** abfangen `System.Exception` oder `System.SystemException`, außer bei Ausnahmehandler der obersten Ebene.  
  
## <a name="applicationexception"></a>ApplicationException  
 **X DO NOT** lösen oder eine Ableitung von <xref:System.ApplicationException>.  
  
## <a name="invalidoperationexception"></a>InvalidOperationException  
 **✓ DO** Auslösen einer <xref:System.InvalidOperationException> , wenn das Objekt in einem unzulässigen Zustand ist.  
  
## <a name="argumentexception-argumentnullexception-and-argumentoutofrangeexception"></a>ArgumentException "ArgumentNullException" und ArgumentOutOfRangeException  
 **✓ DO** auslösen <xref:System.ArgumentException> oder einem seiner Untertypen, wenn ungültige Argumente auf einen Member übergeben werden. Bevorzugen Sie am weitesten abgeleiteten Ausnahmetyp, falls zutreffend.  
  
 **✓ DO** legen Sie die `ParamName` Eigenschaft, die beim Auslösen einer die Unterklasse von `ArgumentException`.  
  
 Diese Eigenschaft stellt den Namen des Parameters, der die Ausnahme ausgelöst hat. Beachten Sie, dass die Eigenschaft mit einer der überladenen Konstruktor festgelegt werden kann.  
  
 **✓ DO** verwenden `value` für den Namen des Parameters impliziter Wert der Eigenschaftensetter.  
  
## <a name="nullreferenceexception-indexoutofrangeexception-and-accessviolationexception"></a>"NullReferenceException" IndexOutOfRangeException und AccessViolationException  
 **X DO NOT** ermöglichen öffentlich aufrufbare APIs explizit oder implizit auslöst <xref:System.NullReferenceException>, <xref:System.AccessViolationException>, oder <xref:System.IndexOutOfRangeException>. Diese Ausnahmen sind reserviert und wird von der ausführungs-Engine ausgelöst und in den meisten Fällen einen Fehler hinweisen.  
  
 Führen Sie Argument überprüfen, um zu vermeiden, diese Ausnahmen auslösen. Diese Ausnahmen auslösen, stellt Details zur Implementierung der Methode, die sich im Laufe der Zeit ändern kann.  
  
## <a name="stackoverflowexception"></a>StackOverflowException  
 **X DO NOT** explizit auslösen <xref:System.StackOverflowException>. Die Ausnahme sollte nur von der CLR explizit ausgelöst werden.  
  
 **X DO NOT** catch `StackOverflowException`.  
  
 Es ist nahezu unmöglich, verwalteten Code schreiben, der bei beliebigen Stapelüberläufe konsistent bleibt. Mithilfe von Tests um zu verschieben, dass klar definierte stellen Stapelüberläufe anstatt aus beliebigen Stapelüberläufe zurückziehen, wird von die nicht verwalteten Teilen der CLR konsistent bleiben.  
  
## <a name="outofmemoryexception"></a>OutOfMemoryException  
 **X DO NOT** explizit auslösen <xref:System.OutOfMemoryException>. Diese Ausnahme wird nur von der CLR-Infrastruktur ausgelöst wird.  
  
## <a name="comexception-sehexception-and-executionengineexception"></a>ComException, ExecutionEngineException und SEHException-Ausnahme  
 **X DO NOT** explizit auslösen <xref:System.Runtime.InteropServices.COMException>, <xref:System.ExecutionEngineException>, und <xref:System.Runtime.InteropServices.SEHException>. Diese Ausnahmen werden nur von der CLR-Infrastruktur ausgelöst wird.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)
