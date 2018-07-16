---
title: Nastavení e-mailu pro zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte e-mailový profil konfigurace zařízení, který používá servery Exchange a načítá atributy ze služby Azure Active Directory. Pomocí Microsoft Intune můžete na zařízeních s Windows 10 také povolit protokol SSL a synchronizovat e-maily a plány.
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
ms.openlocfilehash: 04834f21e5fd2f6ed0f7454988936397d3249987
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/07/2018
ms.locfileid: "37904964"
---
# <a name="email-profile-settings-for-devices-running-windows-10---intune"></a>Nastavení e-mailového profilu pro zařízení s Windows 10 – Intune

Pomocí nastavení e-mailového profilu můžete konfigurovat zařízení s Windows 10.

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

## <a name="security-settings"></a>Nastavení zabezpečení

- **SSL**: Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).

## <a name="synchronization-settings"></a>Nastavení synchronizace

- **Počet e-mailů k synchronizaci**: Zvolte počet dní, za které se mají e-maily synchronizovat. Nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Plán synchronizace**: Vyberte pro zařízení plán synchronizace dat z Exchange serveru. Můžete také vybrat **Při doručení zprávy**, kdy se data budou synchronizovat při doručení, nebo **Ručně**, kdy musí synchronizaci zahájit uživatel zařízení.

## <a name="content-sync-settings"></a>Nastavení synchronizace obsahu

- **Typ obsahu k synchronizaci**: Vyberte typy obsahu, které se mají na zařízeních synchronizovat:
  - **Kontakty**
  - **Kalendář**
  - **Úkoly**

## <a name="next-steps"></a>Další kroky
[Konfigurace nastavení e-mailu v Intune](email-settings-configure.md)