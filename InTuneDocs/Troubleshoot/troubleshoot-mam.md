---
title: "Řešení potíží se správou mobilních aplikací | Dokumentace Microsoftu"
description: "Toto téma popisuje některé tipy pro řešení potíží při nasazování podmíněného přístupu."
keywords: 
author: NathBarn
ms.author: oldang
manager: angerobe
ms.date: 09/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
translationtype: Human Translation
ms.sourcegitcommit: d50a5751a5afd987196336e9443dc5a429a283fd
ms.openlocfilehash: b333c0f5097fec38bf0dd78726a028fd7aaccd2f


---

# <a name="troubleshoot-mobile-application-management"></a>Řešení potíží se správou mobilních aplikací

Pokud máte problémy se správou mobilních aplikací Intune, začněte tady. Toto téma obsahuje některé běžné problémy a otázky, které může mít, a poskytuje řešení a odpovědi.

## <a name="common-it-administrator-issues"></a>Běžné problémy správců IT

1. **Problém:** Zásady ochrany aplikací bez registrace zařízení, vytvořené na portálu Azure Portal, se neuplatňují na aplikaci Skype pro firmy na zařízeních s iOSem a Androidem.

  **Řešení**: Pro Skype pro firmy se musí nastavit moderní ověřování.  Pokud chcete pro Skype nastavit moderní ověřování, řiďte se pokyny v tématu [Povolení tenanta pro moderní ověřování](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

2. **Problém:** Zásady ochrany aplikací se neuplatňují na žádné [podporované aplikace Office](https://www.microsoft.com/en-us/cloud-platform/microsoft-intune-partners) u žádného uživatele.

  **Řešení**: Zkontrolujte, jestli má uživatel licenci pro Intune a na aplikace Office cílí nasazené zásady ochrany aplikací. Než se nově nasazené zásady ochrany aplikací uplatní, může to trvat až 8 hodin.

3. **Problém:** Uživatel s oprávněním správce IT nemůže na portálu Azure Portal nakonfigurovat zásady ochrany aplikací.

  **Řešení:**

  K portálu Azure Portal mají přístup tyto role uživatelů:

  - Globální správce, kterého můžete nastavit na [Portálu Office](http://portal.office.com/)
  - Vlastník, kterého můžete nastavit na webu [Azure Portal](https://portal.azure.com/).
  - Přispěvatel, kterého můžete nastavit na webu [Azure Portal](https://portal.azure.com/).<br>

  Nápovědu k nastavení těchto rolí najdete v tématu [Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).

4. **Problém:** Sestavy z konzoly správce nezobrazují uživatelské účty, na které byly nedávno nasazeny zásady ochrany aplikací.

  **Řešení**: Než se uživatelé nově zacílení pomocí zásad ochrany aplikací zobrazí v sestavách jako cíloví uživatelé, může uplynout až 24 hodin.

5. **Problém:** Než se změny/aktualizace zásad projeví, může uplynout až 8 hodin.  

  **Řešení**: Koncový uživatel se může z aplikace odhlásit a znovu přihlásit, aby vynutil synchronizaci se službou.  

6. **Problém:** Zásady ochrany aplikací se nevztahují na zařízení v programu Apple DEP.

  **Řešení**: Zkontrolujte, jestli používáte Přidružení uživatele s Programem registrace zařízení Apple (DEP). Spřažení uživatelů je požadováno u všech aplikací vyžadujících ověření uživatele pod programem DEP.
Další informace o registraci DEP pro iOS najdete v tématu [Registrace zařízení s iOSem vlastněných společností do programu registrace zařízení DEP](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md).

## <a name="common-end-user-issues"></a>Běžné problémy koncových uživatelů

### <a name="issues-on-ios"></a>Problémy v iOS

Dialog / chybová zpráva | Příčina | Odstranění rizika |
-- | --- | --- |
**Nenastavena aplikace**: Tato aplikace zatím není nastavená tak, abyste ji mohli používat. O pomoc požádejte správce IT. | Nepodařilo se rozpoznat požadované zásady ochrany aplikací pro aplikaci. |Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací iOS a cílí na tuto aplikaci.
**Vítá vás Intune Managed Browser**: Tato aplikace funguje nejlépe, když je spravována službou Microsoft Intune. Aplikaci můžete kdykoli použít k procházení webu, a pokud k její správě použijete Microsoft Intune, získáte přístup k dalším funkcím ochrany dat. | Nepodařilo se rozpoznat požadované zásady ochrany aplikací pro aplikaci Intune Managed Browser. <br><br>Uživatel může aplikaci stále používat k procházení webu, ale aplikaci nespravuje Intune. | Zkontrolujte, jestli jsou ve skupině zabezpečení uživetele nasazené zásady ochrany aplikací pro iOS a cílí na aplikaci Intune Managed Browser.
**Přihlášení se nezdařilo**: Teď vás nemůžeme přihlásit. Zkuste to prosím znovu později. | Nepodařilo se zaregistrovat uživatele ke službě MAM po tom, co se uživatel pokusil přihlásit pomocí svého pracovního nebo školního účtu. | Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací iOS a cílí na tuto aplikaci.
**Nenastaven účet**: Vaše organizace nenastavila váš účet tak, aby měl přístup k pracovním nebo školním datům. Požádejte prosím o pomoc svého správce IT. | Uživatelský účet nemá licenci pro Intune A Direct. | Zkontrolujte, jestli má uživatelský účet přiřazenou licenci Intune v [portálu Office](http://portal.office.com).
**Zařízení nesplňuje požadavky**: Tuto aplikaci nejde použít, protože používáte zařízení s jailbreakem. Požádejte o pomoc správce IT. | Intune zjistil, že uživatel je na zařízení s jailbreakem. | Resetujte zařízení na výchozí tovární nastavení. Postupujte podle [těchto pokynů](https://support.apple.com/en-us/HT201274) z webu podpory Apple.
**Vyžaduje se připojení k internetu **: Musíte být připojení k internetu, abychom mohli ověřit, že můžete používat tuto aplikaci. | Zařízení není připojené k internetu. | Připojte zařízení k síti Wi-Fi nebo mobilní síti.
**Neznámé selhání**: Zkuste aplikaci restartovat. Pokud s tím budou dál problémy, požádejte o pomoc správce IT. | Došlo k neznámému selhání. | Chvíli počkejte a zkuste to znovu. Pokud chyba trvá, vytvořte [tady](/how-to-get-support-for-microsoft-intune.md) lístek podpory pomocí Intune.
**Přístup k datům vaší organizace**: Pracovní nebo školní účet, který jste zadali, nemá přístup k této aplikaci. Možná se budete muset přihlásit s jiným účtem. Požádejte o pomoc správce IT. | Intune zjistil, že se uživatel pokusil přihlásit pomocí druhého pracovního nebo školního účtu, který se liší od účtu pro zařízení zaregistrovaného do MAM. MAM může na jednom zařízení najednou spravovat jenom jeden pracovní nebo školní účet. | Ať se uživatel přihlásí pomocí účtu, jehož uživatelské jméno je na přihlašovací obrazovce předem vyplněné. <br> <br> Nebo nechte uživatele, ať se přihlásí pomocí nového pracovního nebo školního účtu, a odeberte stávající účet zaregistrovaný v MAM.
**Potíže s připojením**: Došlo k neočekávaným potížím s připojením. Zkontrolujte připojení a zkuste to znovu.  |  Došlo k neočekávanému selhání. | Chvíli počkejte a zkuste to znovu. Pokud chyba trvá, vytvořte [tady](/how-to-get-support-for-microsoft-intune.md) lístek podpory pomocí Intune.
**Výstraha**: Tuto aplikaci už nejde používat. O další informace požádejte správce IT. | Nepodařilo se ověřit certifikát aplikace. | Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Nainstalujte aplikaci znovu.
**Chyba**: V této aplikaci došlo k chybě a je potřeba ji zavřít. Pokud se bude tato chybová zpráva zobrazovat dál, obraťte se prosím na správce IT. | Nepodařilo se přečíst PIN kód aplikace MAM z řetězce klíčů Apple iOS. | Restartujte zařízení. Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Nainstalujte aplikaci znovu.


### <a name="issues-on-android"></a>Problémy v Androidu

Dialog / chybová zpráva | Příčina | Odstranění rizika |
-- | --- | --- |
**Nenastavena aplikace**: Tato aplikace zatím není nastavená tak, abyste ji mohli používat. Požádejte o pomoc správce IT. | Nepodařilo se rozpoznat požadované zásady ochrany aplikací pro aplikaci. |Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací iOS a cílí na tuto aplikaci.
**Aplikaci se nepodařilo spustit**: Při spouštění vaší aplikace se objevil problém. Zkuste aplikaci (nebo aplikaci Portál společnosti Intune) aktualizovat. Pokud potřebujete pomoc, obraťte se na správce IT. | Intune zjistil platné zásady ochrany aplikací pro aplikaci, ale aplikace selhává během inicializace MAM. | Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Zkontrolujte, jestli je na zařízení nainstalovaná aktuální aplikace Portál společnosti Intune a jestli je aktuální. <br><br> Pokud chyba trvá, pomocí aplikace Portál společnosti odešlete protokoly do Intune nebo [tady](/how-to-get-support-for-microsoft-intune.md) vytvořte lístek podpory.
**Nenašla se žádná aplikace**: Na tomto zařízení nejsou žádné aplikace, ve kterých by vaše organizace povolovala otevření tohoto obsahu. Požádejte o pomoc správce IT. | Uživatel se pokusil otevřít pracovní nebo školní data pomocí jiné aplikace, ale Intune nemůže najít žádné jiné spravované aplikace, které jsou k otevírání těchto dat povolené. | Zkontrolujte, jestli jsou ve skupině zabezpečení uživatele nasazené zásady ochrany aplikací pro Android a cílí aspoň na jednu další aplikaci povolenou v MAM, která může požadovaná data otevírat.
**Přihlášení se nezdařilo**: Zkuste se znovu přihlásit. Pokud s tím budou dál problémy, požádejte o pomoc správce IT. | Nepodařilo se ověřit účet, pomocí kterého se uživatel pokusil přihlásit. | Zkontrolujte, jestli se uživatel přihlašuje pomocí pracovního nebo školního účtu, který je už zaregistrovaný službou Intune MAM (první pracovní nebo školní účet, který se do této aplikace úspěšně přihlásil). <br><br> Vymažte data aplikace. <br><br> Zkontrolujte, jestli je verze aplikace aktuální. <br><br> Zkontrolujte, jestli je verze Portálu společnosti aktuální.
**Vyžaduje se připojení k internetu **: Musíte být připojení k internetu, abychom mohli ověřit, že můžete používat tuto aplikaci. | Zařízení není připojené k internetu. | Připojte zařízení k síti Wi-Fi nebo mobilní síti.
**Zařízení nesplňuje požadavky**: Tuto aplikaci nejde použít, protože používáte rootované zařízení. Požádejte o pomoc správce IT. | Intune zjistil, že uživatel je na rootovaném zařízení. | Resetujte zařízení na výchozí tovární nastavení.
**Nenastaven účet**: Tato aplikace se musí spravovat přes Microsoft Intune, ale nemáte nastavený účet. Požádejte o pomoc správce IT. | Uživatelský účet nemá licenci pro Intune A Direct. | Zkontrolujte, jestli má uživatelský účet přiřazenou licenci Intune v [portálu Office](http://portal.office.com).
**Aplikaci nejde zaregistrovat**: Tato aplikace se musí spravovat přes Microsoft Intune, ale momentálně jsme ji nemohli zaregistrovat. Požádejte o pomoc správce IT. Požádejte o pomoc správce IT. | Nepodařilo se aplikaci automaticky zaregistrovat ve službě MAM, když jsou požadovány zásady ochrany aplikací. | Vymažte data aplikace. <br><br> Odešlete protokoly do Intune prostřednictvím aplikace Portál společnosti nebo [tady](/how-to-get-support-for-microsoft-intune.md) vytvořte lístek podpory.





### <a name="see-also"></a>Viz taky
- [Jak ověřit nastavení správy mobilních aplikací](../deploy-use/validate-mobile-application-management.md)
- [Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)



<!--HONumber=Dec16_HO2-->


