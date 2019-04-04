---
title: Vytvoření zásad dodržování předpisů pro Android v Microsoft Intune – Azure | Microsoft Docs
description: V Microsoft Intune můžete pro zařízení s Androidem Enterprise nebo s pracovním profilem vytvářet zásady dodržování předpisů nebo je konfigurovat. Rozhodněte se povolit zařízení s jailbreakem, nastavte přijatelnou úroveň hrozby, zkontrolujte Google Play, zadejte minimální a maximální verzi operačního systému, zvolte si požadavky na heslo a povolte bokem instalované aplikace.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/02/2019
ms.topic: reference
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 00c48f49507fe4fde5484d0725b605d90407facd
ms.sourcegitcommit: 699427f36dbf31dc7921fb75da647b736eafd79b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/03/2019
ms.locfileid: "58899049"
---
# <a name="add-a-device-compliance-policy-for-android-enterprise-devices-in-intune"></a>Přidání zásady dodržování předpisů pro zařízení s Androidem Enterprise v Intune

Zásady dodržování předpisů pro zařízení jsou klíčovou funkcí Intune, která umožňuje chránit prostředky organizace. V Intune můžete vytvořit pravidla a nastavení, která musí zařízení s Androidem Enterprise splňovat, aby být považováno za dodržující předpisy, třeba délku hesla. Pokud zařízení nevyhovuje, můžete [podmíněným přístupem](conditional-access.md) zablokovat přístup k datům a prostředkům.

Tato funkce platí pro:  
- Android Enterprise

Můžete také získat sestavy o zařízení a v případě jeho nevyhovujícího stavu podniknout určité akce, třeba poslat uživateli oznámení e-mailem. Další informace o zásadách dodržování předpisů a případných požadavcích najdete v tématu [Začínáme s dodržováním předpisů](device-compliance-get-started.md).

V tomto článku je seznam nastavení, která můžete v rámci zásad dodržování předpisů použít u zařízení s Androidem Enterprise.

## <a name="non-compliance-and-conditional-access"></a>Nevyhovující stav a podmíněný přístup

Následující tabulka popisuje, jak jsou spravované nevyhovující nastavení při použití zásad dodržování předpisů se zásadami podmíněného přístupu.

--------------------------

|**nastavení zásad**| **Profil Androidu Enterprise** |
| --- | --- |
| **Konfigurace kódu PIN nebo hesla** |  V karanténě |
| **Šifrování zařízení** |  V karanténě |
| **Zařízení s jailbreakem nebo rootem** | V karanténě (není nastavení) |
| **e-mailový profil** | Nelze použít |
| **Minimální verze operačního systému** | V karanténě |
| **Maximální verze operačního systému** | V karanténě |
| **Ověření stavu Windows** |Nelze použít |

**Opravené** = operační systém zařízení vynucuje dodržování předpisů. Uživatel musí třeba zadat kód PIN.

**V karanténě** = operační systém zařízení nevyhovuje předpisům. Například zařízení s Androidem nenutí uživatele zašifrovat obsah zařízení. Pokud zařízení nevyhovuje, provedou se následující akce:

  - Pokud se zásady podmíněného přístupu vztahují na uživatele, zařízení se zablokuje.
  - Portál společnosti oznamuje uživateli všechny problémy s dodržováním předpisů.

## <a name="create-a-device-compliance-policy"></a>Vytváření zásad dodržování předpisů pro zařízení

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
4. V poli **Platforma** vyberte **Android Enterprise**. 
5. Zvolte **konfiguraci nastavení**. Nastavte **Stav zařízení**, **Vlastnosti zařízení** a **Zabezpečení systému** podle popisu v tomto článku.

## <a name="device-health"></a>Device health

