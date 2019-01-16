---
title: Android & nastavení e-mailu s Androidem Enterprise v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Vytvoření zařízení konfigurace e-mailové profily, které používají servery Exchange a načtení atributů z Azure Active Directory. Povolit protokol SSL nebo SMIME, ověřování uživatelů pomocí certifikátů nebo uživatelského jména a hesla a synchronizace e-mailu a plány na Android a Android pracovní profil zařízení pomocí Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/15/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.openlocfilehash: b96363d679a6f09327bf9a1b46421e786d1956a8
ms.sourcegitcommit: 912aee714432c4a1e8efeee253ca2be4f972adaa
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/15/2019
ms.locfileid: "54316878"
---
# <a name="android-and-android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Nastavení pro zařízení s Androidem Enterprise konfigurace e-mailu, ověřování a synchronizace v Intune a Android

Tento článek uvádí a popisuje jinou e-mailovou nastaveních, pomocí kterých můžete řídit na zařízeních s Androidem a s Androidem Enterprise. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete nakonfigurovat e-mailový server, použijte protokol SSL k šifrování e-mailů a další.

Jako správce Intune můžete vytvořit a přiřadit nastavení e-mailu pro následující zařízení s Androidem:

- Android Samsung Knox Standard
- Android Enterprise

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](email-settings-configure.md).

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **E-mailový server**: Zadejte název hostitele vašeho Exchange serveru.
- **Název účtu**: Zadejte zobrazovaný název e-mailový účet. Tento název se zobrazuje uživatelům na jejich zařízeních.
- **Atribut uživatelského jména z AAD**: Tento název je atribut, který Intune získá z Azure Active Directory (AAD). Intune dynamicky vygeneruje uživatelské jméno, které tento profil používá. Možnosti:
  - **Hlavní název uživatele**: Získá název, jako například `user1` nebo `user1@contoso.com`
  - **Uživatelské jméno**: Získá pouze název, například `user1`
  - **sAM název účtu**: Vyžaduje domény, jako například `domain\user1`. Název účtu SAM lze použít jen u zařízení s Androidem. Android Enterprise není podporovaný.

    Dále zadejte:  
    - **Zdroj názvu domény uživatele**: Zvolte **AAD** (Azure Active Directory) nebo **vlastní**.

      Pokud se rozhodnete získat atributy ze služby **AAD**, zadejte:
      - **Atribut názvu domény uživatele z AAD**: Zvolte zobrazíte **úplným názvem domény** nebo **název pro rozhraní NetBIOS** atribut uživatele

      Pokud se rozhodnete použít **Vlastní** atributy, zadejte:
      - **Název vlastní domény pro použití**: Zadejte hodnotu, která Intune používá pro název domény, jako například `contoso.com` nebo `contoso`

- **Atribut e-mailové adresy z AAD**: Vyberte způsob generování e-mailovou adresu uživatele. Pokud chcete jako e-mailovou adresu použít úplný hlavní název, vyberte **Hlavní název uživatele** (`user1@contoso.com` nebo `user1`). Pokud chcete pro přihlášení k Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP** (`user1@contoso.com`).

- **Metoda ověřování**: Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**.
  - Pokud vyberete **Certifikát**, vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení Exchange.

### <a name="security-settings"></a>Nastavení zabezpečení

- **SSL**: Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).
- **S/MIME**: Posílá odchozí poštu s šifrováním S/MIME.
  - Pokud vyberete **Certifikát**, vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení Exchange.

### <a name="synchronization-settings"></a>Nastavení synchronizace

- **Počet e-mailů k synchronizaci**: Zvolte počet dní e-mailu, který chcete synchronizovat, nebo vyberte **Unlimited** chcete synchronizovat všechny dostupné e-maily.
- **Plán synchronizace**: Vyberte plán, zařízení, synchronizovat data z Exchange serveru. Můžete také vybrat **Při doručování zpráv**, aby se data synchronizovala po doručení, nebo **Ruční**, aby musel synchronizaci zahájit uživatel zařízení.

### <a name="content-sync-settings"></a>Nastavení synchronizace obsahu

- **Typ obsahu k synchronizaci**: Vyberte typy obsahu, které se mají na zařízeních synchronizovat. **Není nakonfigurováno** toto nastavení zakáže. Pokud je nastavena na **Nenakonfigurováno**, pokud synchronizaci koncového uživatele umožňuje na zařízení, synchronizace je zakázaná, znovu když synchronizuje zařízení v Intune, protože posílit zásady. 

  Můžete synchronizovat následujícím obsahem: 
  - **Kontakty**
  - **Kalendář**
  - **Úkoly**

## <a name="android-enterprise"></a>Android Enterprise

- **E-mailová aplikace**: Vyberte buď **Gmail** nebo **Nine Work**
- **E-mailový server**: Název hostitele serveru Exchange.
- **Atribut uživatelského jména z AAD**: Tento název je atribut v Active Directory (AD) nebo Azure AD, který se používá k vygenerování uživatelského jména pro tento e-mailový profil. Vyberte **Primární adresa SMTP**, třeba user1@contoso.com, nebo **Hlavní název uživatele**, třeba uživatel1 nebo user1@contoso.com.
- **Atribut e-mailové adresy z AAD**: Způsob generování e-mailové adresy uživatele na každém zařízení. Pokud chcete jako e-mailovou adresu nebo **uživatelské jméno** používat celý hlavní název, vyberte **Hlavní název uživatele**.
- **Metoda ověřování**: Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**.
  - Pokud jste vybrali **Certifikát**, vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení Exchange.
- **SSL**: Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).
- **Počet e-mailů k synchronizaci**: Zvolte počet dní e-mailu, který chcete synchronizovat, nebo vyberte **Unlimited** chcete synchronizovat všechny dostupné e-maily.
- **Typ obsahu k synchronizaci** (jenom Nine Work): Vyberte typy obsahu, které se mají na zařízeních synchronizovat. **Není nakonfigurováno** toto nastavení zakáže. Pokud je nastavena na **Nenakonfigurováno**, pokud synchronizaci koncového uživatele umožňuje na zařízení, synchronizace je zakázaná, znovu když synchronizuje zařízení v Intune, protože posílit zásady. 

  Můžete synchronizovat následujícím obsahem: 
  - **Kontakty**
  - **Kalendář**
  - **Úkoly**

## <a name="next-steps"></a>Další postup
[Konfigurace nastavení e-mailu v Intune](email-settings-configure.md)
