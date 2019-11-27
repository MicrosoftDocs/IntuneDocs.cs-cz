---
title: Konfigurace nastavení e-mailu pro zařízení s iOS v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na seznam všech nastavení e-mailu, která můžete nakonfigurovat a přidat do zařízení se systémem iOS v Microsoft Intune, včetně použití serverů Exchange a získání atributů z Azure Active Directory. Můžete taky povolit SSL, ověřovat uživatele pomocí certifikátů nebo uživatelského jména a hesla a synchronizovat e-mail na zařízeních s iOS pomocí profilů konfigurace zařízení v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/12/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 73de0ac94ff02e43fe73ca6357f6008ba71e3b93
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390822"
---
# <a name="add-e-mail-settings-for-ios-devices-in-microsoft-intune"></a>Přidání nastavení e-mailu pro zařízení s iOS v Microsoft Intune

V Microsoft Intune můžete vytvořit a nakonfigurovat e-mail pro připojení k e-mailovému serveru, zvolit způsob ověřování uživatelů, použít S/MIME pro šifrování a další.

V tomto článku najdete seznam všech nastavení e-mailu, která jsou dostupná pro zařízení s iOS. Můžete vytvořit konfigurační profil zařízení, který bude nabízet nebo nasazovat tato nastavení e-mailu do zařízení s iOS.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil konfigurace zařízení](../email-settings-configure.md).

> [!NOTE]
> Tato nastavení jsou k dispozici pro všechny typy registrace. Další informace o typech registrace najdete v tématu Registrace zařízení se [systémem iOS](../ios-enroll.md).

## <a name="exchange-activesync-account-settings"></a>Nastavení účtu Exchange ActiveSync

- **E-mailový server**: Zadejte název hostitele vašeho Exchange serveru.
- **Název účtu**: Zadejte zobrazovaný název e-mailového účtu. Tento název se zobrazuje uživatelům na jejich zařízeních.
- **Atribut uživatelského jména z AAD**: Toto jméno je atribut, který Intune získá od služby Azure Active Directory (AAD). Intune dynamicky vygeneruje uživatelské jméno, které tento profil používá. Možnosti:
  - **Hlavní název uživatele**: Získá jméno, například `user1` nebo `user1@contoso.com`.
  - **Primární adresa SMTP**: Získá jméno ve formátu e-mailové adresy, například `user1@contoso.com`.
  - **Název účtu SAM**: Vyžaduje doménu, například `domain\user1`. Dále zadejte:  
    - **Zdroj názvu domény uživatele**: Zvolte **AAD** (Azure Active Directory) nebo **Vlastní**.
      - **AAD**: Získejte atributy z Azure AD. Dále zadejte:
        - **Atribut názvu domény uživatele z AAD**: vyberte, chcete-li získat **úplný název domény** (`contoso.com`) nebo atribut **název pro rozhraní NetBIOS** (`contoso`) daného uživatele.

      - **Vlastní**: Získejte atributy z vlastního názvu domény. Dále zadejte:
        - **Vlastní název domény, který se má použít**: zadejte hodnotu, kterou Intune používá pro název domény, například `contoso.com` nebo `contoso`.

- **Atribut e-mailové adresy z AAD**: Zvolte, jak se generuje e-mailová adresa uživatele. Možnosti:
  - **Hlavní název uživatele**: jako e-mailovou adresu použijte úplný hlavní název, například `user1@contoso.com` nebo `user1`.
  - **Primární adresa SMTP**: k přihlášení k Exchangi použijte primární adresu SMTP, třeba `user1@contoso.com`.
