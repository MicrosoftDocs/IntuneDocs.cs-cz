---
title: "Obnovení továrního nastavení nebo odebrání firemních dat v zařízení pomocí Intune"
titlesuffix: Azure portal
description: "Zjistěte, jak můžete v zařízení odebrat firemní data nebo obnovit tovární nastavení."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f8f004389c8bde2367045019fb04865e1a606914
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Odebrání zařízení pomocí obnovení továrního nastavení nebo odebrání firemních dat

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Zařízení, která už nepotřebujete, která využíváte k jinému účelu nebo která se ztratila, můžete z Intune odebrat. Dosáhnete toho vydáním příkazu k **odebrání firemních dat** nebo **obnovení továrního nastavení**. Uživatelé můžou rovněž z Portálu společnosti Intune vydat vzdálený příkaz zařízením v osobním vlastnictví, která jsou registrovaná v Intune.

> [!NOTE]
> Před odebráním uživatele ze služby Azure Active Directory vydejte příkaz k **obnovení továrního nastavení** nebo **odebrání firemních dat** všem zařízením přidruženým k tomuto uživateli. Pokud ze služby Azure Active Directory odeberete uživatele se spravovanými zařízeními, nemůže už Intune vydat těmto zařízením příkaz k obnovení továrního nastavení nebo odebrání firemních dat.

## <a name="factory-reset"></a>Obnovení továrního nastavení

**Obnovení továrního nastavení** obnoví v zařízení výchozí nastavení výrobce a odebere všechna firemní a uživatelská data a nastavení. Toto zařízení se odebere ze správy v Intune. Obnovení továrního nastavení je vhodné, když chcete zařízení resetovat, abyste ho mohli dát novému uživateli, nebo když došlo k jeho ztrátě nebo odcizení. Při výběru obnovení továrního nastavení buďte obezřetní. Data v zařízení není možné obnovit.

### <a name="to-factory-reset-a-device"></a>Jak u zařízení obnovit tovární nastavení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
4. Zvolte název zařízení, jehož tovární nastavení chcete obnovit.
5. V okně, ve kterém se zobrazuje název zařízení zvolte **Obnovení továrního nastavení**.
6. U Windows 10 verze 1709 nebo vyšší je k dispozici další možnost – Zachovat stav registrace a uživatelský účet. 
    
    |Při obnovení továrního nastavení se zachová|Nezachová se|
    | -------------|------------|
    |Uživatelské účty přidružené k zařízení|Soubory uživatele|
    |Stav počítače \(připojení k doméně, připojení k Azure Active Directory)| Aplikace nainstalované uživatelem \(aplikace ze Storu a aplikace Win32)|
    |Registrace správy mobilních zařízení|Nevýchozí nastavení zařízení|
    |Aplikace nainstalované výrobcem OEM \(aplikace ze Storu a aplikace Win32)||
    |Profil uživatele||
    |Uživatelská data mimo profil uživatele||
    |Automatické přihlášení uživatele|| 
    
         
7. Kliknutím na **Ano** potvrďte obnovení továrního nastavení.

Pokud je zařízení zapnuté a připojené, trvá méně než 15 minut, než se příkaz k obnovení továrního nastavení rozšíří do všech typů zařízení.

## <a name="remove-company-data"></a>Odebrání firemních dat

Příkaz k **odebrání firemních dat** odebere data případných spravovaných aplikací, nastavení a e-mailové profily, které byly přiřazeny přes Intune. Při odebrání firemních dat zůstanou v zařízení osobní data uživatele. Toto zařízení se odebere ze správy v Intune. Následující tabulky popisují, jaká data se odeberou a jaký vliv má odebrání firemních dat na zbývající data v zařízení.

### <a name="ios"></a>iOS

|Datový typ|iOS|
|-------------|-------|
|Firemní aplikace a související data instalovaná službou Intune|Odinstalují se aplikace. Odeberou se data firemních aplikací.<br /><br />Odeberou se data aplikací z aplikací Microsoftu, které používají správu mobilních aplikací. Aplikace se neodebere.|
|Nastavení|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty jsou odebrané a odvolané.|
|Agent pro správu|Profil pro správu se odebere.|
|E-mailu|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune, a odstraní se e-maily uložené v mezipaměti zařízení.|
|Outlook|Odeberou se e-maily přijaté aplikací Microsoft Outlook pro iOS.|
|Zrušení služby Azure Active Directory (AD)|Odebere se záznam služby Azure AD.|
|Kontakty | Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou.  Kontakty synchronizované z nativního adresáře do jiného externího zdroje není možné odebrat. <br /> <br />V současné době se podporuje jen aplikace Outlook.

### <a name="android"></a>Android

