---
title: Zásady dodržování předpisů zařízením pro zařízení Jamf | Microsoft Intune
titlesuffix: Microsoft Intune
description: Použijte zásady dodržování předpisů Microsoft Intune s podmíněným přístupem Azure Active Directory k lepšímu zabezpečení zařízení spravovaných pomocí Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/02/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c87fd2bd-7f53-4f1b-b985-c34f2d85a7bc
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 65a82a171253a40b05c42abec3a12371c471e860
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55837389"
---
# <a name="enforce-compliance-on-macs-managed-with-jamf-pro"></a>Vynucení dodržování předpisů v počítačích Mac spravovaných aplikací Jamf Pro

Platí pro: Intune na portálu Azure Portal

Pomocí Azure Active Directory a zásad podmíněného přístupu pro Microsoft Intune zajistíte, aby vaši koncoví uživatelé splňovali požadavky organizace. Tyto zásady můžete použít na počítače Mac, které jsou [spravované pomocí Jamf Pro](conditional-access-integrate-jamf.md). To vyžaduje přístup ke konzolám Intune a Jamf Pro.

## <a name="set-up-device-compliance-policies-in-intune"></a>Nastavení zásad dodržování předpisů pro zařízení v Intune

1. Otevřete Microsoft Azure a pak přejděte na **Intune** > **Dodržování předpisů zařízením** > **Zásady**. Uživatelé nedodržující předpisy a skupiny můžete vytvořit zásady pro systém macOS včetně výběru série akcí (například odesílání upozornění e-mailů).
2. Vyhledejte požadované skupiny a pak u nich použijte zásady.

> [!Note]
> Intune v zájmu dodržování předpisů vyžaduje úplné šifrování disků.

## <a name="deploy-the-company-portal-app-for-macos-in-jamf-pro"></a>Nasazení aplikace Portál společnosti pro macOS v Jamf Pro

Aplikaci Portál společnosti pro macOS v Jamf Pro byste měli nasadit jako instalaci na pozadí podle tohoto postupu:

1. V zařízení s macOS stáhněte [aplikaci Portál společnosti pro macOS](https://go.microsoft.com/fwlink/?linkid=862280). Neinstalujte ji. Kopii aplikace potřebujete k nahrání do Jamf Pro.
2. Spusťte aplikaci Jamf Pro a pak přejděte do části **Správa počítače (Computer management)** > **Balíčky (Packages)**.
3. Pomocí aplikace Portál společnosti pro macOS vytvořte nový balíček a pak klikněte na **Uložit**.
4. V části **Computers (Počítače)** > **Policies (Zásady)** vyberte možnost **New (Nová)**.
5. Nakonfigurujte nastavení zásad pomocí datové části **General** (Obecné). Měli byste nastavit:
   - Trigger: Vyberte **Enrollment Complete** (Registrace dokončena) a **Recurring Check-in** (Opakované vrácení se změnami).
   - Execution Frequency (Četnost spuštění): Vyberte **Once per computer** (Jednou na počítač).
6. Vyberte datovou část **Packages (Balíčky)** klikněte na **Configure (Konfigurovat)**.
7. Kliknutím na **Add (Přidat)** vyberte balíček pomocí aplikace Portál společnosti.
8. Z místní nabídky z **Action (Akce)** zvolte možnost **Install (Nainstalovat)**.
9. Nakonfigurujte nastavení balíčku.
10. Kliknutím na kartu **Obor** určete, na které počítače se má nainstalovat aplikace Portál společnosti. Klikněte na **Uložit**. Zásady spustí vymezená zařízení při příštím výskytu vybrané aktivační události v počítači a při splnění kritérií v datové části **General**.

## <a name="create-a-policy-in-jamf-pro-to-have-users-register-their-devices-with-azure-active-directory"></a>Vytvoření zásad v Jamf Pro, které donutí uživatele zaregistrovat zařízení ve službě Azure Active Directory

> [!NOTE]
> Před provedením dalších kroků musíte [nasadit Portál společnosti](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro) pro macOS.  

Koncoví uživatelé musí aplikaci Portál společnosti spustit prostřednictvím samoobslužné služby Jamf, aby se zařízení zaregistrovalo s Azure AD jako zařízení spravované aplikací Jamf Pro. To bude vyžadovat, aby koncoví uživatelé provedli akci. Doporučujeme, abyste e-mailem, přes Jamf Pro nebo jiným způsobem [kontaktovali koncové uživatele](end-user-educate.md) a oznámili jim, že musí kliknout na tlačítko ve službě Jamf Self Service.

> [!WARNING]
> Aby bylo možné zahájit registraci zařízení, musí se aplikace Portál společnosti spustit ze služby Jamf Self Service. <br><br>Když aplikaci Portál společnosti spustíte ručně (například ze složek Aplikace nebo Stažené položky), zařízení se nezaregistruje. Pokud koncový uživatel spustí Portál společnosti ručně, zobrazí se mu upozornění, že účet není připojen (AccountNotOnboarded).

1. V Jamf Pro přejděte na **Počítače (Computers)** > **Zásady (Policies)** a vytvořte novou zásadu pro registraci zařízení.
2. Nakonfigurujte datovou část **Microsoft Intune Integration** (Integrace Microsoft Intune) včetně frekvence aktivační události a spouštění.
3. Kliknutím na kartu **Scope (Obor)** nastavte obor zásad na všechna cílová zařízení.
4. Kliknutím na kartu **Self Service (Samoobslužná služba)** zpřístupněte zásady v samoobslužné službě Jamf. Zahrňte zásadu v kategorii **Device Compliance (Dodržování předpisů zařízením)**. Klikněte na **Uložit**.

## <a name="removing-a-jamf-managed-device-from-intune"></a>Odebrání zařízení spravovaného prostřednictvím Jamf z Intune

Zařízení spravované prostřednictvím Jamf můžete z konzoly Intune odebrat výběrem možnosti **Odstranit** v zobrazení **Všechna zařízení**. Hromadné odstranění zařízení se dá povolit výběrem více zařízení a kliknutím na **Odstranit**.

Získejte informace o [odebírání zařízení spravovaného prostřednictvím Jamf v dokumentaci k Jamf Pro](https://www.jamf.com/jamf-nation/articles/80/unmanaging-computers-while-preserving-their-inventory-information). Můžete také pomocí lístku podpory požádat o další pomoc [podporu Jamf](https://www.jamf.com/support/). 

## <a name="next-steps"></a>Další postup

- [Podmíněný přístup ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
- [Začínáme s podmíněným přístupem v adresáři Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
