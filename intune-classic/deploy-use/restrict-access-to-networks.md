---
title: Ochrana přístupu k sítím s modulem Cisco ISE
description: Použijte Cisco ISE s Intune, aby zařízení byla zaregistrovaná v Intune a vyhovovala zásadám, než se pokusí o přístup k sítím Wi-Fi a VPN řízeným pomocí Cisco ISE.
keywords: ''
author: dougeby
ms.author: angrobe
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e455f291d9bfdb655f6c66cad7bf859a864e756d
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="using-cisco-ise-with-microsoft-intune"></a>Použití Cisco ISE s Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Integrace Intune s Cisco ISE (Identity Services Engine) umožňuje vytvářet zásady sítě v prostředí ISE na základě stavu registrace zařízení v Intune a jejich stavu dodržování předpisů. Prostřednictvím těchto zásad můžete zajistit, aby byl přístup k síti vaší společnosti omezen na zařízení, která jsou spravována pomocí Intune a vyhovují zásadám Intune.

## <a name="configuration-steps"></a>Kroky konfigurace

Chcete-li tuto integraci povolit, nemusíte v tenantovi Intune provádět žádné nastavení. Bude třeba poskytnout serveru Cisco ISE oprávnění pro přístup k tenantovi Intune. Zbývající část nastavení se potom provede na serveru Cisco ISE. Tento článek obsahuje pokyny pro poskytnutí oprávnění pro přístup k vašemu tenantovi Intune pro váš server ISE.

### <a name="step-1-manage-the-certificates"></a>Krok 1: Správa certifikátů
Exportujte certifikát z konzoly Azure Active Directory (Azure AD) a importujte jej do úložiště důvěryhodných certifikátů konzoly ISE:

#### <a name="internet-explorer-11"></a>Internet Explorer 11


   a. Spusťte Internet Explorer jako správce a přihlaste se ke konzole Azure AD.

   b. Zvolte ikonu zámku na panelu Adresa a pak zvolte **Zobrazit certifikáty**.

   c. Na kartě **Podrobnosti** v rámci vlastností certifikátu zvolte **Kopírovat do souboru**.

   d. Na úvodní stránce **Průvodce exportem certifikátu** zvolte **Další**.

   e. Na stránce **Formát souboru pro export** ponechte výchozí nastavení **Binární x.509, kódování DER (CER)** a zvolte **Další**.  

   f. Na stránce **Soubor k exportu** zvolte **Procházet**, vyberte umístění, do kterého chcete soubor uložit, a zadejte název souboru. Ačkoli se zdá, že vybíráte soubor pro export, ve skutečnosti pojmenováváte soubor, do kterého bude exportovaný certifikát uložen. Zvolte **Další** &gt; **Dokončit**.

   g. Z konzoly ISE importujte certifikát Intune (soubor, který jste exportovali) do úložiště **Důvěryhodné certifikáty**.

#### <a name="safari"></a>Safari

 a. Přihlaste se ke konzole Azure AD.

b. Zvolte ikonu zámku &gt; **Další informace**.

   c. Zvolte **Zobrazit certifikát** &gt; **Podrobnosti**.

   d. Zvolte certifikát a pak zvolte **Exportovat**. 

   e. Z konzoly ISE importujte certifikát Intune (soubor, který jste exportovali) do úložiště **Důvěryhodné certifikáty**.

> [!IMPORTANT]
>
> Zkontrolujte datum vypršení platnosti certifikátu, protože po vypršení platnosti tohoto certifikátu bude třeba exportovat a importovat nový certifikát.


### <a name="obtain-a-self-signed-cert-from-ise"></a>Získání certifikátu podepsaného svým držitelem ze systému ISE 

1.  V konzole ISE přejděte do části **Správa** > **Certifikáty** > **Systémové certifikáty** > **Generovat certifikát podepsaný jeho držitelem**.  
2.       Exportujte certifikát podepsaný svým držitelem.
3. V textovém editoru upravte exportovaný certifikát:

 - Odstraňte text: **-----BEGIN CERTIFICATE-----**
 - Odstraňte text: **-----END CERTIFICATE-----**
 
Ověřte, že veškerý text leží na jednom řádku.


