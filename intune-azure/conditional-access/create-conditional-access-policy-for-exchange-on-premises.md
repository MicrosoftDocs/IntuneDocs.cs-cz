---
title: "Vytvoření a přiřazení zásad podmíněného přístupu pro místní Exchange"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Jak nakonfigurovat podmíněný přístup pro místní Exchange v Intune a starší verze Exchange Online Dedicated v Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: c8715f96f532ee6bacda231e1147d03226ecbb48
ms.openlocfilehash: 2a011bf390bb55d685f580cfc782b21ff0c2ebd5
ms.lasthandoff: 04/26/2017


---

# <a name="how-to-create-and-assign-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated-in-microsoft-intune-azure-preview"></a>Vytvoření a přiřazení zásad podmíněného přístupu pro místní Exchange a starší verze Exchange Online Dedicated v Microsoft Intune Azure Preview

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Toto téma vás provede procesem konfigurace podmíněného přístupu pro místní Exchange založeného na dodržování předpisů zařízeními.

Pokud máte vyhrazené prostředí Exchange Online a potřebujete zjistit, jestli má novou, nebo starší verzi konfigurace, obraťte se na správce svého účtu. Pokud chcete řídit přístup k e-mailům v místním Exchangi nebo ve starším vyhrazeném prostředí Exchange Online, nakonfigurujte v Intune podmíněný přístup k místnímu Exchangi.

## <a name="before-you-begin"></a>Před zahájením

Než nakonfigurujete podmíněný přístup, ověřte, jestli jsou splněné tyto podmínky:

- Musíte mít **Exchange 2010 SP1 nebo novější**. Podporuje se pole serveru pro klientský přístup (CAS) serveru Exchange.

