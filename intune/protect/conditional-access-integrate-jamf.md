---
title: Integrace Jamf Pro s Microsoft Intune pro dodržování předpisů
titleSuffix: Microsoft Intune
description: K usnadnění zabezpečení zařízení spravovaných Jamf Microsoft Intune použijte zásady dodržování předpisů Azure Active Directory podmíněný přístup.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b439067d06cf49a4ff83288e109d1fccd3801106
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71729770"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrace Jamf Pro s Intune pro dodržování předpisů

Platí pro: Intune na portálu Azure Portal

Pokud vaše organizace používá [Jamf pro](https://www.jamf.com) ke správě počítačů Mac koncových uživatelů, můžete použít Microsoft Intune zásady dodržování předpisů s Azure Active Directory podmíněný přístup, abyste zajistili, že zařízení ve vaší organizaci splňují předpisy.

## <a name="prerequisites"></a>Požadované součásti

Abyste mohli nakonfigurovat podmíněný přístup pomocí Jamf pro, potřebujete následující:

- Jamf Pro 10.1.0 nebo novější
- [Aplikaci Portál společnosti pro macOS](https://aka.ms/macoscompanyportal)
- Zařízení macOS se systémem OS X 10.11 Yosemite nebo novější

## <a name="connect-intune-to-jamf-pro"></a>Připojení Intune k Jamf pro

Postup připojení Intune s Jamf pro:

1. Vytvoří novou aplikaci v Azure.
2. Umožněte integraci Intune s Jamf pro.
3. Nakonfigurujte podmíněný přístup v Jamf pro.

## <a name="create-an-application-in-azure-active-directory"></a>Vytvoření aplikace v Azure Active Directory

1. V [Azure Portal](https://portal.azure.com)klikněte na**registrace aplikací** **Azure Active Directory** >  a pak vyberte **Nová registrace**. 

2. Na stránce **zaregistrovat aplikaci** zadejte následující podrobnosti:
   - V části **název** zadejte smysluplný název aplikace, například **Jamf podmíněný přístup**.
   - V části **podporované typy účtů** vyberte **účty v libovolném organizačním adresáři**. 
   - Pro **identifikátor URI přesměrování**ponechte výchozí nastavení web a potom zadejte adresu URL pro instanci Jamf pro.  

3. Vyberte **Registrovat** , chcete-li vytvořit aplikaci a otevřít stránku **Přehled** pro novou aplikaci.  

4. Na stránce **Přehled** aplikace ZKOPÍRUJTE hodnotu **ID aplikace (klienta)** a zaznamenejte ji pro pozdější použití. Tuto hodnotu budete potřebovat v pozdějších postupech.  

5. V části **Spravovat**vyberte **certifikáty & tajných** kódů. Vyberte tlačítko **nový tajný klíč klienta** . Zadejte hodnotu v **popisu**, vyberte možnost pro **vypršení platnosti** a zvolte **Přidat**.

   > [!IMPORTANT]  
   > Než tuto stránku opustíte, zkopírujte hodnotu pro tajný klíč klienta a zaznamenejte ho pro pozdější použití. Tuto hodnotu budete potřebovat v pozdějších postupech. Tato hodnota není znovu k dispozici, aniž by bylo nutné znovu vytvořit registraci aplikace.  

6. V části **Spravovat**vyberte **oprávnění rozhraní API** . Vyberte existující oprávnění a pak vyberte **Odebrat oprávnění** k odstranění těchto oprávnění. Odebrání všech stávajících oprávnění je nezbytné, protože přidáte nové oprávnění a aplikace funguje pouze v případě, že má jedno požadované oprávnění.  

7. Pokud chcete přiřadit nové oprávnění, vyberte **Přidat oprávnění**. Na stránce **požádat o oprávnění API** vyberte **Intune**a pak vyberte **oprávnění aplikace**. Zaškrtněte políčko pouze pro **update_device_attributes**.  

   Pokud chcete tuto konfiguraci uložit, vyberte **Přidat oprávnění** .  

8. Na stránce **oprávnění rozhraní API** vyberte **udělit souhlas správce Microsoftu**a pak vyberte **Ano**.  

   Proces registrace aplikace v Azure AD je dokončený.


    > [!NOTE]
    > Pokud platnost tajného klíče klienta vyprší, musíte v Azure vytvořit nový tajný klíč klienta a potom aktualizovat data podmíněného přístupu v Jamf pro. Azure umožňuje mít aktivní jak starý tajný klíč, tak i nový klíč, aby nedošlo k přerušení služeb.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Povolení integrace Intune s Jamf Pro

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)a vyhledejte **Microsoft Intune** **dodržování předpisů zařízením** >   > **Správa partnerského zařízení**.

2. Povolte konektor dodržování předpisů pro Jamf vložením ID aplikace, které jste uložili během předchozího postupu do pole **ID aplikace v Jamf Azure Active Directory** .

3. Vyberte **Uložit**.

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Konfigurace integrace Microsoft Intune v Jamf Pro

1. V Jamf Pro přejděte do části **Global Management (Globální správa)**  > **Conditional Access (Podmíněný přístup)** . Klikněte na tlačítko **Upravit** na kartě **integrace MacOS Intune** .

2. Zaškrtněte políčko **Povolit integraci Intune pro MacOS**.

3. Zadejte požadované informace o vašem tenantovi Azure, včetně **umístění**, **názvu domény**, **ID aplikace**a hodnoty *tajného klíče klienta* , který jste uložili při vytváření aplikace ve službě Azure AD.  

4. Vyberte **Uložit**. Jamf pro testuje vaše nastavení a ověří úspěch.

## <a name="set-up-compliance-policies-and-register-devices"></a>Nastavení zásad dodržování předpisů a registrace zařízení

Po nakonfigurování integrace mezi Intune a Jamf je potřeba [použít zásady dodržování předpisů pro zařízení spravovaná Jamf](conditional-access-assign-jamf.md).

## <a name="disconnect-jamf-pro-and-intune"></a>Odpojení služby Jamf pro a Intune 

Pokud už nepoužíváte Jamf pro ke správě počítačů Mac ve vaší organizaci a chcete, aby se uživatelé spravovali přes Intune, musíte připojení mezi Jamf pro a Intune odebrat. Odeberte připojení pomocí konzoly Jamf pro. 

1. V Jamf pro přejděte na **Global Management** > **podmíněný přístup**. Na kartě **integrace MacOS Intune** vyberte **Upravit**.
2. Zrušte zaškrtnutí políčka **Povolit integraci Intune pro MacOS** .
3. Vyberte **Uložit**. Jamf pro pošle vaši konfiguraci do Intune a integrace se ukončí.
4. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973). Přejít na **Microsoft Intune** **dodržování předpisů zařízením** >   > **Správa partnerského zařízení** , aby se ověřilo, že je stav nyní **ukončen**. 

   > [!NOTE]
   > Zařízení Mac vaší organizace budou odebrána v den (3 měsíce), který je zobrazený ve vaší konzole. 

## <a name="next-steps"></a>Další kroky

- [Použití zásad dodržování předpisů pro zařízení spravovaná aplikací Jamf](conditional-access-assign-jamf.md)
- [Data Jamf odesílají do Intune.](data-jamf-sends-to-intune.md)
