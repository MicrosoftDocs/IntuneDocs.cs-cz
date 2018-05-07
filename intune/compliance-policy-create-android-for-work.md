---
title: Vytvoření zásad dodržování předpisů pro Android for Work v Microsoft Intune – Azure | Microsoft Docs
description: Vytvářejte nebo konfigurujte zásady dodržování předpisů zařízením služby Microsoft Intune pro zařízení s Androidem for Work. Rozhodněte se povolit zařízení s jailbreakem, nastavte přijatelnou úroveň hrozby, zkontrolujte Google Play, zadejte minimální a maximální verzi operačního systému, zvolte si požadavky na heslo a povolte bokem instalované aplikace.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/16/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 74fe0897764957e84e5a13944305221cc85bd8c7
ms.sourcegitcommit: 2773f388f50654366197a95a6838306f70fc18b8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="add-a-device-compliance-policy-for-android-for-work-devices-in-intune"></a>Přidání zásad dodržování předpisů pro zařízení s Androidem for Work v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zásady dodržování předpisů Intune pro zařízení s Androidem for Work určují pravidla a nastavení, která musí tato zařízení splňovat, aby byla považována za dodržující předpisy. Pomocí těchto zásad s podmíněným přístupem můžete povolit nebo zablokovat přístup k prostředkům společnosti. Můžete také získat sestavy zařízení a provádět akce v případě nedodržování předpisů. Zásady dodržování předpisů zařízením pro různé platformy vytvoříte na portálu Intune Azure. Další informace o zásadách dodržování předpisů a případných požadavcích najdete v tématu [Začínáme s dodržováním předpisů](device-compliance-get-started.md).

Následující tabulka popisuje, jak jsou spravované nevyhovující nastavení při použití zásad dodržování předpisů se zásadami podmíněného přístupu.

--------------------------

|**nastavení zásad**| **Android for Work** |
| --- | --- |
| **Konfigurace kódu PIN nebo hesla** |  V karanténě |
| **Šifrování zařízení** |  V karanténě |
| **Zařízení s jailbreakem nebo rootem** | V karanténě (není nastavení) |
| **e-mailový profil** | Nelze použít |
| **Minimální verze operačního systému** | V karanténě |
| **Maximální verze operačního systému** | V karanténě |
| **Ověření stavu Windows** |Nelze použít |

**Opravené** = operační systém zařízení vynucuje dodržování předpisů. (Uživatel musí třeba zadat PIN.)

**V karanténě** = operační systém zařízení nevynucuje dodržování předpisů. (Například zařízení s Androidem nenutí uživatele šifrovat zařízení.) Pokud zařízení nesplňuje předpisy, provedou se následující akce:

- Pokud se zásady podmíněného přístupu vztahují na uživatele, zařízení se zablokuje.
- Portál společnosti oznamuje uživateli všechny problémy s dodržováním předpisů.

## <a name="create-a-device-compliance-policy"></a>Vytváření zásad dodržování předpisů pro zařízení

[!INCLUDE [new-device-compliance-policy](./includes/new-device-compliance-policy.md)]
5. U možnosti **Platforma** vyberte **Android for Work**. Zvolte **Nastavení – Konfigurace** a zadejte nastavení **Stav zařízení**, **Vlastnosti zařízení** a **Zabezpečení systému**. Po dokončení zvolte **OK** a **Vytvořit**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="device-health"></a>Device health

- **Zařízení s rootem**: Pokud toto nastavení povolíte, zařízení s jailbreakem se budou považovat za zařízení nedodržující předpisy.
- **Vyžadovat, aby zařízení bylo na určité úrovni hrozby pro zařízení nebo pod ní**: Toto nastavení použijte, pokud chcete jako podmínku dodržování předpisů použít vyhodnocování rizika z řešení Lookout MTP. Vyberte maximální povolenou úroveň hrozby:
  - **Zabezpečeno**: Tato možnost je nejbezpečnější a znamená, že zařízení nesmí být nijak ohroženo. Pokud se v zařízení zjistí libovolná úroveň hrozeb, vyhodnotí se jako nedodržující předpisy.
  - **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází i jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud se zjistí, že zařízení má i hrozby vysoké úrovně, bude vyhodnoceno jako nedodržující předpisy.
  - **Vysoká**: Tato možnost je nejméně bezpečná, protože umožňuje všechny úrovně hrozeb. Může být užitečná, pokud toto řešení používáte jen ke generování sestav.
