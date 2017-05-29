---
title: "Zprávy Portálu společnosti, které uživatelé mohou vidět na Androidu | Dokumentace Microsoftu"
description: "Tento článek popisuje zprávy aplikace Portál společnosti, které se mohou zobrazit koncovým uživatelům Intune."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: jeffgilb
ms.suite: ems
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 81b85ea73759faaa71cbc404e14e8196e9455fb4
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="help-end-users-understand-company-portal-app-messages"></a>Vysvětlení zpráv aplikace Portál společnosti pro koncové uživatele

> [!NOTE]
> Následující informace se vztahují jenom na zařízení s Androidem 6.0 a novějším.

V různých fázích procesu registrace uvidí koncoví uživatelé dvě odlišné zprávy, které mohou být příčinou znepokojení.

- __Povolit pro Portál společnosti telefonování a správu telefonních hovorů?__
- __Povolit pro Portál společnosti přístup k fotkám, médiím a souborům ve vašem zařízení?__

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a>Povolit pro Portál společnosti telefonování a správu telefonních hovorů?

### <a name="where-it-appears"></a>Místo zobrazení
Zpráva **Povolit pro Portál společnosti telefonování a správu telefonních hovorů?** se zobrazí, když uživatel během registrace svého zařízení klepne v aplikaci Portál společnosti na možnost **Zaregistrovat**.

### <a name="what-it-means"></a>Význam
Přijetím této výzvy uživatel umožní, aby se telefonní číslo a číslo IMEI jeho zařízení odeslala do služby Intune. Tyto údaje se objeví v konzole pro správu na stránce __Hardware__.

> [!NOTE]
> **Aplikace Portál společnosti nikdy netelefonuje ani nespravuje telefonní hovory!** Text zprávy je pod kontrolu Googlu a nejde ho změnit.

Stránku **Hardware** zobrazíte tak, že přejdete na **Skupiny** > **Všechna mobilní zařízení** > **Zařízení**. Vyberte zařízení uživatele a pak použijte možnosti **Zobrazit vlastnosti** > **Hardware**.

### <a name="what-happens-if-users-deny-access"></a>Co se stane, když uživatel přístup zamítne
Pokud uživatel přístup zamítne, může aplikaci Portál společnosti dál používat a zaregistrovat své zařízení. Na stránce __Hardware__ v konzole pro správu ale bude telefonní číslo a číslo IMEI zařízení prázdné. Při druhém přihlášení k aplikaci Portál společnosti po zamítnutí přístupu se ve zprávě zobrazí zaškrtávací políčko **Příště se už neptat**, takže uživatel může zobrazování této výzvy zastavit.

Pokud uživatel povolí přístup, ale později ho zamítne, zobrazí se tato zpráva při přihlášení k aplikaci Portál společnosti, které následuje po registraci zařízení.

Pokud se uživatel rozhodne povolit přístup později, může přejít na **Nastavení** > **Aplikace** > **Portál společnosti** > **Oprávnění** > **Telefon** a zapnout ho.

### <a name="how-to-explain-this-to-your-users"></a>Jak to vysvětlit uživatelům
Nasměrujte uživatele na článek [Registrace zařízení s Androidem v Intune](/intune-user-help/enroll-your-device-in-intune-android), kde najdou další informace.

## <a name="allow-company-portal-to-access-your-contacts"></a>Povolit pro Portál společnosti přístup k vašim kontaktům?

### <a name="where-it-appears"></a>Místo zobrazení
Zpráva **Povolit pro Portál společnosti přístup k vašim kontaktům?** se zobrazí, když uživatel během registrace svého zařízení klepne v aplikaci Portál společnosti na možnost **Zaregistrovat**.

### <a name="what-it-means"></a>Význam
Přijetím této výzvy uživatel umožní, aby služba Intune vytvořila pracovní účet a spravovala identitu služby Azure Active Directory, která je pro uživatele registrovaná na tomto zařízení.

> [!NOTE]
> **Společnost Microsoft nebude nikdy přistupovat k vašim kontaktům!** Text zprávy je pod kontrolu Googlu a nejde ho změnit.

### <a name="what-happens-if-users-deny-access"></a>Co se stane, když uživatel přístup zamítne
Pokud uživatel přístup zamítne, nebude zařízení v Intune zaregistrováno a nebude možné ho spravovat. Při druhém přihlášení k aplikaci Portál společnosti po zamítnutí přístupu se ve zprávě zobrazí zaškrtávací políčko **Příště se už neptat**, takže uživatel může zobrazování této výzvy zastavit.

Pokud uživatel povolí přístup, ale později ho zamítne, zobrazí se tato zpráva při přihlášení k aplikaci Portál společnosti, které následuje po registraci zařízení.

Pokud se uživatel rozhodne povolit přístup později, může přejít na **Nastavení** > **Aplikace** > **Portál společnosti** > **Oprávnění** > **Telefon** a zapnout ho.

### <a name="how-to-explain-this-to-your-users"></a>Jak to vysvětlit uživatelům
Nasměrujte uživatele na článek [Registrace zařízení s Androidem v Intune](/intune-user-help/enroll-your-device-in-intune-android), kde najdou další informace.

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a>Povolit pro Portál společnosti přístup k fotkám, médiím a souborům ve vašem zařízení?

### <a name="where-it-appears"></a>Místo zobrazení
Zpráva **Povolit pro Portál společnosti přístup k fotkám, médiím a souborům ve vašem zařízení?** se zobrazí, když uživatel klepnutím na **Odeslat data** odešle protokoly svému správci IT.

### <a name="what-it-means"></a>Význam
Přijetím této výzvy umožní uživatel zápis datových protokolů na SD kartu zařízení a jejich přesun pomocí USB kabelu.   

> [!NOTE]
> **Aplikace Portál společnosti nikdy nemá přístup k fotografiím, médiím a souborům uživatele!** Text zprávy je pod kontrolu Googlu a nejde ho změnit.

### <a name="what-happens-if-users-deny-access"></a>Co se stane, když uživatel přístup zamítne
Pokud uživatel přístup zamítne, může pořád odesílat datové protokoly e-mailem, ale tyto protokoly se nezkopírují na SD kartu zařízení.

Při druhém přihlášení k aplikaci Portál společnosti po zamítnutí přístupu se ve zprávě zobrazí zaškrtávací políčko **Příště se už neptat**, takže uživatel může určit, že se tato zpráva už nebude zobrazovat. Pokud uživatel povolí přístup, ale později ho zamítne, zobrazí se tato zpráva při příštím pokusu o odeslání protokolů. Pokud se uživatel rozhodne povolit přístup později, může přejít na **Nastavení** > **Aplikace** > **Portál společnosti** > **Oprávnění** > **Úložiště** a toto oprávnění zapnout.


### <a name="how-to-explain-this-to-your-users"></a>Jak to vysvětlit uživatelům
Nasměrujte uživatele na článek [Odeslání protokolů správci IT e-mailem](/intune-user-help/send-logs-to-your-it-admin-by-email-android). Můžete jim nabídnout také článek [Odeslání protokolů správci IT kabelem](/intune-user-help/send-logs-to-your-it-admin-by-cable-android) pokud chcete, aby obě metody porovnali.


### <a name="see-also"></a>Související témata
[Co říct koncovým uživatelům o používání služby Intune](/intune-classic/deploy-use/what-to-tell-your-end-users-about-using-microsoft-intune)

