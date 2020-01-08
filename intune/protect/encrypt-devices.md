---
title: Šifrovat zařízení pomocí metody šifrování podporované platformou
titleSuffix: Microsoft Intune
description: Zašifrujte zařízení pomocí integrovaných šifrovacích metod, jako je BitLocker nebo trezoru klíčů, a spravujte klíče pro obnovení těchto zašifrovaných zařízení z portálu Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 12/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: annovich
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 26013ab06cabdfd64ec3cd34254e3cfa2bb2428d
ms.sourcegitcommit: 8d7406b75ef0d75cc2ed03b1a5e5f74ff10b98c0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/03/2020
ms.locfileid: "75654256"
---
# <a name="use-device-encryption-with-intune"></a>Použití šifrování zařízení s Intune

Použijte Intune ke správě zařízení integrovaných na disku nebo šifrování jednotky, abyste mohli chránit data na svých zařízeních.

Nakonfigurujte šifrování disku jako součást profilu konfigurace zařízení pro službu Endpoint Protection. Intune podporuje následující platformy a šifrovací technologie:

- macOS: trezor
- Windows 10 a novější: BitLocker

Intune také obsahuje integrovanou [sestavu šifrování](encryption-monitor.md) , která poskytuje podrobné informace o stavu šifrování zařízení ve všech spravovaných zařízeních.

## <a name="filevault-encryption-for-macos"></a>Šifrování trezoru úložiště pro macOS

Pomocí Intune můžete na zařízeních se systémem macOS nakonfigurovat šifrování disků trezoru. Pak pomocí sestavy šifrování Intune zobrazte podrobnosti o šifrování těchto zařízení a spravujte klíče pro obnovení pro zařízení zašifrovaná pomocí trezoru.

Trezor úložišť je program pro šifrování celého disku, který je součástí macOS. Intune můžete použít ke konfiguraci trezoru úložišť na zařízeních, na kterých běží **macOS 10,13 nebo novější**.

Pro konfiguraci trezoru úložišť vytvořte [profil konfigurace zařízení](../configuration/device-profile-create.md) pro službu Endpoint Protection pro platformu MacOS. Nastavení trezoru úložiště je jednou z dostupných kategorií nastavení pro macOS Endpoint Protection.

Když vytvoříte zásadu pro šifrování zařízení pomocí trezoru, zásada se použije na zařízení ve dvou fázích. Nejdřív je zařízení připravené k tomu, aby Intune mohl načíst a zálohovat obnovovací klíč. To se označuje jako v úschově. Po uloží klíče se může šifrování disku spustit.

![Nastavení trezoru úložišť](./media/encrypt-devices/filevault-settings.png)

