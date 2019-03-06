---
title: Vytvoření zásad dodržování předpisů pro zařízení s Androidem v Microsoft Intune – Azure | Microsoft Docs
description: Vytvářejte nebo konfigurujte zásady dodržování předpisů zařízením služby Microsoft Intune pro zařízení s Androidem. Rozhodněte se povolit zařízení s jailbreakem, nastavte přijatelnou úroveň hrozby, zkontrolujte Google Play, zadejte minimální a maximální verzi operačního systému, zvolte si požadavky na heslo a povolte bokem instalované aplikace.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 473b6259a3ae6fb4da4ad1977423afc381f8168c
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57389571"
---
# <a name="add-a-device-compliance-policy-for-android-devices-in-intune"></a>Přidání zásad dodržování předpisů pro zařízení s Androidem v Intune

Zásada dodržování předpisů Intune pro zařízení s Androidem určuje pravidla a nastavení, které musí zařízení s Androidem splňovat, aby bylo považováno za dodržující předpisy. Tyto zásady [podmíněného přístupu](conditional-access.md) můžete použít k povolení nebo zablokování přístupu k prostředkům organizace. Můžete také získat sestavy zařízení a provádět akce v případě nedodržování předpisů. 

Další informace o zásadách dodržování předpisů a případných požadavcích najdete v tématu [Začínáme s dodržováním předpisů](device-compliance-get-started.md).

V tomto tématu najdete nastavení, která můžete v rámci zásad dodržování předpisů použít u zařízení s Androidem.

## <a name="non-compliance-and-conditional-access"></a>Nevyhovující stav a podmíněný přístup

Následující tabulka popisuje, jak jsou spravované nevyhovující nastavení při použití zásad dodržování předpisů se zásadami podmíněného přístupu.

--------------------

|**Nastavení zásad**| **Android 4.0 nebo novější, Samsung Knox Standard 4.0 nebo novější** |
| --- | ----|
| **Konfigurace kódu PIN nebo hesla** |  V karanténě |
| **Šifrování zařízení** | V karanténě |
| **Zařízení s jailbreakem nebo rootem** | V karanténě (není nastavení) |
| **e-mailový profil** | Nelze použít |
| **Minimální verze operačního systému** | V karanténě |
| **Maximální verze operačního systému** |   V karanténě |
| **Ověření stavu Windows** | Nelze použít |

--------------------------

**Opravené** = operační systém zařízení vynucuje dodržování předpisů. Uživatel musí třeba zadat kód PIN.

**V karanténě** = operační systém zařízení nevyhovuje předpisům. Například zařízení s Androidem nenutí uživatele zašifrovat obsah zařízení. Pokud zařízení nesplňuje předpisy, provedou se následující akce:

  - Zařízení se zablokuje, pokud se zásady podmíněného přístupu vztahují na uživatele.
  - Portál společnosti oznamuje uživateli všechny problémy s dodržováním předpisů.

## <a name="create-a-device-compliance-policy"></a>Vytváření zásad dodržování předpisů pro zařízení

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. U možnosti **Platforma** vyberte **Android**. 
5. Zvolte **konfiguraci nastavení**. Nastavte **Stav zařízení**, **Vlastnosti zařízení** a **Zabezpečení systému** podle popisu v tomto článku.

## <a name="device-health"></a>Device health

- **Zařízení s rootem**: Zvolte **bloku** se začínající kořenovým adresářem (zařízení s jailbreakem) zařízení označí jako nedodržující předpisy. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vyžadovat, aby zařízení bylo na nebo za úrovně hrozby pro zařízení**: Toto nastavení použijte k vyhodnocování rizika z řešení Lookout MTP jako podmínku dodržování předpisů. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. Pokud chcete nastavení použít, zvolte povolenou úroveň ohrožení:
  - **Zabezpečené**: Tato možnost je nejbezpečnější, protože zařízení nesmí být nijak ohroženo zabezpečení. Pokud jsou na zařízení zjištěny hrozby jakékoli úrovně, vyhodnotí se jako nevyhovující.
  - **Nízká**: Zařízení je vyhodnoceno jako vyhovující, pokud jen hrozby nízké úrovně jsou k dispozici. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení je vyhodnoceno jako vyhovující, pokud se existující hrozby v zařízení se střední nebo nízké úrovni. Pokud se u zařízení zjistí vysoká míra ohrožení, vyhodnotí se jako nevyhovující.
  - **Vysoká**: Tato možnost je nejméně bezpečná a umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.
