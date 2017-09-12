---
title: "Nastavení ochrany koncového bodu Intune pro Windows 10"
titlesuffix: Azure portal
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete řídit nastavení ochrany koncového bodu, jako je BitLocker, na zařízeních s Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6c8e9d6b63557a5c73ff027d9bf476a6980f8314
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Nastavení ochrany koncového bodu pro Windows 10 a novější ve službě Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Profil ochrany koncového bodu vám umožňuje ovládat funkce zabezpečení na zařízeních s Windows 10, jako je například BitLocker nebo Windows Defender.

V tomto tématu se dozvíte, jak vytvářet profily ochrany koncového bodu.

## <a name="create-an-endpoint-protection-profile"></a>Vytvoření profilu ochrany koncového bodu

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **Název** a **Popis** profilu pro funkce zařízení.
5. V rozevíracím seznamu **Platforma** vyberte **Windows 10 a novější**.
6. V rozevíracím seznamu **Typ profilu** zvolte **Ochrana koncového bodu**.
7. V okně **Šifrování Windows** můžete konfigurovat požadovaná nastavení. V podrobných informacích v tomto tématu se dozvíte, jaká je funkce každého nastavení. Po dokončení zvolte **OK**.
8. Vraťte se zpět do okna **Vytvořit profil** a zvolte **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.

## <a name="windows-defender-smartscreen-settings"></a>Nastavení filtru SmartScreen v programu Windows Defender

- **Filtr SmartScreen pro aplikace a soubory** – Povolí filtr Windows SmartScreen pro provádění souborů a spuštěné aplikace.
- **Provádění neověřených souborů** – Zablokuje koncovému uživateli možnost provádět soubory, které nebyly ověřeny filtrem Windows SmartScreen.

## <a name="windows-encryption-settings"></a>Nastavení šifrování Windows

### <a name="windows-settings"></a>Nastavení systému Windows

- **Požadovat šifrování zařízení (jenom stolní počítače)** – Pokud je tato možnost povolena, zobrazí se uživatelům výzva, aby povolili šifrování zařízení. Kromě toho jsou požádání o potvrzení, že nebylo povoleno šifrování od jiného zprostředkovatele. Pokud je zapnuto šifrování Windows a současně je aktivní jiná metoda šifrování, mohlo by to narušit stabilitu zařízení.
- **Vyžadovat šifrování paměťové karty (jenom mobilní zařízení)** – Pokud je tato možnost povolena, zašifrují se případné vyměnitelné paměťové karty použité v zařízení.


### <a name="bitlocker-base-settings"></a>Základní nastavení BitLockeru

- **Konfigurovat metody šifrování** – Povolení tohoto nastavení umožní konfiguraci algoritmů šifrování operačního systému, dat a vyměnitelných jednotek.
    - **Šifrování jednotek s operačním systémem** – Umožňuje vybrat metodu šifrování pro jednotky s operačním systémem. Doporučujeme použít algoritmus XTS-AES.
    - **Šifrování pevných datových jednotek** – Umožňuje vybrat metodu šifrování pro pevné (vestavěné) datové jednotky. Doporučujeme použít algoritmus XTS-AES.
    - **Šifrování vyměnitelných datových jednotek** – Umožňuje vybrat metodu šifrování pro vyměnitelné datové jednotky. Pokud se vyměnitelná jednotka používá se zařízeními s jiným systémem než Windows 10, doporučujeme použít algoritmus AES-CBC.


### <a name="bitlocker-os-drive-settings"></a>Nastavení BitLockeru pro jednotky s operačním systémem

- **Vyžadovat při spuštění další ověření** -
    - **BitLocker s nekompatibilním čipem TPM** -
    - **Spouštění s čipem TPM** – Umožňuje konfigurovat, jestli je, nebo není povolený čip TMP, nebo jestli je povinný.
    - **Spouštěcí PIN kód TPM** – Umožňuje konfigurovat, jestli je, nebo není povoleno použití spouštěcího PIN kódu u čipu TPM, nebo jestli je povinné.
    - **Spouštěcí klíč TPM** – Umožňuje konfigurovat, jestli je, nebo není povoleno použití spouštěcího klíče u čipu TPM, nebo jestli je povinné.
    - **Spouštěcí klíč a PIN kód TPM** – Umožňuje konfigurovat, jestli je, nebo není povoleno použití spouštěcího klíče a PIN kódu u čipu TPM, nebo jestli je povinné.
- **Minimální délka PIN kódu** – Po povolení tohoto nastavení můžete konfigurovat minimální délku spouštěcího PIN kódu u čipu TPM.
    - **Minimální počet znaků** – Zadejte počet znaků požadovaný pro spouštěcí PIN kód v rozmezí **4**-**20**.
