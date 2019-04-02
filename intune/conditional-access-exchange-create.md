---
title: Vytvoření zásad podmíněného přístupu Exchange | Microsoft Intune
titleSuffix: Microsoft Intune
description: Konfigurace podmíněného přístupu pro místní Exchange a starší verze Exchange Online Dedicated v Intune
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ca9531bfd16c68c23af05e3db3aa084b26adb0dc
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798520"
---
# <a name="create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated"></a>Vytvořte zásady podmíněného přístupu pro místní Exchange a starší verze Exchange Online Dedicated

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Tento článek popisuje, jak nakonfigurovat podmíněný přístup pro místní Exchange na základě dodržování předpisů zařízením.

Pokud máte vyhrazené prostředí Exchange Online a potřebujete zjistit, jestli má novou, nebo starší verzi konfigurace, obraťte se na správce svého účtu. Pokud chcete řídit přístup k e-mailům v místním Exchangi nebo ve starším vyhrazeném prostředí Exchange Online, nakonfigurujte v Intune podmíněný přístup k místnímu Exchangi.

## <a name="before-you-begin"></a>Před zahájením

Než nakonfigurujete podmíněný přístup, ověřte, jestli jsou splněné tyto podmínky:

- Musíte mít **Exchange 2010 SP1 nebo novější**. Podporuje se pole serveru pro klientský přístup (CAS) serveru Exchange.

- Musíte použít [místní Exchange Connector s protokolem Exchange Active Sync](exchange-connector-install.md), který připojí Intune k místnímu Exchangi.

    >[!IMPORTANT]
    >Místní konektor Exchange je určený výhradně pro vašeho tenanta Intune a nedá se použít s žádným jiným tenantem. Intune teď podporuje více místních Exchange Connectorů pro každé předplatné. Pokud máte více než jednu místní organizaci Exchange, můžete pro každou organizaci Exchange nastavit samostatný konektor.

- Konektor pro místní organizaci Exchange může být nainstalovaný na každém počítači, který může komunikovat se serverem Exchange.

- Tento konektor podporuje **prostředí Exchange CAS**. Z technického hlediska můžete konektor nainstalovat přímo na server Exchange CAS, ale nedoporučuje se to, protože se tím zvýší zátěž serveru. Při konfiguraci musíte konektor nastavit tak, aby komunikoval s jedním ze serverů Exchange CAS.

- Protokol **Exchange ActiveSync** je potřeba nakonfigurovat s ověřováním na základě certifikátů nebo zadávání přihlašovacích údajů uživateli.

- Pokud jsou pro určitého uživatele nakonfigurované zásady podmíněného přístupu, může se tento uživatel připojit k e-mailu teprve tehdy, když jeho **zařízení** splňuje tyto požadavky:
    - Musí být **zaregistrovaný** ve službě Intune nebo se musí jednat o počítač připojený k doméně.
    - **Je zaregistrované v Azure Active Directory**. Kromě toho musí být ve službě Azure Active Directory zaregistrované ID protokolu Exchange ActiveSync klienta.
<br></br>
- Pro zákazníky s Intune a Office 365 se služba Azure AD Device Registration Service (DRS) aktivuje automaticky. Zákazníci, kteří už mají nasazenou službu AD FS Device Registration Service, registrovaná zařízení ve svojí místní službě Active Directory nevidí. **To neplatí pro počítače s Windows ani zařízení Windows Phone**.

- **Musí splňovat** zásady dodržování předpisů, které jsou nasazené na toto zařízení.

- Pokud zařízení nevyhovuje nastavení podmíněného přístupu, zobrazí se uživateli po přihlášení jedna z následujících zpráv:
    - Pokud není zařízení zaregistrované v Intune nebo v Azure Active Directory, zobrazí se zpráva s pokyny k instalaci aplikace Portál společnosti, registraci zařízení a aktivaci e-mailu. Tento proces také přidruží ID protokolu Exchange ActiveSync zařízení k záznamu zařízení v Azure Active Directory.
    - Pokud zařízení není kompatibilní, zobrazí se zpráva, která uživatele přesměruje na web portálu společnosti Intune nebo na aplikaci Portál společnosti, kde může najít informace o problému a jeho řešení.

### <a name="support-for-mobile-devices"></a>Podpora mobilních zařízení

- Windows Phone 8.1 nebo novější
- Nativní e-mailová aplikace v systému iOS
- Poštovní klienti EAS, například Gmail v Androidu 4 a novějším
- Poštovní klienti EAS, **zařízení s pracovním profilem:** Pouze **Gmail** a **Nine Work pro Android Enterprise** v **pracovního profilu** jsou podporovány v zařízení s pracovním profilem. Aby v pracovních profilech Androidu fungoval podmíněný přístup, musíte nasadit e-mailový profil pro aplikaci Gmail nebo Nine Work for Android Enterprise a zároveň tyto aplikace nasadit jako povinnou instalaci.

> [!NOTE]
> Aplikace Microsoft Outlook pro Android a iOS se nepodporuje prostřednictvím místního konektoru Exchange. Pokud chcete využít zásady Azure Active Directory podmíněného přístupu a zásady ochrany aplikací Intune s aplikací Outlook pro iOS a Android poštovních schránek v místním, najdete [hybridní použití moderního ověřování v aplikaci Outlook pro iOS a Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth). 

