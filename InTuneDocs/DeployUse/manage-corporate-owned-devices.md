---
# required metadata

title: Správa zařízení ve vlastnictví firmy | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 2b60bbff-25e6-489b-9621-c71b4275fa06

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Registrace zařízení vlastněných společností pomocí Microsoft Intune
Zařízení vlastněná společností nebo organizací (COD) se mohou do Intune zaregistrovat několika různými způsoby v závislosti na zařízení, způsobu jeho koupě a potřebách organizace.

## Zařízení s iOS ve vlastnictví firmy
Tato metoda registrace je vhodná pro scénáře Vyberte si vlastní zařízení (CYOD), ve kterých organizace koupí zařízení pro uživatele, ale chce si zachovat jejich správu. Pokud organizace koupila zařízení s iOS, můžete předkonfigurovat registraci, aby bylo zařízení spravované od prvního zapnutí uživatelem. Intune podporuje registraci prostřednictvím [programu Apple Device Enrollment Program (DEP)](ios-device-enrollment-program-in-microsoft-intune.md) nebo s použitím nástroje Apple Configurator spuštěného na počítači Mac pro [přímou](ios-direct-enrollment-in-microsoft-intune.md) registraci nebo registraci pomocí [průvodce nastavením](ios-setup-assistant-enrollment-in-microsoft-intune.md).

[Registrace zařízení iOS vlastněných společností](enroll-corporate-owned-ios-devices-in-microsoft-intune.md)

## Správce registrace zařízení
Organizace mohou pomocí Intune spravovat velké počty mobilních zařízení s jediným uživatelským účtem nazývaným účet správce registrace. Po vytvoření účtu správce registrace zařízení může být tento účet použitý manažerem k registraci více než standardních pěti zařízení povolených ve výchozím nastavení běžným uživatelům. Registrace zařízení pomocí správce registrace zařízení funguje pouze u zařízení, která nepoužívá konkrétní uživatel. Tato zařízení jsou vhodná například pro aplikace POS nebo aplikace nástrojů, ale nejsou vhodná pro uživatele, kteří potřebují přístup k e-mailu nebo firemním prostředkům.

[Registrace firemních zařízení pomocí správce registrace zařízení](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md)

## Číslo IMEI (International Mobile Equipment Identity)
Čísla IMEI jsou běžnou vlastností zařízení u celé řady výrobců mobilních zařízení. Správci Intune mohou importovat čísla IMEI pro zařízení, která společnost vlastní. Když se stane zařízení spravovaným v Intune, může být označené jako zařízení vlastněné společností a být cílem příslušné zásady.

