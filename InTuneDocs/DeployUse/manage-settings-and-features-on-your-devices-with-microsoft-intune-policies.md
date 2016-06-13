---
# required metadata

title: Správa nastavení a funkcí v zařízeních pomocí zásad | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 09bae0b9-4f79-4658-8ca1-a71ab992c1b2

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune
**Zásady** služby Microsoft Intune jsou skupiny nastavení, které řídí funkce pro mobilní zařízení a počítače. Zásady můžete vytvořit pomocí šablon, které obsahují doporučená nebo přizpůsobená nastavení, a pak je můžete nasadit na skupiny zařízení nebo uživatelů.

## Jaké typy zásad můžete používat?

Zásady Intune spadají do následujících kategorií. Kategorie, kterou použijete, má vliv na způsob vytvoření a nasazení zásady.


- **Zásady konfigurace:** Běžně se používají ke správě nastavení a funkcí zabezpečení na vašich zařízeních. Z tohoto tématu se dozvíte, jak tyto zásady vytvořit a nasadit, a dozvíte se o dostupných nastaveních.
- **Zásady dodržování předpisů zařízení:** Tyto zásady určují pravidla a nastavení, které musí zařízení dodržovat, aby se dalo považovat za zařízení, které dodržuje zásady podmíněného přístupu. Zásady dodržování předpisů můžete používat i k monitorování a opravám dodržování předpisů u zařízení, a to nezávisle na podmíněném přístupu.
Podrobnosti najdete v tématu [Zásady dodržování předpisů u zařízení v Microsoft Intune](introduction-to-device-compliance-policies-in-microsoft-intune.md).
- **Zásady podmíněného přístupu:** Tyto zásady vám pomůžou zabezpečit e-mail a další služby v závislosti na zadaných podmínkách.
Podrobnosti najdete v tématu [Omezení přístupu k e-mailu a službám O365 pomocí Microsoft Intune](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).
- **Zásady registrace podnikových zařízení:** Informace o vytváření zásad registrace podnikových zařízení najdete v tématu [Nastavení správy pro iOS a Mac pomocí Microsoft Intune](set-up-ios-and-mac-management-with-microsoft-intune.md).
- **Zásady přístupu k prostředkům:** Tato skupina zásad společně pomáhá zajistit uživatelům přístup odkudkoli k souborům a prostředkům, které potřebují ke své práci.
Podrobnosti najdete v tématu [Povolení přístupu k prostředkům společnosti pomocí Microsoft Intune](enable-access-to-company-resources-with-microsoft-intune.md).


Úplný seznam zásad služby Intune najdete v tématu [Odkazy na zásady služby Microsoft Intune](microsoft-intune-policy-reference.md).




## Vytvoření zásady konfigurace

1.  V [konzole správce Microsoft Intune](https://manage.microsoft.com/) klikněte na **Zásady** &gt; **Zásady konfigurace** &gt; **Přidat**.

2.  Zvolte požadovanou zásadu a vyberte doporučené nastavení pro tuto zásady (pokud je dostupné; toto nastavení pak můžete později změnit), nebo vytvořte vlastní zásadu s vlastním nastavením.

    > [!TIP] Pokud potřebujete pomoc s výběrem správné zásady, projděte si téma [Odkazy na zásady Microsoft služby Intune](microsoft-intune-policy-reference.md).

3.  Až budete připravení, klikněte na **Vytvořit zásadu**.

4.  Na obrazovce **Vytvořit zásadu** nakonfigurujte název a volitelný popis zásady.

5.  Nakonfigurujte požadovaná nastavení a pak klikněte na **Uložit zásadu**.

    Pokud potřebujete pomoc s nastavením zásad, vyberte v následujícím seznamu typ své zásady:

    - [Nastavení pro zařízení se systémem iOS](ios-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zařízení se systémem Android](android-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zařízení s Windows 8 a Windows 8.1](windows-configuration-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zařízení Windows Phone 8.1](windows-phone-8-1-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro stolní počítače a mobilní zařízení s Windows 10](windows-10-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zařízení Windows Team](windows-team-configuration-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro upgrade edice systému Windows](edition-upgrade-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zařízení Mac OS X](mac-os-x-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro protokol Exchange ActiveSync](exchange-activesync-policy-settings-in-microsoft-intune.md)
    - [Nastavení pro zásady podmínek a ujednání](terms-and-condition-policy-settings-in-microsoft-intune.md)
    - [Obecné nastavení pro mobilní zařízení (zastaralé)](mobile-device-security-policy-settings-in-microsoft-intune.md)

4.  Kliknutím na tlačítko **Ano** v potvrzovacím dialogovém okně zásadu hned nasadíte, kliknutím na **Ne** zásadu vytvoříte, ale nenasadíte ji.

Novou zásadu můžete zobrazit a upravit tak, že si projdete oddíly pro každý typ zásad v pracovním prostoru **Zásady** .

Když vytvoříte zásadu, která používá doporučená nastavení, je název nové zásady kombinací názvu šablony, data a času. Když zásadu upravujete, název se aktualizuje pomocí data a času úpravy.

Teď když je zásada vytvořená, budete ji obvykle chtít nasadit do jedné nebo víc skupin uživatelů nebo zařízení.

> [!TIP]
> Nenasazujete všechny typy zásad. Třeba zásada správy mobilních aplikací se nenasadila. Tento typ zásad se místo toho přidruží aplikaci a teprve ta se pak nasadí.

## Nasazení zásady konfigurace

1.  V pracovním prostoru **Zásady** vyberte zásadu, kterou chcete nasadit, a pak klikněte na **Spravovat nasazení**.

2.  V dialogovém okně **Spravovat nasazení** :

    -   **Pokud chcete zásadu nasadit** – vyberte jednu nebo víc skupin, do kterých chcete zásady nasadit, a pak klikněte na **Přidat** &gt; **OK**.

    -   **Pokud chcete dialogové okno zavřít bez nasazení zásady** – klikněte na **Zrušit**.

Když vyberete nasazenou zásadu, zobrazí se v dolní části seznamu zásad další informace o tomto nasazení.

## Správa zásad

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/)klikněte na **Zásady**a vyhledejte a vyberte zásadu, kterou chcete spravovat.

