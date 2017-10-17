---
title: "Ochrana e-mailu na místním Exchangi"
description: "Chraňte a kontrolujte přístup k podnikovým e-mailům v místním systému Exchange pomocí podmíněného přístupu."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a55071f5-101e-4829-908d-07d3414011fc
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6bdb5fbf7bb382c9ad503f584b499f5275885ef1
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="protect-email-access-to-exchange-on-premises-and-legacy-exchange-online-dedicated-with-intune"></a>Ochrana přístupu k e-mailu na místním Exchangi a starším Exchangi Online Dedicated v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pokud chcete řídit přístup k e-mailům v místním systému Exchange nebo ve starším prostředí Exchange Online Dedicated, můžete pomocí Microsoft Intune nakonfigurovat podmíněný přístup.
Další informace o tom, jak podmíněný přístup funguje, najdete v článku [Ochrana přístupu k e-mailu a službám O365](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).

> [!NOTE]
> Pokud máte vyhrazené prostředí Exchange Online a potřebujete zjistit, jestli má novou, nebo starší verzi konfigurace, obraťte se na správce svého účtu.

## <a name="before-you-begin"></a>Před zahájením

Nezapomeňte ověřit následující nastavení:

-   Musíte mít **Exchange 2010 nebo novější**. Podporují se pole serveru pro klientský přístup (CAS) Exchange Serveru.

-   Musíte použít [místní konektor Exchange pro Intune](intune-on-premises-exchange-connector.md), který připojí Intune k místnímu systému Exchange. To vám umožní spravovat zařízení přes konzolu Intune.

    -   Místní konektor Exchange, který je dostupný v konzole Intune, je určený výhradně pro vašeho tenanta Intune a nedá se použít s žádným jiným tenantem. Doporučujeme, abyste se také ujistili, že je konektor Exchange pro vašeho tenanta nainstalovaný jenom **na jednom počítači**.

        Konektor si můžete stáhnout z konzoly správce Intune. Podrobný postup při konfiguraci místního konektoru Exchange najdete v článku o [konfiguraci místního konektoru Exchange pro místní nebo hostovaný Exchange](intune-on-premises-exchange-connector.md).

    -   Konektor můžete nainstalovat na každý počítač, který může komunikovat se serverem Exchange.

    -   Tento konektor podporuje **prostředí Exchange CAS**. Technicky vzato můžete konektor nainstalovat přímo na server Exchange CAS. Nedoporučujeme to však, protože to zvyšuje zatížení serveru. Při konfiguraci je nutné konektor nastavit tak, aby komunikoval s jedním ze serverů Exchange CAS.

-   **Exchange ActiveSync** je potřeba nakonfigurovat s ověřováním na základě certifikátů nebo se zadáváním přihlašovacích údajů uživateli.

### <a name="device-compliance-requirements"></a>Požadavky na dodržování předpisů zařízení

Když nakonfigurujete zásady podmíněného přístupu a jejich cílem je určitý uživatel, může se tento uživatel připojit k e-mailu teprve tehdy, když jeho **zařízení** splňuje tyto požadavky:

-  Je počítačem připojeným k doméně nebo **zaregistrovaným** v Intune.

-  **Je zaregistrované v Azure Active Directory**. Kromě toho musí být ve službě Azure Active Directory zaregistrované ID protokolu Exchange ActiveSync klienta.

  Pro zákazníky s Intune a Office 365 se služba Azure Active Directory Device Registration aktivuje automaticky. Zákazníci, kteří už mají nasazenou službu ADFS Device Registration Service, registrovaná zařízení ve svojí místní službě Active Directory neuvidí. **To neplatí pro počítače s Windows ani zařízení Windows Phone**.

-   **Vyhovuje** veškerým zásadám dodržování předpisů Intune, které jsou nasazené na toto zařízení.

### <a name="how-conditional-access-works-with-exchange-on-premises"></a>Jak podmíněný přístup funguje s místním systémem Exchange

Následující diagram znázorňuje postup, který zásady podmíněného přístupu pro místní systém Exchange používají k vyhodnocení toho, jestli se mají zařízení povolit nebo blokovat.

