---
title: Nastavení e-mailu pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte e-mailový profil konfigurace zařízení, který používá servery Exchange a načítá atributy ze služby Azure Active Directory. Pomocí Microsoft Intune můžete na zařízeních s iOSem také povolit protokol SSL, ověřovat uživatele certifikáty nebo uživatelským jménem a heslem a synchronizovat e-maily.
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
ms.custom: intune-azure
ms.openlocfilehash: 3a231adf4e1f5687bc88c8c9b15241d3f89e711d
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905327"
---
# <a name="email-profile-settings-for-ios-devices---intune"></a>Nastavení e-mailového profilu na zařízeních s iOSem – Intune

Pomocí nastavení e-mailového profilu můžete konfigurovat zařízení s iOSem.

## <a name="email-settings"></a>Nastavení e-mailu

- **E-mailový server**: Zadejte název hostitele vašeho Exchange serveru.
- **Název účtu**: Zadejte zobrazovaný název e-mailového účtu. Tento název se zobrazuje uživatelům na jejich zařízeních.
- **Atribut uživatelského jména z AAD**: Toto jméno je atribut, který Intune získá od služby Azure Active Directory (AAD). Intune dynamicky vygeneruje uživatelské jméno, které tento profil používá. Možnosti:
  - **Hlavní název uživatele**: Získá jméno, například `user1` nebo `user1@contoso.com`.
  - **Primární adresa SMTP**: Získá jméno ve formátu e-mailové adresy, například `user1@contoso.com`.
  - **Název účtu SAM**: Vyžaduje doménu, například `domain\user1`.

    Dále zadejte:  
    - **Zdroj názvu domény uživatele**: Zvolte **AAD** (Azure Active Directory) nebo **Vlastní**.

      Pokud se rozhodnete získat atributy ze služby **AAD**, zadejte:
      - **Atribut názvu domény uživatele z AAD**: Zvolte, jestli se má získat atribut **Úplný název domény** nebo **Název NetBIOS** uživatele.

      Pokud se rozhodnete použít **Vlastní** atributy, zadejte:
      - **Vlastní název domény, který se má použít**: Zadejte hodnotu, kterou Intune používá pro název domény, například `contoso.com` nebo `contoso`.

- **Atribut e-mailové adresy z AAD**: Zvolte, jak se generuje e-mailová adresa uživatele. Pokud chcete jako e-mailovou adresu použít úplný hlavní název, vyberte **Hlavní název uživatele** (`user1@contoso.com` nebo `user1`). Pokud chcete pro přihlášení k Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP** (`user1@contoso.com`).
- **Metoda ověřování**: Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**. Vícefaktorové ověřování Azure není podporované.
  - Pokud jste vybrali **Certifikát**, vyberte profil klienta SCEP nebo PKCS, který jste dříve vytvořili a který se použije k ověření připojení Exchange.
- **SSL**: Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).
- **S/MIME**: Odchozí e-maily se budou posílat s podpisovým certifikátem S/MIME.
  - Pokud jste vybrali **Certifikát**, vyberte profil certifikátu PKCS, který jste dříve vytvořili za účelem ověřování připojení Exchange.
- **Počet e-mailů k synchronizaci**: Zvolte počet dní, za které se mají e-maily synchronizovat. Nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Povolit přesouvání zpráv do jiných e-mailových účtů**: Umožňuje uživatelům přesunovat e-mailové zprávy mezi různými účty, které si na svých zařízeních nakonfigurovali.
- **Umožnit posílání e-mailů z aplikací třetích stran**: Umožňuje uživateli, aby tento profil vybral jako výchozí účet pro posílání e-mailů, a povolí aplikacím třetích stran otevírání e-mailů v nativních e-mailových aplikacích, například k připojování souborů k e-mailům.
- **Synchronizovat nedávno použité e-mailové adresy**: Umožňuje uživatelům synchronizovat se serverem seznam e-mailových adres, které se na zařízení nedávno používaly.

## <a name="next-steps"></a>Další kroky
[Konfigurace nastavení e-mailu v Intune](email-settings-configure.md)
