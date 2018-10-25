---
title: Nastavení přístupu zařízení s iOSem k prostředkům společnosti | Microsoft Docs
description: Popisuje, jak začít spravovat zařízení s iOSem pomocí Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 10/05/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6eeec7aa-1b07-4ce3-894c-13e09b89bdd4
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 85d0df026e49b36e148620ce2d06b4afaaf98ace
ms.sourcegitcommit: d92caead1d96151fea529c155bdd7b554a2ca5ac
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/06/2018
ms.locfileid: "48827883"
---
# <a name="set-up-ios-device-access-to-your-company-resources"></a>Nastavení přístupu zařízení s iOSem k prostředkům společnosti

Zaregistrujte si zařízení s iOSem pomocí aplikace Portál společnosti v Intune a získejte zabezpečený přístup k e-mailům, souborům a aplikacím vaší organizace.

Než budete moct přistupovat k interním datům z podnikového nebo osobního zařízení, vyžaduje se, aby bylo vaše zařízení spravované. Jakmile je vaše zařízení spravované, vaše organizace přiřadí zařízení zásady a aplikace prostřednictvím poskytovatele správy mobilních zařízení (MDM). 

Pokud chcete na zařízení udržovat přístup k pracovním nebo školním datům, je nutné nakonfigurovat ho tak, aby odpovídalo upřednostňovaným nastavením vaší organizace. V tomto článku se dozvíte, jak vám může aplikace Portál společnosti pomoct při registraci, konfiguraci a údržbě zařízení, které má splňovat tyto požadavky.

> [!NOTE]
> Pokud jste se pokusili přistoupit k podnikovému e-mailu v aplikaci Pošta a zobrazila se vám výzva ke správě vašeho zařízení, jste na správném místě. Podle pokynů uvedených níže získáte přístup ke svému e-mailu a dalším prostředkům společnosti na zařízení s iOSem.

## <a name="what-to-expect-from-the-company-portal-app"></a>Co čekat od aplikace Portál společnosti

### <a name="security"></a>Zabezpečení
Při počátečním nastavení vás aplikace požádá, abyste se ve vaší organizaci ověřili. Potom vás informuje o všech nastaveních, která musíte aktualizovat. Organizace si například často určují požadavky na minimální a maximální délku hesla, které musíte splnit.    

### <a name="protection"></a>Protection
Po registraci zařízení bude aplikace Portál společnosti i nadále kontrolovat, že je chráněno. Pokud si například nainstalujete aplikaci z nedůvěryhodného zdroje, upozorní vás a dokonce vám může i odvolat přístup k firemním datům. Zásady ochrany aplikací, jako je tato, jsou v organizacích běžné. Často vyžadují, abyste, než budete moct znovu získat přístup, odinstalovali nedůvěryhodnou aplikaci.

### <a name="setting-notifications"></a>Nastavení oznámení
Pokud po registraci vaše organizace vynucuje nový požadavek na zabezpečení (například vícefaktorové ověřování), aplikace Portál společnosti vás o něm informuje. Budete tak mít možnost si nastavení upravit, abyste se zařízením mohli dále pracovat.  

