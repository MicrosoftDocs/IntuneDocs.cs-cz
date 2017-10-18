---
title: "Nastavení sítě VPN pro jednotlivé aplikace v Microsoft Intune pro zařízení s iOSem"
titleSuffix: Intune on Azure
description: "Zadejte spravované aplikace, které mohou používat síť VPN na zařízeních s iOSem spravovaných pomocí Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/5/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c883ab2b96618502be20583908a4caa52ac5432b
ms.sourcegitcommit: 6004fe51e3cee6fb34514ed0d56e20587ecafeb4
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/17/2017
---
# <a name="set-up-per-app-vpn-in-microsoft-intune-for-ios-devices"></a>Nastavení sítě VPN pro jednotlivé aplikace v Microsoft Intune pro zařízení s iOSem

Můžete zadat spravované aplikace, které mohou používat vaši virtuální privátní síť (VPN) na zařízeních s iOSem spravovaných pomocí Intune. Když v Intune zadáte síť VPN pro jednotlivé aplikace, koncový uživatel se při přístupu k firemním dokumentům automaticky připojí přes vaši síť VPN.

## <a name="prerequisites-for-the-per-app-vpn"></a>Předpoklady pro síť VPN pro jednotlivé aplikace:

Server VPN prokáže svoji identitu tak, že předloží certifikát, který musí zařízení bez vyzvání přijmout. Zajištění automatického schválení certifikátu vyžaduje, abyste vytvořili profil důvěryhodného certifikátu, který obsahuje kořenový certifikát serveru VPN vystavený certifikační autoritou. 

Vyexportujte certifikát a přidejte certifikační autoritu.

1. Na serveru VPN otevřete konzolu pro správu.
2. Zkontrolujte, že server VPN používá ověřování prostřednictvím certifikátu. 
3. Vyexportujte soubor s důvěryhodným kořenovým certifikátem. Soubor má příponu .cer a přidáte ho při vytváření profilu důvěryhodného certifikátu.
4. Přidejte název certifikační autority, která vystavila certifikát pro ověřování vůči serveru VPN.
    Pokud certifikační autorita prezentovaná zařízením odpovídá jedné z certifikačních autorit uvedených na seznamu důvěryhodných certifikačních autorit na serveru VPN, server VPN úspěšně ověří zařízení.

## <a name="create-a--group-for-your-vpn-users"></a>Vytvoření skupiny pro uživatele sítě VPN

Vytvořte nebo zvolte existující skupinu ve službě Azure AD (Azure Active Directory), která bude obsahovat členy, kteří mají přístup k síti VPN pro jednotlivé aplikace.

1. Otevřete portál Azure Portal. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
2. Zvolte **Skupiny** a klikněte na **Nová skupina**.
3. Zadejte **název** skupiny. 
4. Zadejte **popis** skupiny. 
5. Jako **typ členství** vyberte **Přiřazeno**.
6. U možnosti **Povolit funkce Office** vyberte **Ne**.
7. V okně **Členové** vyhledejte uživatele sítě VPN podle jména nebo e-mailové adresy.
8. Po jednom vyberte uživatele a klikněte na **Vybrat**.
9. Klikněte na **Vytvořit**.

## <a name="create-a-trusted-certificate-profile"></a>Vytvoření profilu důvěryhodného certifikátu

Kořenový certifikát serveru VPN vystavený certifikační autoritou naimportujte do profilu vytvořeného v Intune. Profil důvěryhodného certifikátu vydá pokyn zařízení s iOSem, aby automaticky důvěřovalo certifikační autoritě, kterou uvádí server VPN.

1. Otevřete portál Azure Portal. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
2. Zvolte **Konfigurace zařízení** a potom klikněte na **Profily**.
3. Klikněte na **+ Vytvořit profil**. V okně **Vytvořit profil**:
    1. Zadejte **název**.
    2. Zadejte **popis**.
    3. Jako **platformu** vyberte **iOS**.
    4. Jako **typ profilu** vyberte **Důvěryhodný certifikát**.
