---
title: nastavení funkcí zařízení macOS v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se na nastavení pro konfiguraci zařízení macOS pro Protisk a přizpůsobení okna přihlášení k zobrazení nebo skrytí tlačítek napájení v Microsoft Intune. Podívejte se na postup, jak získat IP adresu, cestu a nastavení portu tiskového serveru v síti. Pomocí těchto nastavení můžete nakonfigurovat funkce zařízení macOS v profilu konfigurace zařízení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/16/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7a6c145d5c18a63be512b7fbaca7fae3c660872f
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71301789"
---
# <a name="macos-device-feature-settings-in-intune"></a>nastavení funkcí zařízení macOS v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune obsahuje některá vestavěná nastavení pro přizpůsobení funkcí na zařízeních macOS. Správci můžou například přidat tiskárny pro průchozí tisk, zvolit způsob, jakým se uživatelé přihlásí, konfigurovat řízení spotřeby, používat ověřování pomocí jednotného přihlašování a další.

Pomocí těchto funkcí můžete řídit zařízení macOS jako součást řešení správy mobilních zařízení (MDM).

Tento článek uvádí tato nastavení a popisuje, co jednotlivé nastavení dělá. V této části najdete taky postup pro získání IP adresy, cesty a portu pro tiskárny pro práci na tiskárně pomocí Terminálové aplikace (emulátor). Další informace o funkcích zařízení najdete v pro [Přidání nastavení funkcí zařízení se systémem iOS nebo MacOS](device-features-configure.md).

## <a name="before-you-begin"></a>Před zahájením

[Vytvořte profil konfigurace zařízení MacOS](device-features-configure.md).

> [!NOTE]
> Tato nastavení platí pro různé typy registrace s některými nastaveními, která platí pro všechny možnosti registrace. Další informace o různých typech registrace najdete v tématu [registrace MacOS](macos-enroll.md).

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-device-enrollment"></a>Nastavení platí pro: Registrace zařízení

