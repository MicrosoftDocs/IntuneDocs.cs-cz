---
title: "Správa hromadně zakoupených aplikací pro iOS | Dokumentace Microsoftu"
titlesuffix: Azure portal
description: "Zjistěte, jak synchronizovat s Intune aplikace zakoupené v rámci multilicenčního programu z App Storu pro zařízení s iOSem a jak následně spravovat a sledovat jejich používání."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 76764155e66ab69b5428712dae8a860233acaeb6
ms.sourcegitcommit: 751587b1c6ed15877152d770772748e042c1e3ff
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/13/2017
---
# <a name="how-to-manage-ios-apps-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Správa aplikací pro systém iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

App Store pro iOS umožňuje pro aplikace, které chcete spouštět ve vaší společnosti, nakoupit víc licencí. Nákupem více kopií aplikace snížíte administrativní režii potřebnou ke sledování více zakoupených kopií aplikací.

Microsoft Intune pomáhá spravovat aplikace koupené prostřednictvím tohoto programu:

- Vykazuje informace o licencích z App Storu.
- Sleduje počet použitých licencí.
- Pomáhá zajistit, abyste nenainstalovali více kopií aplikace, než vlastníte.

Hromadně zakoupené aplikace můžete přiřadit dvěma způsoby:

### <a name="device-licensing"></a>Licencování zařízení

Když aplikaci přiřadíte k zařízením, použije se jedna licence aplikace, která zůstane spojená se zařízením, jemuž jste ji přiřadili.
Když k zařízení přiřadíte hromadně zakoupené aplikace, nemusí koncový uživatel zařízení zadávat Apple ID pro přístup do obchodu. 



### <a name="user-licensing"></a>Licencování uživatelů

Když aplikaci přiřadíte k uživatelům, použije se jedna licence aplikace, která bude spojená s uživatelem. Tato aplikace může být spuštěna na více zařízeních, která uživatel vlastní (s limitem, který určuje Apple).
Když uživatelům přiřadíte hromadně zakoupenou aplikaci, musí mít každý koncový uživatel platné a jedinečné Apple ID pro přístup k App Storu.

V Intune také můžete synchronizovat, spravovat a přiřazovat knihy, které jste koupili v Apple Storu v rámci multilicenčního programu. Další informace najdete v článku [Správa e-knih pro iOS zakoupených v rámci multilicenčního programu](vpp-ebooks-ios.md).

## <a name="manage-volume-purchased-apps-for-ios-devices"></a>Správa hromadně koupených aplikací pro zařízení s iOSem

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps-for-ios-devices"></a>Podpora hromadně zakoupených aplikací pro zařízení s iOSem prostřednictvím programu Apple Volume Purchase Program

