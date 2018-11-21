---
title: Nastavení registrace v Intune pro zařízení připojená k hybridní službě Active Directory pomocí Windows Autopilotu
titleSuffix: Microsoft Intune
description: K registraci zařízení připojených k hybridní službě Active Directory v Intune použijte Windows Autopilot.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 77a0c3f3a2e1ed0ee2dbc652049bb7057c736010
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52189958"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-using-intune-and-windows-autopilot-preview"></a>Nasazení zařízení připojených k hybridní službě Azure AD pomocí Intune a Windows Autopilotu (Preview)
Zařízení připojená k hybridní službě Azure Active Directory můžete nastavit pomocí Intune a Windows Autopilotu. Použijte k tomu následující postup.

> [!NOTE]
> Tato funkce se bude zavádět pro uživatelskou základnu v průběhu několika dalších dnů. Následující postup bude možné provést až po jejím zavedení pro váš účet.

## <a name="prerequisites"></a>Požadavky

- [Zařízení připojená k hybridní službě Active Directory](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) musí být úspěšně nakonfigurovaná.
    - Nezapomeňte [ověřit registraci pomocí rutiny Get-MsolDevice]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration).

Zařízení, která chcete zaregistrovat, musí:
- Používat Windows 10 s [aktualizací z října 2018](https://blogs.windows.com/windowsexperience/2018/10/02/how-to-get-the-windows-10-october-2018-update/)
- Mít přístup k internetu
- Mít přístup k Active Directory (připojení VPN se nepodporuje)
- Projít postupem Software spouštěný při prvním zapnutí zařízení

## <a name="set-up-windows-10-automatic-enrollment"></a>Nastavení automatické registrace pro Windows 10

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com) a vyberte **Azure Active Directory**.

   ![Snímek obrazovky portálu Azure Portal](./media/auto-enroll-azure-main.png)

2. Vyberte **Mobilita (MDM a MAM)**.

   ![Snímek obrazovky portálu Azure Portal](./media/auto-enroll-mdm.png)

3. Vyberte **Microsoft Intune**.

   ![Snímek obrazovky portálu Azure Portal](./media/auto-enroll-intune.png)

4. Ujistěte se, že uživatelé nasazující zařízení připojená ke službě Azure Active Directory pomocí Intune a Windows jsou členy skupiny, která je součástí vašeho **Oboru uživatele MDM**.

   ![Snímek obrazovky portálu Azure Portal](./media/auto-enroll-scope.png)

5. Použijte výchozí hodnoty pro následující adresy URL:
    - **Adresa URL podmínek použití MDM**
    - **Adresa URL zjišťování MDM**
    - **Adresa URL s předpisy služby MDM**
6. Zvolte **Uložit**.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>Zvýšení limitu pro účty počítačů v organizační jednotce

Konektor Intune pro Active Directory vytváří počítače registrované pomocí Autopilotu v místní doméně služby Active Directory. Počítač hostující tento konektor Intune musí mít práva k vytváření objektů počítače v této doméně. 

V některých doménách se počítačům práva k vytváření počítačů neudělují. Správci možná také nechtějí limit pro účty počítačů v doméně zvyšovat. V těchto situacích se dají tato práva delegovat na organizační jednotku, ve které se zařízení připojená k hybridní službě Azure AD vytvářejí.

Organizační jednotce, které se udělí právo k vytváření počítačů, musí odpovídat:
- organizační jednotka zadaná v profilu připojení k doméně
- nebo (pokud není vybraný žádný profil) název domény počítače pro vaši doménu

1. Otevřete položku **Uživatelé a počítače služby Active Directory** (DSA.msc).

2. Klikněte pravým tlačítkem na organizační jednotku, kterou použijete k vytváření počítačů připojených k hybridní službě Azure AD > **Delegovat řízení**.

    ![Snímek obrazovky delegování řízení](media/windows-autopilot-hybrid/delegate-control.png)

3. V **Průvodci delegováním řízení** zvolte **Další** > **Přidat** > **Typy objektů**.

4. V dialogovém okně **Typy objektů** zaškrtněte políčko **Počítače** a pak zvolte **OK**.

    ![Snímek obrazovky delegování řízení](media/windows-autopilot-hybrid/object-types-computers.png)

5. V dialogovém okně **Vyberte uživatele, počítače nebo skupiny** do pole **Zadejte názvy objektů k výběru** zadejte název počítače, ve kterém je konektor nainstalovaný.

    ![Snímek obrazovky delegování řízení](media/windows-autopilot-hybrid/enter-object-names.png)