2.  Vyberte jednu z následujících akcí:

- **Upravit**: Otevře vlastnosti vybrané zásady a umožní vám provádět změny.
- **Odstranit**: Odstraní vybranou zásadu.<br>Pokud zásadu odstraníte, odebere se ze všech skupin, ve kterých byla nasazená.
- **Spravovat nasazení**: Vyberte skupinu, do které chcete zásadu nasadit, a klikněte na **Přidat**.

## Úlohy pro zásady Intune

### Aktualizace zásad na zařízení k zajištění jejich aktuálnosti (platí jenom pro počítače s Windows a klientským softwarem Intune)

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/)klikněte na **Skupiny**a pak vyberte skupinu zařízení.

2.  Vyberte zařízení, na kterých chcete zásady aktualizovat, a pak klikněte na **Vzdálené úlohy** &gt; **Obnovit zásady**.

3.  V pravém dolním rohu okna konzoly správce Intune klikněte na **Vzdálené úlohy** a zkontrolujte stav úlohy.

## Nejčastější dotazy týkající se zásad Intune

### Jak dlouho trvá mobilnímu zařízení, než získá zásadu nebo aplikaci potom, co byly nasazené?
Po nasazení zásady nebo aplikace se Intune hned začne pokoušet upozornit zařízení, že se mělo ohlásit službě Intune. To obvykle trvá méně než 5 minut.

Pokud se zařízení neohlásí po odeslání prvního oznámení, následují 3 další pokusy.  Když je zařízení offline (je třeba vypnuté nebo není připojené k síti), nemusí oznámení vůbec dostat.

V takovém případě zařízení získá zásadu při dalším plánovaném ohlášení své přítomnosti ve službě Intune:

- iOS – každých 6 hodin
- Android – každých 8 hodin
- Windows Phone – každých 8 hodin
- Zaregistrovaná zařízení s Windows RT – každých 24 hodin
- Počítače s Windows 8.1 a Windows 10 zaregistrované jako zařízení – každých 8 hodin

Pokud se zařízení právě zaregistrovalo, četnost ohlašování bude vyšší:

- iOS – prvních 6 hodin každých 15 minut a potom každých 6 hodin
- Android – prvních 15 minut každé 3 minuty, další 2 hodiny každých 15 minut a potom každých 8 hodin
- Windows Phone – prvních 15 minut každých 5 minut, další 2 hodiny každých 15 minut a potom každých 8 hodin
- Počítače s Windows zaregistrované jako zařízení – prvních 30 minut každé 3 minuty a potom každých 24 hodin

Uživatelé můžou taky spustit aplikaci Portál společnosti a synchronizovat zařízení. Zásady se tak zkontrolují hned.

### Jaké akce způsobí, že Intune hned zařízení odešle oznámení?
Zařízení se ohlašují službě Intune buď když dostanou oznámení, že se mají ohlásit, nebo při pravidelném plánovaném ohlašování, jak je uvedené v tabulkách výše.  Když akce, jako je vymazání, zamknutí, resetování hesla, nasazení aplikace, nasazení profilu (WiFi, VPN, e-mail atd.) nebo nasazení zásad, cílí na konkrétního uživatele nebo zařízení, Intune se hned pokusí zařízení upozornit, že by se mělo ohlásit službě Intune a získat tyto aktualizace.

