---
title: Odebrání firemních dat ze zařízení pomocí Microsoft Intune – Azure | Microsoft Docs
description: Můžete odebrat firemní data společnosti v zařízení nebo obnovit tovární nastavení zařízení s Androidem, Androidem for Work, iOSem, macOS nebo Windows pomocí Microsoft Intune. Můžete také odstranit zařízení z Azure Active Directory.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f7d3e768e740866d69d675a962dfca6d98c85568
ms.sourcegitcommit: 401cedcd7acc6cb3a6f18d4679bdadb0e0cdf443
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/28/2018
---
# <a name="remove-devices-by-using-factory-reset-or-remove-company-data"></a>Odebrání zařízení pomocí obnovení továrního nastavení nebo odebrání firemních dat

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zařízení, která už nepotřebujete, která využíváte k jinému účelu nebo která se ztratila, můžete z Intune odebrat. Můžete k tomu použít akce **Odebrat firemní data** nebo **Obnovení továrního nastavení**. Uživatelé můžou také z Portálu společnosti Intune vydat vzdálený příkaz zařízením v osobním vlastnictví, která jsou registrovaná v Intune.

> [!NOTE]
> Před odebráním uživatele z Azure Active Directory (Azure AD) použijte akce **Obnovení továrního nastavení** nebo **Odebrat firemní data** pro všechna zařízení přidružená k tomuto uživateli. Pokud z Azure AD odeberete uživatele se spravovanými zařízeními, nemůže už Intune těmto zařízením vydat příkaz k obnovení továrního nastavení nebo odebrání firemních dat.

## <a name="factory-reset"></a>Obnovení továrního nastavení

Akce **Obnovení továrního nastavení** obnoví výchozí tovární nastavení zařízení. Obnovení továrního nastavení odebere všechna firemní a uživatelská data a nastavení. Toto zařízení se odebere ze správy v Intune. Obnovení továrního nastavení je vhodné, když chcete zařízení resetovat, abyste ho mohli dát novému uživateli, nebo když došlo k jeho ztrátě nebo odcizení. Při zvolení **Obnovení továrního nastavení** buďte obezřetní. Data v zařízení není možné obnovit.

### <a name="factory-reset-a-device"></a>Obnovení továrního nastavení zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** > **Všechna zařízení**.
4. Zvolte název zařízení, jehož tovární nastavení chcete obnovit.
5. V podokně s názvem zařízení vyberte **Obnovení továrního nastavení**.
6. Pro Windows 10 verze 1709 nebo novější máte také možnost **Zachovat stav registrace a uživatelský účet**. 
    
    |Zachová se při obnovení továrního nastavení|Nezachová se|
    | -------------|------------|
    |Uživatelské účty přidružené k zařízení|Soubory uživatele|
    |Stav počítače \(připojení k doméně, připojení k Azure AD)| Aplikace nainstalované uživatelem \(aplikace ze Storu a aplikace Win32)|
    |Registrace ve správě mobilních zařízení (MDM)|Nevýchozí nastavení zařízení|
    |Aplikace nainstalované výrobcem OEM \(aplikace ze Storu a aplikace Win32)||
    |Profil uživatele||
    |Uživatelská data mimo profil uživatele||
    |Automatické přihlášení uživatele|| 
    
         
7. Kliknutím na **Ano** potvrďte obnovení továrního nastavení.

Pokud je zařízení zapnuté a připojené, akce **Obnovení továrního nastavení** se do všech typů zařízení rozšíří do 15 minut.

## <a name="remove-company-data"></a>Odebrání firemních dat

Akce **Odebrat firemní data** odebere data případných spravovaných aplikací, nastavení a e-mailové profily, které byly přiřazeny přes Intune. Toto zařízení se odebere ze správy v Intune. K tomu dojde, když se zařízení příště přihlásí a přijme vzdálenou akci **Odebrat firemní data**.

Při **odebrání firemních dat** zůstanou v zařízení osobní data uživatele.  

Následující tabulky popisují, jaká data se odeberou a jaký vliv má akce **Odebrat firemní data** na zbývající data v zařízení po odebrání firemních dat.

### <a name="ios"></a>iOS

