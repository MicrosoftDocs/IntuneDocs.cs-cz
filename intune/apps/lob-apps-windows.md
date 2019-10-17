---
title: Přidání obchodní aplikace pro Windows do Microsoft Intune
titleSuffix: ''
description: Naučte se, jak pomocí Microsoft Intune přidat obchodní aplikaci pro Windows.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9042c5bd41f0186e1c7735acf537a0328f29d94b
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507178"
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Přidání obchodní aplikace pro Windows do Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Obchodní aplikace (LOB) je aplikace, kterou přidáte z instalačního souboru aplikace. Tento typ aplikace zpravidla vzniká interně. Následující kroky obsahují pokyny k přidání obchodní aplikace pro Windows do Microsoft Intune.

> [!IMPORTANT]
> Když nasazujete aplikace Win32 pomocí instalačního souboru s příponou *. msi* , zvažte použití [rozšíření pro správu služby Intune](../apps/intune-management-extension.md). Pokud během registrace automatického pilotního nasazení kombinujete instalaci aplikací Win32 a obchodních aplikací, může instalace aplikace selhat.  

## <a name="step-1-specify-the-software-setup-file"></a>Krok 1: Určení instalačního souboru softwaru

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V úloze **Klientské aplikace** vyberte **Spravovat** > **Aplikace**.
5. Nad seznamem aplikací vyberte **Přidat**.
6. V podokně **Přidat aplikaci** vyberte **Obchodní aplikace**.

## <a name="step-2-configure-the-app-package-file"></a>Krok 2: Konfigurace souboru balíčku aplikace

1. V podokně **Přidat aplikaci** zvolte **Soubor balíčku aplikace**.
2. V podokně **Soubor balíčku aplikace** vyberte tlačítko Procházet. Potom vyberte instalační soubor Windows s příponou **.msi**, **.appx** nebo **.appxbundle**.

    > [!NOTE]
    > Mezi přípony souborů aplikací pro Windows patří **.msi**, **.appx**, **.appxbundle**, **.msix** a **.msixbundle**.  

1. Až to budete mít, vyberte **OK**.


## <a name="step-3-configure-app-information"></a>Krok 3: Konfigurace informací o aplikaci

1. V podokně **Přidat aplikaci** vyberte **Informace o aplikaci**.
2. V podokně **Informace o aplikaci** nakonfigurujte následující údaje. Některé hodnoty v tomto podokně mohou být vyplněné automaticky.
    - **Název**: Zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti jen jedna z aplikací.
    - **Popis**: Zadejte popis aplikace. Popis se zobrazí na portálu společnosti.
    - **Vydavatel**: Zadejte název vydavatele aplikace.
    - **Ignorovat verzi aplikace**: Nastavte na **Ano**, pokud aplikaci automaticky aktualizuje její vývojář. Tato možnost platí jen pro mobilní aplikace .msi.
    - **Kategorie**: Vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste si vytvořili sami. Díky kategoriím uživatelé aplikaci při procházení portálu společnosti snadněji najdou.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci**: Aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů**: Volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Argumenty příkazového řádku**: Volitelně zadejte jakékoli argumenty příkazového řádku, které chcete použít při spuštění souboru .msi.  Příkladem je **/q**. Nepoužívejte příkaz nebo argumenty příkazu msiexec, například **/i** nebo **/x**, jak se používají automaticky. Další informace najdete v tématu [Možnosti příkazového řádku](https://docs.microsoft.com/windows/desktop/Msi/command-line-options). Pokud. Soubor MSI potřebuje další možnosti příkazového řádku, které se považují za použití [správy aplikací Win32](app-management.md).
    - **Vývojář**: Volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník**: Volitelně zadejte jméno vlastníka aplikace. Zadat můžete například **Personální oddělení**.
    - **Poznámky**: Zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Logo**: Nahrajte ikonu, která se k aplikaci přidruží. Ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
3. Až to budete mít, vyberte **OK**.

## <a name="step-4-finish-up"></a>Krok 4: Dokončení

1. V podokně **Přidat aplikaci** zkontrolujte správnost nakonfigurovaných informací o aplikaci.
2. Pomocí možnosti **Přidat** nahrajte aplikaci do Intune.

## <a name="step-5-update-a-line-of-business-app"></a>Krok 5: Aktualizace obchodní aplikace

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

   > [!NOTE]
   > Aby služba Intune úspěšně nasadila nový soubor APPX do zařízení, musíte zvýšit hodnotu řetězce `Version` v souboru AppxManifest. XML v balíčku APPX.
    
## <a name="configure-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Konfigurace automaticky aktualizované mobilní aplikace MSI na ignorování procesu kontroly verzí

Známou automaticky aktualizovanou mobilní aplikaci MSI můžete nakonfigurovat tak, aby ignorovala proces kontroly verzí. 

Některé aplikace založené na instalační službě MSI automaticky aktualizuje vývojář aplikace. Pro tyto automaticky aktualizované aplikace MSI můžete v podokně **Informace o aplikaci** nakonfigurovat nastavení **Ignorovat verzi aplikace**. Po přepnutí tohoto nastavení na **Ano** nebude Microsoft Intune vynucovat verzi aplikace instalovanou na klientovi Windows. 

Tato možnost je užitečná, když chcete předejít konfliktu časování. Ke konfliktu časování může například dojít, když aplikaci automaticky aktualizuje vývojář aplikace a také Intune. Jak vývojář, tak Intune můžou vynucovat verzi aplikace na klientovi Windows, což způsobí konflikt.

## <a name="next-steps"></a>Další kroky

- Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací. Teď ji můžete přiřadit do požadovaných skupin. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

- Zjistěte, jakými způsoby můžete monitorovat vlastnosti a přiřazení aplikace. Viz [Postup monitorování informací a přiřazení aplikace](apps-monitor.md).

- Zjistěte více o kontextu své aplikace v Intune. Podívejte [se na Přehled životního cyklu aplikace v Microsoft Intune](app-lifecycle.md).
