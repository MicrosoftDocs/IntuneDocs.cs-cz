---
title: "Správa nastavení zařízení pomocí zásad | Dokumentace Microsoftu"
description: "Pomocí Intune můžete vytvořit a nasadit zásady, které řídí nastavení a funkce na zaregistrovaných zařízeních, která spravujete."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: f153e3a58f9655bd1e36094f292098c9f55742b6
ms.lasthandoff: 12/10/2016


---

# <a name="manage-settings-and-features-on-your-devices-with-microsoft-intune-policies"></a>Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

*Zásady* služby Microsoft Intune jsou skupiny nastavení, které řídí funkce pro mobilní zařízení a počítače. Zásady můžete vytvořit pomocí šablon, které obsahují doporučená nebo přizpůsobená nastavení, a potom je můžete nasadit pro skupiny zařízení nebo uživatelů.

## <a name="types-of-policies"></a>Typy zásad

Zásady Intune spadají do následujících kategorií. Kategorie, kterou použijete, má vliv na způsob vytvoření a nasazení zásady.


- **Zásady konfigurace:** Běžně se používají ke správě nastavení a funkcí zabezpečení na vašich zařízeních. Z tohoto tématu se dozvíte, jak tyto zásady vytvořit a nasadit, a dozvíte se o dostupných nastaveních.
- **Zásady dodržování předpisů zařízení:** Tyto zásady určují pravidla a nastavení, které musí zařízení dodržovat, aby se dalo považovat za zařízení, které dodržuje zásady podmíněného přístupu. Zásady dodržování předpisů můžete používat i k monitorování a opravám dodržování předpisů u zařízení, a to nezávisle na podmíněném přístupu.
Podrobnosti najdete v tématu [Zásady dodržování předpisů u zařízení v Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- **Zásady podmíněného přístupu:** Tyto zásady pomáhají zabezpečit e-mail a další služby v závislosti na zadaných podmínkách.
Podrobnosti najdete v tématu [Omezení přístupu k e-mailu a službám O365 pomocí Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).
- **Zásady registrace podnikových zařízení:** Informace o vytváření zásad registrace podnikových zařízení najdete v tématu [Nastavení správy pro iOS a Mac pomocí Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md).
- **Zásady přístupu k prostředkům:** Tyto zásady společně pomáhají uživatelům zajistit odkudkoli přístup k souborům a prostředkům, které potřebují ke své práci.
Podrobnosti najdete v tématu [Povolení přístupu k prostředkům společnosti pomocí Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md).

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Úplný seznam zásad služby Intune najdete v tématu [Odkazy na zásady služby Microsoft Intune](microsoft-intune-policy-reference.md).

## <a name="create-a-configuration-policy"></a>Vytvoření zásady konfigurace

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) vyberte **Zásady** &gt; **Zásady konfigurace** &gt; **Přidat**.

2.  Zvolte požadovanou zásadu a vyberte doporučené nastavení pro tuto zásadu (pokud je dostupné; toto nastavení pak můžete později změnit), nebo zvolte možnost vytvořit vlastní zásadu s vlastním nastavením.

    > [!TIP]
    > Pokud potřebujete pomoc s výběrem správné zásady, projděte si téma [Referenční informace o zásadách Intune](microsoft-intune-policy-reference.md).

3.  Až budete připravení, vyberte **Vytvořit zásadu**.

4.  Na stránce **Vytvořit zásadu** nakonfigurujte název a volitelný popis zásady.

5.  Nakonfigurujte požadovaná nastavení a potom vyberte **Uložit zásadu**.

    Pokud potřebujete pomoc s nastavením zásad, vyberte v následujícím seznamu typ své zásady:

    - [Nastavení pro zařízení s iOSem](ios-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zařízení s Androidem](android-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zařízení s Androidem for Work](android-for-work-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zařízení s Windows 8 a Windows 8.1](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zařízení Windows Phone 8.1](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro počítače a mobilní zařízení s Windows 10](windows-10-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zařízení s Windows Team](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro upgrade edice systému Windows](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zařízení s Mac OS X](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro Exchange ActiveSync](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zásady podmínek a ujednání](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Obecné nastavení pro mobilní zařízení (zastaralé)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  Výběrem možnosti **Ano** v potvrzovacím dialogu zásadu hned nasadíte, výběrem možnosti **Ne** zásadu vytvoříte, ale nenasadíte ji.

Novou zásadu můžete zobrazit a upravit tak, že si projdete oddíly pro jednotlivé typy zásad v pracovním prostoru **Zásady**.

Když vytvoříte zásadu, která používá doporučená nastavení, je název nové zásady kombinací názvu šablony, data a času. Když zásadu upravujete, název se aktualizuje pomocí data a času úpravy.

Zásadu po vytvoření obvykle chcete nasadit pro jednu nebo několik skupin uživatelů nebo zařízení.

> [!TIP]
> Nenasazujete všechny typy zásad. Třeba zásada správy mobilních aplikací se nenasazuje. Tento typ zásad se místo toho přidruží aplikaci a teprve ta se pak nasadí.

## <a name="deploy-a-configuration-policy"></a>Nasazení zásady konfigurace

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a potom vyberte **Spravovat nasazení**.

2.  V dialogovém okně **Spravovat nasazení** :

    -   Pokud chcete zásadu nasadit, vyberte jednu nebo několik skupin, do kterých chcete zásady nasadit, a potom vyberte **Přidat** &gt; **OK**.

    -   Pokud chcete dialogové okno zavřít bez nasazení zásady, zvolte **Zrušit**.

Když vyberete nasazenou zásadu, zobrazí se v dolní části seznamu zásad další informace o tomto nasazení.

## <a name="manage-policies"></a>Správa zásad

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) vyberte **Zásady**, vyhledejte zásadu, kterou chcete spravovat, a vyberte ji.

