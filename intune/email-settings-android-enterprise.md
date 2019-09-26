---
title: Nastavení e-mailu pro Android Enterprise v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte e-mailové profily konfigurace zařízení, které používají Exchange servery, a načtěte atributy z Azure Active Directory. Povolení SSL nebo SMIME, ověřování uživatelů pomocí certifikátů nebo uživatelského jména a hesla a synchronizace e-mailů a plánů na zařízeních s pracovním profilem Androidu pomocí Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/07/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.reviewer: maholdaa
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8e13c2dce5e8da2ce71b97de496d5234096c3b22
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "71301951"
---
# <a name="android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Nastavení zařízení s Androidem Enterprise pro konfiguraci e-mailu, ověřování a synchronizace v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek obsahuje seznam a popis různých nastavení e-mailů, která můžete řídit na zařízeních s Androidem Enterprise. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete nakonfigurovat e-mailový server, použijte protokol SSL k šifrování e-mailů a další.

Jako správce Intune můžete v pracovním profilu vytvořit a přiřadit nastavení e-mailu pro zařízení s Androidem Enterprise.

Další informace o e-mailových profilech v Intune najdete v tématu [Konfigurace nastavení e-mailu](email-settings-configure.md).

## <a name="before-you-begin"></a>Před zahájením

Vytvořte [profil konfigurace zařízení](email-settings-configure.md#create-a-device-profile) (vyberte pracovní profil) nebo vytvořte [zásadu konfigurace aplikace](app-configuration-policies-use-android.md).

## <a name="android-enterprise"></a>Android Enterprise

- **E-mailová aplikace**: Vyberte buď **Gmail** , nebo **devět práce** .
- **E-mailový server**: Název hostitele vašeho Exchange serveru. Zadejte například `outlook.office365.com`.
- **Atribut uživatelského jména z AAD**: Tento název je atribut Intune získává z Azure Active Directory (Azure AD). Intune dynamicky vygeneruje uživatelské jméno, které tento profil používá. Možnosti:

  - **Hlavní název uživatele**: Získá název, například `user1` nebo.`user1@contoso.com`
  - **Uživatelské jméno**: Získá pouze název, například`user1`

- **Atribut e-mailové adresy z AAD**: Tento název je atribut e-mailu, který Intune získá z Azure AD. Intune dynamicky generuje e-mailovou adresu, kterou používá tento profil. Možnosti:
  - **Hlavní název uživatele**:  Jako e-mailová adresa používá úplný `user1@contoso.com` hlavní `user1`název, jako je například nebo.
  - **Primární adresa SMTP**: K přihlášení k Exchangi používá primární adresu SMTP `user1@contoso.com`, třeba.

- **Metoda ověřování**: Jako metodu ověřování používanou e-mailovým profilem vyberte **uživatelské jméno a heslo** nebo **certifikáty** .
  - Pokud vyberete **Certifikát**, vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení Exchange.
- **SSL**: Vyberte možnost **Povolit** , pokud chcete při posílání e-mailů, přijímání e-mailů a komunikaci s Exchange serverem používat komunikaci SSL (Secure SOCKETS Layer) (SSL).
- **Velikost e-mailu, který se má synchronizovat**: Vyberte dobu, po kterou chcete synchronizovat e-mail. Případně můžete vybrat možnost **neomezeno** a synchronizovat všechny dostupné e-maily.
- **Typ obsahu, který se má synchronizovat** (Jenom devět práce): Vyberte, která data chcete na zařízeních synchronizovat. Možnosti:
  - **Kontakty**: Zvolením možnosti **Povolit** koncovým uživatelům umožníte synchronizaci kontaktů s jejich zařízeními.
  - **Kalendář**: Zvolením možnosti **Povolit** koncovým uživatelům umožníte synchronizaci kalendáře s jejich zařízeními.
  - **Úkoly**: Zvolením možnosti **Povolit** koncovým uživatelům umožníte synchronizaci všech úkolů s jejich zařízeními.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit e-mailové profily pro zařízení se systémem [Android Samsung KNOX](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 a novějším](email-settings-windows-10.md)a [Windows Phone 8,1](email-settings-windows-phone-8-1.md) .