4. Klikněte na ikonu složky a vyhledejte certifikát VPN (soubor s příponou .cer), který jste vyexportovali z konzoly pro správu sítě VPN. Klikněte na tlačítko OK.
5. Klikněte na **Vytvořit**.

    ![Vytvoření profilu důvěryhodného certifikátu](media\vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-certificate-profile"></a>Vytvoření profilu certifikátu SCEP

Profil důvěryhodného kořenového certifikátu umožňuje iOSu automaticky důvěřovat serveru VPN. Certifikát SCEP poskytuje serveru VPN přihlašovací údaje z klienta VPN iOSu. Certifikát umožňuje, aby se zařízení tiše ověřilo, aniž by po uživateli zařízení s iOSem požadovalo uživatelské jméno a heslo. 

1. Otevřete portál Azure Portal. Zvolte **Další služby** > **Monitorování + správa** > **Intune**. 
2. Zvolte **Konfigurace zařízení** a potom klikněte na **Profily**.
3. Klikněte na **+ Vytvořit profil**. V okně **Vytvořit profil**:
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

    ![Vytvoření profilu certifikátu SCEP](media\vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a>Vytvoření profilu sítě VPN pro jednotlivé aplikace

Součástí profilu sítě VPN je certifikát SCEP, který obsahuje přihlašovací údaje klienta, informace o připojení k síti VPN a příznak sítě VPN pro jednotlivé aplikace a umožní aplikaci iOSu používat funkce sítě VPN pro jednotlivé aplikace.

1. Otevřete portál Azure Portal. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
2. Zvolte **Konfigurace zařízení** a potom klikněte na **Profily**.
3. Klikněte na **+ Vytvořit profil**. V okně **Vytvořit profil**:
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

    ![Vytvoření profilu sítě VPN pro jednotlivé aplikace](media\vpn-per-app-create-vpn-profile.png)


## <a name="associate-an-app-with-the-vpn-profile"></a>Přidružení aplikace k profilu sítě VPN

Po přidání profilu sítě VPN přidružte aplikaci a skupinu služby Azure AD k profilu.

1. Otevřete portál Azure Portal. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
2. Zvolte **Mobilní aplikace**.
3. Klikněte na **Aplikace**.
4. Ze seznamu aplikací vyberte požadovanou aplikaci.
5. Klikněte na **Přiřazení**.
6. Klikněte na **Vybrat skupiny** a vyberte skupinu, kterou jste definovali dříve. Klikněte na **Vybrat**.
7. V okně **Přiřazení** vyberte jako **typ** možnost **Povinné**.
8. V seznamu **Sítě VPN** vyberte definici své sítě VPN.
 
    > [!NOTE]  
    > Někdy se může stát, že načtení hodnoty definice sítě VPN trvá až jednu minutu. Než kliknete na **Uložit**, počkejte tři až pět minut.

9. Klikněte na **Uložit**.

    ![Přidružení aplikace k síti VPN](media\vpn-per-app-app-to-vpn.png)

## <a name="verify-the-connection-on-the-ios-device"></a>Ověření připojení na zařízení s iOSem

Po nastavení sítě VPN pro jednotlivé aplikace a jejím přidružení k aplikaci ověřte, že připojení ze zařízení funguje.

### <a name="before-you-attempt-to-connect"></a>Než se pokusíte připojit

 - Ověřte, že používáte iOS 7 nebo novější.
 - Zkontrolujte, že *všechny* výše uvedené zásady nasazujete do stejné skupiny uživatelů. V opačném případě nebude síť VPN pro jednotlivé aplikace s největší pravděpodobností fungovat.  
 - Zkontrolujte, že máte nainstalovanou podporovanou aplikaci VPN od jiného výrobce. Podporují se tyto aplikace VPN:
    - Pulse Secure
    - CheckPoint
    - F5
    - SonicWall

### <a name="connect-using-the-per-app-vpn"></a>Připojení pomocí sítě VPN pro jednotlivé aplikace

Ověřte funkčnost bezdotykového prostředí – připojte se bez výběru sítě VPN nebo zadání svých přihlašovacích údajů. Bezdotykové prostředí znamená toto:

 - Zařízení vás nežádá, abyste vyjádřili důvěru serveru VPN. To znamená, že uvidíte **dynamické dialogové okno důvěryhodnosti**.
 - Nemusíte zadávat přihlašovací údaje.
 - Po klepnutí na tlačítko pro připojení se připojíte k síti VPN.

Ověřte připojení na zařízení s iOSem.

1. Klepněte na aplikaci VPN.
2. Klepněte na **Připojit**.  
Síť VPN se úspěšně připojí bez dalších výzev.

<!-- ## Troubleshooting the Per-App VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a>Další kroky

- Na nastavení iOSu se můžete podívat v článku [Nastavení sítě VPN pro zařízení s iOSem v Microsoft Intune](vpn-settings-ios.md).
-  Další informace o nastavení sítě VPN a Intune najdete v článku [Konfigurace nastavení sítě VPN v Microsoft Intune](vpn-settings-configure.md).