Další informace o registraci najdete v tématu s informacemi o tom, [co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení](https://docs.microsoft.com//intune-user-help/what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios). 

## <a name="before-you-start"></a>Než začnete

- Ujistěte se, že když zahájíte registraci, budete moct celý proces dokončit najednou. Pokud ho přerušíte na dobu delší než několik minut, nastavení se může ukončit a bude potřeba začít znovu.  
- Pokud by se proces nezdařil, vraťte se do aplikace Portál společnosti a začněte znovu.  
- Zkontrolujte, že je funkční Wi-Fi a že ve vašem zařízení funguje aplikace Safari.
- Stáhněte a nainstalujte [aplikaci Portál společnosti Intune](install-and-sign-in-to-the-intune-company-portal-app-ios.md).  


## <a name="using-the-company-portal-app-to-set-up-access-to-company-resources"></a>Nastavení přístupu k prostředkům společnosti pomocí aplikace Portál společnosti

|Co se zobrazí|Vysvětlení|
|---|---|
|![Přihlašovací obrazovka aplikace Portál společnosti s tlačítkem Přihlásit se v dolní části](./media/ios-01-cp-enroll-1802.png)|Otevřete aplikaci Portál společnosti a klepněte na **Přihlásit se**.|
|![Výzva k přihlášení do služby Azure AD](./media/ios-02-cp-enroll-1802.png)|Zadejte e-mailovou adresu vaší společnosti a pak klepněte na **Další**.|
|![Výzva k zadání hesla Azure AD.](./media/ios-03-cp-enroll-1802.png)|Zadejte heslo a potom klepněte na **Přihlásit se**.|
|![Úvodní obrazovka načítání firemních prostředků](./media/ios-04-cp-enroll-1802.png)|Počkejte, až se tato obrazovka načte.|
|![Stránka Podmínky a ujednání](./media/ios-05-cp-enroll-1802.png)|Přečtěte si podmínky a ujednání a vyberte možnost **Přijmout vše**.|
|![Nastavte obrazovku firemního přístupu. Aktuálně je potřeba vyřešit správu a nastavení.](./media/ios-06-cp-enroll-1802.png)|Klepnutím na volbu **Začít** zahájíte proces zpřístupnění prostředků společnosti pro vaše zařízení. Pokud to nemůžete udělat teď hned, můžete proces **Odložit**, ale znamená to, že nebudete moct získat e-mail, dokumenty atd.|
|![Obrazovka Co uvidí moje společnost.](./media/ios-07-cp-enroll-1802.png)|**Další informace** o tom, co vaše může společnost zobrazit, získáte klepnutím na odkaz dole. Jinak klepněte na **Pokračovat**.|
|![Obrazovka Co dál?](./media/ios-08-cp-enroll-1802.png)|Tato obrazovka vás provede kroky instalace. Budete využívat prohlížeč Safari, aplikaci Nastavení a aplikaci Portál společnosti. Klepněte na **Pokračovat**.|
|![Načítání obrazovky po klepnutí na možnost Další na obrazovce Co dál](./media/ios-09-cp-enroll-1802.png)|Počkejte, až se tato obrazovka načte.|
|![Přepnutí do Safari pro registraci](./media/ios-cp-sent-to-safari-1808.png)|Přesměruje vás to do prohlížeče Safari, abyste získali informace o správě vašeho zařízení.|
|![Výzva systému ke spuštění aplikace Nastavení](./media/ios-8-cp-enroll-1711.png)|Klepnutím na **Povolit** otevřete aplikaci Nastavení, která stáhne konfigurační profil. Touto instalací umožníte vaší společnosti spravovat podnikové informace ve vašem zařízení.|
|![Snímek obrazovky s obrazovkou Nainstalovat profil v nastaveních zařízení](./media/ios-9-cp-enroll-1711.png)|Klepněte na **Instalovat**.|
|![Modální dialogové okno instalace profilu z dolní části obrazovky](./media/ios-10-cp-enroll-1711.png)|Klepněte na **Instalovat**.|
|![Obrazovka načítání instalace profilu](./media/ios-11-cp-enroll-1711.png)|Počkejte, až se tato obrazovka načte.|
|![Obrazovka upozornění správy profilu](./media/ios-12-cp-enroll-1711.png)|Toto upozornění vydané společností Apple poskytuje více informací o typech akcí, které lze provést v zařízení v rámci správy. Přečtěte si další informace o tom, [jaké informace může vaše společnost zobrazit](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).|
|![Výzva systému s žádostí o vztah důvěryhodnosti vzdálené správy](./media/ios-13-cp-enroll-1711.png)|Klepnutím na **Důvěřovat** umožníte vaší společnosti spravovat podnikové informace a nastavení v daném zařízení.|
|![Obrazovka načítání pro dokončení instalace profilu](./media/ios-14-cp-enroll-1711.png)|Počkejte, až se tato obrazovka načte.|
|![Obrazovka nainstalovaného profilu](./media/ios-15-cp-enroll-1711.png)|Váš profil je nainstalovaný a podnikové informace a nastavení vašeho zařízení již brzo bude možné spravovat.|
|![Přepnutí do Safari pro registraci](./media/ios-16-cp-enroll-1711.png)|Přecházíte zpět do prohlížeče Safari, abyste dokončili získání informací o správě vašeho zařízení. |
|![Výzva systému k otevření portálu společnosti](./media/ios-17-cp-enroll-1711.png)|Klepněte na **Otevřít**.|
|![Obrazovka načítání prostředků společnosti](./media/ios-21-cp-enroll-1802.png)|Počkejte, až se tato obrazovka načte.|
|![Vyberte kategorii zařízení v aplikaci portálu společnosti.](./media/ios-22-cp-enroll-1802.png)|Zvolte nejvhodnější kategorii pro vaše zařízení. To obvykle souvisí s majitelem zařízení nebo s jeho převládajícím umístěním.|
|![Vybraná kategorie](./media/ios-23-cp-enroll-1802.png)||
|![Správa zařízení probíhá úspěšně. Teď je potřeba aktualizovat nastavení.](./media/ios-24-cp-enroll-1802.png)|Úspěšně jste začali vaše zařízení spravovat. Existují pravděpodobně stále nastavení, jako je délka hesla, která po vás může chtít vaše společnost aktualizovat. Pokračujte klepnutím na **Pokračovat**.|
|![Potvrzení nastavení zařízení](./media/ios-25-cp-enroll-1802.png)|Portál společnosti zkontroluje, zda je nutné aktualizovat některá nastavení.|
|![Kontrola nastavení byla dokončena s nesprávnou verzí operačního systému.](./media/ios-26-cp-enroll-1802.png)|Portál společnosti vám poskytne pokyny, jak opravit problémy s nastavením. Jakmile dokončíte opravu problémů, klepněte na možnost **Zkontrolovat nastavení**.|
|![Obrazovka načítání pro potvrzení nastavení zařízení](./media/ios-27-cp-enroll-1802.png)|Zařízení zkontroluje, jestli jsou nastavení dostatečně zabezpečená pro přístup k prostředkům společnosti.|
|![Úspěšně zaregistrované a aktualizované nastavení](./media/ios-28-cp-enroll-1802.png)|Gratulujeme! Právě jste zaregistrovali své zařízení do služby Intune.|

> [!Note]
> K dokončení přípravy zařízení pro správu je potřeba dokončit ještě několik kroků. Přečtěte si další informace o [registraci zařízení s použitím softwaru pro správu telekomunikačních výdajů](enroll-your-device-with-telecom-expense-management-ios.md). Pokud vaše organizace používá program registrace zařízení společnosti Apple, přečtěte si další informace [tady](enroll-your-device-dep-ios.md).

Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu. Kontaktní informace správce najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).  
