---
title: Správa aplikací pro iOS zakoupených v rámci multilicenčního programu v Microsoft Intune
titlesuffix: ''
description: Zjistěte, jak s Microsoft Intune synchronizovat aplikace zakoupené v rámci multilicenčního programu z obchodu pro iOS a jak následně spravovat a sledovat jejich používání.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/15/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 122f0b70392df65076622354722b6d546f4fe7b7
ms.sourcegitcommit: 34e96e57af6b861ecdfea085acf3c44cff1f3d43
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/17/2018
---
# <a name="how-to-manage-ios-apps-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Správa aplikací pro systém iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
1.  V podokně **Intune** v části **Nastavení** zvolte **Mobilní aplikace** > **Tokeny VPP pro iOS**.
2.  V podokně s tokeny VPP vyberte **Vytvořit**.
4. V podokně **Vytvořit token VPP** zadejte následující informace:
    - **Soubor tokenu VPP** – pokud jste to ještě neudělali, zaregistrujte se do programu Volume Purchase Program for Business nebo Volume Purchase Program for Education. Po zaregistrování si stáhněte token Apple VPP pro svůj účet a vyberte ho tady.
    - **Apple ID** – zadejte Apple ID účtu přidruženého k multilicenčnímu programu.
    - **Země/oblast** – vyberte regionální VPP Store.  Intune synchronizuje aplikace VPP pro všechna národní prostředí z určeného regionálního VPP Storu.
        > [!WARNING]  
        > Po změně země se u aplikací vytvořených pomocí tohoto tokenu při příští synchronizaci se službou Apple aktualizují metadata aplikací a adresa URL Storu. Pokud aplikace v novém regionálním Storu neexistuje, neaktualizuje se.

    - **Typ účtu VPP** – zvolte jednu z možností: **Obchodní** nebo **Vzdělávání**.
    - **Automatické aktualizace aplikací** – Přepnutím ze **Zapnuto** na **Vypnuto** povolíte automatické aktualizace. Když jsou povolené, Intune aktualizuje všechny aplikace zakoupené pro konkrétní token prostřednictvím služby Intune, jakmile se zařízení ohlásí.
Intune zjistí aktualizace aplikací VPP v App Storu a automaticky je nabídne zařízení, jakmile se zařízení ohlásí.
4. Až to budete mít, vyberte **Vytvořit**.

Token se zobrazí v podokně se seznamem tokenů.

Data ukládaná společností Apple můžete kdykoli synchronizovat s Intune výběrem položky **Synchronizovat nyní**.

## <a name="to-assign-a-volume-purchased-app"></a>Přiřazení aplikace zakoupené v rámci multilicenčního programu

1.  V podokně **Intune** v části **Spravovat** zvolte **Mobilní aplikace** > **Aplikace**.
2.  V podokně se seznamem aplikací zvolte aplikaci, kterou chcete přiřadit, a pak zvolte **Přiřazení**.
3.  V podokně ***Název aplikace*** - **Přiřazení** zvolte **Přidat skupinu** a pak v podokně **Přidat skupinu** zvolte **Typ přiřazení** a skupiny uživatelů nebo zařízení Azure AD, ke kterým chcete aplikaci přiřadit.
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

<!-- 820863 -->  
Pro dané zařízení, které má jednu nebo více aplikací pro iOS koupených přes Volume Purchase Program (VPP), můžete odvolat všechny licence aplikací přidružené na základě zařízení. Odvoláním licence aplikace se příslušná aplikace VPP neodinstaluje ze zařízení. Pokud chcete odinstalovat aplikaci VPP a získat licenci zpět, je nutné změnit typ přiřazení aplikace VPP na **Odinstalovat**. Pokud odeberete aplikaci, která byla přiřazena uživateli, Intune získá zpět licenci uživatele nebo zařízení a odinstaluje aplikaci ze zařízení.

>[!NOTE]
>Když zaměstnanec opustí společnost a není už členem skupin AAD, Intune odvolá všechny licence aplikací programu VPP pro iOS daného uživatele.

<!-- 820879 -->  
K odstranění tokenu programu Volume Purchasing Program (VPP) pro iOS můžete použít konzolu. To může být nutné v případě, že máte duplicitní instance tokenu VPP. Odstraněním tokenu se odstraní také všechny přidružené aplikace a přiřazení. Odstraněním tokenu se ale licence aplikací neodvolají ani aplikace neodinstalují. 

>[!NOTE]
>Po odstranění tokenu nemůže Intune odvolat licence aplikací. 

<!-- 820870 -->  
K odvolání licencí všech aplikací VPP pro daný token VPP je nutné nejprve odvolat všechny licence aplikací, které jsou k tomuto tokenu přidružené, a potom daný token odstranit.

## <a name="further-information"></a>Další informace

Když se uživatel s oprávněným zařízením poprvé pokusí do zařízení nainstalovat aplikaci programu VPP, zobrazí se výzva k účasti v programu Apple Volume Purchase Program (VPP). Aby mohla instalace pokračovat, musí uživatel potvrdit svou účast. Aby se mohl uživatel připojit do programu Apple Volume Purchase Program, musí používat na zařízení s iOSem aplikaci iTunes. Pokud jste nastavili zásadu, která zakazuje aplikace z iTunes Storu, nebude licencování založené na uživatelích pro aplikace z programu VPP fungovat. Řešením je odebrat zásady a povolit tak aplikaci iTunes nebo použít licencování na základě zařízení.

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

#### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Jak dlouho trvá, než portál po instalaci aplikace nebo jejím odebrání ze zařízení aktualizuje počet licencí?
Licence by se měly aktualizovat do několika hodin od instalace nebo odinstalace aplikace. Je třeba mít na paměti, že pokud koncový uživatel odebere aplikaci ze zařízení, zůstává licence danému uživateli nebo zařízení stále přiřazená.

#### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>Je možné přidělit aplikaci nadměrnému počtu subjektů? A pokud ano, za jakých okolností?
Ano. Správce Intune může aplikaci přidělit nadměrnému počtu uživatelů nebo zařízení. A to například tehdy, když zakoupí sto licencí k aplikaci XYZ a potom ji zacílí na skupinu s pěti sty členy. Prvnímu stu členů (uživatelům nebo zařízením) se licence přiřadí a u zbylých členů se přiřazení licence nezdaří.

#### <a name="i-understand-intune-automatically-syncs-app-licenses-each-day-with-apple-is-that-correct"></a>Chápu správně, že Intune automaticky synchronizuje licence aplikací s Apple každý den?
Intune synchronizuje licence aplikací s Apple každých 15 hodin.

## <a name="next-steps"></a>Další kroky

Informace, s kterými budete moct lépe sledovat přiřazování aplikací, najdete v článku [Jak sledovat přiřazení aplikací](apps-monitor.md).
