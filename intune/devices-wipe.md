---
title: Vyřazení nebo vymazání zařízení pomocí Microsoft Intune – Azure | Microsoft Docs
description: Pomocí Microsoft Intune můžete vyřadit nebo vymazat zařízení s Androidem, pracovním profilem Androidu, iOSu, macOS nebo Windows. Můžete také odstranit zařízení z Azure Active Directory.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: ''
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4fdb787e-084f-4507-9c63-c96b13bfcdf9
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: e24043bb1c41d68de04669ff27cc659624dc56c1
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55846821"
---
# <a name="remove-devices-by-using-wipe-retire-or-manually-unenrolling-the-device"></a>Odebrání zařízení vymazáním, vyřazením nebo ručním zrušením registrace

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zařízení, která už nepotřebujete, která využíváte k jinému účelu nebo která se ztratila, můžete z Intune odebrat prostřednictvím akce **Vyřazení** nebo **Vymazání**. Uživatelé můžou také z Portálu společnosti Intune vydat vzdálený příkaz zařízením v osobním vlastnictví, která jsou registrovaná v Intune.

> [!NOTE]
> Před odebráním uživatele z Azure Active Directory (Azure AD) použijte akce **Vymazání** nebo **Vyřazení** u všech zařízení přidružených k tomuto uživateli. Pokud z Azure AD odeberete uživatele se spravovanými zařízeními, nemůže už Intune tato zařízení vymazat ani vyřadit.

## <a name="wipe"></a>Vymazání

Akce **Vymazání** obnoví výchozí tovární nastavení zařízení. Data uživatele se zachovají, pokud zaškrtnete políčko **Zachovat stav registrace a uživatelský účet**. Jinak se jednotka bezpečně vymaže.

|Akce vymazání|**Zachovat stav registrace a uživatelský účet**|Odebráno ze správy v Intune|Popis|
|:-------------:|:------------:|:------------:|------------|
|**Vymazání**| Není zaškrtnuto | Ano | Vymaže všechny uživatelské účty, data, zásady MDM a nastavení. Obnoví operační systém do výchozího stavu a nastavení.|
|**Vymazání**| Zaškrtnuto | Ne | Vymaže všechny zásady MDM. Zachová uživatelské účty a data. Obnoví nastavení uživatele zpět na výchozí nastavení. Obnoví operační systém do výchozího stavu a nastavení.|

Pro Windows 10 verze 1709 nebo novější máte také možnost **Zachovat stav registrace a uživatelský účet**.

Zásady MDM se znovu použijí při příštím připojení zařízení k Intune.

Vymazání je vhodné, když chcete zařízení resetovat, abyste ho mohli dát novému uživateli, nebo když došlo k jeho ztrátě nebo odcizení. Volbu **vymazání** používejte velmi opatrně. Data v zařízení není možné obnovit.

### <a name="wiping-a-device"></a>Vymazání zařízení

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** > **Všechna zařízení**.
4. Zvolte název zařízení, které chcete vymazat.
5. V podokně s názvem zařízení vyberte **Vymazání**.
6. Pro Windows 10 verze 1709 nebo novější máte také možnost **Zachovat stav registrace a uživatelský účet**. 
    
    |Zachová se při vymazání |Nezachová se|
    | -------------|------------|
    |Uživatelské účty přidružené k zařízení|Soubory uživatele|
    |Stav počítače \(připojení k doméně, připojení k Azure AD)| Aplikace nainstalované uživatelem \(aplikace ze Storu a aplikace Win32)|
    |Registrace ve správě mobilních zařízení (MDM)|Nevýchozí nastavení zařízení|
    |Aplikace nainstalované výrobcem OEM \(aplikace ze Storu a aplikace Win32)||
    |Profil uživatele||
    |Uživatelská data mimo profil uživatele||
    |Automatické přihlášení uživatele|| 
    
         
7. Potvrďte vymazání volbou možnosti **Ano**.

