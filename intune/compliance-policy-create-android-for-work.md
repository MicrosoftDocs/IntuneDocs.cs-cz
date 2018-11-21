---
title: Vytvoření zásad dodržování předpisů pro Android v Microsoft Intune – Azure | Microsoft Docs
description: V Microsoft Intune můžete pro zařízení s Androidem Enterprise nebo s pracovním profilem vytvářet zásady dodržování předpisů nebo je konfigurovat. Rozhodněte se povolit zařízení s jailbreakem, nastavte přijatelnou úroveň hrozby, zkontrolujte Google Play, zadejte minimální a maximální verzi operačního systému, zvolte si požadavky na heslo a povolte bokem instalované aplikace.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: a606f63bd22ce2ed543b6c5863ddc4f35d7ea212
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52186201"
---
# <a name="add-a-device-compliance-policy-for-android-enterprise-devices-in-intune"></a>Přidání zásady dodržování předpisů pro zařízení s Androidem Enterprise v Intune

Zásady dodržování předpisů pro zařízení jsou klíčovou funkcí Intune, která umožňuje chránit prostředky organizace. V Intune můžete vytvářet pravidla a nastavení, která musejí zařízení dodržovat, aby vyhovovala. Může jít třeba o délku hesla. Pokud zařízení nevyhovuje, můžete [podmíněným přístupem](conditional-access.md) zablokovat přístup k datům a prostředkům. 

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

- **Zařízení s rootem:** Pokud chcete všechna zařízení s rootem (jailbreakem) označit jako nevyhovující, zvolte **Blokovat**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Vyžadovat, aby zařízení bylo na určité úrovni hrozby pro zařízení nebo pod ní**: Toto nastavení použijte, pokud chcete jako podmínku dodržování předpisů použít vyhodnocování rizika z řešení Lookout MTP. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. Pokud chcete nastavení použít, zvolte povolenou úroveň ohrožení:
  - **Zabezpečeno**: Tato možnost je nejbezpečnější a znamená, že na zařízení nesmí být žádné hrozby. Pokud jsou na zařízení zjištěny hrozby jakékoli úrovně, vyhodnotí se jako nevyhovující.
  - **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází i jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud se u zařízení zjistí vysoká míra ohrožení, vyhodnotí se jako nevyhovující.
  - **Vysoká**: Tato možnost je nejméně bezpečná, protože umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.