2.  Vyberte jednu z následujících akcí:

- **Upravit**: Otevře vlastnosti vybrané zásady a umožní vám provádět změny.
- **Odstranit**: Odstraní vybranou zásadu.<br>Pokud zásadu odstraníte, odebere se ze všech skupin, ve kterých byla nasazená.
- **Spravovat nasazení**: Vyberte skupinu, do které chcete zásadu nasadit, a potom vyberte **Přidat**.


## <a name="frequently-asked-questions-about-intune-policies"></a>Nejčastější dotazy týkající se zásad Intune

### <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-deployed"></a>Jak dlouho trvá mobilnímu zařízení, než získá zásadu nebo aplikaci potom, co byly nasazené?
Po nasazení zásady nebo aplikace se Intune hned začne pokoušet upozornit zařízení, že se mělo ohlásit službě Intune. To obvykle trvá méně než pět minut.

Pokud se zařízení neohlásí po odeslání prvního oznámení, Intune provede tři další pokusy.  Když je zařízení offline (je třeba vypnuté nebo není připojené k síti), nemusí oznámení vůbec dostat. V takovém případě zařízení získá zásadu při dalším plánovaném ohlášení své přítomnosti ve službě Intune:

- iOS a Mac OS X: Každých 6 hodin.
- Android: Každých 8 hodin.
- Windows Phone: Každých 8 hodin.
- Počítače s Windows 8.1 a Windows 10 zaregistrované jako zařízení: Každých 8 hodin.

Pokud se zařízení právě zaregistrovalo, četnost ohlašování bude vyšší:

- iOS a Mac OS X: Prvních 6 hodin každých 15 minut a potom každých 6 hodin.
- Android: Prvních 15 minut každé 3 minuty, další 2 hodiny každých 15 minut a potom každých 8 hodin.
- Windows Phone: Prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin.
- Počítače s Windows zaregistrované jako zařízení: Prvních 30 minut každé 3 minuty a potom každých 8 hodin.

Uživatelé můžou taky otevřít aplikaci Portál společnosti a synchronizovat zařízení. Zásady se tak zkontrolují hned.

### <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Které akce způsobí, že Intune hned pošle oznámení do zařízení?
Zařízení se ohlašují službě Intune, buď když dostanou oznámení, že se mají ohlásit, nebo při pravidelném plánovaném ohlašování.  Když akce, jako je vymazání, zamknutí, resetování hesla, nasazení aplikace, nasazení profilu (WiFi, VPN, e-mail atd.) nebo nasazení zásad, cílí na konkrétního uživatele nebo zařízení, Intune se hned pokusí zařízení upozornit, že by se mělo ohlásit službě Intune a získat tyto aktualizace.

Ostatní změny, jako je třeba úprava kontaktních informací na portálu společnosti, nezpůsobí okamžité odeslání oznámení.

### <a name="if-multiple-policies-are-deployed-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a>Pokud se pro stejné zařízení nebo uživatele nasadí víc zásad, jak poznám, které nastavení se použije?
Pokud se pro stejného uživatele nebo zařízení nasadí dvě nebo víc zásad, k vyhodnocení toho, které nastavení se použije, dochází na úrovni jednotlivých nastavení:

-   Nastavení zásad dodržování předpisů mají vždycky přednost před nastaveními zásad konfigurace.

-   Nejvíc omezující nastavení zásad dodržování předpisů se použije při vyhodnocení proti stejnému nastavení v jiné zásadě dodržování předpisů.