|Datový typ|iOS|
|-------------|-------|
|Firemní aplikace a související data instalovaná službou Intune|Odinstalují se aplikace. Odeberou se data firemních aplikací.<br /><br />Odeberou se data aplikací z aplikací Microsoftu, které používají správu mobilních aplikací. Aplikace se neodebere.|
|Nastavení|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty jsou odebrané a odvolané.|
|Agent pro správu|Odebere se profil pro správu.|
|E-mailu|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune. Odstraní se e-maily v mezipaměti zařízení.|
|Outlook|Odeberou se e-maily přijaté aplikací Microsoft Outlook pro iOS. Nejprve ale budete muset uživatelům iOSu nasadit mobilní aplikaci Outlook jako požadovanou aplikaci.|
|Zrušení připojení k Azure AD|Odebere se záznam Azure AD.|
|Kontakty |Odeberou se kontakty synchronizované přímo z aplikace do nativního adresáře. Kontakty synchronizované z nativního adresáře do jiného externího zdroje není možné odebrat. <br /> <br />V současné době se podporuje jenom aplikace Outlook.

### <a name="android"></a>Android

|Datový typ|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Webové odkazy|Odebrány.|Odebrány.|
|Nespravované aplikace Google Play|Aplikace a data zůstanou nainstalována.|Aplikace a data zůstanou nainstalována.|
|Nespravované obchodní aplikace|Aplikace a data zůstanou nainstalována.|Odinstalují se aplikace a odeberou se jejich místní data. Data mimo aplikaci (například na kartě SD) se neodeberou.|
|Spravované aplikace Google Play|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním správy mobilních zařízení (MAM) mimo aplikaci (třeba na kartě SD) zůstanou zašifrována, takže nepůjdou použít, ale neodeberou se.|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním MAM mimo aplikaci (třeba na kartě SD) zůstanou zašifrována, ale neodeberou se.|
|Spravované obchodní aplikace|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním MAM mimo aplikaci (třeba na kartě SD) zůstanou zašifrována, takže nepůjdou použít, ale neodeberou se.|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním MAM mimo aplikaci (třeba na kartě SD) zůstanou zašifrována, takže nepůjdou použít, ale neodeberou se.|
|Nastavení|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty se zruší, ale neodeberou.|Certifikáty jsou odebrané a odvolané.|
|Agent pro správu|Zruší se oprávnění správce zařízení.|Zruší se oprávnění správce zařízení.|
|E-mailu|Není k dispozici (zařízení s Androidem nepodporují e-mailové profily)|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune. Odstraní se e-maily v mezipaměti zařízení.|
|Outlook|E-mail přijatý aplikací Outlook pro Android se odebere, ale jenom v případě, že je Outlook chráněný zásadami MAM. Jinak se Outlook při zrušení registrace zařízení nevymaže.|E-mail přijatý aplikací Outlook pro Android se odebere, ale jenom v případě, že je Outlook chráněný zásadami MAM. Jinak se Outlook při zrušení registrace zařízení nevymaže.|
|Zrušení připojení k Azure AD|Odebere se záznam Azure AD.|Odebere se záznam Azure AD.|
|Kontakty |Odeberou se kontakty synchronizované přímo z aplikace do nativního adresáře. Kontakty synchronizované z nativního adresáře do jiného externího zdroje není možné odebrat. <br /> <br />V současné době se podporuje jenom aplikace Outlook.|Odeberou se kontakty synchronizované přímo z aplikace do nativního adresáře. Kontakty synchronizované z nativního adresáře do jiného externího zdroje není možné odebrat. <br /> <br />V současné době se podporuje jenom aplikace Outlook.

### <a name="android-for-work"></a>Android for Work

Při odebrání firemních dat v zařízení Android for Work se odeberou všechna data, aplikace a nastavení v pracovním profilu na tomto zařízení. Zařízení se vyřadí ze správy pomocí Intune. Android for Work nepodporuje obnovení továrního nastavení.


### <a name="macos"></a>macOS

|Datový typ|macOS|
|-------------|-------|
|Nastavení|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty nasazené prostřednictvím správy mobilních zařízení se odeberou a odvolají.|
|Agent pro správu|Odebere se profil pro správu.|
|Outlook|Při povolení podmíněného přístupu nebude zařízení přijímat žádnou novou poštu.|
|Zrušení připojení k Azure AD|Odebere se záznam Azure AD.|

