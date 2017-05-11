---
title: "Řešení potíží s aplikací Lookout Integration | Dokumentace Microsoftu"
description: "Toto téma popisuje řešení nejčastějších potíží s aplikací Lookout Integration"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbe0b5f4-b8bc-49f3-85a9-51fb2f226fca
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: 0b5586a06af7658c0c7a328ae1a824f88129039f
ms.contentlocale: cs-cz
ms.lasthandoff: 04/25/2017


---

# <a name="troubleshoot-lookout-integration-with-intune"></a>Řešení potíží s aplikací Lookout Integration pomocí služby Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Toto téma popisuje některé z nejčastějších problémů, na které můžete narazit při nastavení ochrany před mobilními útoky (MTP) Lookout.

**Chyby při přihlášení**

## <a name="403-errors"></a>Chyby 403
Když se přihlásíte ke [konzole Lookout MTP](https://aad.lookout.com), zobrazí se chyba 403: **Nemáte oprávnění pro přístup ke službě.** K této situaci může dojít, pokud zadané uživatelské jméno není členem skupiny Azure Active Directory (AD), která je nakonfigurovaná pro přístup k Lookout MTP.

Přístup k Lookout MTP mají jenom uživatelé z nakonfigurované skupiny Azure AD. Pokud chcete zjistit, která skupina je nakonfigurovaná tak, aby měla přístup k Lookout MTP, obraťte se na tým podpory Lookoutu:

* E-mail: enterprisesupport@lookout.com
* Přihlaste se ke [konzole MTP](http://aad.lookout.com) a přejděte do modulu **Podpora**.
* Přejděte na adresu https://enterprise.support.lookout.com/hc/requests a vytvořte žádost o podporu.

## <a name="unable-to-sign-in"></a>Nelze se přihlásit
Pokud globální správce Azure AD nepřijal úvodní nastavení Lookoutu, zobrazí se následující chyba.

![snímek přihlašovací obrazovky služby Lookout zobrazující chybu přihlášení](../media/mtp/lookout-mtp-consent-not-accepted-error.png)

Pokud chcete tento problém vyřešit, musí se globální správce přihlásit na adrese https://aad.lookout.com/les?action=consent a přijmout výzvu k zahájení nastavení. Podrobnější informace najdete v tématu [Nastavení předplatného pro Lookout MTP](../deploy-use/set-up-your-subscription-with-lookout-mtp.md)

**Potíže se stavem zařízení**

## <a name="device-missing-from-lookout-device-list"></a>Dané zařízení v seznamu zařízení služby Lookout chybí

Tato situace může nastat při jednom z následujících scénářů:
* Uživatel daného zařízení není ve **skupině pro registraci** zadané v **konzole Lookout MTP**.  V [konzole Lookout](http://aad.lookout.com) přejděte na **Systém** > **Konektor Intune** > **Správa registrace**.  Zkontrolujte skupiny Azure AD nakonfigurované pro registraci a ověřte, že uživatel zařízení je členem některé skupiny Azure AD.  Po přidání uživatele do skupiny pro registraci je nutné vyčkat, až uplyne nakonfigurovaný interval dotazování (výchozí nastavení je 5 minut). Teprve poté se zařízení zobrazí v modulu **Zařízení** konzoly Lookout MTP.
* Pokud zařízení není podporováno službou Lookout MTP.  Zařízení, která nejsou podporována, se zobrazí v části **Spravovaná zařízení** v nastavení konektoru v konzole Lookout MTP.

### <a name="device-reported-as-pending"></a>Zařízení se zobrazuje jako **čekající**

Zařízení zobrazuje stav **Čekající**, pokud koncový uživatel dosud neotevřel aplikaci Lookout for Work a neklepl na tlačítko **Aktivovat**. Další podrobnosti o aktivaci zařízení s aplikací Lookout for Work najdete v tématu [Jste vyzváni k instalaci aplikace Lookout for Work na zařízení s Androidem](http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android) nebo [Jste vyzváni k instalaci aplikace Lookout for Work na zařízení s iOSem](https://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-ios).

## <a name="device-whos-active-but-has-no-device-id"></a>Zařízení je aktivní, ale nemá ID zařízení
Pokud aktivní zařízení v konzole Lookout MTP nemá ID zařízení, není uživatel daného zařízení ve skupině pro registraci. Tento stav může nastat, pokud byl uživatel daného zařízení odebrán ze skupiny pro registraci nebo pokud byla skupina pro registraci odebrána.

V [konzole Lookout](http://aad.lookout.com) přejděte na **Systém** > **Konektor Intune** > **Registrace** a zkontrolujte nastavení.  Zkontrolujte skupiny Azure AD a ověřte, že uživatel zařízení je členem některé skupiny Azure AD.

Zatímco je zařízení v tomto stavu, aplikace Lookout bude uživatele i nadále upozorňovat na veškeré rozpoznané hrozby, ale nebude odesílat informace o hrozbách do služby Intune.

## <a name="device-reported-as-disconnected"></a>Zařízení se zobrazuje jako **odpojené**

**Odpojení** znamená, že synchronizace daného zařízení s Lookout MTP se v nakonfigurovaném intervalu neprovedla (výchozí nastavení je 30 dnů, přičemž minimální hodnota je 7 dnů). Aplikace Portál společnosti nebo aplikace Lookout for Work v zařízení chybí. Tento problém by měla vyřešit opětovná instalace aplikací. Když uživatel otevře aplikaci Lookout for Work a aktivuje ji, zařízení provede novou synchronizaci se službami Lookout MTP a Intune.

### <a name="forcing-a-device-sync"></a>Vynucení synchronizace zařízení
Správce může z modulu **Zařízení** v konzole Lookout MTP vybrat zařízení a rozhodnout se jej odstranit.   Až příště vlastník zařízení spustí aplikaci Lookout for Work a klepne na možnost **Aktivovat**, stav zařízení provede úplnou novou synchronizaci.

## <a name="device-has-a-new-user"></a>Zařízení má nového uživatele
Měli byste zařízení vymazat a požádat nového uživatele, aby se zaregistroval.  V [konzole pro správu Intune](https://manage.microsoft.com) vyberte zařízení, klikněte na něj pravým tlačítkem myši a zvolte možnost **Vyřadit/Vymazat**, čímž zařízení odeberete ze správy. Po vyřazení zařízení jej můžete odstranit.

![snímek obrazovky modulu zařízení v konzole pro správu Intune se zobrazenými možnostmi vyřadit/vymazat](../media/mtp/mtp-retire-device-intune-console.png)

Můžete také přejít v [konzole Lookout](http://aad.lookout.com) do modulu **Zařízení** a zvolit možnost **Odstranit**.

Pokud je nový uživatel v Lookout MTP členem skupiny pro registraci, zobrazí se zařízení ihned poté, co Azure AD přidruží zařízení k novému uživateli.

## <a name="compliance-remediation-workflows"></a>Pracovní postupy nápravy dodržování předpisů
- [Zobrazuje se výzva k instalaci aplikace Lookout for Work na zařízení s Androidem]( http://docs.microsoft.com/intune/enduser/you-are-prompted-to-install-lookout-for-work-android)
- [Je třeba vyřešit hrozbu, kterou objevila aplikace Lookout for Work na zařízení s Androidem](http://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-android)
- [Je třeba vyřešit hrozbu, kterou aplikace Lookout for Work objevila na vašem zařízení s iOSem](https://docs.microsoft.com/intune/enduser/you-need-to-resolve-a-threat-found-by-lookout-for-work-ios)


### <a name="see-also"></a>Související témata
[Nastavení předplatného pro Lookout MTP](https://docs.microsoft.com/intune/deploy-use/set-up-your-subscription-with-lookout-mtp)