|Datový typ|Android|Android Samsung Knox Standard|
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
|E-mailu|Není k dispozici (zařízení s Androidem nepodporují e-mailové profily)|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune, a odstraní se e-maily uložené v mezipaměti zařízení.|
|Outlook|E-mail přijatý aplikací Microsoft Outlook pro Android se odebere, ale pouze v případě, že je Outlook chráněný zásadami MAM. V opačném případě se Outlook při zrušení registrace nevymaže.|E-mail přijatý aplikací Microsoft Outlook pro Android se odebere, ale pouze v případě, že je Outlook chráněný zásadami MAM. V opačném případě se Outlook při zrušení registrace nevymaže.|
|Zrušení služby Azure Active Directory (AD)|Odebere se záznam služby Azure AD.|Odebere se záznam služby Azure AD.|
|Kontakty | Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou.  Kontakty synchronizované z nativního adresáře do jiného externího zdroje není možné odebrat. <br /> <br />V současné době se podporuje jen aplikace Outlook.|Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou.  Kontakty synchronizované z nativního adresáře do jiného externího zdroje není možné odebrat. <br /> <br />V současné době se podporuje jen aplikace Outlook.

### <a name="android-for-work"></a>Android for Work

Při odebrání firemních dat v zařízení Android for Work se odeberou všechna data, aplikace a nastavení v pracovním profilu na tomto zařízení. Zařízení se tím vyřadí ze správy pomocí Intune. Android for Work nepodporuje obnovení továrního nastavení.


### <a name="macos"></a>macOS

|Datový typ|macOS|
|-------------|-------|
|Nastavení|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty nasazené prostřednictvím správy mobilních zařízení se odeberou a odvolají.|
|Agent pro správu|Profil pro správu se odebere.|
|Outlook|Při povolení podmíněného přístupu nebude zařízení přijímat žádnou novou poštu.|
|Zrušení služby Azure Active Directory (AD)|Odebere se záznam služby Azure AD.|

### <a name="windows"></a>Windows

|Datový typ|Windows 8.1 (MDM) a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Firemní aplikace a související data instalovaná službou Intune|U souborů chráněných systémem souborů EFS dojde ke zrušení klíče a uživatel nebude moct soubory otevírat.|Neodebere firemní aplikace.|Odinstalují se aplikace původně nainstalované prostřednictvím firemního portálu. Odeberou se data firemních aplikací.|Aplikace jsou odinstalovány a jsou odebrány klíče zkušebního načtení.<br>Ve Windows 10 verze 1703 (Creator Update) a novějších verzích nejsou odebrány aplikace Office 365 ProPlus.|
|Nastavení|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|Konfigurace nastavené zásadami Intune se nevynucují, tzn. že uživatelé mohou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|Odebrány.|Není podporováno.|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty se odeberou a zruší.|Certifikáty se odeberou a zruší.|Není podporováno.|Certifikáty se odeberou a zruší.|
|E-mailu|Odebere se e-mail se zapnutým systémem souborů EFS, včetně e-mailů a příloh aplikace Pošta pro Windows.|Není podporováno.|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune, a odstraní se e-maily uložené v mezipaměti zařízení.|Odebere se e-mail se zapnutým systémem souborů EFS, včetně e-mailů a příloh aplikace Pošta pro Windows. Odebere e-mailové účty, které byly zřízené Intune.|
|Zrušení služby Azure Active Directory (AD)|Ne.|Ne.|Odebere se záznam služby Azure AD.|Nelze použít. Ve Windows 10 se nepodporuje odebrání firemních dat u zařízení připojených ke službě Azure Active Directory.|

### <a name="to-remove-company-data"></a>Jak odebrat firemní data

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Zařízení a skupiny** zvolte **Všechna zařízení**.
4. Zvolte název zařízení, ze kterého chcete odebrat firemní data.
5. V okně, kde se zobrazuje název zařízení, zvolte **Odebrat firemní data**, a volbou možnosti **Ano** tuto akci potvrďte.

Pokud je zařízení zapnuté a připojené, trvá méně než 15 minut, než se příkaz k odebrání dat rozšíří do všech typů zařízení.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Odstranění zařízení z portálu služby Azure Active Directory

Kvůli komunikačním problémům nebo ztraceným zařízením můžete potřebovat odstranit zařízení ze služby Azure Active Directory (AD). Příkazem k odstranění se zařízení neodebere ze správy, příkazem **Odstranit** ale můžete z Azure Portalu odebrat záznamy zařízení, o kterých víte, že jsou nedosažitelná a je nepravděpodobné, že by se službou Azure znovu komunikovala.

1.  Přihlaste se ke službě [Azure Active Directory na Azure Portalu](http://aka.ms/accessaad) pomocí přihlašovacích údajů správce. Můžete se také přihlásit k [portálu Office 365](https://portal.office.com) a pak pomocí odkazu na levé straně stránky zvolit **Správce** &gt; **Azure AD**.
3.  Pokud nemáte předplatné Azure, vytvořte ho. Pokud máte placený účet, neměli byste potřebovat platební kartu ani zadání platby (zvolte odkaz pro předplatné **Zdarma zaregistrovat službu Azure Active Directory**).
4.  Vyberte možnost **Active Directory** a potom vyberte svoji organizaci.
5.  Vyberte kartu **Uživatelé** .
6.  Vyberte uživatele, jehož zařízení chcete odstranit.
7.  Zvolte **Zařízení**.
8.  Odeberte zařízení podle potřeby, třeba zařízení, která už se nepoužívají, nebo zařízení s nesprávnými definicemi.
