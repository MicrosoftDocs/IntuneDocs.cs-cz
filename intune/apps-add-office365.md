---
title: "Instalace aplikací Office 365 ProPlus na zařízení s Windows 10 pomocí Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak můžete použít Intune a usnadnit instalaci aplikací Office 365 na zařízení s Windows 10."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 07/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3292671a-5f5a-429e-90f7-b20019787d22
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1a97e58f1d108932e44b0b4e36bda5a30b7a90da
ms.sourcegitcommit: 79116d4c7f11bafc7c444fc9f5af80fa0b21224e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/03/2017
---
# <a name="how-to-assign-office-365-proplus-2016-apps-to-windows-10-devices-with-microsoft-intune"></a>Přiřazení aplikací Office 365 ProPlus 2016 k zařízením s Windows 10 pomocí Microsoft Intune

Tento typ aplikace vám usnadní přiřazování aplikací Office 365 ProPlus 2016 na vámi spravovaná zařízení s Windows 10. Můžete si také nainstalovat aplikace pro klienta pro stolní počítače Microsoft Project Online a Microsoft Visio Pro Office 365, pokud vlastníte jejich licence. Požadované aplikace se v seznamu aplikací v konzole Intune zobrazí jako jedna aplikace.


## <a name="before-you-start"></a>Než začnete

>[!IMPORTANT]
>Tato metoda instalace Office se podporuje jenom v případě, že nejsou na zařízení nainstalované jiné verze Microsoft Office.

- Zařízení, na která chcete tyto aplikace nasadit, musí mít aktualizaci Windows 10 Creators Update nebo novější.
- Intune podporuje přidání aplikací Office jenom ze sady Office 365 ProPlus 2016.
- Pokud jsou spuštěné nějaké aplikace Office, když Intune instaluje sadu aplikací, můžou koncoví uživatelé přijít o data z neuložených souborů.
- Tato metoda instalace není podporovaná v zařízeních s Windows 10S.
- Pokud tento typ aplikace přiřadíte jako K dispozici a zacílíte různá přiřazení na více uživatelů, uvidí jenom poslední zacílené přiřazení.


## <a name="get-started"></a>Začínáme

1.  Přihlaste se k portálu Azure Portal.
2.  Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3.  V okně **Intune** zvolte **Mobilní aplikace**.
4.  V úloze **Mobilní aplikace** zvolte **Spravovat** > **Aplikace**.
5.  Nad seznamem aplikací zvolte **Přidat**.
6.  V okně **Přidat aplikaci** zvolte **Office 365 ProPlus Suite (Windows 10)**.

## <a name="configure-the-app-suite"></a>Konfigurace sady aplikací

V tomto kroku vyberte aplikace Office, které chcete přiřadit k zařízení.

1.  V okně **Přidat aplikaci** zvolte možnost pro **konfiguraci sady aplikací**.
2.  V okně pro **konfiguraci sady aplikací** vyberte standardní aplikace Office, které chcete přiřadit k zařízení. Kromě toho si můžete nainstalovat aplikace pro klienta pro stolní počítače Microsoft Project Online a Microsoft Visio Pro for Office 365, pokud vlastníte jejich licence.
3.  Po dokončení klikněte na **OK**.

>[!IMPORTANT]
> Vlastnosti již vytvořené sady aplikací není možné upravit. Pokud chcete nakonfigurovat jiné vlastnosti, odstraňte sadu aplikací a vytvořte novou.

## <a name="configure-app-information"></a>Konfigurace informací o aplikaci

V tomto kroku zadejte informace o sadě aplikací. Tyto informace vám ji pomůžou identifikovat v konzole Intune a pomůžou také koncovým uživatelům, aby ji našli v aplikaci Portál společnosti.

1.  V okně **Přidat aplikaci** zvolte možnost pro **informace o sadě aplikací**.
2.  V okně s **informacemi o sadě aplikací** zadejte následující informace: 
    - **Název sady** – zadejte název sady aplikací, který se zobrazí na portálu společnosti. Názvy všech používaných aplikací musí být jedinečné. Pokud stejný název sady aplikací existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis sady** – zadejte popis sady aplikací. Můžete například uvést aplikace, které jste vybrali pro zahrnutí.
    - **Vydavatel** – zadejte název vydavatele aplikace.
    - **Kategorie** – můžete vybrat jednu nebo několik předdefinovaných kategorií nebo kategorii, kterou jste vytvořili. Uživatelé tak dokážou sadu aplikací při procházení portálu společnosti jednodušeji najít.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – sada aplikací se uživatelům, kteří hledají aplikace, zobrazí na výrazném místě na hlavní stránce portálu společnosti.
    - **Adresa URL informací** – volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů** – volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář** – volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník** – volitelně zadejte vlastníka aplikace, například **Personální oddělení**.
    - **Poznámky** – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Nahrát ikonu** – nahrajte ikonu, která se zobrazí u aplikace, když uživatelé procházejí portál společnosti.
3.  Po dokončení klikněte na **OK**.

## <a name="configure-app-settings"></a>Konfigurace nastavení aplikace

V tomto kroku nakonfigurujte možnosti instalace pro sadu aplikací. Nastavení budou platit pro všechny aplikace přidané k sadě.

