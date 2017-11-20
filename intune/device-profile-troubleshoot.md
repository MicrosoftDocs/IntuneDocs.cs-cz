---
title: "Řešení potíží s profily zařízení v Microsoft Intune"
titlesuffix: Azure portal
description: "Pokud nevíte, jak dál, přečtěte si toto téma, které vám pomůže vyřešit problémy s profily zařízení v Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ff950ce35c491ca576dc9cc77ab561e2cfef0381
ms.sourcegitcommit: 1df625330f4e8f7f661b5f2b9f16b5590971838d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/10/2017
---
# <a name="troubleshooting-device-profiles-in-microsoft-intune"></a>Řešení potíží s profily zařízení v Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Informace v tomto tématu vám mohou pomoct vyřešit běžné problémy s profily zařízení v Intune.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Proč uživatel nezíská nový profil, když změníte heslo u existujícího profilu Wi-Fi? 
Když vytvoříte profil podnikové sítě Wi-Fi, nasadíte profil u skupiny, změníte heslo a uložíte profil, můžete očekávat, že uživatel získá nový profil. Uživatel ale nemusí nový profil získat. 

Jestli chcete tento problém zmírnit, vytvořte síť Wi-Fi pro hosty, ke které se uživatel uchýlí, pokud podniková síť Wi-Fi selže. Musí být povolená nastavení pro automatické připojení. Tento profil sítě Wi-Fi pro hosty musí být nasazený u všech uživatelů.

Existují některé další osvědčené postupy, kterými se můžete řídit:
- Protože síť Wi-Fi, ke které se připojujete, vyžaduje heslo, zajistěte, abyste se mohli připojit přímo ke směrovači sítě Wi-Fi. Můžete to vyzkoušet na zařízení s iOSem.
- Až se úspěšně připojíte ke koncovému bodu sítě Wi-Fi (směrovači sítě Wi-Fi), zapište si identifikátor SSID a použité přihlašovací údaje (heslo).
- Zadejte identifikátor SSID a přihlašovací údaje (heslo) do pole Předsdílený klíč. 
- Nasaďte profil u testovací skupiny, která má omezený počet uživatelů, nejlépe jenom u IT týmu. 
- Synchronizujte vaše zařízení s iOSem do Intune. Zaregistrujte se (pokud jste to ještě neudělali). 
- Vyzkoušejte připojení ke stejnému koncovému bodu sítě Wi-Fi (jak je uvedeno v prvním kroku).
- Zaveďte profil u větších skupin a nakonec u všech předpokládaných uživatelů ve vaší organizaci. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Jak dlouho trvá mobilnímu zařízení, než získá zásady nebo aplikace potom, co byly přiřazené?
Po přiřazení zásady nebo aplikace se Intune hned začne pokoušet upozornit zařízení, že se mělo ohlásit službě Intune. To obvykle trvá méně než pět minut.

Pokud se zařízení neohlásí po odeslání prvního oznámení, Intune provede tři další pokusy.  Když je zařízení offline (je třeba vypnuté nebo není připojené k síti), nemusí oznámení vůbec dostat. V takovém případě zařízení získá zásadu při dalším plánovaném ohlášení své přítomnosti ve službě Intune:

- iOS a macOS: Každých 6 hodin
- Android: Každých 8 hodin.
- Windows Phone: Každých 8 hodin.
- Počítače s Windows 8.1 a Windows 10 zaregistrované jako zařízení: Každých 8 hodin.

Pokud se zařízení právě zaregistrovalo, četnost ohlašování bude vyšší:

- iOS a macOS: Prvních 6 hodin každých 15 minut a potom každých 6 hodin
- Android: Prvních 15 minut každé 3 minuty, další 2 hodiny každých 15 minut a potom každých 8 hodin.
- Windows Phone: Prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin.
- Počítače s Windows zaregistrované jako zařízení: Prvních 30 minut každé 3 minuty a potom každých 8 hodin.

Uživatelé můžou taky otevřít aplikaci Portál společnosti a synchronizovat zařízení. Zásady se tak zkontrolují hned.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Které akce způsobí, že Intune hned pošle oznámení do zařízení?
Zařízení se ohlašují službě Intune, buď když dostanou oznámení, že se mají ohlásit, nebo při pravidelném plánovaném ohlašování.  Když akce, jako je vymazání, zamknutí, resetování hesla, přiřazení aplikace, přiřazení profilu (WiFi, VPN, e-mailu atd.), nebo přiřazení zásad cílí na konkrétního uživatele nebo zařízení, Intune se hned pokusí zařízení upozornit, že by se mělo ohlásit službě Intune a získat tyto aktualizace.

