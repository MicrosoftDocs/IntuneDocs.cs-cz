---
title: Konfigurace nastavení e-mailu pro zařízení s iOS v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení e-mailu, která můžete nakonfigurovat a přidat do zařízení se systémem iOS v Microsoft Intune, včetně použití serverů Exchange a získání atributů z Azure Active Directory. Můžete taky povolit SSL, ověřovat uživatele pomocí certifikátů nebo uživatelského jména a hesla a synchronizovat e-mail na zařízeních s iOS pomocí profilů konfigurace zařízení v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/05/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8fa0a7edd1782cd3eae725e6adf0af867e0f3727
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71301929"
---
# <a name="add-e-mail-settings-for-ios-devices-in-microsoft-intune"></a>Přidání nastavení e-mailu pro zařízení s iOS v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

V Microsoft Intune můžete vytvořit a nakonfigurovat e-mail pro připojení k e-mailovému serveru, zvolit způsob ověřování uživatelů, použít S/MIME pro šifrování a další.

V tomto článku najdete seznam všech nastavení e-mailu, která jsou dostupná pro zařízení s iOS. Můžete vytvořit konfigurační profil zařízení, který bude nabízet nebo nasazovat tato nastavení e-mailu do zařízení s iOS.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](email-settings-configure.md).

> [!NOTE]
> Tato nastavení jsou k dispozici pro všechny typy registrace. Další informace o typech registrace najdete v tématu Registrace zařízení se [systémem iOS](ios-enroll.md).

## <a name="email-settings"></a>Nastavení e-mailu

- **E-mailový server**: Zadejte název hostitele vašeho Exchange serveru.
- **Název účtu**: Zadejte zobrazovaný název e-mailového účtu. Tento název se zobrazuje uživatelům na jejich zařízeních.
- **Atribut uživatelského jména z AAD**: Tento název je atribut Intune získá z Azure Active Directory (AAD). Intune dynamicky vygeneruje uživatelské jméno, které tento profil používá. Možnosti:
  - **Hlavní název uživatele**: Získá název, například `user1` nebo.`user1@contoso.com`
  - **Primární adresa SMTP**: Získá název ve formátu e-mailové adresy, například`user1@contoso.com`
  - **název účtu SAM**: Vyžaduje doménu, třeba `domain\user1`.

    Dále zadejte:  
    - **Zdroj názvu domény uživatele**: Vyberte **AAD** (Azure Active Directory) nebo **vlastní**.

      Pokud se rozhodnete získat atributy ze služby **AAD**, zadejte:
      - **Atribut názvu domény uživatele z AAD**: Vyberte, chcete-li získat **úplný název domény** nebo atribut **názvu NetBIOS** pro uživatele.

      Pokud se rozhodnete použít **Vlastní** atributy, zadejte:
      - **Vlastní název domény, který se má použít**: Zadejte hodnotu, kterou Intune používá pro název domény, například `contoso.com` nebo.`contoso`

- **Atribut e-mailové adresy z AAD**: Vyberte způsob generování e-mailové adresy uživatele. Pokud chcete jako e-mailovou adresu použít úplný hlavní název, vyberte **Hlavní název uživatele** (`user1@contoso.com` nebo `user1`). Pokud chcete pro přihlášení k Exchangi použít primární adresu SMTP, vyberte **Primární adresa SMTP** (`user1@contoso.com`).
- **Metoda ověřování**: Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**. Vícefaktorové ověřování Azure není podporované.
  - Pokud jste vybrali **Certifikát**, vyberte profil klienta SCEP nebo PKCS, který jste dříve vytvořili a který se použije k ověření připojení Exchange.
