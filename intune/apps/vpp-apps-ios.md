---
title: Správa hromadně zakoupených aplikací Apple
titleSuffix: Microsoft Intune
description: Přečtěte si, jak synchronizovat aplikace zakoupené v rámci multilicenčního programu z obchodu iOS a macOS App Storu do Microsoft Intune a pak můžete spravovat a sledovat jejich používání.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 08/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a63bf187d0774b9f50351b45e53095d994720878
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72496658"
---
# <a name="how-to-manage-ios-and-macos-apps-purchased-through-apple-volume-purchase-program-with-microsoft-intune"></a>Jak spravovat aplikace pro iOS a macOS zakoupené prostřednictvím Apple Volume Purchase Program s využitím Microsoft Intune


[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Apple vám umožní nakoupit více licencí pro aplikaci, kterou chcete ve vaší firmě spustit na zařízeních s iOS a macOS. Zakoupením více kopií můžete efektivně spravovat aplikace ve vaší společnosti.

Microsoft Intune pomáhá spravovat více kopií aplikací koupených prostřednictvím tohoto programu:

- Vykazuje informace o licencích z App Storu.
- Sleduje počet použitých licencí.
- Pomáhá zajistit, abyste nenainstalovali více kopií aplikace, než vlastníte.

Hromadně zakoupené aplikace můžete přiřadit dvěma způsoby:

## <a name="device-licensing"></a>Licencování zařízení

Když aplikaci přiřadíte k zařízením, použije se jedna licence aplikace, která zůstane spojená se zařízením, jemuž jste ji přiřadili.

Když k zařízení přiřadíte hromadně zakoupené aplikace, nemusí koncový uživatel zařízení zadávat Apple ID pro přístup do obchodu.

## <a name="user-licensing"></a>Licencování uživatelů

Když aplikaci přiřadíte uživateli, použije se jedna licence aplikace, která bude s uživatelem spojená. Aplikaci lze spustit až na 5 zařízení, která uživatel vlastní (limit zařízení je řízen společností Apple).

Když uživatelům přiřadíte hromadně zakoupenou aplikaci, musí mít každý koncový uživatel platné a jedinečné Apple ID pro přístup k App Storu.

Kromě toho můžete synchronizovat, spravovat a přiřazovat knihy, které jste koupili v obchodě programu Apple Volume-purchase program (VPP), s Intune a zařízeními se systémem iOS. Další informace najdete v článku [Správa e-knih pro iOS zakoupených v rámci multilicenčního programu](vpp-ebooks-ios.md).

## <a name="manage-volume-purchased-apps-for-ios-and-macos-devices"></a>Správa hromadně koupených aplikací pro zařízení s iOS a macOS

### <a name="supports-apple-volume-purchase-program-volume-purchased-apps"></a>Podporuje Apple Volume Purchase Program hromadně zakoupených aplikací.

Zakupte více licencí pro aplikace iOS a macOS prostřednictvím [Apple Volume purchase program pro firmy](https://www.apple.com/business/vpp/) nebo [Apple Volume purchase program pro vzdělávání](https://volume.itunes.apple.com/us/store). Součástí tohoto procesu je vytvoření účtu Apple VPP na webu Apple a odeslání tokenu Apple VPP do Intune.  Potom je možné synchronizovat informace o hromadném nákupu s Intune a sledovat využití aplikací, které jste tímto způsobem koupili.

### <a name="supports-business-to-business-volume-purchased-apps"></a>Podporuje hromadně zakoupené aplikace pro firmy

Kromě toho můžou vývojáři třetích stran také soukromě distribuovat aplikace do autorizovaného programu Volume purchase program pro obchodní členy zadané v App Storu Connect. Tito členové programu VPP for Business se mohou přihlásit do zvláštního App Storu pro tento program a aplikace si zakoupit. Aplikace VPP for Business zakoupené koncovým uživatelem se potom synchronizují jeho tenantům Intune.

## <a name="before-you-start"></a>Než začnete
Než začnete, potřebujete od společnosti Apple získat token VPP a nahrát ho do svého účtu Intune. Měli byste se také seznámit s následujícími kritérii:

* K účtu Intune můžete přiřadit více tokenů VPP.
* Pokud jste už dřív použili token VPP s jiným produktem, musíte pro Intune vygenerovat nový token.
* Tokeny mají platnost jeden rok.
* Ve výchozím nastavení se Intune synchronizuje se službou Apple VPP dvakrát denně. Ruční synchronizaci můžete spustit kdykoli.
* Než začnete používat Apple VPP s Intune, odeberte všechny existující uživatelské účty VPP vytvořené pomocí jiných řešení správy zařízení (MDM). V rámci bezpečnostních opatření Intune nesynchronizuje tyto uživatelské účty do Intune. Intune synchronizuje jenom data služby Apple VPP vytvořená službou Intune.
* Intune podporuje přidání až 256 tokenů VPP.
* Program Profil registrace zařízení (DEP) společnosti Apple automatizuje registraci správy mobilních zařízení (MDM). Pomocí programu DEP můžete nakonfigurovat podniková zařízení bezkontaktně. Do programu DEP se můžete zaregistrovat pomocí stejného účtu agenta programu, který jste použili s programem VPP společnosti Apple. ID programu Apple Deployment Program je jedinečné pro programy uvedené na webu v části [Apple Deployment Programs](https://deploy.apple.com) a nelze ho použít pro přihlášení ke službám společnosti Apple, jako je například obchod iTunes.
* Když uživatelům nebo zařízením (přiřazeným uživatelům) na základě modelu poskytování uživatelských licencí přiřazujete aplikace získané v rámci programu VPP, musí mít každý uživatel Intune, který na svém zařízení potvrdí smluvní podmínky společnosti Apple, přiřazeno jedinečné Apple ID nebo e-mailovou adresu.
* Dbejte na to, abyste při nastavování zařízení pro nového uživatele Intune nakonfigurovali jedinečné Apple ID nebo e-mailovou adresu. Apple ID nebo e-mailová adresa a uživatel Intune tvoří jedinečný pár, který lze použít až pro pět zařízení.
* Token VPP se dá použít vždy jen v jednom účtu Intune. Proto nepoužívejte stejný token VPP ve více tenantech Intune.

>[!IMPORTANT]
>Po naimportování tokenu VPP do Intune neimportujte stejný token do žádného jiného řešení správy zařízení. Pokud byste to udělali, mohli byste ztratit přiřazení licence a uživatelských záznamů.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Získání a odeslání tokenu Apple VPP

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. V podokně **Intune** v části **Nastavení**vyberte **klientské aplikace** > **tokeny Apple VPP** .
4. V podokně s tokeny VPP vyberte **Vytvořit**.
5. V podokně **Vytvořit token VPP** zadejte následující informace:
    - **Soubor tokenu VPP** – pokud jste to ještě neudělali, zaregistrujte se do programu Volume Purchase Program for Business nebo Volume Purchase Program for Education. Po zaregistrování si stáhněte token Apple VPP pro svůj účet a vyberte ho tady.
    - **Apple ID** – zadejte Apple ID účtu přidruženého k multilicenčnímu programu.
    - **Země/oblast** – vyberte úložiště VPP země/oblast.  Intune synchronizuje aplikace VPP pro všechna národní prostředí ze zadaného úložiště v zemi nebo oblasti VPP.
        > [!WARNING]  
        > Když se změní země nebo oblast, aktualizují se metadata aplikace a adresa URL Storu při příští synchronizaci se službou Apple pro aplikace vytvořené pomocí tohoto tokenu. Aplikace nebude aktualizována, pokud neexistuje v úložišti nové země/oblast.

    - **Typ účtu VPP** – zvolte jednu z možností: **Obchodní** nebo **Vzdělávání**.
    - **Automatické aktualizace aplikací** – zvolte **Zapnuto** nebo **Vypnuto** podle toho, jestli chcete automatické aktualizace povolit nebo zakázat. Když je tato možnost povolená, Intune zjistí aktualizace aplikací VPP v App Storu a automaticky je odešle do zařízení, jakmile se ohlásí. Automatické aktualizace aplikací Apple VPP automaticky aktualizují jenom aplikace nasazené pomocí instalačního záměru **Povinné**. Pro aplikace nasazené s **dostupným** záměrem instalace vygeneruje funkce Automatické aktualizace oznámení pro správce informující o tom, že je k dispozici nová verze aplikace. Kromě toho uživatel uvidí tuto aplikaci jako nenainstalovanou na Portálu společnosti, i když je nainstalovaná starší verze aplikace. V takovém případě může uživatel aplikaci přeinstalovat kliknutím na tlačítko **nainstalovat** na obrazovce s podrobnostmi o aplikaci v aplikaci Portál společnosti pro instalaci novější verze aplikace.

        > [!NOTE]
        > Automatické aktualizace aplikací fungují pro aplikace i uživatele licencované pro iOS 11,0 a vyšší nebo macOS 10,12 a novější.
6. Až to budete mít, vyberte **Vytvořit**.

Token se zobrazí v podokně se seznamem tokenů.

Data ukládaná společností Apple můžete kdykoli synchronizovat s Intune výběrem položky **Synchronizovat nyní**.

## <a name="to-assign-a-volume-purchased-app"></a>Přiřazení aplikace zakoupené v rámci multilicenčního programu

1. V podokně **Intune** v části **Spravovat** zvolte **Klientské aplikace** > **Aplikace**.
2. V podokně se seznamem aplikací zvolte aplikaci, kterou chcete přiřadit, a pak zvolte **Přiřazení**.
3. V podokně ***Název aplikace*** - **Přiřazení** zvolte **Přidat skupinu** a pak v podokně **Přidat skupinu** zvolte **Typ přiřazení** a skupiny uživatelů nebo zařízení Azure AD, ke kterým chcete aplikaci přiřadit.
5. Pro každou zvolenou skupinu vyberte následující nastavení:
    - **Typ** – vyberte, jestli bude aplikace **k dispozici** (koncoví uživatelé můžou aplikaci nainstalovat z Portálu společnosti), nebo **povinná** (aplikace se na zařízení koncových uživatelů nainstaluje automaticky).
    - **Typ licence** – vyberte **Licencování uživatelů** nebo **Licencování zařízení**.
6. Až to budete mít, zvolte **Uložit**.


>[!NOTE]
>Dostupný záměr nasazení není pro skupiny zařízení podporován, jsou podporovány pouze skupiny uživatelů. V seznamu zobrazené aplikace jsou přidružené k tokenu. Pokud máte aplikaci, která je spojená s více tokeny VPP, zobrazí se stejná aplikace několikrát – jednou u každého tokenu.

## <a name="end-user-prompts-for-vpp"></a>Výzvy k VPP pro koncové uživatele

Koncový uživatel obdrží výzvu k instalaci aplikace v rámci VPP v řadě scénářů. Jednotlivé podmínky jsou vysvětlené v tabulce:

| # | Scénář                                | Pozvánka do programu Apple VPP                              | Výzva při instalaci aplikace | Výzva k zadání Apple ID |
|---|--------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------|-----------------------------------|
| 1 | Vlastní zařízení – licencovaný uživatel                             | Požadované                                                                                               | Požadované                                           | Požadované                                 |
| 2 | Zařízení společnosti – licencovaný uživatel (zařízení není pod dohledem)     | Požadované                                                                                               | Požadované                                           | Požadované                                 |
| 3 | Zařízení společnosti – licencovaný uživatel (zařízení pod dohledem)         | Požadované                                                                                               | N                                           | Požadované                                 |
| 4 | Vlastní zařízení – licencované zařízení                           | N                                                                                               | Požadované                                           | N                                 |
| 5 | Zařízení společnosti – licencované zařízení (zařízení není pod dohledem)                           | N                                                                                               | Požadované                                           | N                                 |
| 6 | Zařízení společnosti – licencované zařízení (zařízení pod dohledem)                           | N                                                                                               | N                                           | N                                 |
| 7 | Beznabídkový režim (zařízení pod dohledem) – licencované zařízení | N                                                                                               | N                                           | N                                 |
| 8 | Beznabídkový režim (zařízení pod dohledem) – licencovaný uživatel   | --- | ---                                          | ---                                |

> [!Note]  
> Nedoporučujeme přiřazovat aplikace VPP zařízením s beznabídkovým režimem pomocí licencování uživatelů v rámci VPP.

## <a name="revoking-app-licenses"></a>Odvolávání licencí aplikací

Můžete odvolat všechny přidružené licence aplikací pro iOS nebo macOS Volume-purchase program (VPP) na základě daného zařízení, uživatele nebo aplikace.  Existují však určité rozdíly mezi platformami iOS a macOS. 

### <a name="revoking-app-licenses-on-ios"></a>Odvolávání licencí aplikací v iOS
Uživatele můžete upozornit, že už nemají aplikaci přiřazenou. Pokud ale odvoláte licenci aplikace, nebude se v zařízení odinstalovat související aplikace VPP. Pokud chcete aplikaci VPP odinstalovat a uvolnit licenci aplikace, která byla přiřazena uživateli nebo zařízení, je nutné akci přiřazení změnit na **Odinstalovat**. Pokud odeberete aplikaci, která byla přiřazena uživateli, Intune získá zpět licenci uživatele nebo zařízení a odinstaluje aplikaci ze zařízení. Počet uvolněných licencí se v Intune projeví v uzlu **Licencované aplikace** v úloze **Aplikace**. Po odinstalaci aplikace VPP a opětovné žádosti o licenci aplikace se můžete rozhodnout přiřadit licenci aplikace jinému uživateli nebo zařízení.


### <a name="revoking-app-licenses-on-macos"></a>Odvolávání licencí aplikací v macOS
Odvolání licence k aplikaci neodinstaluje aplikaci VPP ze zařízení. Když odvoláte licenci aplikace, která byla přiřazena uživateli, Intune znovu získá licenci pro uživatele nebo zařízení. Aplikace macOS s odvolanými licencemi zůstává v zařízení použitelná, ale nedá se aktualizovat, dokud uživatel nebo zařízení nepřidá licenci. Podle Applu se takové aplikace po uplynutí 30denní lhůty odeberou. Společnost Apple ale neposkytuje způsob, jak Intune aplikaci odebrat, a to pomocí akce **odinstalovat** přiřazení. Můžete se ale rozhodnout přiřadit licenci k uvolněné aplikaci jinému uživateli nebo zařízení.

>[!NOTE]
>Pokud zaměstnanec odejde z firmy a už není součástí skupin AAD, Intune bude získávat licence aplikace VPP pro iOS i macOS uživatele.

## <a name="deleting-vpp-tokens"></a>Odstraňují se tokeny VPP.
<!-- 820879 -->  
Pomocí konzoly nástroje můžete odstranit token programu Apple Volume purchase program (VPP). To může být nutné v případě, že máte duplicitní instance tokenu VPP. Odstraněním tokenu se odstraní také všechny přidružené aplikace a přiřazení. Odstraněním tokenu se ale licence aplikací neodvolají ani aplikace neodinstalují. 

>[!NOTE]
>Po odstranění tokenu nemůže Intune odvolat licence aplikací. 

<!-- 820870 -->  
K odvolání licencí všech aplikací VPP pro daný token VPP je nutné nejprve odvolat všechny licence aplikací, které jsou k tomuto tokenu přidružené, a potom daný token odstranit.

## <a name="renewing-app-licenses"></a>Obnovení licencí aplikací

Token Apple VPP můžete obnovit tak, že z portálu Apple Volume Purchase Program stáhnete nový token a aktualizujete existující token v Intune.

## <a name="deleting-a-vpp-app"></a>Odstranění aplikace VPP

V současné době nelze aplikace VPP pro iOS z Microsoft Intune odstraňovat.

## <a name="assigning-custom-role-permissions-for-vpp"></a>Přiřazují se oprávnění vlastní role pro VPP

Přístup k tokenům Apple VPP a aplikacím VPP se dá řídit nezávisle pomocí oprávnění přiřazených k vlastním rolím Správce v Intune.

* Pokud chcete, aby mohla vlastní role Intune spravovat tokeny Apple VPP v **klientských aplikacích** > **tokeny Apple VPP**, přiřaďte oprávnění pro **spravované aplikace**.
* Pokud chcete, aby vlastní role Intune spravovala aplikace zakoupené pomocí tokenů VPP iOS v **klientských aplikacích**@no__t **-1,** přiřaďte oprávnění pro **mobilní aplikace**. 

## <a name="additional-information"></a>Další informace

Když se uživatel s oprávněným zařízením poprvé pokusí do zařízení nainstalovat aplikaci programu VPP, zobrazí se výzva k účasti v programu Apple Volume Purchase Program (VPP). Aby mohla instalace pokračovat, musí uživatel potvrdit svou účast. Pozvánka k připojení k programu Apple Volume purchase program vyžaduje, aby uživatel mohl použít aplikaci App Storu na zařízení se systémem iOS nebo macOS. Pokud jste nastavili zásadu pro zakázání aplikace App Storu, Licencování uživatelů pro aplikace VPP nefunguje. Řešením je buď dovolit aplikaci App Storu odebrat zásadu, nebo použít licencování na základě zařízení.

Při vytváření a obnovování tokenů VPP můžete využít přímou podporu od společnosti Apple. Podrobnosti najdete v článku [Distribuce obsahu vašim uživatelům v rámci programu hromadných nákupů (VPP)](https://go.microsoft.com/fwlink/?linkid=2014661) v dokumentaci Apple. 

Pokud se na portálu Intune uvádí **Přiřazeno k externí správě MDM**, můžete v Intune použít token VPP až poté, co jste ho (vy jako správce) odebrali ze správy MDM třetí strany.

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

### <a name="how-long-does-the-portal-take-to-update-the-license-count-once-an-app-is-installed-or-removed-from-the-device"></a>Jak dlouho trvá, než portál po instalaci aplikace nebo jejím odebrání ze zařízení aktualizuje počet licencí?
Licence by se měly aktualizovat do několika hodin od instalace nebo odinstalace aplikace. Je třeba mít na paměti, že pokud koncový uživatel odebere aplikaci ze zařízení, zůstává licence danému uživateli nebo zařízení stále přiřazená.

### <a name="is-it-possible-to-oversubscribe-an-app-and-if-so-in-what-circumstance"></a>Je možné přidělit aplikaci nadměrnému počtu subjektů? A pokud ano, za jakých okolností?
Ano. Správce Intune může aplikaci přidělit nadměrnému počtu uživatelů nebo zařízení. A to například tehdy, když zakoupí sto licencí k aplikaci XYZ a potom ji zacílí na skupinu s pěti sty členy. Prvnímu stu členů (uživatelům nebo zařízením) se licence přiřadí a u zbylých členů se přiřazení licence nezdaří.

### <a name="how-frequently-does-intune-sync-vpp-tokens-with-apple"></a>Jak často Intune synchronizuje tokeny VPP s Apple?
Intune synchronizuje tokeny a licence VPP dvakrát denně s Apple. Správce Intune může iniciovat ruční synchronizaci v rámci **klientských aplikací** > **tokeny Apple VPP**.

## <a name="next-steps"></a>Další kroky

Informace, s kterými budete moct lépe sledovat přiřazování aplikací, najdete v článku [Jak sledovat přiřazení aplikací](apps-monitor.md).
