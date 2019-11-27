---
title: Použití šablon pro zařízení s Windows 10 v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí šablon pro správu v Microsoft Intune můžete vytvořit skupiny nastavení pro zařízení s Windows 10. Tato nastavení použijte v profilu konfigurace zařízení k řízení programů Office, Microsoft Edge, zabezpečení funkcí v Internet Exploreru, řízení přístupu k OneDrivu, použití funkcí vzdálené plochy, povolení automatického přehrání, nastavení řízení spotřeby, používání HTTP tisku. Použijte různé možnosti přihlašování uživatelů a řízení velikosti protokolu událostí.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: ca087ec67542102a0cd3111d27a860500b23d3c4
ms.sourcegitcommit: 23e9c48348a6eba494d072a2665b7481e5b5c84e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/26/2019
ms.locfileid: "74547975"
---
# <a name="use-windows-10-templates-to-configure-group-policy-settings-in-microsoft-intune"></a>Pomocí šablon Windows 10 můžete nakonfigurovat nastavení zásad skupiny v Microsoft Intune

Při správě zařízení ve vaší organizaci chcete vytvořit skupiny nastavení, které se vztahují k různým skupinám zařízení. Máte například několik skupin zařízení. Pro skupinu a chcete přiřadit konkrétní sadu nastavení. Pro GroupB chcete přiřadit jinou sadu nastavení. Potřebujete také jednoduché zobrazení nastavení, která můžete konfigurovat.

Tuto úlohu můžete dokončit pomocí **šablony pro správu** v Microsoft Intune. Šablony pro správu obsahují stovky nastavení, která řídí funkce Microsoft Edge verze 77 a novější, Internet Explorer, systém Microsoft Office programů, Vzdálená plocha, OneDrive, hesla a PIN kódy a další. Tato nastavení umožňují správcům skupiny spravovat zásady skupiny pomocí cloudu.

