---
title: "Registrace zařízení | Microsoft Intune"
description: "Správa mobilních zařízení (MDM) využívá registraci pro zajištění správy zařízení a povolení přístupu k prostředkům."
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0d1b6fea5284f7825da412351f5b5d5f2a47857d
ms.openlocfilehash: caef9301c965704893b3a546429760cf779579f2


---

# Registrace zařízení pro správu v Intune
Zařízení, včetně počítačů s Windows, můžete registrovat ke správě mobilních zařízení (MDM) pomocí služby Microsoft Intune. Toto téma popisuje různé způsoby registrace mobilních zařízení do správy Intune. Způsob registrace zařízení závisí na jeho typu, vlastnictví a požadované úrovni správy. Registrace vlastního zařízení (BYOD) umožňuje uživatelům registrovat své osobní telefony, tablety nebo počítače. Registrace zařízení vlastněného společností (COD) umožňuje scénáře správy, jako je vzdálené vymazání, sdílená zařízení nebo spřažení uživatele pro zařízení.

Pokud používáte [Exchange ActiveSync](#mobile-device-management-with-exchange-activesync-and-intune), ať už místní nebo hostovaný v cloudu, můžete povolit jednoduchou správu Intune bez registrace. Počítače s Windows je možné spravovat taky pomocí [klientského softwaru Intune](#manage-windows-pcs-with-intune).

## Přehled metod registrace zařízení

Následující tabulka uvádí metody registrace do služby Intune s jejich podporovanými možnostmi. Mezi tyto možnosti patří:
- **Vymazání** – obnova výrobního nastavení zařízení, odstranění všech dat. [Vyřazení zařízení](retire-devices-from-microsoft-intune-management.md)
- **Spřažení** – přidruží zařízení k uživatelům. Požadováno pro správu mobilních aplikací (MAM) a podmíněný přístup k datům společnosti. [Spřažení uživatele](enroll-corporate-owned-ios-devices-in-microsoft-intune.md#using-company-portal-on-dep-or-apple-configurator-enrolled-devices)
- **Zámek** zabrání uživatelům odebrat zařízení ze správy. Zařízení s iOS vyžadují pro zámek režim dohledu. [Vzdálené uzamčení](retire-devices-from-microsoft-intune-management.md#block-access-a-device)

**Metody registrace zařízení s iOS**

| **Metoda** |  **Vymazání** |  **Spřažení**    |   **Uzamčení** | **Podrobnosti** |
|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením](#byod)** | Ne|    Ano |   Ne | [další](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management)|
|**[DEM](#dem)**|   Ne |Ne |Ne  | [další](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|
|**[DEP](#dep)**|   Ano |   Volitelné |  Volitelné|[další](ios-device-enrollment-program-in-microsoft-intune.md)|
|**[USB (SA)](#usb-sa)**| Ano |   Volitelné |  Ne| [další](ios-setup-assistant-enrollment-in-microsoft-intune.md)|
|**[USB (přímo)](#usb-direct)**| Ne |    Ne  | Ne|[další](ios-direct-enrollment-in-microsoft-intune.md)|

**Metody registrace zařízení se systémem Windows a Android**

| **Metoda** |  **Vymazání** |  **Spřažení**    |   **Uzamčení** | **Podrobnosti**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením](#byod)** | Ne|    Ano |   Ne | [další](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management)|
|**[DEM](#dem)**|   Ne |Ne |Ne  |[další](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)|

Sérii otázek, které vám pomohou najít tu správnou metodu pro vás, najdete v tématu [Volba způsobu registrace zařízení](/intune/get-started/choose-how-to-enroll-devices1).

## Uživatelé s vlastním zařízením
Uživatelé s vlastním zařízením si nainstalují aplikaci Portál společnosti a zaregistrují svoje zařízení. To jim umožní připojit se k podnikové síti, k doméně nebo službě Azure Active Directory. Povolení registrace vlastních zařízení (BYOD) je předpokladem pro mnoho scénářů COD pro většinu platforem. Viz [Předpoklady pro registraci zařízení](prerequisites-for-enrollment.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

## Zařízení vlastněná společností
Zařízení vlastněná společností (COD) je možné spravovat pomocí konzoly Intune. Zařízení s iOS se mohou zaregistrovat přímo pomocí nástrojů poskytovaných společností Apple. Všechny typy zařízení může zaregistrovat správce využívající správce registrace zařízení. Zařízení s číslem IMEI se také dají identifikovat a označit jako zařízení ve vlastnictví společnosti, což umožní využít scénáře COD.

[Registrace zařízení vlastněných společností](manage-corporate-owned-devices.md)

### DEM
Správce registrace zařízení je speciální účet Intune, který slouží k registraci a správě více zařízení vlastněných společností. Správci pak mohou nainstalovat aplikaci Portál společnosti a zaregistrovat velký počet zařízení bez uživatele. Přečtěte si další informace o [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

### DEP
Správa Programu registrace zařízení Apple (DEP) umožňuje vytvořit a bezdrátově nasadit zásady v zařízeních iOS zakoupených a spravovaných pomocí programu DEP. Zařízení je zaregistrováno, když ho uživatel poprvé zapne a spustí se Průvodce nastavením iOS. Tato metoda podporuje režim **iOS – Pod dohledem**, který pak povoluje následující funkce:
  - Registrace uzamčeného zařízení
  - Podmíněný přístup
  - Detekce jailbreaků
  - Správa mobilních aplikací

Přečtěte si další informace o [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

### USB (SA)
Registrace prostřednictvím Pomocníka s nastavením přes připojení USB. Správce vytvoří zásadu Intune a vyexportuje ji do Apple Configuratoru. Pro zařízení vlastněná společností, která jsou připojená přes USB, jsou připraveny zásady Intune. Správce musí každé zařízení zaregistrovat ručně. Uživatelé dostanou svoje zařízení a spuštěním Pomocníka s nastavením je zaregistrují. Tato metoda podporuje režim **iOS – Pod dohledem**, který pak povoluje následující funkce:
  - Podmíněný přístup
  - Detekce jailbreaků
  - Správa mobilních aplikací

Přečtěte si víc o [registraci prostřednictvím Pomocníka s nastavením a Apple Configuratoru](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

### USB (přímo)
Přímá registrace Správce vytvoří zásadu Intune a vyexportuje ji do Apple Configuratoru. Zařízení vlastněná společností, která jsou připojena přes USB, se registrují přímo a nevyžadují obnovení do výrobního nastavení. Správce musí každé zařízení zaregistrovat ručně. Zařízení se spravují jako zařízení bez uživatele. Nejsou uzamčená ani pod dohledem a nepodporují podmíněný přístup, detekci jailbreaků ani správu mobilních aplikací. Přečtěte si víc o [přímé registraci prostřednictvím Apple Configuratoru](ios-direct-enrollment-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-device-enrollment-methods))

## Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune
Mobilní zařízení, která nejsou zaregistrovaná, ale připojují se k Exchange ActiveSync (EAS), je možné spravovat pomocí Intune s využitím zásad EAS MDM. Intune využívá Exchange Connector ke komunikaci s protokolem EAS, ať už místním, nebo hostovaným v cloudu.

[Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Správa počítačů s Windows pomocí Intune  
Microsoft Intune můžete také využít ke správě počítačů s Windows, a to pomocí klientského softwaru Intune. Počítače spravované pomocí Intune mohou:

 - Vytvářet sestavy inventáře softwaru a hardwaru
 - Instalovat desktopové aplikace (například soubory .exe a .msi)
 - Nastavení brány firewall

Počítače spravované pomocí klientského softwaru Intune nejde vymazat a nemohou také využívat řadu funkcí správy Intune, jako je třeba nastavení podmíněného přístupu, VPN a Wi-Fi nebo nasazení certifikátů a konfigurací e-mailu.

[Správa počítačů s Windows pomocí Intune](manage-windows-pcs-with-microsoft-intune.md)

##  Podporované platformy zařízení

Intune může spravovat tyto platformy zařízení:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Další kroky
- [Viz Předpoklady pro registraci zařízení](prerequisites-for-enrollment.md)
- [Správa zařízení vlastněných společností](manage-corporate-owned-devices.md)
- [Podporovaná mobilní zařízení a počítače](../get-started/supported-mobile-devices-and-computers.md)



<!--HONumber=Sep16_HO3-->


