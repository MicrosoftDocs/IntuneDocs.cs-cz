---
title: Nastavení sítě VPN pro jednotlivé aplikace pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: Prohlédněte si předpoklady, vytvořte skupinu pro uživatele sítě VPN (Virtual Private Network), přidejte profil certifikátu SCEP, nakonfigurujte profil sítě VPN pro jednotlivé aplikace a přiřaďte v Microsoft Intune některé aplikace k profilu sítě VPN na zařízeních s iOSem. Součástí článku je také postup pro ověření připojení VPN na zařízení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/04/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: tycast
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: c0177e136d516ba1d4fe44c7301b1534ab1c5e6a
ms.sourcegitcommit: 12f8b7f0bca1baa2c1f68dd6af4f16a4814daa11
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/05/2019
ms.locfileid: "55737464"
---
# <a name="set-up-per-app-virtual-private-network-vpn-for-ios-devices-in-intune"></a>Nastavte si aplikaci virtuální privátní sítě (VPN) pro zařízení s Iosem v Intune

V Microsoft Intune můžete vytvořit a používat virtuální privátní sítě (VPN) přiřazené k aplikaci. Tato funkce se nazývá "VPN pro jednotlivé aplikace". Zvolíte spravovaných aplikací, které můžete použít svou síť VPN na zařízeních spravovaných přes Intune. Při použití sítě VPN pro aplikaci, koncoví uživatelé automaticky připojovat prostřednictvím VPN a získat přístup k prostředkům organizace, jako jsou například dokumenty.

Tato funkce platí pro:

- iOS 9 a novější

Pokud chcete zobrazit, pokud vaši síť VPN podporuje VPN pro jednotlivé aplikace v dokumentaci poskytovatele připojení VPN.

Tento článek ukazuje, jak vytvořit profil VPN pro aplikaci a přiřadit tento profil ke svým aplikacím. Pomocí těchto kroků můžete vytvořit prostředí bezproblémové aplikaci VPN pro koncové uživatele. Pro většinu sítí VPN, které podporují VPN pro jednotlivé aplikace uživatel otevře aplikaci a automaticky se připojí k síti VPN.

Některé sítě VPN umožňují ověřování uživatelského jména a hesla s VPN pro jednotlivé aplikace. To znamená, uživatelé musí zadat uživatelské jméno a heslo pro připojení k síti VPN.

## <a name="per-app-vpn-with-zscaler"></a>VPN pro jednotlivé aplikace se Zscalerem