Nákup více licencí k aplikacím pro iOS je možný prostřednictvím programu [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) nebo [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Součástí tohoto procesu je vytvoření účtu Apple VPP na webu Apple a odeslání tokenu Apple VPP do Intune.  Potom je možné synchronizovat informace o hromadném nákupu s Intune a sledovat využití aplikací, které jste tímto způsobem koupili.

### <a name="supports-business-to-business-volume-purchased-apps-for-ios-devices"></a>Podpora hromadně zakoupených aplikací pro zařízení s iOSem v rámci spolupráce mezi firmami

Vývojáři třetích stran mohou také navíc soukromě distribuovat aplikace autorizovaným členům programu Volume Purchase Program (VPP) for Business, kteří jsou uvedeni ve službě iTunes Connect. Tito členové programu VPP for Business se mohou přihlásit do zvláštního App Storu pro tento program a aplikace si zakoupit. Aplikace VPP for Business zakoupené koncovým uživatelem se potom synchronizují jeho tenantům Intune.

## <a name="before-you-start"></a>Než začnete
Než začnete, potřebujete od společnosti Apple získat token VPP a nahrát ho do svého účtu Intune. Měli byste se také seznámit s následujícími kritérii:

* Ke svému účtu Intune můžete přidružit několik tokenů multilicenčního programu.
* Pokud jste už dřív použili token VPP s jiným produktem, musíte pro Intune vygenerovat nový token.
* Tokeny mají platnost jeden rok.
* Ve výchozím nastavení se Intune synchronizuje se službou Apple VPP dvakrát denně. Ruční synchronizaci můžete spustit kdykoli.
* Než začnete používat iOS VPP s Intune, odeberte všechny existující uživatelské účty VPP vytvořené pomocí jiných řešení správy zařízení (MDM). V rámci bezpečnostních opatření Intune nesynchronizuje tyto uživatelské účty do Intune. Intune synchronizuje jenom data služby Apple VPP vytvořená službou Intune.
* Intune podporuje přidání až 256 tokenů VPP.
* Program Profil registrace zařízení (DEP) společnosti Apple automatizuje registraci správy mobilních zařízení (MDM). Pomocí programu DEP můžete nakonfigurovat podniková zařízení bezkontaktně. Do programu DEP se můžete zaregistrovat pomocí stejného účtu agenta programu, který jste použili s programem VPP společnosti Apple. ID programu Apple Deployment Program je jedinečné pro programy uvedené na webu v části [Apple Deployment Programs](https://deploy.apple.com) a nelze ho použít pro přihlášení ke službám společnosti Apple, jako je například obchod iTunes. 
* Když uživatelům nebo zařízením (přiřazeným uživatelům) na základě modelu poskytování uživatelských licencí přiřazujete aplikace získané v rámci programu VPP, musí mít každý uživatel Intune, který na svém zařízení potvrdí smluvní podmínky společnosti Apple, přiřazeno jedinečné Apple ID nebo e-mailovou adresu. Dbejte na to, abyste při nastavování zařízení pro nového uživatele Intune nakonfigurovali jedinečné Apple ID nebo e-mailovou adresu. Apple ID nebo e-mailová adresa a uživatel Intune tvoří jedinečný pár, který lze použít až pro pět zařízení.
* Token VPP se dá použít vždy jen v jednom účtu Intune. Proto nepoužívejte stejný token VPP ve více tenantech Intune.

>[!IMPORTANT]
>Po naimportování tokenu VPP do Intune neimportujte stejný token do žádného jiného řešení správy zařízení. Pokud byste to udělali, mohli byste ztratit přiřazení licence a uživatelských záznamů.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Získání a odeslání tokenu Apple VPP

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
2.  V okně se seznamem tokenů VPP klikněte na **Vytvořit**.
4. V okně **Vytvořit token VPP** zadejte následující informace:
    - **Soubor tokenu VPP** – pokud jste to ještě neudělali, zaregistrujte se do programu Volume Purchase Program for Business nebo Volume Purchase Program for Education. Po zaregistrování si stáhněte token Apple VPP pro svůj účet a vyberte ho tady.
    - **Automatické aktualizace aplikací** – Přepnutím ze **Zapnuto** na **Vypnuto** povolíte automatické aktualizace. Když jsou povolené, Intune aktualizuje všechny aplikace zakoupené pro konkrétní token prostřednictvím služby Intune, jakmile se zařízení ohlásí. Intune zjistí aktualizace aplikací VPP v App Storu a automaticky je nabídne zařízení, jakmile se zařízení ohlásí.
4. Po dokončení klikněte na **Nahrát**.

Token se zobrazí v okně se seznamem tokenů.

Data ukládaná společností Apple můžete kdykoli synchronizovat s Intune výběrem položky **Synchronizovat nyní**.

> [!NOTE]
> Microsoft Intune synchronizuje jenom informace o aplikacích, které jsou veřejně dostupné prostřednictvím iTunes Storu. **Vlastní B2B aplikace pro iOS** se zatím nepodporují. Pokud tento scénář platí pro vaše aplikace, nebudou se informace o aplikaci synchronizovat.

## <a name="to-assign-a-volume-purchased-app"></a>Přiřazení aplikace zakoupené v rámci multilicenčního programu

1.  V okně **Intune** zvolte v části **Spravovat** **Mobilní aplikace** > **Aplikace**.
2.  V okně se seznamem aplikací zvolte aplikaci, kterou chcete přiřadit, a pak zvolte **Přiřazení**.
3.  V okně ***Název aplikace*** - **Přiřazení** zvolte **Vybrat skupiny** a pak v okně **Vybrat skupiny** zvolte skupiny uživatelů nebo zařízení Azure AD, ke kterým chcete aplikaci přiřadit.
5.  Pro každou zvolenou skupinu vyberte následující nastavení:
    - **Typ** – vyberte, jestli bude aplikace **k dispozici** (koncoví uživatelé mohou aplikaci nainstalovat z Portálu společnosti), nebo **povinná** (aplikace se na zařízení koncových uživatelů nainstaluje automaticky).
    - **Typ licence** – vyberte **Licencování uživatelů** nebo **Licencování zařízení**.
6.  Až to budete mít, zvolte **Uložit**.


>[!NOTE]
>V seznamu zobrazené aplikace jsou přidružené k tokenu. Pokud máte aplikaci, která je spojená s více tokeny VPP, zobrazí se stejná aplikace několikrát – jednou u každého tokenu.

## <a name="further-information"></a>Další informace

Když chcete licenci získat zpět, musíte nastavit akci přiřazení na Odinstalovat. Až se aplikace odinstaluje, licence se uvolní. Pokud odeberete aplikaci, která byla přiřazena uživateli, pokusí se Intune uvolnit všechny licence aplikace, které byly k tomuto uživateli přidruženy.

Když se uživatel s oprávněným zařízením poprvé pokusí do zařízení nainstalovat aplikaci programu VPP, zobrazí se výzva k účasti v programu Apple Volume Purchase Program (VPP). Aby mohla instalace pokračovat, musí uživatel potvrdit svou účast. Aby se mohl uživatel připojit do programu Apple Volume Purchase Program, musí používat na zařízení s iOSem aplikaci iTunes. Pokud jste nastavili zásadu, která zakazuje aplikace z iTunes Storu, nebude licencování založené na uživatelích pro aplikace z programu VPP fungovat. Řešením je odebrat zásady a povolit tak aplikaci iTunes nebo použít licencování na základě zařízení.



## <a name="next-steps"></a>Další kroky

Informace, s kterými budete moct lépe sledovat přiřazování aplikací, najdete v článku [Jak sledovat přiřazení aplikací](apps-monitor.md).