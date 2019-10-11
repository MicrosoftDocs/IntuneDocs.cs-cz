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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c2b20030bd6c7e1dc9108002cc43f105cb8c6784
ms.sourcegitcommit: fca2670142c083d7562c0a36547a6a451863e315
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/08/2019
ms.locfileid: "72036458"
---
# <a name="add-a-windows-line-of-business-app-to-microsoft-intune"></a>Přidání obchodní aplikace pro Windows do Microsoft Intune

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Obchodní aplikace (LOB) je ta, kterou přidáte z instalačního souboru aplikace. Tento druh aplikace se obvykle napíše interně. Následující kroky poskytují pokyny, které vám pomůžou přidat obchodní aplikaci pro Windows do Microsoft Intune.

> [!IMPORTANT]
> Když nasazujete aplikace Win32 pomocí instalačního souboru s příponou *. msi* , zvažte použití [rozšíření pro správu služby Intune](../apps/intune-management-extension.md). Pokud během registrace automatického pilotního nasazení kombinujete instalaci aplikací Win32 a obchodních aplikací, může instalace aplikace selhat.  

## <a name="step-1-specify-the-software-setup-file"></a>Krok 1: určení instalačního souboru softwaru

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** vyberte **klientské aplikace**.
4. V úloze **klientské aplikace** vyberte **Spravovat** **aplikace** > .
5. Nad seznamem aplikací vyberte **Přidat**.
6. V podokně **Přidat aplikaci** vyberte **obchodní aplikace**.

## <a name="step-2-configure-the-app-package-file"></a>Krok 2: konfigurace souboru balíčku aplikace

1. V podokně **Přidat aplikaci** vyberte **soubor balíčku aplikace**.
2. V podokně **soubor balíčku aplikace** klikněte na tlačítko Procházet. Pak vyberte instalační soubor Windows s příponou **. msi**, **. appx**nebo **. appxbundle**.

    > [!NOTE]
    > Mezi přípony souborů pro aplikace pro Windows patří soubory **. msi**, **. appx**, **. appxbundle**, **. msix**a **. msixbundle**.  

1. Až budete hotovi, vyberte **OK**.


## <a name="step-3-configure-app-information"></a>Krok 3: Konfigurace informací o aplikaci

1. V podokně **Přidat aplikaci** vyberte **informace o aplikaci**.
2. V podokně **informace o aplikaci** nakonfigurujte následující informace. Některé hodnoty v tomto podokně mohou být automaticky vyplněny.
    - **Název**: zadejte název aplikace, který se zobrazí na portálu společnosti. Ujistěte se, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti jenom jedna z aplikací.
    - **Popis**: zadejte popis aplikace. Popis se zobrazí na portálu společnosti.
    - **Vydavatel**: zadejte název vydavatele aplikace.
    - **Ignorovat verzi aplikace**: nastavte na **Ano** , pokud vývojář aplikace tuto aplikaci automaticky aktualizuje. Tato možnost se vztahuje jenom na mobilní aplikace. msi.
    - **Kategorie**: vyberte jednu nebo více předdefinovaných kategorií aplikací nebo vyberte kategorii, kterou jste vytvořili. Kategorie usnadňují uživatelům vyhledání aplikace při procházení portálu společnosti.
    - **Zobrazit jako doporučenou aplikaci v portál společnosti**: aplikace bude na hlavní stránce portálu společnosti výrazně zobrazovat, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Adresa URL ochrany osobních údajů**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o ochraně osobních údajů pro aplikaci. Adresa URL se zobrazí na portálu společnosti.
    - **Argumenty příkazového řádku**: Volitelně můžete zadat jakékoli argumenty příkazového řádku, které chcete použít pro soubor. msi při spuštění.  Příklad je **/q**. Nepoužívejte příkaz nebo argumenty příkazu msiexec, například **/i** nebo **/x**, jak se používají automaticky. Další informace najdete v tématu [Možnosti příkazového řádku](https://docs.microsoft.com/windows/desktop/Msi/command-line-options). Pokud. Soubor MSI potřebuje další možnosti příkazového řádku, které se považují za použití [správy aplikací Win32](app-management.md).
    - **Vývojář**: Volitelně můžete zadat název vývojáře aplikace.
    - **Vlastník**: Volitelně zadejte jméno vlastníka této aplikace. Příkladem je **personální oddělení**.
    - **Poznámky**: Zadejte jakékoli poznámky, které chcete přidružit k této aplikaci.
    - **Logo**: Nahrajte ikonu, která je přidružená k aplikaci. Ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
3. Až budete hotovi, vyberte **OK**.

## <a name="step-4-finish-up"></a>Krok 4: dokončení

1. V podokně **Přidat aplikaci** ověřte, jestli jste správně nakonfigurovali informace o aplikaci.
2. Vyberte **Přidat** a nahrajte aplikaci do Intune.

## <a name="step-5-update-a-line-of-business-app"></a>Krok 5: aktualizace obchodní aplikace

[!INCLUDE [shared-proc-lob-updateapp](../includes/shared-proc-lob-updateapp.md)]

   > [!NOTE]
   > Aby služba Intune úspěšně nasadila nový soubor APPX do zařízení, musíte zvýšit hodnotu řetězce `Version` v souboru AppxManifest. XML v balíčku APPX.
    
## <a name="configure-a-self-updating-mobile-msi-app-to-ignore-the-version-check-process"></a>Konfigurace automaticky aktualizované mobilní aplikace MSI pro ignorování procesu kontroly verzí

Můžete nakonfigurovat známou automaticky aktualizovanou mobilní aplikaci MSI, aby ignorovala proces kontroly verzí. 

Některé aplikace založené na instalační službě MSI automaticky aktualizuje vývojář aplikace. Pro tyto automaticky aktualizované aplikace MSI můžete v podokně **informace o aplikaci** nakonfigurovat nastavení **Ignorovat verzi aplikace** . Když toto nastavení přepnete na **Ano**, Microsoft Intune nebude vymáhat verzi aplikace, která je nainstalovaná na klientovi Windows. 

Tato možnost se hodí k tomu, abyste se vyhnuli sporům. Například konflikt časování může nastat, když aplikaci automaticky aktualizuje vývojář aplikace a aktualizuje ji Intune. Obě se můžou pokusit vyhovět verzi aplikace na klientovi Windows, což vytvoří konflikt.

## <a name="next-steps"></a>Další kroky

- Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací. Teď ji můžete přiřadit do skupin, které vyberete. Nápovědu najdete v článku [přiřazení aplikací do skupin](apps-deploy.md).

- Přečtěte si další informace o způsobech, kterými můžete monitorovat vlastnosti a přiřazení vaší aplikace. Podívejte [se, jak monitorovat informace a přiřazení aplikace](apps-monitor.md).

- Přečtěte si další informace o kontextu vaší aplikace v Intune. Podívejte [se na Přehled životního cyklu aplikace v Microsoft Intune](app-lifecycle.md).