1.  V okně **Přidat aplikaci** zvolte možnost pro **nastavení sady aplikací**.
2.  V okně s **nastavením sady aplikací** zadejte následující informace: 
    - **Verze Office** – vyberte, jestli chcete přiřadit 32bitovou nebo 64bitovou verzi Office. 32bitovou verzi můžete nainstalovat na 32bitová i 64bitová zařízení, ale 64bitovou verzi můžete nainstalovat jenom na 64bitová zařízení.
    - **Kanál aktualizací** – zvolte, jak se na těchto zařízeních aktualizuje Office. Informace o jiných kanálech aktualizací najdete v tématu Přehled kanálů aktualizací pro Office 365 ProPlus. Vybírejte z těchto možností: 
        - **Current**
        - **Deferred**
        - **Current Channel pro nové verze**
        - **Deferred Channel pro nové verze**
    - **Automaticky přijmout licenční smlouvu s koncovým uživatelem aplikace** – tuto možnost vyberte, pokud nevyžadujete přijetí licenční smlouvy koncovými uživateli. Intune pak smlouvu přijme automaticky.
    - **Použít aktivaci pro sdílené počítače** – aktivace pro sdílené počítače se používá, když počítač sdílí více uživatelů. Další informace najdete v Přehledu aktivace pro sdílené počítače pro Office 365 ProPlus.
    - **Jazyky** – Office se automaticky nainstaluje ve všech podporovaných jazycích nainstalovaných s Windows na zařízení koncových uživatelů. Tuto možnost zvolte, pokud chcete nainstalovat se sadou aplikací další jazyky.

>[!IMPORTANT]
> Vlastnosti již vytvořené sady aplikací není možné upravit. Pokud chcete nakonfigurovat jiné vlastnosti, odstraňte sadu aplikací a vytvořte novou.

## <a name="finish-up"></a>Dokončení

Až skončíte, zvolte v okně **Přidat aplikaci** možnost **Uložit**. Aplikace, kterou jste vytvořili, se zobrazí v seznamu aplikací.

## <a name="error-codes-when-installing-the-app-suite"></a>Kódy chyb při instalaci sady aplikací

V následující tabulce jsou uvedené běžné kódy chyb, se kterými se můžete setkat, a jejich význam.

### <a name="status-for-office-csp"></a>Stav pro Office CSP: 

||||
|-|-|-|
|Stav|Fáze|Popis|
|1460 (ERROR_TIMEOUT)|Stažení|Nepodařilo se stáhnout nástroj pro nasazení Office.|    
|13 (ERROR_INVALID_DATA)|-|Nelze ověřit podpis staženého nástroje pro nasazení Office.| 
|Kód chyby z CertVerifyCertificateChainPolicy|-|Nezdařila se kontrola certifikace staženého nástroje pro nasazení Office.|    
|997|WIP|Instalace| 
|0|Po instalaci|Instalace proběhla úspěšně.|    
|1603 (ERROR_INSTALL_FAILURE)|-|Nezdařila se kontrola předpokladů, například:<br>– SxS (pokus o instalaci, když je nainstalovaná MSI 2016)<br>– neshoda verzí<br>– atd.|     
|0x8000ffff (E_UNEXPECTED)|-|Pokus odinstalovat, když na počítači není technologie Office Klikni a spusť|    
|17002|-|Scénář se nepodařilo dokončit (nainstalovat). Možné důvody:<br>– Instalace zrušena uživatelem<br>– Instalace zrušena jinou instalací<br>– Nedostatek místa na disku během instalace<br>– Neznámý identifikátor jazyka| 
|17004|-|Neznámé skladové položky|   


### <a name="office-deployment-tool-error-codes"></a>Kódy chyb nástroje pro nasazení Office

|||||
|-|-|-|-|
|Scénář|Návratový kód|Uživatelské rozhraní|Poznámka| 
|Pokus odinstalovat bez aktivní instalace Klikni a spusť|-2147418113, 0x8000ffff nebo 2147549183|Kód chyby: 30088-1008<br>Kód chyby: 30125-1011 (404)|Nástroj pro nasazení systému Office| 
|Instalace, když je nainstalovaná verze MSI|1603|-|Nástroj pro nasazení systému Office| 
|Instalace byla zrušena uživatelem nebo jinou instalací.|17002|-|Klikni a spusť| 
|Pokus nainstalovat 64bitovou verzi na zařízení, na kterém je nainstalovaná 32bitová verze.|1603|-|Návratový kód nástroje pro nasazení Office| 
|Pokus nainstalovat neznámou skladovou položku (případ neoprávněného použití Office CSP, protože je nutné předávat jenom platné skladové položky)|17004|-|Klikni a spusť| 
|Nedostatek místa|17002|-|Klikni a spusť| 
|Klienta s technologií Klikni a spusť se nepodařilo spustit (neočekávané)|17000|-|Klikni a spusť| 
|U klienta s technologií Klikni a spusť se nepodařilo zařadit scénář do fronty (neočekávané)|17001|-|Klikni a spusť| 

## <a name="next-steps"></a>Další kroky

Nyní můžete přiřadit aplikace do skupin podle vlastního výběru. Nápovědu najdete v článku [Přiřazení aplikací do skupin](/intune-azure/manage-apps/deploy-apps).

             


