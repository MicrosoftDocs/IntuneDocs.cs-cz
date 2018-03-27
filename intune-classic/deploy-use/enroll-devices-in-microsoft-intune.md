---
title: Registrovat zařízení
description: Správa mobilních zařízení (MDM) využívá registraci pro zajištění správy zařízení a povolení přístupu k prostředkům.
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 09/22/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 99a4273a5f3ef2e1696d2fdc1c2a9b9f251b5b87
ms.sourcegitcommit: df60d03a0ed54964e91879f56c4ef0a7507c17d4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2018
---
# <a name="enroll-devices-for-management-in-intune"></a>Registrace zařízení pro správu v Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Zařízení, včetně počítačů s Windows, můžete registrovat ke správě mobilních zařízení (MDM) pomocí služby Microsoft Intune. Toto téma popisuje různé způsoby registrace mobilních zařízení do systému správy Intune. Způsob registrace zařízení závisí na jeho typu, vlastnictví a požadované úrovni správy. Registrace vlastního zařízení (BYOD) umožňuje uživatelům registrovat své osobní telefony, tablety nebo počítače. Registrace firemního zařízení (zařízení vlastněné společností, COD) umožňuje různé způsoby správy, například v podobě automatické registrace, sdílených zařízení nebo předem autorizovaných požadavků na registraci.

