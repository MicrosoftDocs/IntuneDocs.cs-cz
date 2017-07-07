---
title: "Použití vzdáleného vymazání při ochraně dat"
description: "Intune poskytuje možnosti selektivního a úplného vymazání, aby bylo možné odebrat citlivá firemní data a odebrat přístup k mnoha firemním prostředkům."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9d03f3936d608b9d526724eccbbdadbe030b53b8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="help-protect-your-data-with-full-or-selective-wipe-using-microsoft-intune"></a>Lepší ochrana dat s využitím plného nebo selektivního vymazání pomocí Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Ze zařízení spravovaných pomocí Intune, která už nejsou potřeba, mají se začít používat pro jiné účely nebo se ztratila, můžete vymazat aplikace a data. K tomuto účelu Intune poskytuje možnosti selektivního a úplného vymazání. Uživatelé také mohou odeslat příkaz ke vzdálenému vymazání zařízení z aplikace Portál společnosti Intune nainstalované na soukromých zařízeních zaregistrovaných v Intune.

  > [!NOTE]
  > Toto téma se věnuje jenom vymazání zařízení registrovaných ve správě mobilních zařízení Intune. K [vymazání firemních dat z aplikací](https://portal.azure.com) můžete také použít [portál Azure Portal](wipe-managed-company-app-data-with-microsoft-intune.md). Je rovněž možné [vyřadit počítače spravované klientským softwarem Intune](retire-a-windows-pc-with-microsoft-intune.md).

## <a name="full-wipe"></a>Úplné vymazání

**Úplné vymazání** na zařízení obnoví výchozí nastavení od výrobce a odebere všechna firemní a uživatelská data a nastavení. Zařízení se odebere ze služby Intune. Úplné vymazání je vhodné, když chcete zařízení resetovat, abyste ho mohli dát novému uživateli, nebo když došlo k jeho ztrátě nebo odcizení.  **Volbu úplného vymazání používejte velmi opatrně. Data v zařízení nejde obnovit.**


> [!Warning]
> Zařízení s Windows 10 RTM (zařízení se starším systémem než Windows 10 verze 1511) s méně než 4 GB paměti RAM mohou být po vymazání nedostupná. Pokud chcete získat přístup k zařízení s Windows 10, které nereaguje, použijte k jeho spuštění USB flash disk.

### <a name="remotely-wipe-a-device-from-the-intune-administrator-console"></a>Vzdálené vymazání zařízení z konzoly správce Intune

1.  Vyberte zařízení, která se mají vymazat. Můžete je vyhledat podle uživatele nebo podle zařízení.

    -   **Podle uživatele:**

        1.  V [konzole správce Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všichni uživatelé**.

        2.  Zvolte jméno uživatele, pro kterého chcete vymazat mobilní zařízení. Vyberte **Zobrazit vlastnosti**.

        3.  Na stránce **Vlastnosti** tohoto uživatele zvolte **Zařízení** a pak klikněte na název mobilního zařízení, které chcete vymazat. Pokud chcete vybrat více zařízení, použijte Ctrl + kliknutí.

    -   **Podle zařízení:**

        1.  V [konzole správce Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna mobilní zařízení**.

         ![Zahájení operace vymazání nebo vyřazení](../media/dev-sa-wipe.png)

        2.  Zvolte **Zařízení** a pak vyberte název mobilního zařízení, které chcete vymazat. Pokud chcete vybrat více zařízení, použijte Ctrl + kliknutí.

2.  Zvolte **Vyřadit z provozu či vymazat**.

3.  Zobrazí se zpráva, která žádá o potvrzení, že chcete zařízení vyřadit.

    -   Pokud chcete provést **selektivní vymazání**, které odebere jenom aplikace a data společnosti, zvolte **Ano**.

    -   Pokud chcete provést **úplné vymazání**, který vymaže všechny aplikace a data a vrátí zařízení do výchozího nastavení z výroby, zvolte **Před vyřazením z provozu zařízení vymazat**. Tato akce se vztahuje na všechny platformy kromě Windows 8.1. **Data odebraná pomocí úplného vymazání nejde obnovit**.

Pokud je zařízení zapnuté a připojené, trvá vymazání všech typů zařízení méně než 15 minut.

#### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Odstranění zařízení na portálu služby Azure Active Directory

1.  Přejděte na adresu [http://aka.ms/accessaad](http://aka.ms/accessaad) nebo zvolte **Správce** &gt; **Azure AD** na webu [https://portal.office.com](https://portal.office.com).

2.  Použijte odkaz v levé části stránky a přihlaste se pod svým ID organizace.

3.  Pokud nemáte předplatné Azure, vytvořte ho. Pokud máte placený účet, neměli byste potřebovat platební kartu ani zadání platby (zvolte odkaz pro předplatné **Zdarma zaregistrovat službu Azure Active Directory**).

4.  Vyberte možnost **Active Directory** a potom vyberte svoji organizaci.

5.  Vyberte kartu **Uživatelé** .

6.  Vyberte uživatele, jehož zařízení chcete odstranit.

7.  Zvolte **Zařízení**.

8.  Odeberte zařízení podle potřeby, třeba zařízení, která už se nepoužívají, nebo zařízení s nesprávnými definicemi.


## <a name="selective-wipe"></a>selektivní vymazání

**Selektivní vymazání** odebere ze zařízení firemní data, včetně případných dat správy mobilních aplikací (MAM), nastavení a e-mailových profilů. Při selektivním vymazání se osobní údaje uživatele na zařízení ponechají. Zařízení se odebere ze služby Intune. Následující tabulky popisují, jaká data se odeberou a jaký vliv má selektivní vymazání na zbývající data v zařízení (tabulky jsou uspořádané podle platformy).

**iOS**

|Datový typ|iOS|
|-------------|-------|
|Firemní aplikace a související data instalovaná službou Intune|Odinstalují se aplikace. Odeberou se data firemních aplikací.<br /><br />Odeberou se data aplikací z aplikací Microsoftu, které používají správu mobilních aplikací. Aplikace se neodebere.|
|Nastavení|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty jsou odebrané a odvolané.|
|Agent pro správu|Profil pro správu se odebere.|
|E-mailu|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune, a odstraní se e-maily uložené v mezipaměti zařízení. Pokud je Microsoft Exchange hostovaný na místním serveru, e-mailové profily a e-maily uložené v mezipaměti se neodeberou.|
|Outlook|Odeberou se e-maily přijaté aplikací Microsoft Outlook pro iOS.</br>Výjimka: Pokud je Exchange hostovaný na místním serveru, e-maily se neodeberou.|
|Zrušení služby Azure Active Directory (AAD)|Odebere se záznam AAD.|
|Kontakty | Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou.  Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. <br /> <br />V současné době se podporuje jen aplikace Outlook.

**Android**

|Datový typ|Android|Android Samsung KNOX Standard|
|-------------|-----------|------------------------|
|Webové odkazy|Odebrány.|Odebrány.|
|Nespravované aplikace Google Play|Aplikace a data zůstanou nainstalována.|Aplikace a data zůstanou nainstalována.|
|Nespravované obchodní aplikace|Aplikace a data zůstanou nainstalována.|Odinstalují se aplikace a následkem toho se odeberou i jejich místní data. Data mimo aplikaci (například na kartě SD) odebrána nebudou.|
|Spravované aplikace Google Play|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním MAM mimo aplikaci (například na kartě SD) zůstanou zašifrována, takže nepůjdou použít, ale odebrána nebudou.|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním MAM mimo aplikaci (například na kartě SD) zůstanou zašifrována, ale odebrána nebudou.|
|Spravované obchodní aplikace|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním MAM mimo aplikaci (například na kartě SD) zůstanou zašifrována, takže nepůjdou použít, ale odebrána nebudou.|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním MAM mimo aplikaci (například na kartě SD) zůstanou zašifrována, takže nepůjdou použít, ale odebrána nebudou.|
|Nastavení|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty se zruší, ale neodeberou.|Certifikáty se odeberou a zruší.|
|Agent pro správu|Zruší se oprávnění správce zařízení.|Zruší se oprávnění správce zařízení.|
|E-mailu|není k dispozici Viz položka Outlook.|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune, a odstraní se e-maily uložené v mezipaměti zařízení.|
|Outlook|E-mail přijatý aplikací Microsoft Outlook pro Android se odebere, ale pouze v případě, že je Outlook chráněný zásadami MAM. V opačném případě se Outlook při zrušení registrace nevymaže.</br>Výjimka: Pokud je Exchange hostovaný na místním serveru, e-maily se neodeberou.|E-mail přijatý aplikací Microsoft Outlook pro Android se odebere, ale pouze v případě, že je Outlook chráněný zásadami MAM. V opačném případě se Outlook při zrušení registrace nevymaže.</br>Výjimka: Pokud je Exchange hostovaný na místním serveru, e-maily se neodeberou.|
|Zrušení služby Azure Active Directory (AAD)|Odebere se záznam AAD.|Odebere se záznam AAD.|
|Kontakty | Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou.  Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. <br /> <br />V současné době se podporuje jen aplikace Outlook.|Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou.  Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. <br /> <br />V současné době se podporuje jen aplikace Outlook.

**Android for Work**

Při selektivním vymazání na zařízení Android for Work se odeberou všechna data, aplikace a nastavení v pracovním profilu na tomto zařízení. Zařízení se tím vyřadí ze správy pomocí Intune. U Androidu for Work se úplné vymazání nepodporuje.

**Windows**

|Datový typ|Windows 8.1 (MDM) a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Firemní aplikace a související data instalovaná službou Intune|U souborů chráněných systémem souborů EFS dojde ke zrušení klíče a uživatel nebude moct soubory otevírat.|Neodebere firemní aplikace.|Odinstalují se aplikace původně nainstalované prostřednictvím firemního portálu. Odeberou se data firemních aplikací.|Aplikace jsou odinstalovány a jsou odebrány klíče zkušebního načtení.|
|Nastavení|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|Odebrány.|Není podporováno.|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty se odeberou a zruší.|Certifikáty se odeberou a zruší.|Není podporováno.|Certifikáty se odeberou a zruší.|
|E-mailu|Odebere se e-mail se zapnutým systémem souborů EFS, včetně e-mailů a příloh aplikace Pošta pro Windows.|Není podporováno.|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune, a odstraní se e-maily uložené v mezipaměti zařízení.|Odebere se e-mail se zapnutým systémem souborů EFS, včetně e-mailů a příloh aplikace Pošta pro Windows. Odebere e-mailové účty, které byly zřízené Intune.</br>**Výjimka**: Pokud je Microsoft Exchange hostovaný na místním serveru, e-mailové účty se neodeberou.|
|Zrušení služby Azure Active Directory (AAD)|Ne.|Ne.|Odebere se záznam AAD.|Nelze použít. Systém Windows 10 nepodporuje selektivní vymazání zařízení připojených k Azure Active Directory.|

## <a name="wipe-encryption-file-system-efs-enabled-content"></a>Vymazání obsahu s povoleným šifrováním systému souborů EFS (Encryption File System)
Selektivní vymazání obsahu zašifrovaného systémem souborů EFS podporuje Windows 8.1 a Windows RT 8.1. Při selektivním vymazání obsahu s povoleným systémem souborů EFS platí následující body:

-   Selektivně se vymažou jenom aplikace a data, která jsou chráněná systémem souborů EFS ve stejné internetové doméně jako účet Intune. Další informace najdete v tématu [Selektivní vymazání ve Windows pro správu dat na zařízeních](http://technet.microsoft.com/library/dn486874.aspx)

-   Pokud u domény přidružené k systému souborů EFS dojde ke změnám, může trvat až 48 hodin, než se aplikace a data využívající tuto novou doménu selektivně vymažou.

-   Vymažou se všechny domény, které je zaregistrované ve službě Intune.

Mezi data a aplikace, u kterých se aktuálně podporuje selektivní vymazání systému souborů EFS, patří:

-   Aplikace Pošta pro Windows

-   Pracovní složky

-   Soubory a složky zašifrované systémem souborů EFS. Další informace najdete v článku [Osvědčené postupy pro systém souborů EFS](http://support.microsoft.com/kb/223316).

-   Pokud vaše organizace udržuje svou identitu ve službě Active Directory, musí používat nástroj synchronizace adresářů (DirSync) k synchronizaci informací do AAD, aby selektivní vymazání pro systém souborů EFS fungovalo správně.  Další informace o nástroji DirSync najdete v tématu [Scénář synchronizace adresářů](http://technet.microsoft.com/library/dn441212.aspx) v dokumentaci služby Azure Active Directory.

## <a name="monitor-retire-wipe-and-delete-actions"></a>Sledování akcí vyřazení z provozu, vymazání a odstranění
Získání sestavy s vyřazenými, vymazanými nebo odstraněnými zařízeními:

1.  V [konzole správce Intune](https://manage.microsoft.com/) zvolte **Sestavy** &gt; **Sestavy historie zařízení**.

2.  Zadejte počáteční a koncové datum sestavy a zvolte **Zobrazit sestavu**.

Sestava také zobrazuje, kdo akci provedl.

### <a name="see-also"></a>Viz taky
[Vyřazení zařízení](retire-devices-from-microsoft-intune-management.md)

[Selektivní vymazání ve Windows pro správu dat na zařízeních](http://technet.microsoft.com/library/dn486874.aspx)
