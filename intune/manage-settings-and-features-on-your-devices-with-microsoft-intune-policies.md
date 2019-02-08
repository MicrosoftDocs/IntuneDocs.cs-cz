---
title: Zásady zařízení, profily a otázky a odpovědi pro Intune – Azure | Microsoft Docs
description: Přečtěte si informace o různých zásadách a profilech, které můžete využívat v Microsoft Intune, včetně zásad pro konfiguraci zařízení, získání přístupu k firemním prostředkům, povolování podmíněného přístupu a registraci podnikových zařízení. A také získejte odpovědi na nejčastější dotazy.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ROBOTS: ''
ms.reviewer: heenamac
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: e36580a477db29a52249c4ce809239ae3a524462
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55837882"
---
# <a name="manage-settings-and-features-on-your-devices-with-intune-policies"></a>Správa nastavení a funkcí v zařízeních pomocí zásad Intune

*Zásady* služby Microsoft Intune jsou skupiny nastavení, které řídí funkce pro mobilní zařízení a počítače. Zásady můžete vytvořit pomocí šablon, které obsahují doporučené nebo vlastní nastavení. Potom je nasadíte do zařízení nebo skupin uživatelů.

## <a name="types-of-policies"></a>Typy zásad

Zásady Intune spadají do následujících kategorií. Kategorie, kterou použijete, má vliv na způsob vytvoření a nasazení zásady.

- **Zásady konfigurace**: Běžně se používají ke správě nastavení zabezpečení a funkcí v zařízeních, včetně přístupu k prostředkům společnosti. Pokud začínáte, přečtěte si článek o [profilech zařízení v Intune](device-profiles.md).
- **Zásady dodržování předpisů zařízením**: Definujte pravidla a nastavení, která musí zařízení dodržovat, aby bylo považováno za vyhovující zásady podmíněného přístupu. Zásady dodržování předpisů můžete používat i k monitorování a opravám dodržování předpisů u zařízení, a to nezávisle na podmíněném přístupu. Pokud začínáte, přečtěte si článek o [zásadách dodržování předpisů pro zařízení](device-compliance-get-started.md).
- **Zásady podmíněného přístupu**: Pomoct zabezpečit e-mail a další služby, v závislosti na podmínkách, které zadáte. Dobrým zdrojem informací jsou pro začátek články [Co je podmíněný přístup](conditional-access.md) a [Jaké jsou běžné způsoby používání podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md).
- **Zásady registrace podnikových zařízení**: Informace o vytváření zásad registrace podnikových zařízení najdete v tématu [registrace zařízení s Iosem](ios-enroll.md).

## <a name="frequently-asked-questions-about-intune-policies"></a>Nejčastější dotazy týkající se zásad Intune

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-being-deployed"></a>Jak dlouho trvá mobilnímu zařízení, než získá zásadu nebo aplikaci potom, co byly nasazené?
Po nasazení zásady nebo aplikace začne Intune hned upozorňovat zařízení, že se má ohlásit službě Intune. Tento krok obvykle trvá méně než pět minut.

Pokud se zařízení neohlásí po odeslání prvního oznámení, Intune provede tři další pokusy.  Když je zařízení offline (je třeba vypnuté nebo není připojené k síti), nemusí oznámení vůbec dostat. V takovém případě zařízení získá zásadu při dalším plánovaném ohlášení své přítomnosti ve službě Intune:

| Platforma | Četnost ohlašování |
| --- | --- |
| iOS | Každých 6 hodin | 
| Mac OS X | Každých 6 hodin |
| Android | Každých 8 hodin | 
| Windows Phone | Každých 8 hodin | 
| Windows 8.1  | Každých 8 hodin |  
| Počítače s Windows 10 zaregistrované jako zařízení | Každých 8 hodin | 

Pokud se zařízení zaregistrovalo nedávno, četnost ohlašování bude vyšší:

| Platforma | Četnost |
| --- | --- |
| iOS | Prvních 6 hodin každých 15 minut a potom každých 6 hodin |  
| Mac OS X | Prvních 6 hodin každých 15 minut a potom každých 6 hodin | 
| Android | Prvních 15 minut každé 3 minuty, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Windows Phone | Prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin | 
| Počítače s Windows zaregistrované jako zařízení | Prvních 30 minut každé 3 minuty a potom každých 8 hodin | 