Pokud používáte [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune), ať už místní nebo hostovaný v cloudu, můžete povolit jednoduchou správu Intune bez registrace. Počítače s Windows je možné spravovat taky pomocí [klientského softwaru Intune](#windows-pc-management-with-intune).

Standardně se do Intune můžou registrovat zařízení pro všechny platformy. Pokud chcete u zařízení zablokovat možnost registrace, přihlaste se na [portál pro správu Microsoft Intune](https://manage.microsoft.com) pomocí přihlašovacích údajů správce. Zvolte možnost **správy** > **Správa mobilních zařízení** > **Pravidla registrace** a zrušte zaškrtnutí políček pro platformy, které chcete blokovat.

## <a name="overview-of-device-enrollment-methods"></a>Přehled metod registrace zařízení

Následující tabulka uvádí metody registrace v Intune a podporované možnosti a požadavky každé metody. Možnosti a požadavky jsou popsané níže.

- **Vymazání** – Udává, jestli musí být zařízení vymazáno, aby ho uživatelé mohli zaregistrovat. Pojmem „vymazání“ se rozumí obnovení továrních nastavení zařízení, které odstraní všechna data. Další informace najdete v tématu [Vyřazení zařízení](retire-devices-from-microsoft-intune-management.md).
- **Spřažení** – Přidruží zařízení k uživatelům. Požadováno pro správu mobilních aplikací (MAM) a podmíněný přístup k datům společnosti. Další informace najdete v tématu [Přidružení uživatele](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#use-the-company-portal-on-dep-enrolled-or-apple-configurator-enrolled-devices).
- **Uzamčení** – určuje, jestli se má uživatelům bránit v rušení registrace jejich zařízení pomocí nativních nabídek operačního systému. Uživatelé můžou rušit registraci svých zařízení na všech platformách pomocí aplikace Portál společnosti.

**Metody registrace zařízení s iOSem**

| **Metoda** |  **Vyžadováno vymazání?** |    **Spřažení**    |   **Uzamčení** | **Podrobnosti** |
|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#byod)** | Ne|    Ano |   Ne | [Další informace](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|   Ne |Ne |Ne  | [Další informace](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   Ano |   Volitelné |  Volitelné|[Další informace](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB-SA](#usb-sa)**| Ano |   Volitelné |  Ne| [Další informace](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB (přímo)](#usb-direct)**| Ne |    Ne  | Ne|[Další informace](ios-direct-enrollment-in-microsoft-intune.md)|

**Metody registrace zařízení s Windows**

| **Metoda** |  **Vyžadováno vymazání?** |    **Spřažení**    |   **Uzamčení** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#byod)** | Ne|    Ano |   Ne | [Další informace](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|   Ne |Ne |Ne  |[Další informace](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Metody registrace zařízení s Androidem**

| **Metoda** |  **Vyžadováno vymazání?** |    **Spřažení**    |   **Uzamčení** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#byod)** | Ne|    Ano |   Ne | [Další informace](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|   Ne |Ne |Ne  |[Další informace](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Metody registrace Androidu for Work**

| **Metoda** |  **Vyžadováno vymazání?** |    **Spřažení**    |   **Uzamčení** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#byod)** | Ne|    Ano |   Ne | [Další informace](prerequisites-for-enrollment.md)|
|**[DEM](#dem)**|   Ne |Ne |Ne  |[Další informace](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Metody registrace zařízení s macOS**

| **Metoda** |  **Vyžadováno vymazání?** |    **Spřažení**    |   **Uzamčení** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením (BYOD)](#byod)** | Ne|    Ano |   Ne | [Další informace](prerequisites-for-enrollment.md)|


Sadu otázek, které vám pomohou najít správnou metodu, najdete v tématu [Volba způsobu registrace zařízení](/intune-classic/get-started/choose-how-to-enroll-devices1).

## <a name="byod"></a>uživatelé s vlastním zařízením (BYOD)
Uživatelé s vlastním zařízením si nainstalují aplikaci Portál společnosti a zaregistrují svoje zařízení. To jim umožní připojit se k podnikové síti a doméně nebo ke službě Azure Active Directory. V mnoha scénářích COD (zařízení ve vlastnictví společnosti), musíte pro většinu platforem povolit registraci vlastních zařízení (BYOD). Další informace najdete v tématu [Požadavky na správu mobilních zařízení](prerequisites-for-enrollment.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

## <a name="corporate-owned-devices"></a>Zařízení vlastněná společností
Ke správě zařízení vlastněných společností (COD) můžete použít konzolu Intune. Zařízení s iOSem můžete zaregistrovat přímo nástroji poskytovanými společností Apple. Všechny typy zařízení může zaregistrovat správce využívající správce registrace zařízení. Zařízení s číslem IMEI se také dají identifikovat a označit jako zařízení ve vlastnictví společnosti, což umožní využít scénáře COD.

Další informace najdete v tématu [Registrace zařízení vlastněných společností](manage-corporate-owned-devices.md).

### <a name="dem"></a>DEM
Správce registrace zařízení je zvláštní účet Intune, který se používá k registraci a správě více zařízení vlastněných společností. Správci pak mohou nainstalovat aplikaci Portál společnosti a zaregistrovat velký počet zařízení bez uživatele. Přečtěte si další informace o [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

### <a name="dep"></a>DEP
Správa programu DEP společnosti Apple umožňuje vytvářet a bezdrátově nasazovat zásady v zařízeních s iOSem zakoupených a spravovaných prostřednictvím programu DEP. Zařízení se zaregistruje, když ho uživatel poprvé zapne a spustí pomocníka pro nastavení iOS (Setup Assistant). Tento způsob podporuje režim **dozoru nad iOS**, který zase umožňuje následující funkce:
  - Registrace uzamčeného zařízení
  - Beznabídkový režim a další pokročilé konfigurace a omezení

Přečtěte si další informace o [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

### <a name="usb-sa"></a>USB (pomocník pro instalaci)
Správci IT používají k ruční přípravě každého zařízení vlastněného společností pro registraci Apple Configurator (přes USB) pomocí pomocníka pro nastavení (Setup Assistant). Správce IT vytvoří registrační profil a vyexportuje ho do Apple Configuratoru. Když uživatelé obdrží svá zařízení, budou vyzváni ke spuštění pomocníka pro nastavení a k registraci zařízení. Tento způsob podporuje režim **dozoru nad iOS**, který zase umožňuje následující funkce:
  - Registrace uzamčeného zařízení
  - Beznabídkový režim a další pokročilé konfigurace a omezení

Přečtěte si víc o [registraci prostřednictvím pomocníka pro nastavení a Apple Configuratoru](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

### <a name="usb-direct"></a>USB (přímo)
U přímé registrace musí správce každé zařízení zaregistrovat ručně vytvořením zásady registrace, kterou vyexportuje do Apple Configuratoru. Zařízení vlastněná společností, která jsou připojena přes USB, se zaregistrují přímo, a nevyžadují obnovení továrního nastavení. Zařízení se spravují jako zařízení bez uživatele. Nejsou uzamčená ani pod dohledem a nepodporují podmíněný přístup, detekci jailbreaků ani správu mobilních aplikací.  Přečtěte si víc o [přímé registraci prostřednictvím Apple Configuratoru](ios-direct-enrollment-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune
Mobilní zařízení, která nejsou zaregistrovaná, ale připojují se k Exchange ActiveSync (EAS), je možné spravovat pomocí Intune s využitím zásad EAS MDM. Intune používá ke komunikaci s EAS softwarovou funkci Exchange Connector, která může být místní nebo hostovaná v cloudu. Další informace najdete v tématu [Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).


## <a name="windows-pc-management-with-intune"></a>Správa počítačů s Windows pomocí Intune  
Microsoft Intune také můžete použít ke správě počítačů s Windows a klientským softwarem Intune. Počítače spravované pomocí Intune mohou:

 - Vytvářet sestavy inventáře softwaru a hardwaru
 - Instalovat desktopové aplikace (například soubory .exe a .msi)
 - Spravovat nastavení brány firewall

Počítače spravované pomocí klientského softwaru Intune nejdou vymazat úplně, ale umožňují selektivní vymazání. Počítače spravované pomocí klientského softwaru Intune nemohou využívat některé funkce správy ve službě Intune, jako je podmíněný přístup, nastavení sítí VPN a Wi-Fi nebo nasazení certifikátů a konfigurací e-mailu. Další informace najdete v tématu [Správa počítačů s Windows pomocí Intune](manage-windows-pcs-with-microsoft-intune.md).

## <a name="supported-device-platforms"></a>Podporované platformy zařízení

Intune může spravovat tyto platformy zařízení:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## <a name="next-steps"></a>Další kroky
- [Předpoklady pro registraci zařízení](prerequisites-for-enrollment.md)
- [Správa zařízení vlastněných společností](manage-corporate-owned-devices.md)
- [Podporovaná mobilní zařízení a počítače](/intune/supported-devices-browsers#intune-supported-devices)
