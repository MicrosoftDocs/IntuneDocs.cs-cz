---
title: Nastavení přístupu k prostředkům společnosti | Microsoft Docs
description: Popisuje, jak začít spravovat zařízení s iOSem pomocí Intune
keywords: ''
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 6474688a09c4063c55eff07f3cf84ebcb1911c65
ms.sourcegitcommit: c29241a88e67137f0fbc678b9eae1db2b2cded14
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2018
---
# <a name="set-up-access-to-your-company-resources"></a>Nastavení přístupu k prostředkům společnosti

Vaše společnost má spoustu vlastnických informací z e-mailu, souborů, sítí a dalších zdrojů. Vaše společnost používá Microsoft Intune k lepší ochraně těchto informací při přístupu ze zařízení s iOSem. Je tak možné spravovat tyto prostředky, zvýšit jejich zabezpečení a dát vám volnost při výběru zařízení, s jakým chcete pracovat.

> [!NOTE]
> Pokud se pokoušíte získat přístup k firemnímu e-mailu v aplikaci Mail, pravděpodobně se vám zobrazí výzva ke správě zařízení, abyste zajistili jeho zabezpečení. Podle pokynů uvedených níže získáte přístup ke svému e-mailu a dalším prostředkům společnosti na zařízení s iOSem.

## <a name="before-you-start"></a>Než začnete

- Ujistěte se, že když začnete, budete moct celý proces dokončit najednou. Přerušení na více než několik minut obvykle celý proces zastaví a bude vyžadovat jeho opětovné zahájení.
- Pokud by se proces nezdařil, budete se muset vrátit do aplikace Portál společnosti a začít znovu.
- Zkontrolujte, že je funkční Wi-Fi a že aplikace Safari funguje ve vašem zařízení.
- Stáhněte a nainstalujte [aplikaci Portál společnosti Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md).


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>Nastavení přístupu k prostředkům společnosti pomocí aplikace Portál společnosti

