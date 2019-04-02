---
title: Instalace aplikací Office 365 na zařízení pomocí Intune
titleSuffix: ''
description: Zjistěte, jak můžete s Microsoft Intune zjednodušit instalaci aplikací Office 365 na zařízeních s Windows 10.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/29/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: craigma
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1ecdb96bc908f4220d2eb62c52df3b7750e0cba3
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798244"
---
# <a name="assign-office-365-apps-to-windows-10-devices-with-microsoft-intune"></a>Přiřazení aplikací Office 365 k zařízením s Windows 10 pomocí Microsoft Intune

Než budete moct přiřadit, monitorovat, konfigurovat nebo chránit aplikace, musíte je přidat do Intune. Jeden z dostupných [typy aplikací](apps-add.md#app-types-in-microsoft-intune) je aplikací Office 365 pro zařízení s Windows 10. Pokud vyberete tento typ aplikace v Intune, můžete přiřadit a instalaci aplikací Office 365 na vámi spravovaných zařízeních s Windows 10. Můžete také přiřadit a nainstalovat aplikace pro klienta pro stolní počítače Microsoft Project Online a Microsoft Visio Online Plan 2, pokud vlastníte jejich licence. Dostupné aplikace Office 365 se zobrazí jako jedna položka v seznamu aplikací v konzole Intune v rámci Azure.

> [!NOTE]
> K aktivaci aplikací Office 365 ProPlus nasazených prostřednictvím Microsoft Intune musíte použít licence Office 365 ProPlus. V současné době Intune nepodporuje edici Office 365 Business.

## <a name="before-you-start"></a>Než začnete

> [!IMPORTANT]
> Pokud se na zařízení koncového uživatele nacházejí aplikace Office MSI, je nutné tyto aplikace bezpečně odinstalovat pomocí funkce pro **odebrání MSI**. Jinak se instalace aplikací Office 365 doručených pomocí Intune nezdaří.

- Zařízení, na která chcete tyto aplikace nasadit, musí mít aktualizaci Windows 10 Creators Update nebo novější.
- Intune podporuje přidání aplikací Office jenom ze sady Office 365.
- Pokud jsou spuštěné nějaké aplikace Office, když Intune instaluje sadu aplikací, může instalace selhat a uživatelé můžou přijít o data z neuložených souborů.
- Tato metoda instalace není podporovaná na zařízeních s Windows 10 S, Windows Home, Windows Team, Windows Holographic a Windows Holographic for Business.
- Intune nepodporuje instalaci desktopových aplikací Office 365 z Microsoft Storu (označovaných jako aplikace Office Centennial) na zařízení, na která jste už nasadili aplikace Office 365 pomocí Intune. Pokud nainstalujete tuto konfiguraci, může to způsobit ztrátu nebo poškození dat.
- V případě vícenásobného přiřazení požadovaných nebo dostupných aplikací nemá novější přiřazení aditivní účinek. Novější přiřazení aplikací přepíše dříve existující přiřazení nainstalovaných aplikací. Pokud například první sada aplikací Office obsahuje Word a novější sada ho neobsahuje, Word se odinstaluje. To se netýká aplikací Visio a Project.
- **Verze Office**: Vyberte, jestli chcete přiřadit 32bitovou nebo 64bitovou verzi Office. 32bitovou verzi můžete nainstalovat na 32bitová i 64bitová zařízení, ale 64bitovou verzi můžete nainstalovat jenom na 64bitová zařízení.
- **Odebrat MSI ze zařízení koncových uživatelů**: Vyberte, jestli chcete ze zařízení koncových uživatelů odebrat dřívější aplikace Office .MSI. Pokud na zařízeních koncových uživatelů takové aplikace jsou, instalace se nezdaří. Aplikace k odinstalování se neomezují jen na ty, které jsou vybrané pro instalaci v nastavení **Nakonfigurovat sadu aplikací**, protože ze zařízení koncového uživatele se odeberou všechny aplikace Office (MSI). Další informace najdete v článku věnovaném [odebrání stávajících verzí služby MSI v systému Office při upgradu na Office 365 ProPlus](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version). Když Intune přeinstaluje Office na počítače koncových uživatelů, získají koncoví uživatelé automaticky stejné jazykové sady, které měli s předchozími instalacemi Office .MSI.

## <a name="get-started"></a>Začínáme

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V podokně úloh **Klientské aplikace** vyberte v části **Spravovat** možnost **Aplikace**.
5. Vyberte **Přidat**.
6. V podokně **Přidat aplikace** v seznamu **Typ aplikace** vyberte v oblasti **Sada Office 365** možnost **Windows 10**.

## <a name="select-settings-format"></a>Vyberte formát nastavení

Můžete zvolit metodu pro konfiguraci nastavení aplikace, které tak, že vyberete **formát nastavení**. Možnosti nastavení formátu:
- Návrháře konfigurace
- Zadání XML dat

Pokud zvolíte **Configuration designer** **přidat aplikaci** okno se změní na nabízí dvě možnosti pro další nastavení:
- Konfigurace sady aplikací
- Nastavení sady aplikací

<img alt="Add Office 365 - Configuration designer" src="./media/apps-add-office365/apps-add-office365-02.png" width="700">

Pokud zvolíte **zadat XML data** **přidat aplikaci** okno se zobrazením **zadat XML data** možnost. Výběrem této možnosti Zobrazit **konfigurační soubor** okno. 

![Přidat návrháře konfigurace Office 365](./media/apps-add-office365/apps-add-office365-01.png)
    
Další informace o **zadat XML data** možnosti najdete v tématu [zadat XML data](apps-add-office365.md#enter-xml-format) níže.

## <a name="configure-app-suite-information"></a>Nakonfigurujte informace o sadě aplikací

V tomto kroku zadáte informace o sadě aplikací. Tyto informace vám pomůžou sadu aplikací identifikovat v Intune a uživatelům ji pomůžou najít na portálu společnosti.

1. V podokně **Přidat aplikaci** vyberte **Informace o sadě aplikací**.
2. V podokně **Informace o sadě aplikací** postupujte takto:
    - **Název sady**: Zadejte název sady aplikací, který se zobrazí v aplikaci portál společnosti. Názvy všech používaných sad musí být jedinečné. Pokud stejný název sady aplikací existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis sady**: Zadejte popis sady aplikací. Můžete například uvést aplikace, které jste vybrali pro zahrnutí.
    - **Publisher**: Jako vydavatel se zobrazí Microsoft.
    - **Kategorie**: Volitelně vyberte jednu nebo několik předdefinovaných kategorií aplikací nebo kategorii, kterou jste vytvořili. Díky tomuto nastavení uživatelé dokážou sadu aplikací při procházení portálu společnosti jednodušeji najít.
    - **Zobrazit tuto aplikaci jako doporučenou aplikaci portálu společnosti**: Vyberte tuto možnost, chcete-li zobrazit sadu aplikací výrazném místě na hlavní stránce portálu společnosti když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Soukromá adresa URL**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Pro vývojáře**: Jako vývojář se zobrazí Microsoft.
    - **Vlastník**: Jako vlastník se zobrazí Microsoft.
    - **Poznámky k**: Zadejte jakékoli poznámky, které chcete přidružit k této aplikaci.
    - **Logo**: Logo Office 365 se zobrazí u aplikace, když uživatelé procházejí portál společnosti.
3. Vyberte **OK**.

## <a name="configure-app-suite"></a>Konfigurace sady aplikací

Pokud jste vybrali **Configuration designer** v části **formát nastavení** rozevíracím seznamu, uvidíte **konfiguraci sady aplikací** možnost **přidat aplikace** okno. Vyberte aplikace Office, které chcete přiřadit k zařízením.

1. V podokně **Přidat aplikaci** zvolte **Nakonfigurovat sadu aplikací**.
2. V podokně **Nakonfigurovat sadu aplikací** vyberte standardní aplikace Office, které chcete přiřadit k zařízením.  
    Kromě toho můžete nainstalovat aplikace pro klienta pro stolní počítače Microsoft Project Online a Microsoft Visio Online Plan 2, pokud vlastníte jejich licence.
3. Vyberte **OK**.

## <a name="configure-app-suite-settings"></a>Konfigurace nastavení sady aplikací

Pokud jste vybrali **Configuration designer** v části **formát nastavení** rozevíracím seznamu, uvidíte **nastavení sady aplikací** možnost **přidat aplikaci**  okno. V tomto kroku nakonfigurujte možnosti instalace pro sadu aplikací. Nastavení budou platit pro všechny aplikace přidané k sadě.

1. V podokně **Přidat aplikaci** vyberte **Nastavení sady aplikací**.
2. V podokně **Nastavení sady aplikací** postupujte takto:
    - **Verze Office**: Zvolte, zda chcete přiřadit 32bitové nebo 64bitové verzi systému Office. 32bitovou verzi můžete nainstalovat na 32bitová i 64bitová zařízení, ale 64bitovou verzi můžete nainstalovat jenom na 64bitová zařízení.
    - **Aktualizační kanál**: Zvolte, jak je na těchto zařízeních aktualizuje Office. Informace o různých kanálech aktualizací najdete v článku [Přehled kanálů aktualizací pro Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus). Vybírejte z těchto možností:
        - **Měsíčně**
        - **Měsíční (cílený)**
        - **Půlroční**
        - **Půlroční (cílený)**

        Po volbě kanálu můžete volitelně vybrat možnost **Konkrétní** a nainstalovat tak pro daný kanál na zařízeních koncových uživatelů konkrétní verzi Office. Potom vyberte **konkrétní verzi** Office, která se má použít.
        
        Dostupné verze se budou v průběhu času měnit. Při vytváření nového nasazení tedy můžou být dostupné novější verze a některé starší verze nemusí být k dispozici. Aktuální nasazení budou dál nasazovat starší verzi, ale seznam verzí se bude průběžně aktualizovat podle kanálu.
        
        Pokud se nainstalovala starší verze, na zařízeních, které aktualizují připnutou verzi (nebo jakékoli jiné vlastnosti) a nasazují se jako dostupné, se až do ohlášení zařízení zobrazí stav hlášení Nainstalováno. Když se zařízení ohlásí, stav se dočasně změní na Neznámé, ale nezobrazí se uživateli. Jakmile uživatel zahájí instalaci novější dostupné verze, uvidí změněný stav Nainstalováno.
        
        Další informace najdete v článku [Základní informace o aktualizačních kanálech Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus).

    - **Odebrat MSI ze zařízení koncových uživatelů**: Vyberte, jestli chcete ze zařízení koncových uživatelů odebrat dřívější aplikace Office .MSI. Pokud na zařízeních koncových uživatelů takové aplikace jsou, instalace se nezdaří. Aplikace k odinstalování se neomezují jen na ty, které jsou vybrané pro instalaci v nastavení **Nakonfigurovat sadu aplikací**, protože ze zařízení koncového uživatele se odeberou všechny aplikace Office (MSI). Další informace najdete v článku věnovaném [odebrání stávajících verzí služby MSI v systému Office při upgradu na Office 365 ProPlus](https://docs.microsoft.com/deployoffice/upgrade-from-msi-version). Když Intune přeinstaluje Office na počítače koncových uživatelů, získají koncoví uživatelé automaticky stejné jazykové sady, které měli s předchozími instalacemi Office .MSI. 
    - **Automaticky přijmout licenční smlouvy s koncovým uživatelem aplikace**: Tuto možnost vyberte, Pokud nevyžadujete přijetí licenční smlouvy koncovým uživatelům. Intune pak smlouvu přijme automaticky.
    - **Použít sdílenou aktivaci počítače**: Tuto možnost vyberte, když počítač sdílí několik uživatelů. Další informace najdete v článku s [přehledem aktivace pro sdílené počítače pro Office 365](https://docs.microsoft.com/DeployOffice/overview-of-shared-computer-activation-for-office-365-proplus).
    - **Jazyky**: Office je automaticky nainstalován v některém z podporovaných jazyků, které jsou nainstalovány s Windows na zařízení koncového uživatele společnosti. Tuto možnost zvolte, pokud chcete nainstalovat se sadou aplikací další jazyky. <p></p>
    Můžete nasadit další jazyky pro aplikace Office 365 Pro Plus spravované prostřednictvím Intune. Seznam dostupných jazyků zahrnuje **Typ** jazykové sady (Základní, Částečná a Kontrola pravopisu). Na portálu Azure Portal vyberte **Microsoft Intune** > **Klientské aplikace** > **Aplikace** > **Přidat**. V okně **Přidat aplikaci** v seznamu **Typ aplikace** vyberte v části **Sada Office 365** možnost **Windows 10**. V okně **Nastavení sady aplikací** vyberte **Jazyky**. Další informace najdete v tématu s [přehledem jazyků nasazení v Office 365 ProPlus](https://docs.microsoft.com/deployoffice/overview-of-deploying-languages-in-office-365-proplus).

## <a name="enter-xml-format"></a>Zadejte formát XML

Pokud jste vybrali **zadat XML data** v části **formát nastavení** rozevíracím seznamu, uvidíte **formátu XML zadejte** možnost **přidat aplikaci**okno. Další informace najdete v tématu [možnosti konfigurace pro nástroj pro nasazení Office](https://docs.microsoft.com/DeployOffice/configuration-options-for-the-office-2016-deployment-tool).

## <a name="finish-up"></a>Dokončení

Až budete hotoví, v podokně **Přidat aplikaci** zvolte **Přidat**. Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací.

## <a name="errors-during-installation-of-the-app-suite"></a>Chyby při instalaci sady aplikací

V následující tabulce jsou uvedené běžné kódy chyb, se kterými se můžete setkat, a jejich význam.

### <a name="status-for-office-csp"></a>Stav pro Office CSP

| Stav | Fáze | Popis |
|--------------------------------------------------|--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1460 (ERROR_TIMEOUT) | Stažení | Nepodařilo se stáhnout nástroj pro nasazení Office. |
| 13 (ERROR_INVALID_DATA) | - | Nelze ověřit podpis staženého nástroje pro nasazení Office. |
| Kód chyby z CertVerifyCertificateChainPolicy | - | Nezdařila se kontrola certifikace staženého nástroje pro nasazení Office. |
| 997 | WIP | Instalace |
| 0 | Po instalaci | Instalace proběhla úspěšně. |
| 1603 (ERROR_INSTALL_FAILURE) | - | Se nezdařila kontrola předpokladů, jako například: SxS (pokus o instalaci, když je nainstalovaná MSI 2016) mismatchOthers verze |
| 0x8000ffff (E_UNEXPECTED) | - | Pokus odinstalovat, když na počítači není technologie Office Klikni a spusť |
| 17002 | - | Scénář se nepodařilo dokončit (nainstalovat). Možné důvody: instalace zrušena userInstallation zrušil installationOut jiného místa na disku během installationUnknown ID jazyka |
| 17004 | - | Neznámé skladové položky |


### <a name="office-deployment-tool-error-codes"></a>Kódy chyb nástroje pro nasazení Office

| Scénář | Návratový kód | Uživatelské rozhraní | Poznámka |
|------------------------------------------------------------------------------------------------------------------|---------------------------------------|----------------------------------------------------|------------------------------------|
| Pokus odinstalovat bez aktivní instalace Klikni a spusť | -2147418113, 0x8000ffff nebo 2147549183 | Kód chyby: 30088-1008Error kód: 30125-1011 (404) | Nástroj pro nasazení systému Office |
| Instalace, když je nainstalovaná verze MSI | 1603 | - | Nástroj pro nasazení systému Office |
| Instalace byla zrušena uživatelem nebo jinou instalací. | 17002 | - | Klikni a spusť |
| Pokus nainstalovat 64bitovou verzi na zařízení, na kterém je nainstalovaná 32bitová verze. | 1603 | - | Návratový kód nástroje pro nasazení Office |
| Pokus nainstalovat neznámou skladovou položku (případ neoprávněného použití Office CSP, protože je nutné předávat jenom platné skladové položky) | 17004 | - | Klikni a spusť |
| Nedostatek místa | 17002 | - | Klikni a spusť |
| Klienta s technologií Klikni a spusť se nepodařilo spustit (neočekávané) | 17000 | - | Klikni a spusť |
| U klienta s technologií Klikni a spusť se nepodařilo zařadit scénář do fronty (neočekávané) | 17001 | - | Klikni a spusť |

## <a name="next-steps"></a>Další postup

- Pokud chcete aplikace přiřadit do vybraných skupin, přečtěte si článek [Přiřazení aplikací do skupin](/intune-azure/manage-apps/deploy-apps).