- **Aplikace Služby Google Play je nakonfigurovaná:** **Vyžaduje**, aby aplikace Služby Google Play byla nainstalovaná a povolená. Aplikace Služby Google Play umožňuje instalaci aktualizací zabezpečení a je základní závislostí pro mnoho funkcí zabezpečení na zařízeních s certifikací Google. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Aktualizovaný poskytovatel zabezpečení:** **Vyžaduje**, aby aktualizovaný poskytovatel zabezpečení chránil zařízení před známými hrozbami. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Ověření zařízení SafetyNet**: Zadejte úroveň [ověření SafetyNet](https://developer.android.com/training/safetynet/attestation.html), které musí zařízení dosáhnout. Možnosti:
  - **Nenakonfigurováno** (výchozí): U nastavení se nevyhodnocuje, jestli zařízení vyhovuje.
  - **Zkontrolovat základní integritu**
  - **Zkontrolovat základní integritu a certifikovaná zařízení**

#### <a name="threat-scan-on-apps"></a>Kontrola ohrožení aplikací

Na zařízeních s Androidem Enterprise je nastavení **Kontrola ohrožení aplikací** konfigurovatelná zásada. Další informace viz [Nastavení omezení pro zařízení s Androidem](device-restrictions-android-for-work.md).

## <a name="device-properties-settings"></a>Nastavení vlastností zařízení

- **Minimální verze OS**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, označí se jako nekompatibilní. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může zařízení upgradovat. Potom bude mít přístup k prostředkům společnosti.
- **Maximální verze OS**: Pokud zařízení používá verzi operačního systému, která je novější než verze v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud se nezmění pravidlo, aby tuto verzi operačního systému povolovalo, nebude mít zařízení přístup k prostředkům společnosti.

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Minimální délka hesla:** Zadejte minimální počet číslic nebo znaků, které musí mít heslo uživatele.
- **Požadovaný typ hesla:** Zvolte, jestli se má heslo obsahovat jenom číslice nebo kombinaci číslic s jinými znaky. Možnosti:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Aspoň číselné** (výchozí)
  - **Číselné komplexní**
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**

- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.
- **Konec platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která se nesmí použít znovu**: Zadejte počet dřívějších hesel, která se nesmí znovu použít. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.

### <a name="encryption"></a>Šifrování

- **Šifrování datového úložiště na zařízení:** Pokud chcete, aby zařízení měla šifrované datové úložiště, zvolte **Vyžadovat**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje. 

  Toto nastavení nemusíte konfigurovat, protože zařízení s pracovním profilem Androidu šifrování vyžadují.

### <a name="device-security"></a>Zabezpečení zařízení

- **Blokovat aplikace z neznámých zdrojů:** Zvolte, že chcete **blokovat** zařízení s povolenými zdroji Zabezpečení > Neznámé zdroje (podporované v Androidu 4.0 – Android 7.x, nepodporované v Androidu 8.0 a novějších verzích). Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Pokud chcete instalovat aplikace bokem, musí být povoleny neznámé zdroje. Pokud aplikace pro Android neinstalujete bokem, nastavte tuto funkci na **Blokovat**, abyste tuto zásadu dodržování předpisů povolili. 

  > [!IMPORTANT]
  > Aplikace instalované bokem vyžadují, aby bylo povolené nastavení **Blokovat aplikace z neznámých zdrojů**. Na dodržení této zásady trvejte jenom v případě, že na zařízeních neprovádíte instalaci aplikací pro Android bokem.

  Toto nastavení nemusíte konfigurovat, protože v zařízeních s pracovním profilem Androidu je instalace z neznámých zdrojů zakázaná vždy.

- **Integrita modulu runtime aplikace Portál společnosti:** Pokud chcete potvrdit, že aplikace Portál společnosti splňuje všechny následující požadavky, zvolte **Vyžadovat**:

  - Má nainstalované výchozí prostředí modulu runtime.
  - Je řádně podepsaná.
  - Není v režimu ladění.
  - Je nainstalovaná ze známého zdroje.

  Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

- **Blokovat u zařízení ladění USB:** Pokud chcete zařízením zabránit v použití funkce ladění USB, zvolte **Blokovat**. Pokud zvolíte **Nenakonfigurováno** (výchozí), nebude se u tohoto nastavení vyhodnocovat, jestli zařízení vyhovuje.

  Toto nastavení nemusíte konfigurovat, protože v zařízeních s pracovním profilem Androidu je ladění USB zakázané.

- **Minimální úroveň opravy zabezpečení**: Vyberte nejstarší úroveň opravy zabezpečení, kterou může zařízení mít. Zařízení, která nemají aspoň tuto úroveň opravy, nevyhovují. Datum musí být zadáno ve formátu *RRRR-MM-DD*.

Až to budete mít, uložte změny volbou **OK** > **OK**.

## <a name="actions-for-noncompliance"></a>Akce při nedodržení předpisů

Vyberte **Akce při nedodržení předpisů**. Výchozí akce okamžitě označí zařízení jako nedodržující předpisy.

Pokud je zařízení označené jako nevyhovující, můžete plán třeba další den změnit. Můžete také nakonfigurovat druhou akci, která uživateli nevyhovujícího zařízení pošle e-mail.

Další informace, včetně návodu na vytvoření e-mailu s oznámením pro uživatele, najdete v článku o [přidání akcí pro nevyhovující zařízení](actions-for-noncompliance.md).

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
[Nastavení zásad dodržování předpisů pro Android](compliance-policy-create-android.md)