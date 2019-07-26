---
title: Nastavení sítě VPN pro jednotlivé aplikace pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: Prohlédněte si předpoklady, vytvořte skupinu pro uživatele sítě VPN (Virtual Private Network), přidejte profil certifikátu SCEP, nakonfigurujte profil sítě VPN pro jednotlivé aplikace a přiřaďte v Microsoft Intune některé aplikace k profilu sítě VPN na zařízeních s iOSem. Součástí článku je také postup pro ověření připojení VPN na zařízení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/04/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: b3c2b5bc0091544136848bf92fc6cef7524ffa54
ms.sourcegitcommit: bd09decb754a832574d7f7375bad0186a22a15ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/19/2019
ms.locfileid: "68354506"
---
# <a name="set-up-per-app-virtual-private-network-vpn-for-ios-devices-in-intune"></a>Nastavení virtuální privátní sítě (VPN) pro aplikaci pro zařízení s iOS v Intune

V Microsoft Intune můžete vytvářet a používat virtuální privátní sítě (VPN) přiřazené k aplikaci. Tato funkce se nazývá VPN pro aplikaci. Zvolíte spravované aplikace, které můžou používat vaši síť VPN na zařízeních spravovaných přes Intune. Při použití sítí VPN pro jednotlivé aplikace se koncoví uživatelé automaticky připojují přes síť VPN a získají přístup k prostředkům organizace, jako jsou například dokumenty.

Tato funkce platí pro:

- iOS 9 a novější

Zkontrolujte si dokumentaci poskytovatele sítě VPN a zjistěte, jestli vaše síť VPN podporuje síť VPN pro jednotlivé aplikace.

V tomto článku se dozvíte, jak vytvořit profil sítě VPN pro jednotlivé aplikace a přiřadit tento profil k vašim aplikacím. Pomocí těchto kroků můžete pro koncové uživatele vytvořit bezproblémové prostředí sítě VPN pro jednotlivé aplikace. U většiny sítí VPN, které podporují síť VPN pro jednotlivé aplikace, uživatel otevře aplikaci a automaticky se připojí k síti VPN.

Některé sítě VPN umožňují ověřování uživatelského jména a hesla u sítě VPN pro jednotlivé aplikace. To znamená, že uživatelé musí zadat uživatelské jméno a heslo pro připojení k síti VPN.

## <a name="per-app-vpn-with-zscaler"></a>SÍŤ VPN pro jednotlivé aplikace s Zscaler