6. Zvolte **Kontrola názvů**, aby se daná položka ověřila, a pak zvolte **OK** > **Další**.

7. Zvolte **Vytvořit vlastní úkol a delegovat jeho řízení** > **Další**.

8. Zvolte **Pouze následující objekty ve složce** a zaškrtněte tyto možnosti:
    - **Objekty počítače**
    - **Vytvořit vybrané objekty v této složce**
    - **Odstranit vybrané objekty z této složky**

    ![Snímek obrazovky delegování řízení](media/windows-autopilot-hybrid/only-following-objects.png)
    
9. Vyberte **Další**.

10. V části **Oprávnění** zaškrtněte možnost **Úplné řízení** (tím se zaškrtnou všechny ostatní možnosti) > **Další** > **Dokončit**.

    ![Snímek obrazovky delegování řízení](media/windows-autopilot-hybrid/full-control.png)

## <a name="install-the-intune-connector"></a>Instalace konektoru Intune

Konektor Intune pro Active Directory je nutné nainstalovat do počítače s Windows Serverem 2016, který má přístup k internetu a službě Active Directory. Pokud chcete zvýšit škálování a dostupnost nebo chcete podporovat více domén Active Directory, můžete do vašeho prostředí nainstalovat více konektorů. Konektor doporučujeme nainstalovat na server, na kterém se neprovozují žádné jiné konektory Intune.