Pokud je zařízení zapnuté a připojené, akce **Vymazání** se do všech typů zařízení rozšíří do 15 minut.

## <a name="retire"></a>Vyřazení

Akce **Vyřazení** odebere data případných spravovaných aplikací, nastavení a e-mailové profily, které byly přiřazeny přes Intune. Toto zařízení se odebere ze správy v Intune. K tomu dojde, když se zařízení příště přihlásí a přijme vzdálenou akci **Vyřazení**.

Při této akci zůstanou v zařízení osobní data uživatele.  

Následující tabulky popisují, jaká data se odeberou a jaký vliv má akce **Vyřazení** na zbývající data v zařízení po odebrání firemních dat.

### <a name="ios"></a>iOS

|Datový typ|iOS|
|-------------|-------|
|Firemní aplikace a související data instalovaná službou Intune|**Aplikace nainstalované pomocí portálu společnosti:** Díky aplikace, které jsou připnuté na profil pro správu, všechna data aplikace a aplikace se odeberou. Tyto aplikace patří aplikace původně nainstalované z App Store a později spravovat jako podnikové aplikace. <br /><br /> **Aplikace Microsoftu, které používají správu mobilních aplikací a byly nainstalovány z App Store:** Pro aplikace, které se nespravují přes portál společnosti se odeberou firemní aplikace data chráněná šifrováním správy mobilních aplikací (MAM) v rámci místní úložiště aplikací. Data chráněná šifrováním MAM mimo aplikaci zůstávají šifrovaná a nepoužitelná, ale neodeberou. Osobní aplikační data a aplikace se neodeberou.|
|Nastavení|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty jsou odebrané a odvolané.|
|Agent pro správu|Odebere se profil pro správu.|
|Email|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune. Odstraní se e-maily v mezipaměti zařízení.|
|Zrušení připojení k Azure AD|Odebere se záznam Azure AD.|

### <a name="android"></a>Android

|Datový typ|Android|Android Samsung Knox Standard|
|-------------|-----------|------------------------|
|Webové odkazy|Odebrány.|Odebrány.|
|Nespravované aplikace Google Play|Aplikace a data zůstanou nainstalována. <br /> <br />Data firemních aplikací, která je chráněná šifrováním správy mobilních aplikací (MAM) v rámci místní úložiště aplikací se odebere. Data chráněná šifrováním MAM mimo aplikaci zůstávají šifrovaná a nepoužitelná, ale neodeberou. |Aplikace a data zůstanou nainstalována. <br /> <br />Data firemních aplikací, která je chráněná šifrováním správy mobilních aplikací (MAM) v rámci místní úložiště aplikací se odebere. Data chráněná šifrováním MAM mimo aplikaci zůstávají šifrovaná a nepoužitelná, ale neodeberou.|
|Nespravované obchodní aplikace|Aplikace a data zůstanou nainstalována.|Odinstalují se aplikace a odeberou se jejich místní data. Data mimo aplikaci (například na kartě SD) se neodeberou.|
|Spravované aplikace Google Play|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním správy mobilních zařízení (MAM) mimo aplikaci (třeba na kartě SD) zůstanou zašifrována, takže nepůjdou použít, ale neodeberou se.|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním MAM mimo aplikaci (třeba na kartě SD) zůstanou zašifrována, ale neodeberou se.|
|Spravované obchodní aplikace|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním MAM mimo aplikaci (třeba na kartě SD) zůstanou zašifrována, takže nepůjdou použít, ale neodeberou se.|Odeberou se data aplikací. Aplikace se neodebere. Data chráněná šifrováním MAM mimo aplikaci (třeba na kartě SD) zůstanou zašifrována, takže nepůjdou použít, ale neodeberou se.|
|Nastavení|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty se zruší, ale neodeberou.|Certifikáty jsou odebrané a odvolané.|
|Agent pro správu|Zruší se oprávnění správce zařízení.|Zruší se oprávnění správce zařízení.|
|Email|Není k dispozici (zařízení s Androidem nepodporují e-mailové profily)|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune. Odstraní se e-maily v mezipaměti zařízení.|
|Zrušení připojení k Azure AD|Odebere se záznam Azure AD.|Odebere se záznam Azure AD.|

