---
title: Použití šablon pro zařízení s Windows 10 v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Pomocí šablony pro správu v Microsoft Intune můžete vytvořit skupiny nastavení pro zařízení s Windows 10. Pomocí těchto nastavení v profilu konfigurace zařízení k řízení aplikace sady Office, zabezpečené funkce v aplikaci Internet Explorer, řízení přístupu k Onedrivu, pomocí funkce vzdálené plochy, povolit automatické přehrávání, nastavení řízení spotřeby, použít tisk HTTP, použijte jiný uživatel Možnosti přihlášení a řízení velikosti protokolu událostí.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/27/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3385d28ea4e97533784340c5d3240fb60f57fd47
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2019
ms.locfileid: "57231382"
---
# <a name="use-windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>Použití šablon Windows 10 v Microsoft Intune konfigurovat nastavení zásad skupiny

Při správě zařízení ve vaší organizaci, můžete chtít vytvořit skupinu nastavení, která se použijí v různých skupinách zařízení. Například můžete mít několik skupin zařízení. Pro GroupA kterému chcete přiřadit určitou sadu nastavení. Pro GroupB kterému chcete přiřadit jinou sadu nastavení. Chcete také jednoduchý přehled na nastavení, která můžete nakonfigurovat.

Pomocí této úlohy můžete dokončit **šablony pro správu** v Microsoft Intune. Šablony pro správu zahrnují stovky nastavení, která řídí funkce v aplikaci Internet Explorer sady Microsoft Office, vzdálené plochy, přístup k Onedrivu, použití obrázkového hesla nebo PIN kód pro přihlášení a další. Tyto šablony jsou podobné nastavení skupiny zásad (objekt zásad skupiny) v Active Directory (AD) a jsou [zálohovanou ADMX nastavení](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) (otevře jiný web dokumentace), které používají XML. Ale šablony v Intune jsou 100 % založené na cloudu. Nabízejí další jednoduché a přímočaré až po konfiguraci nastavení a najít nastavení chcete.

**Šablony pro správu** jsou integrované do Intune a nevyžadují žádné úpravy, včetně použití OMA-URI. Jako součást řešení správy mobilních zařízení pomocí těchto nastavení šablony jako univerzálním nástrojem pro správu zařízení s Windows 10.

V tomto článku jsou uvedené kroky k vytvoření šablony pro zařízení s Windows 10 a ukazuje, jak filtrovat všechna nastavení, které jsou dostupné v Microsoft Intune. Při vytváření šablony vytvoří profil konfigurace zařízení. Pak můžete přiřadit nebo tento profil nasadíte u zařízení s Windows 10 ve vaší organizaci.

> [!NOTE]
> Šablony pro správu jsou podporovány pro samostatné zařízení. Nejsou aktuálně podporovány pro spoluspravovaná zařízení System Center Configuration Manageru (SCCM).

## <a name="create-a-template"></a>Vytvoření šablony

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte název pro profil.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: Vyberte **Windows 10 a novější**.
    - **Typ profilu**: Vyberte **šablony pro správu (Preview)**.

4. Vyberte **Vytvořit**. V novém okně vyberte **nastavení**. Každé nastavení odpovídá a můžete použít předtím a vedle šipky zobrazíte další nastavení:

    ![Podívejte se do seznamu ukázková nastavení a tlačítky předchozí a další](./media/administrative-templates-windows/sample-settings-list-next-page.png)

5. Vyberte všechna nastavení. Vyberte například **povolit stahování souborů**. Podrobný popis nastavení se zobrazí. Zvolit **povolit**, **zakázat**, nebo nechte toto nastavení jako **Nenakonfigurováno** (výchozí). Podrobný popis také vysvětluje, co se stane, když zvolíte **povolit**, **zakázat**, nebo **Nenakonfigurováno**.
6. Vyberte **OK** uložte provedené změny.

I nadále projít seznam nastavení a nakonfigurujte nastavení, které mají ve vašem prostředí. Následuje několik příkladů:

- Použití **nastavení oznámení – makro VBA** nastavení pro zpracování makra jazyka VBA v různých aplikacích Microsoft Office, včetně aplikace Word a Excel.
- Použití **povolit stahování souborů** nastavení povolit nebo zakázat soubory ke stažení z aplikace Internet Explorer.
- Použití **požadovat heslo, když počítače probudí (zapojené do elektrické zásuvky)** nastavení vyzve uživatele k zadání hesla při zařízení probuzení z režimu spánku.
- Použití **stahování bez znaménka ovládací prvky ActiveX** nastavení k blokování uživatelů stahování bez znaménka ovládacích prvků ActiveX v Internet Exploreru.
- Použití **obnovení systému vypnout** nastavení pro povolení nebo zabránit uživatelům ve spouštění obnovení systému v zařízení.
- A spoustu dalších věcí...

## <a name="find-some-settings"></a>Najít některé nastavení

Nejsou k dispozici v těchto šablon stovky nastavení. Aby bylo snazší najít konkrétní nastavení, použijte integrované funkce:

- V šabloně, vyberte **nastavení**, **stavu**, nebo **cesta** sloupce seřadíte seznam. Vyberte například **cesta** sloupec, který chcete zobrazovat všechna nastavení v `Microsoft Excel` cesta:

  ![Klikněte na cestu k seřadit podle abecedy](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- V šabloně, použijte **hledání** pole najít konkrétní nastavení. Například vyhledejte `copy`. Všechna nastavení s `copy` se zobrazí:

  ![Klikněte na cestu k seřadit podle abecedy](./media/administrative-templates-windows/search-copy-settings.png)

  Například vyhledejte `microsoft word`. Zobrazí všechna nastavení, můžete nastavit pro aplikace Microsoft Word. Vyhledejte `explorer` zobrazíte všechna nastavení Internet Exploreru můžete přidat do šablony.

Tato funkce používá [zásad Windows CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies) (otevře jiný web Docs). Poskytovatelé CSP fungovat v různých edicích Windows, jako je například Home, Professional, Enterprise a tak dále. Pokud chcete zobrazit, pokud zprostředkovatel kryptografických služeb pracuje v konkrétní verzi, přejděte na [zásad Windows CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#admx-backed-policies) (otevře jiný web Docs).

## <a name="next-steps"></a>Další postup

Vytvoření šablony, ale to není teď zrovna nic nedělá ještě. Dále [přiřadit šablonu, také nazývaný jako profil](device-profile-assign.md) a [monitorování jejího stavu](device-profile-monitor.md).