[Určení podnikem vlastněných zařízení podle kódů IMEI (International Mobile Equipment Identity)](specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

## Přehled metod registrace zařízení ve vlastnictví firmy

Následující tabulka popisuje metody registrace zařízení ve vlastnictví společnosti a jejich výhody.

**Metody registrace zařízení se systémem iOS**

| **Metoda** |  **[Reset](#Reset)** |   **[Spřažení](#Affinity)**   |   **[Zamčené](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením](#BYOD)** | Ne|    Ano |   Ne |
|**[DEM](#DEM)**|   Ne |Ne |Ne  |
|**[DEP](#DEP)**|   Ano |   Volitelně |   Volitelně|
|**[USB (SA)](#USB-SA)**| Ano |   Volitelně |   Ne|
|**[USB (přímo)](#USB-Direct)**| Ne |    Ne  | Ne|

**Metody registrace zařízení se systémem Windows a Android**

| **Metoda** |  **[Vymazání](#Wipe)** | **[Uživatel](#User)**   |   **[Zamčené](#Locked)** |
|:---:|:---:|:---:|:---:|
|**[Uživatelé s vlastním zařízením](#BYOD)** | Ne|    Ano |   Ne |
|**[DEM](#DEM)**|   Ne |Ne |Ne  |

**Metody registrace pro zařízení ve vlastnictví společnosti**

### Uživatelé s vlastním zařízením
Funkce Přineste si vlastní zařízení. Uživatelé si nainstalují aplikaci Portál společnosti a zaregistrují svoje zařízení. Registrace zařízení na Portálu společnosti zajistí jeho připojení k pracovišti. Registrace zařízení s iOS pomocí Portálu společnosti vyžaduje Apple ID. Funkce Přineste si vlastní zařízení nevyžaduje další konfiguraci pro zařízení ve vlastnictví firmy. Prohlédněte si postup [nastavení správy zařízení](get-ready-to-enroll-devices-in-microsoft-intune#set-up-device-management.md). ([Zpět k tabulce](#overview-of corporate-owned-device-enrollment-methods))

### DEM
Správce registrace zařízení. Správce vytvoří účty DEM. Správci pak mohou nainstalovat aplikaci Portál společnosti a zaregistrovat velký počet zařízení bez uživatele. Přečtěte si další informace o [DEM](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of corporate-owned-device-enrollment-methods))

### DEP
Apple Device Enrollment Program. Správce vytvoří zásady a zařízení s iOS zakoupených a spravovaných s DEP je nasadí „vzduchem“. Zařízení se zaregistruje, když uživatel spustí Pomocníka s nastavením iOS. Tato metoda podporuje režim **iOS – Pod dohledem**, který pak povoluje následující funkce:
  - Registrace uzamčeného zařízení
  - Podmíněný přístup
  - Detekce jailbreaků
  - Správa mobilních aplikací

Přečtěte si další informace o [DEP](ios-device-enrollment-program-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of corporate-owned-device-enrollment-methods))

### USB (SA)
Registrace prostřednictvím Pomocníka s nastavením přes připojení USB. Správce vytvoří zásadu Intune a vyexportuje ji do Apple Configuratoru. Zařízení připojená přes USB mají připravené zásady Intune. Správce musí každé zařízení zaregistrovat ručně. Uživatelé dostanou svoje zařízení a spuštěním Pomocníka s nastavením je zaregistrují. Tato metoda podporuje režim **iOS – Pod dohledem**, který pak povoluje následující funkce:
  - Registrace uzamčeného zařízení
  - Podmíněný přístup
  - Detekce jailbreaků
  - Správa mobilních aplikací

Přečtěte si víc o [registraci prostřednictvím Pomocníka s nastavením a Apple Configuratoru](ios-setup-assistant-enrollment-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of corporate-owned-device-enrollment-methods))

### USB (přímo)
Přímá registrace Správce vytvoří zásadu Intune a vyexportuje ji do Apple Configuratoru. Zařízení s připojením USB zařízení se registrují přímo a nevyžadují obnovení do výrobního nastavení. Správce musí každé zařízení zaregistrovat ručně. Zařízení se spravují jako zařízení bez uživatele. Nejsou uzamčená ani pod dohledem a nepodporují podmíněný přístup, detekci jailbreaků ani správu mobilních aplikací. Přečtěte si víc o [přímé registraci prostřednictvím Apple Configuratoru](ios-direct-enrollment-in-microsoft-intune.md). ([Zpět k tabulce](#overview-of corporate-owned-device-enrollment-methods))

**Chování mobilních zařízení ve vlastnictví firmy**

### Reset
Určuje, jestli registrace zařízení vyžaduje, aby se v zařízení obnovilo tovární nastavení, odebrala se z něj všechna data a vrátilo se do původního stavu.
([Zpět k tabulce](#overview-of corporate-owned-device-enrollment-methods))

### Spřažení
Určuje, jestli metoda registrace podporuje přidružení uživatele, které propojí zařízení s konkrétním uživatelem. Zařízení označená „Volitelně“ se dají zaregistrovat s přidružením uživatele nebo bez něj. Přidružení uživatele je nezbytné pro podporu následujících funkcí:
  - Aplikace MAM (správa mobilních aplikací)
  - Podmíněný přístup k e-mailu a firemním datům
  - Aplikace Portál společnosti

([Zpět k tabulce](#overview-of corporate-owned-device-enrollment-methods))

### Uzamčení
Určuje, jestli jde zařízení zamknout a zabránit tak uživateli odebrání zásad Intune (to by znamenalo vyjmutí zařízení ze správy). U zařízení s iOS zamknutí vyžaduje, aby byl nastaven režim Pod dohledem.
([Zpět k tabulce](#overview-of corporate-owned-device-enrollment-methods)) ([Zpět k tabulce](#overview-of corporate-owned-device-enrollment-methods))


<!--HONumber=Jun16_HO1-->


