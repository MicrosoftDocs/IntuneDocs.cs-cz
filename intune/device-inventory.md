---
title: Zobrazení podrobností o zařízeních v Microsoft Intune – Azure | Microsoft Docs
description: Zobrazte si podrobnosti o zařízení, včetně operačních systémů, místa v úložišti, výrobce a modelu. Microsoft Intune v Azure vám umožňuje získat seznam nainstalovaných aplikací, zkontrolovat zásady dodržování předpisů a nastavit TeamViewer. Jedná se o podobný princip jako při zobrazení inventáře zařízení, která spravujete.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a658182800f480f27097e078f28adc95c35aa3ea
ms.sourcegitcommit: 4d314df59747800169090b3a870ffbacfab1f5ed
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/30/2018
ms.locfileid: "43313174"
---
# <a name="see-device-details-in-intune"></a>Zobrazení podrobností o zařízení v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Funkce **Zařízení** poskytuje další podrobnosti o zařízení, která spravujete, včetně jejich hardwaru a nainstalovaných aplikací.

V tomto článku se dozvíte, jak si můžete zobrazit všechna zařízení a jejich vlastnosti na portálu Azure Portal.

## <a name="view-the-device-details"></a>Zobrazení podrobností o zařízení

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Zařízení** > **Všechna zařízení** > výběrem zařízení uvedeného v seznamu otevřete podrobné informace o něm:

   - **Přehled** zobrazuje název zařízení a uvádí některé jeho klíčové vlastnosti, včetně toho, jestli se jedná o zařízení programu Přineste si vlastní zařízení (BYOD), kdy bylo zaregistrováno a dalších informací. Na zařízení můžete provést následující akce:
      - [Vyřadit](devices-wipe.md#retire)
        - [Vymazání](devices-wipe.md#wipe)
        - [Vzdálené uzamčení](device-remote-lock.md)
        - [Synchronizace zařízení](device-sync.md)
        - [Resetovat heslo](device-passcode-reset.md)
        - [Restartovat](device-restart.md) (jenom Windows)
        - [Začít znovu](device-fresh-start.md) (jenom Windows)
     - Spustit relaci vzdálené pomoci
   - Pomocí **vlastností** můžete zařízení přiřadit [kategorii, kterou vytvoříte](device-group-mapping.md), a upravit jeho vlastnictví na osobní nebo podnikové.
   - Část **Hardware** obsahuje řadu podrobnosti o zařízení, včetně jeho ID, operačního systému a verze, úložného prostoru, modelu a výrobce, nastavení podmíněného přístupu a další.
   - V části **Zjištěné aplikace** se zobrazuje seznam všech nainstalovaných aplikací, které služba Intune v zařízení našla, včetně jejich verzí. Seznam aplikací můžete také **exportovat** do souboru CSV.
   - V části **Dodržování předpisů zařízení** najdete všechny přiřazené zásady dodržování předpisů a informaci, jestli je zařízení splňuje.
   - Část **Konfigurace zařízení** obsahuje všechny zásady konfigurace přiřazené zařízení a informaci, jestli byly zásady úspěšné.

Intune shromažďuje seznam aplikací jenom na zařízeních vlastněných společností. Na osobních zařízeních se aplikace nekontrolují. V případě počítačů s Windows 10 se uvádí jenom moderní aplikace na zařízeních vlastněných společností. Intune neshromažďuje informace o aplikacích Win32 na zařízeních. V závislosti na operátorovi, kterého zařízení používají, se některé aplikace nemusí shromažďovat.

|Platforma|Pro zařízení v osobním vlastnictví|Pro zařízení ve vlastnictví společnosti|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (bez klienta Configuration Manageru)|Pouze spravované aplikace|Pouze spravované aplikace|
|Windows 8.1 (bez klienta Configuration Manageru)|Pouze spravované aplikace|Pouze spravované aplikace|  
|Windows Phone 8|Pouze spravované aplikace|Pouze spravované aplikace|  
|Windows RT|Pouze spravované aplikace|Pouze spravované aplikace|  
|iOS|Pouze spravované aplikace|Všechny aplikace instalované na zařízení|
|macOS|Všechny aplikace instalované na zařízení|Všechny aplikace instalované na zařízení|  
|Android|Pouze spravované aplikace|Všechny aplikace instalované na zařízení|  

## <a name="hardware-device-details"></a>Podrobnosti o hardwarovém zařízení

### <a name="windows-and-ios-device-details"></a>Podrobnosti o zařízení s Windows a iOSem:
|Podrobnosti|Popis|  
|--------------|----------------------|  
|Název|Název zařízení|
|Název správy|Název zařízení používaný jenom v konzole. Změnou tohoto názvu nedojde ke změně názvu v zařízení.|
|UDID|Jedinečný identifikátor zařízení|
|ID zařízení Intune|Globálně jedinečný identifikátor, který jednoznačně identifikuje zařízení|
|Sériové číslo|Sériové číslo zařízení od výrobce|
|Sdílené zařízení|Pokud **Ano**, je zařízení sdílené více než jedním uživatelem|
|Registrace schválená uživatelem|Pokud **Ano**, pak má zařízení registraci schválenou uživatelem, která správcům umožňuje spravovat některá nastavení zabezpečení na zařízení|
|Operační systém|Operační systém používaný v zařízení|
|Verze operačního systému|Verze operačního systému v zařízení.|
|Jazyk operačního systému|Jazyk nastavený pro operační systému v zařízení|
|Celkové místo v úložišti|Celkové místo úložiště v zařízení (v gigabajtech)|
|Volné místo úložiště|Nevyužité místo úložiště v zařízení (v gigabajtech)|


### <a name="windows-ios-and-macos-device-details"></a>Podrobnosti o zařízení s Windows, iOSem a macOS
|Podrobnosti|Popis|  
|--------------|----------------------|  
|IMEI|Mezinárodní identita mobilního zařízení|
|MEID|Identifikátor mobilního zařízení|
|Výrobce|Výrobce zařízení|
|Model|Model zařízení|
|Telefonní číslo|Telefonní číslo přidružené k zařízení|
|Poskytovatel služeb pro odběratele|Bezdrátový operátor zařízení|
|Mobilní technologie|Rádiový systém používaný zařízením|
|Wi-Fi MAC|Adresa MAC zařízení|
|ICCID|Identifikátor karty s integrovaným obvodem, což je jedinečné identifikační číslo SIM karty|
|Datum zápisu|Datum a čas, kdy se zařízení zaregistrovalo v Intune|
|Poslední kontakt|Datum a čas posledního připojení zařízení k Intune|
|Kód pro obejití zámku aktivace|Kód, který se dá použít k obejití zámku aktivace|
|Registrováno v Azure AD|Pokud **Ano**, zařízení je registrované v Azure Active Directory|
|Dodržování předpisů|Stav dodržování předpisů zařízení|
|EAS aktivované|Pokud **Ano**, pak je zařízení synchronizované s poštovní schránkou Exchange|
|ID aktivace EAS|Identifikátor protokolu Exchange ActiveSync zařízení|
|Pod dohledem|Pokud **Ano**, mají správci nad zařízením lepší kontrolu|
|Šifrované|Pokud **Ano**, jsou data uložená v zařízení šifrovaná|



## <a name="next-steps"></a>Další kroky
Podívejte se, jaké další akce [správy zařízení](device-management.md) můžete provádět pomocí Intune.