Uživatelé můžou taky otevřít aplikaci Portál společnosti a synchronizovat zařízení. Zásady se tak zkontrolují hned.

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Které akce způsobí, že Intune hned pošle oznámení do zařízení?
Zařízení se ohlašují službě Intune, buď když dostanou oznámení, že se mají ohlásit, nebo při pravidelném plánovaném ohlašování.  Když akce, jako je vymazání, zamknutí, resetování hesla, nasazení aplikace, nasazení profilu (WiFi, VPN, e-mail) nebo nasazení zásad, cílí na uživatele nebo zařízení, Intune se hned pokusí zařízení upozornit, že by se mělo ohlásit službě Intune.

Ostatní změny, jako je úprava kontaktních informací na portálu společnosti, nezpůsobí okamžité odeslání oznámení.

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-are-applied"></a>Pokud se pro stejné zařízení nebo uživatele nasadí více zásad, jak poznám, které nastavení se použije?
Pokud se pro stejného uživatele nebo zařízení nasadí dvě nebo víc zásad, k vyhodnocení toho, které nastavení se použije, dochází na úrovni jednotlivých nastavení:

- Nastavení zásad dodržování předpisů mají vždycky přednost před nastaveními zásad konfigurace.

- Nejvíc omezující nastavení zásad dodržování předpisů se použije při vyhodnocení proti stejnému nastavení v jiné zásadě dodržování předpisů.

- Pokud je nastavení zásady konfigurace v konfliktu s nastavením jiné zásady konfigurace, zobrazí se tento konflikt v Intune. Konflikty vyřešte ručně.

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-applies-to-the-app"></a>Co se stane, když jsou zásady správy mobilních aplikací ve vzájemném konfliktu? Která z nich se pro aplikaci použije?
Nejvíce omezující nastavení v zásadách MAM jsou konfliktní hodnoty, s výjimkou polí s počtem zadání (jako jsou pokusy o zadání PINu před resetováním).  Pole s počtem zadání se nastaví na stejnou hodnotu, jako když zásadu MAM vytvoříte v konzole pomocí možnosti doporučeného nastavení.

Konflikt nastane, když je nastavení dvou zásad stejné.  Představte si třeba, že jste nakonfigurovali dvě zásady MAM, které jsou stejné až na nastavení kopírování/vkládání.  V tomto scénáři se nastavení kopírování/vkládání nastaví na nejvíce omezující hodnotu, ale ostatní nastavení se použijí tak, jak se nakonfigurovala.

Pokud se jedna zásada nasadí do aplikace a uplatní se a potom se nasadí druhá zásada, bude mít první zásada přednost a zůstane nasazená. U druhé se zobrazí konflikt. Když se obě nasadí současně (to znamená, že není žádná předchozí zásada), budou v konfliktu obě. Všechna konfliktní nastavení se nastaví na nejvíce omezující hodnoty.

### <a name="what-happens-when-ios-custom-policies-conflict"></a>Co se stane při konfliktu vlastních zásad iOS?
Intune nevyhodnocuje datovou část konfiguračních souborů Apple nebo vlastní zásady OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Slouží jenom jako mechanismus doručování.

Když nasadíte vlastní zásadu, ověřte, že nakonfigurované nastavení není v konfliktu se zásadami dodržování předpisů, konfiguračními zásadami nebo jinými vlastními zásadami. Při konfliktu mezi nastavením a vlastní zásadou je pořadí použití nastavení náhodné.

### <a name="what-happens-when-a-policy-is-deleted-or-no-longer-applicable"></a>Co se stane, když se zásada odstraní nebo už není platná?
Pokud odstraníte zásadu nebo odeberete zařízení ze skupiny s nasazenou zásadou, tato zásada a nastavení se ze zařízení odeberou podle následujících seznamů.

#### <a name="enrolled-devices"></a>Registrovaná zařízení

- Wi-Fi, VPN, certifikátu a e-mailové profily: Tyto profily se odeberou ze všech podporovaných registrovaných zařízení.
- Všechny ostatní typy zásad:
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

### <a name="where-can-i-find-help-troubleshooting-policies"></a>Kde najdu nápovědu k odstraňování potíží se zásadami?

Přečtěte si článek o [řešení problémů se zásadami](troubleshoot-policies-in-microsoft-intune.md).
