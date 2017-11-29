---
title: "Použití zásad dodržování předpisů pro zařízení spravovaná aplikací Jamf"
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
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6184552ce901ffc062f0453f169ec992049ae69b
ms.sourcegitcommit: 82088d297eef629e3da6011681ead442ae7e25f7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2017
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Vynucení dodržování předpisů v počítačích Mac spravovaných aplikací Jamf Pro

|Platí pro: Intune na portálu Azure Portal |
|--|
|Hledáte dokumentaci k Intune na klasickému portálu? [Přejděte sem](/intune/introduction-intune?toc=/intune-classic/toc.json).|
| |

|Aktuálně ve verzi Private Preview|
|--|
|Funkce popsané v tomto tématu jsou zákazníkům momentálně k dispozici jen ve verzi Private Preview. Jakmile budou vydány pro všechny zákazníky, tato zpráva zmizí.|
| |

Pomocí Azure Active Directory a zásad podmíněného přístupu pro Microsoft Intune zajistíte, aby vaši koncoví uživatelé splňovali požadavky organizace. Tyto zásady můžete použít na počítače Mac, které jsou [spravované pomocí Jamf Pro](conditional-access-integrate-jamf.md). To vyžaduje přístup ke konzolám Intune a Jamf Pro.

## <a name="set-up-device-compliance-policies-in-intune"></a>Nastavení zásad dodržování předpisů pro zařízení v Intune

1. Otevřete Microsoft Azure a pak přejděte na **Intune** > **Dodržování předpisů zařízením** > **Zásady**. Můžete vytvářet zásady pro systém macOS včetně výběru série akcí (například zasílání e-mailů s upozorněním) pro uživatele a skupiny, kteří nesplňují požadavky.
2. Vyhledejte požadované skupiny a pak u nich použijte zásady.

## <a name="require-the-company-portal-app-for-macos"></a>Požadavek na aplikaci Portál společnosti pro macOS

1. V zařízení s macOS přejděte na https://aka.ms/macoscompanyportal a stáhněte aktuální verzi aplikace Portál společnosti pro macOS.
2. Spusťte aplikaci Jamf Pro a pak přejděte do části **Správa počítače (Computer management)** > **Balíčky (Packages)**.
3. Pomocí aplikace Portál společnosti pro macOS vytvořte nový balíček a pak klikněte na **Uložit**.
4. V části **Computers (Počítače)** > **Policies (Zásady)** vyberte možnost **New (Nová)**.
5. Pomocí datové části **General (Obecné)** nakonfigurujte nastavení zásad, včetně frekvence aktivační události a spouštění.
6. Vyberte datovou část **Packages (Balíčky)** klikněte na **Configure (Konfigurovat)**.
7. Kliknutím na **Add (Přidat)** vyberte balíček pomocí aplikace Portál společnosti.
8. Z místní nabídky z **Action (Akce)** zvolte možnost **Install (Nainstalovat)**.
9. Nakonfigurujte nastavení balíčku.
10. Kliknutím na kartu **Obor** určete, na které počítače se má nainstalovat aplikace Portál společnosti. Klikněte na **Uložit**. Zásady spustí vymezená zařízení při příštím výskytu vybrané aktivační události v počítači a při splnění kritérií v datové části **General**.

## <a name="direct-your-users-to-register-jamf-pro-managed-devices-with-azure-active-directory"></a>Pokyny uživatelům k registraci zařízení spravovaných aplikací Jamf Pro pomocí Azure Active Directory

> [!NOTE]
> Před provedením dalších kroků musíte [nasadit Portál společnosti](conditional-access-assign-jamf.md#require-the-company-portal-app-for-macos) pro macOS.  

Koncoví uživatelé musí aplikaci Portál společnosti spustit prostřednictvím samoobslužné služby Jamf, aby se zařízení zaregistrovalo s Azure AD jako zařízení spravované aplikací Jamf Pro.

1. V Jamf Pro přejděte na **Počítače (Computers)** > **Zásady (Policies)** a vytvořte novou zásadu pro registraci zařízení.
2. Nakonfigurujte datovou část **Conditional Access (Podmíněný přístup)** včetně frekvence aktivační události a spouštění. Nastaví prioritu na hodnotu **After (Po)**.
3. Kliknutím na kartu **Scope (Obor)** nastavte obor zásad na všechna cílová zařízení.
4. Kliknutím na kartu **Self Service (Samoobslužná služba)** zpřístupněte zásady v samoobslužné službě Jamf. Zahrňte zásadu v kategorii **Device Compliance (Dodržování předpisů zařízením)**. Klikněte na **Save (Uložit)**.
