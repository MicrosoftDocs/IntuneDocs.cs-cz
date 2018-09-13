---
title: Nastavení sítě VPN pro jednotlivé aplikace pro zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: Prohlédněte si předpoklady, vytvořte skupinu pro uživatele sítě VPN (Virtual Private Network), přidejte profil certifikátu SCEP, nakonfigurujte profil sítě VPN pro jednotlivé aplikace a přiřaďte v Microsoft Intune některé aplikace k profilu sítě VPN na zařízeních s iOSem. Součástí článku je také postup pro ověření připojení VPN na zařízení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 08/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7cf005b225dd11ca6b95dbed0a82330544575f92
ms.sourcegitcommit: 2d1e89fa5fa721e79648e41fde147a035e7b047d
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/31/2018
ms.locfileid: "43347470"
---
# <a name="set-up-per-app-virtual-private-network-vpn-in-intune-for-ios-devices"></a>Nastavení virtuální privátní sítě (VPN) pro jednotlivé aplikace v Intune pro zařízení s iOSem

Můžete určit, které spravované aplikace můžou používat vaši virtuální privátní síť (VPN) na zařízeních s iOSem spravovaných pomocí Intune. Když v Intune vytvoříte síť VPN pro jednotlivé aplikace, koncový uživatel se při přístupu k firemním dokumentům automaticky připojí přes vaši síť VPN.

Síť VPN pro jednotlivé aplikace je v tuto chvíli k dispozici pro následující poskytovatele:

 - Check Point Remote Access VPN
 - Cisco AnyConnect
 - Citrix
 - F5
 - Pulse Connect Secure
 - SonicWall
 - Palo Alto Networks GlobalProtect
 - Zscaler

## <a name="prerequisites-for-per-app-vpn"></a>Předpoklady pro síť VPN pro jednotlivé aplikace

> [!IMPORTANT]
> Dodavatel sítě VPN může mít jiné zvláštní požadavky na VPN pro aplikaci, například zvláštní hardware nebo licencování. Nezapomeňte zkontrolovat jeho dokumentaci a splnit tyto požadavky dříve, než VPN pro aplikaci v Intune nastavíte.

Server VPN prokáže svoji identitu tak, že předloží certifikát, který musí zařízení bez vyzvání přijmout. Zajištění automatického schválení certifikátu vyžaduje, abyste vytvořili profil důvěryhodného certifikátu, který obsahuje kořenový certifikát serveru VPN vystavený certifikační autoritou. 

Vyexportujte certifikát a přidejte certifikační autoritu.

1. Na serveru VPN otevřete konzolu pro správu.
2. Zkontrolujte, že server VPN používá ověřování prostřednictvím certifikátu. 
3. Vyexportujte soubor s důvěryhodným kořenovým certifikátem. Soubor má příponu .cer a přidáte ho při vytváření profilu důvěryhodného certifikátu.
4. Přidejte název certifikační autority, která vystavila certifikát pro ověřování vůči serveru VPN.
    Pokud certifikační autorita prezentovaná zařízením odpovídá jedné z certifikačních autorit uvedených na seznamu důvěryhodných certifikačních autorit na serveru VPN, server VPN úspěšně ověří zařízení.

## <a name="create-a-group-for-your-vpn-users"></a>Vytvoření skupiny pro uživatele sítě VPN

Vytvořte nebo zvolte existující skupinu ve službě Azure AD (Azure Active Directory), která bude obsahovat členy, kteří mají přístup k síti VPN pro jednotlivé aplikace.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Zvolte **Skupiny** a klikněte na **Nová skupina**.
3. Vyberte **typ skupiny**. 
3. Zadejte **název skupiny**. 
4. Zadejte **popis** skupiny. 
5. Jako **typ členství** vyberte **Přiřazeno**.
7. V podokně **Členové** vyhledejte uživatele sítě VPN podle jména nebo e-mailové adresy.
8. Po jednom vyberte uživatele a klikněte na **Vybrat**.
9. Klikněte na **Vytvořit**.

## <a name="create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu

Kořenový certifikát serveru VPN vystavený certifikační autoritou naimportujte do profilu vytvořeného v Intune. Profil důvěryhodného certifikátu vydá pokyn zařízení s iOSem, aby automaticky důvěřovalo certifikační autoritě, kterou uvádí server VPN.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Zvolte **Konfigurace zařízení** a potom klikněte na **Profily**.
3. Klikněte na **Vytvořit profil**. V okně **Vytvořit profil**:
    1. Zadejte **název**.
    2. Zadejte **popis**.
    3. Jako **platformu** vyberte **iOS**.
    4. Jako **typ profilu** vyberte **Důvěryhodný certifikát**.
