---
title: F#Styleguide
description: Erfahren Sie, die fünf Prinzipien guten F# Code.
ms.date: 12/10/2018
ms.openlocfilehash: 9f47257626e04b09b546de2ae315d48d791678be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61901848"
---
# <a name="f-style-guide"></a>F#Styleguide

Die folgenden Artikel beschreiben der Richtlinien für die Formatierung F# Code und die aktuellen Anleitungen für die Funktionen der Sprache und wie sie verwendet werden soll.

Dieser Leitfaden wurde basierend auf formuliert wurde die Verwendung von F# in großen Codebasen zu einer Vielzahl von Programmierern. Dieser Leitfaden ist im Allgemeinen führt zu einer erfolgreichen Verwendung von F# und Ärgernisse minimiert, wenn Anforderungen für Programme im Laufe der Zeit ändern.

## <a name="five-principles-of-good-f-code"></a>Fünf Prinzipien guten F# Code

Bedenken Sie die folgenden Prinzipien jedes Mal, die Sie schreiben F# Code, vor allem bei Systemen, die im Laufe der Zeit ändern. Jedes Datenelement des Leitfadens in weiteren Artikeln erwächst aus diesen fünf Punkte.

1. **Gute F# Code ist prägnante, aussagefähige und zusammensetzbar**

    F#umfasst viele Features, mit denen Sie Aktionen in weniger Codezeilen express und generische Funktionen wiederverwenden. Die F# -Kernbibliothek enthält außerdem viele hilfreiche Typen und Funktionen zum Arbeiten mit gemeinsamen Auflistungen von Daten. Komposition mit Ihren eigenen Funktionen und in der F# -Kernbibliothek (oder andere Bibliotheken) ist ein Teil der Routine idiomatische F# programmieren. Als allgemeine Regel Wenn Sie eine Lösung für ein Problem in weniger Codezeilen Ausdrücken können werden andere Entwickler (oder Ihre zukünftige Self) wertschätzenden. Es wird auch dringend empfohlen, dass Sie eine Bibliothek, z. B. FSharp.Core vorgenommen, verwenden die [große Bibliotheken für .NET](../../../api/index.md) , F# ausgeführt wird, oder ein Drittanbieter-Paket auf [NuGet](https://www.nuget.org/) Wenn müssen Sie eine komplexe Aufgabe.

2. **Gute F# Code ist interoperabel**

    Interoperation kann mehrere Formen annehmen, einschließlich Code in verschiedenen Sprachen nutzen. Die Grenzen Ihres Codes, die mit anderen Abrufe Zusammenwirken sind wichtige Bestandteile Recht, abrufen, auch wenn der Aufrufer auch in F#. Beim Schreiben von F#, Sie sollten immer denken vielleicht, wie andere Code in den Code aufrufen, wird Sie schreiben, einschließlich, wenn sie dies in einer anderen Sprache wie C#. Die [ F# Richtlinien zum Entwerfen der Komponente](component-design-guidelines.md) Interoperabilität im Detail beschrieben.

3. **Gute F# Code macht objektprogrammierung verwenden, nicht Objekt Ausrichtung**

    F#verfügt über vollständige Unterstützung für die Programmierung mit Objekten in .NET, einschließlich [Klassen](../language-reference/classes.md), [Schnittstellen](../language-reference/interfaces.md), [Zugriffsmodifizierer](../language-reference/access-control.md), [abstrakte Klassen](../language-reference/abstract-classes.md)und so weiter. Für kompliziertere Funktionscode, wie z. B. Funktionen, die Kontext-fähig ist, muss können Objekte problemlos kontextbezogenen Informationen in einer Weise, die nicht von Funktionen kapseln. Funktionen, z. B. [optionale Parameter](../language-reference/members/methods.md#optional-arguments) und sorgfältige Verwendung von [überladen](../language-reference/members/methods.md#overloaded-methods) können vereinfachen die Nutzung dieser Funktionalität für Aufrufer.

4. **Gute F# Code ausführt, ohne zu Mutation verfügbar zu machen**

    Es ist kein Geheimnis, dass zum Schreiben von Code mit hoher Leistung Mutation verwendet werden muss. Es ist, wie Computer, nachdem alle funktionieren. Solcher Code ist häufig auf, fehleranfällig und schwierig zu verwirklichen. Vermeiden Sie Mutation für Aufrufer verfügbar zu machen. Stattdessen [erstellen eine funktionsfähige-Schnittstelle, die eine Mutation-basierten Implementierung verbirgt](conventions.md#performance) Wenn Leistung wichtig ist.

5. **Gute F# Code ist lässt**

    Tools sind von großer Bedeutung für die Arbeit in großen Codebasen, und Sie können F#-Code schreiben, sodass sie effektiver mit Tools für die Sprache F# verwendet werden kann. Ein Beispiel ist sichergestellt, dass Sie mit einem Punkt kostenfreie der Programmierung, übertreiben nicht so, dass die temporären Werte mit einem Debugger überprüft werden können. Ein weiteres Beispiel verwendet den [XML-Dokumentationskommentare](../language-reference/xml-documentation.md) , beschreibt die Konstrukte, so, dass QuickInfos im Editor diese Kommentare an der Aufrufsite anzeigen können. Immer Denken Sie wie Ihr Code wird gelesen, navigiert, Debuggen, und andere Programmierer mit ihren Tools bearbeitet.

## <a name="next-steps"></a>Nächste Schritte

Die [ F# codeformatierung Richtlinien](formatting.md) bieten eine Anleitung zum Code zu formatieren, sodass sie leicht zu lesen ist.

Die [F#-Programmierung Konventionen](conventions.md) bieten eine Anleitung für F#-Programmierung arbeiten, die die langfristige Wartung von größeren F# unterstützen Codebasen.

Die [ F# Richtlinien zum Entwerfen der Komponente](component-design-guidelines.md) bieten eine Anleitung zum Erstellen von F# Komponenten, z. B. Bibliotheken.
