---
title: Befehl „dotnet tool list“
description: Der Befehl „dotnet tool list“ listet die angegebenen globalen .NET Core-Tools auf Ihrem Computer auf.
ms.date: 05/29/2018
ms.openlocfilehash: 6d35b1dce0c6d57edb0c6dd5f9711f093bc804aa
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117557"
---
# <a name="dotnet-tool-list"></a>dotnet tool list

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>NAME

`dotnet tool list`: listet alle [globalen .NET Core-Tools](global-tools.md) auf, die derzeit im Standardverzeichnis oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind.

## <a name="synopsis"></a>Zusammenfassung

```dotnetcli
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a>BESCHREIBUNG

Der Befehl `dotnet tool list` ermöglicht Ihnen das Auflisten aller globalen .NET Core-Tools, die benutzerweit (aktuelles Benutzerprofil) oder unter dem angegebenen Pfad auf Ihrem Computer installiert sind. Der Befehl listet den Paketnamen, die installierte Version und den Befehl für das globale Tool auf. Zum Verwenden des list-Befehls müssen Sie entweder mit der Option `--global` angeben, dass alle benutzerweiten Tools angezeigt werden sollen, oder mit der Option `--tool-path` einen benutzerdefinierten Pfad angeben.

## <a name="options"></a>Optionen

`-g|--global`

Listet benutzerweite globale Tools auf. Kann nicht mit der Option `--tool-path` kombiniert werden. Wenn Sie diese Option nicht angeben, müssen Sie die Option `--tool-path` angeben.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--tool-path <PATH>`

Legt einen benutzerdefinierten Speicherort fest, an dem globale Tools gespeichert sind. „PATH“ kann absolut oder relativ sein. Kann nicht mit der Option `--global` kombiniert werden. Wenn Sie diese Option nicht angeben, müssen Sie die Option `--global` angeben.

## <a name="examples"></a>Beispiele

Listet alle globale Tools auf, die benutzerweit auf Ihrem Computer installiert sind (aktuelles Benutzerprofil):

`dotnet tool list -g`

Listet die globalen Tools aus einem bestimmten Windows-Ordner auf:

`dotnet tool list --tool-path c:\global-tools`

Listet die globalen Tools aus einem bestimmten Linux-/macOS-Ordner auf:

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a>Siehe auch

- [.NET Core Global Tools (Globale .NET Core-Tools)](global-tools.md)
