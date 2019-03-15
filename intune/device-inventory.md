---
title: Zobrazení podrobností o zařízeních v Microsoft Intune – Azure | Microsoft Docs
description: Zobrazte si podrobnosti o zařízení, včetně operačních systémů, místa v úložišti, výrobce a modelu. Microsoft Intune v Azure vám umožňuje získat seznam nainstalovaných aplikací, zkontrolovat zásady dodržování předpisů a nastavit TeamViewer. Jedná se o podobný princip jako při zobrazení inventáře zařízení, která spravujete.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 05/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c22822f34f426897549383df5e9c71b21b497a7e
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57391202"
---
# <a name="see-device-details-in-intune"></a>Zobrazení podrobností o zařízení v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Funkce **Zařízení** poskytuje další podrobnosti o zařízení, která spravujete, včetně jejich hardwaru a nainstalovaných aplikací.

V tomto článku se dozvíte, jak si můžete zobrazit všechna zařízení a jejich vlastnosti na portálu Azure Portal.

## <a name="view-the-device-details"></a>Zobrazení podrobností o zařízení

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
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
   - V části **Zjištěné aplikace** se zobrazuje seznam všech nainstalovaných aplikací, které služba Intune v zařízení našla, včetně jejich verzí. Seznam aplikací můžete také **exportovat** do souboru CSV. Tento seznam se aktualizuje každých 7 dní.
   - V části **Dodržování předpisů zařízení** najdete všechny přiřazené zásady dodržování předpisů a informaci, jestli je zařízení splňuje.
   - Část **Konfigurace zařízení** obsahuje všechny zásady konfigurace přiřazené zařízení a informaci, jestli byly zásady úspěšné.

Intune shromažďuje seznam aplikací jenom na zařízeních vlastněných společností. Na osobních zařízeních se aplikace nekontrolují. V případě počítačů s Windows 10 se uvádí jenom moderní aplikace na zařízeních vlastněných společností. Intune neshromažďuje informace o aplikacích Win32 na zařízeních. V závislosti na operátorovi, kterého zařízení používají, se některé aplikace nemusí shromažďovat.

|Platforma|Pro zařízení v osobním vlastnictví|Pro zařízení vlastněná společností|  
|--------------|---------------------------------|--------------------------------|  
|Windows 10 (bez klienta Configuration Manageru)|Jenom spravované aplikace|Jenom spravované aplikace|
|Windows 8.1 (bez klienta Configuration Manageru)|Jenom spravované aplikace|Jenom spravované aplikace|  
|Windows Phone 8|Jenom spravované aplikace|Jenom spravované aplikace|  
|Windows RT|Jenom spravované aplikace|Jenom spravované aplikace|  
|iOS|Jenom spravované aplikace|Všechny aplikace nainstalované v zařízení|
|macOS|Všechny aplikace nainstalované v zařízení|Všechny aplikace nainstalované v zařízení|  
|Android|Jenom spravované aplikace|Všechny aplikace nainstalované v zařízení|  
|Android Enterprise|Jenom spravované aplikace|Jenom aplikace nainstalované v pracovním profilu|  

## <a name="hardware-device-details"></a>Podrobnosti o hardwarovém zařízení
V závislosti na operátorovi zařízení používají mohou být shromažďovány všechny podrobnosti

|Podrobnosti|Popis|Platforma| 
|--------------|----------------------|----|  
|Name|Název zařízení|Windows, iOS|
|Název správy|Název zařízení používaný jenom v konzole. Změnou tohoto názvu nedojde ke změně názvu v zařízení.|Windows, iOS|
|UDID|Jedinečný identifikátor zařízení|Windows, iOS|
|ID zařízení Intune|Globálně jedinečný identifikátor, který jednoznačně identifikuje zařízení|Windows, iOS|
|Sériové číslo|Sériové číslo zařízení od výrobce|Windows, iOS|
|Sdílené zařízení|Pokud **Ano**, je zařízení sdílené více než jedním uživatelem|Windows, iOS|
|Registrace schválená uživatelem|Pokud **Ano**, pak má zařízení registraci schválenou uživatelem, která správcům umožňuje spravovat některá nastavení zabezpečení na zařízení|Windows, iOS|
|Operační systém|Operační systém používaný v zařízení|Windows, iOS|
|Verze operačního systému|Verze operačního systému v zařízení.|Windows, iOS|
|Jazyk operačního systému|Jazyk nastavený pro operační systému v zařízení|Windows, iOS|
|Celkové místo v úložišti|Celkové místo úložiště v zařízení (v gigabajtech)|Windows, iOS|
|Volné místo úložiště|Nevyužité místo úložiště v zařízení (v gigabajtech)|Windows, iOS|
|IMEI|Mezinárodní identita mobilního zařízení|Windows, iOS, Android|
|MEID|Identifikátor mobilního zařízení|Windows, iOS, Android|
|Výrobce|Výrobce zařízení|Windows, iOS, Android|
|Model|Model zařízení|Windows, iOS, Android|
|Telefonní číslo|Telefonní číslo přidružené k zařízení|Windows, iOS, Android|
|Poskytovatel služeb pro odběratele|Bezdrátový operátor zařízení|Windows, iOS, Android|
|Mobilní technologie|Rádiový systém používaný zařízením|Windows, iOS, Android|
|Wi-Fi MAC|Adresa MAC zařízení|Windows, iOS, Android|
|ICCID|Identifikátor karty s integrovaným obvodem, což je jedinečné identifikační číslo SIM karty|Windows, iOS, Android|
|Datum zápisu|Datum a čas, kdy se zařízení zaregistrovalo v Intune|Windows, iOS, Android|
|Poslední kontakt|Datum a čas posledního připojení zařízení k Intune|Windows, iOS, Android|
|Kód pro obejití zámku aktivace|Kód, který se dá použít k obejití zámku aktivace|Windows, iOS, Android|
|Registrováno v Azure AD|Pokud **Ano**, zařízení je registrované v Azure Active Directory|Windows, iOS, Android|
|Dodržování předpisů|Stav dodržování předpisů zařízení|Windows, iOS, Android|
|EAS aktivované|Pokud **Ano**, pak je zařízení synchronizované s poštovní schránkou Exchange|Windows, iOS, Android|
|ID aktivace EAS|Identifikátor protokolu Exchange ActiveSync zařízení|Windows, iOS, Android|
|Pod dohledem|Pokud **Ano**, mají správci nad zařízením lepší kontrolu|Windows, iOS, Android|
|Šifrované|Pokud **Ano**, jsou data uložená v zařízení šifrovaná|Windows, iOS, Android|



## <a name="next-steps"></a>Další postup
Podívejte se, jaké další akce [správy zařízení](device-management.md) můžete provádět pomocí Intune.
