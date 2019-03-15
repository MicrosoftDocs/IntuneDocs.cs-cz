---
title: Řešení potíží s profily zařízení v Microsoft Intune – Azure | Microsoft Docs
description: Běžné otázky a odpovědi s zařízení zásady a profily, včetně změny profilu, neuplatňují na uživatele nebo zařízení, jak dlouho trvá, nové zásady doručí do zařízení, která nastavení se použijí, pokud existuje více zásad, co se stane, když profil je odstraněna nebo odebrána a více s Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 12ac2b93126f271bf4918c6a914dedc7a22c1010
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57461001"
---
# <a name="common-questions-issues-and-resolutions-with-device-policies-and-profiles-in-microsoft-intune"></a>Běžné dotazy, problémy a řešení u profilů v Microsoft Intune a zásad zařízení

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Získejte odpovědi na běžné otázky při práci s profily zařízení a zásad v Intune. Tento článek také seznamy vrácení se změnami časové intervaly, poskytuje více detains na konflikty a další.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Proč uživatel nezíská nový profil, když změníte heslo u existujícího profilu Wi-Fi?

Vytvoříte profil podnikové sítě Wi-Fi, nasadíte profil u skupiny, změníte heslo a profil uložíte. Když se profil změní, nemusí někteří uživatelé nový profil obdržet.

Abyste zmírnili následky tohoto problému, nastavte Wi-Fi pro hosty. Když selže podniková síť Wi-Fi, můžou se uživatelé připojit k Wi-Fi pro hosty. Je nutné povolit veškerá nastavení automatického připojení. Nasaďte profil sítě Wi-Fi pro hosty všem uživatelům.

Další doporučení:  

- Pokud síť Wi-Fi, ke kterému se připojujete, používá heslo nebo přístupové heslo, ujistěte se, že se že přímo připojit ke směrovači sítě Wi-Fi. Můžete to vyzkoušet na zařízení s iOSem.
- Až se úspěšně připojíte ke koncovému bodu sítě Wi-Fi (směrovači sítě Wi-Fi), zapište si identifikátor SSID a použité přihlašovací údaje (heslo).
- Zadejte identifikátor SSID a přihlašovací údaje (heslo) do pole Předsdílený klíč. 
- Nasaďte profil u testovací skupiny, která má omezený počet uživatelů, nejlépe jenom u IT týmu. 
- Synchronizujte vaše zařízení s iOSem do Intune. Zaregistrujte se (pokud jste to ještě neudělali). 
- Vyzkoušejte připojení ke stejnému koncovému bodu sítě Wi-Fi (jak je uvedeno v prvním kroku).
- Zaveďte profil u větších skupin a nakonec u všech předpokládaných uživatelů ve vaší organizaci. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Jak dlouho trvá mobilnímu zařízení, než získá zásady nebo aplikace potom, co byly přiřazené?

Po přiřazení zásady nebo aplikace začne Intune hned upozorňovat zařízení, že se má ohlásit službě Intune. Trvá to obvykle méně než pět minut.

Pokud se zařízení neohlásí po prvním oznámení získá zásady, Intune provede tři další pokusy. Offline zařízení, třeba vypnuté nebo není připojené k síti, nemusí oznámení vůbec dostat. V takovém případě zařízení získá zásadu při další naplánované ohlášení své přítomnosti ve službě Intune, která je:

| Platforma | Aktualizovat cyklu|
| --- | --- |
| iOS | Každých 6 hodin |
| macOS | Každých 6 hodin |
| Android | Každých 8 hodin |
| Počítače s Windows 10 zaregistrované jako zařízení | Každých 8 hodin |
| Windows Phone | Každých 8 hodin |
| Windows 8.1 | Každých 8 hodin |

Pokud zařízení zaregistrovalo nedávno, vrácení se změnami se spustí častěji:

| Platforma | Četnost |
| --- | --- |
| iOS | Prvních 6 hodin každých 15 minut a potom každých 6 hodin |  
| Mac OS X | Prvních 6 hodin každých 15 minut a potom každých 6 hodin | 
| Android | Prvních 15 minut každé 3 minuty, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Windows Phone | Prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Počítače s Windows zaregistrované jako zařízení | Prvních 30 minut každé 3 minuty a potom každých 8 hodin | 

Kdykoli můžete uživatelům otevřete aplikaci portál společnosti a synchronizovat zařízení okamžitě zkontroloval aktualizace profilu.

Pro zařízení bez přidružení uživatele frekvence synchronizace hned po registraci může lišit od hodin za den nebo více. Intune odesílá požadavky v různých intervalech zařízení k Intune. Je však stále až do zařízení se změnami. Po počáteční registraci je čas potřebný k dokončení vrácení se změnami zařízení nepředvídatelné. Také závisí na typu registrace zařízení, zásad a profilů přiřazených k zařízení. Po jeho registraci, a všech počátečních zásad zařízení obvykle zjišťuje nové zásady každých 6 až 8 hodin.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Které akce způsobí, že Intune hned pošle oznámení do zařízení?

Zařízení se ohlašují Intune když dostanou oznámení, chcete-li zkontrolovat, nebo při naplánované vrácení se změnami. Při cílení na uživatele s akcí, jako je například uzamčení, resetování hesla, přiřazení aplikace, přiřazení profilu nebo zásad, nebo zařízení, upozorní hned Intune zařízení k vrácení se změnami a získat tyto aktualizace.

