---
title: Řešení potíží se správou mobilních aplikací
titleSuffix: Microsoft Intune
description: Toto téma popisuje některé tipy k odstraňování potíží pro nasazení podmíněného přístupu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/03/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9a272da470e206279e68077ce80324183c7a8227
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940459"
---
# <a name="troubleshoot-mobile-application-management"></a>Řešení potíží se správou mobilních aplikací

Toto téma obsahuje řešení běžných problémů, ke kterým došlo při použití Intune App Protection (označované také jako MAM nebo Správa mobilních aplikací).

Pokud tyto informace problém nevyřeší, přečtěte si téma [Jak získat podporu pro Microsoft Intune](../fundamentals/get-support.md) , kde najdete další informace o tom, jak získat nápovědu.

## <a name="common-it-administrator-issues"></a>Běžné problémy správců IT

Jedná se o běžné problémy, ke kterým může při používání zásad ochrany aplikací Intune docházet správce IT.

| Problém | Popis | Řešení |
| -- | -- | -- |
| Zásady neplatí pro Skype pro firmy. | Zásady ochrany aplikací bez registrace zařízení, které jsou v Azure Portal, se nevztahují na aplikaci Skype pro firmy na zařízeních s iOS a Androidem. | Pro Skype pro firmy se musí nastavit moderní ověřování.  Postupujte prosím podle pokynů v tématu [Povolení moderního ověřování pro tenanta](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) a nastavte moderní ověřování pro Skype. |
| Zásada aplikace Office se nepoužívá. | Zásady ochrany aplikací se nevztahují na žádnou z [podporovaných aplikací Office](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) pro žádného uživatele. | Potvrďte, že uživatel má licenci pro Intune a aplikace Office cílí na nasazené zásady ochrany aplikací. Aby bylo možné použít nově nasazené zásady ochrany aplikací, může trvat až 8 hodin. |
| Správce nemůže v Azure Portal nakonfigurovat zásady ochrany aplikací. | Uživatel správce IT nemůže v Azure Portal nakonfigurovat zásady ochrany aplikací. | Následující role uživatelů mají přístup k Azure Portal: <ul><li>Globální správce, který můžete nastavit v [centru pro správu Microsoft 365](https://admin.microsoft.com/)</li><li>Vlastník, který můžete nastavit v [Azure Portal](https://portal.azure.com/).</li><li>Přispěvatel, který můžete nastavit v [Azure Portal](https://portal.azure.com/).</li></ul> Nápovědu k nastavení těchto rolí najdete [v tématu řízení správy na základě rolí (RBAC) pomocí Microsoft Intune](../fundamentals/role-based-access-control.md) .|
|V sestavách zásad ochrany aplikací chybí uživatelské účty. | Sestavy konzoly správce nezobrazují uživatelské účty, na které byly nedávno nasazeny zásady ochrany aplikací. | Pokud je uživatel nově cílený zásadami ochrany aplikací, může trvat až 24 hodin, než se tento uživatel v sestavách zobrazí jako cílový uživatel. |
| Změny zásad nefungují. | Použití změn a aktualizací v zásadách ochrany aplikací může trvat až 8 hodin. | V případě potřeby se koncový uživatel může z aplikace odhlásit a znovu přihlásit, aby vynutil synchronizaci se službou. |
| Zásady ochrany aplikací nefungují s programem DEP | Zásady ochrany aplikací se nevztahují na zařízení Apple DEP. | Ujistěte se prosím, že používáte přidružení uživatele s Apple Program registrace zařízení (DEP). Přidružení uživatele se vyžaduje pro libovolnou aplikaci, která vyžaduje ověření uživatele v rámci programu DEP. <br><br>Další informace o registraci DEP pro iOS najdete v tématu [Automatická registrace zařízení s iOS pomocí program registrace zařízení společnosti Apple](../enrollment/device-enrollment-program-enroll-ios.md) .|
| Zásady přenosu dat nepracují se systémem iOS | Možnost **Povolit aplikaci přenášet data do jiných aplikací** a **Povolit aplikaci přijímat data z jiných aplikací** nespravuje přenos dat v iOS úspěšně. | Přečtěte si téma [Správa přenosu dat mezi aplikacemi pro iOS v Microsoft Intune](data-transfer-between-apps-manage-ios.md). |

## <a name="common-end-user-issues"></a>Běžné problémy koncových uživatelů

Běžné problémy koncových uživatelů jsou rozdělené do následujících kategorií:

* **Scénáře normálního použití**: koncový uživatel se může setkat s těmito scénáři u aplikací, které mají zásady ochrany aplikací Intune. Nejedná se o skutečné problémy, ale mohou být zjištěny jako chyby nebo chyby.

* **Dialogová okna pro normální využití**: Jedná se o dialogová okna použití, která se můžou zobrazovat koncovému uživateli v aplikacích, které mají zásady ochrany aplikací Intune. Tyto zprávy a dialogová okna **nenaznačují chybu** nebo chybu.

* **Chybové zprávy a dialogy**: Jedná se o chybové zprávy a dialogy, které se koncovému uživateli můžou zobrazovat v aplikacích, které mají zásady ochrany aplikací Intune. Tyto chyby se často označují tím, že správce IT nebo chyba se službou Intune App Protection vytvořila chyba.

### <a name="normal-usage-scenarios"></a>Běžné scénáře použití

Platforma | Scénář | Vysvětlení |
---| --- | --- |
iOS | Koncový uživatel může pomocí rozšíření pro sdílení v iOS otevírat pracovní nebo školní data v nespravovaných aplikacích, a to i v případě, že se zásady přenosu dat nastavily **jenom na spravované aplikace** nebo **žádné aplikace.** Nejedná se o nevrácená data? | Zásady ochrany aplikací Intune nemůžou řídit rozšíření sdílené složky iOS bez správy zařízení. Proto **Intune "Podniková" data před jejich sdílením mimo aplikaci zašifruje**. Můžete to ověřit tak, že se pokusíte otevřít soubor "Corporate" mimo spravovanou aplikaci. Soubor by měl být zašifrovaný a nemůže být otevřený mimo spravovanou aplikaci.
iOS | Proč se koncovým uživatelům **zobrazí výzva k instalaci aplikace Microsoft Authenticator** | To je potřeba v případě, že se používá podmíněný přístup na základě aplikace, přečtěte si téma [vyžadování schválené klientské aplikace](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access).
Android | Proč koncový uživatel **potřebuje nainstalovat aplikaci Portál společnosti**, i když používám ochranu aplikací mam bez registrace zařízení?  | V systému Android je většina funkcí ochrany aplikací integrovaná do aplikace Portál společnosti. **Registrace zařízení se nevyžaduje, i když je aplikace Portál společnosti vždycky povinná**. V případě ochrany aplikací bez registrace musí koncový uživatel mít v zařízení nainstalovanou aplikaci Portál společnosti.
iOS/Android | Zásady ochrany aplikací se nepoužívají při použití konceptu e-mailu v aplikaci Outlook. | Vzhledem k tomu, že Outlook podporuje podnikový i osobní kontext, nevynutilo MAM v konceptu e-mailu.
iOS/Android | Zásady ochrany aplikací se nepoužívají pro nové dokumenty v WXP (Word, Excel, PowerPoint) | Vzhledem k tomu, že WXP podporuje podnikový i osobní kontext, neuplatňuje MAM na nových dokumentech, dokud se neuloží do identifikovaného podnikového umístění, jako je OneDrive.
iOS/Android | Aplikace, které neumožňují možnost Uložit jako do místního úložiště, když je povolená zásada | Chování aplikace pro toto nastavení řídí vývojář aplikace.
Android | Android má více omezení než iOS, na kterých můžou nativní aplikace přistupovat k MAM chráněnému obsahu. | Android je otevřená platforma a "nativní" přidružení aplikace může změnit koncový uživatel na potenciálně nebezpečné aplikace. Použijte [výjimky zásad přenosu dat](app-protection-policies-exception.md) pro vyloučení konkrétních aplikací.
Android | Azure Information Protection (AIP) se může uložit jako PDF, pokud je zabráněno možnost Uložit jako. | AIP respektuje zásadu MAM pro možnost zakázat tisk při použití příkazu Uložit jako PDF.
iOS | Otevírání příloh PDF v aplikaci Outlook se nepovede a akce není povolená. | Tato situace může nastat, pokud se uživatel neověřil do aplikace Acrobat Reader pro Intune nebo použil k ověření v organizaci kryptografický otisk. Otevřete si aplikaci Acrobat Reader předem a proveďte ověření pomocí přihlašovacích údajů UPN.


### <a name="normal-usage-dialogs"></a>Dialogová okna pro normální využití

Platforma | Zpráva nebo dialog | Vysvětlení |
--- | --- | --- |
iOS, Android | **Přihlášení**: aby byla zajištěna ochrana svých dat, vaše organizace potřebuje tuto aplikaci spravovat. Tuto akci dokončíte tak, že se přihlásíte pomocí svého pracovního nebo školního účtu. | Aby bylo možné tuto aplikaci používat, musí se koncový uživatel přihlásit pomocí svého pracovního nebo školního účtu, který vyžaduje zásady ochrany aplikací. Aby se zásady daly použít, musí se uživatel ověřit proti Azure Active Directory.
iOS, Android |**Vyžadováno restartování**: vaše organizace teď chrání svá data v této aplikaci. Aby bylo možné pokračovat, je nutné aplikaci restartovat. | Aplikace přijala zásady ochrany aplikací Intune a je nutné ji restartovat, aby bylo možné zásady použít.
iOS, Android |**Akce není povolená**: vaše organizace vám v této aplikaci umožňuje otevřít jenom pracovní nebo školní data. | Správce IT nastavil, aby **aplikace přijímala data z jiných aplikací** jenom na **spravované aplikace**. Proto koncoví uživatelé můžou do této aplikace přenést data jenom z jiných aplikací, které mají zásady ochrany aplikací.
iOS, Android |**Akce není povolena**: vaše organizace umožňuje přenést data jenom do jiných spravovaných aplikací. | Správce IT nastavil, aby **aplikace povolovala přenos dat do jiných aplikací** **jenom na spravované aplikace**. Proto může koncový uživatel z této aplikace přenášet data jenom na jiné aplikace, které mají zásady ochrany aplikací.
iOS, Android |**Upozornění na vymazání**: vaše organizace odebrala svá data přidružená k této aplikaci. Pokud chcete pokračovat, restartujte aplikaci. | Správce IT inicioval vymazání aplikace pomocí ochrany aplikací Intune.
Android | **Portál společnosti požadováno**: Chcete-li použít svůj pracovní nebo školní účet s touto aplikací, je nutné nainstalovat aplikaci Portál společnosti Intune. Pokračujte kliknutím na tlačítko Přejít do obchodu. | V systému Android je většina funkcí ochrany aplikací integrovaná do aplikace Portál společnosti. **Registrace zařízení se nevyžaduje, i když je aplikace Portál společnosti vždycky povinná**. V případě ochrany aplikací bez registrace musí koncový uživatel mít v zařízení nainstalovanou aplikaci Portál společnosti.

### <a name="error-messages-and-dialogs-on-ios"></a>Chybové zprávy a dialogy v iOS

Chybová zpráva nebo dialog | příčina | Nápravy |
-- | --- | --- |
**Aplikace není nastavená**: Tato aplikace není nastavená, abyste ji mohli používat. Požádejte o nápovědu správce IT. | Nepovedlo se zjistit požadované zásady ochrany aplikací pro aplikaci. |Ujistěte se, že jsou do skupiny zabezpečení uživatele nasazené zásady ochrany aplikací pro iOS a cílí na tuto aplikaci.
**Vítá vás Intune Managed Browser**: Tato aplikace funguje nejlépe, když je spravovaná pomocí Microsoft Intune. Tuto aplikaci můžete vždy použít k procházení webu, a když je spravujete Microsoft Intune získáte přístup k dalším funkcím ochrany dat. | Nepovedlo se zjistit požadované zásady ochrany aplikací pro Intune Managed Browser aplikaci. <br><br>Uživatel může tuto aplikaci pořád používat k procházení webu, ale aplikace se nespravuje přes Intune. | Ujistěte se, že jsou do skupiny zabezpečení uživatele nasazené zásady ochrany aplikací pro iOS a cílí na Intune Managed Browser aplikaci.
**Přihlášení se nezdařilo**: nyní vás nemůžeme přihlásit. Zkuste to prosím znovu později. | Po pokusu uživatele o přihlášení pomocí pracovního nebo školního účtu se nepovedlo zaregistrovat uživatele ve službě MAM. | Ujistěte se, že jsou do skupiny zabezpečení uživatele nasazené zásady ochrany aplikací pro iOS a cílí na tuto aplikaci.
**Účet není nastavený**: vaše organizace nemá nastavený účet pro přístup k pracovním nebo školním datům. Požádejte o podporu svého správce IT. | Uživatelský účet nemá přímou licenci Intune. | Ujistěte se, že účet uživatele má přiřazenou licenci Intune v [centru pro správu Microsoft 365](https://admin.microsoft.com).
**Zařízení nedodržující předpisy**: tuto aplikaci nejde použít, protože používáte zařízení s jailbreakem. Požádejte o nápovědu správce IT. | Intune zjistil, že uživatel je na zařízení s jailbreakem. | Obnoví výchozí tovární nastavení zařízení. Postupujte podle [těchto pokynů](https://support.apple.com/HT201274) na webu podpory společnosti Apple.
**Vyžaduje se připojení k Internetu**: musíte být připojení k Internetu, abyste mohli ověřit, že můžete používat tuto aplikaci. | Zařízení není připojené k Internetu. | Připojte zařízení k síti Wi-Fi nebo k datové síti.
**Neznámá chyba**: zkuste tuto aplikaci restartovat. Pokud potíže potrvají, požádejte o podporu svého správce IT. | Došlo k neznámé chybě. | Chvíli počkejte a pak to zkuste znovu. Pokud chyba přetrvává, vytvořte [lístek podpory](../fundamentals/get-support.md#create-an-online-support-ticket) s Intune.
**Přístup k datům vaší organizace**: pracovní nebo školní účet, který jste zadali, nemá přístup k této aplikaci. Možná se budete muset přihlásit pomocí jiného účtu. Požádejte o nápovědu správce IT. | Intune rozpozná, že se uživatel pokusil přihlásit pomocí druhého pracovního nebo školního účtu, který se liší od MAM zaregistrovaného účtu pro dané zařízení. MAM může spravovat jenom jeden pracovní nebo školní účet pro každé zařízení. | Přihlaste se uživateli pomocí účtu, jehož uživatelské jméno je předem vyplněné přihlašovací obrazovkou. Možná budete muset [nakonfigurovat nastavení hlavního názvu uživatele (UPN) pro Intune](data-transfer-between-apps-manage-ios.md#configure-user-upn-setting-for-microsoft-intune-or-third-party-emm). <br> <br> Nebo se přihlaste k novému pracovnímu nebo školnímu účtu a odeberte stávající účet zaregistrovaný v MAM.
**Problém s připojením**: došlo k neočekávanému problému s připojením. Ověřte připojení a zkuste to znovu.  |  Neočekávaná chyba. | Chvíli počkejte a pak to zkuste znovu. Pokud chyba přetrvává, vytvořte [lístek podpory](../fundamentals/get-support.md#create-an-online-support-ticket) s Intune.
**Výstraha**: tuto aplikaci již nelze použít. Pro další informace se obraťte na správce IT. | Nepovedlo se ověřit certifikát aplikace. | Ujistěte se, že je verze aplikace aktuální. <br><br> Nainstalujte aplikaci znovu.
**Chyba**: v této aplikaci došlo k problému a je třeba ji zavřít. Pokud s tím budou dál problémy, obraťte se prosím na správce IT. | Nepovedlo se přečíst PIN kód aplikace MAM z řetězce klíčů Apple iOS. | Restartujte zařízení. Ujistěte se, že je verze aplikace aktuální. <br><br> Nainstalujte aplikaci znovu.

### <a name="error-messages-and-dialogs-on-android"></a>Chybové zprávy a dialogy v Androidu

Dialog/chybová zpráva | příčina | Nápravy |
-- | --- | --- |
**Aplikace není nastavená**: Tato aplikace není nastavená, abyste ji mohli používat. Požádejte o nápovědu správce IT. | Nepovedlo se zjistit požadované zásady ochrany aplikací pro aplikaci. |Ujistěte se, že jsou do skupiny zabezpečení uživatele nasazené zásady ochrany aplikací pro Android a cílí na tuto aplikaci.
**Nepovedlo se spustit aplikaci**: při spouštění aplikace došlo k potížím. Zkuste aplikaci nebo aplikaci Portál společnosti Intune aktualizovat. Pokud potřebujete pomáhat, obraťte se na správce IT. | Intune zjistil pro aplikaci platné zásady ochrany aplikací, ale během inicializace MAM dojde k chybě aplikace. | Ujistěte se, že je verze aplikace aktuální. <br><br> Ujistěte se, že je na zařízení nainstalovaná a aktuální aplikace Portál společnosti Intune. <br><br> Pokud chyba přetrvává, použijte aplikaci Portál společnosti k odeslání protokolů do Intune nebo vytvoření [lístku podpory](../fundamentals/get-support.md#create-an-online-support-ticket).
**Nenašly se žádné aplikace**: na tomto zařízení nejsou žádné aplikace, které vaše organizace umožňuje otevřít tento obsah. Požádejte o nápovědu správce IT. | Uživatel se pokusil otevřít pracovní nebo školní data s jinou aplikací, ale Intune nemůže najít žádné jiné spravované aplikace, které můžou data otevírat. | Zajistěte, aby byly do zabezpečení uživatele nasazené zásady ochrany aplikací pro Android a aby se zajistila aspoň jedna další aplikace s podporou MAM, která může otevřít příslušné údaje.
**Přihlášení se nepovedlo**: zkuste se znovu přihlásit. Pokud s tím budou dál problémy, požádejte o podporu svého správce IT. | Nepovedlo se ověřit účet, ke kterému se uživatel pokusil přihlásit. | Ujistěte se, že se uživatel přihlásí pomocí pracovního nebo školního účtu, který je už zaregistrovaný ve službě Intune MAM (první pracovní nebo školní účet, který se v této aplikaci úspěšně přihlásil). <br><br> Vymaže data aplikace. <br><br> Ujistěte se, že je verze aplikace aktuální. <br><br> Ujistěte se, že je verze Portál společnosti aktuální.
**Vyžaduje se připojení k Internetu**: musíte být připojení k Internetu, abyste mohli ověřit, že můžete používat tuto aplikaci. | Zařízení není připojené k Internetu. | Připojte zařízení k síti Wi-Fi nebo k datové síti.
**Zařízení nedodržující předpisy**: tuto aplikaci nejde použít, protože používáte zařízení s rootem. Požádejte o nápovědu správce IT. | Intune zjistil, že uživatel je na kořenovém zařízení. | Obnoví výchozí tovární nastavení zařízení.
**Účet není nastavený**: Tato aplikace musí být spravovaná pomocí Microsoft Intune, ale váš účet není nastavený. Požádejte o nápovědu správce IT. | Uživatelský účet nemá přímou licenci Intune. | Ujistěte se, že účet uživatele má přiřazenou licenci Intune v [centru pro správu Microsoft 365](https://admin.microsoft.com).
**Nepovedlo se zaregistrovat aplikaci**: tuto aplikaci musí spravovat Microsoft Intune, ale v tuto chvíli se nám nepovedlo zaregistrovat tuto aplikaci. Požádejte o nápovědu správce IT. | Pokud se vyžadují zásady ochrany aplikací, nemusíte aplikaci v rámci služby MAM automaticky registrovat. | Vymaže data aplikace. <br><br> Odešlete protokoly do Intune prostřednictvím aplikace Portál společnosti nebo souboru lístkem podpory. Další informace najdete v tématu [Jak získat podporu pro Microsoft Intune](../fundamentals/get-support.md).

## <a name="next-steps"></a>Další kroky

- [Ověřuje se nastavení správy mobilních aplikací.](app-protection-policies-validate.md)
- Naučte se používat soubory protokolu k řešení potíží se zásadami Intune App Protection, přečtěte si [https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Intune-app-protection-policy-using/ba-p/330372](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Intune-app-protection-policy-using/ba-p/330372) .
- Další informace o řešení potíží s Intune najdete v tématu [použití portálu pro řešení potíží k pomoc uživatelům ve vaší společnosti](../fundamentals/help-desk-operators.md). 
- Přečtěte si o známých problémech v Microsoft Intune. Další informace najdete v tématu [známé problémy v Microsoft Intune](../known-issues.md).
- Potřebujete další podporu? Další informace najdete v tématu [Jak získat podporu pro Microsoft Intune](../fundamentals/get-support.md).