![Diagram zobrazující průběh rozhodování, jestli má zařízení povolený přístup k místnímu Exchangi, nebo je zablokované](../media/ConditionalAccess8-2.png)

Pokud se nedodrží zásady podmíněného přístupu, mezi zablokováním zařízení a přijetím jedné z následujících zpráv o karanténě uživatelem při přihlášení je 10minutová prodleva:

- Pokud není zařízení zaregistrované v Intune nebo v Azure Active Directory, zobrazí se zpráva s pokyny k instalaci aplikace Portál společnosti, registraci zařízení a aktivaci e-mailu. Tento proces také přidruží ID protokolu Exchange ActiveSync zařízení k záznamu zařízení v Azure Active Directory.

-   Pokud zařízení nedodržuje předpisy, zobrazí se zpráva, která uživatele přesměruje na web Portál společnosti Intune nebo na aplikaci Portál společnosti, kde může najít informace o problému a jeho řešení.

## <a name="support-for-mobile-devices"></a>Podpora mobilních zařízení
Podporované systémy:
-   Windows Phone 8.1 a novější

-   Nativní e-mailová aplikace v iOSu

-   Poštovní klienti Exchange ActiveSync, například Gmail v Androidu 4 nebo novějším
-   Poštovní klienti Exchange ActiveSync na **zařízeních s Androidem for Work**: Na zařízeních s Androidem for Work se v **pracovním profilu** podporují jenom aplikace **Gmail** a **Nine Work**. Aby v Androidu for Work fungoval podmíněný přístup, je nutné nasadit e-mailový profil pro aplikaci Gmail nebo Nine Work a zároveň tyto aplikace nasadit jako požadovanou instalaci. 

> [!NOTE]
> Aplikace Microsoft Outlook pro Android a iOSem se nepodporuje.

## <a name="support-for-pcs"></a>Podpora počítačů
Podporovaná možnost:
-   Aplikace **Pošta** ve Windows 8.1 a novějších verzích (při registraci počítače v Intune)

##  <a name="configure-a-conditional-access-policy"></a>Konfigurace zásad podmíněného přístupu

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Zásady** > **Podmíněný přístup** > **Zásady pro místní Exchange**.
![IntuneSA5aSelectExchOnPremPolicy](../media/IntuneSA5aSelectExchOnPremPolicy.png)

2.  Nakonfigurujte zásady pomocí vámi požadovaných nastavení: ![Snímek obrazovky se stránkou zásad místního systému Exchange](../media/IntuneSA5bExchangeOnPremPolicy.png)

  - **Blokovat e-mailovým aplikacím přístup k místnímu systému Exchange, pokud zařízení nevyhovuje nebo není zaregistrované v Microsoft Intune:** Pokud vyberete tuto možnost, zařízení, která nespravuje Intune nebo která nevyhovují zásadám dodržování předpisů, budou mít zablokovaný přístup ke službám Exchange.

  - **Přepis výchozího pravidla – Vždy povolit zaregistrovaným a kompatibilním aplikacím přístup k Exchange:** Pokud vyberete tuto možnost, zařízení zaregistrovaná v Intune a splňující zásady dodržování předpisů budou moct získat přístup k Exchangi.
  Toto pravidlo přepíše **Výchozí pravidlo**. To znamená, že i když nastavíte **Výchozí pravidlo** na umístění do karantény nebo blokování přístupu, zaregistrovaná zařízení splňující předpisy budou mít pořád povolený přístup k Exchangi.

  - **Cílové skupiny:** Vyberte skupiny uživatelů Intune, kteří musí zaregistrovat svoje zařízení v Intune předtím, než získají přístup k Exchangi.

  - **Vyloučené skupiny:** Vyberte skupiny uživatelů Intune, které jsou ze zásad podmíněného přístupu vyloučené. Uživatelé v tomto seznamu budou vyloučení, i když jsou zároveň uvedení i v seznamu **Cílové skupiny**.

  - **Výjimky platforem:** Vyberte **Přidat pravidlo** a nakonfigurujte pravidlo, které bude definovat úrovně přístupu pro zadané řady a modely mobilních zařízení. Vzhledem k tomu, že tato zařízení můžou být jakéhokoli typu, můžete nakonfigurovat také typy zařízení, které Intune nepodporuje.

  - **Výchozí pravidlo:** U zařízení, pro které neplatí žádné z ostatních pravidel, můžete zvolit, aby mělo přístup k Exchangi, můžete ho blokovat nebo umístit do karantény. Pokud nastavíte pravidlo, kterým povolíte přístup pro zaregistrovaná zařízení splňující předpisy, automaticky se udělí přístup k e-mailům pro zařízení se systémy iOS, Windows a řešením Samsung KNOX. Uživatel získá přístup k e-mailům a nemusí kvůli tomu provádět žádné kroky.
      - U zařízení s Androidem, která nepoužívají řešení Samsung KNOX, dostanou uživatelé e-mail s informací o karanténě, který bude obsahovat návod k ověření registrace a dodržování předpisů. K e-mailům získají přístup až po tomto ověření. Pokud nastavíte pravidlo na blokování přístupu nebo umístění zařízení do karantény, budou mít všechna zařízení zablokovaný přístup k Exchangi bez ohledu na to, jestli jsou už zaregistrovaná v Intune. Pokud nechcete, aby toto pravidlo platilo pro zaregistrovaná zařízení splňující předpisy, zaškrtněte políčko **Přepis výchozího pravidla**.