Zscaler Private Access (ZPA) se integruje s Azure Active Directory (Azure AD) pro ověřování. Pokud používáte ZPA, nepotřebujete profily [](#create-a-trusted-certificate-profile) [certifikátů SCEP nebo PKCS](#create-a-scep-or-pkcs-certificate-profile) (popsané v tomto článku). Pokud máte nastaven profil sítě VPN pro jednotlivé aplikace pro Zscaler, otevření jedné z přidružených aplikací se automaticky nepřipojí k ZPA. Místo toho se uživatel musí nejdřív přihlašovat do aplikace Zscaler. Vzdálený přístup je pak omezen na přidružené aplikace.

## <a name="prerequisites-for-per-app-vpn"></a>Předpoklady pro síť VPN pro jednotlivé aplikace

> [!IMPORTANT]
> Dodavatel VPN může mít další požadavky na síť VPN pro jednotlivé aplikace, jako je třeba konkrétní hardware nebo licencování. Nezapomeňte zkontrolovat jeho dokumentaci a splnit tyto požadavky dříve, než VPN pro aplikaci v Intune nastavíte.

Server VPN prokáže svoji identitu tak, že předloží certifikát, který musí zařízení bez vyzvání přijmout. Chcete-li potvrdit automatické schválení certifikátu, vytvořte profil důvěryhodného certifikátu, který obsahuje kořenový certifikát serveru VPN vystavený certifikační autoritou (CA). 

### <a name="export-the-certificate-and-add-the-ca"></a>Exportujte certifikát a přidejte certifikační autoritu.

1. Na serveru VPN otevřete konzolu pro správu.
2. Ověřte, že server VPN používá ověřování pomocí certifikátů. 
3. Vyexportujte soubor s důvěryhodným kořenovým certifikátem. Soubor má příponu .cer a přidáte ho při vytváření profilu důvěryhodného certifikátu.
4. Přidejte název certifikační autority, která vystavila certifikát pro ověřování vůči serveru VPN.

    Pokud certifikační autorita, kterou zařízení prezentuje, odpovídá certifikační autoritě v seznamu důvěryhodných certifikačních autorit na serveru VPN, pak server VPN úspěšně ověří zařízení.

## <a name="create-a-group-for-your-vpn-users"></a>Vytvoření skupiny pro uživatele sítě VPN

Vytvořte nebo vyberte existující skupinu v Azure Active Directory (Azure AD) pro uživatele nebo zařízení, která používají síť VPN pro jednotlivé aplikace. Pokud chcete vytvořit novou skupinu, přečtěte si téma [Přidání skupin pro uspořádání uživatelů a zařízení](groups-add.md).

## <a name="create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu

Kořenový certifikát serveru VPN vystavený certifikační autoritou naimportujte do profilu vytvořeného v Intune. Profil důvěryhodného certifikátu vydá pokyn zařízení s iOSem, aby automaticky důvěřovalo certifikační autoritě, kterou uvádí server VPN.

1. Přihlaste [](https://go.microsoft.com/fwlink/?linkid=2090973)se k Intune.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:
    - **Název**
    - **Popis**
    - **Platforma**: Vyberte **iOS**.
    - **Typ profilu**: Vyberte **důvěryhodný certifikát**.
4. Vyberte ikonu složky a přejděte k certifikátu sítě VPN (soubor. cer), který jste exportovali z konzoly pro správu sítě VPN. 
5. Vyberte **OK** > **vytvořit**.

    ![Vytvoření profilu důvěryhodného certifikátu pro zařízení s iOS v Microsoft Intune](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-or-pkcs-certificate-profile"></a>Vytvoření profilu certifikátu SCEP nebo PKCS

Profil důvěryhodného kořenového certifikátu umožňuje zařízení automaticky důvěřovat serveru VPN. Certifikát SCEP nebo PKCS poskytuje přihlašovací údaje od klienta VPN iOS k serveru VPN. Certifikát umožňuje, aby se zařízení tiše ověřovalo bez výzvy k zadání uživatelského jména a hesla. 

Pokud chcete nakonfigurovat a přiřadit certifikát pro ověřování klientů, přečtěte si jeden z následujících článků:

- [Konfigurace a správa certifikátů SCEP pomocí Intune](certificates-scep-configure.md)
- [Konfigurace a správa certifikátů PKCS pomocí Intune](certficates-pfx-configure.md)

Nezapomeňte nakonfigurovat certifikát pro ověřování klientů. Tuto možnost můžete nastavit přímo v profilech certifikátů SCEP (seznam**použití rozšířeného klíče** > **ověřování klientů**). V případě PKCS nastavte ověřování klientů v šabloně certifikátu v certifikační autoritě (CA).

![Vytvoření profilu certifikátu SCEP v Microsoft Intune, včetně formátu názvu subjektu, použití klíče, rozšířeného použití klíče a dalších](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Vytvoření profilu sítě VPN pro jednotlivé aplikace

Profil VPN obsahuje certifikát SCEP nebo PKCS s přihlašovacími údaji klienta, informace o připojení k síti VPN a příznak sítě VPN pro jednotlivé aplikace, pomocí kterých aplikace pro iOS povoluje funkci VPN pro jednotlivé aplikace.

1. V **Intune**vyberte **Konfigurace** > zařízení**profily** > **vytvořit profil**. 
2. Zadejte tyto vlastnosti: 
    - **Název**
    - **Popis**
    - **Platforma**: Vyberte **iOS**.
    - **Typ profilu**: Vyberte **VPN**.
3. V **typu připojení**vyberte klientská aplikace VPN.
4. Vyberte **Základní síť VPN**. [nastavení sítě VPN pro iOS](vpn-settings-ios.md) uvádí a popisuje všechna nastavení. Při použití sítě VPN pro jednotlivé aplikace se ujistěte, že jste nastavili následující vlastnosti, jak je uvedeno níže: 
    
    - **Metoda ověřování**: Vyberte **certifikáty**. 
    - **Ověřovací certifikát**: Vyberte existující certifikát SCEP nebo PKCS > **OK**.      
    - **Dělené tunelové propojení**: Vyberte možnost **Zakázat** , pokud chcete vynutit, aby veškerý provoz používal tunel VPN v případě, že je připojení VPN aktivní. 

      ![V profilu sítě VPN pro jednotlivé aplikace zadejte připojení, IP adresu nebo plně kvalifikovaný název domény, metodu ověřování a rozdělení s v Microsoft Intune](./media/vpn-per-app-create-vpn-profile.png)

    Informace o dalších nastaveních najdete v tématu [nastavení sítě VPN pro iOS](vpn-settings-ios.md).

5. Vyberte **Automatický typ sítě** > VPN**Automatické** > sítě VPN**pro jednotlivé aplikace** .

    ![V Intune nastavte pro zařízení s iOS automatickou síť VPN na síť VPN pro jednotlivé aplikace.](./media/vpn-per-app-automatic.png)

6. Vyberte **OK** > okvytvořit > .

## <a name="associate-an-app-with-the-vpn-profile"></a>Přidružení aplikace k profilu sítě VPN

Po přidání profilu sítě VPN přidružte aplikaci a skupinu služby Azure AD k profilu.

1. V **Intune** vyberte **Klientské aplikace** > **Aplikace**.
2. Vyberte aplikaci ze seznamu > **přiřazení** > **Přidat skupinu**.
3. V **typu přiřazení**vyberte možnost **požadováno** nebo **k dispozici pro zaregistrovaná zařízení**.
4. Vyberte **zahrnuté skupiny** > **Vybrat skupiny, které se mají zahrnout** > vyberte skupinu [, kterou jste vytvořili](#create-a-group-for-your-vpn-users) (v tomto článku) > **Vybrat**.
5. V části **sítě VPN**vyberte profil sítě VPN pro jednotlivé aplikace [, který jste vytvořili](#create-a-per-app-vpn-profile) (v tomto článku).

    ![Přiřaďte aplikaci k profilu sítě VPN pro jednotlivé aplikace v Microsoft Intune](./media/vpn-per-app-app-to-vpn.png)

6. Vyberte **OK** > **Uložit**.

Přidružení mezi aplikací a profilem se při dalším vrácení se změnami zařízení odebere, pokud existují všechny následující podmínky:

- Aplikace byla cílem záměru požadované instalace.
- Profil a aplikace cílí na stejnou skupinu.
- Odeberete konfiguraci sítě VPN pro jednotlivé aplikace z přiřazení aplikace.

Přidružení mezi aplikací a profilem přetrvá, dokud uživatel nepožaduje přeinstalaci z Portál společnosti, pokud existují všechny následující podmínky:

- Aplikace byla cílem záměru dostupné instalace.
- Profil a aplikace cílí na stejnou skupinu.
- Koncový uživatel požádal o instalaci aplikace z Portál společnosti, což vede k tomu, že se na zařízení nainstalují aplikace a profil.
- Z přiřazené aplikace jste odebrali konfiguraci sítě VPN pro aplikaci nebo jste ji změnili.

## <a name="verify-the-connection-on-the-ios-device"></a>Ověření připojení na zařízení s iOSem

Po nastavení sítě VPN pro jednotlivé aplikace a jejím přidružení k aplikaci ověřte, že připojení ze zařízení funguje.

### <a name="before-you-attempt-to-connect"></a>Než se pokusíte připojit

- Ujistěte se, že jste nasadili všechny výše uvedené zásady do stejné skupiny. V opačném případě prostředí VPN pro jednotlivé aplikace nebude fungovat.
- Pokud používáte aplikaci VPN Pulse Secure nebo vlastní klientská aplikace VPN, můžete použít tunelování vrstvy aplikace nebo paketů. U tunelování v aplikační vrstvě nastavte hodnotu **ProviderType** na **app-proxy**, u tunelování na úrovni paketů na **packet-tunnel**. Zkontrolujte dokumentaci poskytovatele sítě VPN a ujistěte se, že používáte správnou hodnotu.

### <a name="connect-using-the-per-app-vpn"></a>Připojení pomocí sítě VPN pro jednotlivé aplikace

Ověřte funkčnost bezdotykového prostředí – připojte se bez výběru sítě VPN nebo zadání svých přihlašovacích údajů. Bezdotykové prostředí znamená toto:

- Zařízení vás nevyzve k důvěřování serveru VPN. To znamená, že uživatel se nezobrazí v dialogovém okně **dynamického vztahu důvěryhodnosti** .
- Uživatel není muset zadávat přihlašovací údaje.
- Zařízení uživatele je připojené k síti VPN, když uživatel otevře jednu z přidružených aplikací.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Další kroky

- Na nastavení iOSu se můžete podívat v článku [Nastavení sítě VPN pro zařízení s iOSem v Microsoft Intune](vpn-settings-ios.md).
- Další informace o nastavení sítě VPN a Intune najdete v tématu [Konfigurace nastavení sítě VPN v Microsoft Intune](vpn-settings-configure.md).
