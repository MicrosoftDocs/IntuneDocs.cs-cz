---
title: "Správa hromadně zakoupených aplikací pro iOS | Microsoft Docs"
titlesuffix: Azure portal
description: "Zjistěte, jak synchronizovat s Intune aplikace zakoupené v rámci multilicenčního programu z App Storu pro zařízení s iOSem a jak následně spravovat a sledovat jejich používání."
keywords: 
author: erikre
ms.author: erikre
manager: dougeby
ms.date: 01/30/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dc5ebd90483b0fa0e25461574085bd4160f012ea
ms.sourcegitcommit: a6fd6b3df8e96673bc2ea48a2b9bda0cf0a875ae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/03/2018
---
# <a name="how-to-manage-ios-apps-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Správa aplikací pro systém iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

App Store pro iOS umožňuje pro aplikace, které chcete spouštět ve vaší společnosti, nakoupit víc licencí. Zakoupením více kopií můžete efektivně spravovat aplikace ve vaší společnosti.

Microsoft Intune pomáhá spravovat více kopií aplikací koupených prostřednictvím tohoto programu:

- Vykazuje informace o licencích z App Storu.
- Sleduje počet použitých licencí.
- Pomáhá zajistit, abyste nenainstalovali více kopií aplikace, než vlastníte.

Hromadně zakoupené aplikace můžete přiřadit dvěma způsoby:

### <a name="device-licensing"></a>Licencování zařízení

Když aplikaci přiřadíte k zařízením, použije se jedna licence aplikace, která zůstane spojená se zařízením, jemuž jste ji přiřadili.

Když k zařízení přiřadíte hromadně zakoupené aplikace, nemusí koncový uživatel zařízení zadávat Apple ID pro přístup do obchodu.

### <a name="user-licensing"></a>Licencování uživatelů

Když aplikaci přiřadíte uživateli, použije se jedna licence aplikace, která bude s uživatelem spojená. Tato aplikace může být spuštěna na více zařízeních, která uživatel vlastní (s limitem, který určuje Apple).

Když uživatelům přiřadíte hromadně zakoupenou aplikaci, musí mít každý koncový uživatel platné a jedinečné Apple ID pro přístup k App Storu.

V Intune také můžete synchronizovat, spravovat a přiřazovat knihy, které jste koupili v rámci programu Apple Volume Purchase Program (VPP). Další informace najdete v článku [Správa e-knih pro iOS zakoupených v rámci multilicenčního programu](vpp-ebooks-ios.md).

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Správa hromadně koupených aplikací pro zařízení s iOSem

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps-for-ios-devices"></a>Podpora hromadně zakoupených aplikací pro zařízení s iOSem prostřednictvím programu Apple Volume Purchase Program

