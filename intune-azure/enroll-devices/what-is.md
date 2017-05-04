---
title: "Co je registrace zařízení v Microsoft Intune?"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si o registraci zařízení s iOS, Androidem a Windows."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e10453155343bb7fd91a4fd3874d393ef78d0b1a
ms.openlocfilehash: a816ee8fd2738cf244fd46a91af46d2b137a5dfb
ms.lasthandoff: 04/25/2017


---

# <a name="what-is-device-enrollment"></a>Co je registrace zařízení?
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Toto téma popisuje registraci a různé způsoby registrace mobilních zařízení do systému správy Intune.

Zařízení se do Intune registrují proto, abyste je mohli spravovat. V dokumentaci k Intune se tato funkce označuje jako správa mobilních zařízení (MDM). Když se zařízení do Intune zaregistrují, vystaví se jim certifikát MDM, který pak tato zařízení používají ke komunikaci se službou Intune.

Způsob, jakým se zařízení registrují, závisí na typu zařízení, vlastnictví a požadované úrovni správy. Registrace vlastního zařízení (BYOD) umožňuje uživatelům registrovat své osobní telefony, tablety nebo počítače. Registrace firemního zařízení (zařízení vlastněné společností, COD) umožňuje různé způsoby správy, například v podobě automatické registrace, sdílených zařízení nebo předem autorizovaných požadavků na registraci.

Pokud používáte Exchange ActiveSync, ať už místní nebo hostovaný v cloudu, můžete povolit jednoduchou správu Intune bez registrace (brzy budou k dispozici další informace). Počítače s Windows můžete spravovat jako mobilní zařízení, což je doporučený způsob popsaný níže.


## <a name="overview-of-device-enrollment-methods"></a>Přehled metod registrace zařízení

Následující tabulka uvádí metody registrace v Intune a podporované možnosti a požadavky každé metody. Možnosti a požadavky jsou popsané níže. V tabulce se používají následující pojmy:

- **Vymazání** – Udává, jestli musí být zařízení vymazáno, aby ho uživatelé mohli zaregistrovat. Pojmem „vymazání“ se rozumí obnovení továrních nastavení zařízení, které odstraní všechna data. Další informace najdete v článku [Použití úplného nebo selektivního vymazání u zařízení](/intune-azure/manage-devices/use-full-or-selective-wipe-on-devices-using-microsoft-intune).
- **Spřažení** – Přidruží zařízení k uživatelům. Požadováno pro správu mobilních aplikací (MAM) a podmíněný přístup k datům společnosti. Další informace najdete v tématu [Přidružení uživatele](enroll-ios-devices-using-device-enrollment-program.md).
- **Uzamčení** – Udává, jestli se má uživatelům bránit v rušení registrace jejich zařízení ve správě. Uživatelé můžou rušit registraci svých zařízení na všech platformách pomocí aplikace Portál společnosti. Registraci nemůžou rušit pomocí nativních nabídek operačního systému.


**Metody registrace zařízení s iOS**

