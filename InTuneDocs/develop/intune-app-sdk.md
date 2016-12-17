---
title: "Výhody sady Intune App SDK | Dokumentace Microsoftu"
description: 
keywords: 
author: mtillman
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd9f05e7-26e6-45e0-8d38-67d8232b1cae
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 613e293d9bd853d6de7cdc0d753cc8473afc180b
ms.openlocfilehash: e8f96499f006af590b6e7da295503696110dad4e


---

# <a name="intune-app-sdk-overview"></a>Přehled sady Intune App SDK
Sada Intune App SDK je dostupná pro platformy iOS i Android a umožňuje funkce správy mobilních aplikací s Microsoft Intune. Usiluje o minimalizaci nutných změn kódu, které musí vývojáře aplikace provádět. Zjistíte, že většinu funkcí sady SDK můžete povolit bez změny chování vaší aplikace. Za účelem zlepšení činnosti koncových uživatelů a správců IT můžete využít rozhraní API k přizpůsobení chování vaší aplikace pro funkce, které vyžadují zapojení vaší aplikace. 

Po povolení aplikace můžou správci IT nasadit zásady pro aplikace spravované v Intune a využít těchto funkcí k ochraně podnikových dat.

## <a name="regular-features"></a>Běžné funkce

### <a name="control-users-ability-to-move-corporate-documents"></a>Ovládání možnosti uživatele přesouvat podnikové dokumenty
Správci IT můžou řídit relokaci souborů podnikových dokumentů v aplikacích spravovaných v Intune. Můžou třeba nasadit zásadu, která zakazuje aplikacím pro zálohování souborů zálohovat podniková data do cloudu.

### <a name="configure-clipboard-restrictions"></a>Konfigurace omezení schránky
Správci IT můžou konfigurovat chování schránky v aplikacích spravovaných v Intune. Můžou třeba nasadit zásadu, která koncovým uživatelům znemožní používat schránku k vyjmutí/kopírování z aplikace spravované v Intune a vložení obsahu do nespravované, osobní aplikace.

### <a name="enforce-encryption-on-saved-data"></a>Vynucení šifrování uložených dat
Správci IT můžou vynutit zásadu, která zajišťuje, aby data ukládaná aplikací do zařízení šifrovala.

### <a name="remotely-wipe-corporate-data"></a>Vzdálené vymazání podnikových dat
Správci IT můžou vzdáleně vymazat podniková data z aplikací spravovaných v Intune. Tato funkce je založená na identitě a odstraní jenom soubory přidružené k podnikové identitě koncového uživatele. Kvůli tomu funkce vyžaduje zapojení aplikace. Aplikace může určit identitu, u které má dojít k vymazání, na základě uživatelského nastavení. Když uvedená uživatelská nastavení v aplikaci chybí, výchozím chováním bude vymazání adresáře aplikace a upozornění koncového uživatele, že došlo k odebrání přístupu.

### <a name="enforce-the-use-of-a-managed-browser"></a>Vynucení používání spravovaného prohlížeče
Správci IT můžou při otevírání odkazů z aplikací spravovaných v Intune vynutit používání spravovaného prohlížeče. Tím se zajistí, aby odkazy zobrazované v podnikovém prostředí zůstaly uchované v rámci aplikací spravovaných v Intune.

### <a name="enforce-a-pin-policy"></a>Vynucení zásady kódu PIN
Správci IT můžou vynutit zásady kódu PIN při spuštění aplikace spravované v Intune. Tím se zajistí, že uživatel, který aplikaci spouští, je tím samým uživatelem, který se původně přihlásil pomocí zaregistrovaného pracovního nebo školního účtu. Když koncoví uživatelé nakonfigurují kód PIN, sada Intune App SDK použije Azure Active Directory k ověření přihlašovacích údajů koncového uživatele podle registrovaného účtu Intune.

### <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Vyžádání přihlašovacích údajů před spuštěním aplikací
Správci IT můžou vyžadovat, aby uživatelé před spuštěním aplikací spravovaných v Intune zadali přihlašovací údaje. Sada Intune App SDK použije Azure Active Directory k jednotnému přihlášení, při kterém se jednou zadané přihlašovací údaje znovu použijí pro další přihlášení. Také podporujeme ověřování řešení správy identity [sdružených se službou Azure Active Directory](https://msdn.microsoft.com/library/azure/jj679342.aspx).

### <a name="check-device-health-and-compliance"></a>Kontrola stavu zařízení a dodržování předpisů
Správci IT můžou před přístupem koncových uživatelů k aplikacím spravovaným v Intune kontrolovat stav zařízení a dodržování podnikových zásad. Na platformě iOS tato zásada kontroluje, jestli zařízení nemá jailbreak. Na platformě Android tato zásada kontroluje, jestli zařízení nemá root.

### <a name="sdk-multi-identity-support"></a>Podpora více identit v sadě SDK
Podpora více identit je funkce umožňující koexistenci účtů spravovaných zásadou (podnikových) a nespravovaných (osobních) v jediné aplikaci.

Mnoho uživatelů si například v aplikaci Outlook pro iOS a Android konfiguruje podnikové i osobní e-mailové účty. Když uživatel přistupuje k datům v podnikovém účtu, správce IT si musí být jistý, že se použije správa zásad MAM. Když ale uživatel přistupuje k osobnímu e-mailovému účtu, tato data by měla být mimo dosah správce IT. Microsoft Intune toho dosahuje pomocí cílení zásad správy v aplikaci jenom na podnikový účet. Tato funkce více identit vám pomůže vyřešit problém s ochranou dat, se kterým se setkávají organizace se zařízeními a aplikacemi, které podporují osobní i pracovní účty.

* **Způsob podpory více identit**: Rozhraní API sady Microsoft Intune App SDK vám umožňují určit Hlavní název uživatele (UPN) se specifickými datovými operacemi, jako jsou operace se schránkou a operace se soubory. Sada SDK používá název UPN k přiřazení volání k názvu UPN, který byl použit k registraci zařízení ve službě Microsoft Intune. Když se názvy UPN shodují, se volání považuje za volání podnikových dat a data jsou chráněna. Když se názvy UPN neshodují, volání se považuje za volání osobních dat a data nejsou chráněna.

### <a name="app-management-without-device-enrollment"></a>Správa aplikací bez registrace zařízení

>[!IMPORTANT]
>Správa mobilních aplikací Intune bez registrace zařízení je aktuálně dostupná jenom v sadě Intune App SDK pro iOS. 


Mnoho uživatelů chce zobrazovat a používat podniková data bez registrace svého osobního zařízení v produktu správy mobilních zařízení (MDM). Registrace MDM vyžaduje globální kontrolu zařízení, proto uživatelé váhají předat tuto globální kontrolu vlastního osobního zařízení společnosti.

Správa aplikací bez registrace zařízení umožňuje službě Microsoft Intune nasadit zásady MAM přímo na aplikaci bez spoléhání na nasazení zásad prostřednictvím kanálu MDM. Protože není potřeba žádný kanál MDM, není potřeba ani registrace MDM.



<!--HONumber=Dec16_HO2-->