Zscalerem privátní přístup (ZPA) se integruje s Azure Active Directory (Azure AD) pro ověřování. Při použití ZPA, není nutné [důvěryhodný certifikát](#create-a-trusted-certificate-profile) nebo [certifikátu SCEP nebo PKCS](#create-a-scep-or-pkcs-certificate-profile) profily (popsané v tomto článku). Pokud máte nastavení profilu sítě VPN pro aplikaci do služby Zscalerem, otevření jedné ze přidružené aplikace nebude automaticky připojit k ZPA. Místo toho uživatel musí pro přihlášení do aplikace Zscalerem nejprve. Potom vzdálený přístup je omezený na přidružené aplikace.

## <a name="prerequisites-for-per-app-vpn"></a>Předpoklady pro síť VPN pro jednotlivé aplikace

> [!IMPORTANT]
> Váš dodavatel sítě VPN může mít jiné požadavky na VPN pro jednotlivé aplikace, jako je například specifický hardware nebo licencování. Nezapomeňte zkontrolovat jeho dokumentaci a splnit tyto požadavky dříve, než VPN pro aplikaci v Intune nastavíte.

Server VPN prokáže svoji identitu tak, že předloží certifikát, který musí zařízení bez vyzvání přijmout. Potvrďte automatické schválení certifikátu vytvořte profil důvěryhodného certifikátu obsahující kořenový certifikát serveru VPN vystavený službou certifikační autority (CA). 

#### <a name="export-the-certificate-and-add-the-ca"></a>Vyexportujte certifikát a přidejte certifikační Autoritu

1. Na serveru VPN otevřete konzolu pro správu.
2. Potvrďte, že VPN server používá ověřování prostřednictvím certifikátu. 
3. Vyexportujte soubor s důvěryhodným kořenovým certifikátem. Soubor má příponu .cer a přidáte ho při vytváření profilu důvěryhodného certifikátu.
4. Přidejte název certifikační autority, která vystavila certifikát pro ověřování vůči serveru VPN.

    Pokud certifikační Autorita poskytlo odpovídá certifikační Autoritu v seznamu důvěryhodných certifikačních Autorit na serveru VPN, VPN server úspěšně ověří zařízení.

## <a name="create-a-group-for-your-vpn-users"></a>Vytvoření skupiny pro uživatele sítě VPN

Vytvořte nebo vyberte existující skupinu ve službě Azure Active Directory (Azure AD) pro uživatele nebo zařízení, která používají VPN pro jednotlivé aplikace. Pokud chcete vytvořit novou skupinu, naleznete v tématu [přidat skupiny pro uspořádání uživatelů a zařízení](groups-add.md).

## <a name="create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu

Kořenový certifikát serveru VPN vystavený certifikační autoritou naimportujte do profilu vytvořeného v Intune. Profil důvěryhodného certifikátu vydá pokyn zařízení s iOSem, aby automaticky důvěřovalo certifikační autoritě, kterou uvádí server VPN.

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte tyto vlastnosti:
    - **Název**
    - **Popis**
    - **Platforma**: Vyberte **iOS**.
    - **Typ profilu**: Vyberte **důvěryhodný certifikát**.
4. Vyberte ikonu složky a vyhledejte certifikát VPN (soubor .cer), který jste exportovali z konzoly pro správu vaší sítě VPN. 
5. Vyberte **OK** > **vytvořit**.

    ![Vytvoření profilu důvěryhodného certifikátu pro zařízení s Iosem v Microsoft Intune](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-or-pkcs-certificate-profile"></a>Vytvoření profilu certifikátu SCEP nebo PKCS

Profil důvěryhodného kořenového certifikátu umožňuje zařízení automaticky důvěřovat serveru VPN. Certifikát SCEP nebo PKCS poskytuje přihlašovací údaje z klienta VPN Iosu na serveru sítě VPN. Tento certifikát umožňuje zařízení tiše ověřilo, aniž by vás vyzve k zadání uživatelského jména a hesla. 

Ke konfiguraci a přiřazení certifikátu ověřování klienta, přečtěte si následující články:

- [Konfigurace a správa certifikátů SCEP pomocí Intune](certificates-scep-configure.md)
- [Konfigurace a správa certifikátů PKCS pomocí Intune](certficates-pfx-configure.md)

Je potřeba nakonfigurovat certifikát pro ověřování klientů. Tento parametr můžete nastavit přímo do profilů certifikátů SCEP (**rozšířené použití klíče** seznamu > **ověření klienta**). Pro PKCS nastavte ověření klienta v šabloně certifikátu v certifikační autority (CA).

![Vytvoření profilu certifikátu SCEP v Microsoft Intune, včetně formát názvu subjektu, použití klíče, rozšířeného použití klíče a další](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Vytvoření profilu sítě VPN pro jednotlivé aplikace

Certifikát SCEP nebo PKCS pomocí přihlašovacích údajů klienta, informace o připojení k síti VPN, obsahuje profil sítě VPN a příznak sítě VPN pro jednotlivé aplikace k povolení této funkce sítě VPN pro aplikaci používají, aplikace pro iOS.

1. V **Intune**vyberte **konfigurace zařízení** > **profily** > **vytvořit profil**. 
2. Zadejte tyto vlastnosti: 
    - **Název**
    - **Popis**
    - **Platforma**: Vyberte **iOS**.
    - **Typ profilu**: Vyberte **VPN**.
3. V **typ připojení**, vyberte svou aplikaci klienta VPN.
4. Vyberte **Základní síť VPN**. [nastavení sítě VPN iOS](vpn-settings-ios.md) uvádí a popisuje všechna nastavení. Když používáte VPN pro jednotlivé aplikace, nezapomeňte že nastavit následující vlastnosti, jak je uvedeno: 
    
    - **Metoda ověřování**: Vyberte **certifikáty**. 
    - **Certifikát pro ověřování**: Vyberte existující certifikát SCEP nebo PKCS > **OK**.      
    - **Dělené tunelové propojení**: Vyberte **zakázat** přinutit veškerý provoz směrem k pomocí tunelového připojení sítě VPN při připojení k síti VPN je aktivní. 

      ![V profilu sítě VPN pro aplikaci zadejte připojení, IP adresa nebo plně kvalifikovaný název domény, metodu ověřování a rozdělení tunning v Microsoft Intune](./media/vpn-per-app-create-vpn-profile.png)

    Informace o dalších nastaveních najdete v tématu [nastavení sítě VPN iOS](vpn-settings-ios.md).

5. Vyberte **automatické připojení VPN** > **typ Automatické sítě VPN** > **VPN pro jednotlivé aplikace**

    ![V Intune nastavte automatické připojení VPN na VPN pro jednotlivé aplikace na zařízeních s Iosem](./media/vpn-per-app-automatic.png)

6. Vyberte **OK** > **OK** > **vytvořit**.

## <a name="associate-an-app-with-the-vpn-profile"></a>Přidružení aplikace k profilu sítě VPN

Po přidání profilu sítě VPN přidružte aplikaci a skupinu služby Azure AD k profilu.

1. V **Intune** vyberte **Klientské aplikace** > **Aplikace**.
2. Vyberte aplikaci ze seznamu > **přiřazení** > **přidat skupinu**.
3. V **typ přiřazení**vyberte **vyžaduje** nebo **k dispozici pro zaregistrovaná zařízení**.
4. Vyberte **zahrnutých skupin** > **vybrat skupiny, které chcete zahrnout** > vyberte skupinu [jste vytvořili](#create-a-group-for-your-vpn-users) (v tomto článku) > **vyberte**.
5. V **VPN**, vyberte profil sítě VPN pro jednotlivé aplikace [jste vytvořili](#create-a-per-app-vpn-profile) (v tomto článku).

    ![Přiřazení aplikace k profilu sítě VPN pro jednotlivé aplikace v Microsoft Intune](./media/vpn-per-app-app-to-vpn.png)

6. Vyberte **OK** > **Uložit**.

Přidružení mezi aplikace a profil se odebere během další zařízení vrácení se změnami, pokud existují všechny následující podmínky:

- Aplikace byla cílem záměru požadované instalace.
- Profil a aplikace cílí na stejnou skupinu.
- Odeberete konfiguraci sítě VPN pro jednotlivé aplikace z přiřazení aplikace.

Přidružení mezi aplikace a profil potrvá, dokud uživatel požaduje přeinstalaci z portálu společnosti, pokud existují všechny následující podmínky:

- Aplikace byla cílem záměru dostupné instalace.
- Profil a aplikace cílí na stejnou skupinu.
- Koncový uživatel si vyžádal instalace aplikací z portálu společnosti, což vede k aplikaci a profilu se instalují na zařízení.
- Z přiřazené aplikace jste odebrali konfiguraci sítě VPN pro aplikaci nebo jste ji změnili.

## <a name="verify-the-connection-on-the-ios-device"></a>Ověření připojení na zařízení s iOSem

Po nastavení sítě VPN pro jednotlivé aplikace a jejím přidružení k aplikaci ověřte, že připojení ze zařízení funguje.

### <a name="before-you-attempt-to-connect"></a>Než se pokusíte připojit

 - Zajistěte, aby že všechny výše uvedené zásady nasazujete do stejné skupiny. V opačném případě nebude fungovat rozhraní VPN pro aplikaci.
 - Pokud používáte aplikaci Pulse Secure VPN nebo vlastní klientskou aplikaci VPN, můžete použít aplikační vrstvy nebo tunelové propojení vrstvě paketů. U tunelování v aplikační vrstvě nastavte hodnotu **ProviderType** na **app-proxy**, u tunelování na úrovni paketů na **packet-tunnel**. Abyste měli jistotu, že používáte správné hodnoty v dokumentaci poskytovatele připojení VPN.

### <a name="connect-using-the-per-app-vpn"></a>Připojení pomocí sítě VPN pro jednotlivé aplikace

Ověřte funkčnost bezdotykového prostředí – připojte se bez výběru sítě VPN nebo zadání svých přihlašovacích údajů. Bezdotykové prostředí znamená toto:

 - Zařízení není dotaz, aby důvěřoval serveru VPN. To znamená, nezobrazí uživateli **dynamického vztahu důvěryhodnosti** dialogové okno.
 - Uživatel nemá k zadání přihlašovacích údajů.
 - Zařízení uživatele je připojený k síti VPN, když uživatel otevře jeden přidružené aplikace.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Další postup

- Na nastavení iOSu se můžete podívat v článku [Nastavení sítě VPN pro zařízení s iOSem v Microsoft Intune](vpn-settings-ios.md).
- Další informace o nastavení sítě VPN a Intune najdete v tématu [nastavení sítě VPN v Microsoft Intune](vpn-settings-configure.md).