### <a name="android-work-profile"></a>Pracovní profil Androidu

Při odebrání firemních dat ze zařízení s pracovním profilem Androidu se odeberou všechna data, aplikace a nastavení v pracovním profilu na tomto zařízení. Zařízení se vyřadí ze správy pomocí Intune. Pracovní profily Androidu nepodporují vymazání.

### <a name="android-enterprise-kiosk-devices"></a>Zařízení s Androidem Enterprise v beznabídkovém režimu

Zařízení s Androidem v beznabídkovém režimu můžete jen vymazat. Vyřazení u nich není možné.


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

|Datový typ|Windows 8.1 (MDM) a Windows RT 8.1|Windows RT|Windows Phone 8.1 a Windows Phone 8|Windows 10|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Firemní aplikace a související data instalovaná službou Intune|Odvolají se klíče pro soubory, které jsou chráněné systémem souborů EFS. Uživatel nemůže soubory otevřít.|Firemní aplikace se neodeberou.|Odinstalují se aplikace původně nainstalované prostřednictvím Portálu společnosti. Odeberou se data firemních aplikací.|Odinstalují se aplikace. Odeberou se klíče pro zkušební načtení.<br>Ve Windows 10 verze 1703 (Creators Update) a novějších verzích se neodeberou aplikace Office 365 ProPlus.|
|Nastavení|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|Konfigurace nastavené zásadami Intune se už nevynucují. Uživatelé můžou nastavení změnit.|
|Nastavení profilu sítě Wi-Fi a VPN|Odebrány.|Odebrány.|Nepodporuje se.|Odebrány.|
|Nastavení profilu certifikátu|Certifikáty jsou odebrané a odvolané.|Certifikáty jsou odebrané a odvolané.|Nepodporuje se.|Certifikáty jsou odebrané a odvolané.|
|Email|Odeberou se e-maily s povoleným systémem souborů EFS. To zahrnuje e-maily a přílohy v aplikaci Pošta pro Windows.|Nepodporuje se.|Odeberou se e-mailové profily, které jsou zřízené prostřednictvím Intune. Odstraní se e-maily v mezipaměti zařízení.|Odeberou se e-maily s povoleným systémem souborů EFS. To zahrnuje e-maily a přílohy v aplikaci Pošta pro Windows. Odebere e-mailové účty, které byly zřízené Intune.|
|Zrušení připojení k Azure AD|Ne.|Ne.|Odebere se záznam Azure AD.|Není k dispozici. Ve Windows 10 nelze u zařízení připojených k Azure AD vyřazení provést.|

### <a name="retire"></a>Vyřazení