Podrobnosti o nastavení trezoru klíčů, které můžete spravovat pomocí Intune, najdete v tématu [trezor](endpoint-protection-macos.md#filevault) pro MacOS v článku Intune pro nastavení ochrany koncových bodů.

### <a name="how-to-configure-macos-filevault"></a>Jak nakonfigurovat macOS trezor

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte **zařízení** > **konfiguračních profilech** > **vytvořit profil**.

3. Nastavte následující možnosti:

   - Platforma: macOS
   - Typ profilu: Endpoint Protection

4. Vyberte **nastavení** > **trezoru úložišť**.

5. V případě *trezoru úložišť*vyberte **Povolit**.

6. Pro *typ obnovovacího klíče*se podporuje jenom **osobní klíč** .

   Zvažte přidání zprávy do Průvodce nápovědou koncovým uživatelům, jak získat obnovovací klíč pro své zařízení. Tyto informace mohou být užitečné pro koncové uživatele, když použijete nastavení pro rotaci klíče pro obnovení, což může pravidelně automaticky generovat nový obnovovací klíč pro zařízení.

   Příklad: Chcete-li načíst ztracený nebo nedávno otočený obnovovací klíč, přihlaste se k webu Portál společnosti Intune z libovolného zařízení. Na portálu klikněte na *zařízení* a vyberte zařízení s povoleným trezorem úložiště a pak vyberte *získat obnovovací klíč*. Zobrazí se aktuální obnovovací klíč.

7. Nakonfigurujte zbývající [Nastavení trezoru úložišť](endpoint-protection-macos.md#filevault) tak, aby splňovalo vaše obchodní potřeby, a pak vyberte **OK**.

   > [!IMPORTANT]
   > K dispozici je známý problém, pokud je nastavení **Zakázat příkazový řádek při odhlášení** nastaveno na *Povolit*. Pokud je nastavena hodnota *Povolit*, nastavení pro **počet povolených pokusů o obejití** musí být nastaveno na hodnotu a nesmí být nastaven jako *není nakonfigurováno*. Pokud je nastavené na *Nenakonfigurováno*, profil se v zařízení nezdařil. V tomto scénáři zařízení hlásí **souhrn stavu profilu** jako **chybu** bez dalších podrobností.
   >
   > Pokud je možnost **Zakázat výzvu při odhlášení** nastavena na hodnotu *není nakonfigurováno*, **počet povolených potlačení** nemůže být *nakonfigurován* nebo mít hodnotu.
   >
   > Tento problém opraví budoucí aktualizace.

8. Dokončete konfiguraci dalšího nastavení a potom profil uložte.  

### <a name="manage-filevault"></a>Správa trezoru úložišť

Jakmile Intune zašifruje zařízení macOS s trezorem, můžete zobrazit a spravovat klíče pro obnovení trezoru úložiště, když si zobrazíte [sestavu šifrování](encryption-monitor.md)Intune.

Jakmile Intune zašifruje zařízení macOS s trezorem souborů, můžete si z webu zobrazit jeho osobní obnovovací klíč, který je Portál společnosti na jakémkoli zařízení. Jednou na webu Portál společnosti zvolte šifrované zařízení macOS a pak zvolte možnost "získat klíč pro obnovení" jako akci vzdáleného zařízení.

### <a name="retrieve-personal-recovery-key-from-mem-encrypted-macos-devices"></a>Načtení osobního obnovovacího klíče ze zařízení s macOS šifrovaným zařízením MEM

Koncoví uživatelé budou moci načíst svůj osobní obnovovací klíč (klíč trezoru) pomocí aplikace Portál společnosti pro iOS. Zařízení, které má osobní obnovovací klíč, musí být zaregistrované v Intune a zašifrované pomocí trezoru služby prostřednictvím Intune. Pomocí aplikace Portál společnosti pro iOS může koncový uživatel otevřít webovou stránku, která obsahuje klíč pro osobní obnovení trezoru souborů. Obnovovací klíč můžete z Intune načíst taky tak, že vyberete **zařízení** > *šifrovaných a zaregistrovaných zařízení MacOS* > **získat obnovovací klíč**. 

## <a name="bitlocker-encryption-for-windows-10"></a>Šifrování BitLockeru pro Windows 10

Pomocí Intune můžete nakonfigurovat nástroj BitLocker Drive Encryption na zařízeních s Windows 10. Pak můžete pomocí sestavy šifrování Intune zobrazit podrobnosti o šifrování těchto zařízení. K důležitým informacím z vašich zařízení můžete také přistupovat pomocí nástroje BitLocker, jak se nachází v Azure Active Directory (Azure AD).

BitLocker je k dispozici na zařízeních se **systémem Windows 10 nebo novějším**.

Nakonfigurujte BitLocker při vytváření [profilu konfigurace zařízení](../configuration/device-profile-create.md) pro službu Endpoint Protection pro platformu Windows 10 nebo novější. Nastavení BitLockeru jsou v kategorii nastavení šifrování Windows pro Endpoint Protection pro Windows 10.

![Nastavení BitLockeru](./media/encrypt-devices/bitlocker-settings.png)

### <a name="how-to-configure-windows-10-bitlocker"></a>Jak nakonfigurovat Windows 10 BitLocker

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte **zařízení** > **konfiguračních profilech** > **vytvořit profil**.

3. Nastavte následující možnosti:

   - Platforma: Windows 10 a novější
   - Typ profilu: Endpoint Protection

4. Vyberte **nastavení** > **šifrování Windows**.

5. Nakonfigurujte nastavení BitLockeru tak, aby vyhovovalo vašim obchodním potřebám, a pak vyberte **OK**.

6. Dokončete konfiguraci dalšího nastavení a potom profil uložte.

### <a name="manage-bitlocker"></a>Spravovat nástroj BitLocker

Jakmile Intune zašifruje zařízení s Windows 10 pomocí nástroje BitLocker, můžete zobrazit a načíst klíče pro obnovení nástroje BitLocker při zobrazení [sestavy šifrování](encryption-monitor.md)Intune.

### <a name="rotate-bitlocker-recovery-keys"></a>Otočit obnovovací klíče BitLockeru

Pomocí akce zařízení v Intune můžete vzdáleně otočit obnovovací klíč BitLockeru zařízení se systémem Windows 10 verze 1909 nebo novějším.

#### <a name="prerequisites"></a>Požadované součásti

Zařízení musí splňovat následující požadavky, aby podporovaly rotaci obnovovacího klíče nástroje BitLocker:

- Zařízení musí používat Windows 10 verze 1909 nebo novější.

- Zařízení, která jsou připojená k Azure AD a která jsou připojená hybridem, musí mít podporu pro rotaci klíčů:

  - **Otočení hesla pro obnovení na základě klienta**

  Toto nastavení se nachází v části *šifrování Windows* jako součást zásad konfigurace zařízení pro Windows 10 Endpoint Protection.
  
#### <a name="to-rotate-the-bitlocker-recovery-key"></a>Otočení obnovovacího klíče BitLockeru

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte **Zařízení** > **Všechna zařízení**.

3. V seznamu zařízení, která spravujete, vyberte zařízení, klikněte na **Další**a pak vyberte vzdálenou akci zařízení pro **střídání klíčů nástrojem BitLocker** .

## <a name="next-steps"></a>Další kroky

Vytvořte zásady [dodržování předpisů pro zařízení](compliance-policy-create-windows.md) .

Pomocí sestavy šifrování můžete spravovat:

- [Obnovovací klíče nástroje BitLocker](encryption-monitor.md#bitlocker-recovery-keys)
- [Klíče obnovení trezoru úložišť](encryption-monitor.md#filevault-recovery-keys)

Zkontrolujte nastavení šifrování, která můžete nakonfigurovat pomocí Intune pro:

- [BitLocker](endpoint-protection-windows-10.md#windows-encryption)
- [FileVault](endpoint-protection-macos.md#filevault)
