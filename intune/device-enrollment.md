---
title: "Co je registrace zařízení v Microsoft Intune?"
titlesuffix: Azure portal
description: "Přečtěte si o registraci zařízení s iOSem, Androidem a Windows."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 05/29/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dda7108aedcc4d3878fe3743ee0b88b26fabbe6f
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="what-is-device-enrollment"></a>Co je registrace zařízení?
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Toto téma popisuje registraci a různé způsoby registrace mobilních zařízení do systému správy Intune.

Zařízení se do Intune registrují proto, abyste je mohli spravovat. V dokumentaci k Intune se tato funkce označuje jako správa mobilních zařízení (MDM). Když se zařízení do Intune zaregistrují, vystaví se jim certifikát MDM, který pak tato zařízení používají ke komunikaci se službou Intune.

Způsob, jakým se zařízení registrují, závisí na typu zařízení, vlastnictví a požadované úrovni správy. Registrace vlastního zařízení (BYOD) umožňuje uživatelům registrovat své osobní telefony, tablety nebo počítače. Registrace firemního zařízení (zařízení vlastněné společností, COD) umožňuje různé způsoby správy, například v podobě automatické registrace, sdílených zařízení nebo předem autorizovaných požadavků na registraci.

Pokud používáte Exchange ActiveSync, ať už místní nebo hostovaný v cloudu, můžete povolit jednoduchou správu Intune bez registrace (brzy budou k dispozici další informace). Počítače s Windows můžete spravovat jako mobilní zařízení, což je doporučený způsob popsaný níže.


## <a name="overview-of-device-enrollment-methods"></a>Přehled metod registrace zařízení

Následující tabulka nabízí přehled metod registrace v Intune a jejich funkce a požadavky, které jsou popsané dole.
**Legenda**

- **Vyžadováno resetování** – Během registrace se obnoví tovární nastavení zařízení.
- **Přidružení uživatele** – Přidruží zařízení k uživatelům. Další informace najdete v tématu [Přidružení uživatele](device-enrollment-program-enroll-ios.md).
- **Uzamčeno** – Zabraňuje uživatelům zrušit registraci zařízení.

**Metody registrace zařízení s iOSem**