Ostatní změny, jako je úprava kontaktních informací na portálu společnosti, nezpůsobí okamžité odeslání oznámení.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-gets-applied"></a>Pokud se stejnému zařízení nebo uživateli přiřadí několik zásad, jak poznám, které nastavení se použije?

Pokud pro stejného uživatele nebo zařízení přiřadí dvě nebo více zásad, nastavení, která se použije dochází na úrovni jednotlivých nastavení:

- Nastavení zásad dodržování předpisů mají vždycky přednost před nastavení profilu konfigurace.

- Zásady dodržování předpisů vyhodnotí proti stejnému nastavení v jiné zásadě dodržování předpisů, pak platí nejvíc omezující nastavení zásad dodržování předpisů.

- Pokud je nastavení je v konfliktu s nastavením jiné zásady Konfigurace zásady konfigurace, zobrazí se tento konflikt v Intune. Konflikty vyřešte ručně.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-is-applied-to-the-app"></a>Co se stane, když zásady ochrany aplikací navzájem kolidují? Která se použije pro příslušnou aplikaci?

Nejvíc omezující nastavení v zásady ochrany aplikací jsou konfliktní hodnoty *s výjimkou* pro pole s počtem zadání, jako je například pokusů o zadání PIN kódu před resetováním. Pole s počtem zadání se nastaví na stejnou hodnotu, jako když vytvoříte zásady MAM pomocí možnosti doporučeného nastavení.

Konflikty dojít, když je nastavení dvou profilů stejné. Představte si třeba, že jste nakonfigurovali dvě zásady MAM, které jsou stejné až na nastavení kopírování/vkládání. V tomto scénáři se nastavení kopírování/vkládání nastaví na nejvíce omezující hodnotu, ale ostatní nastavení se použijí tak, jak se nakonfigurovala.

Zásady se nasadí do aplikace a uplatní. Nasazuje se druhá zásada. V tomto scénáři první zásada přednost a bude se dál používat. Druhá zásada se zobrazí konflikt. Pokud jsou obě nasadí současně, což znamená, že se předchozí zásada, pak obě jsou v konfliktu. Všechna konfliktní nastavení se nastaví na nejvíce omezující hodnoty.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Co se stane při konfliktu vlastních zásad iOS?

Intune nevyhodnocuje datovou část konfiguračních souborů Apple nebo vlastní zásady OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Slouží jenom jako mechanismus doručování.

Když přiřazujete vlastní zásady, potvrďte, že nakonfigurované nastavení není v konfliktu se dodržování předpisů, konfiguračními zásadami nebo jinými vlastními zásadami. V případě konfliktu vlastních zásad a nastavení se náhodně použijí nastavení.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Co se stane, když se profil odstraní nebo už není použitelný?

Pokud odstraníte profil nebo odeberete zařízení ze skupiny, který se má profil, profil a nastavení se ze zařízení odeberou podle popisu:

- Wi-Fi, VPN, certifikátu a e-mailové profily: Tyto profily se odeberou ze všech podporovaných registrovaných zařízení.
- Všechny ostatní typy profilů:  

  - **Windows a androidem**: Nastavení se ze zařízení neodeberou.
  - **Zařízení s Windows Phone 8.1**: Následující nastavení jsou odebraná:  
  
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

  - **iOS**: Odeberou se všechna nastavení, s výjimkou:
  
    - Povolit hlasový roaming
    - Povolit datový roaming
    - Povolit automatickou synchronizaci při roamingu

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Změnil(a) jsem profil omezení zařízení, ale tyto změny se neprojevily

Po nastavení zařízení Windows Phone neumožňují zmírnění zásad zabezpečení nastavených s použitím MDM nebo EAS snížení zabezpečení. Například můžete nastavit **minimální počet znaků hesla** na 8. Pokusíte snížit na 4. Do zařízení se už používá více omezující profil.

Chcete profil změnit na méně zabezpečenou hodnotu, a resetovat zásady zabezpečení. Například ve Windows 8.1, na ploše prstem zprava > vyberte **nastavení** > **ovládací panely**. Vyberte aplet **Uživatelské účty** . V levé navigační nabídce je **resetovat zásady zabezpečení** odkaz (dole). Vyberte ho a potom zvolte **Resetovat zásady**.

Jiná zařízení MDM, jako je například Android, Windows Phone 8.1 a novější, iOS a Windows 10 může třeba být vyřadit a znovu zaregistrovat v Intune použít méně omezující profil.

## <a name="some-settings-in-a-windows-10-profile-return-not-applicable"></a>Některá nastavení v profilu Windows 10 vrátit "Není k dispozici"

Některá nastavení v zařízení s Windows 10 se můžou zobrazovat jako "Není k dispozici". Pokud k tomu dojde, že konkrétní nastavení nepodporuje verzi nebo edici Windows spuštěného v příslušném zařízení. Tato zpráva může dojít z následujících důvodů:

- Nastavení dostupná jenom pro novější verze systému Windows a ne aktuální verzi operačního systému (OS) na zařízení.
- Nastavení dostupná jenom pro konkrétní edice Windows, nebo jen některé, například Home, Professional, Enterprise a Education.

Další informace o verzi a požadavky na SKU pro různá nastavení, najdete v článku [poskytovatele konfiguračních služeb (CSP) odkaz](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference).

## <a name="next-steps"></a>Další postup

Potřebujete další pomoc? Přečtěte si téma [Jak získat podporu pro Microsoft Intune](get-support.md).
