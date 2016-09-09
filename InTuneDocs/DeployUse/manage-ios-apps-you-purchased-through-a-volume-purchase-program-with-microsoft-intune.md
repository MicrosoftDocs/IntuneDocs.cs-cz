---
title: "Správa hromadně koupených aplikací pro iOS | Microsoft Intune"
description: "Použijte Intune ke správě aplikací, které jste koupili od Applu, importováním licenčních informací z App Storu, sledováním, kolik licencí jste už použili, a zabráněním instalace více aplikací, než na kolik máte licence."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 09/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 164f9656246a46bf39e263fc3c5f16828674e1fd
ms.openlocfilehash: a5c37c470f937c682d9138a636d1211f641da784


---

# Správa aplikací pro iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune
App Store pro iOS umožňuje pro aplikace, které chcete spouštět ve vaší společnosti, nakoupit víc licencí. Můžete tak snížit administrativní režii při sledování několika kopií koupených aplikací.

Microsoft Intune vám pomůže spravovat aplikace, které jste koupili prostřednictvím tohoto programu, importováním licenčních informací z App Storu, sledováním, kolik licencí jste už použili, a zabráněním instalace více aplikací, než na kolik máte licence.

> [!Important]
> V současné době Intune přiřazuje licence aplikací iOS typu VPP (Volume Purchase Program for Business) uživatelům, nikoli zařízením. Z tohoto důvodu musí koncoví uživatelé před instalací aplikace zadat své Apple ID a heslo.

## Správa hromadně koupených aplikací pro zařízení s iOS
K hromadnému nákupu licencí pro aplikace iOS se používá program [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/). Součástí této operace je vytvoření účtu Apple VPP na webu Apple a odeslání tokenu Apple VPP do Intune.  Potom je možné synchronizovat informace o hromadném nákupu s Intune a sledovat využití aplikací, které jste tímto způsobem koupili.

## Než začnete
Než začnete, musíte od společnosti Apple získat token VPP a odeslat ho do svého účtu Intune. Dále byste měli mít na paměti následující:

* Každá organizace může mít jenom jeden token a účet VPP.
* Poté, co přidružíte účet Apple VPP k Intune, už nebude později možné přidružit jiný účet. Z tohoto důvodu je důležité, aby přístupové údaje k používanému účtu měla víc než jedna osoba.
* Pokud jste už dřív použili token VPP s jiným produktem, musíte pro Intune vygenerovat nový token.
* Tokeny mají platnost jeden rok.
* Ve výchozím nastavení se Intune synchronizuje se službou Apple VPP dvakrát denně. Ruční synchronizaci můžete spustit kdykoli.
* Po naimportování tokenu VPP do Intune neimportujte stejný token do žádného jiného řešení správy zařízení. Pokud byste to udělali, mohli byste ztratit přiřazení licence a uživatelských záznamů.
* Než začnete používat iOS VPP s Intune, odeberte všechny existující uživatelské účty VPP vytvořené pomocí jiných řešení správy zařízení (MDM). V rámci bezpečnostních opatření nebude Intune synchronizovat tyto uživatelské účty do Intune. Intune bude synchronizovat jen ta data ze služby Apple VPP, která byla vytvořená pomocí Intune.
* Aplikace iOS VPP se nedají nasadit na zařízení zaregistrovaná pomocí programu DEP (Device Enrollment Protocol).

## Získání a odeslání tokenu Apple VPP

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) klikněte na **Správce** &gt; **iOS a Mac OS X** &gt; **VPP (Volume Purchase Program)**.

2.  Vyberte odkaz **účet Apple VPP**. Pokud jste to ještě neudělali, zaregistrujte se do programu Volume Purchase Program for Business. Po přihlášení stáhněte token Apple VPP pro svůj účet.

3.  Na stránce **Spravovat Apple VPP (Volume Purchase Program)** v konzole Intune vyberte **Odeslat token VPP**.

4.  V dialogu **Odeslat token VPP** zadejte nebo vložte název tokenu VPP a vaše Apple ID a potom vyberte **Odeslat**.

5.  V dialogu s upozorněním zaškrtnutím políčka potvrďte, že jste si vědomi, že později nebude možné přejít k jinému účtu VPP, a potom vyberte **Ano**.

Na kartě **Volume Purchase Program** si můžete prohlédnout informace o tokenu Apple VPP, včetně data jeho poslední aktualizace, data vypršení a data poslední synchronizace s Intune.

Data ukládaná společností Apple můžete kdykoli synchronizovat s Intune výběrem položky **Synchronizovat nyní**.

## Nasazení hromadně koupené aplikace

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) klikněte na **Aplikace** &gt; **Spravovaný software** &gt; **Multilicenční aplikace**. Tento seznam obsahuje všechny aplikace, které byly synchronizovány ze služby Apple VPP.

2.  Vyberte aplikaci, kterou chcete nasadit, klikněte na **Spravovat nasazení** a potom postupujte podle pokynů v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md) a dokončete odeslání, vytvoření a nasazení aplikace.

> [!TIP]
> Musíte vybrat akci nasazení s nastavením **Požadované**. Instalace typu Dostupná se v současnosti nepodporují.

Když nasazujete aplikaci s typem instalace **Požadovaná**, každý uživatel, který aplikaci nainstaluje, využije jednu licenci.

Když chcete licenci získat zpět, je třeba nastavit typ instalace na **Odinstalovat**. Až se aplikace odinstaluje, licence se uvolní.

Když se uživatel s oprávněným zařízením poprvé pokusí o instalaci aplikace VPP, požádá se o připojení k programu Apple Volume Purchase. To je třeba provést před instalací aplikace.

> [!TIP]
> Podívejte se na sloupec **Stav podmínek VPP**, který obsahuje stav přijetí pro každého uživatele, pro kterého byla aplikace nasazená.

Pokud jsou k dispozici žádné další licence, nasazení selže.

## Monitorování aplikací Apple VPP
Které aplikace VPP jsou nasazené a kolik licencí je už využito, můžete sledovat v pracovním prostoru **Aplikace** v uzlu **Spravovaný software** &gt; **Hromadně zakoupené aplikace**.

> [!TIP]
> Můžete také použít **filtry** aplikací pro zjištění stavu instalace konkrétních aplikací.

### Viz taky
[Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md)



<!--HONumber=Sep16_HO2-->