| **Metoda** |    **Vyžadováno vymazání?** |    **Spřažení**    |    **Uzamčení** | **Podrobnosti** |
|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#byod)** | Ne|    Ano |    Ne | Brzy budou k dispozici další informace.|
|**[DEM](#dem)**|    Ne |Ne |Ne    | [Další informace](enroll-ios-devices-using-device-enrollment-program.md)|
|**[DEP](#dep)**|    Ano |    Volitelné |    Volitelné|[Další informace](enroll-ios-devices-using-device-enrollment-program.md)|
|**[USB-SA](#usb-sa)**|    Ano |    Volitelné |    Ne| [Další informace](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)|
|**[USB (přímo)](#usb-direct)**|    Ne |    Ne    | Ne|[Další informace](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)|

**Metody registrace zařízení s Windows**

| **Metoda** |    **Vyžadováno vymazání?** |    **Spřažení**    |    **Uzamčení** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#byod)** | Ne |    Ano |    Ne | [Další informace](#enroll-windows-devices.md)|
|**[DEM](#dem)**|    Ne |Ne |Ne    |[Další informace](enroll-devices-using-device-enrollment-manager.md)|

**Metody registrace zařízení s Androidem**

| **Metoda** |    **Vyžadováno vymazání?** |    **Spřažení**    |    **Uzamčení** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#byod)** | Ne|    Ano |    Ne | [Další informace](#enroll-android-and-knox-standard-devices.md)|
|**[DEM](#dem)**|    Ne |Ne |Ne    |[Další informace](enroll-ios-devices-using-device-enrollment-program.md)|
|[**Android for Work**](#android-for-work)| Ne | Ano | Ne| [Další informace](#enroll-android-and-knox-standard-devices.md) |


## <a name="byod"></a>Uživatelé s vlastním zařízením
Uživatelé s vlastním zařízením si nainstalují aplikaci Portál společnosti a zaregistrují svoje zařízení. To jim umožní připojit se k podnikové síti a doméně nebo ke službě Azure Active Directory. V mnoha scénářích COD (zařízení ve vlastnictví společnosti), musíte pro většinu platforem povolit registraci vlastních zařízení (BYOD). Registraci osobně vlastněných zařízení s iOSem a Androidem je možné blokovat. Pokyny najdete v tématu [Nastavení omezení typu zařízení](https://docs.microsoft.com/intune-azure/enroll-devices/set-enrollment-restrictions#set-device-type-restrictions).

## <a name="corporate-owned-devices"></a>Zařízení vlastněná společností
Ke správě zařízení vlastněných společností (COD) můžete použít portál Azure Portal. Zařízení s iOSem můžete zaregistrovat přímo nástroji poskytovanými společností Apple. Všechny typy zařízení může zaregistrovat správce využívající správce registrace zařízení. Zařízení s číslem IMEI se také dají identifikovat a označit jako zařízení ve vlastnictví společnosti, což umožní využít scénáře COD.

### <a name="dem"></a>DEM
Správce registrace zařízení (DEM) je zvláštní uživatelský účet, který se používá k registraci a správě více zařízení vlastněných společností. Správci pak mohou nainstalovat aplikaci Portál společnosti a zaregistrovat velký počet zařízení bez uživatele. Přečtěte si další informace o [DEM](enroll-devices-using-device-enrollment-manager.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Správa programu DEP společnosti Apple umožňuje vytvářet a bezdrátově nasazovat zásady v zařízeních s iOSem zakoupených a spravovaných prostřednictvím programu DEP. Zařízení se zaregistruje, když ho uživatel poprvé zapne a spustí pomocníka pro nastavení iOS (Setup Assistant). Tento způsob podporuje režim **dozoru nad iOS**, který zase umožňuje následující funkce:

  -    Registrace uzamčeného zařízení
  -    Beznabídkový režim a další pokročilé konfigurace a omezení

Registrace iOS je podrobněji popsaná zde:

- [Volba způsobu registrace zařízení s iOSem](choose-ios-enrollment-method.md)
- [Registrace zařízení s iOSem pomocí Programu registrace zařízení (DEP)](enroll-ios-devices-using-device-enrollment-program.md)
- [Zpět k předchozí tabulce](#overview-of-device-enrollment-methods)

### <a name="usb-sa"></a>USB (pomocník pro instalaci)
Správci IT používají k ruční přípravě každého zařízení vlastněného společností pro registraci Apple Configurator (přes USB) pomocí pomocníka pro nastavení (Setup Assistant). Správce IT vytvoří registrační profil a vyexportuje ho do Apple Configuratoru. Když uživatelé obdrží svá zařízení, budou vyzváni ke spuštění pomocníka pro nastavení a k registraci zařízení. Tento způsob podporuje režim **dozoru nad iOS**, který zase umožňuje následující funkce:
  -    Registrace uzamčeného zařízení
  -    Beznabídkový režim a další pokročilé konfigurace a omezení

Registrace iOS je podrobněji popsaná zde:

- [Rozhodnutí o způsobu registrace zařízení s iOSem](choose-ios-enrollment-method.md)
- [Registrace zařízení s iOSem pomocí nástroje Configurator a Průvodce nastavením](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md)

### <a name="usb-direct"></a>USB (přímo)
U přímé registrace musí správce každé zařízení zaregistrovat ručně vytvořením zásady registrace, kterou vyexportuje do Apple Configuratoru. Zařízení vlastněná společností, která jsou připojena přes USB, se zaregistrují přímo, a nevyžadují obnovení továrního nastavení. Zařízení se spravují jako zařízení bez uživatele. Nejsou uzamčená ani pod dohledem a nepodporují podmíněný přístup, detekci jailbreaků ani správu mobilních aplikací.

Registrace iOS je podrobněji popsaná zde:

- [Rozhodnutí o způsobu registrace zařízení s iOSem](choose-ios-enrollment-method.md)
- [Registrace zařízení s iOSem pomocí nástroje Configurator a přímé registrace](enroll-ios-devices-with-apple-configurator-and-direct-enrollment.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune
Mobilní zařízení, která nejsou zaregistrovaná, ale připojují se k Exchange ActiveSync (EAS), je možné spravovat pomocí Intune s využitím zásad EAS MDM. Intune používá ke komunikaci s EAS softwarovou funkci Exchange Connector, která může být místní nebo hostovaná v cloudu. Brzy budou k dispozici další informace.

## <a name="supported-device-platforms-and-browsers"></a>Podporované platformy zařízení a prohlížeče

Viz [Podporovaná zařízení a prohlížeče pro Intune](https://docs.microsoft.com/intune/get-started/supported-mobile-devices-and-computers).

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Vyčištění mobilních zařízení po vypršení platnosti certifikátu MDM

Certifikát MDM se obnovuje automaticky, když mobilní zařízení komunikují se službou Intune. Když se mobilní zařízení vymažou nebo se jim po určitou dobu nedaří komunikovat se službou Intune, certifikát MDM se neobnoví. Zařízení se z portálu Azure Portal odebere po uplynutí 180 dnů od vypršení platnosti certifikátu MDM.

