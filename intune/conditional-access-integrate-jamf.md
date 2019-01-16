---
title: Integrace Jamf Pro s Microsoft Intune pro dodržování předpisů | Microsoft Intune
description: Použijte zásady dodržování předpisů Microsoft Intune s podmíněným přístupem Azure Active Directory k lepšímu zabezpečení zařízení spravovaných pomocí Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 01/16/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 971dc851714045a8a3b60dfe8ff6c6acc4419294
ms.sourcegitcommit: 7c41f42d6e398ed46aa602ec8aaa4f39aaf92772
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54325011"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrace Jamf Pro s Intune pro dodržování předpisů

Platí pro: Intune na portálu Azure Portal

Pokud vaše organizace používá [Jamf Pro](https://www.jamf.com) ke správě vašich koncových uživatelů Mac, můžete zásady dodržování předpisů Microsoft Intune s podmíněným přístupem Azure Active Directory k zajištění, že jsou kompatibilní zařízení ve vaší organizaci.

## <a name="prerequisites"></a>Předpoklady

Pro konfiguraci podmíněného přístupu s Jamf Pro je potřeba následující:

- Jamf Pro 10.1.0 nebo novější
- [Aplikaci Portál společnosti pro macOS](https://aka.ms/macoscompanyportal)
- Zařízení macOS se systémem OS X 10.11 Yosemite nebo novější

## <a name="connecting-intune-to-jamf-pro"></a>Připojení Intune k Jamf Pro

Propojení služby Intune s Jamf Pro můžete:

1. Vytvoření nové aplikace v Azure
2. Povolení integrace Intune s Jamf Pro
3. Konfigurace podmíněného přístupu v aplikaci Jamf Pro

## <a name="create-an-application-in-azure-active-directory"></a>Vytvoření aplikace v Azure Active Directory

1. V [webu Azure portal](https://portal.azure.com), přejděte na stránku **Azure Active Directory** > **registrace aplikací**.
2. Vyberte **+ registrace nové aplikace**.
3. Zadejte **Zobrazovaný název**, jako například **Podmíněný přístup Jamf**.
4. Vyberte **webovou aplikaci nebo API**.
5. Pomocí adresy URL instance Jamf Pro zadejte **přihlašovací adresu URL**.
6. Vyberte **Vytvořit**. Aplikace se vytvoří a na portálu zobrazí podrobnosti o aplikaci.
7. Uložit kopii **ID aplikace** pro novou aplikaci. Toto ID je zadat v pozdějším postupu. V dalším kroku vyberte **nastavení** a přejděte na **přístup přes rozhraní API** > **klíče**.
8. Na *klíče* podokně, zadejte **popis**, jak dlouho se má čekat, než **Expires**a pak vyberte **Uložit** pro vygenerování aplikace Klíč (hodnota).

   > [!IMPORTANT]
   > Klíč aplikace se zobrazí pouze jednou během tohoto procesu. Nezapomeňte ho uložit, abyste ho měli snadno k dispozici.

8. Na *nastavení* podokno pro aplikaci, přejděte na **přístup přes rozhraní API** > **požadovaná oprávnění**. Vyberte všechna stávající oprávnění a potom klikněte na tlačítko **odstranit** a odstraňte všechna oprávnění. Odstraňuje se stávající oprávnění je nutné přidat nové oprávnění a aplikace funguje, pouze pokud má jediné požadované oprávnění.  
9. Chcete-li přiřadit nové oprávnění, vyberte **+ přidat** > **vyberte rozhraní API** > **rozhraní API Microsoft Intune**a potom klikněte na **vyberte**.
10. Na *povolit přístup z* vyberte **odesílat atributy zařízení do Microsoft Intune** a potom klikněte na tlačítko **vyberte**a potom **provádí**.
11. Na *požadovaná oprávnění* vyberte **udělit oprávnění** a potom **Ano** použít potřebná oprávnění k aplikaci.

    > [!NOTE]
    > Pokud klíč aplikace vyprší, musíte vytvořit nový klíč aplikace v Microsoft Azure a pak aktualizovat data podmíněného přístupu v Jamf Pro. Azure umožňuje mít aktivní starý klíč i nový klíč, aby se zabránilo přerušení služeb.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Povolení integrace Intune s Jamf Pro

1. V [webu Azure portal](https://portal.azure.com), přejděte na stránku **Microsoft Intune** > **dodržování předpisů zařízením** > **Správa partnerského zařízení**.
2. Povolte konektor dodržování předpisů pro Jamf vložením ID aplikace, který jste uložili během předchozího postupu do **Jamf Azure Active Directory App ID** pole.
3. Vyberte **Uložit**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Konfigurace integrace Microsoft Intune v Jamf Pro

1. V Jamf Pro přejděte do části **Global Management (Globální správa)** > **Conditional Access (Podmíněný přístup)**. Klikněte na tlačítko **Edit** (Upravit) na kartě **Microsoft Intune Integration** (Integrace Microsoft Intune).
2. Zaškrtněte políčko **Enable Microsoft Intune Integration** (Povolit integraci Microsoft Intune).
3. Zadejte požadované informace o vašem tenantovi Azure včetně polí **Location (Umístění)**, **Domain name (Název domény)** a **Application ID (ID aplikace)** a **Application Key (Klíč aplikace)**, která jste uložili v předchozích krocích.
4. Vyberte **Uložit**. Jamf Pro otestuje nastavení a ověří úspěšné propojení.

## <a name="set-up-compliance-policies-and-register-devices"></a>Nastavení zásad dodržování předpisů a registrace zařízení

Po dokončení konfigurace integrace mezi Intune a Jamf musíte [použití zásad dodržování předpisů pro zařízení spravovaná aplikací Jamf](conditional-access-assign-jamf.md).



## <a name="next-steps"></a>Další postup

- [Použití zásad dodržování předpisů pro zařízení spravovaná aplikací Jamf](conditional-access-assign-jamf.md)
- [Odešle data Jamf do Intune](data-jamf-sends-to-intune.md)
