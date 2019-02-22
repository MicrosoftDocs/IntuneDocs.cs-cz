---
title: Řešení potíží se správou mobilních aplikací
titlesuffix: Microsoft Intune
description: Toto téma popisuje některé tipy pro řešení potíží při nasazování podmíněného přístupu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 02/21/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ae8113a603ae4c091005f7c82045708f7e9e3e97
ms.sourcegitcommit: 8943848d47d5d5d6e44c74d414c34c5e3457862b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56655387"
---
# <a name="troubleshoot-mobile-application-management"></a>Řešení potíží se správou mobilních aplikací

Toto téma obsahuje řešení běžných problémů, ke kterým došlo při použití správy mobilních aplikací Intune.

Pokud tyto informace váš problém nevyřeší, přečtěte si téma [Jak získat podporu pro Microsoft Intune](get-support.md), ve kterém najdete další způsoby, jak získat nápovědu.

## <a name="common-it-administrator-issues"></a>Běžné problémy správců IT

Jedná se o běžné problémy, které správce IT může docházet při použití zásad ochrany aplikací Intune.

| Problém | Popis | Řešení |
| -- | -- | -- |
| Zásady se neuplatňují na Skype pro firmy. | Zásady ochrany aplikací bez registrace zařízení, vytvořené na portálu Azure Portal, se neuplatňují na aplikaci Skype pro firmy na zařízeních s iOSem a Androidem. | Pro Skype pro firmy se musí nastavit moderní ověřování.  Pokud chcete pro Skype nastavit moderní ověřování, řiďte se pokyny v tématu [Povolení tenanta pro moderní ověřování](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). |
| Zásady pro aplikace Office se neuplatňují. | Zásady ochrany aplikací se neuplatňují na žádné [podporované aplikace Office](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) u žádného uživatele. | Zkontrolujte, jestli má uživatel licenci pro Intune a jestli na aplikace Office cílí nasazené zásady ochrany aplikací. Než se nově nasazené zásady ochrany aplikací uplatní, může to trvat až 8 hodin. |
| Správce nemůže na portálu Azure Portal nakonfigurovat zásady ochrany aplikací. | Uživatel s oprávněním správce IT nemůže na portálu Azure Portal nakonfigurovat zásady ochrany aplikací. | K portálu Azure Portal mají přístup tyto role uživatelů: <ul><li>Globální správce, kterého můžete nastavit na [Portálu Office](https://portal.office.com/)</li><li>Vlastník, kterého můžete nastavit na webu [Azure Portal](https://portal.azure.com/).</li><li>Přispěvatel, kterého můžete nastavit na webu [Azure Portal](https://portal.azure.com/).</li></ul> Odkazovat na [řízení správy na základě rolí (RBAC) v Microsoft Intune](role-based-access-control.md) nápovědu k nastavení těchto rolí.|
|V sestavách zásad ochrany aplikací chybí uživatelské účty. | Sestavy z konzoly správce nezobrazují uživatelské účty, na které se nedávno nasadily zásady ochrany aplikací. | Než se uživatelé nově zacílení pomocí zásad ochrany aplikací zobrazí v sestavách jako cíloví uživatelé, může uplynout až 24 hodin. |
| Změny zásad se neuplatňují. | Než se změny a aktualizace zásad ochrany aplikací uplatní, může uplynout až 8 hodin. | Koncový uživatel se může z aplikace odhlásit a znovu přihlásit, aby vynutil synchronizaci se službou. |
| Zásady ochrany aplikace se neuplatňují na program DEP. | Zásady ochrany aplikací se nevztahují na zařízení v programu Apple DEP. | Zkontrolujte, jestli v programu Apple DEP (Device Enrollment Program) používáte přidružení uživatele. Spřažení uživatelů je požadováno u všech aplikací vyžadujících ověření uživatele pod programem DEP. <br><br>Odkazovat na [Automatická registrace zařízení s Iosem pomocí programu registrace zařízení společnosti Apple](device-enrollment-program-enroll-ios.md) Další informace o registrace DEP pro iOS.|
| Zásady pro přenos dat v iOSu nefungují. | Správa přenosu dat v iOSu pomocí zásad **Povolit aplikaci posílat data do jiných aplikací** a **Povolit aplikaci přijímat data z jiných aplikací** nefunguje správně. | Zobrazit [Správa přenosu dat mezi aplikacemi pro iOS v Microsoft Intune](data-transfer-between-apps-manage-ios.md). |

## <a name="common-end-user-issues"></a>Běžné problémy koncových uživatelů

Běžné problémy koncových uživatelů jsou rozdělené do následujících kategorií:

* **Scénáře při běžném používání**: Koncový uživatel se mohou vyskytnout scénářů v aplikacích používajících zásady ochrany aplikací Intune. Nejedná se o skutečné problémy, můžou ale být vnímané jako chyby.

* **Dialogy při běžném používání**: Jedná se o dialogy, které koncovému uživateli můžou zobrazovat v aplikacích používajících zásady ochrany aplikací Intune. Tyto zprávy a dialogy **neindikují** chybu.

* **Chybové zprávy a dialogy**: Toto jsou chybové zprávy a dialogy, které koncovému uživateli můžou zobrazovat v aplikacích používajících zásady ochrany aplikací Intune. Často indikují, že správce IT udělal při ochraně aplikací pro Intune nějakou chybu.

### <a name="normal-usage-scenarios"></a>Scénáře při běžném používání

Platforma | Scénář | Vysvětlení |
---| --- | --- |
iOS | Koncový uživatel může pomocí rozšíření pro sdílení v iOSu otevírat pracovní nebo školní data v nespravovaných aplikacích, a to i v případě, že je u zásad pro přenos dat nastavená možnost **Pouze spravované aplikace** nebo **Žádné aplikace**. Nemůže při tom dojít k úniku dat? | Zásady ochrany aplikací pro Intune nemůžou ovládat rozšíření pro sdílení v iOS, když dané zařízení nespravují. Proto **Intune „podniková“ data před jejich sdílením mimo příslušnou aplikaci zašifruje**. Můžete si to ověřit pokusem o otevření „podnikového“ souboru mimo spravovanou aplikaci. Soubor by měl být zašifrovaný a mimo spravovanou aplikaci by ho nemělo být možné otevřít.
Android | Proč je potřeba, aby si koncový uživatel **nainstaloval aplikaci Portál společnosti** i v případě, že používám ochranu aplikací MAM bez registrace zařízení?  | V Androidu je většina funkcí ochrany aplikací integrovaná do aplikace Portál společnosti. **Aplikace Portál společnosti se sice vyžaduje vždycky, ale registrace zařízení se nevyžaduje**. K ochraně aplikací bez registrace je jenom nutné, aby měl koncový uživatel aplikaci Portál společnosti na zařízení nainstalovanou.

### <a name="normal-usage-dialogs"></a>Dialogy při běžném používání

Platforma | Zpráva nebo dialog | Vysvětlení |
--- | --- | --- |
iOS, Android | **Přihlášení**: Pokud chcete chránit svá data, vaše organizace potřebuje ke správě této aplikace. Pokud budete chtít správu nastavit, přihlaste se svým pracovním nebo školním účtem. | Koncový uživatel musí přihlásit pomocí svého pracovního nebo školního účtu chcete-li použít tuto aplikaci, která vyžaduje zásady ochrany aplikací. Aby zásady začaly platit uživatel musí ověřit vůči Azure Active Directory.
iOS, Android |**Vyžadováno restartování**: Vaše organizace teď chrání svoje data v této aplikaci. Abyste mohli pokračovat, musíte aplikaci restartovat. | Aplikace právě přijala zásady ochrany aplikací Intune a musí se restartovat, aby zásady začaly platit.
iOS, Android |**Akce Nepovolena**: Vaše organizace povoluje pouze otevírat pracovní nebo školní data v této aplikaci. | Správce IT nastavil u zásady **Povolit aplikaci přijímat data z jiných aplikací** možnost **Pouze spravované aplikace**. Proto se koncový uživatel může přenášet data jenom do této aplikace z jiných aplikací, které mají zásady ochrany aplikací.
iOS, Android |**Akce Nepovolena**: Vaše organizace jenom povoluje přenést její data do ostatních spravovaných aplikací. | Správce IT nastavil u zásady **Povolit aplikaci posílat data do jiných aplikací** možnost **Pouze spravované aplikace**. Proto se koncový uživatel může přenášet data jenom z této aplikace do jiných aplikací, které mají zásady ochrany aplikací.
iOS, Android |**Vymazání výstrahy**: Vaše organizace odebrala svoje data související s touto aplikací. Pokud chcete pokračovat, restartujte aplikaci. | Správce IT pomocí ochrany aplikací pro Intune inicioval vymazání aplikace.
Android | **Firemní portál vyžaduje**: S touto aplikací používat svůj pracovní nebo školní účet, musíte nainstalovat aplikaci portál společnosti Intune. Klikněte na tlačítko "Přejít do obchodu" abyste mohli pokračovat. | V Androidu je většina funkcí ochrany aplikací integrovaná do aplikace Portál společnosti. **Aplikace Portál společnosti se sice vyžaduje vždycky, ale registrace zařízení se nevyžaduje**. K ochraně aplikací bez registrace stačí, aby měl koncový uživatel na zařízení nainstalovanou aplikaci Portál společnosti.

### <a name="error-messages-and-dialogs-on-ios"></a>Chybové zprávy a dialogy v iOS

Chybová zpráva nebo dialog | Příčina | Náprava |
-- | --- | --- |
**Nenastavena aplikace**: Tato aplikace není nastavený pro použití. Požádejte o pomoc správce IT. | Nepodařilo se rozpoznat požadované zásady ochrany aplikací pro aplikaci. |Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací iOS a cílí na tuto aplikaci.
**Vítá vás Intune Managed Browser**: Tato aplikace funguje nejlépe, když se spravují přes Microsoft Intune. Aplikaci můžete kdykoli použít k procházení webu, a pokud k její správě použijete Microsoft Intune, získáte přístup k dalším funkcím ochrany dat. | Nepodařilo se rozpoznat požadované zásady ochrany aplikací pro aplikaci Intune Managed Browser. <br><br>Uživatel může aplikaci stále používat k procházení webu, ale aplikaci nespravuje Intune. | Zkontrolujte, jestli jsou ve skupině zabezpečení uživetele nasazené zásady ochrany aplikací pro iOS a cílí na aplikaci Intune Managed Browser.
**Nepovedlo se přihlásit**: Nemůžeme přihlásit vás teď. Zkuste to prosím znovu později. | Nepodařilo se zaregistrovat uživatele ke službě MAM po tom, co se uživatel pokusil přihlásit pomocí svého pracovního nebo školního účtu. | Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací iOS a cílí na tuto aplikaci.
**Nenastaven účet**: Vaše organizace nenastavila váš účet k práci s pracovními nebo školními daty. Požádejte prosím o pomoc svého správce IT. | Uživatelský účet nemá licenci pro Intune A Direct. | Zkontrolujte, jestli má uživatelský účet přiřazenou licenci Intune v [portálu Office](https://portal.office.com).
**Zařízení nedodržující předpisy**: Tuto aplikaci nejde použít, protože používáte zařízení s jailbreakem. Požádejte o pomoc správce IT. | Intune zjistil, že uživatel je na zařízení s jailbreakem. | Resetujte zařízení na výchozí tovární nastavení. Postupujte podle [těchto pokynů](https://support.apple.com/HT201274) z webu podpory Apple.
**Připojení k Internetu vyžaduje**: Musíte být připojeni k Internetu, abychom mohli ověřit, že můžete používat tuto aplikaci. | Zařízení není připojené k internetu. | Připojte zařízení k síti Wi-Fi nebo mobilní síti.
**Došlo k neznámé chybě**: Zkuste aplikaci restartovat. Pokud s tím budou dál problémy, požádejte o pomoc správce IT. | Došlo k neznámému selhání. | Chvíli počkejte a zkuste to znovu. Pokud potíže potrvají, vytvořte [lístek podpory](get-support.md#create-an-online-support-ticket) s Intune.
**Přístup k datům vaší organizace**: Pracovní nebo školní účet, který jste zadali, nemá přístup k této aplikaci. Možná se budete muset přihlásit s jiným účtem. Požádejte o pomoc správce IT. | Intune zjistil, že se uživatel pokusil přihlásit pomocí druhého pracovního nebo školního účtu, který se liší od účtu pro zařízení zaregistrovaného do MAM. MAM může na jednom zařízení najednou spravovat jenom jeden pracovní nebo školní účet. | Ať se uživatel přihlásí pomocí účtu, jehož uživatelské jméno je na přihlašovací obrazovce předem vyplněné. <br> <br> Nebo nechte uživatele, ať se přihlásí pomocí nového pracovního nebo školního účtu, a odeberte stávající účet zaregistrovaný v MAM.
**Potíže s připojením**: Došlo k neočekávaným potížím s připojením. Zkontrolujte připojení a zkuste to znovu.  |  Došlo k neočekávanému selhání. | Chvíli počkejte a zkuste to znovu. Pokud potíže potrvají, vytvořte [lístek podpory](get-support.md#create-an-online-support-ticket) s Intune.
**Upozornění**: Tato aplikace je už nebude možné. O další informace požádejte správce IT. | Nepodařilo se ověřit certifikát aplikace. | Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Nainstalujte aplikaci znovu.
**Chyba**: Tato aplikace došlo k potížím a musíte zavřít. Pokud se bude tato chybová zpráva zobrazovat dál, obraťte se prosím na správce IT. | Nepodařilo se přečíst PIN kód aplikace MAM z řetězce klíčů Apple iOS. | Restartujte zařízení. Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Nainstalujte aplikaci znovu.

### <a name="error-messages-and-dialogs-on-android"></a>Chybové zprávy a dialogy v Androidu

Dialog / chybová zpráva | Příčina | Náprava |
-- | --- | --- |
**Nenastavena aplikace**: Tato aplikace není nastavený pro použití. Požádejte o pomoc správce IT. | Nepodařilo se rozpoznat požadované zásady ochrany aplikací pro aplikaci. |Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací pro Android a jestli cílí na tuto aplikaci.
**Aplikaci se nepodařilo spustit**: Došlo k nějakému problému spouštění vaší aplikace. Zkuste aplikaci (nebo aplikaci Portál společnosti Intune) aktualizovat. Pokud potřebujete pomoc, obraťte se na správce IT. | Intune zjistil platné zásady ochrany aplikací pro aplikaci, ale aplikace selhává během inicializace MAM. | Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Zkontrolujte, jestli je na zařízení nainstalovaná aktuální aplikace Portál společnosti Intune a jestli je aktuální. <br><br> Pokud potíže potrvají, můžete aplikaci portál společnosti odešlete protokoly do Intune, nebo vytvořte [lístek podpory](get-support.md#create-an-online-support-ticket).
**Nenašly se žádné aplikace**: Na tomto zařízení, které vaše organizace povolovala otevření tohoto obsahu nejsou žádné aplikace. Požádejte o pomoc správce IT. | Uživatel se pokusil otevřít pracovní nebo školní data pomocí jiné aplikace, ale Intune nemůže najít žádné jiné spravované aplikace, které jsou k otevírání těchto dat povolené. | Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací pro Android a cílí aspoň na jednu další aplikaci povolenou v MAM, která může požadovaná data otevírat.
**Nepovedlo se přihlásit**: Zkuste se přihlásit znovu. Pokud s tím budou dál problémy, požádejte o pomoc správce IT. | Nepodařilo se ověřit účet, pomocí kterého se uživatel pokusil přihlásit. | Zkontrolujte, jestli se uživatel přihlašuje pomocí pracovního nebo školního účtu, který je už zaregistrovaný službou Intune MAM (první pracovní nebo školní účet, který se do této aplikace úspěšně přihlásil). <br><br> Vymažte data aplikace. <br><br> Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Zkontrolujte, jestli je verze Portálu společnosti aktuální.
**Připojení k Internetu vyžaduje**: Musíte být připojeni k Internetu, abychom mohli ověřit, že můžete používat tuto aplikaci. | Zařízení není připojené k internetu. | Připojte zařízení k síti Wi-Fi nebo mobilní síti.
**Zařízení jako nevyhovující**: Tuto aplikaci nejde použít, protože používáte zařízení s rootem. Požádejte o pomoc správce IT. | Intune zjistil, že uživatel je na rootovaném zařízení. | Resetujte zařízení na výchozí tovární nastavení.
**Nenastaven účet**: Tato aplikace se musí spravovat přes Microsoft Intune, ale váš účet zatím není nastavené. Požádejte o pomoc správce IT. | Uživatelský účet nemá licenci pro Intune A Direct. | Zkontrolujte, jestli má uživatelský účet přiřazenou licenci Intune v [portálu Office](https://portal.office.com).
**Nepodařilo se zaregistrovat aplikaci**: Tato aplikace se musí spravovat přes Microsoft Intune, ale nebylo možné zaregistrovat v tuto chvíli. Požádejte o pomoc správce IT. | Nepodařilo se aplikaci automaticky zaregistrovat ve službě MAM, když jsou požadovány zásady ochrany aplikací. | Vymažte data aplikace. <br><br> Odešlete protokoly do Intune prostřednictvím aplikace portál společnosti nebo lístek podpory. Další informace najdete v tématu [jak získat podporu pro Microsoft Intune](get-support.md).

## <a name="next-steps"></a>Další postup

- [Jak ověřit nastavení správy mobilních aplikací](app-protection-policies-validate.md)
- Další informace o řešení potíží s Intune najdete v článku [Použití portálu pro řešení potíží k poskytování pomoci uživatelům ve vaší společnosti](help-desk-operators.md). 
- Zjistěte další informace o známých problémech v Microsoft Intune. Ty najdete v článku [Známé problémy v Microsoft Intune](known-issues.md).
- Potřebujete další pomoc? Přečtěte si téma [Jak získat podporu pro Microsoft Intune](get-support.md).