- **Služby Google Play je nakonfigurovaná**: **Vyžadovat** , že služby Google Play aplikace je nainstalován a povolen. Aplikace Služby Google Play umožňuje instalaci aktualizací zabezpečení a je základní závislostí pro mnoho funkcí zabezpečení na zařízeních s certifikací Google. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Aktualizovaný poskytovatel zabezpečení**: **Vyžadovat** , aby aktualizovaný poskytovatel zabezpečení chránil zařízení před známými chybami zabezpečení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Kontrola ohrožení aplikací**: **Vyžadovat** , která Android **ověřovat aplikace** funkce je povolená. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  > [!NOTE]
  > Na starších verzích platformy Android tato funkce představuje nastavení dodržování předpisů. Intune může jenom zkontrolovat, jestli je toto nastavení povolené na úrovni zařízení.

- **V rámci ověření zařízení SafetyNet**: Zadejte úroveň [ověření SafetyNet](https://developer.android.com/training/safetynet/attestation.html) , který musí být splněny. Možnosti:
  - **Není nakonfigurováno** (výchozí): Nastavení se nevyhodnotí dodržování předpisů nebo nedodržení předpisů.
  - **Zkontrolovat základní integritu**
  - **Zkontrolovat základní integritu a certifikovaná zařízení**

## <a name="device-property-settings"></a>Nastavení vlastností zařízení

- **Minimální verze operačního systému**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nedodržující předpisy. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel si může zařízení upgradovat. Potom získá přístup k prostředkům společnosti.
- **Maximální verze operačního systému**: Když zařízení používá verzi operačního systému novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud se nezmění pravidlo, aby tuto verzi operačního systému povolovalo, nebude mít zařízení přístup k prostředkům společnosti.

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadovat** uživatelé zadat heslo, než bude moct svoje zařízení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Vyžadovaný typ hesla**: Zvolte, pokud heslo by měl obsahovat pouze číselné znaky, nebo kombinací číslic a dalších znaků. Možnosti:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Aspoň číselné** (výchozí)
  - **Číselné komplexní**: Opakované nebo po sobě jdoucí čísla, jako například `1111` nebo `1234`, nejsou povoleny.
  - **Aspoň abecední znaky** 
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**

- **Maximální počet minut nečinnosti před vyžádáním hesla**: Zadejte dobu nečinnosti, než uživatel musí znovu zadat heslo. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vypršení platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové heslo.
- **Počet předchozích hesel, která zakázat opakované použití**: Zadejte počet dřívějších hesel, která se nesmí znovu použít. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.

### <a name="encryption"></a>Šifrování

- **Šifrování datového úložiště na zařízení** (Android 4.0 a vyšší nebo KNOX 4.0 a novější): Zvolte **vyžadují** a zašifrujte úložiště dat na vašich zařízeních. Zařízení se šifrují, pokud vyberete nastavení **Vyžadovat heslo k odemknutí mobilních zařízení**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

### <a name="device-security"></a>Zabezpečení zařízení

- **Blokovat aplikace z neznámých zdrojů**: Zvolit **bloku** zařízení s "Zabezpečení > neznámé zdroje" povolené zdroje (podporuje se ve Android 4.0 – Android 7.x; není podporované nepodporováno na Androidu 8.0 a novější). Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Pokud chcete instalovat aplikace bokem, musí být povoleny neznámé zdroje. Pokud aplikace pro Android neinstalujete bokem, nastavte tuto funkci na **Blokovat**, abyste tuto zásadu dodržování předpisů povolili. 

  > [!IMPORTANT]
  > Aplikace instalované bokem vyžadují, aby bylo povolené nastavení **Blokovat aplikace z neznámých zdrojů**. Na dodržení této zásady trvejte jenom v případě, že na zařízeních neprovádíte instalaci aplikací pro Android bokem.

- **Integrita modulu runtime aplikace portál společnosti**: Zvolte **vyžadují** potvrďte portálu společnosti aplikaci splňuje následující požadavky:

  - Má nainstalované výchozí prostředí modulu runtime.
  - Je řádně podepsaná.
  - Není v režimu ladění.
  - Je nainstalovaná ze známého zdroje.

  Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

- **Blokovat u zařízení ladění USB** (Android 4.2 nebo novější): Zvolte **bloku** chcete zabránit používání funkce ladění USB zařízení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Minimální úroveň oprav zabezpečení** (Android 6.0 nebo novější): Vyberte nejstarší úroveň opravy zabezpečení, kterou může zařízení mít. Zařízení, která nemají aspoň tuto úroveň opravy, nevyhovují. Datum musí být zadáno ve formátu `YYYY-MM-DD`.
- **Omezených aplikací**: Zadejte **název aplikace** a **ID sady prostředků aplikace** pro aplikace, které by měla být omezena. Zvolte **přidat**. Pokud je na zařízení nainstalovaná aspoň jedna zakázaná aplikace, označí se zařízení jako nevyhovující.

Až to budete mít, uložte změny volbou **OK** > **OK**.

## <a name="locations"></a>Umístění

V zásadách zvolte některé z existujících umístění. Žádné umístění ještě nemáte? Pokyny najdete v tématu o [používání umístění (ochranné sítě) v Intune](use-network-locations.md).

1. Zvolte **Umístění**.
2. V seznamu zkontrolujte umístění a zvolte **Vybrat**.
3. **Uložte** zásady.

## <a name="actions-for-noncompliance"></a>Akce při nedodržení předpisů

Vyberte **Akce při nedodržení předpisů**. Výchozí akce okamžitě označí zařízení jako nedodržující předpisy.

Pokud je zařízení označené jako nevyhovující, můžete plán třeba další den změnit. Můžete také nakonfigurovat druhou akci, která uživateli nevyhovujícího zařízení pošle e-mail.

Další informace, včetně návodu na vytvoření e-mailu s oznámením pro uživatele, najdete v článku o [přidání akcí pro nevyhovující zařízení](actions-for-noncompliance.md).

Pokud například používáte funkci Umístění, přidáte do zásady dodržování předpisů nějaké umístění a vyberete aspoň jedno umístění, použije se pro nevyhovující zařízení výchozí akce. Pokud zařízení není připojené k vybraným umístěním, považuje se hned za nevyhovující. Uživatelům můžete dát určitou lhůtu, třeba jeden den.

## <a name="scope-tags"></a>Značky oboru

Značky oboru umožňují přiřadit zásady určitým skupinám, třeba prodejnímu, technickému, personálnímu nebo jinému oddělení. Značky oboru můžete přidat zásadám dodržování předpisů. Další informace najdete v článku [Filtrování zásad pomocí značek oboru](scope-tags.md). 

## <a name="assign-user-groups"></a>Přiřazení skupin uživatelů

Vytvořená zásada nedělá nic, dokud ji nepřiřadíte. Přiřazení zásady: 

1. Vyberte zásadu, kterou jste nakonfigurovali. Existující zásady najdete v **Dodržování předpisů zařízením** > **Zásady**.
2. Zvolte zásady a pak **Přiřazení**. Můžete zahrnout nebo vyloučit skupiny zabezpečení služby Azure Active Directory (AD).
3. Vyberte **Vybrané skupiny** a zobrazte skupiny zabezpečení Azure AD. Můžete vybrat skupiny uživatelů, na které chcete zásady použít, a pak pomocí **Uložit** tyto zásady uživatelům nasadit.

Nastavili jste zásady uživatelům zařízení. U zařízení používaných uživateli, pro která platí nastavené zásady, se vyhodnocuje, jestli vyhovují.

## <a name="next-steps"></a>Další postup
[Automatické e-maily a přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md)  
[Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md)  
[Nastavení zásad dodržování předpisů pro Android Enterprise](compliance-policy-create-android-for-work.md)