-   Pokud je nastavení zásady konfigurace v konfliktu s nastavením v rámci jiné zásady konfigurace, zobrazí se tento konflikt v konzole Intune. Takové konflikty je třeba vyřešit ručně.

### <a name="what-happens-when-mobile-application-management-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a>Co se stane, když jsou zásady správy mobilních aplikací ve vzájemném konfliktu? Která se použije pro příslušnou aplikaci?
Nejvíc omezující nastavení v zásadách MAM jsou konfliktní hodnoty, s výjimkou polí s počtem zadání (jako jsou pokusy o zadání PINu před resetováním).  Pole s počtem zadání se nastaví na stejnou hodnotu, jako když zásadu MAM vytvoříte v konzole pomocí možnosti doporučeného nastavení.

Konflikt nastane, když je nastavení dvou zásad stejné.  Představte si třeba, že jste nakonfigurovali dvě zásady MAM, které jsou stejné až na nastavení kopírování/vkládání.  V tomto scénáři se nastavení kopírování/vkládání nastaví na nejvíc omezující hodnotu, ale ostatní nastavení se použijí tak, jak se nakonfigurovala.

Pokud se jedna zásada nasadí do aplikace a uplatní se a pak se nasadí druhá zásada, bude mít první zásada přednost a zůstane nasazená, a u druhé se zobrazí konflikt. Když se obě nasadí současně, to znamená, že není žádná předchozí zásada, budou v konfliktu obě. Všechna konfliktní nastavení se nastaví na nejvíc omezující hodnoty.

### <a name="what-happens-when-ios-custom-policies-conflict"></a>Co se stane při konfliktu vlastních zásad iOS?
Intune nevyhodnocuje datovou část konfiguračních souborů Apple nebo vlastní zásady OMA-URI (Open Mobile Alliance Uniform Resource Identifier). Slouží jenom jako mechanismus doručování.

Když nasadíte vlastní zásadu, zkontrolujte, jestli nakonfigurované nastavení není v konfliktu se zásadami dodržování předpisů, konfiguračními zásadami nebo jinými vlastními zásadami. Při konfliktu mezi nastavením a vlastní zásadou je pořadí použití nastavení náhodné.

### <a name="what-happens-when-a-policy-is-deleted-or-no-longer-applicable"></a>Co se stane, když se zásada odstraní nebo už není platná?
Pokud odstraníte zásadu nebo odeberete zařízení ze skupiny, na kterou byla zásada nasazená, zásada a nastavení se ze zařízení odeberou podle následujících seznamů.

#### <a name="enrolled-devices"></a>Registrovaná zařízení

- Profily sítě Wi-Fi, VPN, certifikátu a e-mailu: Tyto profily se odeberou ze všech podporovaných registrovaných zařízení.
- Všechny ostatní typy zásad:
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

#### <a name="windows-pcs-running-the-intune-client-software"></a>Počítače s Windows s klientským softwarem Intune

- **Nastavení služby Endpoint Protection**: Obnoví se doporučené hodnoty nastavení. Jedinou výjimkou je nastavení **Připojit ke službě Microsoft Active Protection Service**, pro které je výchozí hodnota **Ne**. Podrobnosti najdete v tématu [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).
- **Nastavení aktualizací softwaru**: Nastavení se obnoví do výchozího stavu pro příslušný operační systém. Podrobnosti najdete v tématu [Udržování počítačů s Windows v aktuálním stavu díky softwarovým aktualizacím v Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).
- **Nastavení Microsoft Intune Center**: Z počítačů se odstraní veškeré kontaktní informace podpory, které zásady nakonfigurovaly.
- **Nastavení brány Windows Firewall**: Nastavení se obnoví na výchozí hodnoty pro operační systém počítače. Podrobnosti najdete v tématu [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).


### <a name="how-can-i-refresh-the-policies-on-a-device-to-ensure-that-they-are-current-applies-to-windows-pcs-running-the-intune-client-software-only"></a>Jak se dají aktualizovat zásady na zařízení, aby se zajistila jejich aktuálnost (platí jenom pro počítače s Windows a klientským softwarem Intune)?

1.  V kterékoli skupině zařízení vyberte zařízení, na kterých chcete zásady aktualizovat, a potom vyberte **Vzdálené úlohy** &gt; **Obnovit zásady**.
2.  V pravém dolním rohu okna konzoly pro správu Intune vyberte **Vzdálené úlohy** a zkontrolujte stav úlohy.

### <a name="where-can-i-find-help-troubleshooting-policies"></a>Kde najdu nápovědu k odstraňování potíží se zásadami?

Projděte si téma [Řešení potíží se zásadami v Microsoft Intune](/intune/troubleshoot/troubleshoot-policies-in-microsoft-intune).