### <a name="step-2-create-an-app-for-ise-in-your-azure-ad-tenant"></a>Krok 2: Vytvoření aplikace pro ISE ve vašem tenantovi Azure AD
1. V konzole Azure AD zvolte **Aplikace** > **Přidat aplikaci** > **Přidat aplikaci, kterou vyvíjí moje organizace**.
2. Zadejte název a adresu URL pro aplikaci. Adresou URL může být web vaší společnosti.
3. Stáhněte manifest aplikace (soubor JSON).
4. Upravte soubor JSON manifestu. V nastavení s názvem **keyCredentials** zadejte jako hodnotu nastavení upravený text certifikátu z kroku 1.
5. Uložte soubor beze změny jeho názvu.
6. Poskytněte své aplikaci oprávnění pro rozhraní API Microsoft Intune a Microsoft Graph.

 a. Pro Microsoft Graph vyberte následující:
    - **Oprávnění aplikací**: Čtení dat adresáře
    - **Delegovaná oprávnění**:
        - Časově neomezený přístup k datům uživatele
        - Přihlášení uživatelů

 b. Pro rozhraní API Microsoft Intune v části **Oprávnění aplikací** zvolte **Zjistit stav zařízení a jeho stav dodržování předpisů z služby Intune**.

7. Zvolte **Zobrazit koncové body** a zkopírujte následující hodnoty pro použití při konfiguraci nastavení ISE:

|Hodnota v portálu Azure AD|Odpovídající pole v rámci portálu ISE|
|-------------------|---------------------------------|
|Koncový bod rozhraní API pro Microsoft Azure AD Graph|Adresa URL pro automatické zjišťování|
|Koncový bod tokenu OAuth 2.0|Adresa URL pro vydávání tokenů|
|Aktualizace kódu s použitím ID klienta|ID klienta|

### <a name="step-4-upload-the-self-signed-certificate-from-ise-into-the-ise-app-you-created-in-azure-ad"></a>Krok 4: Nahrání certifikátu podepsaného svým držitelem z ISE do aplikace ISE, kterou jste vytvořili ve službě Azure AD
1.     Získejte hodnotu zakódovaného certifikátu base64 a kryptografický otisk ze souboru certifikátu .cer X509. V tomto příkladu je používáno prostředí PowerShell:
   
      
      $cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2    $cer.Import(“mycer.cer”)    $bin = $cer.GetRawCertData()    $base64Value = [System.Convert]::ToBase64String($bin)    $bin = $cer.GetCertHash()    $base64Thumbprint = [System.Convert]::ToBase64String($bin)    $keyid = [System.Guid]::NewGuid().ToString()
 
    Uložte hodnoty pro $base64Thumbprint, $base64Value a $keyid, které použijete v dalším kroku.