Nastavení Windows jsou podobná nastavení zásad skupiny (GPO) ve službě Active Directory (AD). Tato nastavení jsou integrovaná ve Windows a jsou [Nastavení založená na ADMX](https://docs.microsoft.com/windows/client-management/mdm/understanding-admx-backed-policies) , která používají XML. Nastavení Office a Microsoft Edge jsou ingestovaná v ADMX a používají nastavení ADMX v [souborech šablon pro správu Office](https://www.microsoft.com/download/details.aspx?id=49030) a v [souborech šablon pro správu Microsoft Edge](https://www.microsoftedgeinsider.com/enterprise). Šablony Intune ale mají 100% cloudové. Nabízí jednoduchý a přímo převedený způsob konfigurace nastavení a vyhledá požadovaná nastavení.

**Šablony pro správu** jsou integrované do Intune a nevyžadují žádné vlastní nastavení, včetně použití OMA-URI. Jako součást řešení pro správu mobilních zařízení (MDM) použijte při správě zařízení s Windows 10 Tato nastavení šablony jako zastávku.

Tento článek obsahuje seznam kroků pro vytvoření šablony pro zařízení s Windows 10 a ukazuje, jak filtrovat všechna dostupná nastavení v Intune. Když vytvoříte šablonu, vytvoří se profil konfigurace zařízení. Pak můžete tento profil přiřadit nebo nasadit do zařízení s Windows 10 ve vaší organizaci.

## <a name="before-you-begin"></a>Před zahájením

- Některá z těchto nastavení jsou k dispozici počínaje verzí Windows 10 1703 (RS2). Některá nastavení nejsou součástí všech edicí systému Windows. Pro dosažení co nejlepších výsledků se doporučuje používat Windows 10 Enterprise verze 1903 (19H1) a novější.

- Nastavení systému Windows používají [zprostředkovatele CSP v zásadách systému Windows](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-group-policy-and-admx-backed-policies). Zprostředkovatelé CSP fungují na různých edicích Windows, jako jsou například Home, Professional, Enterprise atd. Pokud chcete zjistit, jestli zprostředkovatel kryptografických služeb funguje na konkrétní edici, přejděte na [Zásady Windows CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#policies-supported-by-group-policy-and-admx-backed-policies).

## <a name="create-a-template"></a>Vytvoření šablony

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
2. Vyberte **zařízení** > **konfiguračních profilech** > **vytvořit profil**.
3. Zadejte následující vlastnosti:

    - **Název**: zadejte název profilu.
    - **Popis**: Zadejte popis profilu. Toto nastavení není povinné, ale doporučujeme ho zadat.
    - **Platforma**: vyberte **Windows 10 a novější**.
    - **Typ profilu**: vyberte **šablony pro správu**.

4. Vyberte **Vytvořit**. V novém okně vyberte **Nastavení**. V seznamu je uvedeno každé nastavení a pomocí šipek před a další můžete zobrazit další nastavení:

    ![Podívejte se na vzorový seznam nastavení a použijte tlačítka předchozí a další.](./media/administrative-templates-windows/administrative-templates-sample-settings-list.png)

    > [!TIP]
    > Nastavení Windows v Intune se koreluje s cestou k místní zásadě skupiny, kterou vidíte v Editor místních zásad skupiny (`gpedit`).

5. V rozevíracím seznamu vyberte možnost **všechny produkty**. V seznamu můžete také filtrovat nastavení tak, aby se zobrazila pouze nastavení **systému Windows** , zobrazit pouze nastavení **Office** nebo pouze zobrazit **Edge verze 77 nebo novější** :

    ![Vyfiltruje seznam, aby se zobrazila všechna okna nebo všechna nastavení Office v šablonách pro správu v Intune.](./media/administrative-templates-windows/administrative-templates-choose-windows-office-all-products.png)

    > [!NOTE]
    > Nastavení Microsoft Edge platí pro:
    >
    > - Microsoft Edge verze 77 a novější. Pokud chcete nakonfigurovat Microsoft Edge verze 45 a starší, přečtěte si téma [Nastavení omezení pro zařízení v prohlížeči Microsoft Edge](device-restrictions-windows-10.md#microsoft-edge-browser).
    > - Windows 10 RS4 a novější s nainstalovanou verzí [KB 4512509](https://support.microsoft.com/kb/4512509)
    > - Windows 10 RS5 a novější s nainstalovanou verzí [KB 4512534](https://support.microsoft.com/kb/4512534)
    > - Windows 10 19H1 a novější s nainstalovanou verzí [KB 4512941](https://support.microsoft.com/kb/4512941)

6. Vyberte libovolné nastavení. Můžete například vyfiltrovat **sadu Office**a vybrat **Aktivovat prohlížení s omezeným přístupem**. Zobrazí se podrobný popis nastavení. Vyberte možnost **povoleno**, **zakázáno**nebo ponechat nastavení jako **Nenakonfigurováno** (výchozí). Podrobný popis také vysvětluje, co se stane, když vyberete možnost **povoleno**, **zakázáno**nebo **není nakonfigurováno**.
7. Výběrem **OK** uložte změny.

Přejděte do seznamu nastavení a nakonfigurujte požadovaná nastavení v prostředí. Tady je několik příkladů:

- Pomocí nastavení pro **oznamování maker v jazyce VBA** můžete zpracovávat makra VBA v různých systém Microsoft Office programech, včetně Wordu a Excelu.
- Pomocí nastavení **povolení stahování souborů** povolte nebo Zabraňte stažení z aplikace Internet Explorer.
- Při **probuzení počítače (napájení ze sítě) použít příkaz vyžadovat heslo** , když se zařízení probudí z režimu spánku, vyzvat uživatele k zadání hesla.
- Pomocí nastavení **Stáhnout nepodepsané ovládací prvky ActiveX** zabráníte uživatelům v Stahování nepodepsaných ovládacích prvků ActiveX z Internet Exploreru.
- Pomocí nastavení **vypnout obnovení systému** povolíte nebo zabráníte uživatelům v zařízení spouštět obnovení systému.
- Nastavení **povoluje Import oblíbených položek** použijte, když chcete uživatelům dovolit nebo zablokovat Import oblíbených položek z jiného prohlížeče do Microsoft Edge.
- A mnohem víc...

## <a name="find-some-settings"></a>Najít některá nastavení

V těchto šablonách jsou k dispozici stovky nastavení. Aby bylo snazší najít konkrétní nastavení, použijte integrované funkce:

- V šabloně pro řazení seznamu vyberte sloupce **Nastavení**, **stav**, **Typ nastavení**nebo **cesta** . Pokud například chcete zobrazit všechna nastavení v cestě `Microsoft Excel`, vyberte sloupec **cesta** :

  ![Kliknutím na cesta zobrazíte všechna nastavení seskupená podle zásad skupiny nebo cesty k ADMX v šablonách pro správu v Intune.](./media/administrative-templates-windows/path-filter-shows-excel-options.png)

- V šabloně vyhledejte konkrétní nastavení pomocí **vyhledávacího** pole. Můžete hledat nastavením nadpisu nebo cesty. Vyhledejte například `copy`. Zobrazí se všechna nastavení s `copy`:

  ![Vyhledat kopii pro zobrazení všech nastavení systému Windows a sady Office v šablonách pro správu v Intune](./media/administrative-templates-windows/search-copy-settings.png) 

  V jiném příkladu vyhledejte `microsoft word`. Zobrazí se všechna nastavení, která můžete nastavit pro program Microsoft Word. Vyhledejte `explorer` pro zobrazení všech nastavení aplikace Internet Explorer, která můžete přidat do šablony.

## <a name="next-steps"></a>Další kroky

Šablona se vytvoří, ale ještě nic nedělá. Dále [přiřaďte šablonu, která se označuje také jako profil](device-profile-assign.md) a [sledujte její stav](device-profile-monitor.md).

[Aktualizujte Office 365 pomocí šablon pro správu](administrative-templates-update-office.md).
