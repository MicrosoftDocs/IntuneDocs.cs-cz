---
title: "Přehled sady Microsoft Intune App SDK | Dokumentace Microsoftu"
description: "Sada Intune App SDK je dostupná pro platformy iOS i Android a umožňuje povolit funkce správy mobilních aplikací v Microsoft Intune."
keywords: 
author: mtillman
manager: angrobe
ms.author: mtillman
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f46f13e9dbf03fa2b3e2ec7339cad927ea0b38e0
ms.openlocfilehash: 99f3aa3c8640dd41133584b3e1cb056dfd493efa


---

# <a name="overview-of-the-microsoft-intune-app-sdk"></a>Přehled Microsoft Intune App SDK

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Sada Intune App SDK je dostupná pro platformy iOS i Android a umožňuje povolit funkce správy mobilních aplikací v Microsoft Intune. Navíc snižuje množství změn, které musí vývojáři v kódu udělat.

Zjistíte, že většinu funkcí sady SDK můžete povolit bez změny chování vaší aplikace.  Pokud chcete rozšířit možnosti, které můžou koncoví uživatelé a správci IT využívat, můžete pomocí rozhraní API přizpůsobit chování aplikace u funkcí, které vyžadují použití vaší aplikace.

Po povolení aplikace můžou správci IT nasadit zásady pro aplikace spravované v Intune a využít těchto funkcí k ochraně podnikových dat.

## <a name="features"></a>Funkce:
### <a name="control-users-ability-to-move-corporate-documents"></a>Ovládání možnosti uživatele přesouvat podnikové dokumenty
Správci IT můžou řídit relokaci souborů podnikových dokumentů v aplikacích spravovaných v Intune. Můžou třeba nasadit zásadu, která zakazuje aplikacím pro zálohování souborů zálohovat podniková data do cloudu.  

### <a name="configure-clipboard-restrictions"></a>Konfigurace omezení schránky
Správci IT můžou konfigurovat chování schránky v aplikacích spravovaných v Intune. Můžou třeba nasadit zásadu, která koncovým uživatelům znemožní použít schránku pro vyjmutí a kopírování z aplikace spravované v Intune a vložení obsahu do nespravované aplikace.

### <a name="enforce-encryption-on-saved-data"></a>Vynucení šifrování uložených dat
Správci IT můžou vynutit zásadu, která zajistí, aby byla data ukládaná aplikací do zařízení zašifrovaná.

### <a name="remotely-wipe-corporate-data"></a>Vzdálené vymazání podnikových dat
Správci IT můžou vzdáleně vymazat podniková data z aplikace spravované v Intune, když se zruší registrace zařízení v Intune. Tato funkce je založená na identitě a odstraní jenom soubory, které se vztahují k podnikové identitě koncového uživatele. Kvůli tomu funkce vyžaduje zapojení aplikace. Aplikace může určit identitu, u které má dojít k vymazání, na základě uživatelského nastavení. Když uvedená uživatelská nastavení v aplikaci chybí, výchozí chování je vymazat adresář aplikace a upozornit koncového uživatele, že došlo k odebrání přístupu k prostředkům společnosti.

### <a name="enforce-the-use-of-a-managed-browser"></a>Vynucení používání spravovaného prohlížeče
Správci IT můžou vynutit použití spravovaného prohlížeče v případech, kdy uživatelé otevírají odkazy z aplikací spravovaných v Intune. Pokud uživatelé používají prohlížeč spravovaný v Microsoft Intune, je možné zajistit, aby odkazy v e-mailech v e-mailovém klientovi spravovaném v Intune zůstaly v doméně aplikací spravovaných v Intune.

### <a name="enforce-a-pin-policy"></a>Vynucení zásady kódu PIN
Správci IT můžou vynutit zásadu kódu PIN při spuštění aplikace spravované v Intune. Tato zásada pomáhá zkontrolovat, jestli jsou koncoví uživatelé, kteří zaregistrovali svá zařízení do Microsoft Intune, totožné s osobami, které teď aplikace spouštějí. Když koncoví uživatelé nakonfigurují kód PIN, použije sada Intune App SDK službu Azure Active Directory k ověření přihlašovacích údajů koncového uživatele s přihlašovacími údaji z registrace zařízení.

### <a name="require-users-to-enter-credentials-before-they-can-start-apps"></a>Vyžádání přihlašovacích údajů před spuštěním aplikací
Správci IT můžou vyžadovat, aby koncoví uživatelé před spuštěním aplikací spravovaných v Intune zadali přihlašovací údaje. Sada SDK aplikace Intune poskytuje pomocí služby Azure Active Directory možnost používat jediné přihlášení. To znamená, že jakmile přihlašovací údaje jednou zadáte, použijí se znovu pro následující přihlášení. Sada SDK podporuje také ověřování řešení správy identity [sdružených se službou Azure Active Directory](/active-directory/active-directory-aadconnect-federation-compatibility).

### <a name="check-device-health-and-compliance"></a>Kontrola stavu zařízení a dodržování předpisů
Správci IT můžou před přístupem koncových uživatelů k aplikacím spravovaným v Intune kontrolovat stav zařízení a dodržování podnikových zásad. Na platformě iOS tato zásada kontroluje, jestli zařízení nemá jailbreak. Na platformě Android tato zásada kontroluje, jestli zařízení nemá root.  



<!--HONumber=Dec16_HO3-->


