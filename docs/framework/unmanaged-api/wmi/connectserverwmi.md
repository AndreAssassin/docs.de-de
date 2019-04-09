---
title: ConnectServerWmi-Funktion (Referenz zur nicht verwalteten API)
description: Die ConnectServerWmi-Funktion verwendet DCOM, um eine Verbindung mit einem WMI-Namespace zu erstellen.
ms.date: 11/06/2017
api_name:
- ConnectServerWmi
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ConnectServerWmi
helpviewer_keywords:
- ConnectServerWmi function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8786892d591a98ddcd7f51eddf86fdbcf50f2197
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214870"
---
# <a name="connectserverwmi-function"></a><span data-ttu-id="ca4f0-103">ConnectServerWmi-Funktion</span><span class="sxs-lookup"><span data-stu-id="ca4f0-103">ConnectServerWmi function</span></span>
<span data-ttu-id="ca4f0-104">Erstellt über DCOM eine Verbindung mit einem WMI-Namespace auf einem angegebenen Computer.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-104">Creates a connection through DCOM to a WMI namespace on a specified computer.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ca4f0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca4f0-105">Syntax</span></span>

```
HRESULT ConnectServerWmi (
   [in] BSTR               strNetworkResource,
   [in] BSTR               strUser,
   [in] BSTR               strPassword,
   [in] BSTR               strLocale,
   [in] long               lSecurityFlags,
   [in] BSTR               strAuthority,
   [in] IWbemContext*      pCtx,
   [out] IWbemServices**   ppNamespace,
   [in] DWORD              impLevel, 
   [in] DWORD              authLevel
);
```
## <a name="parameters"></a><span data-ttu-id="ca4f0-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca4f0-106">Parameters</span></span>

