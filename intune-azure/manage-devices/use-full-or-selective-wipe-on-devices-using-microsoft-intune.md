---
title: "Úplné nebo selektivní vymazání zařízení pomocí Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si, jak provést selektivní vymazání firemních dat v zařízení nebo úplné vymazání, které obnoví zařízení do továrního nastavení."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 22e188e81f2bc278045bb0988642b1b68372d6af
ms.lasthandoff: 02/18/2017


---

# <a name="use-full-or-selective-wipe"></a>Použití úplného nebo selektivního vymazání 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Ze zařízení spravovaných pomocí Intune, která už nejsou potřeba, mají se začít používat pro jiné účely nebo se ztratila, můžete vymazat aplikace a data. K tomuto účelu Intune poskytuje možnosti selektivního a úplného vymazání. Uživatelé také mohou odeslat příkaz ke vzdálenému vymazání zařízení z aplikace Portál společnosti Intune nainstalované na soukromých zařízeních zaregistrovaných v Intune.

  > [!NOTE]
  > Toto téma se věnuje jenom vymazání zařízení registrovaných ve správě mobilních zařízení Intune. K [vymazání firemních dat z aplikací](https://portal.azure.com) můžete také použít [portál Azure Portal](https://docs.microsoft.com/intune/deploy-use/wipe-managed-company-app-data-with-microsoft-intune). Je rovněž možné [vyřadit počítače spravované klientským softwarem Intune](https://docs.microsoft.com/intune/deploy-use/retire-a-windows-pc-with-microsoft-intune).

## <a name="full-wipe"></a>Úplné vymazání

**Úplné vymazání** na zařízení obnoví výchozí nastavení od výrobce a odebere všechna firemní a uživatelská data a nastavení. Zařízení se odebere ze služby Intune. Úplné vymazání je vhodné, když chcete zařízení resetovat, abyste ho mohli dát novému uživateli, nebo když došlo k jeho ztrátě nebo odcizení.  **Volbu úplného vymazání používejte velmi opatrně. Data v zařízení nejde obnovit.**


> [!Warning]
> Zařízení s Windows 10 RTM (zařízení se starším systémem než Windows 10 verze 1511) s méně než 4 GB paměti RAM mohou být po vymazání nedostupná. Pokud chcete získat přístup k zařízení s Windows 10, které nereaguje, použijte k jeho spuštění USB flash disk.


**Úplné vymazání zařízení (obnovení do továrního nastavení)**:

1.  V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.

2.  Zvolte název zařízení, které chcete vymazat.

3.  V okně s názvem zařízení zvolte **Obnovení továrního nastavení** a potom zvolte **Ano**, abyste vymazání potvrdili.

Pokud je zařízení zapnuté a připojené, trvá vymazání všech typů zařízení méně než 15 minut.

### <a name="to-delete-devices-in-the-azure-active-directory-portal"></a>Odstranění zařízení na portálu služby Azure Active Directory

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
|E-mailu|Odeberou se e-maily přijaté aplikací Microsoft Outlook pro Android.|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune, a odstraní se e-maily uložené v mezipaměti zařízení.|
|Outlook|Odeberou se e-maily přijaté aplikací Microsoft Outlook pro iOS.</br>Výjimka: Pokud je Exchange hostovaný na místním serveru, e-maily se neodeberou.|Odeberou se e-maily přijaté aplikací Microsoft Outlook pro iOS.</br>Výjimka: Pokud je Exchange hostovaný na místním serveru, e-maily se neodeberou.|
|Zrušení služby Azure Active Directory (AAD)|Odebere se záznam AAD.|Odebere se záznam AAD.|
|Kontakty | Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou.  Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. <br /> <br />V současné době se podporuje jen aplikace Outlook.|Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou.  Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat. <br /> <br />V současné době se podporuje jen aplikace Outlook.

**Windows**

|Datový typ|Windows 8.1 (MDM) a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Firemní aplikace a související data instalovaná službou Intune|U souborů chráněných systémem souborů EFS dojde ke zrušení klíče a uživatel nebude moct soubory otevírat.|Neodebere firemní aplikace.|Odinstalují se aplikace původně nainstalované prostřednictvím firemního portálu. Odeberou se data firemních aplikací.|Aplikace jsou odinstalovány a jsou odebrány klíče zkušebního načtení.|
|Nastavení|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|Odebrány.|Není podporováno.|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty se odeberou a zruší.|Certifikáty se odeberou a zruší.|Není podporováno.|Certifikáty se odeberou a zruší.|
|E-mailu|Odebere se e-mail se zapnutým systémem souborů EFS, včetně e-mailů a příloh aplikace Pošta pro Windows.|Není podporováno.|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune, a odstraní se e-maily uložené v mezipaměti zařízení.|Odebere se e-mail se zapnutým systémem souborů EFS, včetně e-mailů a příloh aplikace Pošta pro Windows. Odebere e-mailové účty, které byly zřízené Intune.</br>**Výjimka**: Pokud je Microsoft Exchange hostovaný na místním serveru, e-mailové účty se neodeberou.|
|Zrušení služby Azure Active Directory (AAD)|Ne.|Ne.|Odebere se záznam AAD.|Nelze použít. Systém Windows 10 nepodporuje selektivní vymazání zařízení připojených k Azure Active Directory.|

**Selektivní vymazání**:

1.  V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.

2.  Zvolte název zařízení, které chcete vymazat.

3.  V okně s názvem zařízení zvolte **Odebrat firemní data** a potom zvolte **Ano**, abyste vymazání potvrdili.

Pokud je zařízení zapnuté a připojené, trvá vymazání všech typů zařízení méně než 15 minut.

