---
title: Nastavení e-mailu pro zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte e-mailový profil konfigurace zařízení, který používá servery Exchange a načítá atributy ze služby Azure Active Directory. Pomocí Microsoft Intune můžete na zařízeních s Windows 10 také povolit protokol SSL a synchronizovat e-maily a plány.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/29/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a631ff93ed135ebbf389059c08f52b3df90e4295
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55838933"
---
# <a name="email-profile-settings-for-devices-running-windows-10---intune"></a>Nastavení e-mailového profilu pro zařízení s Windows 10 – Intune

E-mailového profilu můžete nakonfigurovat e-mailové aplikace na zařízení s Windows 10.

- **E-mailový server**: Zadejte název hostitele vašeho Exchange serveru.
- **Název účtu**: Zadejte zobrazovaný název e-mailový účet. Tento název se zobrazuje uživatelům na jejich zařízeních.
- **Atribut uživatelského jména z AAD**: Tento název je atribut, který Intune získá z Azure Active Directory (AAD). Intune dynamicky vygeneruje uživatelské jméno, které tento profil používá. Možnosti:
  - **Hlavní název uživatele**: Získá název, jako například `user1` nebo `user1@contoso.com`
  - **Primární adresa SMTP**: Získá název ve formátu e-mailové adresy, jako například `user1@contoso.com`
  - **sAM název účtu**: Vyžaduje domény, jako například `domain\user1`.

    Dále zadejte:  
    - **Zdroj názvu domény uživatele**: Zvolte **AAD** (Azure Active Directory) nebo **vlastní**.

      Pokud se rozhodnete získat atributy ze služby **AAD**, zadejte:
      - **Atribut názvu domény uživatele z AAD**: Zvolte zobrazíte **úplným názvem domény** nebo **název pro rozhraní NetBIOS** atribut uživatele

      Pokud se rozhodnete použít **Vlastní** atributy, zadejte:
      - **Název vlastní domény pro použití**: Zadejte hodnotu, která Intune používá pro název domény, jako například `contoso.com` nebo `contoso`

- **Atribut e-mailové adresy z AAD**: Vyberte způsob generování e-mailovou adresu uživatele. Pokud chcete jako e-mailovou adresu použít úplný hlavní název, vyberte **Hlavní název uživatele** (`user1@contoso.com` nebo `user1`). Pokud chcete pro přihlášení k Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP** (`user1@contoso.com`).

## <a name="security-settings"></a>Nastavení zabezpečení

- **SSL**: Při posílání a přijímání e-mailů a komunikaci se serverem Exchange se použije komunikace SSL (Secure Sockets Layer).

## <a name="synchronization-settings"></a>Nastavení synchronizace

- **Počet e-mailů k synchronizaci**: Zvolte počet dní e-mailu, který chcete synchronizovat. Nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Plán synchronizace**: Vyberte plán, zařízení, synchronizovat data z Exchange serveru, můžete také vybrat **při doručování zpráv**, který synchronizuje data ihned po doručení, nebo **ruční**, kde uživatel zařízení musel synchronizaci zahájit.

## <a name="content-sync-settings"></a>Nastavení synchronizace obsahu

- **Typ obsahu k synchronizaci**: Vyberte typy obsahu, které chcete na zařízeních synchronizovat:
  - **Kontakty**
  - **Kalendář**
  - **Úkoly**

## <a name="next-steps"></a>Další postup
[Konfigurace nastavení e-mailu v Intune](email-settings-configure.md)
