---
title: "Řešení potíží se správou mobilních aplikací"
description: "Toto téma popisuje některé tipy pro řešení potíží při nasazování podmíněného přístupu."
keywords: 
author: oydang
ms.author: oydang
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: 15baae06398d135557439c0e67b50f7e1326b6fe
ms.sourcegitcommit: 468480b61110ca81f737582ebbefd4efda6fd667
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2018
---
# <a name="troubleshoot-mobile-application-management"></a>Řešení potíží se správou mobilních aplikací

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Pokud máte problémy se správou mobilních aplikací Intune, začněte tady. Toto téma obsahuje některé běžné problémy a otázky, které může mít, a poskytuje řešení a odpovědi.

Pokud tyto informace váš problém nevyřeší, přečtěte si téma [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md), ve kterém najdete další způsoby, jak získat nápovědu.


## <a name="common-it-administrator-issues"></a>Běžné problémy správců IT

Jedná se o běžné problémy, ke kterým může docházet, když správce IT používá zásady ochrany aplikací pro Intune.

| Problém | Popis | Řešení |
| -- | -- | -- |
| Zásady se neuplatňují na Skype pro firmy. | Zásady ochrany aplikací bez registrace zařízení, vytvořené na portálu Azure Portal, se neuplatňují na aplikaci Skype pro firmy na zařízeních s iOSem a Androidem. | Pro Skype pro firmy se musí nastavit moderní ověřování.  Pokud chcete pro Skype nastavit moderní ověřování, řiďte se pokyny v tématu [Povolení tenanta pro moderní ověřování](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). |
| Zásady pro aplikace Office se neuplatňují. | Zásady ochrany aplikací se neuplatňují na žádné [podporované aplikace Office](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) u žádného uživatele. | Zkontrolujte, jestli má uživatel licenci pro Intune a jestli na aplikace Office cílí nasazené zásady ochrany aplikací. Než se nově nasazené zásady ochrany aplikací uplatní, může to trvat až 8 hodin. |
| Správce nemůže na portálu Azure Portal nakonfigurovat zásady ochrany aplikací. | Uživatel s oprávněním správce IT nemůže na portálu Azure Portal nakonfigurovat zásady ochrany aplikací. | K portálu Azure Portal mají přístup tyto role uživatelů: <ul><li>Globální správce, kterého můžete nastavit na [Portálu Office](http://portal.office.com/)</li><li>Vlastník, kterého můžete nastavit na webu [Azure Portal](https://portal.azure.com/).</li><li>Přispěvatel, kterého můžete nastavit na webu [Azure Portal](https://portal.azure.com/).</li></ul>  Nápovědu k nastavení těchto rolí najdete v tématu [Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).|
|V sestavách zásad ochrany aplikací chybí uživatelské účty. | Sestavy z konzoly správce nezobrazují uživatelské účty, na které se nedávno nasadily zásady ochrany aplikací. | Než se uživatelé nově zacílení pomocí zásad ochrany aplikací zobrazí v sestavách jako cíloví uživatelé, může uplynout až 24 hodin. |
| Změny zásad se neuplatňují. | Než se změny a aktualizace zásad ochrany aplikací uplatní, může uplynout až 8 hodin. | Koncový uživatel se může z aplikace odhlásit a znovu přihlásit, aby vynutil synchronizaci se službou. |
| Zásady ochrany aplikace se neuplatňují na program DEP. | Zásady ochrany aplikací se nevztahují na zařízení v programu Apple DEP. | Zkontrolujte, jestli v programu Apple DEP (Device Enrollment Program) používáte přidružení uživatele. Spřažení uživatelů je požadováno u všech aplikací vyžadujících ověření uživatele pod programem DEP. <br><br>Další informace o registraci DEP pro iOS najdete v tématu [Registrace zařízení s iOSem vlastněných společností do programu registrace zařízení DEP](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md).|
| Zásady pro přenos dat v iOSu nefungují. | Správa přenosu dat v iOSu pomocí zásad **Povolit aplikaci posílat data do jiných aplikací** a **Povolit aplikaci přijímat data z jiných aplikací** nefunguje správně. | Přečtěte si téma [Správa přenosu dat mezi aplikacemi pro iOS pomocí Microsoft Intune](/deploy-use/manage-data-transfer-between-ios-apps-with-microsoft-intune.md). |






## <a name="common-end-user-issues"></a>Běžné problémy koncových uživatelů

Běžné problémy koncových uživatelů jsou rozdělené do následujících kategorií:

* **Scénáře při běžném používání**: Koncový uživatel se s těmito scénáři může setkat v aplikacích používajících zásady ochrany aplikací pro Intune. Nejedná se o skutečné problémy, můžou ale být vnímané jako chyby.

* **Dialogy při běžném používání**: Jedná se o dialogy, které se koncovému uživateli můžou zobrazovat v aplikacích používajících zásady ochrany aplikací pro Intune. Tyto zprávy a dialogy **neindikují** chybu.

* **Chybové zprávy a dialogy**: Jedná se o chybové zprávy a dialogy, které se koncovému uživateli můžou zobrazovat v aplikacích používajících zásady ochrany aplikací pro Intune. Často indikují, že správce IT udělal při ochraně aplikací pro Intune nějakou chybu.



### <a name="normal-usage-scenarios"></a>Scénáře při běžném používání

Platforma | Scénář | Vysvětlení |
---| --- | --- |
iOS | Koncový uživatel může pomocí rozšíření pro sdílení v iOSu otevírat pracovní nebo školní data v nespravovaných aplikacích, a to i v případě, že je u zásad pro přenos dat nastavená možnost **Pouze spravované aplikace** nebo **Žádné aplikace**. Nemůže při tom dojít k úniku dat? | Zásady ochrany aplikací pro Intune nemůžou ovládat rozšíření pro sdílení v iOS, když dané zařízení nespravují. Proto **Intune „podniková“ data před jejich sdílením mimo příslušnou aplikaci zašifruje**. Můžete si to ověřit pokusem o otevření „podnikového“ souboru mimo spravovanou aplikaci. Soubor by měl být zašifrovaný a mimo spravovanou aplikaci by ho nemělo být možné otevřít.
Android | Proč je potřeba, aby si koncový uživatel **nainstaloval aplikaci Portál společnosti** i v případě, že používám ochranu aplikací MAM bez registrace zařízení?  | V Androidu je většina funkcí ochrany aplikací integrovaná do aplikace Portál společnosti. **Aplikace Portál společnosti se sice vyžaduje vždycky, ale registrace zařízení se nevyžaduje**. K ochraně aplikací bez registrace je jenom nutné, aby měl koncový uživatel aplikaci Portál společnosti na zařízení nainstalovanou.

### <a name="normal-usage-dialogs"></a>Dialogy při běžném používání

Platforma | Zpráva nebo dialog | Vysvětlení |
--- | --- | --- |
iOS, Android | **Přihlášení**: Aby mohla organizace chránit svoje data, musí tuto aplikaci spravovat. Pokud budete chtít správu nastavit, přihlaste se svým pracovním nebo školním účtem. | Aby mohl koncový uživatel používat tuto aplikaci, která vyžaduje zásady ochrany aplikací, musí se přihlásit svým pracovním nebo školním účtem. Aby zásady začaly platit, je nutné, aby se uživatel ověřil v Azure Active Directory.
iOS, Android |**Vyžadováno restartování**: Organizace teď chrání svoje data v této aplikaci. Abyste mohli pokračovat, musíte aplikaci restartovat. | Aplikace právě přijala zásady ochrany aplikací pro Intune a musí se restartovat,aby zásady začaly platit.
iOS, Android |**Akce nepovolena**: Vaše organizace vám v této aplikaci umožňuje otevřít jenom pracovní nebo školní data. | Správce IT nastavil u zásady **Povolit aplikaci přijímat data z jiných aplikací** možnost **Pouze spravované aplikace**. Koncový uživatel proto může do této aplikace přenášet data jenom z aplikací, které používají zásady ochrany aplikací.
iOS, Android |**Akce nepovolena**: Vaše organizace povoluje přenést její data jenom do jiných spravovaných aplikací. | Správce IT nastavil u zásady **Povolit aplikaci posílat data do jiných aplikací** možnost **Pouze spravované aplikace**. Koncový uživatel proto může z této aplikace přenášet data jenom do aplikací, které používají zásady ochrany aplikací.
iOS, Android |**Upozornění na vymazání**: Vaše organizace odebrala svoje data související s touto aplikací. Pokud chcete pokračovat, restartujte aplikaci. | Správce IT pomocí ochrany aplikací pro Intune inicioval vymazání aplikace.
Android | **Vyžaduje se aplikace Portál společnosti**: Pokud chcete s touto aplikací používat svůj pracovní nebo školní účet, musíte si nainstalovat aplikaci Portál společnosti Intune. Pokračujte klepnutím na Přejít do obchodu. | V Androidu je většina funkcí ochrany aplikací integrovaná do aplikace Portál společnosti. **Aplikace Portál společnosti se sice vyžaduje vždycky, ale registrace zařízení se nevyžaduje**. K ochraně aplikací bez registrace stačí, aby měl koncový uživatel na zařízení nainstalovanou aplikaci Portál společnosti.


### <a name="error-messages-and-dialogs-on-ios"></a>Chybové zprávy a dialogy v iOS


Chybová zpráva nebo dialog | Příčina | Odstranění rizika |
-- | --- | --- |
**Nenastavena aplikace**: Tato aplikace zatím není nastavená tak, abyste ji mohli používat. O pomoc požádejte správce IT. | Nepodařilo se rozpoznat požadované zásady ochrany aplikací pro aplikaci. |Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací iOS a cílí na tuto aplikaci.
**Vítá vás Intune Managed Browser**: Tato aplikace funguje nejlépe, když je spravována službou Microsoft Intune. Aplikaci můžete kdykoli použít k procházení webu, a pokud k její správě použijete Microsoft Intune, získáte přístup k dalším funkcím ochrany dat. | Nepodařilo se rozpoznat požadované zásady ochrany aplikací pro aplikaci Intune Managed Browser. <br><br>Uživatel může aplikaci stále používat k procházení webu, ale aplikaci nespravuje Intune. | Zkontrolujte, jestli jsou ve skupině zabezpečení uživetele nasazené zásady ochrany aplikací pro iOS a cílí na aplikaci Intune Managed Browser.
**Přihlášení se nezdařilo**: Teď vás nemůžeme přihlásit. Zkuste to prosím znovu později. | Nepodařilo se zaregistrovat uživatele ke službě MAM po tom, co se uživatel pokusil přihlásit pomocí svého pracovního nebo školního účtu. | Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací iOS a cílí na tuto aplikaci.
**Nenastaven účet**: Vaše organizace nenastavila váš účet tak, aby měl přístup k pracovním nebo školním datům. Požádejte prosím o pomoc svého správce IT. | Uživatelský účet nemá licenci pro Intune A Direct. | Zkontrolujte, jestli má uživatelský účet přiřazenou licenci Intune v [portálu Office](http://portal.office.com).
**Zařízení nesplňuje požadavky**: Tuto aplikaci nejde použít, protože používáte zařízení s jailbreakem. Požádejte o pomoc správce IT. | Intune zjistil, že uživatel je na zařízení s jailbreakem. | Resetujte zařízení na výchozí tovární nastavení. Postupujte podle [těchto pokynů](https://support.apple.com/HT201274) z webu podpory Apple.
**Vyžaduje se připojení k internetu** : Musíte být připojení k internetu, abychom mohli ověřit, že můžete používat tuto aplikaci. | Zařízení není připojené k internetu. | Připojte zařízení k síti Wi-Fi nebo mobilní síti.
**Neznámé selhání**: Zkuste aplikaci restartovat. Pokud s tím budou dál problémy, požádejte o pomoc správce IT. | Došlo k neznámému selhání. | Chvíli počkejte a zkuste to znovu. Pokud chyba trvá, vytvořte [tady](how-to-get-support-for-microsoft-intune.md) lístek podpory pomocí Intune.
**Přístup k datům vaší organizace**: Pracovní nebo školní účet, který jste zadali, nemá přístup k této aplikaci. Možná se budete muset přihlásit s jiným účtem. Požádejte o pomoc správce IT. | Intune zjistil, že se uživatel pokusil přihlásit pomocí druhého pracovního nebo školního účtu, který se liší od účtu pro zařízení zaregistrovaného do MAM. MAM může na jednom zařízení najednou spravovat jenom jeden pracovní nebo školní účet. | Ať se uživatel přihlásí pomocí účtu, jehož uživatelské jméno je na přihlašovací obrazovce předem vyplněné. <br> <br> Nebo nechte uživatele, ať se přihlásí pomocí nového pracovního nebo školního účtu, a odeberte stávající účet zaregistrovaný v MAM.
**Potíže s připojením**: Došlo k neočekávaným potížím s připojením. Zkontrolujte připojení a zkuste to znovu.  |  Došlo k neočekávanému selhání. | Chvíli počkejte a zkuste to znovu. Pokud chyba trvá, vytvořte [tady](how-to-get-support-for-microsoft-intune.md) lístek podpory pomocí Intune.
**Výstraha**: Tuto aplikaci už nejde používat. O další informace požádejte správce IT. | Nepodařilo se ověřit certifikát aplikace. | Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Nainstalujte aplikaci znovu.
**Chyba**: V této aplikaci došlo k chybě a je potřeba ji zavřít. Pokud se bude tato chybová zpráva zobrazovat dál, obraťte se prosím na správce IT. | Nepodařilo se přečíst PIN kód aplikace MAM z řetězce klíčů Apple iOS. | Restartujte zařízení. Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Nainstalujte aplikaci znovu.


### <a name="error-messages-and-dialogs-on-android"></a>Chybové zprávy a dialogy v Androidu

Dialog / chybová zpráva | Příčina | Odstranění rizika |
-- | --- | --- |
**Nenastavena aplikace**: Tato aplikace zatím není nastavená tak, abyste ji mohli používat. Požádejte o pomoc správce IT. | Nepodařilo se rozpoznat požadované zásady ochrany aplikací pro aplikaci. |Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací pro Android a jestli cílí na tuto aplikaci.
**Aplikaci se nepodařilo spustit**: Při spouštění vaší aplikace se objevil problém. Zkuste aplikaci (nebo aplikaci Portál společnosti Intune) aktualizovat. Pokud potřebujete pomoc, obraťte se na správce IT. | Intune zjistil platné zásady ochrany aplikací pro aplikaci, ale aplikace selhává během inicializace MAM. | Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Zkontrolujte, jestli je na zařízení nainstalovaná aktuální aplikace Portál společnosti Intune a jestli je aktuální. <br><br> Pokud chyba trvá, pomocí aplikace Portál společnosti odešlete protokoly do Intune nebo [tady](how-to-get-support-for-microsoft-intune.md) vytvořte lístek podpory.
**Nenašla se žádná aplikace**: Na tomto zařízení nejsou žádné aplikace, ve kterých by vaše organizace povolovala otevření tohoto obsahu. Požádejte o pomoc správce IT. | Uživatel se pokusil otevřít pracovní nebo školní data pomocí jiné aplikace, ale Intune nemůže najít žádné jiné spravované aplikace, které jsou k otevírání těchto dat povolené. | Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací pro Android a cílí aspoň na jednu další aplikaci povolenou v MAM, která může požadovaná data otevírat.
**Přihlášení se nezdařilo**: Zkuste se znovu přihlásit. Pokud s tím budou dál problémy, požádejte o pomoc správce IT. | Nepodařilo se ověřit účet, pomocí kterého se uživatel pokusil přihlásit. | Zkontrolujte, jestli se uživatel přihlašuje pomocí pracovního nebo školního účtu, který je už zaregistrovaný službou Intune MAM (první pracovní nebo školní účet, který se do této aplikace úspěšně přihlásil). <br><br> Vymažte data aplikace. <br><br> Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Zkontrolujte, jestli je verze Portálu společnosti aktuální.
**Vyžaduje se připojení k internetu** : Musíte být připojení k internetu, abychom mohli ověřit, že můžete používat tuto aplikaci. | Zařízení není připojené k internetu. | Připojte zařízení k síti Wi-Fi nebo mobilní síti.
**Zařízení nesplňuje požadavky**: Tuto aplikaci nejde použít, protože používáte zařízení s rootem. Požádejte o pomoc správce IT. | Intune zjistil, že uživatel je na rootovaném zařízení. | Resetujte zařízení na výchozí tovární nastavení.
**Nenastaven účet**: Tato aplikace se musí spravovat přes Microsoft Intune, ale nemáte nastavený účet. Požádejte o pomoc správce IT. | Uživatelský účet nemá licenci pro Intune A Direct. | Zkontrolujte, jestli má uživatelský účet přiřazenou licenci Intune v [portálu Office](http://portal.office.com).
**Aplikaci nejde zaregistrovat**: Tato aplikace se musí spravovat přes Microsoft Intune, ale momentálně jsme ji nemohli zaregistrovat. Požádejte o pomoc správce IT. Požádejte o pomoc správce IT. | Nepodařilo se aplikaci automaticky zaregistrovat ve službě MAM, když jsou požadovány zásady ochrany aplikací. | Vymažte data aplikace. <br><br> Odešlete protokoly do Intune prostřednictvím aplikace Portál společnosti nebo [tady](how-to-get-support-for-microsoft-intune.md) vytvořte lístek podpory.




### <a name="see-also"></a>Viz taky
- [Jak ověřit nastavení správy mobilních aplikací](../deploy-use/validate-mobile-application-management.md)
- [Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md)