Ostatní změny, jako je třeba úprava kontaktních informací na portálu společnosti, nezpůsobí okamžité odeslání oznámení.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a>Pokud se stejnému zařízení nebo uživateli přiřadí několik zásad, jak poznám, které nastavení se použije?
Pokud se stejnému uživateli nebo zařízení přiřadí dvě nebo více zásad, dochází k vyhodnocení toho, které nastavení se použije, na úrovni jednotlivých nastavení:

-   Nastavení zásad dodržování předpisů mají vždycky přednost před nastaveními zásad konfigurace.

-   Nejvíc omezující nastavení zásad dodržování předpisů se použije při vyhodnocení proti stejnému nastavení v jiné zásadě dodržování předpisů.

-   Pokud je nastavení zásady konfigurace v konfliktu s nastavením jiné zásady konfigurace, zobrazí se tento konflikt na portálu Azure Portal. Takové konflikty je třeba vyřešit ručně.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a>Co se stane, když zásady ochrany aplikací navzájem kolidují? Která se použije pro příslušnou aplikaci?
Nejvíce omezující nastavení dostupná v zásadách ochrany aplikací jsou konfliktní hodnoty s výjimkou polí pro zadání čísel (jako je zadání PIN kódu před resetováním).  Pole pro zadání čísel se nastaví na stejnou hodnotu, jako kdybyste zásadu MAM vytvořili v konzole pomocí možnosti doporučeného nastavení.

Konflikt nastane, když je nastavení dvou profilů stejné.  Představte si třeba, že jste nakonfigurovali dvě zásady MAM, které jsou stejné až na nastavení kopírování/vkládání.  V tomto scénáři se nastavení kopírování/vkládání nastaví na nejvíc omezující hodnotu, ale ostatní nastavení se použijí tak, jak se nakonfigurovala.

Pokud se jeden profil přiřadí aplikaci a uplatní se a pak se přiřadí druhý profil, bude mít první profil přednost a zůstane uplatněný, zatímco u druhého se zobrazí konflikt. Když se uplatní oba současně, což znamená, že neexistuje žádný předchozí profil, budou v konfliktu oba. Všechna konfliktní nastavení se nastaví na nejvíc omezující hodnoty.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Co se stane při konfliktu vlastních zásad iOS?
Intune nevyhodnocuje datovou část konfiguračních souborů Apple ani vlastní profil OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Slouží jenom jako mechanismus doručování.

Při přiřazování vlastního profilu zkontrolujte, jestli nakonfigurované nastavení není v konfliktu se zásadami dodržování předpisů, konfiguračními zásadami nebo jinými vlastními zásadami. Při konfliktu mezi vlastním profilem a nastavením je pořadí, ve kterém se nastavení uplatní, náhodné.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Co se stane, když se profil odstraní nebo už není použitelný?
Pokud odstraníte profil nebo odeberete zařízení ze skupiny, ke které byl profil přiřazený, profil a nastavení se ze zařízení odeberou podle následujících seznamů.

### <a name="enrolled-devices"></a>Registrovaná zařízení

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
        - Povolit obnovení továrního nastavení
        - Povolit Bluetooth
        - Povolit komunikaci NFC
        - Povolit Wi-Fi

    - **iOS**: Odeberou se všechna nastavení s těmito výjimkami:
        - Povolit hlasový roaming
        - Povolit datový roaming
        - Povolit automatickou synchronizaci při roamingu

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Změnil(a) jsem profil omezení zařízení, ale tyto změny se neprojevily
Zařízení s Windows Phone neumožňují zmírnění zásad zabezpečení nastavených přes MDM nebo EAS potom, co je nastavíte. Nastavíte třeba **Minimální počet znaků hesla** na hodnotu 8 a tu se pak pokusíte snížit na 4. V zařízení se už používá více omezující profil.

Pokud chcete profil změnit na méně zabezpečenou hodnotu, v závislosti na platformě zařízení může být potřeba resetovat zásady zabezpečení.
Například ve Windows otevřete potáhnutím prstu z pravého okraje plochy panel **ovládacích tlačítek** a zvolte **Nastavení** &gt; **Ovládací panely**.  Vyberte aplet **Uživatelské účty** .
V navigační nabídce vlevo najdete dole odkaz **Resetovat zásady zabezpečení** . Zvolte jej a potom zvolte tlačítko **Resetovat zásady** .
Jiná zařízení MDM, například zařízení se systémy Android, Windows Phone 8.1 (a novějšími) a iOS, může být potřeba vyřadit a znovu zaregistrovat do služby, abyste mohli použít méně omezující profil.


### <a name="next-steps"></a>Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](get-support.md).