- **Metoda ověřování**: Vyberte způsob ověřování uživatelů pro e-mailový server. Možnosti:
  - **Certifikát**: vyberte profil certifikátu SCEP nebo PKCS klienta, který jste dříve vytvořili za účelem ověřování připojení k systému Exchange. Tato možnost nabízí nejbezpečnější a bezproblémové prostředí pro vaše uživatele.
  - **Uživatelské jméno a heslo**: uživatelům se zobrazí výzva k zadání uživatelského jména a hesla.
  - **Odvozené přihlašovací údaje**: použijte certifikát, který je odvozený od čipové karty uživatele. Další informace najdete v tématu [použití odvozených přihlašovacích údajů v Microsoft Intune](../protect/derived-credentials.md).

  >[!NOTE]
  > Vícefaktorové ověřování Azure není podporované.
  
- **SSL**: Při volbě **Povolit** se při posílání a přijímání e-mailů a komunikaci se serverem Exchange používá komunikace SSL (Secure Sockets Layer).
- **OAuth**: Při volbě **Povolit** se při posílání a přijímání e-mailů a komunikaci se serverem Exchange používá komunikace OAuth (Open Authorization). Pokud server OAuth používá ověřování certifikátem, u možnosti **Metoda ověřování** zvolte **Certifikát** a zahrňte do profilu příslušný certifikát. V opačném případě u možnosti **Metoda ověřování** zvolte **Uživatelské jméno a heslo**. Při použití OAuth mějte na paměti tyto skutečnosti:

  - Před zacílením tohoto profilu na uživatele potvrďte, že vaše e-mailové řešení podporuje OAuth. Office 365 se službou Exchange Online podporuje OAuth. Místní Exchange a jiná řešení od partnerů nebo třetích stran nemusí OAuth podporovat. U místního Exchange je možné nakonfigurovat moderní ověřování (viz příspěvek blogu s [oznámením hybridního moderního ověřování pro místní Exchange](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/)).

    Pokud e-mailový profil používá Oauth a e-mailová služba ho nepodporuje, bude se možnost **Zadejte heslo znovu** jevit jako nefunkční. Když například uživatel vybere možnost **Zadejte heslo znovu** v nastavení zařízení Apple, nic se nestane.

  - Při povoleném OAuth mají koncoví uživatelé jiné prostředí přihlašování k e-mailu s moderním ověřováním, které podporuje vícefaktorové ověřování. 

  - Některé organizace zakazují koncovým uživatelům možnost [samoobslužného přístupu k aplikacím](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). V této situaci může přihlášení s moderním ověřováním selhat, dokud správce nevytvoří podnikovou aplikaci „Účty iOS“ a neudělí uživatelům k této aplikaci přístup ve službě Azure AD.

    Výchozí akcí je přidání aplikace pomocí funkce [Přidat aplikaci](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) na **přístupovém panelu aplikace** **bez schválení organizací**. Další informace najdete v článku o [přiřazení uživatelů k aplikacím](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > Když povolíte OAuth, stane se následující:  
  > 1. Zařízením, která už jsou zacílená, se vystaví nový profil.
  > 2. Koncovým uživatelům se zobrazí výzva k opětovnému zadání přihlašovacích údajů.

## <a name="exchange-activesync-profile-configuration"></a>Konfigurace profilu Exchange ActiveSync

> [!IMPORTANT]
> Při konfiguraci těchto nastavení se do zařízení nasadí nový profil, a to i v případě, že se aktualizuje stávající e-mailový profil, aby zahrnoval tato nastavení. Uživatelům se zobrazí výzva k zadání hesla k účtu Exchange ActiveSync. Tato nastavení mají vliv na zadání hesla.

- **Data k synchronizaci**: Pokud používáte Exchange ActiveSync, vyberte služby Exchange, které jsou synchronizované na zařízení: kalendář, kontakty, připomenutí, poznámky a e-mail. Možnosti:
  - **Všechna data** (výchozí): synchronizace je povolena pro všechny služby.
  - **Pouze e-mail**: synchronizace je povolena pouze pro e-maily. Synchronizace je pro ostatní služby zakázaná.
  - **Pouze kalendář**: synchronizace je povolena pouze pro kalendář. Synchronizace je pro ostatní služby zakázaná.
  - **Pouze kalendář a kontakty**: synchronizace je povolena pouze pro kalendář a kontakty. Synchronizace je pro ostatní služby zakázaná.
  - **Pouze kontakty**: synchronizace je povolena pouze pro kontakty. Synchronizace je pro ostatní služby zakázaná.

  Tato funkce platí pro:  
  - iOS 13,0 a novější
  - iPadOS 13,0 a novější

- **Umožňuje uživatelům změnit nastavení synchronizace**: vyberte, jestli uživatelé můžou měnit nastavení Exchange ActiveSync pro služby Exchange na zařízení: kalendář, kontakty, připomenutí, poznámky a e-mail. Možnosti:

  - **Ano** (výchozí): uživatelé můžou změnit chování synchronizace všech služeb. Zvolíte-li možnost **Ano** , povolíte změny *všech* služeb.
  - **Ne**: uživatelé nemůžou měnit nastavení synchronizace všech služeb. Volba **žádného** blokování se nemění pro *všechny* služby.

  > [!TIP]
  > Pokud jste nakonfigurovali nastavení **Exchange data na synchronizaci** jenom na některé služby, doporučujeme pro toto nastavení vybrat **ne** . Zvolíte-li možnost **ne** , nebudou moci uživatelé měnit službu Exchange, která je synchronizovaná.

  Tato funkce platí pro:  
  - iOS 13,0 a novější
  - iPadOS 13,0 a novější

## <a name="exchange-activesync-email-settings"></a>Nastavení e-mailu Exchange ActiveSync

- **S/MIME**: s/MIME využívají e-mailové certifikáty, které poskytují dodatečné zabezpečení e-mailové komunikace, a to pomocí podepisování, šifrování a dešifrování. Když použijete S/MIME s e-mailovou zprávou, ověříte pravost odesilatele a integritu a důvěrnost zprávy.

  Možnosti:

  - **Zakázat S/MIME** (výchozí): nepoužívá e-mailový certifikát S/MIME k podepsání, šifrování nebo dešifrování e-mailů.
  - **Povolit S/MIME**: umožňuje uživatelům podepsat a šifrovat e-mail v aplikaci iOS Native mail. Dále zadejte:

    - **Povolené podepisování S/MIME**: **Zakázat** (výchozí) neumožní uživatelům digitálně podepsat zprávu. **Možnost Povolit** umožňuje uživatelům digitálně podepisovat odchozí e-maily pro účet, který jste zadali. Podepisování pomáhá uživatelům, kteří přijímají zprávy, určit, že zpráva pochází od konkrétního odesílatele, a ne od někoho, kdo má jako odesílatele.
      - **Povolit uživateli změnu nastavení**: **Povolit** umožňuje uživatelům změnit možnosti podepisování. **Disable** (výchozí) znemožní uživatelům měnit podepisování a vynutí, aby uživatelé používali nakonfigurovaná podepisování.
      - **Typ podpisového certifikátu**: vaše možnosti:
        - **Nenakonfigurováno**: Intune neaktualizuje nebo nemění toto nastavení.
        - **Žádné**: jako správce nebudete vynucovat konkrétní certifikát. Tuto možnost vyberte, pokud si uživatelé můžou zvolit vlastní certifikát.
        - **Odvozené přihlašovací údaje**: použijte certifikát, který je odvozený od čipové karty uživatele. Další informace najdete v tématu [použití odvozených přihlašovacích údajů v Microsoft Intune](../protect/derived-credentials.md).
        - **Certifikáty**: Vyberte existující profil certifikátu PKCS nebo SCEP, který se používá k podepisování e-mailových zpráv.
      - **Povolit uživateli změnu nastavení**: **Povolit** umožňuje uživatelům změnit podpisový certifikát. **Disable** (výchozí) znemožní uživatelům měnit podpisový certifikát a vynutí, aby uživatelé používali nakonfigurovaný certifikát.

        Tato funkce platí pro:  
        - iOS 12 a novější
        - iPadOS 12 a novější

    - **Zašifrovat ve výchozím nastavení**: **Povolit** šifruje všechny zprávy jako výchozí chování. **Disable** (výchozí) nešifruje všechny zprávy jako výchozí chování.
      - **Povolit uživateli změnu nastavení**: **Povolit** umožňuje uživatelům změnit výchozí chování šifrování. Při použití hodnoty **Zakázat** mohou uživatelé měnit výchozí chování šifrování a vynutí, aby uživatelé používali konfigurované šifrování.

        Tato funkce platí pro:  
        - iOS 12 a novější
        - iPadOS 12 a novější

    - **Vynutit šifrování podle zpráv**: šifrování na základě zpráv umožňuje uživatelům zvolit, které e-maily se před odesláním šifrují.

      Při vytváření nového e-mailu se v části **Povolit** zobrazí možnost šifrování pro jednotlivé zprávy. Uživatelé si pak můžou zvolit výslovný souhlas nebo odsouhlasení šifrování podle zpráv. Pokud je povolené taky **šifrování ve výchozím** nastavení, povolení šifrování pro jednotlivé zprávy umožňuje uživatelům odsouhlasit šifrování na jednu zprávu.

      **Disable** (výchozí) znemožní zobrazování možnosti šifrování jednotlivých zpráv. Pokud je možnost **šifrování ve výchozím** nastavení také zakázaná, povolení šifrování pro jednotlivé zprávy umožňuje uživatelům přihlášení k šifrování na základě zprávy.

      - **Typ certifikátu šifrování**: vaše možnosti:
        - **Nenakonfigurováno**: Intune neaktualizuje nebo nemění toto nastavení.
        - **Žádné**: jako správce nebudete vynucovat konkrétní certifikát. Tuto možnost vyberte, pokud si uživatelé můžou zvolit vlastní certifikát.
        - **Odvozené přihlašovací údaje**: použijte certifikát, který je odvozený od čipové karty uživatele. Další informace najdete v tématu [použití odvozených přihlašovacích údajů v Microsoft Intune](../protect/derived-credentials.md).
        - **Certifikáty**: Vyberte existující profil certifikátu PKCS nebo SCEP, který se používá k podepisování e-mailových zpráv.
      - **Povolit uživateli změnu nastavení**: **Povolit** uživatelům změnit šifrovací certifikát. **Disable** (výchozí) znemožní uživatelům měnit šifrovací certifikát a vynutí, aby uživatelé používali nakonfigurovaný certifikát.

        Tato funkce platí pro:  
        - iOS 12 a novější
        - iPadOS 12 a novější

- **Počet e-mailů k synchronizaci**: Zvolte počet dní, za které se mají e-maily synchronizovat. Nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Povolit přesouvání zpráv do jiných e-mailových účtů**: **Povolit** (výchozí) umožňuje uživatelům přesouvat e-mailové zprávy mezi různými účty, které uživatelé na svých zařízeních nakonfigurovali.
- **Povolit odesílání e-mailů z aplikací třetích stran**: **Povolit** (výchozí) umožní uživatelům vybrat tento profil jako výchozí účet pro odesílání e-mailů. Aplikacím třetích stran umožňuje otevírat e-maily v nativní e-mailové aplikaci, například při připojení souborů k e-mailu.
- **Synchronizovat naposledy použité e-mailové adresy**: **Povolit** (výchozí) umožní uživatelům synchronizovat seznam e-mailových adres, které se nedávno používaly na zařízení se serverem.

## <a name="next-steps"></a>Další kroky

Profil je vytvořený, ale zatím se nepoužívá. Dále [Přiřaďte profil](../device-profile-assign.md) a [sledujte jeho stav](../device-profile-monitor.md).

Nakonfigurujte nastavení e-mailu na zařízeních se systémem [Android](../email-settings-android.md), [Android Enterprise](../email-settings-android-enterprise.md), [Windows 10](email-settings-windows-10.md)a [Windows Phone 8,1](email-settings-windows-phone-8-1.md) .
