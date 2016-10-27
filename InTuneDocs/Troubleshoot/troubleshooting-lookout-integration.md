---
title: "Řešení potíží s aplikací Lookout Integration | Microsoft Intune"
description: "Toto téma popisuje řešení nejčastějších potíží s aplikací Lookout Integration"
keywords: 
author: karthikaraman
ms.author: karaman
manager: angrobe
ms.date: 09/13/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0736b5f24065f55d8fbd312395e4bb7226ebf619
ms.openlocfilehash: 5acf5c707a93aa0b5e7cefdcb0b160af09b9cf70


---

# Řešení potíží s aplikací Lookout Integration pomocí služby Intune
Toto téma popisuje některé z nejčastějších problémů, na které můžete narazit při nastavení ochrany před mobilními útoky (MTP) Lookout.
## Řešení potíží při přihlášení
### Chyby 403
Když se přihlásíte ke [konzole Lookout MTP](https://aad.lookout.com), může se zobrazit chyba 403: **nemáte oprávnění pro přístup ke službě** K této situaci může dojít, pokud zadané uživatelské jméno není členem skupiny Azure Active Directory (Azure AD), která je nakonfigurovaná pro přístup ke službě Lookout MTP.

Služba Lookout MTP je nakonfigurovaná tak, aby povolila přístup pouze uživatelům z nakonfigurované skupiny Azure AD. Pokud si nejste jisti, která skupina je nakonfigurovaná tak, aby měla přístup ke službě Lookout MTP, obraťte se na tým podpory služby Lookout.

Tým podpory Lookout můžete kontaktovat následujícími způsoby:

* E-mail: enterprisesupport@lookout.com
* Přihlaste se ke [konzole MTP](http://aad.lookout.com) a přejděte do modulu **Podpora**.
* Přejděte na adresu: https://enterprise.support.lookout.com/hc/en-us/requests a vytvořte žádost o podporu.

### Nelze se přihlásit
Pokud globální správce Azure AD nepřijal úvodní nastavení služby Lookout, může se zobrazit následující chyba.

![snímek přihlašovací obrazovky služby Lookout zobrazující chybu přihlášení](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Pokud chcete tento problém vyřešit, musí se globální správce přihlásit na adrese https://aad.lookout.com/les?action=consent a přijmout výzvu k zahájení nastavení. Podrobnější informace najdete v tématu [Nastavení předplatného pro Lookout MTP](set-up-your-subscription-with-lookout-mtp.md)

## Řešení potíží se stavem zařízení

### Zařízení se nezobrazuje v seznamu zařízení konzoly Lookout MTP

Tato situace může nastat při jednom z následujících scénářů:
* Pokud uživatel, který vlastní toto zařízení, není ve **skupině pro registraci** zadané v **konzole Lookout MTP**.  Přejděte z modulu **Systém** na kartu **Konektor Intune** a podívejte se na nastavení **Správa registrace**.  Měla by se vám zobrazit jedna nebo více skupin Azure AD nakonfigurovaných pro registraci.  Ověřte, jestli je uživatel, který chybějící zařízení vlastní, členem jedné ze zadaných skupin Azure AD.  Až bude nový uživatel přidán do skupiny pro registraci, bude nutné vyčkat, až uplyne nakonfigurovaný interval dotazování (výchozí nastavení je 5 minut). Teprve poté se zařízení zobrazí v modulu **Zařízení** konzoly Lookout MTP.

* Pokud zařízení není podporováno službou Lookout MTP.  Zařízení, která nejsou podporována, se zobrazí v části **Spravovaná zařízení** v nastavení konektoru v konzole Lookout MTP.

### Zařízení bude i nadále hlášeno jako **čekající**

Pokud zařízení zobrazuje stav **Čekající**, znamená to, že koncový uživatel dosud neotevřel aplikaci Lookout for Work a neklepl na tlačítko **Aktivovat**. Další podrobnosti o aktivaci zařízení pomocí aplikace Lookout for Work najdete v následujícím tématu:

[Zobrazí se výzva k instalaci aplikace Lookout for Work na zařízení s Androidem ](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

### Zařízení se v konzole Lookout MTP zobrazuje jako aktivní, ale nemá ID zařízení.  
To znamená, že uživatel, který toto zařízení vlastní, není ve skupině pro registraci zadané v konzole Lookout MTP.   Tento stav může nastat, pokud byl uživatel, který toto zařízení vlastní, odebrán ze skupiny pro registraci, nebo pokud byla odebrána skupina pro registraci, do které tento uživatel patří.

Z modulu **Systém** v konzole Lookout MTP přejděte na kartu **Konektor Intune** a zkontrolujte nastavení **Registrace**.  Měla by se vám zobrazit jedna nebo více skupin Azure AD nakonfigurovaných pro registraci.  Ověřte, jestli je uživatel, který zařízení vlastní, členem jedné ze zadaných skupin Azure AD.  

Zatímco je zařízení v tomto stavu, aplikace Lookout bude uživatele i nadále upozorňovat na veškeré rozpoznané hrozby, ale nebude odesílat informace o hrozbách do služby Intune.

### Zařízení se zobrazuje jako odpojené

Stav odpojeno znamená, že mezi službou Lookout MTP a zařízením neproběhla žádná komunikace po dobu předkonfigurovaného časového intervalu (výchozí nastavení je 30 dní, minimální hodnota je 7 dní). To znamená, že aplikace Portál společnosti nebo aplikace Lookout for Work není na zařízení nainstalována, případně že byla odinstalována. Tento problém by měla vyřešit opětovná instalace aplikací. Když uživatel otevře aplikaci Lookout for Work a aktivuje ji, zařízení provede novou synchronizaci se službami Lookout MTP a Intune.    

### Vynucení opětovné synchronizace v zařízení
Správce může z modulu **Zařízení** v konzole Lookout MTP vybrat zařízení a rozhodnout se jej odstranit.   Až příště vlastník zařízení spustí aplikaci Lookout for Work a klepne na možnost **Aktivovat**, stav zařízení provede úplnou novou synchronizaci.

### Vlastník zařízení již toto zařízení nepoužívá
Musíte zařízení vymazat a požádat nového uživatele, aby se zaregistroval.  V [konzole pro správu Intune](https://manage.microsoft.com) vyberte zařízení, klikněte na něj pravým tlačítkem myši a zvolte možnost **Vyřadit/Vymazat**, čímž zařízení odeberete ze správy. Po vyřazení zařízení jej můžete odstranit.

![snímek obrazovky modulu zařízení v konzole pro správu Intune se zobrazenými možnostmi vyřadit/vymazat](../media/mtp/mtp-retire-device-intune-console.png)

Můžete také přejít v konzole Lookout MTP do modulu **Zařízení** a zvolit možnost **Odstranit**.  

Pokud je nový uživatel členem skupiny pro registraci zadané v konzole Lookout MTP, zařízení se zobrazí ihned poté, co Azure AD přidruží zařízení k novému uživateli.

## Pracovní postupy nápravy dodržování předpisů
[Zobrazí se výzva k instalaci aplikace Lookout for Work na zařízení s Androidem]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)

[Je třeba vyřešit hrozbu, kterou aplikace Lookout for Work objevila na vašem zařízení s Androidem ](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)


### Související témata
[Nastavení předplatného pomocí pro Lookout MTP](https://docs.microsoft.com/en-us/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)



<!--HONumber=Oct16_HO1-->


