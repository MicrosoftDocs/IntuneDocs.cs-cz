---
title: "Registrace zařízení | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8fc415f7-0053-4aa5-8d2b-03202eca4b87
ms.reviewer: damionw
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 69cf07aa0747448e0ef3384b5b5132e0e76aed45
ms.openlocfilehash: 930cbc806d8fd1185cf33fd64d866b88ec9a6a04


---

# Registrace zařízení pro správu v Intune
Správa mobilních zařízení Microsoft Intune (MDM) využívá registraci pro zajištění správy zařízení a povolení přístupu k prostředkům. Způsob registrace zařízení závisí na jeho typu, vlastnictví a požadované úrovni správy. Scénáře pro zařízení vlastněná společností (COD) a Přineste si vlastní zařízení (BYOD) vyžadují proces registrace. Organizace, které využívají protokol Exchange ActiveSync, ať už místní, nebo hostovaný v cloudu, mohou povolit jednodušší správu bez požadavků na registraci. Pomocí klientského softwaru Intune je také možné spravovat počítače s Windows.

###  Podporované platformy zařízení

Intune může spravovat tyto platformy zařízení:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

## Přehled metod registrace zařízení

Následující tabulka popisuje metody registrace zařízení ve vlastnictví společnosti a jejich výhody.

**Metody registrace zařízení se systémem iOS**