- **Povolit obnovování jednotek s operačním systémem** – Po povolení tohoto nastavení můžete řídit obnovu jednotek s operačním systémem chráněných BitLockerem v situacích, kdy nejsou k dispozici požadované informace pro spuštění.
    - **Agent obnovení dat založený na certifikátech** – Toto nastavení povolte, pokud chcete, aby bylo u jednotek s operačním systémem chráněných BitLockerem možné používat agenty obnovení dat.
    - **Vytváření hesla pro obnovení uživatelem** – Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 48místné heslo pro obnovení nebo jestli je vytvoření povinné.
    - **Vytváření obnovovacího klíče uživatelem** – Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 256bitové heslo pro obnovení nebo jestli je vytvoření povinné.
    - **Skrýt možnosti obnovení v průvodci nastavením BitLockeru** – Povolením tohoto nastavení zabráníte uživatelům zobrazovat a měnit po zapnutí BitLockeru možnosti obnovení.
    - **Ukládat informace pro obnovení BitLockeru do AD DS** – Umožňuje ukládání informací pro obnovení BitLockeru do služby Active Directory.
    - **Konfigurace úložiště informací pro obnovení BitLockeru ve službě AD DS** – Můžete nakonfigurovat, které části informací pro obnovení BitLockeru jsou uložené ve službě Active Directory. Vybírejte z těchto možností:
        - **Zálohovat hesla pro obnovení a sady klíčů**
        - **Zálohovat jenom hesla pro obnovení**
    - **Před povolením BitLockeru vyžadovat uložení informací pro obnovení do AD DS** – Povolením tohoto nastavení zabráníte uživatelům, aby zapínali BitLocker, pokud není zařízení připojené k doméně a informace pro obnovení BitLockeru nejsou úspěšně uloženy ve službě Active Directory.
- **Povolit zprávu o obnovení a adresu URL před spuštěním** – Po povolení tohoto nastavení můžete konfigurovat zprávu a adresu URL, které se zobrazí na obrazovce pro obnovení klíče před spuštěním.
    - **Zpráva o obnovení před spuštěním** – Můžete konfigurovat, jak se zpráva o obnovení před spuštěním zobrazí uživatelům. Vybírejte z těchto možností:
        - **Použít výchozí zprávu a adresu URL pro obnovení**
        - **Použít prázdnou zprávu a adresu URL pro obnovení**
        - **Použít vlastní zprávu o obnovení**
        - **Použít vlastní adresu URL pro obnovení**


### <a name="bitlocker-fixed-data-drive-settings"></a>Nastavení nástroje BitLocker pro pevné datové jednotky

- **Zamítnout přístup pro zápis na pevné datové jednotky, které nechrání BitLocker** – Pokud je tato možnost povolena, zapisování na všechny pevné (vestavěné) datové jednotky je povoleno jenom tehdy, když je na nich povolen BitLocker.
- **Povolit obnovení pevných jednotek** – Pokud povolíte toto nastavení, můžete řídit obnovu pevných jednotek chráněných BitLockerem v případě, že nejsou k dispozici požadované informace pro spuštění.
    - **Agent obnovení dat** – Toto nastavení povolte, pokud chcete u pevných jednotek chráněných BitLockerem používat agenty obnovení dat.
    - **Vytváření hesla pro obnovení uživatelem** – Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 48místné heslo pro obnovení nebo jestli je vytvoření povinné.  
    - **Vytváření obnovovacího klíče uživatelem** – Můžete nakonfigurovat, jestli mají uživatelé povoleno nebo zakázáno vytvořit 256bitové heslo pro obnovení nebo jestli je vytvoření povinné.
    - **Skrýt možnosti obnovení v průvodci nastavením BitLockeru** – Povolením tohoto nastavení zabráníte uživatelům zobrazovat a měnit po zapnutí BitLockeru možnosti obnovení.
    - **Ukládat informace pro obnovení BitLockeru do AD DS** – Umožňuje ukládání informací pro obnovení BitLockeru do služby Active Directory.
    - **Konfigurace úložiště informací pro obnovení BitLockeru ve službě AD DS** – Můžete nakonfigurovat, které části informací pro obnovení BitLockeru jsou uložené ve službě Active Directory. Vybírejte z těchto možností:
        - **Zálohovat hesla pro obnovení a sady klíčů**
        - **Zálohovat jenom hesla pro obnovení**
    - **Před povolením BitLockeru vyžadovat uložení informací pro obnovení do AD DS** – Povolením tohoto nastavení zabráníte uživatelům, aby zapínali BitLocker, pokud není zařízení připojené k doméně a informace pro obnovení BitLockeru nejsou úspěšně uloženy ve službě Active Directory.


### <a name="bitlocker-removable-data-drive-settings"></a>Nastavení nástroje BitLocker pro vyměnitelné datové jednotky

- **Zamítnout přístup pro zápis na vyměnitelné datové jednotky, které nechrání BitLocker** – Můžete zadat, jestli se u vyměnitelných datových jednotek musí povinně používat šifrování BitLockeru.
    - **Zablokovat přístup pro zápis na zařízení nakonfigurovaná jinou organizací** – Můžete zadat, jestli je možné zapisovat na zařízení patřící jiné organizaci.



## <a name="next-steps"></a>Další kroky

Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).
