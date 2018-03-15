---
title: "Zprávy Portálu společnosti, které se můžou uživatelům zobrazit na zařízeních"
titlesuffix: Microsoft Intune
description: "Vysvětlení různých zpráv, které se můžou koncovým uživatelům zobrazit v aplikaci Portál společnosti"
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 03/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: aanavath
ms.suite: ems
ms.openlocfilehash: e78d43cf1cb96575ebc8d8143b7b4fc1103a9bd1
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2018
---
# <a name="help-end-users-understand-company-portal-app-messages"></a>Vysvětlení zpráv aplikace Portál společnosti pro koncové uživatele

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

> [!NOTE]
> Následující informace se vztahují jenom na zařízení s Androidem 6.0 a novějším.

Tady najdete vysvětlení různých zpráv, které se můžou koncovým uživatelům zobrazit v aplikaci Portál společnosti. Tyto zprávy aplikace se běžně zobrazují v různých okamžicích procesu registrace. Zjistěte, kde se tyto zprávy objevují, co znamenají a co se stane, když uživatel přístup zamítne. Také se dozvíte, jak zprávy nejlépe vysvětlit uživatelům.

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
Přijetím této výzvy umožní uživatel zápis datových protokolů na SD kartu zařízení. Také se tím umožní přesun těchto protokolů pomocí USB kabelu.   

> [!NOTE]
> **Aplikace Portál společnosti nikdy nemá přístup k fotografiím, médiím a souborům uživatele!** Text zprávy je pod kontrolu Googlu a nejde ho změnit.

### <a name="what-happens-if-users-deny-access"></a>Co se stane, když uživatel přístup zamítne
Pokud uživatel přístup zamítne, může pořád odesílat datové protokoly e-mailem, ale tyto protokoly se nezkopírují na SD kartu zařízení.

Při druhém přihlášení k aplikaci Portál společnosti po zamítnutí přístupu se ve zprávě zobrazí zaškrtávací políčko **Příště se už neptat**, takže uživatel může určit, že se tato zpráva už nebude zobrazovat. Pokud uživatel povolí přístup, ale později ho zamítne, zobrazí se tato zpráva při příštím pokusu o odeslání protokolů. Pokud se ale uživatel rozhodne povolit přístup později, může přejít na **Nastavení** > **Aplikace** > **Portál společnosti** > **Oprávnění** > **Úložiště** a toto oprávnění zapnout.


### <a name="how-to-explain-this-to-your-users"></a>Jak to vysvětlit uživatelům
Nasměrujte uživatele na článek [Odeslání protokolů správci IT e-mailem](/intune-user-help/send-logs-to-your-it-admin-by-email-android). 

## <a name="your-company-support-needs-to-give-you-access-to-company-resources"></a>Podpora vaší společnosti vám musí udělit přístup k prostředkům společnosti

### <a name="where-it-appears"></a>Místo zobrazení
Pokud jste aplikaci Portál společnosti nepřidali na seznam **Povolených aplikací** nebo **Aplikací s výjimkou** a uživatel se pokusí přihlásit, přihlášení selže. Zobrazí se tato zpráva:

> **Podpora vaší společnosti vám musí udělit přístup k prostředkům společnosti**  
> Vaše společnost k ochraně vašeho zařízení používá zásady Windows Information Protection. Podpora společnosti musí Portálu společnosti povolit k těmto prostředkům přístup.

### <a name="what-it-means"></a>Význam

Přidejte Portál společnosti na seznam **Povolených aplikací** nebo **Aplikací s výjimkou** v zásadě ochrany aplikací Windows Information Protection (WIP). Další informace najdete v článku [Vytvoření a nasazení zásady ochrany aplikací WIP (Windows Information Protection) u Intune](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune).

### <a name="see-also"></a>Viz taky
[Co říct koncovým uživatelům o používání služby Intune](end-user-educate.md)