- **Aplikace Služby Google Play je nakonfigurovaná**: Vyžaduje, aby byla nainstalovaná a povolená aplikace Služby Google Play. Aplikace Služby Google Play umožňuje instalaci aktualizací zabezpečení a je základní závislostí pro mnoho funkcí zabezpečení na zařízeních s certifikací Google.
- **Aktualizovaný poskytovatel zabezpečení**: Vyžaduje, aby aktualizovaný poskytovatel zabezpečení chránil zařízení před známými chybami zabezpečení.
- **Ověření zařízení SafetyNet**: Zadejte úroveň [ověření SafetyNet](https://developer.android.com/training/safetynet/attestation.html), které musí zařízení dosáhnout. Možnosti:
  - **Není nakonfigurováno**
  - **Zkontrolovat základní integritu**
  - **Zkontrolovat základní integritu a certifikovaná zařízení**

#### <a name="threat-scan-on-apps"></a>Kontrola ohrožení aplikací

Na zařízeních s pracovními profily (Android for Work) je nastavení **Kontrola ohrožení aplikací** dostupné jako nastavení zásad konfigurace. Správci mohou povolit toto nastavení pro zařízení.

Pokud vaše společnost používá pracovní profily Androidu, můžete nastavení **Kontrola ohrožení aplikací** povolit pro zaregistrovaná zařízení. Vytvořte profil zařízení a vyžadujte v něm toto nastavení zabezpečení systému. Další informace najdete v článku [Nastavení omezení pro zařízení s Androidem for Work v Intune](device-restrictions-android-for-work.md).

## <a name="device-property-settings"></a>Nastavení vlastností zařízení

- **Minimální verze OS**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, označí se jako nekompatibilní. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může zařízení upgradovat. Potom bude mít přístup k prostředkům společnosti.
- **Maximální verze OS**: Pokud zařízení používá verzi operačního systému, která je novější než verze v pravidle, bude přístup k prostředkům společnosti blokovaný. Uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nebude mít zařízení přístup k prostředkům společnosti.

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení**: **Vyžadujte**, aby uživatelé před získáním přístupu ke svému zařízení zadali heslo.
- **Minimální délka hesla**: Zadejte minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.
- **Požadovaný typ hesla**: Zvolte, jestli má heslo obsahovat pouze číselné znaky, nebo jestli má obsahovat kombinaci čísel a dalších znaků. Vybírejte z těchto možností:
  - **Výchozí ze zařízení**
  - **Biometrika s nízkým zabezpečením**
  - **Aspoň číslice**
  - **Číselné komplexní**
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Aspoň alfanumerické se symboly**
- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo**: Zadejte dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla.
- **Konec platnosti hesla (dny)**: Vyberte počet dní, za který skončí platnost hesla a uživatel bude muset vytvořit nové.
- **Počet předchozích hesel, která se nesmí použít znovu**: Zadejte počet dřívějších hesel, která se nesmí znovu použít. Toto nastavení použijte, pokud chcete uživateli zabránit ve vytváření hesel, která používal dříve.

### <a name="encryption"></a>Šifrování

- **Vyžadovat šifrování u mobilního zařízení:** Toto nastavení nemusíte konfigurovat, protože u zařízení s Androidem for Work je šifrování vynucené.

### <a name="device-security"></a>Zabezpečení zařízení

- **Blokovat aplikace z neznámých zdrojů:** Toto nastavení nemusíte konfigurovat, protože v zařízeních s Androidem for Work je instalace z neznámých zdrojů trvale zakázaná.
- **Integrita modulu runtime aplikace Portál společnosti**: Zkontroluje, jestli má aplikace Portál společnosti nainstalované výchozí prostředí modulu runtime, je správně podepsaná, není v režimu ladění a je nainstalovaná ze známého zdroje.
- **Blokovat u zařízení ladění USB**: Toto nastavení nemusíte konfigurovat, protože ladění USB je na zařízeních s Androidem for Work už zakázané.
- **Minimální úroveň opravy zabezpečení**: Vyberte nejstarší úroveň opravy zabezpečení, kterou může zařízení mít. Zařízení, která nejsou alespoň na této úrovni oprav, nebudou kompatibilní. Datum musí být zadáno ve formátu `YYYY-MM-DD`.

## <a name="assign-user-groups"></a>Přiřazení skupin uživatelů

1. Vyberte zásadu, kterou jste nakonfigurovali. Existující zásady najdete v **Dodržování předpisů zařízením** > **Zásady**.
2. Zvolte zásady a pak **Přiřazení**. Můžete zahrnout nebo vyloučit skupiny zabezpečení služby Azure Active Directory (AD).
3. Vyberte **Vybrané skupiny** a zobrazte skupiny zabezpečení Azure AD. Můžete vybrat skupiny uživatelů, na které chcete zásady použít, a pak pomocí **Uložit** tyto zásady uživatelům nasadit.

Tím jste zásady uplatnili u uživatelů. U zařízení používaných uživateli, na které zásady cílí, se vyhodnotí dodržování předpisů.

## <a name="next-steps"></a>Další kroky
[Automatické e-maily a přidání akcí pro zařízení nedodržující předpisy](actions-for-noncompliance.md)  
[Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md)