|Co se zobrazí|Vysvětlení|
|---|---|
|![Přihlašovací obrazovka aplikace Portál společnosti s tlačítkem Přihlásit se v dolní části.](./media/ios-01-cp-enroll-1802.png)|Otevřete aplikaci Portál společnosti na zařízení a klepněte na **Přihlásit se**.|
|![Výzva k přihlášení do služby Azure AD.](./media/ios-02-cp-enroll-1802.png)|Zadejte e-mailovou adresu vaší společnosti a pak klepněte na **Další**.|
|![Výzva k zadání hesla Azure AD.](./media/ios-03-cp-enroll-1802.png)|Zadejte heslo a potom klepněte na **Přihlásit se**.|
|![Úvodní obrazovka načítání firemních prostředků](./media/ios-04-cp-enroll-1802.png)|Počkejte na načtení.|
|![Stránka Podmínky a ujednání](./media/ios-05-cp-enroll-1802.png)|Přečtěte si podmínky a ujednání a vyberte možnost **Přijmout vše**.|
|![Nastavte obrazovku firemního přístupu. Aktuálně je potřeba vyřešit správu a nastavení.](./media/ios-06-cp-enroll-1802.png)|Klepnutím na volbu **Začít** zahájíte proces zpřístupnění prostředků společnosti pro vaše zařízení. Pokud to nemůžete udělat teď hned, můžete proces **Odložit**, ale znamená to, že nebudete moct získat e-mail, dokumenty atd.|
|![Obrazovka Co uvidí moje společnost.](./media/ios-07-cp-enroll-1802.png)|**Další informace** o tom, co vaše může společnost zobrazit, získáte klepnutím na odkaz dole. Jinak klepněte na **Pokračovat**.|
|![Obrazovka Co dál?](./media/ios-08-cp-enroll-1802.png)|Tato obrazovka vás provede kroky instalace. K dokončení procesu budete využívat prohlížeč Safari, aplikaci Nastavení a aplikaci Portál společnosti. Klepněte na **Pokračovat**.|
|![Načítání obrazovky po klepnutí na možnost Další na obrazovce Co dál](./media/ios-09-cp-enroll-1802.png)|Počkejte na načtení.|
|![Přepnutí do Safari pro registraci](./media/ios-7-cp-enroll-1711.png)|Přesměruje vás to do prohlížeče Safari, abyste získali informace o správě vašeho zařízení.|
|![Výzva systému ke spuštění aplikace Nastavení](./media/ios-8-cp-enroll-1711.png)|Klepnutím na **Povolit** otevřete aplikaci Nastavení, která stáhne konfigurační profil. Touto instalací umožníte vaší společnosti spravovat podnikové informace ve vašem zařízení.|
|![Otevřený profil v nastavení](./media/ios-9-cp-enroll-1711.png)|Klepněte na **Instalovat**.|
|![Modální dialogové okno instalace profilu z dolní části obrazovky](./media/ios-10-cp-enroll-1711.png)|Klepněte na **Instalovat**.|
|![Obrazovka načítání instalace profilu](./media/ios-11-cp-enroll-1711.png)|Počkejte na načtení.|
|![Obrazovka upozornění správy profilu](./media/ios-12-cp-enroll-1711.png)|Toto upozornění vydané společností Apple poskytuje více informací o typech akcí, které lze provést v zařízení v rámci správy. Přečtěte si další informace o tom, [jaké informace může vaše společnost zobrazit](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).|
|![Výzva systému s žádostí o vztah důvěryhodnosti vzdálené správy](./media/ios-13-cp-enroll-1711.png)|Klepnutím na **Důvěřovat** umožníte vaší společnosti spravovat podnikové informace a nastavení v daném zařízení.|
|![Obrazovka načítání pro dokončení instalace profilu](./media/ios-14-cp-enroll-1711.png)|Počkejte na načtení.|
|![Obrazovka nainstalovaného profilu](./media/ios-15-cp-enroll-1711.png)|Váš profil je nainstalovaný a podnikové informace a nastavení vašeho zařízení již brzo bude možné spravovat.|
|![Přepnutí do Safari pro registraci](./media/ios-16-cp-enroll-1711.png)|Přecházíte zpět do prohlížeče Safari, abyste dokončili získání informací o správě vašeho zařízení. |
|![Výzva systému k otevření portálu společnosti](./media/ios-17-cp-enroll-1711.png)|Klepněte na **Otevřít**.|
|![Obrazovka načítání prostředků společnosti](./media/ios-21-cp-enroll-1802.png)|Počkejte na načtení.|
|![Vyberte kategorii zařízení v aplikaci portálu společnosti.](./media/ios-22-cp-enroll-1802.png)|Zvolte nejvhodnější kategorii pro vaše zařízení. To obvykle souvisí s majitelem zařízení nebo s jeho převládajícím umístěním.|
|![Vybraná kategorie](./media/ios-23-cp-enroll-1802.png)||
|![Správa zařízení probíhá úspěšně. Teď je potřeba aktualizovat nastavení.](./media/ios-24-cp-enroll-1802.png)|Úspěšně jste začali vaše zařízení spravovat. Existují pravděpodobně stále nastavení, jako je délka hesla, která po vás může chtít vaše společnost aktualizovat. Pokračujte klepnutím na **Pokračovat**.|
|![Potvrzení nastavení zařízení](./media/ios-25-cp-enroll-1802.png)|Portál společnosti zkontroluje, zda je nutné aktualizovat některá nastavení.|
|![Kontrola nastavení byla dokončena s nesprávnou verzí operačního systému.](./media/ios-26-cp-enroll-1802.png)|Portál společnosti vám poskytne pokyny, jak opravit problémy s nastavením. Jakmile dokončíte opravu problémů, klepněte na možnost **Zkontrolovat nastavení**.|
|![Obrazovka načítání pro potvrzení nastavení zařízení](./media/ios-27-cp-enroll-1802.png)|Zařízení zkontroluje, jestli jsou nastavení dostatečně zabezpečená pro přístup k prostředkům společnosti.|
|![Úspěšně zaregistrované a aktualizované nastavení](./media/ios-28-cp-enroll-1802.png)|Gratulujeme! Právě jste zaregistrovali své zařízení do služby Intune.|

> [!Note]
> K dokončení přípravy zařízení pro správu je potřeba dokončit ještě několik kroků. Přečtěte si další informace o [registraci zařízení s použitím softwaru pro správu telekomunikačních výdajů](enroll-your-device-with-telecom-expense-management-ios.md). Pokud vaše organizace používá program registrace zařízení společnosti Apple, přečtěte si další informace [tady](enroll-your-device-dep-ios.md).

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog).