### <a name="support-for-pcs"></a>Podpora počítačů

Nativní aplikace **Pošta** ve Windows 8.1 a novějších verzích (při registraci v Intune)


## <a name="configure-exchange-on-premises-access"></a>Konfigurace přístupu k místnímu Exchangi

1. Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2. Přejděte na **Intune** > **přístup k Exchangi**a pak vyberte **přístup k systému Exchange On-premises**. 

3. Na **Exchange přístup k místnímu** podokně zvolte **Ano** k *povolit místnímu Exchangi řízení přístupu*.

4. V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

5. Zvolte **Intune** a zobrazí se **řídicí panel Intune**.

6. Vyberte **Místní přístup**. V podokně **Místní přístup** se zobrazí stav zásad podmíněného přístupu a zařízení, na která má vliv.

7. V části **Správa** zvolte **Přístup k místnímu Exchangi**.

8. V podokně **Přístup k místnímu Exchangi** zvolte **Ano** a povolte tak řízení přístupu k místnímu Exchangi.

    > [!NOTE]
    > Pokud jste nenakonfigurovali místní konektor s protokolem Exchange Active Sync, je tato možnost zakázaná.  Před povolením podmíněného přístupu pro místní Exchange je nutné nejdříve nainstalovat a nakonfigurovat aspoň jeden konektor. Další podrobnosti najdete v tématu [Instalace místního Exchange Connectoru v Intune](exchange-connector-install.md).

9. V části **Přiřazení** zvolte **Zahrnuté skupiny**.  Použijte skupinu zabezpečení uživatelů, která by měla mít přiřazený podmíněný přístup. Tato akce vyžaduje, aby uživatelé zaregistrovali svoje zařízení v Intune a vyhověli podmínkám profilů pro dodržování předpisů.

10. Pokud chcete vyloučit určité skupiny uživatelů, můžete to udělat tak, že zvolíte **Vyloučené skupiny** a vyberete skupinu uživatelů, kterou chcete vyloučit z povinné registrace zařízení a dodržování předpisů.

11. Pokud chcete upravit výchozí e-mailovou zprávu, zvolte v části **Nastavení** možnost **Oznámení uživateli**. Tato zpráva se pošle uživatelům, pokud jejich zařízení nevyhovuje zásadám, a uživatelé chtějí získat přístup k místnímu Exchangi. Šablona zprávy používá jazyk využívající značky.  V průběhu psaní se zobrazí také náhled toho, jak bude zpráva vypadat.
    > [!TIP]
    > Další informace o jazyku využívajícím značky najdete v [článku](https://en.wikipedia.org/wiki/Markup_language) na Wikipedii.

12. V podokně **Upřesnit nastavení přístupu k Exchange ActiveSyncu** nastavte globální výchozí pravidlo pro přístup ze zařízení, která se nespravují v Intune, a pro pravidla na úrovni platformy, jak popisují další dva kroky.

8. U zařízení, na která nemá vliv podmíněný přístup ani další pravidla, můžete zvolit povolení přístupu k Exchangi, nebo tento přístup můžete zablokovat.

   - Pokud povolíte přístup, všechna zařízení mají okamžitě přístup k místnímu Exchangi.  U zařízení, která patří uživatelům v **zahrnutých skupinách**, se bude blokovat přístup v případě, že budou vyhodnocená jako zařízení, která nevyhovují zásadám nebo nejsou zaregistrovaná v Intune.
   - Při nastavení blokování přístupu se hned na začátku blokuje přístup na Exchange u všech zařízení.  Zařízení, která patří uživatelům v **zahrnutých skupinách**, získají přístup po registraci v Intune a jejich stav se vyhodnotí jako vyhovující zásadám. Zařízení s Androidem, která nepoužívají Samsung Knox Standard, jsou blokována vždy, protože nastavení nepodporují.

13. V části **Výjimky platformy zařízení** zvolte **Přidat** a určete platformy. Pokud je u nastavení **Nespravovaný přístup zařízení** nastavená možnost **Blokováno**, jsou zařízení, která jsou zaregistrovaná a vyhovují podmínkám zásad, povolená i tehdy, když existuje výjimka pro blokování platformy. Kliknutím na **OK** uložte nastavení.

14. V podokně **Místní** kliknutím na tlačítko **Uložit** uložte zásady podmíněného přístupu.

## <a name="create-azure-ad-conditional-access-policies-in-intune"></a>Vytvoření zásad podmíněného přístupu Azure AD v Intune

Podmíněný přístup je technologie Azure Active Directory (Azure AD). Uzel podmíněného přístupu, ke kterému se přistupuje z *Intune*, je stejný uzel, ke kterému se přistupuje z *Azure AD*.  

> [!IMPORTANT]
> Abyste mohli vytvořit zásady podmíněného přístupu Azure AD na portálu Intune Azure Portal, musíte mít licenci Azure AD Premium.

### <a name="to-create-a-conditional-access-policy"></a>Chcete-li vytvořit zásadu podmíněného přístupu

1. V **řídicí panel Intune**vyberte **podmíněného přístupu**.

2. V **zásady** vyberte **nové zásady** vytvoření nové Azure AD zásadu podmíněného přístupu.

## <a name="see-also"></a>Viz také:

[Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
