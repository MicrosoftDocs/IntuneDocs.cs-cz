---
title: Přidání obchodních aplikací pro macOS do Microsoft Intune
titleSuffix: ''
description: Přečtěte si, jak přidat macOS obchodní aplikace do Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/26/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ef8008ac-8b85-4bfc-86ac-1f9fcbd3db76
ms.reviewer: aiwang
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 81a084528fdc500bf9b6de0ca5fa847c2e0b3797
ms.sourcegitcommit: 73b362173929f59e9df57e54e76d19834f155433
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/27/2019
ms.locfileid: "74563931"
---
# <a name="how-to-add-macos-line-of-business-lob-apps-to-microsoft-intune"></a>Přidání obchodních aplikací pro macOS do Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Informace v tomto článku vám pomůžou přidat do Microsoft Intune obchodní aplikace pro macOS. Než budete moct obchodní soubor nahrát do Microsoft Intune, musíte si stáhnout externí nástroj pro předběžné zpracování souborů *.pkg*. Předběžné zpracování souborů *.pkg* se musí provést v zařízení s macOS.

> [!NOTE]
> Od vydání verze macOS Catalina 10,15 se před přidáním vašich aplikací do Intune ujistěte, že jsou vaše obchodní aplikace macOS notarized. Pokud vývojáři vašich obchodních aplikací nenotarize své aplikace, aplikace se nespustí na zařízeních macOS vašich uživatelů. Další informace o tom, jak zjistit, jestli je aplikace notarized, najdete v článku [Notarize své aplikace MacOS pro přípravu na MacOS Catalina](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Notarizing-your-macOS-apps-to-prepare-for-macOS/ba-p/808579).

> [!NOTE]
> Uživatelé zařízení s macOS můžou odebrat některé integrované aplikace pro macOS, třeba aplikace Akcie a Mapy, ale není možné tyto aplikace s použitím Intune znovu nasadit. Když koncoví uživatelé tyto aplikace odstraní, musí přejít do App Storu a znovu si je ručně nainstalovat.

## <a name="before-your-start"></a>Než začnete

Musíte si stáhnout externí nástroj, označit stažený nástroj jako spustitelný soubor a předem zpracovat soubory *. pkg* pomocí nástroje, abyste mohli nahrát svůj obchodní soubor do Microsoft Intune. Předběžné zpracování souborů *.pkg* se musí provést v zařízení s macOS. Pomocí nástroje Intune App Wrapping Tool pro Mac umožněte správu aplikací pro Mac pomocí Microsoft Intune.

> [!IMPORTANT]
> Soubor *. pkg* musí být podepsán pomocí certifikátu instalační program ID pro vývojáře získaný z účtu Apple Developer. K nahrání obchodních aplikací pro macOS do Microsoft Intune je možné použít jenom soubory *.pkg*. Převod jiných formátů, například z *.dmg* na *.pkg*, není podporovaný.
>

1. Stáhněte si [Nástroj pro zabalení aplikace Intune pro Mac](https://github.com/msintuneappsdk/intune-app-wrapping-tool-mac).

    > [!NOTE]
    > **Intune App Wrapping Tool pro Mac** se musí spustit v počítači s macOS. 

2. Označte stažený nástroj jako spustitelný soubor:
   - Spusťte aplikaci Terminal.
   - Změňte adresář na umístění, kde se nachází `IntuneAppUtil`.
   - Spusťte následující příkaz, který nastaví spustitelný soubor nástroje:<br> 
       `chmod +x IntuneAppUtil`

3. Pomocí příkazu `IntuneAppUtil` v **Intune App Wrapping Tool pro Mac** zabalte soubor obchodní aplikace *.pkg* ze souboru *.intunemac*.<br>

    Tady jsou vzorové příkazy pro Microsoft Intune App Wrapping Tool pro macOS:
    
    - `IntuneAppUtil -h`<br>
    Tento příkaz zobrazí informace o využití nástroje.
    
    - `IntuneAppUtil -c <source_file> -o <output_file> [-v]`<br>
    Tento příkaz zabalí soubor obchodní aplikace *.pkg* do souboru *.intunemac*.
    
    - `IntuneAppUtil -r <filename.intunemac> [-v]`<br>
    Tento příkaz extrahuje zjištěné parametry a verze vytvořeného souboru *.intunemac*.

## <a name="step-1---specify-the-software-setup-file"></a>Krok 1 – určení instalačního souboru softwaru

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **aplikace** > **všechny aplikace** > **Přidat**.
3. V podokně **Přidat aplikaci** vyberte jako **Typ aplikace** **obchodní aplikaci** .

## <a name="step-2---configure-the-app-package-file"></a>Krok 2 – konfigurace souboru balíčku aplikace

1. V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V podokně **Soubor balíčku aplikace** klikněte na tlačítko Procházet a vyberte instalační soubor macOS s příponou *.intunemac*.
3. Po dokončení zvolte **OK**.


## <a name="step-3---configure-app-information"></a>Krok 3 – konfigurace informací o aplikaci

1. V podokně **Přidat aplikaci** zvolte **Informace o aplikaci**.
2. V podokně **Informace o aplikaci** přidejte podrobnosti o aplikaci. V závislosti na zvolené aplikaci můžou být některé hodnoty v tomto podokně vyplněné automaticky:
    - **Název** – zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis** – zadejte popis aplikace, který se zobrazí uživatelům na portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele aplikace.
    - **Minimální operační systém** – v seznamu zvolte minimální verzi operačního systému, na kterou lze aplikaci nainstalovat. Pokud aplikaci přiřadíte k zařízení se starším operačním systémem, nenainstaluje se.
    - **Kategorie** – vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste si vytvořili sami. Uživatelé tak dokážou aplikaci při procházení portálu společnosti najít jednodušeji.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací** – volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů** – volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář** – volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník** – volitelně zadejte vlastníka aplikace, například **Personální oddělení**.
    - **Poznámky** – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Logo** – nahrajte ikonu, která se přidruží k aplikaci. Tato ikona se u aplikace zobrazuje, když uživatelé procházejí portál společnosti.
3. Po dokončení zvolte **OK**.

## <a name="step-4---finish-up"></a>Krok 4 – dokončení

1. V podokně **Přidat aplikaci** ověřte správnost podrobností o aplikaci.
2. Zvolte **Přidat** a nahrajte aplikaci do Intune.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřadit ke zvoleným skupinám. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

> [!NOTE]
> Pokud soubor *.pkg* obsahuje více aplikací nebo instalačních programů aplikací, pak Microsoft Intune ohlásí, že je *aplikace* úspěšně nainstalovaná, jenom když se v zařízení zjistí všechny nainstalované aplikace.

## <a name="step-5---update-a-line-of-business-app"></a>Krok 5 – aktualizace obchodní aplikace

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

> [!NOTE]
> Aby služba Intune úspěšně nasadila nový soubor *.pkg* do zařízení, musíte zvýšit hodnotu řetězců `version` a `CFBundleVersion` balíčku v souboru *packageinfo* v balíčku *.pkg*.

## <a name="next-steps"></a>Další kroky

- Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací. Nyní ji můžete přiřadit do požadované skupiny. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

- Zjistěte, jakými způsoby můžete monitorovat vlastnosti a přiřazení aplikace. Další informace najdete v tématu [Postup monitorování informací a přiřazení aplikace](apps-monitor.md).

- Zjistěte více o kontextu své aplikace v Intune. Další informace najdete v tématu [Přehled životních cyklů zařízení a aplikací](../fundamentals/device-lifecycle.md).