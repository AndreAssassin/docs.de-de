---
title: <mailSettings>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mailSettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings
helpviewer_keywords:
- mailSettings element
- <mailSettings> element
ms.assetid: 54f0f153-17e5-4f49-afdc-deadb940c9c1
ms.openlocfilehash: b8ea08cbd76e60a3665703bc50924dd94500cd87
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659333"
---
# <a name="mailsettings-element-network-settings"></a><span data-ttu-id="48d1a-102">\<mailSettings >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="48d1a-102">\<mailSettings> Element (Network Settings)</span></span>
<span data-ttu-id="48d1a-103">Konfiguriert E-Mail-Sendeoptionen.</span><span class="sxs-lookup"><span data-stu-id="48d1a-103">Configures mail sending options.</span></span>  

<span data-ttu-id="48d1a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="48d1a-104">\<configuration></span></span>  
<span data-ttu-id="48d1a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="48d1a-105">\<system.net></span></span>  
<span data-ttu-id="48d1a-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="48d1a-106">\<mailSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48d1a-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="48d1a-107">Syntax</span></span>  
  
```xml  
<mailSettings>
  <smtp>...</smtp>  
</mailSettings>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48d1a-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="48d1a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="48d1a-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="48d1a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48d1a-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="48d1a-110">Attributes</span></span>  
 <span data-ttu-id="48d1a-111">Keine</span><span class="sxs-lookup"><span data-stu-id="48d1a-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="48d1a-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="48d1a-112">Child Elements</span></span>  
  
|<span data-ttu-id="48d1a-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="48d1a-113">Attribute</span></span>|<span data-ttu-id="48d1a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48d1a-114">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="48d1a-115">\<SMTP->-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="48d1a-115">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="48d1a-116">Konfiguriert die Optionen des Simple Mail-Transport Protokolls.</span><span class="sxs-lookup"><span data-stu-id="48d1a-116">Configures Simple Mail Transport Protocol options.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="48d1a-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="48d1a-117">Parent Elements</span></span>  
  
|<span data-ttu-id="48d1a-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="48d1a-118">**Element**</span></span>|<span data-ttu-id="48d1a-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="48d1a-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="48d1a-120">\<system.Net>-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="48d1a-120">\<system.Net> Element (Network Settings)</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="48d1a-121">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="48d1a-121">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="48d1a-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48d1a-122">Example</span></span>  
 <span data-ttu-id="48d1a-123">Im folgenden Beispiel werden die entsprechenden SMTP-Parameter zum Senden von e-Mails mit den standardmäßigen Netzwerk Anmelde Informationen angegeben.</span><span class="sxs-lookup"><span data-stu-id="48d1a-123">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          host="localhost"  
          port="25"  
          defaultCredentials="true"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="48d1a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48d1a-124">See also</span></span>

- <xref:System.Net.Mail.SmtpClient>
- [<span data-ttu-id="48d1a-125">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="48d1a-125">Network Settings Schema</span></span>](index.md)
