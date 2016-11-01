---
title: "Registrace zařízení | Microsoft Intune"
description: "Správa mobilních zařízení (MDM) využívá registraci pro zajištění správy zařízení a povolení přístupu k prostředkům."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 92e40930c0ccbeb3d98bef43b115fd92f24beaef
ms.openlocfilehash: 136f91e26a367ab107a80673930e735c85008ac7


---

# Registrace zařízení pro správu v Intune
Zařízení, včetně počítačů s Windows, můžete registrovat ke správě mobilních zařízení (MDM) pomocí služby Microsoft Intune. Toto téma popisuje různé způsoby registrace mobilních zařízení do systému správy Intune. Způsob registrace zařízení závisí na jeho typu, vlastnictví a požadované úrovni správy. Registrace vlastního zařízení (BYOD) umožňuje uživatelům registrovat své osobní telefony, tablety nebo počítače. Registrace zařízení vlastněného společností (COD) umožňuje scénáře správy, jako je vzdálené vymazání, sdílená zařízení nebo spřažení uživatele pro zařízení.

Pokud používáte [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune), ať už místní nebo hostovaný v cloudu, můžete povolit jednoduchou správu Intune bez registrace. Počítače s Windows je možné spravovat taky pomocí [klientského softwaru Intune](#manage-windows-pcs-with-intune).

## Přehled metod registrace zařízení

Následující tabulka uvádí metody registrace do služby Intune s jejich podporovanými možnostmi. Mezi tyto možnosti patří:
- **Vymazání** – Obnova výrobního nastavení zařízení, odstranění všech dat. Další informace najdete v tématu [Vyřazení zařízení](retire-devices-from-microsoft-intune-management.md).
- **Spřažení** – Přidruží zařízení k uživatelům. Požadováno pro správu mobilních aplikací (MAM) a podmíněný přístup k datům společnosti. Další informace najdete v tématu [Přidružení uživatele](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices).
- **Zámek** – Brání uživatelům odebrat zařízení ze správy. Zařízení s iOS vyžadují pro zámek režim dohledu. Další informace najdete v tématu [Vzdálené uzamčení](retire-devices-from-microsoft-intune-management.md#block-access-a-device).

**Metody registrace zařízení s iOS**

| **Metoda** |  **Vymazání** |  **Spřažení**    |   **Uzamčení** | **Podrobnosti** |
|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením](#byod)** | Ne|    Ano |   Ne | [Další informace](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Ne |Ne |Ne  | [Další informace](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   Ano |   Volitelné |  Volitelné|[Další informace](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB (SA)](#usb-sa)**| Ano |   Volitelné |  Ne| [Další informace](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB (přímo)](#usb-direct)**| Ne |    Ne  | Ne|[Další informace](ios-direct-enrollment-in-microsoft-intune.md)|

**Metody registrace zařízení s Windows**

| **Metoda** |  **Vymazání** |  **Spřažení**    |   **Uzamčení** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením](#byod)** | Ano|   Ano |   Ne | [Další informace](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Ne |Ne |Ne  |[Další informace](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

**Metody registrace zařízení s Androidem**

| **Metoda** |  **Vymazání** |  **Spřažení**    |   **Uzamčení** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením](#byod)** | Ne|    Ano |   Ne | [Další informace](prerequisites-for-enrollment.md#set-up-device-management)|
|**[DEM](#dem)**|   Ne |Ne |Ne  |[Další informace](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

Sadu otázek, které vám pomohou najít správnou metodu, najdete v tématu [Volba způsobu registrace zařízení](/intune/get-started/choose-how-to-enroll-devices1).

## Uživatelé s vlastním zařízením
Uživatelé s vlastním zařízením si nainstalují aplikaci Portál společnosti a zaregistrují svoje zařízení. To jim umožní připojit se k podnikové síti a doméně nebo ke službě Azure Active Directory. V mnoha scénářích COD (zařízení ve vlastnictví společnosti), musíte pro většinu platforem povolit registraci vlastních zařízení (BYOD). Další informace najdete v tématu [Požadavky na správu mobilních zařízení](prerequisites-for-enrollment.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

## Zařízení vlastněná společností
Ke správě zařízení vlastněných společností (COD) můžete použít konzolu Intune. Zařízení s iOS můžete zaregistrovat přímo nástroji poskytovanými společností Apple. Všechny typy zařízení může zaregistrovat správce využívající správce registrace zařízení. Zařízení s číslem IMEI se také dají identifikovat a označit jako zařízení ve vlastnictví společnosti, což umožní využít scénáře COD.

Další informace najdete v tématu [Registrace zařízení vlastněných společností](manage-corporate-owned-devices.md).

### DEM
Správce registrace zařízení je zvláštní účet Intune, který se používá k registraci a správě více zařízení vlastněných společností. Správci pak mohou nainstalovat aplikaci Portál společnosti a zaregistrovat velký počet zařízení bez uživatele. Přečtěte si další informace o [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

### DEP
Správa programu DEP společnosti Apple umožňuje vytvářet a bezdrátově nasazovat zásady v zařízeních s iOS zakoupených a spravovaných prostřednictvím programu DEP. Zařízení se zaregistruje, když ho uživatel poprvé zapne a spustí průvodce nastavením iOS. Tento způsob podporuje režim **dozoru nad iOS**, který zase umožňuje následující funkce:
  - Registrace uzamčeného zařízení
  - Podmíněný přístup
  - Detekce jailbreaků
  - Správa mobilních aplikací

Přečtěte si další informace o [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

### USB (SA)
Pro zařízení vlastněná společností, která jsou připojená přes USB, jsou připraveny zásady Intune. Při registraci prostřednictvím průvodce nastavením vytvoří správce zásadu Intune a exportuje ji do Apple Configuratoru. Správce musí každé zařízení zaregistrovat ručně. Uživatelé dostanou svoje zařízení a spuštěním Pomocníka s nastavením je zaregistrují. Tento způsob podporuje režim **dozoru nad iOS**, který zase umožňuje následující funkce:
  - Podmíněný přístup
  - Detekce jailbreaků
  - Správa mobilních aplikací

Přečtěte si víc o [registraci prostřednictvím Pomocníka s nastavením a Apple Configuratoru](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

### USB (přímo)
Při přímé registraci správce vytvoří zásadu Intune a exportuje ji do Apple Configuratoru. Zařízení patřící společnosti, která jsou připojena přes USB, se zaregistrují přímo, a nevyžadují obnovení továrního nastavení. Správce musí každé zařízení zaregistrovat ručně. Zařízení se spravují jako zařízení bez uživatele. Nejsou uzamčená ani pod dohledem a nepodporují podmíněný přístup, detekci jailbreaků ani správu mobilních aplikací. Přečtěte si víc o [přímé registraci prostřednictvím Apple Configuratoru](ios-direct-enrollment-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

## Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune
Mobilní zařízení, která nejsou zaregistrovaná, ale připojují se k Exchange ActiveSync (EAS), je možné spravovat pomocí Intune s využitím zásad EAS MDM. Intune používá ke komunikaci s EAS softwarovou funkci Exchange Connector, která může být místní nebo hostovaná v cloudu.

Další informace najdete v tématu [Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md).


## Správa počítačů s Windows pomocí Intune  
Microsoft Intune také můžete použít ke správě počítačů s Windows a klientským softwarem Intune. Počítače spravované pomocí Intune mohou:

 - Vytvářet sestavy inventáře softwaru a hardwaru
 - Instalovat desktopové aplikace (například soubory .exe a .msi)
 - Nastavení brány firewall

Počítače spravované pomocí klientského softwaru Intune nejdou vymazat úplně, ale umožňují selektivní vymazání. Počítače spravované pomocí klientského softwaru Intune nemohou využívat některé funkce správy ve službě Intune, jako je podmíněný přístup, nastavení sítí VPN a Wi-Fi nebo nasazení certifikátů a konfigurací e-mailu.

Další informace najdete v tématu [Správa počítačů s Windows pomocí Intune](manage-windows-pcs-with-microsoft-intune.md).

## Podporované platformy zařízení

Intune může spravovat tyto platformy zařízení:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Další kroky
- [Viz Předpoklady pro registraci zařízení](prerequisites-for-enrollment.md)
- [Správa zařízení vlastněných společností](manage-corporate-owned-devices.md)
- [Podporovaná mobilní zařízení a počítače](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Oct16_HO3-->