| **Metoda** |  **[Vymazání](#Wipe)** | **[Spřažení](#Affinity)**   |   **[Zamčené](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením](#BYOD)** | Ne|    Ano |   Ne |
|**[DEM](#DEM)**|   Ne |Ne |Ne  |
|**[DEP](#DEP)**|   Ano |   Volitelně |   Volitelně|
|**[USB (SA)](#USB-SA)**| Ano |   Volitelně |   Ne|
|**[USB (přímo)](#USB-Direct)**| Ne |    Ne  | Ne|

**Metody registrace zařízení se systémem Windows a Android**

| **Metoda** |  **[Vymazání](#Wipe)** | **[Spřažení](#Affinity)**   |   **[Zamčené](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením](#BYOD)** | Ne|    Ano |   Ne |
|**[DEM](#DEM)**|   Ne |Ne |Ne  |

**Metody registrace pro zařízení ve vlastnictví společnosti**

### Uživatelé s vlastním zařízením
Funkce Přineste si vlastní zařízení. Uživatelé si nainstalují aplikaci Portál společnosti a zaregistrují svoje zařízení. Registrace zařízení na Portálu společnosti zajistí jeho připojení k pracovišti. Registrace zařízení s iOS pomocí Portálu společnosti vyžaduje Apple ID. Funkce Přineste si vlastní zařízení nevyžaduje další konfiguraci pro zařízení ve vlastnictví firmy. Prohlédněte si postup [nastavení správy zařízení](get-ready-to-enroll-devices-in-microsoft-intune.md#set-up-device-management). ([Zpět k tabulce](#overview-of-corporate-owned-device-enrollment-methods))

### DEM
Správce registrace zařízení. Správce vytvoří účty DEM pro správu zařízení vlastněných společností. Správci pak mohou nainstalovat aplikaci Portál společnosti a zaregistrovat velký počet zařízení bez uživatele. Přečtěte si další informace o [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-corporate-owned-device-enrollment-methods))

### DEP
Apple Device Enrollment Program. Správce vytvoří zásady a nasadí je „bezdrátově “ do zařízení s iOS zakoupených a spravovaných pomocí DEP. Zařízení se zaregistruje, když uživatel spustí Pomocníka s nastavením iOS. Tato metoda podporuje režim **iOS – Pod dohledem**, který pak povoluje následující funkce:
  - Registrace uzamčeného zařízení
  - Podmíněný přístup
  - Detekce jailbreaků
  - Správa mobilních aplikací

Přečtěte si další informace o [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-corporate-owned-device-enrollment-methods))

### USB (SA)
Registrace prostřednictvím Pomocníka s nastavením přes připojení USB. Správce vytvoří zásadu Intune a vyexportuje ji do Apple Configuratoru. Pro zařízení vlastněná společností, která jsou připojená přes USB, jsou připraveny zásady Intune. Správce musí každé zařízení zaregistrovat ručně. Uživatelé dostanou svoje zařízení a spuštěním Pomocníka s nastavením je zaregistrují. Tato metoda podporuje režim **iOS – Pod dohledem**, který pak povoluje následující funkce:
  - Podmíněný přístup
  - Detekce jailbreaků
  - Správa mobilních aplikací

Přečtěte si víc o [registraci prostřednictvím Pomocníka s nastavením a Apple Configuratoru](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-corporate-owned-device-enrollment-methods))

### USB (přímo)
Přímá registrace Správce vytvoří zásadu Intune a vyexportuje ji do Apple Configuratoru. Zařízení vlastněná společností, která jsou připojena přes USB, se registrují přímo a nevyžadují obnovení do výrobního nastavení. Správce musí každé zařízení zaregistrovat ručně. Zařízení se spravují jako zařízení bez uživatele. Nejsou uzamčená ani pod dohledem a nepodporují podmíněný přístup, detekci jailbreaků ani správu mobilních aplikací. Přečtěte si víc o [přímé registraci prostřednictvím Apple Configuratoru](ios-direct-enrollment-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of-corporate-owned-device-enrollment-methods))

**Chování mobilních zařízení ve vlastnictví firmy**

### Vymazání
Určuje, jestli registrace zařízení vyžaduje, aby se v zařízení obnovilo tovární nastavení, odebrala se z něj všechna data a vrátilo se do původního stavu.
([Zpět k tabulce](#overview-of-corporate-owned-device-enrollment-methods))

### Spřažení
Určuje, jestli metoda registrace podporuje přidružení uživatele, které propojí zařízení s konkrétním uživatelem. Zařízení označená „Volitelně“ se dají zaregistrovat s přidružením uživatele nebo bez něj. Přidružení uživatele je nezbytné pro podporu následujících funkcí:
  - Aplikace MAM (správa mobilních aplikací)
  - Podmíněný přístup k e-mailu a firemním datům
  - Aplikace Portál společnosti

([Zpět k tabulce](#overview-of-corporate-owned-device-enrollment-methods))

### Uzamčení
Určuje, jestli jde zařízení zamknout a zabránit tak uživateli odebrání zásad Intune (to by znamenalo vyjmutí zařízení ze správy). U zařízení s iOS zamknutí vyžaduje, aby byl nastaven režim Pod dohledem.
([Zpět k tabulce](#overview-of-corporate-owned-device-enrollment-methods)) ([Zpět k tabulce](#overview-of-corporate-owned-device-enrollment-methods))

## Povolení registrace zařízení  
 Registrace umožňuje uživatelům přistupovat k prostředkům společnosti z jejich osobních zařízení a správcům umožňuje zajistit, že tato zařízení dodržují zásady, které chrání prostředky společnosti. Toto je nejlepší způsob, jak pro Intune povolit scénáře Přineste si vlastní zařízení. Správce musí povolit registraci pomocí konzoly Intune. Může to vyžadovat vytvoření vztahu důvěryhodnosti se zařízením a přiřazení licencí uživatelům. Zařízení se pak zaregistruje, obvykle uživatelem, který zadá přihlašovací údaje svého pracovního nebo školního účtu. Potom zařízení obdrží zásady ze služby Intune a získá přístup k prostředkům.

[Příprava registrace zařízení v Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)

## Registrace zařízení vlastněných společností
Zařízení vlastněná společností (COD) je možné spravovat pomocí konzoly Intune. Zařízení s iOS se mohou zaregistrovat přímo pomocí nástrojů poskytovaných společností Apple. Všechny typy zařízení může zaregistrovat správce využívající správce registrace zařízení. Zařízení s číslem IMEI se také dají identifikovat a označit jako zařízení ve vlastnictví společnosti, což umožní využít scénáře COD.

[Registrace zařízení vlastněných společností](manage-corporate-owned-devices.md)

## Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune
Mobilní zařízení, která nejsou zaregistrovaná, ale připojují se k Exchange ActiveSync (EAS), je možné spravovat pomocí Intune s využitím zásad EAS MDM. Intune využívá Exchange Connector ke komunikaci s protokolem EAS, ať už místním, nebo hostovaným v cloudu.



[Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Intune](mobile-device-management-with-exchange-activesync-and-microsoft-intune.md)


## Správa počítačů s Windows pomocí Intune  
Microsoft Intune můžete také využít ke správě počítačů se systémem Windows, a to pomocí klientského softwaru Intune pro počítače s Windows. Počítače spravované pomocí Intune mohou:

 - Vytvářet sestavy inventáře softwaru a hardwaru
 - Instalovat desktopové aplikace (například soubory .exe a .msi)
 - Nastavení brány firewall

Počítače spravované pomocí klientského softwaru Intune nejde selektivně vymazat nebo vyřadit. Nemohou také využívat řadu funkcí správy Intune, jako je třeba podmíněný přístup, nastavení připojení VPN a Wi-Fi nebo nasazení certifikátů a konfigurací e-mailu.

[Správa počítačů s Windows pomocí Intune](manage-windows-pcs-with-microsoft-intune.md)



<!--HONumber=Jun16_HO5-->


