---
title: Integrace Jamf Pro s Microsoft Intune pro dodržování předpisů | Microsoft Intune
description: Použijte zásady dodržování předpisů Microsoft Intune s podmíněným přístupem Azure Active Directory k lepšímu zabezpečení zařízení spravovaných pomocí Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: cc547926d95e3fa1bec54b4ea55f764b5701b3b7
ms.sourcegitcommit: bee072b61cf8a1b8ad8d736b5f5aa9bc526e07ec
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53816816"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrace Jamf Pro s Intune pro dodržování předpisů

Platí pro: Intune na portálu Azure Portal

Pokud vaše organizace používá [Jamf Pro](https://www.jamf.com) ke správě koncových uživatelů Mac, můžete použít zásady dodržování předpisů Microsoft Intune s podmíněným přístupem Azure Active Directory a zajistit, že zařízení ve vaší organizaci splňují požadavky.

## <a name="prerequisites"></a>Požadavky

Pro konfiguraci podmíněného přístupu s Jamf Pro je potřeba následující:

- Jamf Pro 10.1.0 nebo novější
- [Aplikaci Portál společnosti pro macOS](https://aka.ms/macoscompanyportal)
- Zařízení macOS se systémem OS X 10.11 Yosemite nebo novější

## <a name="connecting-intune-to-jamf-pro"></a>Připojení Intune k Jamf Pro

Intune propojíte s Jamf Pro následujícími postupy:

1. Vytvoření nové aplikace v Azure
2. Povolení integrace Intune s Jamf Pro
3. Konfigurace podmíněného přístupu v aplikaci Jamf Pro

## <a name="create-a-new-application-in-azure-active-directory"></a>Vytvoření nové aplikace v Azure Active Directory

1. Otevřete **Azure Active Directory** > **Registrace aplikací**.
2. Klikněte na možnost **Registrace nové aplikace**.
3. Zadejte **Zobrazovaný název**, jako například **Podmíněný přístup Jamf**.
4. Vyberte **webovou aplikaci nebo API**.
5. Pomocí adresy URL instance Jamf Pro zadejte **přihlašovací adresu URL**.
6. Klikněte na **Vytvořit aplikaci**.
7. Uložte nově vytvořené **ID aplikace**, otevřete **Nastavení** a přejděte na **Přístup přes rozhraní API** > **Klíče** a vytvořte nový klíč aplikace. Zadejte **Popis**, jak dlouho se má čekat, než **vyprší jeho platnost**, a potom klíč aplikace uložte.

   > [!IMPORTANT]
   > Klíč aplikace se zobrazí pouze jednou během tohoto procesu. Nezapomeňte ho uložit, abyste ho měli snadno k dispozici.

8. Otevřete **Nastavení**, přejděte na **Přístup přes rozhraní API** > **Požadovaná oprávnění** a odstraňte všechna oprávnění.

   > [!NOTE]
   > Přidejte nové požadované oprávnění. Aplikace bude správně fungovat, pouze pokud má jediné požadované oprávnění.

9. Vyberte **Rozhraní API Microsoft Intune** a klikněte na možnost **Vybrat**.
10. Zvolte **Odesílat atributy zařízení do Microsoft Intune** a klikněte na **Vybrat**.
11. Klikněte na tlačítko **Udělit oprávnění** po uložení požadovaných oprávnění pro aplikaci.

    > [!NOTE]
    > Pokud klíč aplikace vyprší, musíte vytvořit nový klíč aplikace v Microsoft Azure a pak aktualizovat data podmíněného přístupu v Jamf Pro. Azure umožňuje mít aktivní starý klíč i nový klíč, aby se zabránilo přerušení služeb.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Povolení integrace Intune s Jamf Pro

1. Na portálu Microsoft Azure Portal otevřete **Microsoft Intune** > **Dodržování předpisů zařízením** > **Správa partnerského zařízení**.
2. Povolte konektor dodržování předpisů pro Jamf vložením ID aplikace do pole **ID aplikace Azure AD pro Jamf**.
3. Klikněte na **Uložit**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Konfigurace integrace Microsoft Intune v Jamf Pro

1. V Jamf Pro přejděte do části **Global Management (Globální správa)** > **Conditional Access (Podmíněný přístup)**. Klikněte na tlačítko **Edit** (Upravit) na kartě **Microsoft Intune Integration** (Integrace Microsoft Intune).
2. Zaškrtněte políčko **Enable Microsoft Intune Integration** (Povolit integraci Microsoft Intune).
3. Zadejte požadované informace o vašem tenantovi Azure včetně polí **Location (Umístění)**, **Domain name (Název domény)** a **Application ID (ID aplikace)** a **Application Key (Klíč aplikace)**, která jste uložili v předchozích krocích.
4. Klikněte na **Uložit**. Jamf Pro otestuje nastavení a ověří úspěšné propojení.

## <a name="set-up-compliance-policies-and-register-devices"></a>Nastavení zásad dodržování předpisů a registrace zařízení

Po dokončení konfigurace integrace mezi Intune a Jamf musíte [použít zásady dodržování předpisů pro zařízení spravovaná aplikací Jamf](conditional-access-assign-jamf.md).

## <a name="information-shared-from-jamf-pro-to-intune"></a>Informace sdílené z Jamf Pro do Intune

Jamf Pro zaznamená informace o inventáři spravovaných zařízeních macOS. Jamf Pro dodá do Intune následující informace:

* ID zařízení v Azure AD
* Stav inventáře JAMF (stav inventáře počítače připojeného k Jamf Pro během posledních 24 hodin)
* Verze operačního systému
* ID uživatele v Azure AD
* Šifrované (FileVault 2)
* Stav serveru gatekeeper
* Heslo: minimální počet znakových sad
* Vypršení platnosti hesla (dny)
* Typ hesla – jednoduché, alfanumerické nebo neznámé
* Zakázat automatické přihlášení
* Požadovaná délka hesla
* Heslo: počet předchozích hesel, aby se předešlo opětovnému použití
* Ochrana Integrity systému
* Poslední vrácení se změnami
* Typ architektury
* Dostupné sloty paměti RAM
* Kapacita baterie
* Spouštěcí paměť ROM
* Rychlost sběrnice
* Velikost mezipaměti
* Název zařízení
* Připojení k doméně
* ID Jamf
* Adresa MAC
* Vytvoření
* Model
* Identifikátor modelu
* Rychlost síťové karty
* Počet jader
* Počet procesorů
* Operační systém
* Platforma
* Rychlost procesoru
* Typ procesoru
* Sekundární adresa MAC
* Sériové číslo
* Verze řadiče pro správu systému (SMC)
* Celkové paměti RAM
* UDID
* E-mail uživatele

## <a name="next-steps"></a>Další postup

- [Použití zásad dodržování předpisů pro zařízení spravovaná aplikací Jamf](conditional-access-assign-jamf.md)
