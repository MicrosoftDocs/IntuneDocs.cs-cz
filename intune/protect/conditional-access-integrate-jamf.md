---
title: Integrace Jamf Pro s Microsoft Intune pro dodržování předpisů
titleSuffix: Microsoft Intune
description: Pomocí Microsoft Intune zásad dodržování předpisů s Azure Active Directory podmíněný přístup můžete zajistit integraci a zabezpečení zařízení spravovaných pomocí Jamf.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/18/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 59edb9956ee117e0dbdb9d90a4fd4ef313fd5c66
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390466"
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a>Integrace Jamf Pro s Intune pro dodržování předpisů

Když vaše organizace používá [Jamf pro](https://www.jamf.com) ke správě zařízení MacOS, můžete použít Microsoft Intune zásady dodržování předpisů s podmíněným přístupem Azure Active Directory (Azure AD), abyste zajistili, že zařízení ve vaší organizaci dodržují předpisy, aby mohli získat přístup k prostředkům společnosti. Tento článek vám pomůže nakonfigurovat integraci Jamf s Intune.

Když se Jamf pro integruje s Intune, můžete synchronizovat data inventáře ze zařízení macOS s Intune prostřednictvím služby Azure AD. Modul dodržování předpisů v Intune pak analyzuje data inventáře a generuje sestavu. Analýza Intune je kombinována s inteligentními informacemi o identitě Azure AD uživatele zařízení, aby bylo možné řídit vynucování prostřednictvím podmíněného přístupu. Zařízení, která jsou kompatibilní se zásadami podmíněného přístupu, můžou získat přístup k chráněným prostředkům společnosti.

Až nakonfigurujete integraci, [nakonfigurujte Jamf a Intune tak, aby vynutila dodržování předpisů s podmíněným přístupem](conditional-access-assign-jamf.md) na zařízeních spravovaných pomocí Jamf.

## <a name="prerequisites"></a>Předpoklady

### <a name="products-and-services"></a>Produkty a služby

Abyste mohli nakonfigurovat podmíněný přístup pomocí Jamf pro, potřebujete následující:

- Jamf Pro 10.1.0 nebo novější
- [Aplikaci Portál společnosti pro macOS](https://aka.ms/macoscompanyportal)
- zařízení macOS s operačním systémem X 10,12 Yosemite nebo novějším

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

### <a name="create-an-application-in-azure-active-directory"></a>Vytvoření aplikace v Azure Active Directory

1. V [Azure Portal](https://portal.azure.com)přejít na **Azure Active Directory** > **Registrace aplikací**a vyberte **Nová registrace**.

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

7. Pokud chcete přiřadit nové oprávnění, vyberte **Přidat oprávnění**. Na stránce **požádat o oprávnění API** vyberte **Intune**a pak vyberte **oprávnění aplikace**. Zaškrtněte políčko pouze u **update_device_attributes**.

   Pokud chcete tuto konfiguraci uložit, vyberte **Přidat oprávnění** .

8. Na stránce **oprávnění rozhraní API** vyberte **udělit souhlas správce pro _\<> tenanta_** a pak vyberte **Ano**.  Po úspěšném zaregistrování aplikace by se oprávnění API měla zobrazit takto:

   ![Úspěšná oprávnění](./media/conditional-access-integrate-jamf/sucessfull-app-registration.png)

   Proces registrace aplikace v Azure AD je dokončený.

    > [!NOTE]
    > Pokud platnost tajného klíče klienta vyprší, musíte v Azure vytvořit nový tajný klíč klienta a potom aktualizovat data podmíněného přístupu v Jamf pro. Azure umožňuje mít aktivní jak starý tajný klíč, tak i nový klíč, aby nedošlo k přerušení služeb.

### <a name="enable-intune-to-integrate-with-jamf-pro"></a>Povolení integrace Intune s Jamf Pro

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte možnost **Správa tenanta** > **konektory a tokeny** > **správu partnerských zařízení**.

3. Povolte *konektor dodržování předpisů pro Jamf* tak, že vložíte ID aplikace, které jste uložili během předchozího postupu, do pole **zadejte ID aplikace Azure Active Directory pro pole Jamf** .

4. Vyberte **Uložit**.

### <a name="configure-microsoft-intune-integration-in-jamf-pro"></a>Konfigurace integrace Microsoft Intune v Jamf Pro

1. Aktivujte připojení v konzole Jamf pro:

   1. Otevřete konzolu Jamf pro a přejděte ke **globální správě** > **podmíněný přístup**. Klikněte na tlačítko **Upravit** na kartě **integrace MacOS Intune** .
   2. Zaškrtněte políčko **Povolit integraci Intune pro MacOS**.
   3. Zadejte požadované informace o vašem tenantovi Azure, včetně **umístění**, **názvu domény**, **ID aplikace**a hodnoty *tajného klíče klienta* , který jste uložili při vytváření aplikace ve službě Azure AD.
   4. Vyberte **Uložit**. Jamf pro testuje vaše nastavení a ověří úspěch.

   Vraťte se na stránku **správy partnerského zařízení** v Intune a dokončete konfiguraci.

2. V Intune přejdete na stránku **Správa partnerského zařízení** . V části **Nastavení konektoru** Konfigurujte skupiny pro přiřazení:

   - Vyberte možnost **Zahrnout** a zadejte, které skupiny uživatelů chcete cílit na MacOS registraci pomocí Jamf.
   - Pokud chcete vybrat skupiny uživatelů, které se nezaregistrují do Jamf, použijte možnost **vyloučit** a místo toho si zaregistrujete svoje počítače Mac přímo do Intune.

   *Vyloučení* přepsání *zahrnuje*, což znamená, že všechna zařízení, která jsou v obou skupinách, jsou vyloučená z Jamf a směrována k registraci v Intune.

   >[!NOTE]
   > Tato metoda zahrnutí a vyloučení skupin uživatelů má vliv na možnosti registrace uživatele. Každý uživatel s počítačem Mac, který je už zaregistrovaný v Jamf nebo Intune a který je pak určený k registraci v jiné MDM, musí zrušit registraci zařízení a pak ho znovu zaregistrovat s novým MDM, než bude zařízení správně fungovat.

3. Vyberte možnost **vyhodnotit** a určete, kolik zařízení bude zaregistrováno v Jamf na základě konfigurací skupiny.

4. Až budete připraveni použít konfiguraci, vyberte **Uložit** .

5. Abyste mohli pokračovat, budete muset použít [Jamf k nasazení portál společnosti pro Mac](conditional-access-assign-jamf.md#deploy-the-company-portal-app-for-macos-in-jamf-pro) , aby si mohli uživatelé zaregistrovat svoje zařízení do Intune.

## <a name="set-up-compliance-policies-and-register-devices"></a>Nastavení zásad dodržování předpisů a registrace zařízení

Po nakonfigurování integrace mezi Intune a Jamf je potřeba [použít zásady dodržování předpisů pro zařízení spravovaná Jamf](conditional-access-assign-jamf.md).

## <a name="disconnect-jamf-pro-and-intune"></a>Odpojení služby Jamf pro a Intune

Pokud už nepoužíváte Jamf pro ke správě počítačů Mac ve vaší organizaci a chcete, aby se uživatelé spravovali přes Intune, musíte připojení mezi Jamf pro a Intune odebrat. Odeberte připojení pomocí konzoly Jamf pro.

1. V Jamf pro přejděte na **Globální správa** > **podmíněný přístup**. Na kartě **integrace MacOS Intune** vyberte **Upravit**.

2. Zrušte zaškrtnutí políčka **Povolit integraci Intune pro MacOS** .

3. Vyberte **Uložit**. Jamf pro pošle vaši konfiguraci do Intune a integrace se ukončí.

4. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

5. Vyberte možnost **Správa tenanta** > **konektory a tokeny** > **správu partnerských zařízení** a ověřte, zda je stav nyní **ukončen**.

   > [!NOTE]
   > Zařízení Mac vaší organizace budou odebrána v den (3 měsíce), který je zobrazený ve vaší konzole.

## <a name="next-steps"></a>Další kroky

- [Použití zásad dodržování předpisů pro zařízení spravovaná aplikací Jamf](conditional-access-assign-jamf.md)
- [Data Jamf odesílají do Intune.](data-jamf-sends-to-intune.md)