`strNetworkResource`\
<span data-ttu-id="ca4f0-107">[in] Zeiger auf eine gültige `BSTR` , die den den richtigen Namespace der WMI-Objektpfad enthält.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-107">[in] Pointer to a valid `BSTR` that contains the object path of the correct WMI namespace.</span></span> <span data-ttu-id="ca4f0-108">Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-108">See the [Remarks](#remarks) section for more information.</span></span>

`strUser`\
<span data-ttu-id="ca4f0-109">[in] Ein Zeiger auf ein gültiges `BSTR` , die den Benutzernamen enthält.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-109">[in] A pointer to a valid `BSTR` that contains the user name.</span></span> <span data-ttu-id="ca4f0-110">Ein `null` Wert gibt an, den aktuellen Sicherheitskontext.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-110">A `null` value indicates the current security context.</span></span> <span data-ttu-id="ca4f0-111">Wenn der Benutzer aus einer anderen Domäne als der aktuelle Knoten ist `strUser` kann auch die Domäne und den Namen getrennt durch einen umgekehrten Schrägstrich enthalten.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-111">If the user is from a different domain than the current one, `strUser` can also contain the domain and user name separated by a backslash.</span></span> `strUser` <span data-ttu-id="ca4f0-112">kann auch sein im Format der User-principal-Name (UPN), z. B. `userName@domainName`.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-112">can also be in user principal name (UPN) format, such as `userName@domainName`.</span></span> <span data-ttu-id="ca4f0-113">Finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-113">See the [Remarks](#remarks) section for more information.</span></span>

`strPassword`\
<span data-ttu-id="ca4f0-114">[in] Ein Zeiger auf ein gültiges `BSTR` , die Kennwort enthält.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-114">[in] A pointer to a valid `BSTR` that contains the password.</span></span> <span data-ttu-id="ca4f0-115">Ein `null` gibt den aktuellen Sicherheitskontext.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-115">A `null` indicates the current security context.</span></span> <span data-ttu-id="ca4f0-116">Eine leere Zeichenfolge ("") gibt an, ein gültiges Kennwort für die Länge 0 (null).</span><span class="sxs-lookup"><span data-stu-id="ca4f0-116">An empty string ("") indicates a valid zero-length password.</span></span>

`strLocale`\
<span data-ttu-id="ca4f0-117">[in] Ein Zeiger auf ein gültiges `BSTR` , der angibt, dass des richtigen Gebietsschemas für den Abruf von Informationen.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-117">[in] A pointer to a valid `BSTR` that indicates the correct locale for information retrieval.</span></span> <span data-ttu-id="ca4f0-118">Für Microsoft-Gebietsschemabezeichner, die das Format der Zeichenfolge ist "MS\_*Xxx*", wobei *Xxx* ist eine Zeichenfolge im hexadezimalen Format, der den Gebietsschemabezeichner (LCID) angibt.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-118">For Microsoft locale identifiers, the format of the string is "MS\_*xxx*", where *xxx* is a string in hexadecimal form that indicates the locale identifier (LCID).</span></span> <span data-ttu-id="ca4f0-119">Wenn eine ungültige Gebietsschema angegeben wird, gibt die Methode `WBEM_E_INVALID_PARAMETER` außer auf Windows 7, das Standardgebietsschema des Servers ist, in denen stattdessen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-119">If an invalid locale is specified, the method returns `WBEM_E_INVALID_PARAMETER` except on Windows 7, where the default locale of the server is used instead.</span></span> <span data-ttu-id="ca4f0-120">Wenn "null1, das aktuelle Gebietsschema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-120">If \`null1, the current locale is used.</span></span> 
 
`lSecurityFlags`\
<span data-ttu-id="ca4f0-121">[in] Flags, die zum Übergeben der `ConnectServerWmi` Methode.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-121">[in] Flags to pass to the `ConnectServerWmi` method.</span></span> <span data-ttu-id="ca4f0-122">Der Wert NULL (0) für diesen Parameter im Aufruf führt `ConnectServerWmi` zurückgeben, nur, nachdem eine Verbindung mit dem Server hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-122">A value of zero (0) for this parameter results in the call to `ConnectServerWmi` returning only after a connection to the server is established.</span></span> <span data-ttu-id="ca4f0-123">Dadurch kann eine Anwendung, die nicht auf unbestimmte Zeit reagiert, wenn der Server beschädigt ist.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-123">This could result in an application not responding indefinitely if the server is broken.</span></span> <span data-ttu-id="ca4f0-124">Die andere gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ca4f0-124">The other valid values are:</span></span>

| <span data-ttu-id="ca4f0-125">Konstante</span><span class="sxs-lookup"><span data-stu-id="ca4f0-125">Constant</span></span>  | <span data-ttu-id="ca4f0-126">Wert</span><span class="sxs-lookup"><span data-stu-id="ca4f0-126">Value</span></span>  | <span data-ttu-id="ca4f0-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca4f0-127">Description</span></span>  |
|---------|---------|---------|
| `CONNECT_REPOSITORY_ONLY` | <span data-ttu-id="ca4f0-128">0x40</span><span class="sxs-lookup"><span data-stu-id="ca4f0-128">0x40</span></span> | <span data-ttu-id="ca4f0-129">Für die interne Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-129">Reserved for internal use.</span></span> <span data-ttu-id="ca4f0-130">Nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-130">Do not use.</span></span> |
| `WBEM_FLAG_CONNECT_USE_MAX_WAIT` | <span data-ttu-id="ca4f0-131">0x80</span><span class="sxs-lookup"><span data-stu-id="ca4f0-131">0x80</span></span> | `ConnectServerWmi` <span data-ttu-id="ca4f0-132">Gibt zurück, die innerhalb von zwei Minuten oder weniger.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-132">returns in two minutes or less.</span></span> |

`strAuthority`\
<span data-ttu-id="ca4f0-133">[in] Der Domänenname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-133">[in] The domain name of the user.</span></span> <span data-ttu-id="ca4f0-134">Sie können die folgenden Werte aufweisen:</span><span class="sxs-lookup"><span data-stu-id="ca4f0-134">It can have the following values:</span></span>

| <span data-ttu-id="ca4f0-135">Wert</span><span class="sxs-lookup"><span data-stu-id="ca4f0-135">Value</span></span> | <span data-ttu-id="ca4f0-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca4f0-136">Description</span></span> |
|---------|---------|
| <span data-ttu-id="ca4f0-137">leer</span><span class="sxs-lookup"><span data-stu-id="ca4f0-137">blank</span></span> | <span data-ttu-id="ca4f0-138">NTLM-Authentifizierung verwendet wird, und die NTLM-Domäne des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-138">NTLM authentication is used, and the NTLM domain of the current user is used.</span></span> <span data-ttu-id="ca4f0-139">Wenn `strUser` gibt die Domäne (der empfohlene Speicherort), dürfen nicht hier angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-139">If `strUser` specifies the domain (the recommended location), it must not be specified here.</span></span> <span data-ttu-id="ca4f0-140">Die Funktion gibt `WBEM_E_INVALID_PARAMETER` Wenn Sie die Domäne in beide Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-140">The function returns `WBEM_E_INVALID_PARAMETER` if you specify the domain in both parameters.</span></span> |
| <span data-ttu-id="ca4f0-141">Kerberos:*Prinzipalname*</span><span class="sxs-lookup"><span data-stu-id="ca4f0-141">Kerberos:*principal name*</span></span> | <span data-ttu-id="ca4f0-142">Kerberos-Authentifizierung verwendet wird, und dieser Parameter enthält, ein Kerberos-Prinzipalname.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-142">Kerberos authentication is used, and this parameter contains a Kerberos principal name.</span></span> |
| <span data-ttu-id="ca4f0-143">NTLMDOMAIN:*Domänennamen*</span><span class="sxs-lookup"><span data-stu-id="ca4f0-143">NTLMDOMAIN:*domain name*</span></span> | <span data-ttu-id="ca4f0-144">NT LAN Manager-Authentifizierung wird verwendet, und dieser Parameter enthält einen NTLM-Domänennamen.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-144">NT LAN Manager authentication is used, and this parameter contains an NTLM domain name.</span></span> |

`pCtx`\
<span data-ttu-id="ca4f0-145">[in] Dieser Parameter in der Regel ist `null`.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-145">[in] Typically, this parameter is `null`.</span></span> <span data-ttu-id="ca4f0-146">Andernfalls wird ein Zeiger auf ein [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) Objekt durch eine oder mehrere dynamische Klasse Anbieter erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-146">Otherwise, it is a pointer to an [IWbemContext](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemcontext) object required by one or more dynamic class providers.</span></span> 

`ppNamespace`\
<span data-ttu-id="ca4f0-147">[out] Wenn die Funktion zurückgibt, erhält einen Zeiger auf ein [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) Objekt an den angegebenen Namespace gebunden.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-147">[out] When the function returns, receives a pointer to an [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object bound to the specified namespace.</span></span> <span data-ttu-id="ca4f0-148">Festgelegt auf zeigen `null` , wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-148">It is set to point to `null` when there is an error.</span></span>

`impLevel`\
<span data-ttu-id="ca4f0-149">[in] Die Ebene des Identitätswechsels.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-149">[in] The impersonation level.</span></span>

`authLevel`\
<span data-ttu-id="ca4f0-150">[in] Die Autorisierungsebene.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-150">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="ca4f0-151">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ca4f0-151">Return value</span></span>

<span data-ttu-id="ca4f0-152">Die folgenden Werte, die von dieser Funktion zurückgegebenen werden definiert, der *WbemCli.h* Header-Datei, und Sie können definieren sie als Konstanten in Ihrem Code:</span><span class="sxs-lookup"><span data-stu-id="ca4f0-152">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ca4f0-153">Konstante</span><span class="sxs-lookup"><span data-stu-id="ca4f0-153">Constant</span></span>  |<span data-ttu-id="ca4f0-154">Wert</span><span class="sxs-lookup"><span data-stu-id="ca4f0-154">Value</span></span>  |<span data-ttu-id="ca4f0-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ca4f0-155">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="ca4f0-156">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ca4f0-156">0x80041001</span></span> | <span data-ttu-id="ca4f0-157">Es wurde ein allgemeiner Fehler.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-157">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ca4f0-158">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ca4f0-158">0x80041008</span></span> | <span data-ttu-id="ca4f0-159">Ein Parameter ist ungültig.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-159">A parameter is not valid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ca4f0-160">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ca4f0-160">0x80041006</span></span> | <span data-ttu-id="ca4f0-161">Es ist nicht genügend Arbeitsspeicher verfügbar, um den Vorgang abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-161">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ca4f0-162">0</span><span class="sxs-lookup"><span data-stu-id="ca4f0-162">0</span></span> | <span data-ttu-id="ca4f0-163">Der Funktionsaufruf war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-163">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="ca4f0-164">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca4f0-164">Remarks</span></span>

<span data-ttu-id="ca4f0-165">Diese Funktion umschließt einen Aufruf der [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) Methode.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-165">This function wraps a call to the [IWbemLocator::ConnectServer](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemlocator-connectserver) method.</span></span>

<span data-ttu-id="ca4f0-166">Für den lokalen Zugriff auf den Standardnamespace `strNetworkResource` kann ein einfaches Objekt-Pfad: "Root\default" oder "\\.\root\default".</span><span class="sxs-lookup"><span data-stu-id="ca4f0-166">For local access to the default namespace, `strNetworkResource` can be a simple object path: "root\default" or "\\.\root\default".</span></span> <span data-ttu-id="ca4f0-167">Für den Zugriff auf den Standardnamespace auf einem Remotecomputer mithilfe der COM- oder Microsoft-kompatiblen-Netzwerken, den Namen des Computers enthalten: "\\Myserver\root\default".</span><span class="sxs-lookup"><span data-stu-id="ca4f0-167">For access to the default namespace on a remote computer using COM or Microsoft-compatible networking, include the computer name: "\\myserver\root\default".</span></span> <span data-ttu-id="ca4f0-168">Den Namen des Computers kann auch einen DNS-Namen oder die IP-Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-168">The computer name also can be a DNS name or IP address.</span></span> <span data-ttu-id="ca4f0-169">Die `ConnectServerWmi` Funktion kann auch eine Verbindung herstellen mit IPv6-Computern mit einer IPv6-Adresse.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-169">The `ConnectServerWmi` function can also connect with computers running IPv6 using an IPv6 address.</span></span>

`strUser` <span data-ttu-id="ca4f0-170">eine leere Zeichenfolge darf nicht sein.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-170">cannot be an empty string.</span></span> <span data-ttu-id="ca4f0-171">Wenn in die Domäne angegeben ist `strAuthority`, er darf nicht auch enthalten sein `strUser`, oder die Funktion gibt `WBEM_E_INVALID_PARAMETER`.</span><span class="sxs-lookup"><span data-stu-id="ca4f0-171">If the domain is specified in `strAuthority`, it must not also be included in `strUser`, or the function returns `WBEM_E_INVALID_PARAMETER`.</span></span>

## <a name="requirements"></a><span data-ttu-id="ca4f0-172">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca4f0-172">Requirements</span></span>

 <span data-ttu-id="ca4f0-173">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca4f0-173">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="ca4f0-174">**Header:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ca4f0-174">**Header:** WMINet_Utils.idl</span></span>

 **<span data-ttu-id="ca4f0-175">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="ca4f0-175">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a><span data-ttu-id="ca4f0-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca4f0-176">See also</span></span>

- [<span data-ttu-id="ca4f0-177">WMI und Leistungsindikatoren (Referenz zur nicht verwalteten API)</span><span class="sxs-lookup"><span data-stu-id="ca4f0-177">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)