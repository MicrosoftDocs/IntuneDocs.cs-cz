---
title: "Zásady podmíněného přístupu pro místní Exchange | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Jak nakonfigurovat podmíněný přístup pro místní Exchange v Intune a starší verze Exchange Online Dedicated v Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 581f9be824ea883fd0208abc3b2ecc09174cb911
ms.openlocfilehash: a80d6a19948291cc80e42ad5a9a2f016effb2f37


---

# <a name="how-to-create-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated-in-microsoft-intune-azure-preview"></a>Vytvoření zásad podmíněného přístupu pro místní Exchange a starší verze Exchange Online Dedicated v Microsoft Intune Azure Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Toto téma vás provede procesem konfigurace podmíněného přístupu pro místní Exchange založeného na dodržování předpisů zařízeními.

Pokud máte vyhrazené prostředí Exchange Online a potřebujete zjistit, jestli má novou, nebo starší verzi konfigurace, obraťte se na správce svého účtu. Pokud chcete řídit přístup k e-mailům v místním Exchangi nebo ve starším vyhrazeném prostředí Exchange Online, nakonfigurujte v Intune podmíněný přístup k místnímu Exchangi.

## <a name="prerequisites"></a>Požadavky

**Před tím**, než nakonfigurujete podmíněný přístup, ověřte, jestli jsou splněné tyto podmínky:

- Musíte mít **Exchange 2010 nebo novější**. Podporuje se pole serveru pro klientský přístup (CAS) serveru Exchange.
- Musíte použít **místní Exchange Connector s protokolem Exchange Active Sync**, který připojí Intune k místnímu Microsoft Exchangi. Podrobné informace o konektoru najdete v tématu <link>.

  - Místní konektor Exchange dostupný v konzole Intune je určený výhradně pro vašeho klienta Intune a nedá se použít s žádným jiným klientem. Také se ujistěte, že je konektor Exchange pro vašeho klienta nainstalovaný jenom **na jednom počítači**.

Tento konektor by se měl stáhnout z konzoly správce Intune. Návod ke konfiguraci místního konektoru Exchange najdete v tématu <link to new topic>.

Konektor může být nainstalovaný na každém počítači, který má schopnost komunikovat se serverem Exchange.

- Tento konektor podporuje **prostředí Exchange CAS**. Z technického hlediska můžete konektor nainstalovat přímo na server Exchange CAS, ale nedoporučuje se to, protože to zvýší zátěž serveru. Při konfiguraci musíte konektor nastavit tak, aby komunikoval s jedním ze serverů Exchange CAS.
- Protokol **Exchange ActiveSync** je potřeba nakonfigurovat s ověřováním na základě certifikátů nebo zadávání přihlašovacích údajů uživateli.

Pokud jsou pro určitého uživatele nakonfigurované zásady podmíněného přístupu, může se tento uživatel připojit k e-mailu teprve tehdy, když jeho **zařízení** splňuje tyto požadavky:

- Musí být **zaregistrovaný** ve službě Intune nebo se musí jednat o počítač připojený k doméně.
- **Musí být zaregistrované v Azure Active Directory**. Kromě toho musí být ve službě Azure Active Directory zaregistrované ID protokolu Exchange ActiveSync klienta.

Pro zákazníky Intune a Office 365 je služba AAD DRS aktivovaná automaticky. Zákazníci, kteří už mají nasazenou službu AD FS Device Registration Service, registrovaná zařízení ve svojí místní službě Active Directory neuvidí. **To neplatí pro počítače s Windows ani zařízení Windows Phone**.

- Musí **vyhovovat** veškerým zásadám dodržování předpisů nasazeným na toto zařízení.

Pokud zařízení nevyhoví nastavení podmíněného přístupu, zobrazí se uživateli po přihlášení jedna z následujících zpráv:

- Pokud není zařízení zaregistrované v Intune nebo v Azure Active Directory, zobrazí se zpráva s pokyny k instalaci aplikace Portál společnosti, registraci zařízení a aktivaci e-mailu. Tento proces také přidruží ID protokolu Exchange ActiveSync zařízení k záznamu zařízení v Azure Active Directory.
- Pokud zařízení není kompatibilní, zobrazí se zpráva, která uživatele přesměruje na web portálu společnosti Intune nebo na aplikaci Portál společnosti, kde může najít informace o problému a jeho řešení.

## <a name="support-for-mobile-devices"></a>Podpora mobilních zařízení

- Windows Phone 8.1 nebo novější
- Nativní e-mailová aplikace v systému iOS
- Poštovní klienti EAS, například Gmail v Androidu 4 a novějším
- **Zařízení s Androidem for Work** se poštovními klienty EAS: Na zařízeních s Androidem for Work jsou v **pracovním profilu** podporované jenom aplikace **Gmail** a **Nine Work**. Aby v Androidu for Work fungoval podmíněný přístup, musíte nasadit e-mailový profil pro aplikaci Gmail nebo Nine Work a zároveň tyto aplikace nasadit jako požadovanou instalaci.

