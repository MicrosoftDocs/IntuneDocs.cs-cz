---
title: "Omezení přístup k sítím s Cisco ISE | Microsoft Intune"
description: "Použijte Cisco ISE s Intune, aby zařízení byla zaregistrovaná v Intune a vyhovovala zásadám, než se pokusí o přístup k WiFi a VPN řízeným Cisco ISE."
keywords: 
author: nbigman
manager: jeffgilb
ms.date: 06/24/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
translationtype: Human Translation
ms.sourcegitcommit: f33a86c51320c75ce74d20e0cac2b9581990ecec
ms.openlocfilehash: 78945498a951e7b897164ae6f33c4e87d521ca5b


---

# Použití Cisco ISE s Microsoft Intune
Integrace Intune s Cisco ISE umožňuje vytvářet zásady sítě v prostředí ISE na základě stavu registrace zařízení v Intune a jejich stavu dodržování předpisů. Prostřednictvím těchto zásad lze zajistit, aby byl přístup k síti vaší společnosti omezen na zařízení, která jsou spravována pomocí Intune a vyhovují zásadám Intune. 

## Konfigurace

Chcete-li tuto integraci povolit, nemusíte v tenantovi Intune provádět žádné nastavení. Bude třeba poskytnout oprávnění k serveru Cisco ISE pro přístup k tenantovi Intune. Zbývající část nastavení se potom provede na serveru Cisco ISE. Tento článek obsahuje pokyny pro poskytnutí oprávnění pro přístup k vašemu tenantovi Intune pro váš server ISE. 

### Krok 1: Správa certifikátů
1. V konzole Azure Active Directory (AAD) exportujte certifikát. 

    #### Internet Explorer 11
        
    a. Spusťte Internet Explorer jako správce a přihlaste se ke konzole AAD.
  
    b. Zvolte ikonu zámku na panelu Adresa a pak zvolte **Zobrazit certifikáty**.
    
    c. Na kartě **Podrobnosti** v rámci vlastností certifikátu zvolte **Kopírovat do souboru**.

    d. Na úvodní stránce **Průvodce exportem certifikátu** zvolte **Další**. 

    e. Na stránce **Formát souboru pro export** ponechte výchozí nastavení **Binární x.509, kódování DER (CER)** a zvolte **Další**.  

    f. Na stránce **Soubor k exportu** zvolte **Procházet**, vyberte umístění, do kterého chcete soubor uložit, a zadejte název souboru. Ačkoli se zdá, že vybíráte soubor pro export, ve skutečnosti pojmenováváte soubor, do kterého bude exportovaný certifikát uložen. Zvolte **Další** &gt; **Dokončit**.

    #### Safari
    
    a. Přihlaste se ke konzole AAD.

    b. Zvolte ikonu zámku &gt;  **Další informace**.
    
    c. Zvolte **Zobrazit certifikát** &gt; **Podrobnosti**.

    d. Zvolte certifikát a pak zvolte **Exportovat**.  


> [!IMPORTANT]
> Zkontrolujte datum vypršení platnosti certifikátu, protože po vypršení platnosti tohoto certifikátu bude třeba exportovat a importovat nový certifikát.

    

2. Z konzoly ISE importujte certifikát Intune (soubor, který jste exportovali) do úložiště **Důvěryhodné certifikáty**.
3. V konzole ISE přejděte do části **Správa** > **Certifikáty** > **Systémové certifikáty**.
4. Zvolte certifikát ISE a pak zvolte **Exportovat**.
5. V textovém editoru upravte exportovaný certifikát:
 - Odstraňte text: ** -----BEGIN CERTIFICATE-----**
 - Odstraňte text: ** -----END CERTIFICATE-----**
 - Ověřte, že veškerý text leží na jednom řádku.

### Krok 2: Vytvoření aplikace pro ISE ve vašem tenantovi AAD
1. V konzole Azure Active Directory (AAD) zvolte **Aplikace** > **Přidat aplikaci** > **Přidat aplikaci, kterou vyvíjí moje organizace**.
2. Zadejte název a adresu URL pro aplikaci. Adresou URL může být web vaší společnosti.
3. Stáhněte manifest aplikace (soubor JSON).
4. Upravte soubor JSON manifestu. V nastavení s názvem **keyCredentials** zadejte jako hodnotu nastavení upravený text certifikátu z kroku 1.
5. Uložte soubor beze změny jeho názvu.
6. Poskytněte své aplikaci oprávnění pro rozhraní API Microsoft Intune a Microsoft Graph.
    1. Pro Microsoft Graph vyberte následující:
        - **Oprávnění aplikací**: Čtení dat adresáře
        - **Delegovaná oprávnění**: 
            - Časově neomezený přístup k datům uživatele
          - Přihlášení uživatelů
   2. Pro rozhraní API Microsoft Intune v části **Oprávnění aplikací** zvolte **Zjistit stav zařízení a jeho stav dodržování předpisů z služby Intune**.

