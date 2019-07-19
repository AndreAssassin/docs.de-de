---
title: Erste Schritte mit .NET Core
description: Suchen Sie Ressourcen, um zu erfahren, wie Sie .NET Core-Anwendungen auf Windows, Linux und Mac OS erstellen können.
author: thraka
ms.author: adegeo
ms.date: 06/27/2018
ms.openlocfilehash: b111d464b83f3bc6a4a0da86678c5364bf4a9537
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802302"
---
# <a name="get-started-with-net-core"></a>Erste Schritte mit .NET Core

Dieser Artikel enthält Informationen zu den ersten Schritten mit .NET Core. .NET Core kann unter Windows, Linux und macOS installiert werden. Außerdem können Sie in Ihrem bevorzugten Text-Editor programmieren und plattformübergreifende Bibliotheken und Anwendungen erstellen. 

Wenn Sie nicht sicher sind, was .NET Core ist oder in welcher Beziehung es zu anderen .NET-Technologien steht, sollten Sie mit [What is .NET (Was ist .NET)](https://www.microsoft.com/net/learn/dotnet/what-is-dotnet) beginnen. Einfach ausgedrückt, ist .NET Core eine plattformübergreifende Open-Source-Implementierung von .NET.

## <a name="create-an-application"></a>Erstellen einer Anwendung

Laden Sie das [.NET Core SDK](https://www.microsoft.com/net/download/) auf Ihrem Computer herunter, und installieren Sie es.

Als Nächstes öffnen Sie ein Terminal, z.B. **PowerShell**, die **Eingabeaufforderung** oder die **Bash**. Geben Sie die folgenden `dotnet`-Befehle ein, um eine C#-Anwendung zu erstellen und zu veröffentlichen:

```console
dotnet new console --output sample1
dotnet run --project sample1
```

Die folgende Ausgabe wird angezeigt:

```console
Hello World!
```

Herzlichen Glückwunsch! Sie haben eine einfache .NET Core-Anwendung erstellt. Sie können auch [Visual Studio Code](tutorials/with-visual-studio-code.md), [Visual Studio](tutorials/with-visual-studio.md) (nur Windows) oder [Visual Studio für Mac](tutorials/using-on-mac-vs.md) (nur macOS) verwenden, um eine .NET Core-Anwendung zu erstellen.

## <a name="tutorials"></a>Tutorials

Die folgenden ausführlichen Tutorials helfen Ihnen beim Einstieg in das Entwickeln von .NET Core-Anwendungen.

# <a name="windowstabwindows"></a>[Windows](#tab/windows)

* [Erstellen einer „Hallo Welt“-Anwendung in C# mit .NET Core in Visual Studio 2017](./tutorials/with-visual-studio.md)

* [Erstellen einer Klassenbibliothek mit C# und .NET Core in Visual Studio 2017](./tutorials/library-with-visual-studio.md)

* [Erstellen einer „Hallo Welt“-Anwendung in Visual Basic mit .NET Core in Visual Studio 2017](./tutorials/vb-with-visual-studio.md)

* [Erstellen einer Klassenbibliothek mit Visual Basic und .NET Core in Visual Studio 2017](./tutorials/vb-library-with-visual-studio.md)  

* Sehen Sie sich ein Video zum [Installieren und Verwenden von Visual Studio Code und .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-using-CSharp-and-NET-Core/) an.

* Sehen Sie sich ein Video zum [Installieren und Verwenden von Visual Studio 2017 und .NET Core](https://channel9.msdn.com/Blogs/dotnet/Get-Started-NET-Core-Visual-Studio-2017/) an.

* [Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile](tutorials/using-with-xplat-cli.md)

Eine Liste der unterstützten Windows-Versionen finden Sie unter [Voraussetzungen für .NET Core unter Windows](windows-prerequisites.md).

# <a name="linuxtablinux"></a>[Linux](#tab/linux)

Die folgenden ausführlichen Tutorials helfen Ihnen beim Einstieg in das Entwickeln von .NET Core-Anwendungen.

* [Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile](tutorials/using-with-xplat-cli.md)

* Sehen Sie sich ein Video zu den [ersten Schritte mit Visual Studio Code mit C# und .NET Core unter Ubuntu](https://channel9.msdn.com/Blogs/dotnet/Get-started-with-VS-Code-Csharp-dotnet-Core-Ubuntu) an.

Eine Liste der unterstützten Linux-Versionen finden Sie unter [Voraussetzungen für .NET Core unter Linux](linux-prerequisites.md).

# <a name="macostabmacos"></a>[macOS](#tab/macos)

Die folgenden ausführlichen Tutorials helfen Ihnen beim Einstieg in das Entwickeln von .NET Core-Anwendungen.

* Sehen Sie sich ein Video zu den [ersten Schritte mit Visual Studio Code mit C# und .NET Core unter macOS](https://channel9.msdn.com/Blogs/dotnet/Get-started-VSCode-NET-Core-Mac) an.

* [Erste Schritte mit .NET Core unter Mac OS](tutorials/using-on-macos.md)

* [Erste Schritte mit .NET Core unter Windows/Linux/Mac OS unter Verwendung der Befehlszeile](tutorials/using-with-xplat-cli.md)

* [Erste Schritte mit .NET Core unter macOS mit Visual Studio für Mac](tutorials/using-on-mac-vs.md)

* [Erstellen einer vollständigen .NET Core-Lösung unter macOS mit Visual Studio für Mac](tutorials/using-on-mac-vs-full-solution.md)

Eine Liste der unterstützten macOS-Versionen finden Sie unter [Voraussetzungen für .NET Core unter OS X/macOS](macos-prerequisites.md).

---
