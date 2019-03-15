---
title: Nastavení e-mailu pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: Zobrazit seznam všech nastavení e-mailu můžete nakonfigurovat a přidat do zařízení s Iosem v Microsoft Intune, včetně použití serverů Exchange a získání atributů z Azure Active Directory. Můžete také povolit protokol SSL, ověřování uživatelů pomocí certifikátů nebo uživatelského jména a hesla a synchronizace e-mailu na zařízeních s Iosem pomocí konfiguračních profilů zařízení v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/11/2018
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1cf1daf42d1dfcd8dd25304040e868581a056943
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57566402"
---
# <a name="email-profile-settings-for-ios-devices-in-intune"></a>E-mailového profilu pro zařízení s Iosem v Intune

V Microsoft Intune, můžete vytvořit a nakonfigurovat e-mailu se připojit k e-mailový server, vyberte, jak se uživatelé ověřovat, použít S/MIME pro šifrování a další.

Tento článek uvádí a popisuje všechny nastavení e-mailu pro zařízení s Iosem. Můžete vytvořit profil konfigurace zařízení pro nabízená nebo nasadit tato nastavení e-mailu pro zařízení s Iosem.

## <a name="before-you-begin"></a>Před zahájením

[Vytvořit profil konfigurace zařízení](email-settings-configure.md#create-a-device-profile).

## <a name="email-settings"></a>Nastavení e-mailu

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

- **Atribut e-mailové adresy z AAD**: Vyberte způsob generování e-mailovou adresu uživatele. Pokud chcete jako e-mailovou adresu použít úplný hlavní název, vyberte **Hlavní název uživatele** (`user1@contoso.com` nebo `user1`). Pokud chcete pro přihlášení k Exchangi použít primární adresu SMTP, vyberte **Primární adresa SMTP** (`user1@contoso.com`).
- **Metoda ověřování**: Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**. Vícefaktorové ověřování Azure není podporované.
  - Pokud jste vybrali **Certifikát**, vyberte profil klienta SCEP nebo PKCS, který jste dříve vytvořili a který se použije k ověření připojení Exchange.
- **SSL**: **Povolit** používá komunikaci vrstvy SSL (Secure Sockets) při posílání a přijímání e-mailů a komunikaci se serverem Exchange.
- **OAuth**: **Povolit** používá komunikaci otevřené povolení (OAuth) při posílání a přijímání e-mailů a komunikaci se serverem Exchange. Pokud server OAuth používá ověřování certifikátem, u možnosti **Metoda ověřování** zvolte **Certifikát** a zahrňte do profilu příslušný certifikát. V opačném případě u možnosti **Metoda ověřování** zvolte **Uživatelské jméno a heslo**. Při použití OAuth mějte na paměti tyto skutečnosti:

  - Před zacílením tohoto profilu na uživatele potvrďte, že vaše e-mailové řešení podporuje OAuth. Office 365 se službou Exchange Online podporuje OAuth. Místní Exchange a jiná řešení od partnerů nebo třetích stran nemusí OAuth podporovat. U místního Exchange je možné nakonfigurovat moderní ověřování (viz příspěvek blogu s [oznámením hybridního moderního ověřování pro místní Exchange](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/)).

    Pokud e-mailový profil používá Oauth a e-mailová služba ho nepodporuje, bude se možnost **Zadejte heslo znovu** jevit jako nefunkční. Když například uživatel vybere možnost **Zadejte heslo znovu** v nastavení zařízení Apple, nic se nestane.

  - Při povoleném OAuth mají koncoví uživatelé jiné prostředí přihlašování k e-mailu s moderním ověřováním, které podporuje vícefaktorové ověřování. 

  - Některé organizace zakazují koncovým uživatelům možnost [samoobslužného přístupu k aplikacím](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). V této situaci může přihlášení s moderním ověřováním selhat, dokud správce nevytvoří podnikovou aplikaci „Účty iOS“ a neudělí uživatelům k této aplikaci přístup ve službě Azure AD.

    Výchozí akcí je přidání aplikace pomocí funkce **Přidat aplikaci** na [přístupovém panelu aplikace](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **bez schválení organizací**. Další informace najdete v článku o [přiřazení uživatelů k aplikacím](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > Když povolíte OAuth, stane se následující:  
  > 1. Zařízením, která už jsou zacílená, se vystaví nový profil.
  > 2. Koncovým uživatelům se zobrazí výzva k opětovnému zadání přihlašovacích údajů.

- **S/MIME**: **Povolení S/MIME** umožňuje uživatelům přihlášení a/nebo šifrování e-mailu v nativní e-mailové aplikace iOS. 

  Při použití S/MIME s e-mailovou zprávu potvrzení pravosti odesílatele, a integritu a důvěrnost zprávy.

  - **Povoleno podepisování S/MIME**: Zvolte **povolit** umožňuje uživatelům k podepsání odchozích e-mailu pro zadaný účet. Podepisování umožňuje uživatelům přijímat zprávy potřeba mít jistotu, že zpráva pochází z konkrétního odesílatele a nikoli z někdo že se maskují být odesílatele. **Zakázat** neumožňuje uživatelům podepsání zprávy.
    - **Povolit uživateli měnit nastavení**: Zvolte **povolit** umožňuje uživatelům změnit chování podepisování S/MIME. **Zakázat** zabraňuje uživatelům možnost měnit nastavení nakonfigurované podepisování S/MIME. K dispozici v Iosu 12 a novější.

  - **Podpisový certifikát S/MIME**: Vyberte existující PKCS nebo SCEP profil certifikátu, který se používá k podepisování e-mailové zprávy.
    - **Povolit uživateli měnit nastavení**: Zvolte **povolit** umožňuje uživatelům změnit podpisový certifikát. **Zakázat** zabraňuje uživatelům možnost měnit podpisový certifikát a vynutí uživatelům používat certifikát, který jste nakonfigurovali. K dispozici v Iosu 12 a novější.

  - **Ve výchozím nastavení šifrování**: **Povolit** šifruje všechny zprávy jako výchozí chování. **Zakázat** nešifruje všechny zprávy jako výchozí chování.
    - **Povolit uživateli měnit nastavení**: Zvolte **povolit** umožňuje uživatelům změnit výchozí chování šifrování. **Zakázat** zabrání uživatelům změnit výchozí chování šifrování a nutí uživatele pomocí nastavení, které jste nakonfigurovali. K dispozici v Iosu 12 a novější.

  - **Vynutit šifrování za zprávy**: Šifrování za zpráv umožňuje uživatelům zvolit, komu chcete e-maily se před odesláním zašifrují. Zvolte **povolit** zobrazíte možnosti šifrování za zprávy při vytváření nového e-mailu. Uživatelé pak můžou zvolit vyjádřit výslovný souhlas nebo za zprávy šifrování používat nechcete. **Zakázat** brání možnost šifrování za zprávy ze zobrazení.

    Pokud **šifrovat ve výchozím nastavení** nastavení povoleno, povolení šifrování za zprávy umožňuje uživatelům se odhlásit ze šifrování za zprávy. Pokud **šifrovat ve výchozím nastavení** je zakázáno, povolení šifrování za zprávy umožňuje uživatelům přihlásit se k šifrování za zprávy.

  - **Certifikát šifrování S/MIME**: Vyberte existující PKCS nebo SCEP profil certifikátu, který se používá k šifrování e-mailové zprávy.
    - **Povolit uživateli měnit nastavení**: Zvolte **povolit** umožňuje uživatelům změnit šifrovací certifikát. **Zakázat** zabraňuje uživatelům možnost měnit šifrovací certifikát a vynutí uživatelům používat certifikát, který jste nakonfigurovali. K dispozici v Iosu 12 a novější.
- **Počet e-mailů k synchronizaci**: Zvolte počet dní e-mailu, který chcete synchronizovat. Nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Povolit přesunování na jiné e-mailové účty zpráv**: **Povolit** povolí uživatelům přesunovat e-mailové zprávy mezi různými účty, uživatelé na svých zařízeních nakonfigurovali.
- **Povolit e-mailů z aplikací třetí strany**: **Povolit** umožňuje uživatelům, aby tento profil vybral jako výchozí účet pro posílání e-mailu. Aplikacím třetích stran umožňuje otevírat e-maily v nativní e-mailové aplikaci, například při připojení souborů k e-mailu.
- **Synchronizovat naposledy použité e-mailové adresy**: **Povolit** umožňuje uživatelům povolíte synchronizaci seznamu e-mailové adresy, které byly nedávno použité v zařízení se serverem.

## <a name="next-steps"></a>Další postup

Profil je vytvořený, ale zatím se nepoužívá. Dále [přiřadit profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).

Konfigurace nastavení e-mailu na [Android](email-settings-android.md), [Windows 10](email-settings-windows-10.md), a [Windows Phone 8.1](email-settings-windows-phone-8-1.md) zařízení.
