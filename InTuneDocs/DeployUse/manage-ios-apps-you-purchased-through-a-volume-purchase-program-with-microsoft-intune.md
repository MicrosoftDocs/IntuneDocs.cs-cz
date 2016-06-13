---
# required metadata

title: Správa aplikací pro iOS nakoupených prostřednictvím programu hromadného nákupu | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Správa aplikací pro iOS nakoupených prostřednictvím programu hromadného nákupu pomocí Microsoft Intune
Některé App Story umožňují pro aplikace, které chcete spouštět ve vaší společnosti, nakoupit víc licencí. Můžete tak snížit administrativní režii při sledování několika kopií koupených aplikací.

Microsoft Intune vám pomůže spravovat aplikace, které jste koupili prostřednictvím takového programu, importováním licenčních informací z App Storu, sledováním, kolik licencí jste už použili a zabráněním v instalace víc aplikací, než na kolik máte licence.

> [!Important]
> V současné době Intune přiřazuje licence aplikací VPP iOS uživatelům, nikoli zařízením. Z tohoto důvodu musí koncoví uživatelé před instalací aplikace zadat heslo Apple ID.

## Správa hromadně koupených aplikací pro zařízení s iOS
K hromadnému nákupu licencí pro aplikace iOS se používá program [Apple VPP (Volume Purchase Program for Business)](http://www.apple.com/business/vpp/). Součástí této operace je vytvoření účtu Apple VPP na webu Apple a uložení tokenu Apple VPP do Intune.  Potom je možné synchronizovat informace o hromadném nákupu s Intune a sledovat využití aplikací, které jste tímto způsobem koupili.

## Než začnete
Než začnete, musíte od společnosti Apple získat token VPP a odeslat ho do svého účtu Intune. Dále byste měli mít na paměti následující:

* Každá organizace může mít jenom jeden token a účet VPP.
* Když přidružíte účet Apple VPP k Intune, už nebudete moct přidružit jiný účet. Z tohoto důvodu je důležité, aby podrobné informace o používaném účtu měla víc než jedna osoba.
* Pokud jste už dřív použili token VPP s jiným produktem, musíte pro Intune vygenerovat nový token.
* Tokeny mají platnost jeden rok.
* Ve výchozím nastavení se Intune synchronizuje se službou Apple VPP dvakrát denně. Ruční synchronizaci ale můžete spustit kdykoli.
* Po naimportování tokenu VPP do Intune neimportujte stejný token do žádného jiného řešení správy zařízení. Pokud byste to udělali, mohli byste ztratit přiřazení licence a uživatelských záznamů.
* Než začnete používat iOS VPP s Intune, odeberte všechny existující uživatelské účty VPP vytvořené pomocí jiných dodavatelů MDM. V rámci bezpečnostních opatření nebude Intune synchronizovat tyto uživatelské účty do Intune. Intune bude synchronizovat jen ta data ze služby Apple VPP, která byla vytvořená pomocí Intune. 

## Získání a odeslání tokenu Apple VPP

1.  V [konzole správce Microsoft Intune](https://manage.microsoft.com) klikněte na **Správce** &gt; **iOS a Mac OS X** &gt; **VPP (Volume Purchase Program)**.

2.  Klikněte na odkaz **Účet Apple VPP** a pokud jste to ještě neudělali, zaregistrujte se do programu Volume Purchase Program pro firmy. Po přihlášení stáhněte token Apple VPP pro svůj účet.

3.  Na kartě **Spravovat Apple VPP (Volume Purchase Program)** v konzole Intune klikněte na **Odeslat token VPP**.

4.  V dialogovém okně **Odeslat token VPP** zadejte nebo vložte název tokenu VPP a vaše Apple ID a potom klikněte na **Nahrát**.

5.  V dialogovém okně s upozorněním zaškrtněte políčko s informací o tom, že později nebude možné přejít k jinému účtu VPP, a potom klikněte na **Ano**.

Na kartě **VPP (Volume Purchase Program)** si můžete prohlédnout informace o tokenu Apple VPP, včetně data jeho poslední aktualizace, data vypršení a data poslední synchronizace s Intune.

Data ukládaná společností Apple můžete kdykoli synchronizovat s Intune kliknutím na **Synchronizovat nyní**.

## Nasazení hromadně koupené aplikace

1.  V [konzole správce Microsoft Intune](https://manage.microsoft.com) klikněte na **Aplikace** &gt; **Spravovaný software** &gt; **Hromadně zakoupené aplikace**. Tento seznam obsahuje všechny aplikace, které byly synchronizovány ze služby Apple VPP.

2.  Vyberte aplikaci, kterou chcete nasadit, klikněte na **Spravovat nasazení**, a pak postupujte podle pokynů v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md) a dokončete odeslání, vytvoření a nasazení aplikace.

Když nasazujete aplikaci s typem instalace **Požadovaná**, použije jednu licenci každý uživatel, který aplikaci nainstaluje.

Když chcete licenci získat zpět, je třeba nastavit typ instalace na **Odinstalovat**. Až se aplikace odinstaluje, licence se uvolní.

Když se uživatel s oprávněným zařízením poprvé pokusí o instalaci aplikace VPP, požádá se o připojení k programu Apple Volume Purchase. To je třeba provést před instalací aplikace.

> [!TIP] Podívejte se na sloupec **Stav podmínek VPP**, který obsahuje stav přijetí pro každého uživatele, pro kterého byla aplikace nasazená.

Pokud jsou k dispozici žádné další licence, nasazení se nepovede.

## Monitorování aplikací Apple VPP
Které aplikace VPP jsou nasazené a kolik licencí je už využito, můžete sledovat v pracovním prostoru **Aplikace** v uzlu **Spravovaný software** &gt; **Hromadně zakoupené aplikace**.

> [!TIP] Můžete také použít **filtry** aplikací pro zjištění stavu instalace konkrétních aplikací.

### Viz také
[Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md)



<!--HONumber=May16_HO4-->