Ostatní změny, jako je třeba úprava kontaktních informací na portálu společnosti, nezpůsobí okamžité odeslání oznámení.

> [!TIP]
> Když je nastavení obsahující zásadu nasazené na zařízení s Androidem, uživatel se upozorní, že k zajištění souladu se zásadou je nutné provést akci. Dokud uživatel tuto akci neprovede nebo dokud se zařízení nerestartuje, nastavení nové zásady nebude platné.

### Pokud se pro stejné zařízení nebo uživatele nasadí víc zásad, jak poznám, které nastavení se použije?
Je důležité vědět, že pokud se pro stejného uživatele nebo zařízení nasadí dvě nebo víc zásad, vyhodnocení toho, které nastavení se použije, se provádí na úrovni jednotlivých nastavení.

-   Nastavení zásad dodržování předpisů mají vždycky přednost před nastaveními zásad konfigurace.

-   Nejvíc omezující nastavení zásad dodržování předpisů se použije při vyhodnocení proti stejnému nastavení v jiné zásadě dodržování předpisů.

-   Nejvíc omezující nastavení zásad konfigurace se použije při vyhodnocení proti stejnému nastavení v jiné zásadě konfigurace.

### Co se stane, když jsou zásady správy mobilních aplikací (MAM) ve vzájemném konfliktu? Která se použije pro příslušnou aplikaci?
Nejvíc omezující nastavení v zásadách správy mobilních aplikací jsou konfliktní hodnoty, s výjimkou polí s počtem zadání (jako jsou pokusy o zadání PINu před resetováním).  Pole s počtem zadání se nastaví na stejnou hodnotu, jako když zásadu MAM vytvoříte v konzole pomocí možnosti doporučeného nastavení.

Konflikt nastane, když je nastavení dvou zásad stejné.  Představte si třeba, že jste nakonfigurovali dvě zásady MAM, které jsou stejné až na nastavení kopírování/vkládání.  V tomto scénáři se nastavení kopírování/vkládání nastaví na nejvíc omezující hodnotu, ale ostatní nastavení se použijí tak, jak se nakonfigurovala.

Pokud se jedna zásada nasadí do aplikace a uplatní se a pak se nasadí druhá zásada, bude mít první nasazená zásada přednost a zůstane nasazená, a u druhé se zobrazí konflikt. Když se ale obě nasadí současně, to znamená, že nebude žádná předchozí zásada, budou v konfliktu obě a všechna konfliktní nastavení se nastaví na nejvíc omezující hodnoty.

### Co se stane při konfliktu vlastních zásad iOS?
Intune nevyhodnocuje datovou část konfiguračních souborů Apple nebo vlastní zásady OMA-URI, slouží jenom jako mechanismus doručování.

Proto když nasadíte vlastní zásadu, zkontrolujte, jestli nakonfigurované nastavení není v konfliktu se zásadami dodržování předpisů, konfiguračními zásadami nebo jinými vlastními zásadami. Při konfliktu mezi nastavením a vlastní zásadou je pořadí použití nastavení náhodné.

### Co se stane, když se zásada odstraní nebo už není platná?
Pokud odstraníte zásadu nebo odeberete zařízení ze skupiny, na kterou byla zásada nasazená, zásada a nastavení se ze zařízení odeberou podle následujících tabulek:

#### Registrovaná zařízení

- Profily sítě Wi-Fi, VPN, certifikátu a e-mailu – tyto profily se odeberou ze všech podporovaných registrovaných zařízení.
- Všechny ostatní typy zásad
    - **Zařízení s Windows a Androidem** – ze zařízení se neodebere nastavení.
    - **Zařízení Windows Phone 8.1** – odeberou se tato nastavení:
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
    
    - **iOS** – odeberou se všechna nastavení s těmito výjimkami:
        - Povolit hlasový roaming
        - Povolit datový roaming
        - Povolit automatickou synchronizaci při roamingu

#### Počítače s Windows s klientským softwarem Intune

- **Nastavení služby Endpoint Protection** – obnoví se doporučené hodnoty nastavení. Jedinou výjimkou je nastavení **Připojit ke službě Microsoft Active Protection Service** , pro které je výchozí hodnota **Ne**. Podrobnosti najdete v tématu [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).
- **Nastavení aktualizací softwaru** – nastavení se obnoví do výchozího stavu pro operační systém. Podrobnosti najdete v tématu [Udržování počítačů s Windows v aktuálním stavu díky softwarovým aktualizacím v Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md).
- **Nastavení Microsoft Intune Center** – veškeré kontaktní informace podpory, které zásady nakonfigurovaly, se z počítače odstraní.
- **Nastavení brány Windows Firewall** – nastavení se obnoví na výchozí hodnoty pro operační systém počítače. Podrobnosti najdete v tématu [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md).





<!--HONumber=May16_HO3-->