- Musíte použít [místní Exchange Connector s protokolem Exchange Active Sync](https://docs.microsoft.com/intune-azure/conditional-access/install-intune-on-premises-exchange-connector), který připojí Intune k místnímu Exchangi.

    >[!IMPORTANT]
    >Místní konektor Exchange je určený výhradně pro vašeho tenanta Intune a nedá se použít s žádným jiným tenantem. Také se ujistěte, že je konektor Exchange pro vašeho tenanta nainstalovaný jenom **na jednom počítači**.

- Konektor může být nainstalovaný na každém počítači, který má schopnost komunikovat se serverem Exchange.

- Tento konektor podporuje **prostředí Exchange CAS**. Z technického hlediska můžete konektor nainstalovat přímo na server Exchange CAS, ale nedoporučuje se to, protože to zvýší zátěž serveru. Při konfiguraci musíte konektor nastavit tak, aby komunikoval s jedním ze serverů Exchange CAS.

- Protokol **Exchange ActiveSync** je potřeba nakonfigurovat s ověřováním na základě certifikátů nebo zadávání přihlašovacích údajů uživateli.

- Pokud jsou pro určitého uživatele nakonfigurované zásady podmíněného přístupu, může se tento uživatel připojit k e-mailu teprve tehdy, když jeho **zařízení** splňuje tyto požadavky:
    - Musí být **zaregistrovaný** ve službě Intune nebo se musí jednat o počítač připojený k doméně.
    - **Musí být zaregistrované v Azure Active Directory**. Kromě toho musí být ve službě Azure Active Directory zaregistrované ID protokolu Exchange ActiveSync klienta.
<br></br>
- Pro zákazníky Intune a Office 365 je služba AAD DRS aktivovaná automaticky. Zákazníci, kteří už mají nasazenou službu AD FS Device Registration Service, registrovaná zařízení ve svojí místní službě Active Directory neuvidí. **To neplatí pro počítače s Windows ani zařízení Windows Phone**.

- **Musí splňovat** zásady dodržování předpisů, které jsou nasazené na toto zařízení.

- Pokud zařízení nevyhoví nastavení podmíněného přístupu, zobrazí se uživateli po přihlášení jedna z následujících zpráv:
    - Pokud není zařízení zaregistrované v Intune nebo v Azure Active Directory, zobrazí se zpráva s pokyny k instalaci aplikace Portál společnosti, registraci zařízení a aktivaci e-mailu. Tento proces také přidruží ID protokolu Exchange ActiveSync zařízení k záznamu zařízení v Azure Active Directory.
    - Pokud zařízení není kompatibilní, zobrazí se zpráva, která uživatele přesměruje na web portálu společnosti Intune nebo na aplikaci Portál společnosti, kde může najít informace o problému a jeho řešení.

### <a name="support-for-mobile-devices"></a>Podpora mobilních zařízení

- Windows Phone 8.1 nebo novější
- Nativní e-mailová aplikace v systému iOS
- Poštovní klienti EAS, například Gmail v Androidu 4 a novějším
- **Zařízení s Androidem for Work** se poštovními klienty EAS: Na zařízeních s Androidem for Work jsou v **pracovním profilu** podporované jenom aplikace **Gmail** a **Nine Work**. Aby v Androidu for Work fungoval podmíněný přístup, musíte nasadit e-mailový profil pro aplikaci Gmail nebo Nine Work a zároveň tyto aplikace nasadit jako požadovanou instalaci.

> [!NOTE]
> Aplikace Microsoft Outlook pro Android a iOS se nepodporuje. V současné době do tenantů Intune zavádíme Android for Work. Zavádění bude probíhat ještě několika dalších měsíců.

### <a name="support-for-pcs"></a>Podpora počítačů

Nativní aplikace **Pošta** ve Windows 8.1 a novějších verzích (při registraci v Intune)


## <a name="configure-exchange-on-premises-access"></a>Konfigurace přístupu k místnímu Exchangi

1. Přejděte na portál [Azure Portal](https://portal.azure.com/) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2. Po úspěšném přihlášení se zobrazí **řídicí panel Azure**.

3. V nabídce vlevo zvolte **Další služby** a do filtru textového pole pak zadejte **Intune**.

4. Zvolte **Intune** a zobrazí se **řídicí panel Intune**.

5.  Zvolte **Podmíněný přístup** a potom zvolte

6. V okně **Místní** se zobrazí stav zásad podmíněného přístupu a zařízení, na která má vliv.

7. V části **Správa** zvolte **Přístup k místnímu Exchangi**.

8. V okně **Přístup k místnímu Exchangi** zvolte **Ano** a povolte tak řízení přístupu k místnímu Exchangi.

      > [!NOTE]
      > Pokud jste nenakonfigurovali místní Exchange Connector s protokolem Exchange Active Sync, bude tato možnost zakázaná.  Před povolením podmíněného přístupu pro místní Exchange musíte nejdřív nainstalovat a nakonfigurovat tento konektor. Další podrobnosti najdete v tématu [Instalace místního Exchange Connectoru v Intune](install-intune-on-premises-exchange-connector.md).

9. V části **Přiřazení** zvolte **Zahrnuté skupiny**.  Použijte skupinu zabezpečení uživatelů, která by měla mít přiřazený podmíněný přístup. Bude to vyžadovat, aby uživatelé zaregistrovali svoje zařízení v Intune a vyhověli podmínkám profilů pro dodržování předpisů.

10. Pokud chcete vyloučit určité skupiny uživatelů, můžete to udělat tak, že zvolíte **Vyloučené skupiny** a vyberte skupinu uživatelů, kterou chcete vyloučit z povinné registrace zařízení a dodržování předpisů.

11. Pokud chcete upravit výchozí e-mailovou zprávu, zvolte v části **Nastavení** možnost **Oznámení uživateli**. Tato zpráva se pošle uživatelům, pokud jejich zařízení nevyhovuje zásadám, a uživatelé chtějí získat přístup k místnímu Exchangi. Šablona zprávy používá jazyk využívající značky.  V průběhu psaní se zobrazí také náhled toho, jak bude zpráva vypadat.
    > [!TIP]
    > Další informace o jazyku využívajícím značky najdete v [článku](https://en.wikipedia.org/wiki/Markup_language) na Wikipedii.

12. V okně **Upřesnit nastavení přístupu k Exchange ActiveSyncu** nastavte globální výchozí pravidlo pro přístup ze zařízení, která se nespravují v Intune, a pro pravidla na úrovni platformy, jak popisují další dva kroky.

13. U zařízení, na která nemá vliv podmíněný přístup ani další pravidla, můžete zvolit povolení přístupu k Exchangi, nebo tento přístup můžete zablokovat.
  - Pokud povolíte přístup, budou mít všechna zařízení okamžitě přístup k místnímu Exchangi.  U zařízení, která patří uživatelům v **zahrnutých skupinách**, se bude blokovat přístup v případě, že budou vyhodnocená jako zařízení, která nevyhovují zásadám nebo nejsou zaregistrovaná v Intune.
  - Při nastavení blokování přístupu se bude hned na začátku blokovat přístup na Exchange u všech zařízení.  Zařízení, která patří uživatelům v **zahrnutých skupinách**, budou mít přístup po registraci v Intune a jejich stav se vyhodnotí jako vyhovující zásadám. Zařízení s Androidem, která nepoužívají standard Samsung KNOX, se budou vždycky blokovat, protože nepodporují toto nastavení.
<br></br>
14. V části **Výjimky platformy zařízení** zvolte **Přidat** a určete platformy. Pokud je u nastavení **Nespravovaný přístup zařízení** nastavená možnost **Blokováno**, budou zařízení, která jsou zaregistrovaná a vyhovují podmínkám zásad, povolená i tehdy, když bude existovat výjimka pro blokování platformy. Kliknutím na **OK** uložte nastavení.

15. V okně **Místní** uložte kliknutím na tlačítko **Uložit** zásady podmíněného přístupu.

## <a name="create-azure-ad-conditional-access-policies-in-intune-azure-preview"></a>Vytvoření zásad podmíněného přístupu Azure AD v Intune Azure Preview

Počínaje verzí 1704 můžou správci vytvořit zásady podmíněného přístupu Azure AD v Intune Azure Preview. Má to tu výhodu, že se nemusí přepínat mezi úlohami Azure a Intune.

> [!IMPORTANT]
> Abyste mohli vytvořit zásady podmíněného přístupu Azure AD na portálu Intune Azure Preview, musíte mít licenci Azure AD Premium.

### <a name="to-create-azure-ad-conditional-access-policy"></a>Vytvoření zásad podmíněného přístupu Azure AD

1. Na **řídicím panelu Intune** zvolte **Podmíněný přístup**.

2. Na **řídicím panelu Podmíněný přístup** zvolte **Podmíněný přístup ve službě Azure Active Directory**.

3. Zvolte **Nové zásady** a vytvořte nové zásady podmíněného přístupu Azure AD.

    ![Zásady podmíněného přístupu Azure AD](../media/Azure-AD-CA-Intune.png)

## <a name="see-also"></a>Viz taky

[Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
