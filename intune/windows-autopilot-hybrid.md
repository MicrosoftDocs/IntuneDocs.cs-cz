---
title: Registrace pro hybridní Azure zařízení připojených k doméně AD - Windows Autopilot
titleSuffix: ''
description: Registrace hybridního Azure pomocí Windows Autopilot zařízení připojených k doméně AD v Microsoft Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 12/06/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8518d8fa-a0de-449d-89b6-8a33fad7b3eb
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cb9d1f52ccb147dc9a412f3cb7b601e3b18f214a
ms.sourcegitcommit: a63b9eaa59867ab2b0a6aa415c19d9fff4fda874
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/25/2019
ms.locfileid: "67389324"
---
# <a name="deploy-hybrid-azure-ad-joined-devices-by-using-intune-and-windows-autopilot"></a>Nasazení hybridní Azure zařízení připojených k doméně AD s použitím Intune a Windows Autopilot
Nastavit hybridní služby Azure Active Directory (Azure AD) můžete použít Intune a Windows Autopilot – připojené zařízení. Chcete-li to provést, postupujte podle kroků v tomto článku.

## <a name="prerequisites"></a>Požadavky

Úspěšně konfigurovat vaše [hybridní Azure zařízení připojených k doméně AD](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan). Nezapomeňte [ověřte registraci vašeho zařízení]( https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#verify-the-registration) pomocí rutiny Get-MsolDevice.

Zařízení, která chcete zaregistrovat, musí:
- Běžet v1809 Windows 10 nebo vyšší.
- Mít přístup k internetu
- Máte přístup ke službě Active Directory (připojení k síti VPN v tuto chvíli nepodporuje).
- Této oblasti podstupovali prostředí out-of-box (OOBE).
- Možné poslat příkaz ping řadič domény, který se pokoušíte připojit.

## <a name="set-up-windows-10-automatic-enrollment"></a>Nastavení automatické registrace pro Windows 10

1. Přihlaste se k [webu Azure portal](https://portal.azure.com) a v levém podokně vyberte **Azure Active Directory**.

   ![Na webu Azure portal](./media/auto-enroll-azure-main.png)

1. Vyberte **Mobilita (MDM a MAM)** .

   ![V podokně Azure Active Directory](./media/auto-enroll-mdm.png)

1. Vyberte **Microsoft Intune**.

   ![V podokně nastavení mobilních zařízení (MDM a MAM)](./media/auto-enroll-intune.png)

1. Ujistěte se, že uživatelé, kteří si nasadí Azure zařízení připojených k doméně AD s použitím Intune a Windows jsou členy skupiny, která je součástí vašeho **obor uživatele MDM**.

   ![V podokně Konfigurace mobilita (MDM a MAM)](./media/auto-enroll-scope.png)

1. Použít výchozí hodnoty v **URL MDM podmínek použití**, **adresa URL zjišťování MDM**, a **adresa URL s předpisy MDM** pole a pak vyberte **Uložit**.

## <a name="increase-the-computer-account-limit-in-the-organizational-unit"></a>Zvýšení limitu pro účty počítačů v organizační jednotce

Konektor Intune pro Active Directory vytvoří autopilot zaregistrovaných počítačů v místní doméně služby Active Directory. Počítač hostující konektor Intune musí mít oprávnění k vytváření počítačových objektů v rámci domény. 

Některé domény v počítačích nejsou udělena práva k vytváření počítače. Kromě toho domény mají integrovanou limit (výchozí je 10), která se vztahuje na všechny uživatele a počítače, které nejsou delegovaná oprávnění k vytváření počítačových objektů. Proto je potřeba delegovat na počítače, které hostují konektor Intune v organizační jednotce práva kde hybridní Azure se vytvoří zařízení připojených k doméně AD.

Organizační jednotky, který má oprávnění k vytvoření počítače se shoduje:
- Organizační jednotky, který je zadán v profilu připojení k doméně.
- Pokud je vybrán žádný profil, název domény počítače pro vaši doménu.

1. Otevřít **Active Directory Users and Computers (DSA.msc)** .

1. Klikněte pravým tlačítkem na organizační jednotku, která použijete k vytvoření Azure v hybridním prostředí počítače připojené k doméně AD a pak vyberte **delegovat řízení**.

    ![Příkaz delegovat řízení](media/windows-autopilot-hybrid/delegate-control.png)

1. V **delegování řízení** průvodce, vyberte **Další** > **přidat** > **typy objektů**.

1. V **typy objektů** podokně, vyberte **počítače** zaškrtněte políčko a potom vyberte **OK**.

    ![V podokně typy objektů](media/windows-autopilot-hybrid/object-types-computers.png)

1. V **vybrat uživatele, počítače nebo skupiny** podokno v **zadejte názvy objektů k výběru** zadejte název počítače, ve kterém je konektor nainstalovaný.

    ![V podokně vyberte uživatele, počítače nebo skupiny](media/windows-autopilot-hybrid/enter-object-names.png)

1. Vyberte **Kontrola názvů** ověřit vaše položky, vyberte **OK**a pak vyberte **Další**.

1. Vyberte **vytvořit vlastní úkol a delegovat jeho** > **Další**.

1. Vyberte **pouze následující objekty ve složce** zaškrtněte políčko a potom vyberte **počítačových objektů**, **vytvořit vybrané objekty v této složce**, a  **Odstranit vybrané objekty v této složce** zaškrtávací políčka.

    ![V podokně typ objektu služby Active Directory](media/windows-autopilot-hybrid/only-following-objects.png)
    
1. Vyberte **Další**.

1. V části **oprávnění**, vyberte **úplné řízení** zaškrtávací políčko.  
    Tato akce vybere všechny další možnosti.

    ![Podokno oprávnění](media/windows-autopilot-hybrid/full-control.png)

1. Vyberte **Další**a pak vyberte **Dokončit**.

## <a name="install-the-intune-connector"></a>Instalace konektoru Intune

Konektor Intune pro službu Active Directory musí být nainstalován na počítači, na kterém běží Windows Server 2016 nebo novější. Počítač musí mít také přístup k Internetu a služby Active Directory. Pokud chcete zvýšit škálování a dostupnost nebo chcete podporovat více domén Active Directory, můžete do vašeho prostředí nainstalovat více konektorů. Doporučujeme vám však nainstalovat konektor na serveru, na kterém neběží všech dalších konektorů Intune.

1. Ujistěte se, že máte nainstalovaný a nakonfigurovaný podle popisu v jazykové sady [konektor Intune (Preview) jazykové požadavky](https://docs.microsoft.com/windows/deployment/windows-autopilot/intune-connector).
2. V [Intune](https://aka.ms/intuneportal)vyberte **registrace zařízení** > **registrace Windows** > **konektor Intune pro Active Directory () Ve verzi Preview)**  > **přidání konektoru**. 
3. Postupujte podle pokynů ke stažení konektoru.
4. Otevřete stažený soubor Instalační program konektoru *ODJConnectorBootstrapper.exe*, a nainstalujte konektor.
5. Na konci instalace zaškrtněte **konfigurovat**.
6. Vyberte **přihlášení**.
7. Zadejte přihlašovací údaje roli globálního správce nebo správce služby Intune.  
   Uživatelský účet musí mít přiřazenou licenci pro Intune.
8. Přejděte na **registrace zařízení** > **registrace Windows** > **konektor Intune pro službu Active Directory (Preview)** a potom ověřte, že Stav připojení je **aktivní**.

> [!NOTE]
> Po přihlášení ke konektoru může trvat několik minut, než se zobrazí v [Intune](https://aka.ms/intuneportal). Zobrazí se pouze v případě, že může úspěšně komunikovat se službou Intune.

### <a name="turn-off-ie-enhanced-security-configuration"></a>Vypnout konfiguraci rozšířeného zabezpečení Internet Exploreru
Ve výchozím nastavení systém Windows Server má Internet Explorer konfigurace rozšířeného zabezpečení zapnutá. Pokud se nemůžete přihlásit ke službě Intune Connector pro službu Active Directory pak vypnutí konfigurace rozšířeného zabezpečení Internet Exploreru pro správce. [Aplikace Internet Explorer vypnutí konfigurace rozšířeného zabezpečení](https://blogs.technet.microsoft.com/chenley/2011/03/10/how-to-turn-off-internet-explorer-enhanced-security-configuration)

### <a name="configure-web-proxy-settings"></a>Konfigurace nastavení webového proxy serveru

Pokud máte webový proxy server v síťovém prostředí, ujistěte se, že je konektor Intune pro Active Directory funguje správně rekapitulací [práce s existující místní proxy servery](autopilot-hybrid-connector-proxy.md).


## <a name="create-a-device-group"></a>Vytvoření skupiny zařízení
1. V [Intune](https://aka.ms/intuneportal)vyberte **skupiny** > **novou skupinu**.

1. V **skupiny** podokno, postupujte takto:

    a. Pro **typ skupiny**vyberte **zabezpečení**.

    b. Zadejte **název skupiny** a **popis skupiny**.

    c. Vyberte **typ členství**.

1. Pokud jste vybrali **dynamické zařízení** pro typ členství v **skupiny** vyberte **členové s dynamickými zařízeními** a pak na **rozšířené pravidlo** pole, proveďte jednu z následujících akcí:
    - Chcete-li vytvořit skupinu, která zahrnuje všechna svá zařízení Autopilot, zadejte `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`.
    - Atribut ID objednávky zařízení Azure AD mapuje pole značka skupiny v Intune. Pokud chcete vytvořit skupinu, která obsahuje všechna svá zařízení Autopilot konkrétní Tag(OrderID) skupiny je nutné zadat: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
    - Chcete-li vytvořit skupinu, která zahrnuje všechna zařízení Autopilot s konkrétním ID nákupní objednávky, zadejte `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`.
    
1. Vyberte **Uložit**.

1. Vyberte **Vytvořit**.  

## <a name="register-your-autopilot-devices"></a>Registrace zařízení Autopilot

Vyberte jednu z následujících způsobů, jak zaregistrovat svá zařízení Autopilot.

### <a name="register-autopilot-devices-that-are-already-enrolled"></a>Registrace zařízení Autopilot, která jsou už zaregistrovaná

1. Vytvořte profil nasazení Autopilotu s možností **Převést všechna cílová zařízení na Autopilot** nastavenou na **Ano**. 
2. Přiřaďte profil ke skupině, která obsahuje členy, které chcete automaticky zaregistrují do služby Autopilot.

Další informace najdete v tématu [Vytvoření profilu nasazení Autopilotu](enrollment-autopilot.md#create-an-autopilot-deployment-profile).

### <a name="register-autopilot-devices-that-arent-enrolled"></a>Registrace zařízení Autopilot, která nejsou zaregistrovaná

Pokud zařízení ještě nejsou zaregistrovaná, můžete je zaregistrovat sami. Další informace najdete v tématu [Přidání zařízení](enrollment-autopilot.md#add-devices).

### <a name="register-devices-from-an-oem"></a>Registrace zařízení od výrobce OEM

Pokud kupujete nová zařízení, můžou někteří výrobci OEM zaregistrovat tato zařízení za vás. Další informace najdete na [stránce Windows Autopilot](http://aka.ms/WindowsAutopilot).

Pokud jsou vaše zařízení Autopilot *zaregistrovaný*, před jejich registraci do Intune, se zobrazí na třech místech (s názvy, nastavit jejich sériová čísla):
- **Zařízení Autopilot** podokno v Intune na portálu Azure portal. Vyberte **registrace zařízení** > **registrace Windows** > **zařízení**.
- **Podpora k zařízením Azure AD** podokno v Intune na portálu Azure portal. Vyberte **zařízení** > **podpora k zařízením Azure AD**.
- **Azure AD všechna zařízení** podokně ve službě Azure Active Directory na webu Azure Portal tak, že vyberete **zařízení** > **všechna zařízení**.

Vaše Autopilot zařízení po *zaregistrovaná*, zobrazují se v čtyři místa:
- **Zařízení Autopilot** podokno v Intune na portálu Azure portal. Vyberte **registrace zařízení** > **registrace Windows** > **zařízení**.
- **Podpora k zařízením Azure AD** podokno v Intune na portálu Azure portal. Vyberte **zařízení** > **podpora k zařízením Azure AD**.
- **Azure AD všechna zařízení** podokně ve službě Azure Active Directory na webu Azure Portal. Vyberte **zařízení** > **všechna zařízení**.
- **Všechna zařízení** podokno v Intune na portálu Azure portal. Vyberte **zařízení** > **všechna zařízení**.

Po registraci vašeho zařízení Autopilot jejich názvy se název hostitele zařízení. Ve výchozím nastavení, název hostitele začíná *DESKTOP -* .


## <a name="create-and-assign-an-autopilot-deployment-profile"></a>Vytvoření a přiřazení profilu nasazení Autopilotu
Profily nasazení Autopilotu slouží ke konfiguraci zařízení s AutoPilotem.

1. V [Intune](https://aka.ms/intuneportal)vyberte **registrace zařízení** > **registrace Windows** > **profily nasazení**  >  **Vytvořit profil**.
1. Zadejte **název** a volitelně **popis**.
1. Pro **režim nasazení**vyberte **řízené uživatele**.
1. V **připojit k Azure AD jako** vyberte **připojený hybridní službě Azure AD (Preview)** .
1. Vyberte **Out-of-box zapnutí**, nakonfigurujte možnosti podle potřeby a potom vyberte **Uložit**.
1. Volbou **Vytvořit** vytvořte profil. 
1. V podokně profilů zvolte **přiřazení**.
1. Vyberte **vybrat skupiny**.
1. V **vybrat skupiny** podokně, vyberte skupinu zařízení a potom klikněte na tlačítko **vyberte**.

Trvá přibližně 15 minut pro stav profilu zařízení změnit z *Nepřiřazeno* k *přiřazování* a nakonec *přiřazeno*.

## <a name="optional-turn-on-the-enrollment-status-page"></a>(Volitelné) Tato stránka stavu registrace

1. V [Intune](https://aka.ms/intuneportal)vyberte **registrace zařízení** > **registrace Windows** > **stránka stavu registrace**.
1. V **stránka stavu registrace** vyberte **výchozí** > **nastavení**.
1. V **zobrazit průběh instalace aplikaci a profilu** vyberte **Ano**.
1. Nakonfiguruje další možnosti podle potřeby.
1. Vyberte **Uložit**.

## <a name="create-and-assign-a-domain-join-profile"></a>Vytvoření a přiřazení profilu připojení k doméně

1. V [Intune](https://aka.ms/intuneportal)vyberte **konfigurace zařízení** > **profily** > **vytvořit profil**.
1. Zadejte tyto vlastnosti:
   - **Název**: Zadejte popisný název pro nový profil.
   - **Popis**: Zadejte popis profilu.
   - **Platforma**: Vyberte **Windows 10 a novější**.
   - **Typ profilu**: Vyberte **připojení k doméně (Preview)** .
1. Vyberte **nastavení**a potom zadejte **předpona názvu počítače**, **název domény**a (volitelně) **organizační jednotka** v [Formátu DN](https://docs.microsoft.com/windows/desktop/ad/object-names-and-identities#distinguished-name). 
1. Vyberte **OK** > **vytvořit**.  
    Profil se vytvoří a zobrazí v seznamu.
1. Pokud chcete přiřadit profil, postupujte podle kroků v části [profil zařízení přiřadit](device-profile-assign.md#assign-a-device-profile) a přiřaďte profil do stejné skupiny použité v tomto kroku [vytvoření skupiny zařízení](windows-autopilot-hybrid.md#create-a-device-group)
   - Nasazení víc profilů připojení k doméně
   
     a. Vytvoření dynamické skupiny, která zahrnuje všechna svá zařízení Autopilot konkrétní profilu nasazení Autopilotu, zadejte (device.enrollmentProfileName - eq "Název profilu Autopilot"). 
     
     b. Nahraďte "Název profilu Autopilot" zobrazovaný název profilu vytvořené v rámci [vytvoření a přiřazení profilu nasazení Autopilotu](windows-autopilot-hybrid.md#create-and-assign-an-autopilot-deployment-profile). 
     
     c. Vytvoření více profilů nasazení Autopilotu a přiřadit profil zadaný do této dynamické skupiny zařízení.

> [!NOTE]
> Pojmenování funkce pro Windows Autopilotu pro hybridní připojení k Azure AD nepodporuje proměnné například sériového portu % a podporují pouze předpony pro název počítače.

## <a name="next-steps"></a>Další postup

Po konfiguraci Windows Autopilotu si přečtěte, jak tato zařízení spravovat. Další informace najdete v tématu [co je Správa zařízení v Microsoft Intune?](device-management.md).
