---
# required metadata

title: Vysvětlení zpráv aplikace Portál společnosti pro koncové uživatele | Microsoft Intune
description:
keywords:
author: staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Vysvětlení zpráv aplikace Portál společnosti pro koncové uživatele

Následující informace se vztahují jenom na zařízení s Androidem 6.0 a novějším. Při registraci zařízení koncoví uživatelé vidí dvě zprávy, které se zobrazují během procesu registrace:

- Povolit pro Portál společnosti telefonování a správu telefonních hovorů?
- Povolit pro Portál společnosti přístup k fotkám, médiím a souborům ve vašem zařízení?

V následujících odstavcích najdete podrobnosti o těchto zprávách a informace, které můžete sdílet s koncovými uživateli.

## Povolit pro Portál společnosti telefonování a správu telefonních hovorů?

### Text zprávy a kde se zobrazí
Text zprávy je **Povolit pro Portál společnosti telefonování a správu telefonních hovorů?** a zobrazí se, když se uživatel poprvé přihlásí do aplikace Portál společnosti a začne registrovat svoje zařízení.

### Co tato zpráva znamená
Tato zpráva vyzývá uživatele, aby povolili odeslání čísla IMEI a telefonního čísla zařízení službě Intune a zobrazení těchto informací v konzole správce na stránce Hardware.

> [!NOTE]
> **Aplikace Portál společnosti nikdy netelefonuje ani nespravuje telefonní hovory!** Text zprávy je pod kontrolu Googlu a nejde ho změnit.

Pokud chcete zobrazit stránku **Hardware**, použijte možnosti **Skupiny** > **Všechna mobilní zařízení** > **Zařízení**. Vyberte zařízení uživatele a pak použijte možnosti **Zobrazit vlastnosti** > **Hardware**.

### Co se stane, když uživatel povolí nebo zakáže přístup
Pokud uživatel povolí přístup, IMEI a telefonní číslo zařízení se zobrazí v konzole správce na stránce Hardware.

Pokud uživatel zakáže přístup, může i dál používat aplikaci Portál společnosti a registrovat zařízení, ale IMEI a telefonní číslo jeho zařízení se na stránce Hardware v konzole správce nezobrazí. Při druhém přihlášení k aplikaci Portál společnosti po odepření přístupu se ve zprávě zobrazí zaškrtávací políčko **Příště se už neptat**, takže uživatel může určit, že se tato zpráva už nebude zobrazovat.

Pokud uživatel povolí přístup, ale později ho odepře, tato zpráva se zobrazí při přihlášení k aplikaci Portál společnosti, které následuje po registraci zařízení.</br></br>Pokud se uživatelé rozhodnou povolit přístup později, mohou přejít na **Nastavení** > **Aplikace** > **Portál společnosti** > **Oprávnění** > **Telefon** a toto oprávnění zapnout.

### Kam nasměrovat uživatele, pokud potřebují další informace
Krok 5 v tématu věnovaném [registraci zařízení s Androidem v Intune](/Intune/EndUser/enroll-your-device-in-intune-android)

## Povolit pro Portál společnosti přístup k fotkám, médiím a souborům ve vašem zařízení?

### Text zprávy a kde se zobrazí
Text zprávy je **Povolit pro Portál společnosti přístup k fotkám, médiím a souborům ve vašem zařízení?** a zobrazí se, když uživatel klepnutím na **Odeslat data** odešle datové protokoly svému správci IT.

### Co tato zpráva znamená
Tato zpráva vyzývá uživatele, aby zařízení povolil zápis datových protokolů na kartu SD zařízení a umožnil jejich přesun pomocí kabelu USB.   

> [!NOTE]
> **Aplikace Portál společnosti nikdy nemá přístup k fotografiím, médiím a souborům uživatele.** Text zprávy je pod kontrolu Googlu a nejde ho změnit.

### Co se stane, když uživatel povolí nebo zakáže přístup
Pokud uživatel povolí přístup, protokoly se zkopírují na kartu SD.

Pokud uživatel zakáže přístup, může i dál posílat datové protokoly, ale tyto protokoly se nezkopírují na kartu SD zařízení.

Při druhém přihlášení k aplikaci Portál společnosti po odepření přístupu se ve zprávě zobrazí zaškrtávací políčko **Příště se už neptat**, takže uživatel může určit, že se tato zpráva už nebude zobrazovat. Pokud uživatel povolí přístup, ale později ho odepře, tato zpráva se zobrazí při příštím pokusu o odeslání protokolu. Pokud se uživatelé rozhodnou povolit přístup později, mohou přejít na **Nastavení** > **Aplikace** > **Portál společnosti** > **Oprávnění** > **Úložiště** a toto oprávnění zapnout.

### Kam nasměrovat uživatele, pokud potřebují další informace
[Odeslání protokolů s diagnostickými daty e-mailem vašemu správci IT](/Intune/EndUser/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)


### Související témata
[Co říct koncovým uživatelům o používání služby Intune](/intune/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune.md)


<!--HONumber=May16_HO2-->


