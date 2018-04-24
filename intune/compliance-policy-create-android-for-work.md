---
title: Vytvoření zásad dodržování předpisů pro Android for Work
titleSuffix: Microsoft Intune
description: Vytvořte v Intune zásadu dodržování předpisů zařízením pro zařízení s Androidem for Work umožňující vám zadat požadavky, které zařízení musí splnit, aby vyhovovalo předpisům.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9da89713-6306-4468-b211-57cfb4b51cc6
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 00fa4508cdd4e74a20205ce46025b414cc0bb4cf
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-device-compliance-policy-for-android-for-work-devices-in-intune"></a>Vytvoření zásad dodržování předpisů pro zařízení s Androidem for Work v Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zásada dodržování předpisů Intune pro zařízení s Androidem for Work určuje pravidla a nastavení, které musí zařízení s Androidem for Work splňovat, aby bylo považováno za dodržující předpisy. Tyto zásady můžete použít s podmíněným přístupem k povolení nebo zablokování přístupu k prostředkům společnosti. Můžete také získat sestavy zařízení a provádět kroky v případě, že zařízení předpisy nedodržuje. Zásady dodržování předpisů zařízení pro každou platformu vytvoříte na portálu Intune Azure. Další informace o zásadách dodržování předpisů a požadavcích, kterým před vytvořením zásad dodržování předpisů musíte vyhovět, najdete v tématu [Začínáme se zásadami dodržování předpisů zařízeními](device-compliance-get-started.md).

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

## <a name="create-a-compliance-policy-in-the-azure-portal"></a>Vytvoření zásad dodržování předpisů na portálu Azure Portal

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
1. V podokně **Intune** zvolte  **Dodržování předpisů zařízením**. Pod **Spravovat** vyberte **Zásady** a zvolte **Vytvořit zásadu**.
2. Zadejte název a popis a zvolte platformu, u které chcete použít tyto zásady.
3. Zvolte **Nastavení – Konfigurace** a zadejte nastavení **Zabezpečení systému**, **Stav zařízení** a **Vlastnosti zařízení**. Když jste hotovi, klikněte na **OK**.

<!--- 4. Choose **Actions for noncompliance** to say what actions should happen when a device is determined as noncompliant with this policy.
5. In the **Actions for noncompliance** pane, choose **Add** to create a new action.  The action parameters pane allows you to specify the action, email recipients that should receive the notification in addition to the user of the device, and the content of the notification that you want to send.
6. The message template option allows you to create several custom emails depending on when the action is set to take. For example, you can create a message for notifications that are sent for the first time and a different message for final warning before access is blocked. The custom messages that you create can be used for all your device compliance policy.
7. Specify the **Grace period** which determines when that action to take place.  For example, you may want to send a notification as soon as the device is evaluated as noncompliant, but allow some time before enforcing the conditional access policy to block access to company resources like SharePoint online.
8. Choose **Add** to finish creating the action.
9. You can create multiple actions and the sequence in which they should occur. Choose **Ok** when you are finished creating all the actions.--->

## <a name="assign-user-groups"></a>Přiřazení skupin uživatelů

Pokud chcete přiřadit zásady dodržování předpisů uživatelům, vyberte zásady, které jste nakonfigurovali. Existující zásady najdete v podokně **Dodržování předpisů zařízením – Zásady**.

1. Vyberte zásady, které chcete přiřadit uživatelům, a zvolte **Přiřazení**. Otevře se podokno, kde můžete vybrat **skupiny zabezpečení Azure Active Directory** a přiřadit je k zásadám.
2. Zvolte **Vybrat skupiny** a otevřete tak podokno, kde se zobrazí skupiny zabezpečení v Azure AD.  Pomocí **Uložit** se zásada nasadí uživatelům.

Tím jste zásady uplatnili u uživatelů.  U zařízení používaných uživateli, kteří jsou cílem zásad, se bude vyhodnocovat dodržování předpisů.

<!--- ##  Compliance policy settings--->

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení

### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení:** Pokud tuto možnost nastavíte na **Ano**, budou muset uživatelé zadat heslo, aby mohli získat přístup ke svému zařízení.
- **Minimální délka hesla:** Zadejte minimální počet číslic nebo znaků, které musí heslo obsahovat.
- **Kvalita hesla:** Toto nastavení rozpozná, jestli jsou na zařízení nakonfigurované požadavky na heslo, které jste zadali. Toto nastavení povolte, pokud uživatelé musí pro zařízení s Androidem nakonfigurovat určité požadavky na heslo. Vybírejte z těchto možností:
  - **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  - **Aspoň číslice**
  - **Aspoň abecední znaky**
  - **Aspoň alfanumerické znaky**
  - **Alfanumerické znaky se symboly**
- **Počet minut nečinnosti před vyžádáním hesla:** Určuje dobu nečinnosti, než bude muset uživatel znovu zadat heslo.
- **Konec platnosti hesla (dny):** Vyberte počet dní, za který skončí platnost uživatelského hesla a uživatel bude muset vytvořit nové.
- **Pamatovat si historii hesel**: Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.
- **Zakázat opakované použití předchozích hesel:** Pokud je zvolená možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.
- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo:** Toto nastavení by se mělo použít s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Pro přístup k zařízení, které bylo nečinné po dobu uvedenou v nastavení **Počet minut nečinnosti před vyžádáním hesla**, se koncovým uživatelům zobrazí výzva k zadání hesla.


### <a name="encryption"></a>Šifrování

- **Vyžadovat šifrování u mobilního zařízení:** Toto nastavení nemusíte konfigurovat, protože u zařízení s Androidem for Work je šifrování vynucené.


## <a name="device-health-and-security-settings"></a>Stav zařízení a nastavení zabezpečení

- **Zařízení nesmí mít jailbreak ani root:** Pokud povolíte toto nastavení, budou se zařízení s jailbreakem považovat za nedodržující předpisy.
- **Požadovat, aby zařízení bránila instalaci aplikací z neznámých zdrojů:** Toto nastavení nemusíte konfigurovat, protože v zařízeních s Androidem for Work je instalace z neznámých zdrojů trvale zakázaná.
- **Požadovat, aby ladění USB bylo zakázané:** Toto nastavení nemusíte konfigurovat, protože ladění USB je na zařízeních s Androidem for Work už zakázané.
- **Minimální úroveň oprav zabezpečení Androidu:** Toto nastavení použijte k určení minimální úrovně oprav Androidu. Zařízení, která nejsou alespoň na této úrovni oprav, budou kompatibilní. Datum musí být zadáno ve formátu RRRR-MM-DD.
- **Vyžadovat, aby byla povolena Ochrana zařízení před internetovými útoky**: Toto nastavení použijte, pokud chcete jako podmínku dodržování předpisů použít vyhodnocování rizika z řešení Lookout MTP. Vyberte jednu z následujících úrovní hrozeb jako maximální povolenou:
  - **Žádná (zabezpečeno):** Toto je nejbezpečnější úroveň. Znamená, že zařízení nesmí obsahovat žádné hrozby. Pokud se v zařízení zjistí libovolná úroveň hrozeb, vyhodnotí se jako nedodržující předpisy.
  - **Nízká:** Zařízení je vyhodnoceno jako dodržující předpisy, pokud se v něm nacházejí jen hrozby s nízkou úrovní. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední**: Zařízení je vyhodnoceno jako vyhovující, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud se v zařízení zjistí hrozby vysoké úrovně, vyhodnotí se jako nedodržující předpisy.
  - **Vysoká**: Jedná se o nejméně bezpečnou možnost. V podstatě umožňuje všechny úrovně hrozeb. Toto řešení může být užitečné prakticky jen pro účely vykazování.

## <a name="device-property-settings"></a>Nastavení vlastností zařízení

- **Minimální požadovaný operační systém**: Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní. Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může upgradovat svoje zařízení. Potom bude mít přístup k prostředkům společnosti.
- **Maximální povolená verze operačního systému:** Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.

<!--- ## Next steps

[How to monitor device compliance](device-compliance-monitor.md)--->