- **Zařízení s rootem**: Zvolte **bloku** se začínající kořenovým adresářem (zařízení s jailbreakem) zařízení označí jako nedodržující předpisy. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vyžadovat, aby zařízení bylo na nebo za úrovně hrozby pro zařízení**: Toto nastavení použijte k vyhodnocování rizika z řešení Lookout MTP jako podmínku dodržování předpisů. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. Pokud chcete nastavení použít, zvolte povolenou úroveň ohrožení:
  - **Zabezpečené**: Tato možnost je nejbezpečnější a znamená, že zařízení nesmí obsahovat žádné hrozby. Pokud jsou na zařízení zjištěny hrozby jakékoli úrovně, vyhodnotí se jako nevyhovující.
  - **Nízká**: Zařízení je vyhodnoceno jako vyhovující, pokud jen hrozby nízké úrovně jsou k dispozici. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení je vyhodnoceno jako vyhovující, pokud, které se nacházejí v zařízení hrozby střední nebo nízké úrovni. Pokud se u zařízení zjistí vysoká míra ohrožení, vyhodnotí se jako nevyhovující.
  - **Vysoká**: Tato možnost je nejméně bezpečná, protože umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.

### <a name="google-play-protect"></a>Ochrana služby Google Play

- **Služby Google Play je nakonfigurovaná**: **Vyžadovat** , že služby Google Play aplikace je nainstalován a povolen. Aplikace Služby Google Play umožňuje instalaci aktualizací zabezpečení a je základní závislostí pro mnoho funkcí zabezpečení na zařízeních s certifikací Google. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Aktualizovaný poskytovatel zabezpečení**: **Vyžadovat** , aby aktualizovaný poskytovatel zabezpečení chránil zařízení před známými chybami zabezpečení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **V rámci ověření zařízení SafetyNet**: Zadejte úroveň [ověření SafetyNet](https://developer.android.com/training/safetynet/attestation.html) , který musí být splněny. Možnosti:
  - **Není nakonfigurováno** (výchozí): Nastavení se nevyhodnotí dodržování předpisů nebo nedodržení předpisů.
  - **Zkontrolovat základní integritu**
  - **Zkontrolovat základní integritu a certifikovaná zařízení**

> [!NOTE]
> Na zařízeních s Androidem Enterprise **kontrola ohrožení aplikací** je zásad konfigurace zařízení. Pomocí zásad konfigurace, můžou správci povolit nastavení na zařízení. Další informace viz [Nastavení omezení pro zařízení s Androidem](device-restrictions-android-for-work.md).

## <a name="device-properties-settings"></a>Nastavení vlastností zařízení

- **Minimální verze operačního systému**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nedodržující předpisy. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může zařízení upgradovat. Potom bude mít přístup k prostředkům společnosti.
- **Maximální verze operačního systému**: Pokud zařízení používá verzi operačního systému novější než verze v pravidle, přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud se nezmění pravidlo, aby tuto verzi operačního systému povolovalo, nebude mít zařízení přístup k prostředkům společnosti.

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadovat** uživatelé zadat heslo, než bude moct svoje zařízení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. Toto nastavení se použije na úrovni zařízení. Pokud potřebujete jenom se vyžaduje heslo na úrovni pracovního profilu, použijte zásadu konfigurace. Zobrazit [nastavení konfigurace zařízení s Androidem Enterprise](device-restrictions-android-for-work.md).
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Vyžadovaný typ hesla**: Zvolte, pokud heslo by měl obsahovat pouze číselné znaky, nebo kombinací číslic a dalších znaků. Možnosti:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Aspoň číselné** (výchozí)
  - **Číselné komplexní**
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**

- **Maximální počet minut nečinnosti před vyžádáním hesla**: Zadejte dobu nečinnosti, než uživatel musí znovu zadat heslo. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vypršení platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která zakázat opakované použití**: Zadejte počet dřívějších hesel, která se nesmí znovu použít. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.

### <a name="encryption"></a>Šifrování

- **Šifrování datového úložiště na zařízení**: Zvolte **vyžadují** a zašifrujte úložiště dat na vašich zařízeních. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. 

  Toto nastavení nemusíte konfigurovat, protože zařízení s pracovním profilem Androidu šifrování vyžadují.

### <a name="device-security"></a>Zabezpečení zařízení

- **Blokovat aplikace z neznámých zdrojů**: Zvolit **bloku** zařízení s "Zabezpečení > neznámé zdroje" povolené zdroje (podporuje se ve Android 4.0 – Android 7.x; není podporované nepodporováno na Androidu 8.0 a novější). Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Pokud chcete instalovat aplikace bokem, musí být povoleny neznámé zdroje. Pokud aplikace pro Android neinstalujete bokem, nastavte tuto funkci na **Blokovat**, abyste tuto zásadu dodržování předpisů povolili. 

  > [!IMPORTANT]
  > Aplikace instalované bokem vyžadují, aby bylo povolené nastavení **Blokovat aplikace z neznámých zdrojů**. Na dodržení této zásady trvejte jenom v případě, že na zařízeních neprovádíte instalaci aplikací pro Android bokem.

  Toto nastavení nemusíte konfigurovat, protože v zařízeních s pracovním profilem Androidu je instalace z neznámých zdrojů zakázaná vždy.

- **Integrita modulu runtime aplikace portál společnosti**: Zvolte **vyžadují** potvrďte portálu společnosti aplikaci splňuje následující požadavky:

  - Má nainstalované výchozí prostředí modulu runtime.
  - Je řádně podepsaná.
  - Není v režimu ladění.
  - Je nainstalovaná ze známého zdroje.

  Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

- **Blokovat u zařízení ladění USB**: Zvolte **bloku** chcete zabránit používání funkce ladění USB zařízení. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Toto nastavení nemusíte konfigurovat, protože v zařízeních s pracovním profilem Androidu je ladění USB zakázané.

- **Minimální úroveň oprav zabezpečení**: Vyberte nejstarší úroveň opravy zabezpečení, kterou může zařízení mít. Zařízení, která nemají aspoň tuto úroveň opravy, nevyhovují. Datum musí být zadáno ve formátu *RRRR-MM-DD*.

Až to budete mít, uložte změny volbou **OK** > **OK**.

## <a name="actions-for-noncompliance"></a>Akce při nedodržení předpisů

Vyberte **Akce při nedodržení předpisů**. Výchozí akce okamžitě označí zařízení jako nedodržující předpisy.

Pokud je zařízení označené jako nevyhovující, můžete plán třeba další den změnit. Můžete také nakonfigurovat druhou akci, která uživateli nevyhovujícího zařízení pošle e-mail.

Další informace, včetně návodu na vytvoření e-mailu s oznámením pro uživatele, najdete v článku o [přidání akcí pro nevyhovující zařízení](actions-for-noncompliance.md).

## <a name="scope-tags"></a>Značky oboru

Značky oboru umožňují přiřadit zásady určitým skupinám, třeba prodejnímu, technickému, personálnímu nebo jinému oddělení. Značky oboru můžete přidat do zásad dodržování předpisů. Další informace najdete v článku [Filtrování zásad pomocí značek oboru](scope-tags.md). 

## <a name="assign-user-groups"></a>Přiřazení skupin uživatelů

Vytvořená zásada nedělá nic, dokud ji nepřiřadíte. Přiřazení zásady: 

1. Vyberte zásadu, kterou jste nakonfigurovali. Existující zásady najdete v **Dodržování předpisů zařízením** > **Zásady**.
2. Zvolte zásady a pak **Přiřazení**. Můžete zahrnout nebo vyloučit skupiny zabezpečení služby Azure Active Directory (AD).
3. Vyberte **Vybrané skupiny** a zobrazte skupiny zabezpečení Azure AD. Můžete vybrat skupiny uživatelů, na které chcete zásady použít, a pak pomocí **Uložit** tyto zásady uživatelům nasadit.

Nastavili jste zásady uživatelům zařízení. U zařízení používaných uživateli, pro která platí nastavené zásady, se vyhodnocuje, jestli vyhovují.

## <a name="next-steps"></a>Další postup

[Automatické e-maily a přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md)  
[Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md)  
[Nastavení zásad dodržování předpisů pro Android](compliance-policy-create-android.md)
