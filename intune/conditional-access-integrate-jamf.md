---
title: "Integrace Jamf Pro s Intune pro dodržování předpisů"
titlesuffix: Azure portal
description: "Zajistěte dodržování předpisů k lepšímu zabezpečení zařízení spravovaných aplikací Jamf."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6b37ffd23f8cf8764ba457b0803dfc308cf1c071
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrace Jamf Pro s Intune pro dodržování předpisů

|Platí pro: Intune na portálu Azure Portal |
|--|
|Hledáte dokumentaci k Intune na klasickému portálu? [Přejděte sem](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Aktuálně ve verzi Private Preview|
|--|
|Funkce popsané v tomto tématu jsou zákazníkům momentálně k dispozici jen ve verzi Private Preview. Jakmile budou vydány pro všechny zákazníky, tato zpráva zmizí.|
| |

Pokud vaše organizace používá [Jamf Pro](https://www.jamf.com) ke správě koncových uživatelů Mac, můžete použít zásady dodržování předpisů Microsoft Intune s podmíněným přístupem Azure Active Directory a zajistit, že zařízení ve vaší organizaci splňují požadavky.

## <a name="prerequisites"></a>Požadavky

Pro konfiguraci podmíněného přístupu s Jamf Pro je potřeba následující:

- Přístup k Intune Private Preview pro macOS k zajištění podmíněného přístupu
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
4. Vyberte možnost **Webová aplikace nebo API**.
5. Zadejte **Přihlašovací adresu URL** pro Jamf Pro.
6. Klikněte na **Vytvořit aplikaci**.
7. Uložte nově vytvořené **ID aplikace**, pak otevřete **Všechna nastavení** > **Klíče** a vytvořte nový klíč aplikace. Uložte klíč aplikace.

  > [!NOTE]
  > Klíč aplikace se zobrazí pouze jednou během tohoto procesu. Nezapomeňte ho uložit, abyste ho měli snadno k dispozici.

8. Přejděte na **Všechna nastavení** > **Přístup přes rozhraní API** > **Požadovaná oprávnění** a odstraňte všechna oprávnění.

  > [!NOTE]
  > Přidejte nové požadované oprávnění. Aplikace bude správně fungovat, pouze pokud má jediné požadované oprávnění.

9.  Vyberte **Rozhraní API Microsoft Intune** a klikněte na možnost **Vybrat**.
10. Zvolte **Odesílat atributy zařízení do Microsoft Intune** a klikněte na **Vybrat**.
11. Klikněte na tlačítko **Udělit oprávnění** po uložení požadovaných oprávnění pro aplikaci.

  > [!NOTE]
  > Pokud klíč aplikace vyprší, musíte vytvořit nový klíč aplikace v Microsoft Azure a pak aktualizovat data podmíněného přístupu v Jamf Pro. Azure umožňuje mít aktivní starý klíč i nový klíč, aby se zabránilo přerušení služeb.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Povolení integrace Intune s Jamf Pro

1. Na portálu Microsoft Azure otevřete **Microsoft Intune** > **Dodržování předpisů zařízením** > **Konektor dodržování předpisů pro Jamf**.
2. Povolte konektor dodržování předpisů pro Jamf vložením ID aplikace do pole **ID aplikace Azure AD pro Jamf**.
3. Klikněte na **Uložit**.

## <a name="configure-conditional-access-in-jamf-pro"></a>Konfigurace podmíněného přístupu v aplikaci Jamf Pro

1. V Jamf Pro přejděte do části **Global Management (Globální správa)** > **Conditional Access (Podmíněný přístup)**. Klikněte na tlačítko **Edi t(Upravit)** na kartě **Microsoft**.
2. Zaškrtněte políčko **Enable Conditional Access with Microsoft (Povolit podmíněný přístup pro Microsoft)**.
3. Zadejte požadované informace o vašem tenantovi Azure včetně polí **Location (Umístění)**, **Domain name (Název domény)** a **Application ID (ID aplikace)** a **Application Key (Klíč aplikace)**, která jste uložili v předchozích krocích.
4. Klikněte na **Save (Uložit)**. Jamf Pro otestuje nastavení a ověří úspěšné propojení.

## <a name="information-shared-from-jamf-pro-to-intune"></a>Informace sdílené z Jamf Pro do Intune

Jamf Pro zaznamená informace o inventáři spravovaných zařízeních macOS. Jamf Pro dodá do Intune následující informace:

* ID zařízení v Azure AD
* Stav inventáře JAMF (stav inventáře počítače připojeného k Jamf Pro během posledních 24 hodin)
* Verze operačního systému
* ID uživatele v Azure AD
* Šifrované (FileVault 2)
* Stav serveru gatekeeper
* Heslo: minimální počet znakových sad
* Omezená platnost hesla (ve dnech)
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
* Značka
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
* Celkem paměti RAM
* UDID
* E-mail uživatele

## <a name="next-steps"></a>Další kroky

- [Použití zásad dodržování předpisů pro zařízení spravovaná aplikací Jamf](conditional-access-assign-jamf.md)