| **Metoda** |  **Vyžadováno resetování** |    **Přidružení uživatele**   |   **Uzamčeno** | **Podrobnosti** |
|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#byod)** | Ne|    Ano |   Ne | [Další informace](./apple-mdm-push-certificate-get.md)|
|**[DEM](#dem)**|   Ne |Ne |Ne  | [Další informace](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|   Ano |   Volitelné |  Volitelné|[Další informace](./device-enrollment-program-enroll-ios.md)|
|**[USB-SA](#usb-sa)**| Ano |   Volitelné |  Ne| [Další informace](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB (přímo)](#usb-direct)**| Ne |    Ne  | Ne|[Další informace](./apple-configurator-direct-enroll-ios.md)|

**Metody registrace zařízení s Windows**

| **Metoda** |  **Vyžadováno resetování** |    **Přidružení uživatele**   |   **Uzamčeno** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#byod)** | Ne |   Ano |   Ne | [Další informace](windows-enroll.md)|
|**[DEM](#dem)**|   Ne |Ne |Ne  |[Další informace](device-enrollment-manager-enroll.md)|
|**Automatická registrace** | Ne |Ano |Ne | [Další informace](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Hromadná registrace** |Ne |Ne |Ne | [Další informace](./windows-bulk-enroll.md) |

**Metody registrace zařízení s Androidem**

| **Metoda** |  **Vyžadováno resetování** |    **Přidružení uživatele**   |   **Uzamčeno** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#byod)** | Ne|    Ano |   Ne | [Další informace](./android-enroll.md)|
|**[DEM](#dem)**|   Ne |Ne |Ne  |[Další informace](./device-enrollment-program-enroll-ios.md)|
|**Android for Work**| Ne | Ano | Ne| [Další informace](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="byod"></a>Uživatelé s vlastním zařízením
Uživatelé s vlastním zařízením si nainstalují a spustí aplikaci Portál společnosti a zaregistrují svoje zařízení. Tento program umožňuje uživatelům přístup k firemním prostředkům, jako je třeba e-mail.

## <a name="corporate-owned-devices"></a>Zařízení vlastněná společností
Následují scénáře registrace zařízení vlastněných společností (COD). Zařízení s iOSem můžete zaregistrovat přímo nástroji poskytovanými společností Apple. Všechny typy zařízení může zaregistrovat správce využívající správce registrace zařízení. Zařízení s číslem IMEI se také dají identifikovat a označit jako zařízení ve vlastnictví společnosti, což umožní využít scénáře COD.

### <a name="dem"></a>DEM
Správce registrace zařízení (DEM) je zvláštní uživatelský účet, který se používá k registraci a správě více zařízení vlastněných společností. Správci pak mohou nainstalovat aplikaci Portál společnosti a zaregistrovat velký počet zařízení bez uživatele. Přečtěte si další informace o [DEM](./device-enrollment-manager-enroll.md).

### <a name="dep"></a>DEP
Správa programu DEP společnosti Apple umožňuje vytvářet a bezdrátově nasazovat zásady v zařízeních s iOSem zakoupených a spravovaných prostřednictvím programu DEP. Zařízení se zaregistruje, když ho uživatel poprvé zapne a spustí pomocníka pro nastavení iOS (Setup Assistant). Tato metoda podporuje režim **iOS – Pod dohledem**, který pak povoluje následující funkce:

  - Registrace uzamčeného zařízení
  - Beznabídkový režim a další pokročilé konfigurace a omezení

Registrace DEP pro iOS je podrobněji popsaná zde:

- [Volba způsobu registrace zařízení s iOSem](enrollment-method-choose-ios.md)
- [Registrace zařízení s iOSem pomocí Programu registrace zařízení (DEP)](device-enrollment-program-enroll-ios.md)

### <a name="usb-sa"></a>USB (pomocník pro instalaci)
Správci IT používají k ruční přípravě každého zařízení vlastněného společností pro registraci Apple Configurator (přes USB) a Pomocníka s nastavením. Správce IT vytvoří registrační profil a vyexportuje ho do Apple Configuratoru. Když uživatelé obdrží svá zařízení, budou vyzváni ke spuštění pomocníka pro nastavení a k registraci zařízení. Tato metoda podporuje režim **iOS – Pod dohledem**, který pak povoluje následující funkce:
  - Registrace uzamčeného zařízení
  - Beznabídkový režim a další pokročilé konfigurace a omezení

Další informace o registraci pro iOS prostřednictvím Apple Configuratoru a Pomocníka s nastavením:

- [Rozhodnutí o způsobu registrace zařízení s iOSem](enrollment-method-choose-ios.md)
- [Registrace zařízení s iOSem pomocí nástroje Configurator a Průvodce nastavením](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB (přímo)
U přímé registrace musí správce každé zařízení zaregistrovat ručně vytvořením zásady registrace, kterou vyexportuje do Apple Configuratoru. Zařízení vlastněná společností, která jsou připojena přes USB, se zaregistrují přímo, a nevyžadují obnovení továrního nastavení. Zařízení se spravují jako zařízení bez uživatele. Nejsou uzamčená ani pod dohledem a nepodporují podmíněný přístup, detekci jailbreaků ani správu mobilních aplikací.

Registrace iOS je podrobněji popsaná zde:

- [Rozhodnutí o způsobu registrace zařízení s iOSem](enrollment-method-choose-ios.md)
- [Registrace zařízení s iOSem pomocí nástroje Configurator a přímé registrace](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune
Mobilní zařízení, která nejsou zaregistrovaná, ale připojují se k Exchange ActiveSync (EAS), je možné spravovat pomocí Intune s využitím zásad EAS MDM. Intune používá ke komunikaci s EAS softwarovou funkci Exchange Connector, která může být místní nebo hostovaná v cloudu. Brzy budou k dispozici další informace.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Vyčištění mobilních zařízení po vypršení platnosti certifikátu MDM

Certifikát MDM se obnovuje automaticky, když mobilní zařízení komunikují se službou Intune. Když se mobilní zařízení vymažou nebo se jim po určitou dobu nedaří komunikovat se službou Intune, certifikát MDM se neobnoví. Zařízení se z portálu Azure Portal odebere po uplynutí 180 dnů od vypršení platnosti certifikátu MDM.
