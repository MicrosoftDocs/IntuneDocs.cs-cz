---
title: Vytvoření zásad dodržování předpisů pro zařízení s Androidem v Microsoft Intune – Azure | Microsoft Docs
description: Vytvářejte nebo konfigurujte zásady dodržování předpisů zařízením služby Microsoft Intune pro zařízení s Androidem. Rozhodněte se povolit zařízení s jailbreakem, nastavte přijatelnou úroveň hrozby, zkontrolujte Google Play, zadejte minimální a maximální verzi operačního systému, zvolte si požadavky na heslo a povolte bokem instalované aplikace.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e1258fe4-0b5c-4485-8bd1-152090df6345
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 559fd83d83c7312e0efe0d2c3f6bb7e5ec596a1b
ms.sourcegitcommit: 6a9830de768dd97a0e95b366fd5d2f93980cee05
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/10/2018
---
# <a name="add-a-device-compliance-policy-for-android-devices-in-intune"></a>Přidání zásad dodržování předpisů pro zařízení s Androidem v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zásada dodržování předpisů Intune pro zařízení s Androidem určuje pravidla a nastavení, které musí zařízení s Androidem splňovat, aby bylo považováno za dodržující předpisy. Pomocí těchto zásad s podmíněným přístupem můžete povolit nebo zablokovat přístup k prostředkům společnosti. Můžete také získat sestavy zařízení a provádět akce v případě nedodržování předpisů. Zásady dodržování předpisů zařízení pro každou platformu vytvoříte na portálu Intune Azure. Další informace o zásadách dodržování předpisů a případných požadavcích najdete v tématu [Začínáme s dodržováním předpisů](device-compliance-get-started.md).

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

**Opravené** = operační systém zařízení vynucuje dodržování předpisů. (Uživatel musí třeba zadat kód PIN.)

**V karanténě** = operační systém zařízení nevynucuje dodržování předpisů. (Například zařízení s Androidem nenutí uživatele šifrovat zařízení.) Pokud zařízení nesplňuje předpisy, provedou se následující akce:

- Zařízení se zablokuje, pokud se zásady podmíněného přístupu vztahují na uživatele.
- Portál společnosti oznamuje uživateli všechny problémy s dodržováním předpisů.

## <a name="create-a-device-compliance-policy"></a>Vytváření zásad dodržování předpisů pro zařízení

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. U možnosti **Platforma** vyberte **Android**. Zvolte **Nastavení – Konfigurace** a zadejte nastavení **Stav zařízení**, **Vlastnosti zařízení** a **Zabezpečení systému**. Po dokončení zvolte **OK** a **Vytvořit**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant based on the configured settings in this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **OK** when you are finished creating all the actions.--->

<!---##  Compliance policy settings--->

## <a name="device-health"></a>Device health

- **Zařízení s rootem**: Pokud toto nastavení povolíte, zařízení s jailbreakem se budou považovat za zařízení nedodržující předpisy.
- **Vyžadovat, aby zařízení bylo na určité úrovni hrozby pro zařízení nebo pod ní**: Toto nastavení použijte, pokud chcete jako podmínku dodržování předpisů použít vyhodnocování rizika z řešení Lookout MTP. Vyberte maximální povolenou úroveň hrozby:
  - **Zabezpečeno**: Tato možnost je nejbezpečnější, protože zařízení nesmí být nijak ohroženo. Pokud se v zařízení zjistí libovolná úroveň hrozeb, vyhodnotí se jako nedodržující předpisy.
  - **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází i jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení se vyhodnotí jako vyhovující, pokud se existující hrozby pohybují na střední nebo nízké úrovni. Pokud se zjistí, že zařízení má i hrozby vysoké úrovně, bude vyhodnoceno jako nedodržující předpisy.
  - **Vysoká**: Tato možnost je nejméně bezpečná a umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.
- **Aplikace Služby Google Play je nakonfigurovaná**: Vyžaduje, aby byla nainstalovaná a povolená aplikace Služby Google Play. Aplikace Služby Google Play umožňuje instalaci aktualizací zabezpečení a je základní závislostí pro mnoho funkcí zabezpečení na zařízeních s certifikací Google.
- **Aktualizovaný poskytovatel zabezpečení**: Vyžaduje, aby aktualizovaný poskytovatel zabezpečení chránil zařízení před známými chybami zabezpečení.
- **Kontrola ohrožení aplikací**: Vyžaduje, aby byla povolená funkce Androidu **Ověřovat aplikace**.

  > [!NOTE]
  > Na starších verzích platformy Android tato funkce představuje nastavení dodržování předpisů. Intune může jenom zkontrolovat, jestli je toto nastavení povolené na úrovni zařízení. Na zařízeních s pracovními profily (Android for Work) je toto nastavení dostupné jako nastavení zásad konfigurace. To správcům umožňuje povolit nastavení pro zařízení.

  Pokud vaše společnost používá pracovní profily Androidu, můžete nastavení **Kontrola ohrožení aplikací** povolit pro zaregistrovaná zařízení. Vytvořte profil zařízení a vyžadujte v něm toto nastavení zabezpečení systému. Další informace najdete v článku [Nastavení omezení pro zařízení s Androidem for Work v Intune](device-restrictions-android-for-work.md).