4. Klikněte na ikonu složky a vyhledejte certifikát VPN (soubor s příponou .cer), který jste vyexportovali z konzoly pro správu sítě VPN. Klikněte na **OK**.
5. Klikněte na **Vytvořit**.

    ![Vytvoření profilu důvěryhodného certifikátu](./media/vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-certificate-profile"></a>Vytvoření profilu certifikátu SCEP

Profil důvěryhodného kořenového certifikátu umožňuje iOSu automaticky důvěřovat serveru VPN. Certifikát SCEP poskytuje serveru VPN přihlašovací údaje z klienta VPN iOSu. Certifikát umožňuje, aby se zařízení tiše ověřilo, aniž by po uživateli zařízení s iOSem požadovalo uživatelské jméno a heslo. 

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Zvolte **Konfigurace zařízení** a potom klikněte na **Profily**.
3. Klikněte na **Vytvořit profil**. V okně **Vytvořit profil**:
    1. Zadejte **název**.
    2. Zadejte **popis**.
    3. Jako **platformu** vyberte **iOS**.
    4. Jako **typ profilu** vyberte **Certifikát SCEP**.
4. Vyberte **Roky** a jako **Období platnosti certifikátu** zadejte `2`.
5. Jako **formát názvu subjektu** vyberte **Běžný název**.
6. Jako **alternativní název subjektu** vyberte **Hlavní název uživatele (UPN)**.
7. Vyberte **Digitální podpis** a u možnosti **Použití klíče** vyberte **Šifrování klíče**.
8. Jako **velikost klíče (bity)** vyberte **2048**.
9. Klikněte na Kořenový certifikát a vyberte certifikát SCEP. Klikněte na **OK**.
10. Do pole **Název** v části **Rozšířené použití klíče** zadejte `Client Authentication`.
11. Do pole **Identifikátor objektu** zadejte `1.3.6.1.5.5.7.3.2`.
12. Klikněte na **Přidat**.
13. Zadejte ***adresu URL serveru*** a klikněte na **Přidat**.
14. Klikněte na **OK**.
15. Klikněte na **Vytvořit**.

    ![Vytvoření profilu certifikátu SCEP](./media/vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Vytvoření profilu sítě VPN pro jednotlivé aplikace

Součástí profilu sítě VPN je certifikát SCEP, který obsahuje přihlašovací údaje klienta, informace o připojení k síti VPN a příznak sítě VPN pro jednotlivé aplikace a umožní aplikaci iOSu používat funkce sítě VPN pro jednotlivé aplikace.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Zvolte **Konfigurace zařízení** a potom klikněte na **Profily**.
3. Klikněte na **Vytvořit profil**. V okně **Vytvořit profil**:
    1. Zadejte **název**.
    2. Zadejte **popis**.
    3. Jako **platformu** vyberte **iOS**.
    4. Jako **typ profilu** vyberte **VPN**.
4. Vyberte **Základní síť VPN**. V okně **Základní síť VPN**:
    1. Zadejte **název připojení**.
    2. Zadejte **IP adresu nebo plně kvalifikovaný název domény**.
    3. Jako **metodu ověřování** vyberte **Certifikáty**.
    4. V části **Ověřovací certifikát** vyberte certifikát SCEP a klikněte na **OK**.
    5. Jako **typ připojení** vyberte svou síť VPN.
    6. V případě potřeby nakonfigurujte atributy sítě VPN.
    7. Zvolte, že se má **dělené tunelové propojení zakázat**.
5. Klikněte na **Automatické připojení VPN**. V okně **Automatické připojení VPN**:
    1. Jako **typ automatické sítě VPN** vyberte **VPN pro jednotlivé aplikace**.
    2. Zadejte adresu URL sítě VPN a klikněte na **Přidat**.
    3. Klikněte na **OK**.
6. Klikněte na **OK**.
7. Klikněte na **Vytvořit**.

    ![Vytvoření profilu sítě VPN pro jednotlivé aplikace](./media/vpn-per-app-create-vpn-profile.png)


## <a name="associate-an-app-with-the-vpn-profile"></a>Přidružení aplikace k profilu sítě VPN

Po přidání profilu sítě VPN přidružte aplikaci a skupinu služby Azure AD k profilu.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Klientské aplikace**.
4. Klikněte na **Aplikace**.
5. Ze seznamu aplikací vyberte požadovanou aplikaci.
6. Klikněte na **Přiřazení**.
7. Klikněte na **Přidat skupinu**.
8. Jako **Typ přiřazení** vyberte v podokně **Přidat skupinu** možnost **Povinné**.
9. Vyberte skupinu, kterou jste definovali dříve, a vyberte **Nastavit tuto aplikaci jako povinnou**.
10. V části **VPN** zadejte definici sítě VPN.
 
    > [!NOTE]  
    > Někdy se může stát, že načtení hodnoty definice sítě VPN trvá až jednu minutu. Než kliknete na **Uložit**, počkejte tři až pět minut.

11. Klikněte na **OK** a pak na **Uložit**.

    ![Přidružení aplikace k síti VPN](./media/vpn-per-app-app-to-vpn.png)

Přidružení aplikace k profilu se odebere během dalšího ohlášení zařízení, pokud jsou splněné následující podmínky:
- Aplikace byla cílem záměru požadované instalace.
- Profil a aplikace cílí na stejnou skupinu.
- Odeberete konfiguraci sítě VPN pro jednotlivé aplikace z přiřazení aplikace.

Přidružení aplikace k profilu bude dále existovat, dokud si koncový uživatel nevyžádá opětovnou instalaci z Portálu společnosti, pokud jsou splněné následující podmínky:
- Aplikace byla cílem záměru dostupné instalace.
- Profil a aplikace cílí na stejnou skupinu.
- Koncový uživatel si vyžádal instalaci aplikace z Portálu společnosti, což má za následek, že aplikace a profil se nainstalují na zařízení.
- Odeberete konfiguraci sítě VPN pro jednotlivé aplikace z přiřazení aplikace.

## <a name="verify-the-connection-on-the-ios-device"></a>Ověření připojení na zařízení s iOSem

Po nastavení sítě VPN pro jednotlivé aplikace a jejím přidružení k aplikaci ověřte, že připojení ze zařízení funguje.

### <a name="before-you-attempt-to-connect"></a>Než se pokusíte připojit

 - Ověřte, že používáte iOS 9 nebo novější.
 - Zkontrolujte, že *všechny* výše uvedené zásady nasazujete do stejné skupiny uživatelů. V opačném případě nebude síť VPN pro jednotlivé aplikace s největší pravděpodobností fungovat.  
 - Zkontrolujte, že máte nainstalovanou podporovanou aplikaci VPN od jiného výrobce. Podporují se tyto aplikace VPN:
    - Check Point Capsule Connect
    - Cisco AnyConnect
    - Citrix VPN
    - F5 Access
    - Pulse Secure
    - SonicWall Mobile Connect
    - Zscaler App

    > [!NOTE]
    > Pokud používáte aplikaci VPN Pulse Secure, můžete použít tunelování v aplikační vrstvě nebo na úrovni paketů. U tunelování v aplikační vrstvě nastavte hodnotu **ProviderType** na **app-proxy**, u tunelování na úrovni paketů na **packet-tunnel**.

### <a name="connect-using-the-per-app-vpn"></a>Připojení pomocí sítě VPN pro jednotlivé aplikace

Ověřte funkčnost bezdotykového prostředí – připojte se bez výběru sítě VPN nebo zadání svých přihlašovacích údajů. Bezdotykové prostředí znamená toto:

 - Zařízení vás nežádá, abyste vyjádřili důvěru serveru VPN. To znamená, že uvidíte **dynamické dialogové okno důvěryhodnosti**.
 - Nemusíte zadávat přihlašovací údaje.
 - Po klepnutí na tlačítko pro připojení se připojíte k síti VPN.

Ověřte připojení na zařízení s iOSem.

1. Klepněte na aplikaci VPN.
2. Klepněte na **Připojit**.  
Síť VPN se úspěšně připojí bez dalších výzev.

<!-- ## Troubleshooting the per-app VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Další kroky

- Na nastavení iOSu se můžete podívat v článku [Nastavení sítě VPN pro zařízení s iOSem v Microsoft Intune](vpn-settings-ios.md).
-  Další informace o nastavení sítě VPN a Intune najdete v článku [Konfigurace nastavení sítě VPN v Microsoft Intune](vpn-settings-configure.md).