1. Přihlaste se k [Intune na portálu Azure Portal](https://aka.ms/intuneportal).
2. V podokně **Zařízení** zvolte **Všechna zařízení**.
3. Zvolte název zařízení, které chcete vyřadit.
4. V podokně s názvem zařízení vyberte **Vyřazení**. Potvrďte zvolením **Ano**.

Pokud je zařízení zapnuté a připojené, akce **Vyřazení** se do všech typů zařízení rozšíří do 15 minut.

## <a name="delete-devices-from-the-intune-portal"></a>Odstranění zařízení z portálu Intune

Pokud chcete odebrat zařízení z portálu Intune, můžete je odstranit z podokna konkrétního zařízení. Při příštím přihlášení zařízení se z něj odeberou všechna firemní data.

1. Přihlaste se k [Intune na webu Azure Portal](https://aka.ms/intuneportal).
2. Zvolte **Zařízení** > **Všechna zařízení** > vyberte zařízení, která chcete odstranit > **Odstranit**.

### <a name="automatically-delete-devices-with-cleanup-rules"></a>Automatické odstranění zařízení pomocí pravidel čištění
Můžete nakonfigurovat Intune tak, aby automaticky odstraňoval zařízení, která jsou neaktivní, zastaralá nebo nereagující. Tato pravidla čištění průběžně monitorují váš inventář zařízení, aby záznamy vašich zařízení byly stále aktuální. Zařízení odstraněná tímto způsobem se odeberou ze správy Intune.
1. Přihlaste se k [Intune na portálu Azure Portal](https://aka.ms/intuneportal).
2. Zvolte **Zařízení** > **Pravidla čištění zařízení** > **Ano**.
3. Do pole **Odstranit zařízení, která se po tento počet dní neohlásila** zadejte číslo v rozmezí od 90 do 270.
4. Zvolte **Uložit**.



## <a name="delete-devices-from-the-azure-active-directory-portal"></a>Odstranění zařízení z portálu služby Azure Active Directory

Kvůli komunikačním problémům nebo ztraceným zařízením můžete potřebovat odstranit zařízení z Azure AD. Pomocí akce **Odstranit** můžete z portálu Azure Portal odebrat záznamy zařízení, o kterých víte, že jsou nedosažitelná a je nepravděpodobné, že by se službou Azure znovu komunikovala. Akce **Odstranit** neodebere zařízení ze správy.

1.  Přihlaste se k [Azure Active Directory na portálu Azure Portal](http://aka.ms/accessaad) pomocí přihlašovacích údajů správce. Můžete se také přihlásit k [portálu Office 365](https://portal.office.com). V nabídce vyberte **Centra pro správu** > **Azure AD**.
2.  Pokud nemáte předplatné Azure, vytvořte ho. Pokud máte placený účet, neměli byste potřebovat platební kartu ani zadání platby (vyberte odkaz pro předplatné **Zdarma zaregistrovat službu Azure Active Directory** ).
3.  Vyberte **Azure Active Directory** a pak vyberte svoji organizaci.
4.  Vyberte kartu **Uživatelé** .
5. Vyberte uživatele spojeného se zařízením, které chcete odstranit.
6.  Vyberte **Zařízení**.
7.  Odeberte zařízení podle potřeby. Můžete třeba odebrat zařízení, která už se nepoužívají, nebo zařízení s nesprávnými definicemi.

## <a name="retire-an-apple-dep-device-from-intune"></a>Vyřazení zařízení Apple DEP z Intune

Pokud chcete zařízení Apple DEP zcela odebrat ze systému správy Intune, postupujte takto:

1. Přihlaste se k [Intune na portálu Azure Portal](https://aka.ms/intuneportal).
2. Zvolte **Zařízení** > **Všechna zařízení** > vyberte požadované zařízení > **Vyřazení**.
![Snímek obrazovky s akcí vyřazení](./media/devices-wipe/retire.png)
3. Zvolte **Registrace zařízení** > **Registrace zařízení Apple** > **Tokeny programu registrace** > zvolte token > **Zařízení** > zaškrtněte políčko zařízení > **Odstranit** > **Ano**.
![Snímek obrazovky odstranění zařízení](./media/devices-wipe/delete-device.png)
4. Přejděte na [deploy.apple.com](http://deploy.apple.com) a vyhledejte zařízení podle sériového čísla.
5. V nabídce **Přiřazeno** zvolte **Nepřiřazeno**.

6. Zvolte **Znovu přiřadit**.

    ![Snímek obrazovky opětovného přiřazení Apple](./media/devices-wipe/apple-reassign.png)

## <a name="fresh-start"></a>Akce začít znovu

Platí pro zařízení s Windows 10. Další informace o [začít](https://docs.microsoft.com/intune/device-fresh-start).

## <a name="next-steps"></a>Další postup

Pokud chcete znovu zaregistrovat odstraněné zařízení, najdete informace v tématu o [možnostech registrace](enrollment-options.md).