- **Ověření zařízení SafetyNet**: Zadejte úroveň [ověření SafetyNet](https://developer.android.com/training/safetynet/attestation.html), které musí zařízení dosáhnout. Možnosti:
  - **Není nakonfigurováno**
  - **Zkontrolovat základní integritu**
  - **Zkontrolovat základní integritu a certifikovaná zařízení**

## <a name="device-property-settings"></a>Nastavení vlastností zařízení

- **Minimální verze OS**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, označí se jako nekompatibilní. Zobrazí se odkaz s informacemi, jak upgradovat. Koncový uživatel si může zařízení upgradovat. Potom získá přístup k prostředkům společnosti.
- **Maximální verze OS**: Pokud zařízení používá verzi operačního systému, která je novější než verze specifikovaná v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nebude mít toto zařízení přístup k prostředkům společnosti.

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Požadovaný typ hesla**: Zvolte, jestli má heslo obsahovat pouze číselné znaky nebo jestli má obsahovat kombinaci čísel a dalších znaků. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Aspoň číslice**
  - **Číselné komplexní**: Opakující se nebo po sobě jdoucí čísla (jako jsou 1111 nebo 1234) nejsou povolena.
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla.
- **Vypršení platnosti hesla (dny):** Zvolte počet dní, za který heslo vyprší a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která se nesmí použít znovu**: Zadejte počet dřívějších hesel, která se nesmí znovu použít. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.

### <a name="encryption"></a>Šifrování

- **Šifrování úložiště dat na zařízení** (Android 4.0 a vyšší nebo KNOX 4.0 a vyšší): Vyberte **Vyžadovat** a zašifrujte úložiště dat na vašich zařízeních. Zařízení se šifrují, pokud vyberete nastavení **Vyžadovat heslo k odemknutí mobilních zařízení**.

### <a name="device-security"></a>Zabezpečení zařízení

- **Blokovat aplikace z neznámých zdrojů**: Rozhodněte se blokovat zařízení s povoleným zdroji v Zabezpečení > Neznámé zdroje (Android 4.0 až Android 7.x, nepodporuje se Androidem 8.0 a novějším.). Pokud chcete instalovat aplikace bokem, musí být povoleny neznámé zdroje. Pokud neprovádíte instalaci aplikací pro Android bokem, potom tuto zásadu dodržování předpisů povolte.

  > [!IMPORTANT]
  > Aplikace instalované bokem vyžadují, aby bylo povolené nastavení **Blokovat aplikace z neznámých zdrojů**. Tuto zásadu dodržování předpisů vynuťte jenom v případě, že na zařízeních neprovádíte instalaci aplikací pro Android bokem.

- **Integrita modulu runtime aplikace Portál společnosti**: Zkontroluje, jestli má aplikace Portál společnosti nainstalované výchozí prostředí modulu runtime, je správně podepsaná, není v režimu ladění a je nainstalovaná ze známého zdroje.
- **Blokovat u zařízení ladění USB** (Android 4.2 nebo novější): Vyberte, pokud chcete zabránit tomu, aby zařízení používala funkci ladění USB.
- **Minimální úroveň opravy zabezpečení** (Android 6.0 nebo novější): Vyberte nejstarší úroveň opravy zabezpečení, kterou může zařízení mít. Zařízení, která nejsou alespoň na této úrovni oprav, nebudou kompatibilní. Datum musí být zadáno ve formátu `YYYY-MM-DD`.

## <a name="assign-user-groups"></a>Přiřazení skupin uživatelů

1. Vyberte zásadu, kterou jste nakonfigurovali. Existující zásady najdete v **Dodržování předpisů zařízením** > **Zásady**.
2. Zvolte zásady a pak **Přiřazení**. Můžete zahrnout nebo vyloučit skupiny zabezpečení služby Azure Active Directory (AD).
3. Vyberte **Vybrané skupiny** a zobrazte skupiny zabezpečení Azure AD. Můžete vybrat skupiny uživatelů, na které chcete zásady použít, a pak pomocí **Uložit** tyto zásady uživatelům nasadit.

Tím jste zásady uplatnili u uživatelů. U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů.

## <a name="next-steps"></a>Další kroky
[Automatické e-maily a přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md)  
[Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md)
