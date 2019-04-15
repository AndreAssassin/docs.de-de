---
ms.openlocfilehash: 0dfc87201b9b31cd9d936f2c965c7d0ca0140cab
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234250"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>„X509Certificate2.ToString(Boolean)“ wird jetzt nicht mehr ausgelöst, wenn .NET das Zertifikat nicht verarbeiten kann

|   |   |
|---|---|
|Details|Zuvor wurde diese Methode in .NET Framework 4.5.2 ausgelöst, wenn <code>true</code> für den ausführlichen Parameter übergeben wurde und Zertifikate installiert waren, die von .NET Framework nicht unterstützt wurden. Nun wird die Methode erfolgreich ausgeführt und gibt eine gültige Zeichenfolge zurück, die die Teile des Zertifikats auslässt, auf die nicht zugegriffen werden kann.|
|Vorschlag|Jeder von <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> abhängige Code sollte aktualisiert werden, um zu erwarten, dass die zurückgegebene Zeichenfolge einige Zertifikatsdaten in einigen Fällen ausschließt (z.B. den öffentlichen Schlüssel, den privaten Schlüssel und die Erweiterungen), in denen zuvor die API ausgelöst worden wäre.|
|Bereich|Microsoft Edge|
|Version|4.6|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|