Nákup více licencí k aplikacím pro iOS je možný prostřednictvím programu [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) nebo [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Součástí tohoto procesu je vytvoření účtu Apple VPP na webu Apple a odeslání tokenu Apple VPP do Intune.  Potom je možné synchronizovat informace o hromadném nákupu s Intune a sledovat využití aplikací, které jste tímto způsobem koupili.

### <a name="supports-business-to-business-volume-purchased-apps-for-ios-devices"></a>Podpora hromadně zakoupených aplikací pro zařízení s iOSem v rámci spolupráce mezi firmami

Vývojáři třetích stran mohou také navíc soukromě distribuovat aplikace autorizovaným členům programu Volume Purchase Program (VPP) for Business, kteří jsou uvedeni ve službě iTunes Connect. Tito členové programu VPP for Business se mohou přihlásit do zvláštního App Storu pro tento program a aplikace si zakoupit. Aplikace VPP for Business zakoupené koncovým uživatelem se potom synchronizují jeho tenantům Intune.

## <a name="before-you-start"></a>Než začnete
Než začnete, potřebujete od společnosti Apple získat token VPP a nahrát ho do svého účtu Intune. Měli byste se také seznámit s následujícími kritérii:

* K účtu Intune můžete přiřadit více tokenů VPP.
* Pokud jste už dřív použili token VPP s jiným produktem, musíte pro Intune vygenerovat nový token.
* Tokeny mají platnost jeden rok.
* Ve výchozím nastavení se Intune synchronizuje se službou Apple VPP dvakrát denně. Ruční synchronizaci můžete spustit kdykoli.
* Než začnete používat Apple VPP s Intune, odeberte všechny existující uživatelské účty VPP vytvořené pomocí jiných řešení správy zařízení (MDM). V rámci bezpečnostních opatření Intune nesynchronizuje tyto uživatelské účty do Intune. Intune synchronizuje jenom data služby Apple VPP vytvořená službou Intune.
* Intune podporuje přidání až 256 tokenů VPP.
* Program Profil registrace zařízení (DEP) společnosti Apple automatizuje registraci správy mobilních zařízení (MDM). Pomocí programu DEP můžete nakonfigurovat podniková zařízení bezkontaktně. Do programu DEP se můžete zaregistrovat pomocí stejného účtu agenta programu, který jste použili s programem VPP společnosti Apple. ID programu Apple Deployment Program je jedinečné pro programy uvedené na webu v části [Apple Deployment Programs](https://deploy.apple.com) a nelze ho použít pro přihlášení ke službám společnosti Apple, jako je například obchod iTunes.
* Když uživatelům nebo zařízením (přiřazeným uživatelům) na základě modelu poskytování uživatelských licencí přiřazujete aplikace získané v rámci programu VPP, musí mít každý uživatel Intune, který na svém zařízení potvrdí smluvní podmínky společnosti Apple, přiřazeno jedinečné Apple ID nebo e-mailovou adresu. Dbejte na to, abyste při nastavování zařízení pro nového uživatele Intune nakonfigurovali jedinečné Apple ID nebo e-mailovou adresu. Apple ID nebo e-mailová adresa a uživatel Intune tvoří jedinečný pár, který lze použít až pro pět zařízení.
* Token VPP se dá použít vždy jen v jednom účtu Intune. Proto nepoužívejte stejný token VPP ve více tenantech Intune.
* Když uživatelům nebo zařízením (přiřazeným uživatelům) na základě modelu poskytování uživatelských licencí přiřazujete aplikace získané v rámci programu VPP, musí mít každý uživatel Intune, který na svém zařízení potvrdí smluvní podmínky společnosti Apple, přiřazeno jedinečné Apple ID nebo e-mailovou adresu.
Dbejte na to, abyste při nastavování zařízení pro nového uživatele Intune nakonfigurovali jedinečné Apple ID nebo e-mailovou adresu. Apple ID nebo e-mailová adresa a uživatel Intune tvoří jedinečný pár, který jde použít až pro pět zařízení.

>[!IMPORTANT]
>Po naimportování tokenu VPP do Intune neimportujte stejný token do žádného jiného řešení správy zařízení. Pokud byste to udělali, mohli byste ztratit přiřazení licence a uživatelských záznamů.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Získání a odeslání tokenu Apple VPP

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
1.  V okně **Intune** v části **Nastavení** zvolte **Mobilní aplikace** > **Tokeny VPP pro iOS**.
2.  V okně se seznamem tokenů VPP vyberte možnost **Vytvořit**.
4. V okně **Vytvořit token VPP** zadejte následující informace:
    - **Soubor tokenu VPP** – pokud jste to ještě neudělali, zaregistrujte se do programu Volume Purchase Program for Business nebo Volume Purchase Program for Education. Po zaregistrování si stáhněte token Apple VPP pro svůj účet a vyberte ho tady.
    - **Apple ID** – zadejte Apple ID účtu přidruženého k multilicenčnímu programu.
    - **Země/oblast** – vyberte regionální VPP Store.  Intune synchronizuje aplikace VPP pro všechna národní prostředí z určeného regionálního VPP Storu.
        > [!WARNING]  
        > Po změně země se u aplikací vytvořených pomocí tohoto tokenu při příští synchronizaci se službou Apple aktualizují metadata aplikací a adresa URL Storu. Pokud aplikace v novém regionálním Storu neexistuje, neaktualizuje se.

    - **Typ účtu VPP** – zvolte jednu z možností: **Obchodní** nebo **Vzdělávání**.
    - **Automatické aktualizace aplikací** – Přepnutím ze **Zapnuto** na **Vypnuto** povolíte automatické aktualizace. Když jsou povolené, Intune aktualizuje všechny aplikace zakoupené pro konkrétní token prostřednictvím služby Intune, jakmile se zařízení ohlásí.
Intune zjistí aktualizace aplikací VPP v App Storu a automaticky je nabídne zařízení, jakmile se zařízení ohlásí.
4. Po dokončení vyberte **Nahrát**.

Token se zobrazí v okně se seznamem tokenů.

Data ukládaná společností Apple můžete kdykoli synchronizovat s Intune výběrem položky **Synchronizovat nyní**.

## <a name="to-assign-a-volume-purchased-app"></a>Přiřazení aplikace zakoupené v rámci multilicenčního programu

1.  V okně **Intune** zvolte v části **Spravovat** **Mobilní aplikace** > **Aplikace**.
2.  V okně se seznamem aplikací zvolte aplikaci, kterou chcete přiřadit, a pak zvolte **Přiřazení**.
3.  V okně ***Název aplikace*** - **Přiřazení** zvolte **Vybrat skupiny** a pak v okně **Vybrat skupiny** zvolte skupiny uživatelů nebo zařízení Azure AD, ke kterým chcete aplikaci přiřadit.
5.  Pro každou zvolenou skupinu vyberte následující nastavení:
    - **Typ** – vyberte, jestli bude aplikace **k dispozici** (koncoví uživatelé můžou aplikaci nainstalovat z Portálu společnosti), nebo **povinná** (aplikace se na zařízení koncových uživatelů nainstaluje automaticky).
    - **Typ licence** – vyberte **Licencování uživatelů** nebo **Licencování zařízení**.
6.  Až to budete mít, zvolte **Uložit**.


>[!NOTE]
>V seznamu zobrazené aplikace jsou přidružené k tokenu. Pokud máte aplikaci, která je spojená s více tokeny VPP, zobrazí se stejná aplikace několikrát – jednou u každého tokenu.

## <a name="end-user-prompts-for-vpp"></a>Výzvy k VPP pro koncové uživatele

Koncový uživatel obdrží výzvu k instalaci aplikace v rámci VPP v řadě scénářů. Jednotlivé podmínky jsou vysvětlené v tabulce:

| # | Scénář                                | Pozvánka do programu Apple VPP                              | Výzva při instalaci aplikace | Výzva k zadání Apple ID |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1 | Vlastní zařízení – licencovaný uživatel                             | A                                                                                               | A                                           | A                                 |
| 2 | Zařízení společnosti – licencovaný uživatel (zařízení není pod dohledem)     | A                                                                                               | A                                           | A                                 |
| 3 | Zařízení společnosti – licencovaný uživatel (zařízení pod dohledem)         | A                                                                                               | N                                           | A                                 |
| 4 | Vlastní zařízení – licencované zařízení                           | N                                                                                               | A                                           | N                                 |
| 5 | Zařízení společnosti – licencované zařízení (zařízení není pod dohledem)                           | N                                                                                               | A                                           | N                                 |
| 6 | Zařízení společnosti – licencované zařízení (zařízení pod dohledem)                           | N                                                                                               | N                                           | N                                 |
| 7 | Beznabídkový režim (zařízení pod dohledem) – licencované zařízení | N                                                                                               | N                                           | N                                 |
| 8 | Beznabídkový režim (zařízení pod dohledem) – licencovaný uživatel   | --- | ---                                          | ---                                |

> [!Note]  
> Nedoporučujeme přiřazovat aplikace VPP zařízením s beznabídkovým režimem pomocí licencování uživatelů v rámci VPP.

## <a name="revoking-app-licenses-and-deleting-tokens"></a>Odvolání licencí aplikací a odstranění tokenů 

<!-- 820863 -->For a given device that has one or more iOS volume-purchase program (VPP) apps, you revoke all associated device-based app licenses for the device. Revoking an app license will not uninstall the related VPP app from the device. To uninstall a VPP app and reclaim a license, you must change the assignment type of the VPP app to **Uninstall**. If you remove an app that was assigned to a user, Intune reclaims the user or device license and uninstallS the app from the device.

>[!NOTE]
>Když zaměstnanec opustí společnost a není už členem skupin AAD, Intune odvolá všechny licence aplikací programu VPP pro iOS daného uživatele.

<!-- 820879 -->You can delete a iOS Volume Purchasing Program (VPP) token using the console. This may be necessary when you have duplicate instances of a VPP token. Deleting a token will also delete any associated apps and assignment. However, deleting a token does not revoke app licenses or uninstall apps. 

>[!NOTE]
>Po odstranění tokenu nemůže Intune odvolat licence aplikací. 

<!-- 820870 -->To revoke the license of all VPP apps for a given VPP token, you must first revoke all app licenses associated with the token, then delete the token.

## <a name="further-information"></a>Další informace

Když se uživatel s oprávněným zařízením poprvé pokusí do zařízení nainstalovat aplikaci programu VPP, zobrazí se výzva k účasti v programu Apple Volume Purchase Program (VPP). Aby mohla instalace pokračovat, musí uživatel potvrdit svou účast. Aby se mohl uživatel připojit do programu Apple Volume Purchase Program, musí používat na zařízení s iOSem aplikaci iTunes. Pokud jste nastavili zásadu, která zakazuje aplikace z iTunes Storu, nebude licencování založené na uživatelích pro aplikace z programu VPP fungovat. Řešením je odebrat zásady a povolit tak aplikaci iTunes nebo použít licencování na základě zařízení.

## <a name="next-steps"></a>Další kroky

Informace, s kterými budete moct lépe sledovat přiřazování aplikací, najdete v článku [Jak sledovat přiřazení aplikací](apps-monitor.md).
