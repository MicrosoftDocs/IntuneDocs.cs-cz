---
title: Řešení potíží s profily zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Obvyklé problémy s profily zařízení, včetně situací, kdy se nepoužijí změny profilu u některých uživatelů nebo zařízení, jak dlouho to trvá, než se nová zásada doručí do zařízení, která nastavení se použijí, pokud existuje více zásad, co se stane po odstranění nebo odebrání profilu a další informace k Microsoft InTune na portálu Azure Portal
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 1/17/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d013ad2aefbfee5eea8f240277b0f84c2c6bf05a
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2018
ms.locfileid: "43312945"
---
# <a name="common-issues-and-resolutions-with-device-profiles-in-microsoft-intune"></a>Běžné problémy a řešení u profilů zařízení v Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Řešte běžné problémy s použitím profilů zařízení Intune.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Proč uživatel nezíská nový profil, když změníte heslo u existujícího profilu Wi-Fi? 
Vytvoříte profil podnikové sítě Wi-Fi, nasadíte profil u skupiny, změníte heslo a profil uložíte. Když se profil změní, nemusí někteří uživatelé nový profil obdržet.

Abyste zmírnili následky tohoto problému, nastavte Wi-Fi pro hosty. Když selže podniková síť Wi-Fi, můžou se uživatelé připojit k Wi-Fi pro hosty. Je nutné povolit veškerá nastavení automatického připojení. Nasaďte profil sítě Wi-Fi pro hosty všem uživatelům.

Další doporučení:  

- Protože síť Wi-Fi, ke které se připojujete, používá heslo, je potřeba mít možnost se připojit přímo ke směrovači sítě Wi-Fi. Můžete to vyzkoušet na zařízení s iOSem.
- Až se úspěšně připojíte ke koncovému bodu sítě Wi-Fi (směrovači sítě Wi-Fi), zapište si identifikátor SSID a použité přihlašovací údaje (heslo).
- Zadejte identifikátor SSID a přihlašovací údaje (heslo) do pole Předsdílený klíč. 
- Nasaďte profil u testovací skupiny, která má omezený počet uživatelů, nejlépe jenom u IT týmu. 
- Synchronizujte vaše zařízení s iOSem do Intune. Zaregistrujte se (pokud jste to ještě neudělali). 
- Vyzkoušejte připojení ke stejnému koncovému bodu sítě Wi-Fi (jak je uvedeno v prvním kroku).
- Zaveďte profil u větších skupin a nakonec u všech předpokládaných uživatelů ve vaší organizaci. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Jak dlouho trvá mobilnímu zařízení, než získá zásady nebo aplikace potom, co byly přiřazené?
Po přiřazení zásady nebo aplikace začne Intune hned upozorňovat zařízení, že se má ohlásit službě Intune. Trvá to obvykle méně než pět minut.

Pokud se zařízení neohlásí po odeslání prvního oznámení, Intune provede tři další pokusy. Když je zařízení offline (je třeba vypnuté nebo není připojené k síti), nemusí oznámení vůbec dostat. V takovém případě zařízení získá zásadu při dalším plánovaném ohlášení své přítomnosti ve službě Intune:

- iOS a macOS: Každých 6 hodin
- Android: Každých 8 hodin
- Windows Phone: Každých 8 hodin
- Počítače s Windows 8.1 a Windows 10 zaregistrované jako zařízení: Každých 8 hodin

Pokud se zařízení zaregistrovalo nedávno, četnost ohlašování bude vyšší:

- iOS a macOS: Prvních 6 hodin každých 15 minut a potom každých 6 hodin
- Android: Prvních 15 minut každé 3 minuty, další 2 hodiny každých 15 minut a potom každých 8 hodin
- Windows Phone: Prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin
- Počítače s Windows zaregistrované jako zařízení: Prvních 30 minut každé 3 minuty a potom každých 8 hodin

Pokud chtějí uživatelé zkontrolovat zásady hned, můžou otevřít aplikaci Portál společnosti a synchronizovat zařízení.

U zařízení bez přidružení uživatele se frekvence synchronizace hned po registraci může lišit v rozpětí od několika hodin až po jeden den nebo více. Intune v různých intervalech odesílá žádosti, aby se zařízení službě ohlásilo. Záleží ale na příslušném zařízení, jestli to skutečně udělá. Po počáteční registraci zařízení se nedá podle typu registrace a zásad a profilů přiřazených k zařízení předpovědět, jak dlouho bude trvat, než se dané zařízení ohlásí. Po registraci zařízení a použití všech počátečních zásad zařízení obvykle zjišťuje nové zásady přibližně každých 6 hodin.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Které akce způsobí, že Intune hned pošle oznámení do zařízení?
Zařízení se ohlašují službě Intune, buď když dostanou oznámení, že se mají ohlásit, nebo při pravidelném plánovaném ohlašování. Když zacílíte akci, jako je vymazání, zamknutí, resetování hesla, přiřazení aplikace, přiřazení profilu nebo přiřazení zásad, na uživatele nebo zařízení, upozorní hned Intune zařízení, že by se mělo ohlásit službě Intune, aby získalo aktualizace.

Ostatní změny, jako je třeba úprava kontaktních informací na portálu společnosti, nezpůsobí okamžité odeslání oznámení.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Pokud se stejnému zařízení nebo uživateli přiřadí několik zásad, jak poznám, které nastavení se použije?
Pokud se stejnému uživateli nebo zařízení přiřadí dvě nebo více zásad, závisí použití nastavení na úrovni jednotlivých nastavení:

-   Nastavení zásad dodržování předpisů mají vždycky přednost před nastaveními zásad konfigurace.

-   Pokud se zásady hodnotí podle stejného nastavení v jiné zásadě dodržování předpisů, použije se nejrestriktivnější nastavení dodržování zásad.

-   Pokud je nastavení zásady konfigurace v konfliktu s nastavením jiné zásady konfigurace, zobrazí se tento konflikt na portálu Azure Portal. V tomto scénáři tyto konflikty vyřešte ručně.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Co se stane, když zásady ochrany aplikací navzájem kolidují? Která se použije pro příslušnou aplikaci?
Nejvíce omezující nastavení dostupná v zásadách ochrany aplikací jsou konfliktní hodnoty s výjimkou polí pro zadání čísel (jako je zadání PIN kódu před resetováním). Pole s počtem zadání se nastaví na stejnou hodnotu, jako když zásadu MAM vytvoříte v konzole pomocí možnosti doporučeného nastavení.

Konflikt nastane, když je nastavení dvou profilů stejné. Představte si třeba, že jste nakonfigurovali dvě zásady MAM, které jsou stejné až na nastavení kopírování/vkládání. V tomto scénáři se nastavení kopírování/vkládání nastaví na nejvíce omezující hodnotu, ale ostatní nastavení se použijí tak, jak se nakonfigurovala.

Pokud se jeden profil přiřadí aplikaci a uplatní se a pak se přiřadí druhý profil, bude mít první profil přednost a bude se dál používat, zatímco u druhého se zobrazí konflikt. Když se uplatní oba současně, což znamená, že neexistuje žádný předchozí profil, budou v konfliktu oba. Všechna konfliktní nastavení se nastaví na nejvíce omezující hodnoty.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Co se stane při konfliktu vlastních zásad iOS?
Intune nevyhodnocuje datovou část konfiguračních souborů Apple ani vlastní profil OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Slouží jenom jako mechanismus doručování.

Při přiřazování vlastního profilu zkontrolujte, jestli nakonfigurované nastavení není v konfliktu se zásadami dodržování předpisů, konfiguračními zásadami nebo jinými vlastními zásadami. Pokud dojde ke konfliktu mezi vlastním profilem a jeho nastavením, použije se nastavení náhodně.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Co se stane, když se profil odstraní nebo už není použitelný?
Pokud odstraníte profil nebo odeberete zařízení ze skupiny, která má tento profil, odebere se tento profil a nastavení ze zařízení podle následujících seznamů:

- Profily sítě Wi-Fi, VPN, certifikátu a e-mailu: Tyto profily se odeberou ze všech podporovaných registrovaných zařízení.
- Všechny ostatní typy profilů:  
    - **Zařízení s Windows a Androidem**: Nastavení se ze zařízení neodeberou.
    - **Zařízení Windows Phone 8.1**: Odeberou se tato nastavení:  
        - Vyžadovat heslo k odemknutí mobilních zařízení
        - Povolit jednoduchá hesla
        - Minimální délka hesla
        - Vyžadovaný typ hesla
        - Vypršení platnosti hesla (dny)
        - Pamatovat si historii hesel
        - Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno
        - Počet minut nečinnosti před vyžadováním hesla
        - Typ požadovaného hesla – minimální počet znaků
        - Povolit fotoaparát
        - Vyžadovat šifrování u mobilního zařízení
        - Povolit vyměnitelné úložiště
        - Povolit webový prohlížeč
        - Povolit obchod s aplikacemi
        - Povolit snímek obrazovky
        - Povolit zeměpisnou polohu
        - Povolit účet Microsoft
        - Povolit kopírování a vkládání
        - Povolit sdílení internetového připojení přes Wi-Fi
        - Povolit automatické připojení k bezplatným Wi-Fi hotspotům
        - Povolit oznamování Wi-Fi hotspotů
        - Povolit vymazání
        - Povolit Bluetooth
        - Povolit komunikaci NFC
        - Povolit Wi-Fi

    - **iOS**: Odeberou se všechna nastavení s těmito výjimkami:
        - Povolit hlasový roaming
        - Povolit datový roaming
        - Povolit automatickou synchronizaci při roamingu

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Změnil(a) jsem profil omezení zařízení, ale tyto změny se neprojevily
Zařízení Windows Phone neumožňují zmírnění zásad zabezpečení nastavených s použitím MDM nebo EAS, když je jednou nastavíte. Nastavíte třeba **Minimální počet znaků hesla** na hodnotu 8, kterou se pak pokusíte snížit na 4. V zařízení se už používá více omezující profil.

Pokud chcete profil změnit na méně zabezpečenou hodnotu, resetujte v závislosti na platformě zařízení zásady zabezpečení. Třeba v systému Windows potáhněte na ploše prstem zprava a vyberte **Nastavení** > **Ovládací panely**. Vyberte aplet **Uživatelské účty** .

V navigační nabídce vlevo najdete (dole) odkaz **Resetovat zásady zabezpečení**. Vyberte ho a potom zvolte **Resetovat zásady**. Jiná zařízení MDM, například zařízení se systémy Android, Windows Phone 8.1 (a novějšími) a iOS, může být potřeba vyřadit a potom do služby znovu zaregistrovat, aby se dal použít méně omezující profil.

## <a name="next-steps"></a>Další kroky
Potřebujete další pomoc? Přečtěte si téma [Jak získat podporu pro Microsoft Intune](get-support.md).