---
title: -refout (C# Compileroptionen)
ms.date: 08/08/2017
f1_keywords:
- /refout
helpviewer_keywords:
- refout compiler option [C#]
- /refout compiler option [C#]
- -refout compiler option [C#]
ms.openlocfilehash: 97cbf540527d0449387b71bb1d97df95b6a4aba4
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602506"
---
# <a name="-refout-c-compiler-options"></a>-refout (C# Compileroptionen)

Die Option **-refout** gibt einen Dateipfad an, an den die Verweisassembly ausgegeben werden soll. Dies entspricht `metadataPeStream` in der Emit-API. Diese Option entspricht der Projekteigenschaft [ProduceReferenceAssembly](/visualstudio/msbuild/common-msbuild-project-properties) von MSBuild.

## <a name="syntax"></a>Syntax

```console
-refout:filepath
```

## <a name="arguments"></a>Argumente

 `filepath`: Der Dateipfad für die Verweisassembly. Dieser sollte im Allgemeinen mit der primären Assembly übereinstimmen. Die empfohlene Konvention (von MSBuild verwendet) ist die, die Verweisassembly in einem „ref/“-Unterordner zu platzieren, der relativ zur primären Assembly ist.

## <a name="remarks"></a>Anmerkungen

Bei auf Metadaten beschränkten Assemblys werden die Methodentexte durch einen einzigen `throw null`-Text ersetzt, sie enthalten jedoch alle Member außer anonymen Typen. Der Grund für die Verwendung von `throw null`-Texten (im Gegensatz zu keinen Texten) ist, dass PEVerify erfolgreich ausgeführt werden kann (und so wird die Vollständigkeit der Metadaten überprüft).

Verweisassemblys enthalten ein `ReferenceAssembly`-Attribut auf Assemblyebene. Dieses Attribut kann in der Quelle angegeben werden (dann muss der Compiler es nicht künstlich erstellen). Durch dieses Attribut wird die Laufzeit das Ausführen von Verweisassemblys verweigert (sie können aber dennoch im reflektionsbezogenen Modus geladen werden). Tools, die Assemblys reflektieren, müssen sicherstellen, dass Assemblys nur reflektionsbezogen geladen werden. Andernfalls erhalten Sie einen Laufzeitfehler beim Laden von Typen.

Verweisassemblys entfernen außerdem Metadaten (private Member) aus auf Metadaten beschränkten Assemblys:

- Eine Verweisassembly verfügt nur über die Verweise, die es in der API-Oberfläche benötigt. Die echte Assembly kann über zusätzliche Verweise verfügen, die sich auf bestimmte Implementierungen beziehen. Bei Instanzen verweist die Verweisassembly für `class C { private void M() { dynamic d = 1; ... } }` nicht auf Typen, die für `dynamic` erforderlich sind.
- Private Funktionsmember (Methoden, Eigenschaften und Ereignisse) werden in den Fällen entfernt, in denen ihre Entfernung sich nicht erkennbar auf die Kompilierung auswirkt. Wenn keine <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>-Attribute vorhanden sind, gehen Sie für interne Funktionsmember genauso vor.
- Es werden jedoch alle Typen (einschließlich privater oder geschachtelter Typen) in Verweisassemblys beibehalten. Alle Attribute (auch interne) werden beibehalten.
- Alle virtuellen Methoden werden beibehalten. Explizite Schnittstellenimplementierungen werden beibehalten. Explizit implementierte Eigenschaften und Ereignisse werden beibehalten, aber ihre Accessoren sind virtuell (und werden deshalb beibehalten).
- Alle Felder einer Struktur werden beibehalten. (Dies ist ein Kandidat für eine Optimierung nach C# 7.1)

Die Optionen `-refout` und [`-refonly`](refonly-compiler-option.md) schließen sich gegenseitig aus.

## <a name="see-also"></a>Siehe auch

- [C#-Compileroptionen](./index.md)
- [Verwalten von Projekt- und Projektmappeneigenschaften](/visualstudio/ide/managing-project-and-solution-properties)