7. Zvolte **Zobrazit koncové body** a zkopírujte následující hodnoty pro použití při konfiguraci nastavení ISE:

|Hodnota v rámci portálu AAD|Odpovídající pole v rámci portálu ISE|
|-------------------|---------------------------------|
|Koncový bod rozhraní API pro Microsoft Azure AD Graph|Adresa URL pro automatické zjišťování|
|Koncový bod tokenu OAuth 2.0|Adresa URL pro vydávání tokenů|
|Aktualizace kódu s použitím ID klienta|ID klienta|


### Krok 3: Konfigurace nastavení ISE 
2. V konzole správce ISE zadejte tyto hodnoty nastavení: 
  - **Typ serveru**: Správce mobilních zařízení
  - **Typ ověřování**: OAuth – pověření klienta
  - **Automatické zjišťování**: Ano
  - **Adresa URL pro automatické zjišťování**: Zadejte hodnotu z kroku 1.
  - **ID klienta**: Zadejte hodnotu z kroku 1.
  - **Adresa URL pro vydávání tokenů**: Zadejte hodnotu z kroku 1.



## Informace sdílené mezi vaším tenantem Intune a vaším serverem Cisco ISE
Tato tabulka uvádí informace sdílené mezi vaším tenantem Intune a vaším serverem Cisco ISE pro zařízení, která jsou spravována pomocí Intune.

|Vlastnost|  Popis|
|---------------|------------------------------------------------------------|
|complianceState|   Pravda nebo nepravda (řetězec) určující, zda zařízení je nebo není vyhovující.|
|isManaged| Pravda nebo nepravda (určuje, zda klient je nebo není spravován pomocí Intune.|
|macAddress|Adresa MAC zařízení.|
|serialNumber|Sériové číslo zařízení. Týká se pouze zařízení s iOS.|
|imei|Kód IMEI (15 desítkových číslic: 14 číslic plus kontrolní číslice) nebo IMEISV (16 číslic) obsahuje informace o původu, modelu a sériovém čísle zařízení. Struktura kódu IMEI/SV je popsána ve specifikaci 3GPP TS 23.003. Týká se pouze zařízení s kartami SIM.)|
|udid|Jedinečný identifikátor zařízení: posloupnost 40 písmen a číslic specifická pro zařízení iOS.|
|meid|Identifikátor mobilního zařízení: globálně jedinečné číslo identifikující fyzickou část zařízení mobilní stanice CDMA. Formát čísla je definován specifikací 3GPP2, sestava S. R0048. V praxi však na ně lze nahlížet jako kód IMEI obsahující šestnáctkové číslice. Kód MEID má délku 56 bitů (14 šestnáctkových číslic). Sestává ze tří polí představujících 8bitový kód regionu (RR), 24bitový kód výrobce a 24bitové sériové číslo přiřazené výrobcem.| 
|osVersion| Verze operačního systému pro příslušné zařízení.
|model|Model zařízení.
|manufacturer|Výrobce zařízení.
|azureDeviceId| ID zařízení po připojení pracovního místa k Azure Active Directory. V případě nepřipojených zařízení bude použit prázdný identifikátor guid.|
|lastContactTimeUtc|Datum a čas, kdy zařízení naposled navázalo kontakt se službou správy Intune. 


## Činnost koncového uživatele

Když se uživatel pokusí o přístup k prostředkům z nezaregistrovaného zařízení, zobrazí se výzva k registraci, jako je například znázorněno zde:

![Příklad výzvy k registraci](../media/cisco-ise-user-iphone.png)

Když uživatel zvolí registraci, bude přesměrován na proces registrace v Intune. Aspekty registrace uživatele pro Intune jsou popsány v těchto tématech:

- [Registrace zařízení se systémem Android do Intune](/intune/end-user/enroll-your-device-in-Intune-android)</br>
- [Registrace zařízení se systémem iOS do Intune](/intune/end-user/enroll-your-device-in-intune-ios)</br>
- [Registrace zařízení se systémem Mac OS X v Intune](/intune/end-user/enroll-your-device-in-intune-mac-os-x)</br>
- [Registrace zařízení se systémem Windows do Intune](/intune/end-user/enroll-your-device-in-intune-windows)</br> 

K dispozici je také [sada pokynů pro registraci ke stažení](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a), kterou můžete použít k vytvoření vlastních pokynů pro činnost uživatele.


### Související témata

[Příručka pro správce Cisco Identity Services Engine, vydání 2.1](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)




<!--HONumber=Jun16_HO4-->


