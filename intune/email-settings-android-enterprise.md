---
title: Nastavení e-mailu s androidem Enterprise v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Vytvoření zařízení konfigurace e-mailové profily, které používají servery Exchange a načtení atributů z Azure Active Directory. Povolit protokol SSL nebo SMIME, ověřování uživatelů pomocí certifikátů nebo uživatelského jména a hesla a synchronizace e-mailu a plány na zařízení s pracovním profilem pomocí Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/10/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7e37d6a2b7371cf20cd36a6f3f75a4dd252c332f
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66048048"
---
# <a name="android-enterprise-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Nastavení zařízení s androidem Enterprise konfigurace e-mailu, ověřování a synchronizace v Intune

Tento článek uvádí a popisuje jinou e-mailovou nastaveních, pomocí kterých můžete řídit na zařízeních s Androidem Enterprise. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete nakonfigurovat e-mailový server, použijte protokol SSL k šifrování e-mailů a další.

Jako správce Intune můžete vytvořit a přiřadit nastavení e-mailu pro zařízení s Androidem Enterprise v pracovním profilu.

Další informace o e-mailové profily v Intune najdete v tématu [nakonfigurovat nastavení e-mailu](email-settings-configure.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](email-settings-configure.md#create-a-device-profile)a zvolte možnost pracovní profil.

## <a name="android-enterprise"></a>Android Enterprise

- **E-mailová aplikace**: Vyberte buď **Gmail** nebo **Nine Work**
- **E-mailový server**: Název hostitele serveru Exchange. Zadejte například `outlook.office365.com`.
- **Atribut uživatelského jména z AAD**: Tento název je atribut, který Intune získá od služby Azure Active Directory (Azure AD). Intune dynamicky vygeneruje uživatelské jméno, které tento profil používá. Možnosti:

  - **Hlavní název uživatele**: Získá název, jako například `user1` nebo `user1@contoso.com`
  - **Uživatelské jméno**: Získá pouze název, například `user1`

- **Atribut e-mailové adresy z AAD**: Tento název je atribut e-mailu, který Intune získá od služby Azure AD. Intune dynamicky generuje e-mailovou adresu, která používají tento profil. Možnosti:
  - **Hlavní název uživatele**:  Použije celý hlavní název, jako například `user1@contoso.com` nebo `user1`, jako e-mailovou adresu.
  - **Primární adresa SMTP**: Používá jako primární adresu SMTP, `user1@contoso.com`, pro přihlášení k systému Exchange.

- **Metoda ověřování**: Vyberte **uživatelské jméno a heslo** nebo **certifikáty** jako metodu ověřování používanou pro e-mailový profil.
  - Pokud vyberete **Certifikát**, vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení Exchange.
- **SSL**: Zvolte **povolit** používat vrstvy SSL (Secure Sockets) při posílání a přijímání e-mailů a komunikaci se serverem Exchange.
- **Počet e-mailů k synchronizaci**: Zvolte dobu e-mailů, které se mají synchronizovat. Nebo vyberte **Unlimited** chcete synchronizovat všechny dostupné e-maily.
- **Typ obsahu k synchronizaci** (jenom Nine Work): Vyberte, jaká data se mají na zařízeních synchronizovat. Možnosti:
  - **Kontakty**: Zvolte **povolit** umožňuje koncovým uživatelům synchronizovat kontakty, aby si svoje zařízení.
  - **Kalendář**: Zvolte **povolit** umožňuje koncovým uživatelům synchronizovat kalendář, který bude jejich zařízení.
  - **Úlohy**: Zvolte **povolit** umožňuje koncovým uživatelům k synchronizaci všech úloh se svými zařízeními.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit e-mailových profilů pro [Android Samsung Knox](email-settings-android.md), [iOS](email-settings-ios.md), [Windows 10 a novější](email-settings-windows-10.md), a [Windows Phone 8.1](email-settings-windows-phone-8-1.md) zařízení.
