---
title: Integrace Jamf pro s Microsoft Intune pro dodržování předpisů
titleSuffix: Microsoft Intune
description: Pomocí Microsoft Intune zásad dodržování předpisů s Azure Active Directory podmíněný přístup můžete zajistit integraci a zabezpečení zařízení spravovaných pomocí Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 09/20/2019
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
ms.openlocfilehash: 09566e314f801c0de3f371384126cf672403b6a3
ms.sourcegitcommit: dd6755383ba89824d1cc128698a65fde6bb2de55
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72306654"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrace Jamf pro s Intune pro dodržování předpisů

Platí pro: Intune v Azure Portal

Když vaše organizace používá [Jamf pro](https://www.jamf.com) ke správě zařízení MacOS, můžete použít Microsoft Intune zásady dodržování předpisů s podmíněným přístupem Azure Active Directory (Azure AD), abyste zajistili, že zařízení ve vaší organizaci vyhovují předpisům, ke kterým budou mít přístup. prostředky společnosti. Tento článek vám pomůže nakonfigurovat integraci Jamf s Intune.

Když se Jamf pro integruje s Intune, můžete synchronizovat data inventáře ze zařízení macOS s Intune prostřednictvím služby Azure AD. Modul dodržování předpisů v Intune pak analyzuje data inventáře a generuje sestavu. Analýza Intune je kombinována s inteligentními informacemi o identitě Azure AD uživatele zařízení, aby bylo možné řídit vynucování prostřednictvím podmíněného přístupu. Zařízení, která jsou kompatibilní se zásadami podmíněného přístupu, můžou získat přístup k chráněným prostředkům společnosti.

Až nakonfigurujete integraci, [nakonfigurujte Jamf a Intune tak, aby vynutila dodržování předpisů s podmíněným přístupem](conditional-access-assign-jamf.md) na zařízeních spravovaných pomocí Jamf.  


## <a name="prerequisites"></a>Předpoklady

### <a name="products-and-services"></a>Produkty a služby
Abyste mohli nakonfigurovat podmíněný přístup pomocí Jamf pro, potřebujete následující:

- Jamf pro 10.1.0 nebo novější
- [Aplikace Portál společnosti pro macOS](https://aka.ms/macoscompanyportal)
- zařízení macOS s operačním systémem X 10,11 Yosemite nebo novějším

### <a name="network-ports"></a>Síťové porty
<!-- source: https://support.microsoft.com/en-us/help/4519171/troubleshoot-problems-when-integrating-jamf-with-microsoft-intune -->
Následující porty by měly být přístupné pro Jamf a Intune pro správné integraci: 
- **Intune**: port 443
- **Apple**: porty 2195, 2196 a 5223 (nabízená oznámení do Intune)
- **Jamf**: porty 80 a 5223

Pokud chcete povolit službě APN správné fungování služby APNS v síti, musíte taky povolit odchozí připojení k a přesměrování z:
- blok Apple 17.0.0.0/8 přes porty TCP 5223 a 443 ze všech klientských sítí.   
- porty 2195 a 2196 ze serverů Jamf pro.  

Další informace o těchto portech najdete v následujících článcích:  
- [Požadavky na konfiguraci sítě a šířku pásma Intune](../fundamentals/network-bandwidth-use.md).
- [Síťové porty používané službou Jamf pro](https://www.jamf.com/jamf-nation/articles/34/network-ports-used-by-jamf-pro) v jamf.com.
- [Porty TCP a UDP používané softwarovými produkty společnosti Apple](https://support.apple.com/HT202944) v support.Apple.com


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

8. Na stránce **oprávnění rozhraní API** vyberte * * udělit souhlas správce pro * \<your tenant > * * * a pak vyberte **Ano**.  Po úspěšném zaregistrování aplikace by se oprávnění API měla zobrazit takto: ![Successful oprávnění @ no__t-1.

   Proces registrace aplikace v Azure AD je dokončený.


    > [!NOTE]
    > Pokud platnost tajného klíče klienta vyprší, musíte v Azure vytvořit nový tajný klíč klienta a potom aktualizovat data podmíněného přístupu v Jamf pro. Azure umožňuje mít aktivní jak starý tajný klíč, tak i nový klíč, aby nedošlo k přerušení služeb.

## <a name="enable-intune-to-integrate-with-jamf-pro"></a>Povolení integrace Intune s Jamf pro

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973)a vyhledejte **Microsoft Intune** **dodržování předpisů zařízením** >   > **Správa partnerského zařízení**.

2. Povolte konektor dodržování předpisů pro Jamf vložením ID aplikace, které jste uložili během předchozího postupu do pole **ID aplikace v Jamf Azure Active Directory** .

3. Vyberte **Save** (Uložit).

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Konfigurace integrace Microsoft Intune v Jamf pro

1. V Jamf pro přejděte do **globálního řízení správa** > **podmíněný přístup**. Klikněte na tlačítko **Upravit** na kartě **integrace MacOS Intune** .

2. Zaškrtněte políčko **Povolit integraci Intune pro MacOS**.

3. Zadejte požadované informace o vašem tenantovi Azure, včetně **umístění**, **názvu domény**, **ID aplikace**a hodnoty *tajného klíče klienta* , který jste uložili při vytváření aplikace ve službě Azure AD.  

4. Vyberte **Save** (Uložit). Jamf pro testuje vaše nastavení a ověří úspěch.

## <a name="set-up-compliance-policies-and-register-devices"></a>Nastavení zásad dodržování předpisů a registrace zařízení

Po nakonfigurování integrace mezi Intune a Jamf je potřeba [použít zásady dodržování předpisů pro zařízení spravovaná Jamf](conditional-access-assign-jamf.md).


## <a name="disconnect-jamf-pro-and-intune"></a>Odpojení služby Jamf pro a Intune 

Pokud už nepoužíváte Jamf pro ke správě počítačů Mac ve vaší organizaci a chcete, aby se uživatelé spravovali přes Intune, musíte připojení mezi Jamf pro a Intune odebrat. Odeberte připojení pomocí konzoly Jamf pro. 

1. V Jamf pro přejděte na **Global Management** > **podmíněný přístup**. Na kartě **integrace MacOS Intune** vyberte **Upravit**.
2. Zrušte zaškrtnutí políčka **Povolit integraci Intune pro MacOS** .
3. Vyberte **Save** (Uložit). Jamf pro pošle vaši konfiguraci do Intune a integrace se ukončí.
4. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973). Přejít na **Microsoft Intune** **dodržování předpisů zařízením** >   > **Správa partnerského zařízení** , aby se ověřilo, že je stav nyní **ukončen**. 

   > [!NOTE]
   > Zařízení Mac vaší organizace budou odebrána v den (3 měsíce), který je zobrazený ve vaší konzole. 

## <a name="next-steps"></a>Další kroky

- [Použití zásad dodržování předpisů pro zařízení spravovaná Jamf](conditional-access-assign-jamf.md)
- [Data Jamf odesílají do Intune.](data-jamf-sends-to-intune.md)
