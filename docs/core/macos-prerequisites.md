---
title: Voraussetzungen für .NET Core unter Mac
description: Unterstützte Versionen von macOS-Versionen und .NET Core-Abhängigkeiten, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen.
author: mairaw
ms.author: adegeo
ms.custom: updateeachvsrelease
ms.date: 07/13/2019
ms.openlocfilehash: 5086b185ee2d49c7b569ed0cb62b4c8995f9982c
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433914"
---
# <a name="prerequisites-for-net-core-on-macos"></a>Erforderliche Komponenten für .NET Core unter macOS

Dieser Artikel zeigt Ihnen die unterstützten macOS-Versionen und .NET Core-Abhängigkeiten, die Sie benötigen, um .NET Core-Anwendungen auf macOS-Computern zu entwickeln, bereitzustellen und auszuführen. Die unterstützten Betriebssystemversionen und Abhängigkeiten für die drei Arten der Entwicklung von .NET Core-Apps auf einem Mac: über die [Befehlszeile mit Ihrem bevorzugten Editor](tutorials/using-with-xplat-cli.md), mit [Visual Studio Code](https://code.visualstudio.com/) oder unter Verwendung von [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).

## <a name="supported-macos-versions"></a>Unterstützte macOS-Versionen

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x wird von folgenden macOS-Versionen unterstützt:

* macOS 10.12 „Sierra“ und höher

Unter [Von .NET Core 2.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) und [Von .NET Core 2.2 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 2.1 und .NET Core 2.2 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 2.2-Downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) oder [.NET Core 2.1-Downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x wird von folgenden macOS-Versionen unterstützt:

* macOS 10.12 „Sierra“
* macOS 10.11 „El Capitan“

Unter [Von .NET Core 1.1 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/1.1/1.1.md) und [Von .NET Core 1.0 unterstützte Betriebssystemversionen](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 1.1 und .NET Core 1.0 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 1.1-Downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) oder [.NET Core 1.0-Downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

.NET Core 3.0 wird von folgenden macOS-Versionen unterstützt:

* macOS 10.13 „High Sierra“ und höher

Unter [.NET Core 3.0 Supported OS Versions (Von .NET Core 3.0 unterstützte Betriebssystemversionen)](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) finden Sie die vollständige Liste der Betriebssysteme, Verteilungen und Versionen, die von .NET Core 3.0 unterstützt werden, außerdem nicht mehr unterstützte Betriebssystemversionen und Links zu Lebenszyklusrichtlinien.

Links zum Herunterladen und weitere Informationen finden Sie unter [.NET Core 3.0-Downloads](https://www.microsoft.com/net/download/dotnet-core/3.0).

---

## <a name="net-core-dependencies"></a>.NET Core-Abhängigkeiten

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es. Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich für Ihre installierte Version das Thema [Known issues (Bekannte Probleme)](https://github.com/dotnet/core/tree/master/release-notes/2.1) an.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

.NET Core 1.x erfordert unter macOS OpenSSL. Eine einfache Möglichkeit zum Abrufen von OpenSSL ist mithilfe des [Homebrew („brew“)](https://brew.sh/)-Paket-Managers für macOS. Installieren Sie nach der Installation von *brew* OpenSSL durch Ausführen der folgenden Befehle in einer Terminaleingabeaufforderung (Befehl):

```console
brew update
brew install openssl
mkdir -p /usr/local/lib
ln -s /usr/local/opt/openssl/lib/libcrypto.1.0.0.dylib /usr/local/lib/
ln -s /usr/local/opt/openssl/lib/libssl.1.0.0.dylib /usr/local/lib/
```

Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es. Wenn Sie Probleme bei der Installation auf macOS haben, sehen Sie sich die Themen [1.0.0 Known Issues (1.0.0 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) und [1.0.1 Known Issues (1.0.1 Bekannte Probleme)](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) an.

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

Laden Sie das .NET Core SDK von [.NET Downloads](https://www.microsoft.com/net/download/core) herunter, und installieren Sie es. Wenn Sie Probleme bei der Installation unter macOS haben, sehen Sie sich für Ihre installierte Version das Thema [Anmerkungen zu dieser Version](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) an.

---

## <a name="increase-the-maximum-open-file-limit-net-core-versions-before-net-core-sdk-202"></a>Erhöhen des Limits für die maximale Anzahl von geöffneten Dateien (.NET Core Versionen vor .NET Core SDK 2.0.2)

In früheren Versionen von .NET Core (vor .NET Core SDK 2.0.2) ist das Standardlimit für geöffnete Dateien unter macOS für einige .NET Core-Workloads möglicherweise nicht ausreichend, z.B. für das Wiederherstellen von Projekten oder das Ausführen von Komponententests.

Sie können dieses Limit erhöhen, indem Sie diese Schritte befolgen:

1. Erstellen Sie mithilfe eines Text-Editors die neue Datei _/Library/LaunchDaemons/limit.maxfiles.plist_, und speichern Sie die Datei mit diesem Inhalt:

    ```xml
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
      <dict>
        <key>Label</key>
        <string>limit.maxfiles</string>
        <key>ProgramArguments</key>
        <array>
          <string>launchctl</string>
          <string>limit</string>
          <string>maxfiles</string>
          <string>2048</string>
          <string>4096</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>ServiceIPC</key>
        <false/>
      </dict>
    </plist>
    ```

2. Führen Sie in einem Terminalfenster folgenden Befehl aus:

   ```console
   echo 'ulimit -n 2048' | sudo tee -a /etc/profile
   ```

3. Starten Sie Ihren Mac neu, um diese Einstellungen zu übernehmen.

## <a name="visual-studio-for-mac"></a>Visual Studio für Mac

Sie können einen Editor zur .NET Core-Anwendungsentwicklung mit dem .NET Core SDK verwenden. Wenn Sie jedoch .NET Core-Anwendungen unter Mac in einer integrierten Entwicklungsumgebung entwickeln möchten, können Sie [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) verwenden.

Für die .NET Core-Entwicklung unter macOS mit Visual Studio für Mac benötigen Sie Folgendes:

* Eine unterstützte Version eines macOS-Betriebssystems
* OpenSSL (nur .NET Core 1.x, .NET Core 2.x verwendet native Sicherheitsdienste von macOS)
* .NET Core SDK für Mac
* [Visual Studio für Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