### <a name="windows"></a>Windows

|Datový typ|Windows 8.1 (MDM) a Windows RT 8.1|Windows RT|Windows Phone 8.1 a Windows Phone 8|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Firemní aplikace a související data instalovaná službou Intune|Odvolají se klíče pro soubory, které jsou chráněné systémem souborů EFS. Uživatel nemůže soubory otevřít.|Firemní aplikace se neodeberou.|Odinstalují se aplikace původně nainstalované prostřednictvím Portálu společnosti. Odeberou se data firemních aplikací.|Odinstalují se aplikace. Odeberou se klíče pro zkušební načtení.<br>Ve Windows 10 verze 1703 (Creators Update) a novějších verzích se neodeberou aplikace Office 365 ProPlus.|
|Nastavení|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|Odebrány.|Není podporováno.|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty jsou odebrané a odvolané.|Certifikáty jsou odebrané a odvolané.|Není podporováno.|Certifikáty jsou odebrané a odvolané.|
|E-mailu|Odeberou se e-maily s povoleným systémem souborů EFS. To zahrnuje e-maily a přílohy v aplikaci Pošta pro Windows.|Není podporováno.|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune. Odstraní se e-maily v mezipaměti zařízení.|Odeberou se e-maily s povoleným systémem souborů EFS. To zahrnuje e-maily a přílohy v aplikaci Pošta pro Windows. Odebere e-mailové účty, které byly zřízené Intune.|
|Zrušení připojení k Azure AD|Ne.|Ne.|Odebere se záznam Azure AD.|Nelze použít. Ve Windows 10 není možné u zařízení připojených k Azure AD firemní data odebrat.|

### <a name="remove-company-data"></a>Odebrání firemních dat

1. Přihlaste se k [Intune na portálu Azure Portal](https://aka.ms/intuneportal).
2. V podokně **Zařízení** zvolte **Všechna zařízení**.
3. Zvolte název zařízení, ze kterého chcete odebrat firemní data.
4. V podokně s názvem zařízení vyberte **Odebrat firemní data**. Potvrďte zvolením **Ano**.

Pokud je zařízení zapnuté a připojené, akce **Odebrat firemní data** se do všech typů zařízení rozšíří do 15 minut.

## <a name="delete-devices-from-the-intune-portal"></a>Odstranění zařízení z portálu Intune

Pokud chcete odebrat zařízení z portálu Intune, můžete je odstranit z podokna konkrétního zařízení. Při příštím přihlášení zařízení se z něj odeberou všechna firemní data.

1. Přihlaste se k [Intune na portálu Azure Portal](https://aka.ms/intuneportal).
2. Zvolte **Zařízení** > **Všechna zařízení** > vyberte zařízení, která chcete odstranit > **Odstranit**.

## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Odstranění zařízení z portálu služby Azure Active Directory

Kvůli komunikačním problémům nebo ztraceným zařízením můžete potřebovat odstranit zařízení z Azure AD. Pomocí akce **Odstranit** můžete z portálu Azure Portal odebrat záznamy zařízení, o kterých víte, že jsou nedosažitelná a je nepravděpodobné, že by se službou Azure znovu komunikovala. Akce **Odstranit** neodebere zařízení ze správy.

1.  Přihlaste se k [Azure Active Directory na portálu Azure Portal](http://aka.ms/accessaad) pomocí přihlašovacích údajů správce. Můžete se také přihlásit k [portálu Office 365](https://portal.office.com). V nabídce vyberte **Centra pro správu** > **Azure AD**.
2.  Pokud nemáte předplatné Azure, vytvořte ho. Pokud máte placený účet, neměli byste potřebovat platební kartu ani zadání platby (vyberte odkaz pro předplatné **Zdarma zaregistrovat službu Azure Active Directory** ).
3.  Vyberte **Azure Active Directory** a pak vyberte svoji organizaci.
4.  Vyberte kartu **Uživatelé** .
5. Vyberte uživatele spojeného se zařízením, které chcete odstranit.
6.  Vyberte **Zařízení**.
7.  Odeberte zařízení podle potřeby. Můžete třeba odebrat zařízení, která už se nepoužívají, nebo zařízení s nesprávnými definicemi.