- **IP adresa**: Zadejte adresu protokolu IPv4 nebo IPv6 tiskárny. Pokud k identifikaci tiskáren používáte názvy hostitelů, můžete získat IP adresu pomocí příkazového testu tiskárny v aplikaci Terminal. [Získat IP adresu a cestu](#get-the-ip-address-and-path) (v tomto článku) najdete další podrobnosti.
- **Cesta**: Zadejte cestu k tiskárně. Cesta je typicky `ipp/print` pro tiskárny v síti. [Získat IP adresu a cestu](#get-the-ip-address-and-path) (v tomto článku) najdete další podrobnosti.
- **Port** (iOS 11,0 a novější): Zadejte port naslouchání cíle přenosu. Pokud necháte tuto vlastnost prázdnou, použije se při tisku výchozí port.
- Protokol **TLS** (iOS 11,0 a novější): Vyberte **Povolit** , pokud chcete zabezpečit připojení přes tisk pomocí protokolu TLS (Transport Layer Security).

- **Přidat** Server pro Protisk. Můžete přidat spoustu tiskových serverů.

Můžete taky **importovat** textový soubor s oddělovači (. csv), který obsahuje seznam tiskáren pro průchozí tisk. Po přidání tiskáren pro tisk do Intune můžete také **exportovat** tento seznam.

### <a name="get-the-ip-address-and-path"></a>Získat IP adresu a cestu

Chcete-li přidat servery s modulem pro tisk, budete potřebovat IP adresu tiskárny, cestu k prostředku a port. Následující kroky ukazují, jak tyto informace získat.

1. Na Macu, který je připojený ke stejné místní síti (podsíti) jako tiskárny pro Protisk, otevřete **terminál** (z **/aplikace/Utility**).
2. V aplikaci Terminal App zadejte `ippfind`a vyberte Enter.

    Poznamenejte si informace o tiskárně. Například může vracet něco podobného jako `ipp://myprinter.local.:631/ipp/port1`. První část je název tiskárny. Poslední část (`ipp/port1`) je cesta prostředku.

3. V terminálu zadejte `ping myprinter.local`a vyberte Enter.

   Poznamenejte si IP adresu. Například může vracet něco podobného jako `PING myprinter.local (10.50.25.21)`.

4. Použijte hodnoty IP adresy a prostředku cesty. V tomto příkladu je IP adresa `10.50.25.21`a `/ipp/port1`cesta k prostředku.

## <a name="login-items"></a>Přihlašovací položky

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace

- **Soubory, složky a vlastní aplikace**: **Přidejte** cestu k souboru, složce, vlastní aplikaci nebo systémové aplikaci, kterou chcete otevřít, když se uživatel přihlásí k zařízení. Systémové aplikace nebo aplikace sestavené nebo přizpůsobené pro vaši organizaci jsou obvykle ve `Applications` složce s cestou `/Applications/AppName.app`podobnou. 

  Můžete přidat mnoho souborů, složek a aplikací. Zadejte například:  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Při přidávání libovolné aplikace, složky nebo souboru Nezapomeňte zadat správnou cestu. Ne všechny položky jsou ve `Applications` složce. Pokud uživatel přesune položku z jednoho umístění do druhé, cesta se změní. Tato přesunutá položka nebude otevřena, když se uživatel přihlásí.

## <a name="login-window"></a>Přihlašovací okno

### <a name="settings-apply-to-device-enrollment"></a>Nastavení platí pro: Registrace zařízení

#### <a name="window-layout"></a>Rozložení okna

- **Zobrazit další informace v řádku nabídek**: Když je vybraná časová oblast na panelu **nabídek, možnost** zobrazit zobrazuje název hostitele a verzi MacOS. **Není nakonfigurováno** (výchozí) nezobrazuje tyto informace na řádku nabídek.
- **Banner**: Zadejte zprávu, která se zobrazí na přihlašovací obrazovce zařízení. Zadejte například informace o vaší organizaci, uvítací zprávu, ztracené a zjištěné informace atd.
- **Vyberte formát přihlášení**: Vyberte, jak se uživatelé k zařízení přihlásí. Možnosti:
  - **Vyzvat k zadání uživatelského jména a hesla** (výchozí): Vyžaduje, aby uživatelé zadali uživatelské jméno a heslo.
  - **Seznam všech uživatelů, výzva k zadání hesla**: Vyžaduje, aby uživatelé vybrali své uživatelské jméno ze seznamu uživatelů, a pak zadali heslo. Také konfigurovat:

    - **Místní uživatelé**: Při **skrytí** se nezobrazí místní uživatelské účty v seznamu uživatelů, které mohou zahrnovat účty Standard a admin. Zobrazují se jenom účty uživatelů sítě a systému. **Není nakonfigurováno** (výchozí) zobrazí v seznamu uživatelů místní uživatelské účty.
    - **Mobilní účty**: Při **skrytí** se nezobrazí mobilní účty v seznamu uživatelů. **Není nakonfigurováno** (výchozí) zobrazí mobilní účty v seznamu uživatelů. Některé mobilní účty se můžou zobrazovat jako síťoví uživatelé.
    - **Uživatelé sítě**: Výběrem **Zobrazit zobrazíte** seznam uživatelů sítě v seznamu uživatelů. **Není nakonfigurováno** (výchozí) nezobrazí účty uživatelů sítě v seznamu uživatelů.
    - **Uživatelé s oprávněními správce**: Při **skrytí** se v seznamu uživatelů nezobrazují uživatelské účty správců. **Není nakonfigurováno** (výchozí) zobrazí účty uživatelů správce v seznamu uživatelů.
    - **Jiní uživatelé**: Vyberte **Zobrazit k zobrazení** seznamu **ostatní...** uživatelé v seznamu uživatelů. **Není nakonfigurováno** (výchozí) nezobrazuje ostatní uživatelské účty v seznamu uživatelů.

#### <a name="login-screen-power-settings"></a>Nastavení napájení přihlašovací obrazovky

- **Tlačítko vypnout**: Při **skrytí** se na přihlašovací obrazovce nezobrazí tlačítko vypnout. **Není nakonfigurováno** (výchozí) zobrazí tlačítko vypnout.
- **Tlačítko pro restartování**: Při **skrytí** se na přihlašovací obrazovce nezobrazí tlačítko restartovat. **Není nakonfigurováno** (výchozí) zobrazí tlačítko restartovat.
- **Tlačítko pro režim spánku**: Při **skrytí** se na přihlašovací obrazovce nezobrazí tlačítko režimu spánku. **Není nakonfigurováno** (výchozí) zobrazí tlačítko režimu spánku.

#### <a name="other"></a>Ostatní

- **Zakázat přihlášení uživatele z konzoly**: **Disable Disable** skryje příkaz MacOS, který se používá pro přihlášení. V případě typických uživatelů toto nastavení **zakažte** . **Není nakonfigurováno** (výchozí) umožňuje pokročilým uživatelům, aby se přihlásili pomocí příkazového řádku macOS. Chcete-li přejít do režimu konzoly `>console` , uživatelé zadají do pole uživatelské jméno a musí se ověřit v okně konzoly.

#### <a name="apple-menu"></a>Nabídka Apple

Až se uživatelé přihlásí k zařízením, následující nastavení budou mít vliv na to, co můžou dělat.

- **Zakázat vypnutí**: Možnost **Zakázat** : uživatelům zabránit v výběru možnosti **vypnutí** po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat položku nabídky **vypnutí** na zařízení.
- **Zakázat restart**: Možnost **Zakázat** : uživatelům zabránit v výběru možnosti **restartování** po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat položku nabídky **restartovat** na zařízení.
- **Zakázat**vypnutí: Při výběru možnosti **Zakázat** **budou uživatelé moci vybrat možnost vypnutí** po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat položku nabídky **napájení** v zařízení.
- **Zakázat odhlásit** se (macOS 10,13 a novější): Možnost **Zakázat** : uživatelům brání v výběru možnosti **odhlášení** po přihlášení uživatele. **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat položku nabídky **Odhlásit** se na zařízení.
- **Zakázat zamykací obrazovku** (macOS 10,13 a novější): Při výběru možnosti **Zakázat** budou uživatelé moci po přihlášení uživatele vybrat možnost **zamykací obrazovky** . **Není nakonfigurováno** (výchozí) umožňuje uživatelům vybrat položku nabídky **zamykací obrazovky** na zařízení.

## <a name="single-sign-on-app-extension"></a>Rozšíření aplikace s jednotným přihlašováním

Tato funkce platí pro:

- macOS 10,15 a novější

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace 

- **Typ rozšíření aplikace jednotného přihlašování**: Vyberte typ rozšíření aplikace jednotného přihlašování. Možnosti:

  - Nenakonfigurováno: Rozšíření aplikací se nepoužívají. Pokud chcete zakázat rozšíření aplikace jednotného přihlašování, přepněte typ rozšíření aplikace jednotného přihlašování z **protokolu Kerberos** nebo **přihlašovací údaje** na **Nenakonfigurováno**.
  - **Přihlašovací údaje**: K použití jednotného přihlašování použijte obecné přizpůsobitelné rozšíření aplikace přihlašovacích údajů. Ujistěte se, že znáte ID rozšíření a ID týmu pro rozšíření aplikace jednotného přihlašování ve vaší organizaci.  
  - **Protokol Kerberos**: Použijte integrované rozšíření protokolu Kerberos společnosti Apple, které je součástí macOS Catalina 10,15 a novějších. Tato možnost je verze rozšíření **přihlašovacích údajů** specifická pro Kerberos.

  > [!TIP]
  > Pomocí typu **přihlašovacích údajů** přidáte vlastní hodnoty konfigurace, které chcete předat prostřednictvím rozšíření. Místo toho zvažte použití předdefinovaného nastavení konfigurace poskytované společností Apple v typu **Kerberos** .

- **ID rozšíření** (Pouze přihlašovací údaje): Zadejte identifikátor sady prostředků, který identifikuje vaše rozšíření aplikace jednotného přihlašování `com.apple.ssoexample`, například.
- **ID týmu** (Pouze přihlašovací údaje): Zadejte identifikátor týmu rozšíření aplikace jednotného přihlašování. Identifikátor týmu je alfanumerický řetězec (čísla a písmena), který vygenerovala společnost Apple, `ABCDE12345`jako je například. 

  [Najít ID týmu](https://help.apple.com/developer-account/#/dev55c3c710c) (otevře se webová stránka společnosti Apple) obsahuje další informace.

- **Sféra**: Zadejte název sféry protokolu Kerberos. Název sféry by měl být velkými písmeny, `CONTOSO.COM`například. Název vaší sféry je typicky stejný jako název vaší domény DNS, ale jenom na velká písmena.
- **Domény**: Zadejte doménu nebo názvy hostitelů pro weby, které se dají ověřit pomocí jednotného přihlašování. Například pokud je `mysite.contoso.com`váš web, pak `mysite` je název hostitele a `contoso.com` je název domény. Když se uživatelé připojí k některé z těchto webů, aplikace App Extension zpracuje výzvu ověřování. Toto ověřování umožňuje uživatelům k přihlášení použít ID obličeje, dotykové ID nebo Apple PINCODE/přístupový kód.

  - Všechny domény v profilech služby Intune, které mají rozšíření pro aplikace jednotného přihlašování, musí být jedinečné. Doménu nemůžete opakovat v žádném profilu rozšíření aplikace pro přihlášení, i když používáte různé typy rozšíření aplikace jednotného přihlašování.
  - U těchto domén se nerozlišují velká a malá písmena.

- **Další konfigurace** (Pouze přihlašovací údaje): Zadejte další data specifická pro rozšíření, která chcete předat rozšíření aplikace jednotného přihlašování:
  - **Konfigurační klíč**: Zadejte název položky, kterou chcete přidat, například `user name`.
  - **Typ hodnoty**: Zadejte typ dat. Možnosti:

    - Řetězec
    - Datového Do **hodnoty konfigurace**zadejte `True` nebo `False`.
    - čísla Do **hodnoty konfigurace**zadejte číslo.
    
  - **Hodnota konfigurace**: Zadejte data.
  
  - **Přidat**: Tuto možnost vyberte, pokud chcete přidat konfigurační klíče.

- **Použití řetězce klíčů** (Jenom Kerberos): Vyberte možnost **blokovat** , pokud chcete zabránit ukládání a ukládání hesel do řetězce klíčů. **Není nakonfigurováno** (výchozí) umožňuje ukládat a ukládat hesla do řetězce klíčů.  
- **ID obličeje, dotykové ID nebo heslo** (Jenom Kerberos): **Vyžadovat** , aby uživatelé zadali své ID obličeje, dotykové ID nebo Apple heslo pro přihlášení k doménám, které jste přidali. **Není nakonfigurováno** (výchozí) nevyžaduje, aby uživatelé používali biometrika nebo heslo pro přihlášení.
- **Výchozí sféra** (Jenom Kerberos): Zvolením možnosti **Povolit** nastavte hodnotu **sféry** , kterou jste zadali jako výchozí sféru. **Není nakonfigurováno** (výchozí) nenastavuje výchozí sféru.

  > [!TIP]
  > - Toto nastavení **Povolte** , pokud konfigurujete více rozšíření aplikace pro jednotné přihlašování pomocí protokolu Kerberos ve vaší organizaci.
  > - Toto nastavení **Povolte** , pokud používáte více sfér. Nastaví hodnotu **sféry** , kterou jste zadali jako výchozí sféru.
  > - Pokud máte pouze jednu sféru, ponechte ji **nenakonfigurovanou** (výchozí).

- **Automatická konfigurace** (Jenom Kerberos): Pokud je nastaveno **blokování**, nebude rozšíření protokolu Kerberos automaticky používat protokol LDAP a DNS k určení názvu lokality služby Active Directory. **Není nakonfigurováno** (výchozí) umožňuje rozšíření automaticky najít název lokality služby Active Directory.
- **Změny hesla** (Jenom Kerberos): **Blok** zabraňuje uživatelům měnit hesla, která používají pro přihlášení k doménám, které jste zadali. **Není nakonfigurováno** (výchozí) povolí změny hesla.  
- **Synchronizace hesel** (Jenom Kerberos): Zvolením možnosti **Povolit** synchronizujete místní hesla uživatelů do služby Azure AD. **Není nakonfigurováno** (výchozí) zakáže synchronizaci hesel do služby Azure AD. Toto nastavení použijte jako alternativu nebo zálohu k jednotnému přihlašování. Toto nastavení nefunguje, pokud jsou uživatelé přihlášení pomocí mobilního účtu Apple.
- **Složitost hesla služby Active Directory systému Windows Server** (Jenom Kerberos): Vyberte **vyžadovat** , pokud chcete vynutit uživatelská hesla pro splnění požadavků na složitost hesla služby Active Directory. Další informace najdete v tématu [heslo musí splňovat požadavky na složitost](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements) . **Není nakonfigurováno** (výchozí) nevyžaduje, aby uživatelé splnili požadavky na heslo služby Active Directory.
- **Minimální délka hesla** (Jenom Kerberos): Zadejte minimální počet znaků, které mohou vytvořit heslo uživatele. **Není nakonfigurováno** (výchozí) nevynutila minimální délku hesla pro uživatele.
- **Omezení opakovaného použití hesla** (Jenom Kerberos): Zadejte počet nových hesel, od 1-24, které se musí použít, až bude možné znovu použít předchozí heslo v doméně. **Není nakonfigurováno** (výchozí) neuplatňuje limit opakovaného použití hesla.
- **Minimální stáří hesla** (Jenom Kerberos): Zadejte počet dní, po které musí být heslo v doméně použito, než ho uživatel může změnit. **Není nakonfigurováno** (výchozí) nevynutila minimální stáří hesla, než bude možné je změnit.
- **Oznámení o vypršení platnosti hesla** (Jenom Kerberos): Zadejte počet dní do vypršení platnosti hesla, po které uživatelé obdrží oznámení o vypršení platnosti hesla. **Není nakonfigurováno** (výchozí) používá `15` dny.
- **Vypršení platnosti hesla** (Jenom Kerberos): Zadejte počet dní, než bude nutné změnit heslo zařízení. **Není nakonfigurováno** (výchozí) znamená, že uživatelská hesla nikdy nevyprší.
- **Hlavní název** (Jenom Kerberos): Zadejte uživatelské jméno objektu zabezpečení protokolu Kerberos. Nemusíte zahrnovat název sféry. Například v `user@contoso.com`, `user` je hlavní název a `contoso.com` je název sféry.
- **Kód lokality služby Active Directory** (Jenom Kerberos): Zadejte název lokality služby Active Directory, kterou má rozšíření protokolu Kerberos použít. Tuto hodnotu pravděpodobně nebudete muset měnit, protože rozšíření protokolu Kerberos může automaticky najít kód lokality služby Active Directory.
- **Název mezipaměti** (Jenom Kerberos): Zadejte název obecné služby zabezpečení (GSS) mezipaměti protokolu Kerberos. Tuto hodnotu pravděpodobně nemusíte nastavovat.  
- **Zpráva požadavky na heslo** (Jenom Kerberos): Zadejte textovou verzi požadavků na heslo vaší organizace, které se zobrazují uživatelům. Zpráva se zobrazí, pokud nepožadujete požadavky na složitost hesla služby Active Directory nebo nezadáte minimální délku hesla.  
- **ID sady prostředků aplikace** (Jenom Kerberos): **Přidejte** identifikátory sady prostředků aplikace, které by měly používat jednotné přihlašování na vašich zařízeních. Těmto aplikacím je udělen přístup k lístku pro udělení lístku protokolu Kerberos, ověřovacímu lístku a ověřování uživatelů pro služby, kterým mají oprávnění k přístupu.
- **Mapování sféry domény** (Jenom Kerberos): **Přidejte** přípony DNS domény, které by měly být namapovány na vaši sféru. Toto nastavení použijte, pokud názvy DNS hostitelů neodpovídají názvu sféry. Pravděpodobně nemusíte vytvářet vlastní mapování domén na sféru.

## <a name="associated-domains"></a>Přidružené domény

V Intune můžete:

- Přidejte mnoho přidružení aplikace k doméně.
- Přidružte mnoho domén ke stejné aplikaci.

Tato funkce platí pro:

- macOS 10,15 a novější

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: Všechny typy registrace

- **ID aplikace**: Zadejte identifikátor aplikace, který se má přidružit k webu. Identifikátor aplikace zahrnuje ID týmu a ID sady: `TeamID.BundleID`.

  ID týmu je alfanumerické znaky (písmena a čísla) vygenerované společností Apple pro vývojáře aplikací, `ABCDE12345`jako je například. [Najděte své ID](https://help.apple.com/developer-account/#/dev55c3c710c) týmu (otevře web společnosti Apple) obsahuje další informace.

  ID sady prostředků jednoznačně identifikuje aplikaci a obvykle je ve formátu zpětného zápisu názvů domén. Například ID sady Finder je `com.apple.finder`. Pokud chcete najít ID sady, použijte AppleScript v terminálu:

  `osascript -e 'id of app "ExampleApp"'`

- **Doména**: Zadejte doménu webu, kterou chcete přidružit k aplikaci. Doména zahrnuje typ služby a plně kvalifikovaný název hostitele, `webcredentials:www.contoso.com`jako je například.

  Typ služby může být:

  - **authsrv**: Rozšíření aplikace s jednotným přihlašováním
  - **applink**: Univerzální propojení
  - **přihlašovací údaje**pro web: Automatické vyplnění hesla

- **Přidat**: Tuto možnost vyberte, pokud chcete přidat své aplikace a přidružené domény.

> [!TIP]
> Pokud chcete řešit potíže, otevřete na zařízení MacOS**profily** **Předvolby** > systému. Ověřte, že profil, který jste vytvořili, je v seznamu profily zařízení. Pokud je v seznamu uveden, ujistěte se, že je **Konfigurace přidružených domén** v profilu a obsahuje správné ID aplikace a domény.

## <a name="next-steps"></a>Další kroky

[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).

Můžete taky nakonfigurovat funkce zařízení v [iOS](ios-device-features-settings.md).