>[!TIP]
>Pokud chcete před udělením přístupu k e-mailům nejdřív zablokovat všechna zařízení, vyberte pravidlo Blokovat přístup nebo pravidlo Umístit do karantény. Výchozí pravidlo se použije na všechny typy zařízení, což ovlivní také typy zařízení nakonfigurované jako výjimky platforem, které Intune nepodporuje.

  - **Oznámení uživateli:** Kromě e-mailu s oznámením odeslaného z Exchange odešle Intune e-mail, který obsahuje postup pro odblokování zařízení. Výchozí zprávu můžete upravit a přizpůsobit svým potřebám. Pokud se zařízení uživatele před obdržením e-mailu s oznámením Intune obsahujícím pokyny k nápravě zablokuje (tento e-mail se doručuje do poštovní schránky Exchange uživatele), může uživatel použít pro přístup k Exchangi a zobrazení zprávy odblokované zařízení nebo jinou metodu.
      - To platí hlavně v případě, že je **Výchozí pravidlo** nastavené na blokování nebo umístění do karantény. V takovém případě musí uživatel přejít na web App Store, stáhnout aplikaci Portál společnosti od Microsoftu a zaregistrovat si zařízení. To se vztahuje na zařízení se systémy iOS, Windows a řešením Samsung KNOX. U zařízení nepoužívajících standard Samsung KNOX musíte odeslat e-mail z karantény na alternativní e-mailový účet. Uživatel ho musí zkopírovat na své blokované zařízení a dokončit tak proces registrace a dodržování předpisů.
  > [!NOTE]
  > Aby systém Exchange mohl e-mail s oznámením odeslat, musíte určit účet, který se má k odeslání e-mailu s oznámením použít.
  >
  > Podrobnosti najdete v článku o [konfiguraci místního konektoru Exchange pro místní nebo hostovaný Exchange](intune-on-premises-exchange-connector.md).

3.  Po dokončení vyberte **Uložit**.

-   Zásady podmíněného přístupu nemusíte nasazovat, projeví se okamžitě.

-   Jakmile uživatel nastaví profil Exchange ActiveSync, může trvat jednu až tři hodiny, než se zařízení zablokuje (pokud ho nespravuje Intune).

-   Pokud pak blokovaný uživatel zařízení zaregistruje do Intune a zajistí dodržování předpisů, odblokuje se přístup k e-mailu během dvou minut.

-   Pokud uživatel zruší registraci v Intune, může trvat jednu až tři hodiny, než se zařízení zablokuje.

**Pokud se chcete podívat na nějaké ukázkové scénáře konfigurace zásad podmíněného přístupu, kterými se dá přístup pro zařízení chránit, prohlédněte si [Ukázkové scénáře ochrany přístupu k e-mailu](restrict-email-access-example-scenarios.md).**

## <a name="next-steps"></a>Další kroky
-   [Ochrana přístupu k SharePointu Online](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

-   [Ochrana přístupu k Online Skypu pro firmy](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