- **SSL**: Při posílání e-mailů, přijímání e-mailů a komunikaci se serverem Exchange **umožňuje povolit** použití SSL (Secure SOCKETS Layer) (SSL).
- **OAuth**: Při odesílání e-mailů, přijímání e-mailů a komunikaci se serverem Exchange **povoluje** použití komunikace Open Authorization (OAuth). Pokud server OAuth používá ověřování certifikátem, u možnosti **Metoda ověřování** zvolte **Certifikát** a zahrňte do profilu příslušný certifikát. V opačném případě u možnosti **Metoda ověřování** zvolte **Uživatelské jméno a heslo**. Při použití OAuth mějte na paměti tyto skutečnosti:

  - Před zacílením tohoto profilu na uživatele potvrďte, že vaše e-mailové řešení podporuje OAuth. Office 365 se službou Exchange Online podporuje OAuth. Místní Exchange a jiná řešení od partnerů nebo třetích stran nemusí OAuth podporovat. U místního Exchange je možné nakonfigurovat moderní ověřování (viz příspěvek blogu s [oznámením hybridního moderního ověřování pro místní Exchange](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/)).

    Pokud e-mailový profil používá Oauth a e-mailová služba ho nepodporuje, bude se možnost **Zadejte heslo znovu** jevit jako nefunkční. Když například uživatel vybere možnost **Zadejte heslo znovu** v nastavení zařízení Apple, nic se nestane.

  - Při povoleném OAuth mají koncoví uživatelé jiné prostředí přihlašování k e-mailu s moderním ověřováním, které podporuje vícefaktorové ověřování. 

  - Některé organizace zakazují koncovým uživatelům možnost [samoobslužného přístupu k aplikacím](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). V této situaci může přihlášení s moderním ověřováním selhat, dokud správce nevytvoří podnikovou aplikaci „Účty iOS“ a neudělí uživatelům k této aplikaci přístup ve službě Azure AD.

    Výchozí akcí je přidání aplikace pomocí funkce **Přidat aplikaci** na [přístupovém panelu aplikace](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **bez schválení organizací**. Další informace najdete v článku o [přiřazení uživatelů k aplikacím](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > Když povolíte OAuth, stane se následující:  
  > 1. Zařízením, která už jsou zacílená, se vystaví nový profil.
  > 2. Koncovým uživatelům se zobrazí výzva k opětovnému zadání přihlašovacích údajů.

- **S/MIME**: **Povolte S/MIME** , aby uživatelé mohli podepisovat a šifrovat e-mail v aplikaci iOS Native mail. 

  Když použijete S/MIME s e-mailovou zprávou, ověříte pravost odesilatele a integritu a důvěrnost zprávy.

  - **Povoleno podepisování S/MIME**: Vyberte **Povolit** , pokud chcete uživatelům povolit, aby digitálně podepsali odchozí e-maily pro účet, který jste zadali. Podepisování pomáhá uživatelům, kteří přijímají zprávy, určit, že zpráva pochází od konkrétního odesílatele, a ne od někoho, kdo má jako odesílatele. Při **vypnutí** není možné uživatelům digitálně podepsat zprávu.
    - **Povolí uživateli změnu nastavení**: Zvolením možnosti **Povolit** uživatelům umožníte měnit chování podepisování S/MIME. Při **vypnutí** zabráníte uživatelům měnit nastavení podepisování S/MIME, které jste nakonfigurovali. K dispozici v iOS 12 a novějších.

  - **Podpisový certifikát S/MIME**: Vyberte existující profil certifikátu PKCS nebo SCEP, který se používá k podepisování e-mailových zpráv.
    - **Povolí uživateli změnu nastavení**: Chcete-li uživatelům povolit změnu podpisového certifikátu, vyberte možnost **Povolit** . **Disable zakáže** uživatelům měnit podpisový certifikát a vynutí, aby uživatelé používali nakonfigurovaný certifikát. K dispozici v iOS 12 a novějších.

  - **Šifrování ve výchozím nastavení**: **Možnost Povolit** šifruje všechny zprávy jako výchozí chování. **Disable** nešifruje všechny zprávy jako výchozí chování.
    - **Povolí uživateli změnu nastavení**: Chcete-li uživatelům povolit změnu výchozího chování šifrování, vyberte možnost **Povolit** . Možnost **Zakázat** znemožní uživatelům měnit výchozí chování šifrování a vynutí, aby uživatelé používali nastavení, které jste nakonfigurovali. K dispozici v iOS 12 a novějších.

  - **Vynutit šifrování podle zpráv**: Šifrování pro jednotlivé zprávy umožňuje uživatelům zvolit, které e-maily se před odesláním šifrují. Pokud chcete při vytváření nového e-mailu zobrazit možnost šifrování pro jednotlivé zprávy, vyberte **Povolit** . Uživatelé si pak můžou vybrat, jestli se chcete odhlásit nebo odhlásit šifrování podle zpráv. **Disable** znemožní zobrazování možnosti šifrování jednotlivých zpráv.

    Pokud je povolené šifrování **ve výchozím** nastavení, povolení šifrování pro jednotlivé zprávy umožňuje uživatelům odsouhlasit šifrování na jednu zprávu. Pokud je nastavení **šifrování ve výchozím** nastavení zakázané, povolení šifrování pro jednotlivé zprávy umožňuje uživatelům přihlášení k šifrování na základě zprávy.

  - **Certifikát šifrování S/MIME**: Vyberte existující profil certifikátu PKCS nebo SCEP, který se používá k šifrování e-mailových zpráv.
    - **Povolí uživateli změnu nastavení**: Vyberte **Povolit** , pokud chcete uživatelům povolit, aby změnili certifikát šifrování. **Disable** znemožní uživatelům měnit šifrovací certifikát a vynutí, aby uživatelé používali nakonfigurovaný certifikát. K dispozici v iOS 12 a novějších.
- **Velikost e-mailu, který se má synchronizovat**: Vyberte počet dní, po které se má e-mail synchronizovat. Nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Povolí přesun zpráv do jiných e-mailových účtů**: **Možnost Povolit** umožňuje uživatelům přesouvat e-mailové zprávy mezi různými účty, které uživatelé na svých zařízeních nakonfigurovali.
- **Povolí posílání e-mailů z aplikací třetích stran**: **Možnost Povolit** umožní uživatelům vybrat tento profil jako výchozí účet pro odesílání e-mailů. Aplikacím třetích stran umožňuje otevírat e-maily v nativní e-mailové aplikaci, například při připojení souborů k e-mailu.
- **Synchronizovat naposledy použité e-mailové adresy**: **Možnost Povolit** umožňuje uživatelům synchronizovat seznam e-mailových adres, které se nedávno používaly na zařízení se serverem.

## <a name="next-steps"></a>Další kroky

Profil je vytvořený, ale zatím se nepoužívá. Dále [Přiřaďte profil](device-profile-assign.md) a [sledujte jeho stav](device-profile-monitor.md).

Nakonfigurujte nastavení e-mailu na zařízeních se systémem [Android](email-settings-android.md), [Android Enterprise](email-settings-android-enterprise.md), [Windows 10](email-settings-windows-10.md)a [Windows Phone 8,1](email-settings-windows-phone-8-1.md) .