1. Ujistěte se, že máte nainstalovaný a nakonfigurovaný podle popisu v jazykové sady [konektor Intune (Preview) jazykové požadavky](https://docs.microsoft.com/windows/deployment/windows-autopilot/intune-connector).
2. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Konektor Intune pro Active Directory (Preview)** > **Přidat konektor**. 
3. Podle pokynů tento konektor stáhněte.
4. Otevřete instalační soubor staženého konektoru a nainstalujte konektor (ODJConnectorBootstrapper.exe).
5. Na konci instalace zvolte **Konfigurovat**.
6. Zvolte **Přihlásit se**.
7. Zadejte přihlašovací údaje uživatele s rolí globálního správce nebo správce Intune.
8. Přejděte na **Registrace zařízení** > **Registrace zařízení s Windows** > **Konektor Intune pro Active Directory (Preview)** a ověřte, že stav připojení je **Aktivní**.

### <a name="configure-web-proxy-settings"></a>Konfigurace nastavení webového proxy serveru

Pokud máte v síťovém prostředí webový proxy server, zajistěte správné fungování konektoru Intune pro Active Directory podle těchto pokynů: [Práce s existujícími místními proxy servery](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy-configure-connectors-with-proxy-servers).


## <a name="create-a-device-group"></a>Vytvoření skupiny zařízení
1. V [Intune](https://aka.ms/intuneportal) zvolte **Skupiny** > **Nová skupina**.
2. V okně **Skupina**:
    1. Pro **Typ skupiny** zvolte **Zabezpečení**.
    2. Zadejte **Název skupiny** a **Popis skupiny**.
    3. Zvolte možnost pro **Typ členství**.
3. Pokud jste výše pro **Typ členství** zvolili **Dynamické zařízení**, potom v okně **Skupina** zvolte **Členové s dynamickými zařízeními** a do pole **Pokročilé pravidlo** zadejte některý z následujících kódů.
    - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení Autopilot, zadejte: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení Autopilot s konkrétním ID objednávky, zadejte: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení Autopilot s konkrétním ID nákupní objednávky, zadejte: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Po přidání kódu do pole **Pokročilé pravidlo** zvolte **Uložit**.
5. Zvolte **Vytvořit**.  

## <a name="register-your-autopilot-devices"></a>Registrace zařízení Autopilot

Zvolte jeden z následujících způsobů registrace zařízení Autopilot:

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>Registrace zařízení Autopilot, která jsou už zaregistrovaná

1. Vytvořte profil nasazení Autopilotu s možností **Převést všechna cílová zařízení na Autopilot** nastavenou na **Ano**. 
2. Přiřaďte tento profil skupině obsahující členy, které chcete automaticky zaregistrovat pomocí Autopilotu.

Další informace najdete v tématu [Vytvoření profilu nasazení Autopilotu](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### <a name="register-autopilot-devices-that-arent-enrolled"></a>Registrace zařízení Autopilot, která nejsou zaregistrovaná

Pokud zařízení ještě nejsou zaregistrovaná, můžete je zaregistrovat sami. Další informace najdete v tématu [Přidání zařízení](enrollment-autopilot.md#add-devices).

### <a name="register-devices-from-an-oem"></a>Registrace zařízení od výrobce OEM

Pokud kupujete nová zařízení, můžou někteří výrobci OEM zaregistrovat tato zařízení za vás. Další informace najdete na [stránce Windows Autopilot](http://aka.ms/WindowsAutopilot).

Když jsou zařízení Autopilot zaregistrovaná (před jejich registrací v Intune), zobrazují se na třech místech (s názvy nastavenými na jejich sériová čísla):
- V okně Zařízení Autopilot v Intune na portálu Azure Portal (**Registrace zařízení** > **Registrace zařízení s Windows** > **Zařízení**)
- V okně Zařízení Azure AD v Intune na portálu Azure Portal (**Zařízení** > **Zařízení Azure AD**)
- V okně Všechna zařízení AAD v Azure Active Directory na portálu Azure Portal (**Zařízení** > **Všechna zařízení**)

Po registraci v Intune se zařízení Autopilot budou zobrazovat na čtyřech místech:
- V okně Zařízení Autopilot v Intune na portálu Azure Portal (**Registrace zařízení** > **Registrace zařízení s Windows** > **Zařízení**)
- V okně Zařízení Azure AD v Intune na portálu Azure Portal (**Zařízení** > **Zařízení Azure AD**)
- V okně Všechna zařízení AAD v Azure Active Directory na portálu Azure Portal (**Zařízení** > **Všechna zařízení**)
- V okně Všechna zařízení v Intune na portálu Azure Portal (**Zařízení** > **Všechna zařízení**)

Po registraci zařízení Autopilot se názvy těchto zařízení změní na název hostitele příslušného zařízení. Ve výchozím nastavení název začíná řetězcem „DESKTOP-“.




## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Vytvoření a přiřazení profilu nasazení Autopilotu
Profily nasazení Autopilotu slouží ke konfiguraci zařízení s AutoPilotem.

1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > **Vytvořit profil**.
2. Zadejte **název** a volitelný **popis**.
3. Jako **Režim nasazení** zvolte **Řízení uživatelem**.
4. V poli **Připojit k Azure AD jako** zvolte **Připojeno k hybridní službě Azure AD (Preview)**.
5. Vyberte **Software spouštěný při prvním zapnutí zařízení**, nakonfigurujte možnosti podle potřeby a pak zvolte **Uložit**.
6. Výběrem možnosti **Vytvořit** vytvořte profil. 
7. V okně profilu vyberte **Přiřazení**.
8. Zvolte **Vybrat skupiny** > v okně **Vybrat skupiny** vyberte skupinu zařízení > **Vybrat**.

Bude trvat přibližně 15 minut, než se stav profilu zařízení změní z **Nepřiřazeno** na **Přiřazení** a nakonec na **Přiřazeno**.

## <a name="turn-on-the-enrollment-status-page-optional"></a>Zapnutí stránky stavu registrace (volitelné)

1. V [Intune](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Registrace zařízení s Windows** > **Stránka stavu registrace (Preview)**.
2. V okně **Stránka stavu registrace** zvolte **Výchozí** > **Nastavení**.
3. U možnosti **Zobrazit průběh instalace aplikací a profilů** zvolte **Ano**.
4. Nakonfiguruje další možnosti podle potřeby.
5. Zvolte **Uložit**.

## <a name="create-and-assign-a-domain-join-profile"></a>Vytvoření a přiřazení profilu připojení k doméně

1. V [Intune](https://aka.ms/intuneportal) zvolte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
2. Zadejte tyto vlastnosti:
   - **Název**: Zadejte popisný název nového profilu.
   - **Popis**: Zadejte popis profilu.
   - **Platforma**: Zvolte **Windows 10 a novější**.
   - **Typ profilu**: Zvolte **Připojení k doméně (Preview)**.
3. Zvolte **Nastavení** a zadejte položky **Předpona názvu počítače**, **Název domény** a **Organizační jednotka** (volitelně). 
4. Zvolte **OK** > **Vytvořit**. Profil se vytvoří a zobrazí se v seznamu.
5. Pokud chcete profil přiřadit, postupujte podle kroků v části [Přiřazení profilu zařízení](device-profile-assign.md#assign-a-device-profile). 

## <a name="next-steps"></a>Další postup

Po konfiguraci Windows Autopilotu si přečtěte, jak tato zařízení spravovat. Další informace najdete v článku [Co je správa zařízení v Microsoft Intune](device-management.md).
