---
title: Nastavení Outlooku pro zařízení s iOSem a Androidem v Microsoft Intune
description: Vytvořte zásady konfigurace, které nastaví Microsoft Outlook pro spuštění na zařízeních s iOSem a Androidem.
keywords: ''
author: Erikre
ms.author: erikre
ms.reviewer: smithre4
manager: dougeby
ms.date: 10/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 691029cc7b9fd8880c5440a84b95bbf2462920d6
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180319"
---
# <a name="microsoft-outlook-configuration-settings"></a>Nastavení konfigurace Microsoft Outlooku 

Použijte zásady konfigurace, které nastaví Microsoft Outlook pro spuštění na zařízeních s iOSem a Androidem. 

Pokud chcete vytvořit zásady konfigurace aplikací pro spravovaná zařízení s iOsem, podívejte se na téma [Přidání zásad konfigurace aplikací pro spravovaná zařízení s iOSem](app-configuration-policies-use-ios.md). Pokud chcete vytvořit zásady konfigurace aplikací pro spravovaná zařízení s Androidem, podívejte se na téma [Přidání zásad konfigurace aplikací pro spravovaná zařízení s Androidem](app-configuration-policies-use-android.md). 

## <a name="configuration-settings"></a>Nastavení konfigurace

Při přidávání zásad konfigurace v Intune můžete nastavit konkrétní nastavení pro konfiguraci Microsoft Outlooku. V podokně **Nastavení konfigurace** můžete nastavit konfiguraci e-mailového účtu.

### <a name="basic-authentication-email-account-settings"></a>Nastavení e-mailového účtu s využitím základního ověřování
Outlook pro iOS a Android nabízí správcům Exchange možnost „odeslat“ konfigurace účtů svým místním uživatelům, kteří využívají základní ověřování pomocí protokolu ActiveSync. Další informace najdete v tématu o [nastavení účtu v Outlooku pro iOS a Android s využitím základního ověřování](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/account-setup). Pokud chcete povolit konfiguraci nastavení účtu, můžete nakonfigurovat následující nastavení:

- **E-mailový server**: Zadejte název hostitele místního Exchange Serveru (např. mail.contoso.com).
- **Název e-mailového účtu**: Zadejte zobrazovaný název e-mailového účtu. Tento název se zobrazuje uživatelům na jejich zařízeních.
- **Atribut uživatelského jména z AAD**: Toto jméno je atribut, který Intune získá z Azure Active Directory (Azure AD). Intune dynamicky vygeneruje uživatelské jméno, které tento profil používá. Vaše možnosti jsou:
  - **Hlavní název uživatele**: Získá jméno, například `user1` nebo `user1@contoso.com`.
  - **Primární adresa SMTP**: Získá jméno ve formátu e-mailové adresy, například `user1@contoso.com`.
- **Atribut e-mailové adresy z AAD**: Zvolte, jak se generuje e-mailová adresa uživatele. Pokud chcete jako e-mailovou adresu použít úplný hlavní název, vyberte **Hlavní název uživatele** (`user1@contoso.com` nebo `user1`). Pokud chcete pro přihlášení k Exchange použít primární adresu SMTP, vyberte **Primární adresa SMTP** (`user1@contoso.com`). Doporučuje se vybrat možnost **Primární adresa SMTP**.
- **Doména účtu**: (volitelné) Doména účtu.

## <a name="next-steps"></a>Další postup
[Konfigurace nastavení e-mailu v Intune](email-settings-configure.md)