>[!NOTE]
>Aplikace Microsoft Outlook pro Android a iOS se nepodporuje.

> V současné době do tenantů Intune zavádíme Android for Work. Zavádění bude probíhat ještě několika dalších měsíců.

Další informace o stavu podpory pro Android for Work získáte v oznámení Androidu for Work v tématu [Co je nového v Microsoft Intune](https://docs.microsoft.com/en-us/intune/whats-new/whats-new-archive#october-2016) ve verzi z října 2016.

## <a name="support-for-pcs"></a>Podpora počítačů

Aplikace **Pošta** ve Windows 8.1 a novějších verzích (při registraci v Intune)


## <a name="configure-exchange-on-premises-access"></a>Konfigurace přístupu k místnímu Exchangi

1. Zvolte úlohu **Podmíněný přístup** na portálu Azure Portal a otevřete tak okno Místní.
2. V okně **Místní** se zobrazí stav zásad podmíněného přístupu a zařízení, na která má vliv.
3. V části **Správa** zvolte **Přístup k místnímu Exchangi**.
4. V okně **Přístup k místnímu Exchangi** zvolte **Ano** a povolte tak řízení přístupu k místnímu Exchangi.

  >[!NOTE]
  >Pokud jste nenakonfigurovali místní Exchange Connector s protokolem Exchange Active Sync, bude tato možnost zakázaná.  Před povolením podmíněného přístupu pro místní Exchange musíte nejdřív nainstalovat a nakonfigurovat tento konektor. Další podrobnosti najdete v tématu [Instalace místního Exchange Connectoru v Intune](install-intune-on-premises-exchange-connector.md).

5. V části **Přiřazení** zvolte **Zahrnuté skupiny**.  Použijte skupinu zabezpečení uživatelů, která by měla mít přiřazený podmíněný přístup.  Bude to vyžadovat, aby uživatelé zaregistrovali svoje zařízení v Intune a vyhověli podmínkám profilů pro dodržování předpisů.
6. Pokud chcete vyloučit určité skupiny uživatelů, můžete to udělat tak, že zvolíte **Vyloučené skupiny** a vyberte skupinu uživatelů, kterou chcete vyloučit z povinné registrace zařízení a dodržování předpisů.
7. Pokud chcete upravit výchozí e-mailovou zprávu, zvolte v části **Nastavení** možnost **Oznámení uživateli**. Tato zpráva se pošle uživatelům, pokud jejich zařízení nevyhovuje zásadám, a uživatelé chtějí získat přístup k místnímu Exchangi. Šablona zprávy používá jazyk využívající značky.  V průběhu psaní se zobrazí také náhled toho, jak bude zpráva vypadat. Další informace o jazyku využívajícím značky najdete v [článku](https://en.wikipedia.org/wiki/Markup_language) na Wikipedii.
8. V okně **Upřesnit nastavení přístupu k Exchange ActiveSyncu** nastavte globální výchozí pravidlo pro přístup ze zařízení, která se nespravují v Intune, a pro pravidla na úrovni platformy, jak popisují další dva kroky.
9. U zařízení, na která nemá vliv podmíněný přístup ani další pravidla, můžete zvolit povolení přístupu k Exchangi, nebo tento přístup můžete zablokovat.
  - Pokud povolíte přístup, budou mít všechna zařízení okamžitě přístup k místnímu Exchangi.  U zařízení, která patří uživatelům v **zahrnutých skupinách**, se bude blokovat přístup v případě, že budou vyhodnocená jako zařízení, která nevyhovují zásadám nebo nejsou zaregistrovaná v Intune.
  - Při nastavení blokování přístupu se bude hned na začátku blokovat přístup na Exchange u všech zařízení.  Zařízení, která patří uživatelům v **zahrnutých skupinách**, budou mít přístup po registraci v Intune a jejich stav se vyhodnotí jako vyhovující zásadám. Zařízení s Androidem, která nepoužívají standard Samsung KNOX, se budou vždycky blokovat, protože nepodporují toto nastavení.
10. V části **Výjimky platformy zařízení** zvolte **Přidat** a určete platformy. Pokud je u nastavení **Nespravovaný přístup zařízení** nastavená možnost **Blokováno**, budou zařízení, která jsou zaregistrovaná a vyhovují podmínkám zásad, povolená i tehdy, když bude existovat výjimka pro blokování platformy. Kliknutím na **OK** uložte nastavení.
11. V okně **Místní** uložte kliknutím na tlačítko **Uložit** zásady podmíněného přístupu.



<!--HONumber=Feb17_HO1-->


