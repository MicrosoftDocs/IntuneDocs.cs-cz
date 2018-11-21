---
title: Nastavení e-mailu v zařízeních s Androidem a pracovním profilem Androidu v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte e-mailový profil konfigurace zařízení, který používá servery Exchange a načítá atributy ze služby Azure Active Directory. Pomocí Microsoft Intune můžete také povolit protokol SSL nebo SMIME, ověřovat uživatele certifikáty nebo uživatelským jménem a heslem a synchronizovat e-maily a plány na zařízeních s Androidem a pracovním profilem Androidu.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b8ab8dfadb113d81922119a54aefcac43d15b5a1
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52187425"
---
# <a name="email-profile-settings-for-devices-running-android-and-android-enterprise---intune"></a>Nastavení e-mailového profilu v zařízeních s Androidem a Androidem Enterprise – Intune

Pomocí nastavení e-mailového profilu můžete konfigurovat zařízení s Androidem.

Jako správce Intune můžete vytvořit a přiřadit nastavení e-mailu pro následující zařízení s Androidem:

- Android Samsung Knox Standard
- Android Enterprise

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **E-mailový server**: Zadejte název hostitele vašeho Exchange serveru.
- **Název účtu**: Zadejte zobrazovaný název e-mailového účtu. Tento název se zobrazuje uživatelům na jejich zařízeních.
- **Atribut uživatelského jména z AAD**: Toto jméno je atribut, který Intune získá od služby Azure Active Directory (AAD). Intune dynamicky vygeneruje uživatelské jméno, které tento profil používá. Možnosti:
  - **Hlavní název uživatele**: Získá jméno, například `user1` nebo `user1@contoso.com`.
  - **Uživatelské jméno**: Získá jen jméno, například `user1`.
  - **Název účtu SAM**: Vyžaduje doménu, například `domain\user1`. Název účtu SAM lze použít jen u zařízení s Androidem. Android Enterprise není podporovaný.

    Dále zadejte:  
    - **Zdroj názvu domény uživatele**: Zvolte **AAD** (Azure Active Directory) nebo **Vlastní**.

      Pokud se rozhodnete získat atributy ze služby **AAD**, zadejte:
      - **Atribut názvu domény uživatele z AAD**: Zvolte, jestli se má získat atribut **Úplný název domény** nebo **Název NetBIOS** uživatele.

      Pokud se rozhodnete použít **Vlastní** atributy, zadejte:
      - **Vlastní název domény, který se má použít**: Zadejte hodnotu, kterou Intune používá pro název domény, například `contoso.com` nebo `contoso`.

- **Atribut e-mailové adresy z AAD**: Zvolte, jak se generuje e-mailová adresa uživatele. Pokud chcete jako e-mailovou adresu použít úplný hlavní název, vyberte **Hlavní název uživatele** (`user1@contoso.com` nebo `user1`). Pokud chcete pro přihlášení k Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP** (`user1@contoso.com`).

- **Metoda ověřování**: Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**.
  - Pokud vyberete **Certifikát**, vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení Exchange.

### <a name="security-settings"></a>Nastavení zabezpečení

- **SSL**: Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).
- **S/MIME**: Odchozí e-maily se budou posílat s využitím šifrování S/MIME.
  - Pokud vyberete **Certifikát**, vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení Exchange.

### <a name="synchronization-settings"></a>Nastavení synchronizace

- **Počet e-mailů k synchronizaci**: Zvolte počet dní, za které se mají e-maily synchronizovat, nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Plán synchronizace**: Vyberte plán, podle kterého zařízení synchronizují data z Exchange serveru. Můžete také vybrat **Při doručování zpráv**, aby se data synchronizovala po doručení, nebo **Ruční**, aby musel synchronizaci zahájit uživatel zařízení.

### <a name="content-sync-settings"></a>Nastavení synchronizace obsahu

- **Typ obsahu k synchronizaci**: Vyberte typy obsahu, které se mají na zařízeních synchronizovat:
  - **Kontakty**
  - **Kalendář**
  - **Úkoly**

## <a name="android-enterprise"></a>Android Enterprise

- **E-mailová aplikace**: Vyberte **Gmail** nebo **Nine Work**.
- **E-mailový server**: Název hostitele vašeho Exchange serveru.
- **Atribut uživatelského jména z AAD**: Toto jméno je atribut ve službě Active Directory (AD) nebo Azure AD, který se použije k vygenerování uživatelského jména pro tento e-mailový profil. Vyberte **Primární adresa SMTP**, třeba user1@contoso.com, nebo **Hlavní název uživatele**, třeba uživatel1 nebo user1@contoso.com.
- **Atribut e-mailové adresy z AAD**: Způsob generování e-mailové adresy pro uživatele na každém zařízení. Pokud chcete jako e-mailovou adresu nebo **uživatelské jméno** používat celý hlavní název, vyberte **Hlavní název uživatele**.
- **Metoda ověřování**: Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**.
  - Pokud jste vybrali **Certifikát**, vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení Exchange.
- **SSL**: Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).
- **Počet e-mailů k synchronizaci**: Zvolte počet dní, za které se mají e-maily synchronizovat, nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Typ obsahu k synchronizaci** (jen Nine Work): Vyberte typy obsahu, které se mají na zařízeních synchronizovat:
  - **Kontakty**
  - **Kalendář**
  - **Úkoly**

## <a name="next-steps"></a>Další postup
[Konfigurace nastavení e-mailu v Intune](email-settings-configure.md)
