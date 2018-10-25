---
title: Nastavení Outlooku pro zařízení s iOSem a Androidem v Microsoft Intune
description: Vytvořte zásady konfigurace, které nastaví Microsoft Outlook pro spuštění na zařízeních s iOSem a Androidem.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7fc9f34bbd3d14ac4291582247b1e45169c2cccc
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2018
ms.locfileid: "48828726"
---
# <a name="microsoft-outlook-configuration-settings"></a>Nastavení konfigurace Microsoft Outlooku 

Použijte zásady konfigurace, které nastaví Microsoft Outlook pro spuštění na zařízeních s iOSem a Androidem. 

Pokud chcete vytvořit zásady konfigurace aplikací pro spravovaná zařízení s iOsem, podívejte se na téma [Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOSem](app-configuration-policies-use-ios.md). Pokud chcete vytvořit zásady konfigurace aplikací pro spravovaná zařízení s Androidem, podívejte se na téma [Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem](app-configuration-policies-use-android.md). 

## <a name="configuration-settings"></a>Nastavení konfigurace

Při přidávání zásad konfigurace v Intune můžete nastavit konkrétní nastavení pro konfiguraci Microsoft Outlooku. V podokně **Nastavení konfigurace** můžete nastavit konfiguraci e-mailového účtu.

### <a name="email-account-settings"></a>Nastavení e-mailového účtu

Následující nastavení konfigurace jsou specifická pro Microsoft Outlook.

- **E-mailový server**: Zadejte název hostitele vašeho Exchange serveru.
- **Název e-mailového účtu**: Zadejte zobrazovaný název e-mailového účtu. Tento název se zobrazuje uživatelům na jejich zařízeních.
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
- **Doména účtu**: (volitelné) Doména účtu.

## <a name="next-steps"></a>Další kroky
[Konfigurace nastavení e-mailu v Intune](email-settings-configure.md)

