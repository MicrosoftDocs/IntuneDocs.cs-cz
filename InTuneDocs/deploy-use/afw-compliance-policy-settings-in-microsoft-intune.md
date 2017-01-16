---
title: "Nastavení zásad dodržování předpisů pro zařízení s Androidem for Work | Dokumentace Microsoftu"
description: "Toto téma popisuje nastavení zásad dodržování předpisů pro zařízení s Androidem, která jsou kompatibilní s Androidem for Work."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/13/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2b53e7a410d0ce268ce395c08161095af42857b7


---


# <a name="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune"></a>Nastavení zásad dodržování předpisů pro zařízení s Androidem for Work v Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Nastavení zásad popsaná v tomto tématu platí pro zařízení s Androidem for Work.

Pokud hledáte informace o jiných platformách, vyberte jednu z těchto možností:
> [!div class="op_single_selector"]
- [Nastavení zásad dodržování předpisů pro Android](android-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro zařízení s iOSem](ios-compliance-policy-settings-in-microsoft-intune.md)
- [Nastavení zásad dodržování předpisů pro zařízení s Windows](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a>Systémové nastavení zabezpečení
### <a name="password"></a>Heslo
- **Vyžadovat heslo k odemknutí mobilních zařízení:** Pokud tuto možnost nastavíte na **Ano**, budou muset uživatelé zadat heslo, aby mohli získat přístup ke svému zařízení.

-  **Minimální délka hesla:** Určuje minimální počet číslic nebo znaků, které musí heslo uživatele obsahovat.

- **Kvalita hesla:** Toto nastavení rozpozná, jestli jsou na zařízení nakonfigurované požadavky na heslo, které jste zadali. Toto nastavení povolte, pokud uživatelé musí pro zařízení s Androidem nakonfigurovat určité požadavky na heslo. Vybírejte z těchto možností:
  -   **Biometrika s nízkým zabezpečením**
  - **Požadováno**
  -   **Aspoň číslice**
  -   **Aspoň abecední znaky**
  -   **Aspoň alfanumerické znaky**
  -   **Alfanumerické znaky se symboly**

- **Počet minut nečinnosti, než se požaduje heslo:** Určuje dobu nečinnosti, než uživatel musí znovu zadat heslo.

- **Vypršení platnosti hesla (dny):** Zvolte počet dní, za který uživatelské heslo vyprší a uživatel bude muset vytvořit nové.

- **Pamatovat si historii hesel:** Pokud chcete zabránit uživatelům ve vytváření hesel, která používali dřív, použijte toto nastavení spolu s nastavením **Zakázat opakované použití předchozích hesel**.

- **Zakázat opakované použití předchozích hesel:** Pokud je zvolená možnost **Pamatovat si historii hesel**, zadejte počet předchozích hesel, která se nesmí znovu použít.

- **Po návratu zařízení ze stavu nečinnosti vyžadovat heslo:** Toto nastavení by se mělo použít v kombinaci s nastavením **Počet minut nečinnosti před vyžádáním hesla**. Pro přístup k zařízení, které bylo nečinné po dobu uvedenou v nastavení **Počet minut nečinnosti před vyžádáním hesla**, se koncovým uživatelům zobrazí výzva k zadání hesla.

### <a name="encryption"></a>Encryption
- **Vyžadovat šifrování u mobilního zařízení:** Toto nastavení nemusíte konfigurovat, protože u zařízení s Androidem for Work je šifrování vynucené.

## <a name="device-health-and-security-settings"></a>Stav zařízení a nastavení zabezpečení

- **Zařízení nesmí mít jailbreak ani root:** Pokud povolíte toto nastavení, budou se zařízení s jailbreakem považovat za nevyhovující předpisům.
- **Požadovat, aby zařízení bránila instalaci aplikací z neznámých zdrojů:** Toto nastavení nemusíte konfigurovat, protože v zařízeních s Androidem for Work je instalace z neznámých zdrojů trvale zakázaná. .  

- **Požadovat, aby ladění USB bylo zakázané:** Toto nastavení nemusíte konfigurovat, protože ladění USB je na zařízeních s Androidem for Work už zakázané.

- **Minimální úroveň oprav zabezpečení Androidu:** Toto nastavení použijte k určení minimální úrovně oprav Androidu.  Zařízení, která nejsou alespoň na této úrovni oprav, budou kompatibilní. Datum musí být zadáno ve formátu RRRR-MM-DD.
- **Vyžadovat, aby byla povolena Ochrana zařízení před internetovými útoky**: Toto nastavení použijte, pokud chcete jako podmínku dodržování předpisů použít vyhodnocování rizika z řešení Lookout MTP. Vyberte jednu z následujících úrovní hrozeb jako maximální povolenou:

  - **Žádná (zabezpečeno):** Toto je nejbezpečnější úroveň. Znamená, že zařízení nesmí obsahovat žádné hrozby. Pokud se v zařízení zjistí libovolná úroveň hrozeb, bude vyhodnoceno jako nedodržující předpisy.
  - **Nízká:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm nachází jen nízká úroveň hrozeb. Jakákoliv vyšší úroveň zařízení zařadí do stavu nedodržující předpisy.
  - **Střední:** Zařízení je vyhodnoceno jako vyhovující, pokud se v něm přítomné hrozby pohybují na střední nebo nízké úrovni. Pokud se zjistí, že zařízení má i hrozby vysoké úrovně, bude vyhodnoceno jako nedodržující předpisy.
  - **Vysoká:** Jedná se o nejméně bezpečnou možnost. V podstatě povoluje všechny úrovně hrozeb. Toto řešení může být užitečné prakticky jen pro účely nahlašování.

  Další podrobnosti najdete v tématu [Povolení pravidla ochrany zařízení před hrozbami v zásadách dodržování předpisů](enable-device-threat-protection-rule-in-compliance-policy.md).

## <a name="device-property-settings"></a>Nastavení vlastností zařízení
- **Minimální požadovaný operační systém:** Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, uvede se jako nekompatibilní.
  Zobrazí se odkaz s informacemi o postupu upgradu. Koncový uživatel si může zařízení upgradovat. Potom bude mít přístup k prostředkům společnosti.

- **Maximální povolená verze operačního systému:** Pokud zařízení používá verzi operačního systému, která je novější než verze zadaná v pravidle, bude přístup k prostředkům společnosti blokovaný a uživateli se zobrazí výzva, aby kontaktoval správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.



<!--HONumber=Dec16_HO2-->


