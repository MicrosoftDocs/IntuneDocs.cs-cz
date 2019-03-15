---
title: Nastavení androidu e-mailu v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Vytvoření zařízení konfigurace e-mailové profily, které používají servery Exchange a načtení atributů z Azure Active Directory. Povolit protokol SSL nebo SMIME, ověřování uživatelů pomocí certifikátů nebo uživatelského jména a hesla a synchronizace e-mailu a plány na zařízeních s Androidem Samsung Knox v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 01/15/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 94f907ee8805c5f0559e8751a7cd69bacf1612ee
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57565499"
---
# <a name="android-device-settings-to-configure-email-authentication-and-synchronization-in-intune"></a>Nastavení zařízení s androidem v Intune nakonfigurovat e-mailu, ověřování a synchronizace

Tento článek uvádí a popisuje jinou e-mailovou nastaveních, pomocí kterých můžete řídit na zařízeních s Androidem Samsung Knox v Intune. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení můžete nakonfigurovat e-mailový server, použijte protokol SSL k šifrování e-mailů a další.

Jako správce Intune můžete vytvořit a přiřadit nastavení e-mailu pro zařízení s Androidem Samsung Knox Standard.

Další informace o e-mailové profily v Intune najdete v tématu [nakonfigurovat nastavení e-mailu](email-settings-configure.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](email-settings-configure.md#create-a-device-profile).

## <a name="android-samsung-knox"></a>Android (Samsung Knox)

- **E-mailový server**: Zadejte název hostitele vašeho Exchange serveru. Zadejte například `outlook.office365.com`.
- **Název účtu**: Zadejte zobrazovaný název e-mailový účet. Tento název se zobrazuje uživatelům na jejich zařízeních.
- **Atribut uživatelského jména z AAD**: Tento název je atribut, který Intune získá od služby Azure Active Directory (Azure AD). Intune dynamicky vygeneruje uživatelské jméno, které tento profil používá. Možnosti:
  - **Hlavní název uživatele**: Získá název, jako například `user1` nebo `user1@contoso.com`
  - **Uživatelské jméno**: Získá pouze název, například `user1`
  - **sAM název účtu**: Vyžaduje domény, jako například `domain\user1`. název účtu sAM se používá pouze pro zařízení s Androidem.

    Dále zadejte:  
    - **Zdroj názvu domény uživatele**: Zvolte **AAD** (Azure Active Directory) nebo **vlastní**.

      Pokud se rozhodnete získat atributy ze služby **AAD**, zadejte:
      - **Atribut názvu domény uživatele z AAD**: Zvolte zobrazíte **úplným názvem domény** nebo **název pro rozhraní NetBIOS** atribut uživatele

      Pokud se rozhodnete použít **Vlastní** atributy, zadejte:
      - **Název vlastní domény pro použití**: Zadejte hodnotu, která Intune používá pro název domény, jako například `contoso.com` nebo `contoso`

- **Atribut e-mailové adresy z AAD**: Tento název je atribut e-mailu, který Intune získá od služby Azure AD. Intune dynamicky generuje e-mailovou adresu, která používají tento profil. Možnosti:
  - **Hlavní název uživatele**:  Použije celý hlavní název, jako například `user1@contoso.com` nebo `user1`, jako e-mailovou adresu.
  - **Primární adresa SMTP**: Používá jako primární adresu SMTP, `user1@contoso.com`, pro přihlášení k systému Exchange.

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
  - **Kontakty**: Zvolte **povolit** umožňuje koncovým uživatelům synchronizovat kontakty, aby si svoje zařízení.
  - **Kalendář**: Zvolte **povolit** umožňuje koncovým uživatelům synchronizovat kalendář, který bude jejich zařízení.
  - **Úlohy**: Zvolte **povolit** umožňuje koncovým uživatelům k synchronizaci všech úloh se svými zařízeními.

## <a name="next-steps"></a>Další postup

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete také vytvořit e-mailových profilů pro [Android Enterprise – pracovní profil](email-settings-android-enterprise.md), [iOS](email-settings-ios.md), [Windows 10 a novější](email-settings-windows-10.md), a [Windows Phone 8.1](email-settings-windows-phone-8-1.md).
