---
title: "Přidání obchodních aplikací pro Android do Microsoft Intune"
titlesuffix: 
description: "Přečtěte si o přidávání obchodních aplikací pro Android do Microsoft Intune."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 061d793c-c724-4cd9-9240-adb0cbda5661
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3f336fb295dba396dad3a399aafc17435edb70b3
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-add-android-line-of-business-lob-apps-to-microsoft-intune"></a>Přidání obchodních aplikací pro Android do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Obchodní aplikace (LOB) je aplikace, kterou do Intune přidáte z instalačního souboru aplikace. Tyto typy aplikací obvykle vznikají interně. Intune nainstaluje obchodní aplikaci na zařízení uživatelů. 

> [!Note]
> Pokud potřebujete další informace o obchodních aplikacích z obchodu Google Play for Work, přečtěte si, jak [pracovat s obchodní aplikací z obchodu Google Play for Work](apps-add-android-for-work.md?#working-with-a-line-of-business-app-from-the-google-play-for-work-store). 

## <a name="step-1---specify-the-software-setup-file"></a>Krok 1 – určení instalačního souboru softwaru

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Na stránce **Intune** zvolte **Mobilní aplikace**.
4. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Aplikace**.
5. Nad seznamem aplikací zvolte **Přidat**.
6. V podokně **Přidat aplikaci** zvolte **Obchodní aplikace**.

## <a name="step-2---configure-the-app-package-file"></a>Krok 2 – konfigurace souboru balíčku aplikace

1. V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V podokně **Soubor balíčku aplikace** klikněte na tlačítko Procházet a vyberte instalační soubor Androidu s příponou **.apk**.
3. Po dokončení zvolte **OK**.


## <a name="step-3---configure-app-information"></a>Krok 3 – konfigurace informací o aplikaci

1. V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V podokně **Informace o aplikaci** přidejte podrobnosti o aplikaci. V závislosti na zvolené aplikaci můžou být některé hodnoty v tomto podokně vyplněné automaticky:
    - **Název** – zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis** – zadejte popis aplikace, který se zobrazí uživatelům na portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele aplikace.
    - **Minimální operační systém** – v seznamu zvolte minimální verzi operačního systému, na kterou lze aplikaci nainstalovat. Pokud aplikaci přiřadíte k zařízení se starším operačním systémem, nenainstaluje se.
    - **Ignorovat verzi aplikace** – nastavte na **Ano**, pokud aplikaci automaticky aktualizuje její vývojář.
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

1. V podokně **Přidat aplikaci** ověřte podrobnosti aplikace.
2. Zvolte **Přidat** a nahrajte aplikaci do Intune.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřadit ke zvoleným skupinám. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

## <a name="step-5---update-a-line-of-business-app"></a>Krok 5 – aktualizace obchodní aplikace

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

> [!Note]
> Aby služba Intune úspěšně nasadila nový soubor APK do zařízení, musíte zvýšit hodnotu řetězce android:versionCode v souboru AndroidManifest.xml v balíčku APK.

## <a name="next-steps"></a>Další kroky

- Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací. Nyní ji můžete přiřadit do požadované skupiny. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

- Zjistěte, jakými způsoby můžete monitorovat vlastnosti a přiřazení aplikace. Další informace najdete v tématu [Postup monitorování informací a přiřazení aplikace](apps-monitor.md).

- Zjistěte více o kontextu své aplikace v Intune. Další informace najdete v tématu [Přehled životních cyklů zařízení a aplikací](introduction-device-app-lifecycles.md).
