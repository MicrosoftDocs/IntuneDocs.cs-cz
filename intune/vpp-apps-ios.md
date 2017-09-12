---
title: "Správa hromadně zakoupených aplikací iOS"
titlesuffix: Azure portal
description: "Zjistěte, jak synchronizovat s Intune aplikace zakoupené v rámci multilicenčního programu z App Storu pro zařízení s iOSem a jak následně spravovat a sledovat jejich používání."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 51d45ce2-d81b-4584-8bc4-568c8c62653d
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: addcc2c9a939b8dc62d708b3f9f000cb7c09cef3
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Správa aplikací pro iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune


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
Nákup více licencí k aplikacím pro iOS je možný prostřednictvím programu [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) nebo [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Součástí tohoto procesu je vytvoření účtu Apple VPP na webu Apple a odeslání tokenu Apple VPP do Intune.  Potom je možné synchronizovat informace o hromadném nákupu s Intune a sledovat využití aplikací, které jste tímto způsobem koupili.

## <a name="before-you-start"></a>Než začnete
Než začnete, potřebujete od společnosti Apple získat token VPP a nahrát ho do svého účtu Intune. Měli byste se také seznámit s následujícími kritérii:

* Ke svému účtu Intune můžete přidružit několik tokenů multilicenčního programu.
* Pokud jste už dřív použili token VPP s jiným produktem, musíte pro Intune vygenerovat nový token.
* Tokeny mají platnost jeden rok.
* Ve výchozím nastavení se Intune synchronizuje se službou Apple VPP dvakrát denně. Ruční synchronizaci můžete spustit kdykoli.
* Než začnete používat iOS VPP s Intune, odeberte všechny existující uživatelské účty VPP vytvořené pomocí jiných řešení správy zařízení (MDM). V rámci bezpečnostních opatření Intune nesynchronizuje tyto uživatelské účty do Intune. Intune synchronizuje jenom data služby Apple VPP vytvořená službou Intune.
* Intune podporuje přidání až 256 tokenů VPP.
* Pokud zařízení zaregistrovanému prostřednictvím profilu pro zápis zařízení nebo prostřednictvím Apple Configuratoru přiřadíte hromadně koupenou aplikaci, bude fungovat, jenom pokud je pro toto zařízení určená. Hromadně zakoupené aplikace nemůžete vyhradit pro uživatele zařízení DEP bez přiřazeného uživatele.
Důvodem je skutečnost, že licencování uživatelů v programu VPP pro iOS umožňuje registraci stovek zařízení pomocí stejného uživatelského účtu. Licencování uživatelů v programu VPP pro iOS umožňuje, aby si koncový uživatel nainstaloval aplikaci na 5 až 10 zařízení.
To znamená, že prvních pár zařízení registrovaných v DEM by obdrželo aplikaci programu VPP nainstalovanou pomocí licencování uživatelů, ale ostatní zařízení by tuto aplikaci neobdržela.
* Token VPP se dá použít vždy jen v jednom účtu Intune. Proto nepoužívejte stejný token VPP ve více tenantech Intune.
* Když uživatelům nebo zařízením (přiřazeným uživatelům) na základě modelu poskytování uživatelských licencí přiřazujete aplikace získané v rámci programu VPP, musí mít každý uživatel Intune, který na svém zařízení potvrdí smluvní podmínky společnosti Apple, přiřazeno jedinečné Apple ID nebo e-mailovou adresu.
Dbejte na to, abyste při nastavování zařízení pro nového uživatele Intune nakonfigurovali jedinečné Apple ID nebo e-mailovou adresu. Apple ID nebo e-mailová adresa a uživatel Intune tvoří jedinečný pár, který je možné použít až pro 5 zařízení.

>[!IMPORTANT]
>Po naimportování tokenu VPP do Intune neimportujte stejný token do žádného jiného řešení správy zařízení. Pokud byste to udělali, mohli byste ztratit přiřazení licence a uživatelských záznamů.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Získání a odeslání tokenu Apple VPP

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
1.  V úloze **Mobilní aplikace** zvolte **Nastavení** > **Tokeny VPP pro iOS**.
2.  V okně se seznamem tokenů VPP klikněte na **Přidat**.
3.  V okně **Nový token VPP** zadejte následující informace:
    - **Soubor tokenu VPP** – pokud jste to ještě neudělali, zaregistrujte se do programu Volume Purchase Program for Business nebo Volume Purchase Program for Education. Po zaregistrování si stáhněte token Apple VPP pro svůj účet a vyberte ho tady.
    - **Apple ID** – zadejte Apple ID účtu přidruženého k multilicenčnímu programu.
    - **Typ účtu VPP** – zvolte jednu z možností: **Obchodní** nebo **Vzdělávání**.
4. Po dokončení klikněte na **Nahrát**.

Token se zobrazí v okně se seznamem tokenů.


Data ukládaná společností Apple můžete kdykoli synchronizovat s Intune výběrem položky **Synchronizovat nyní**.

> [!NOTE]
> Microsoft Intune synchronizuje jenom informace o aplikacích, které jsou veřejně dostupné prostřednictvím iTunes Storu. **Vlastní B2B aplikace pro iOS** se zatím nepodporují. Pokud tento scénář platí pro vaše aplikace, nebudou se informace o aplikaci synchronizovat.

## <a name="to-assign-a-volume-purchased-app"></a>Přiřazení aplikace zakoupené v rámci multilicenčního programu

1.  V úloze **Mobilní aplikace** zvolte **Spravovat** > **Licence aplikací**.
2.  V okně se seznamem aplikací zvolte aplikaci, kterou chcete přiřadit, a pak zvolte **...** > **Přiřadit skupiny**.
3.  V okně *<app name>* - **Přiřazení** zvolte **Spravovat** > **Přiřazení**.
4.  Zvolte **Vybrat skupiny** a pak v okně **Vybrat skupiny** zvolte skupiny uživatelů nebo zařízení Azure AD, ke kterým chcete aplikaci přiřadit.
5.  Pro každou zvolenou skupinu vyberte následující nastavení:
    - **Typ** – vyberte, jestli bude aplikace **k dispozici** (koncoví uživatelé můžou aplikaci nainstalovat z Portálu společnosti), nebo **povinná** (aplikace se na zařízení koncových uživatelů nainstaluje automaticky).
    - **Typ licence** – vyberte **Licencování uživatelů** nebo **Licencování zařízení**.
6.  Až to budete mít, zvolte **Uložit**.


>[!NOTE]
>V seznamu zobrazené aplikace jsou přidružené k tokenu. Pokud máte aplikaci, která je spojená s více tokeny VPP, zobrazí se stejná aplikace několikrát – jednou u každého tokenu.

## <a name="further-information"></a>Další informace

Když chcete licenci získat zpět, musíte nastavit akci přiřazení na Odinstalovat. Až se aplikace odinstaluje, licence se uvolní. Pokud odeberete aplikaci, která byla přiřazena uživateli, pokusí se Intune uvolnit všechny licence aplikace, které byly k tomuto uživateli přidruženy.

Když se uživatel s oprávněným zařízením poprvé pokusí do zařízení nainstalovat aplikaci programu VPP, zobrazí se výzva k účasti v programu Apple Volume Purchase Program (VPP). Aby mohla instalace pokračovat, musí uživatel potvrdit svou účast. Aby se mohl uživatel připojit do programu Apple Volume Purchase Program, musí používat na zařízení s iOSem aplikaci iTunes. Pokud jste nastavili zásadu, která zakazuje aplikace z iTunes Storu, nebude licencování založené na uživatelích pro aplikace z programu VPP fungovat. Řešením je odebrat zásady a povolit tak aplikaci iTunes nebo použít licencování na základě zařízení.



## <a name="next-steps"></a>Další kroky

Informace, s kterými budete moct lépe sledovat přiřazování aplikací, najdete v článku [Jak sledovat přiřazení aplikací](apps-monitor.md).