2.       Nahrajte certifikát prostřednictvím souboru manifestu. Přihlaste se k [portálu pro správu Azure](https://manage.windowsazure.com)
2.      Ve snapinu služby Azure AD najděte aplikaci, kterou chcete nakonfigurovat pomocí certifikátu X.509.
3.      Stáhněte si soubor manifestu aplikace. 
5.      Nahraďte prázdnou vlastnost “KeyCredentials”: [] následujícím formátem JSON.  Komplexní typ s názvem KeyCredentials je zdokumentován v [ Referenčních informacích k entitám a komplexním typům](https://msdn.microsoft.com/library/azure/ad/graph/api/entity-and-complex-type-reference#KeyCredentialType).

 
    “keyCredentials“: [ { “customKeyIdentifier“: “$base64Thumbprint_from_above”, “keyId“: “$keyid_from_above“, “type”: “AsymmetricX509Cert”, “usage”: “Verify”, “value”:  “$base64Value_from_above” }2. 
     ], 
 
Příklad:
 
    “keyCredentials“: [
    {
    “customKeyIdentifier“: “ieF43L8nkyw/PEHjWvj+PkWebXk=”,
    “keyId“: “2d6d849e-3e9e-46cd-b5ed-0f9e30d078cc”,
    “type”: “AsymmetricX509Cert”,
    “usage”: “Verify”,
    “value”: “MIICWjCCAgSgAwIBA***omitted for brevity***qoD4dmgJqZmXDfFyQ”
    }
    ],
 
6.      Uložte změny do souboru manifestu aplikace.
7.      Nahrajte upravený soubor manifestu aplikace prostřednictvím Portálu pro správu Azure.
8.      Volitelné: Znovu si stáhněte manifest a zkontrolujte, jestli aplikace obsahuje váš certifikát X.509.

>[!NOTE]
>
> KeyCredentials je kolekce, což znamená, že můžete nahrát více certifikátů X.509 pro scénáře změny klíčů nebo odstranit certifikáty ve scénářích ohrožení.


### <a name="step-4-configure-ise-settings"></a>Krok 4: Konfigurace nastavení ISE
V konzole správce ISE zadejte tyto hodnoty nastavení:
  - **Typ serveru**: Správce mobilních zařízení
  - **Typ ověřování**: OAuth – pověření klienta
  - **Automatické zjišťování**: Ano
  - **Adresa URL pro automatické zjišťování**: *Zadejte hodnotu z kroku 1*.
  - **ID klienta**: *Zadejte hodnotu z kroku 1*.
  - **Adresa URL pro vydávání tokenů**: *Zadejte hodnotu z kroku 1*.



## <a name="information-shared-between-your-intune-tenant-and-your-cisco-ise-server"></a>Informace sdílené mezi vaším tenantem Intune a vaším serverem Cisco ISE
Tato tabulka uvádí informace sdílené mezi vaším tenantem Intune a vaším serverem Cisco ISE pro zařízení, která jsou spravovaná pomocí Intune.

|Vlastnost|  Popis|
|---------------|------------------------------------------------------------|
|complianceState|Řetězec true nebo false určující, jestli zařízení je nebo není vyhovující.|
|isManaged|Řetězec true nebo false určující, jestli klient je nebo není spravovaný pomocí Intune.|
|macAddress|Adresa MAC zařízení.|
|serialNumber|Sériové číslo zařízení. Týká se pouze zařízení s iOSem.|
|imei|Kód IMEI (15 desítkových číslic: 14 číslic plus kontrolní číslice) nebo IMEISV (16 číslic) obsahuje informace o původu, modelu a sériovém čísle zařízení. Struktura tohoto čísla je popsána ve specifikaci 3GPP TS 23.003. Týká se pouze zařízení s kartami SIM.|
|udid|Jedinečný identifikátor zařízení: posloupnost 40 písmen a číslic. Je specifický pro zařízení iOS.|
|meid|Identifikátor mobilního zařízení: globálně jedinečné číslo identifikující fyzický kus zařízení mobilní stanice CDMA. Formát čísla je definován specifikací 3GPP2, zpráva S. R0048. V praxi však na ně lze nahlížet jako kód IMEI obsahující šestnáctkové číslice. Kód MEID má délku 56 bitů (14 šestnáctkových číslic). Sestává ze tří polí představujících 8bitový kód regionu (RR), 24bitový kód výrobce a 24bitové sériové číslo přiřazené výrobcem.|
|osVersion|Verze operačního systému daného zařízení.
|model|Model zařízení.
|manufacturer|Výrobce zařízení.
|azureDeviceId|ID zařízení po připojení pracovního místa k Azure AD. V případě nepřipojených zařízení bude použit prázdný identifikátor GUID.|
|lastContactTimeUtc|Datum a čas, kdy zařízení naposled navázalo kontakt se službou správy Intune.


## <a name="user-experience"></a>Činnost koncového uživatele

Když se uživatel pokusí o přístup k prostředkům z nezaregistrovaného zařízení, zobrazí se výzva k registraci, jako je například tato:

![Příklad výzvy k registraci](../media/cisco-ise-user-iphone.png)

Když uživatel zvolí registraci, bude přesměrován na proces registrace v Intune. Aspekty registrace uživatele pro Intune jsou popsány v těchto tématech:

- [Registrace zařízení s Androidem v Intune](/intune-user-help/enroll-your-device-in-Intune-android)</br>
- [Registrace zařízení s iOSem v Intune](/intune-user-help/enroll-your-device-in-intune-ios)</br>
- [Registrace zařízení s Mac OS X v Intune](/intune-user-help/enroll-your-device-in-intune-mac-os-x)</br>
- [Registrace zařízení s Windows v Intune](/intune-user-help/enroll-your-device-in-intune-windows)</br>

K dispozici je také [sada pokynů pro registraci ke stažení](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a), kterou můžete použít k vytvoření vlastních pokynů pro činnost uživatele.


### <a name="see-also"></a>Viz taky

[Příručka pro správce Cisco Identity Services Engine, vydání 2.1](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)
