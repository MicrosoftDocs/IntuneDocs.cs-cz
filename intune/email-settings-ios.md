---
title: Nastavení e-mailu pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte e-mailový profil konfigurace zařízení, který používá servery Exchange a načítá atributy ze služby Azure Active Directory. Pomocí Microsoft Intune můžete na zařízeních s iOSem také povolit protokol SSL, ověřovat uživatele certifikáty nebo uživatelským jménem a heslem a synchronizovat e-maily.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b3aa3e7a4cd79ab990afe7f02a1d6960bc66494a
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52180183"
---
# <a name="email-profile-settings-for-ios-devices---intune"></a>Nastavení e-mailového profilu na zařízeních s iOSem – Intune

Pomocí nastavení e-mailového profilu můžete konfigurovat zařízení s iOSem.

> [!IMPORTANT]
> Funkci S/MIME popsanou v tomto článku právě vylepšujeme. V důsledku toho je tato funkce S/MIME z Intune odebraná. Až tuto funkci uvolníme k použití, tuto poznámku odstraníme.

## <a name="email-settings"></a>Nastavení e-mailu

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

- **Atribut e-mailové adresy z AAD**: Zvolte, jak se generuje e-mailová adresa uživatele. Pokud chcete jako e-mailovou adresu použít úplný hlavní název, vyberte **Hlavní název uživatele** (`user1@contoso.com` nebo `user1`). Pokud chcete pro přihlášení k Exchangi použít primární adresu SMTP, vyberte **Primární adresa SMTP** (`user1@contoso.com`).
- **Metoda ověřování**: Jako metodu ověřování používanou e-mailovým profilem vyberte buď **Uživatelské jméno a heslo**, nebo **Certifikáty**. Vícefaktorové ověřování Azure není podporované.
  - Pokud jste vybrali **Certifikát**, vyberte profil klienta SCEP nebo PKCS, který jste dříve vytvořili a který se použije k ověření připojení Exchange.
- **SSL**: Při volbě **Povolit** se při posílání a přijímání e-mailů a komunikaci se serverem Exchange používá komunikace SSL (Secure Sockets Layer).
- **OAuth**: Při volbě **Povolit** se při posílání a přijímání e-mailů a komunikaci se serverem Exchange používá komunikace OAuth (Open Authorization). Pokud server OAuth používá ověřování certifikátem, u možnosti **Metoda ověřování** zvolte **Certifikát** a zahrňte do profilu příslušný certifikát. V opačném případě u možnosti **Metoda ověřování** zvolte **Uživatelské jméno a heslo**. Při použití OAuth mějte na paměti tyto skutečnosti:

  - Před zacílením tohoto profilu na uživatele potvrďte, že vaše e-mailové řešení podporuje OAuth. Office 365 se službou Exchange Online podporuje OAuth. Místní Exchange a jiná řešení od partnerů nebo třetích stran nemusí OAuth podporovat. U místního Exchange je možné nakonfigurovat moderní ověřování (viz příspěvek blogu s [oznámením hybridního moderního ověřování pro místní Exchange](https://blogs.technet.microsoft.com/exchange/2017/12/06/announcing-hybrid-modern-authentication-for-exchange-on-premises/)).

    Pokud e-mailový profil používá Oauth a e-mailová služba ho nepodporuje, bude se možnost **Zadejte heslo znovu** jevit jako nefunkční. Když například uživatel vybere možnost **Zadejte heslo znovu** v nastavení zařízení Apple, nic se nestane.

  - Při povoleném OAuth mají koncoví uživatelé jiné prostředí přihlašování k e-mailu s moderním ověřováním, které podporuje vícefaktorové ověřování. 

  - Některé organizace zakazují koncovým uživatelům možnost [samoobslužného přístupu k aplikacím](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-self-service-access). V této situaci může přihlášení s moderním ověřováním selhat, dokud správce nevytvoří podnikovou aplikaci „Účty iOS“ a neudělí uživatelům k této aplikaci přístup ve službě Azure AD.

    Výchozí akcí je přidání aplikace pomocí funkce **Přidat aplikaci** na [přístupovém panelu aplikace](https://docs.microsoft.com/azure/active-directory/user-help/active-directory-saas-access-panel-introduction) **bez schválení organizací**. Další informace najdete v článku o [přiřazení uživatelů k aplikacím](https://docs.microsoft.com/azure/active-directory/manage-apps/ways-users-get-assigned-to-applications).

  > [!NOTE]
  > Když povolíte OAuth, stane se následující:  
  > 1. Zařízením, která už jsou zacílená, se vystaví nový profil.
  > 2. Koncovým uživatelům se zobrazí výzva k opětovnému zadání přihlašovacích údajů.

- **S/MIME**: Použijte možnost **Povolit S/MIME**, aby se odchozí e-maily odesílaly s podpisem S/MIME. Pokud je tato možnost povolená, můžete také šifrovat e-maily pro příjemce, kteří můžou přijímat zašifrované e-maily a dešifrovat přijaté e-maily od odesílatelů.
  - Pokud vyberete **Certifikát**, zvolte pro ověření připojení k Exchangi a/nebo šifrování výměny e-mailů nějaký existující profil certifikátu PKCS.
- **Počet e-mailů k synchronizaci**: Zvolte počet dní, za které se mají e-maily synchronizovat. Nebo vyberte **Bez omezení**, pokud chcete synchronizovat všechny dostupné e-maily.
- **Povolit přesouvání zpráv do jiných e-mailových účtů**: Možnost **Povolit** umožňuje uživatelům přesouvat e-mailové zprávy mezi různými účty, které si na svých zařízeních nakonfigurovali.
- **Umožnit posílání e-mailů z aplikací třetích stran**: Možnost **Povolit** umožňuje uživatelům vybrat tento profil jako výchozí účet pro odesílání e-mailů. Aplikacím třetích stran umožňuje otevírat e-maily v nativní e-mailové aplikaci, například při připojení souborů k e-mailu.
- **Synchronizovat nedávno použité e-mailové adresy**: Možnost **Povolit** umožňuje uživatelům synchronizovat se serverem seznam e-mailových adres, které se na zařízení nedávno používaly.

## <a name="next-steps"></a>Další postup
[Konfigurace nastavení e-mailu v Intune](email-settings-configure.md)
