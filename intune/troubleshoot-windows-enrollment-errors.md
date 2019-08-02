---
title: Řešení potíží s registrací zařízení s Windows v Microsoft Intune
titleSuffix: Microsoft Intune
description: Návrhy pro řešení některých nejběžnějších problémů při registraci zařízení s Windows v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/29/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: d76b9581cac6e9d74e83ce50400e14468a13d3e6
ms.sourcegitcommit: c715c93bb242f4fe44bbdf2fd585909854ed72b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/30/2019
ms.locfileid: "68664177"
---
# <a name="troubleshoot-windows-device-enrollment-problems-in-microsoft-intune"></a>Řešení potíží s registrací zařízení s Windows v Microsoft Intune

Tento článek pomáhá správcům Intune pochopit a řešit problémy při registraci zařízení s Windows v Intune.

## <a name="prerequisites"></a>Požadavky
Než začnete řešit potíže, je důležité shromáždit některé základní informace. Tyto informace vám pomůžou lépe porozumět problému a zkrátit dobu, po kterou je možné najít řešení.

Shromážděte následující informace o problému:
- Má uživatel přiřazenou platnou licenci Intune? Než si uživatelé můžou zaregistrovat svoje zařízení, musí mít přiřazenou potřebnou licenci.
- Je na zařízení s Windows nainstalovaná nejnovější aktualizace? Některé funkce Intune fungují jenom s nejnovější verzí Windows. K dispozici je mnoho oprav pro známé problémy, které jsou dostupné prostřednictvím web Windows Update. Použití všech nejnovějších aktualizací často řeší potíže s registrací zařízení s Windows. 
- Jaká je přesná chybová zpráva?
- Kde se zobrazí chybová zpráva?
- Kdy problém začal? Byl zápis někdy zpracován? 
- Jakou platformu (Android, iOS, Windows) má problém?
- Kolik uživatelů je ovlivněno? Ovlivnili všichni uživatelé nebo jen některé?
- Kolik zařízení je ovlivněno? Jsou všechna zařízení ovlivněná nebo jenom některá?
- Co je Autorita MDM? Pokud je System Center Configuration Manager, jakou verzi Configuration Manager používáte?
- Jak se provádí registrace? Přináší vaše vlastní zařízení (BYOD) nebo Apple Program registrace zařízení (DEP) pomocí profilů zápisu?

## <a name="error-messages"></a>Chybové zprávy

### <a name="this-user-is-not-authorized-to-enroll"></a>Tento uživatel nemá autorizaci k registraci.

Chyba 0x801c003: "Tento uživatel nemá oprávnění k registraci. Můžete to zkusit znovu nebo se obraťte na správce systému a sdělte mu kód chyby (0x801c0003). "
Chyba 80180003: Něco se pokazilo. Tento uživatel nemá autorizaci k registraci. Můžete to zkusit znovu nebo se obraťte na správce systému s kódem chyby 80180003. "

**Způsobit** Kterákoli z následujících podmínek: 

- Uživatel už zaregistroval maximální počet zařízení povolených v Intune.    
- Zařízení je blokováno omezeními typů zařízení.    
- V počítači je spuštěný systém Windows 10 Home. Registrace v Intune nebo připojení služby Azure AD je ale podporovaná jenom v edicích Windows 10 pro a vyšší.

#### <a name="resolution"></a>Řešení
Tento problém může být několik možných řešení:

##### <a name="remove-devices-that-were-enrolled"></a>Odebrat zařízení, která byla zaregistrována
1. Přihlaste se k webu [Azure Portal](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).    
2. Přejít na **uživatele** > **Všichni uživatelé**.    
3. Vyberte příslušný účet uživatele a pak klikněte na **zařízení**.    
4. Vyberte všechna nepoužívaná nebo nežádoucí zařízení a pak klikněte na **Odstranit**. 

##### <a name="increase-thedevice-enrollment-limit"></a>Zvýšení limitu pro registraci zařízení

> [!NOTE]
> Tato metoda zvyšuje limit pro registraci zařízení pro všechny uživatele, nikoli jenom ovlivněného uživatele.

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview).
2. Přejít na **registrace** >zařízení **omezení registrace**a pak vyberte **omezení limitů počtu zařízení**.    
3. Zvyšte hodnotu limitu počtu **zařízení**. 

##### <a name="checkdevice-type-restrictions"></a>Ověřit omezení typu zařízení
1. Přihlaste se k [portálu](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) Intune pomocí účtu globálního správce.
2. V části **omezení typů zařízení**vyberte **výchozí** omezení registrace **zařízení** > .    
3. Vyberte **platformy**a pak vyberte možnost **Povolení** pro **Windows (MDM)** .

    > [!IMPORTANT]
    > Pokud je aktuální nastavení již **povoleno**, změňte ho na **blokovat**, uložte nastavení a pak ho změňte zpět na **povoleno** a uložte nastavení znovu. Tím se obnoví nastavení registrace.

4. Počkejte asi 15 minut a pak příslušné zařízení znovu zaregistrujte.    

##### <a name="upgrade-windows-10-home"></a>Upgradovat domovskou stránku Windows 10
[Upgradujte Windows 10 Home na Windows 10 pro](https://support.microsoft.com/help/12384/windows-10-upgrading-home-to-pro) nebo vyšší edici. 



### <a name="this-user-is-not-allowed-to-enroll"></a>Tento uživatel není povolen k registraci.

Chyba 0x801c0003: "Tento uživatel není povolen k registraci. Můžete to zkusit znovu nebo se obraťte na správce systému a sdělte mu kód chyby 801c0003. "

**Způsobit** **Uživatelé můžou připojovat zařízení k nastavení Azure AD** je nastavená na **žádná**. To zabrání novým uživatelům v připojení svých zařízení k Azure AD. Proto se registrace v Intune nezdařila.

#### <a name="resolution"></a>Řešení
1. Přihlaste se k [Azure Portal](https://portal.azure.com/) jako správce.    
2. Přejít na **Azure Active Directory** > **** zařízenínastavení zařízení.>     
3. Nastavení **Uživatelé můžou připojovat zařízení ke službě Azure AD** **všem**.    
4. Znovu zaregistrujte zařízení.   

### <a name="the-device-is-already-enrolled"></a>Zařízení je už zaregistrované.

Chyba 8018000a: Něco se pokazilo. Zařízení je už zaregistrované.  Můžete se obrátit na správce systému s kódem chyby 8018000a. "

**Způsobit** Platí jedna z následujících podmínek:
- Jiný uživatel už zařízení zaregistroval v Intune nebo se připojil k zařízení do Azure AD. Pokud chcete zjistit, jestli se jedná o tento případ, přejděte na **Nastavení** > **účty** > **pracovní přístup**. Vyhledejte zprávu, která bude vypadat přibližně takto: "Jiný uživatel v systému je již připojen k práci nebo škole. Odeberte prosím toto pracovní nebo školní připojení a zkuste to znovu. "    
- Agent Configuration Manager klienta je nainstalován v počítači.    

#### <a name="resolution"></a>Řešení

K vyřešení tohoto problému použijte jednu z následujících metod:

##### <a name="remove-the-other-work-or-school-account"></a>Odebrat jiný pracovní nebo školní účet
1. Odhlaste se z Windows a pak se přihlaste pomocí jiného účtu, který je zaregistrovaný nebo připojený k zařízení.    
2. Přejděte na **Nastavení** > **účty** > **pracovní přístup**a pak odeberte pracovní nebo školní účet.
3. Odhlaste se z Windows a pak se přihlaste pomocí svého účtu.    
4. Zaregistrujte zařízení v Intune nebo ho připojte k Azure AD. 

##### <a name="remove-the-configuration-manager-client"></a>Odebrání klienta Configuration Manager
Odeberte klienta Configuration Manager a znovu zaregistrujte zařízení.



### <a name="this-account-is-not-allowed-on-this-phone"></a>Tento účet není na tomto telefonu povolený.

Chyba: Tento účet není na tomto telefonu povolený. Ujistěte se, že informace, které jste zadali, jsou správné a potom to zkuste znovu nebo si vyžádejte podporu od vaší společnosti. "

**Způsobit** Uživatel, který se pokusil zaregistrovat zařízení, nemá platnou licenci Intune.

#### <a name="resolution"></a>Řešení
Přiřaďte uživateli platnou licenci Intune a pak zařízení zaregistrujte.


### <a name="looks-like-the-mdm-terms-of-use-endpoint-is-not-correctly-configured"></a>Vypadá to, že koncový bod podmínek použití MDM není správně nakonfigurovaný.

**Způsobit** Platí jedna z následujících podmínek: 
 - Pro Office 365 a Intune na tenantovi používáte správu mobilních zařízení (MDM) a uživatel, který se pokusí zaregistrovat zařízení, nemá platnou licenci Intune nebo licenci na Office 365.     
- Podmínky a ujednání MDM ve službě Azure AD jsou prázdné nebo neobsahují správnou adresu URL.    

#### <a name="resolution"></a>Řešení

Chcete-li tento problém vyřešit, použijte jednu z následujících metod: 
 
##### <a name="assign-a-valid-license-to-the-user"></a>Přiřadit uživateli platnou licenci
Otevřete centrum pro [správu Microsoft 365](https://portal.office.com/adminportal/home)a přiřaďte uživateli buď licenci Intune, nebo Office 365.

##### <a name="correct-themdm-terms-of-use-url"></a>Opravte adresu URL podmínek použití MDM.
  1. Přihlaste se k [Azure Portal](https://portal.azure.com/)a pak vyberte **Azure Active Directory**.    
  2. Vyberte **mobilita (MDM a mam)** a pak klikněte na **Microsoft Intune**.    
  3. Vyberte **Obnovit výchozí adresy URL MDM**a ověřte, že **Adresa URL podmínek použití MDM** je nastavená na **https://portal.manage.microsoft.com/TermsofUse.aspx** .    
  4. Zvolte **Uložit**.    


### <a name="something-went-wrong"></a>Něco se pokazilo.

Chyba 80180026: Něco se pokazilo. Potvrďte, že používáte správné přihlašovací údaje a že vaše organizace tuto funkci používá. Můžete to zkusit znovu nebo se obraťte na správce systému a sdělte mu kód chyby 80180026.

**Způsobit** K této chybě může dojít, když se pokusíte připojit počítač s Windows 10 ke službě Azure AD a platí obě následující podmínky: 
- V Azure je povolený automatický zápis MDM.    
- V počítači s Windows 10 je nainstalovaný klientský počítač Intune (agent pro počítače v Intune) nebo agent Configuration Manager klienta.

#### <a name="resolution"></a>Řešení
K vyřešení tohoto problému použijte jednu z následujících metod:

##### <a name="disablemdm-automatic-enrollment-in-azure"></a>Zakáže automatickou registraci MDM v Azure.
1. Přihlaste se k [Azure Portal](https://portal.azure.com/).    
2. Přejít na **Azure Active Directory** > **mobility (MDM a mam)**  > **Microsoft Intune**.    
3. Nastavte **obor uživatele MDM** na **žádný**a pak klikněte na **Uložit**.    
     
##### <a name="uninstall"></a>Odinstalace
Odinstalujte klientský počítač Intune nebo Configuration Manager klientského agenta z počítače.    

### <a name="the-software-cannot-be-installed"></a>Software nelze nainstalovat.

Chyba: "Software nelze nainstalovat, 0x80cf4017."

**Způsobit** Software klienta není aktuální.

#### <a name="resolution"></a>Řešení
1. Přihlaste [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)se k.    
2. Přejděte na **správce** > **klientského softwaru ke stažení**a pak klikněte na **Stáhnout klientský software**.    
3. Uložte instalační balíček a pak nainstalujte klientský software. 


### <a name="the-account-certificate-is-not-valid-and-may-be-expired"></a>Certifikát účtu není platný a pravděpodobně jeho platnost vypršela.

Chyba: "Certifikát účtu není platný a pravděpodobně vypršela jeho platnost, 0x80cf4017."

**Způsobit** Software klienta není aktuální.

#### <a name="resolution"></a>Řešení
1. Přihlaste [https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)se k.    
2. Přejděte na **správce** > **klientského softwaru ke stažení**a pak klikněte na **Stáhnout klientský software**.    
3. Uložte instalační balíček a pak nainstalujte klientský software.    

### <a name="your-organization-does-not-support-this-version-of-windows"></a>Vaše organizace nepodporuje tuto verzi Windows. 

Chyba: "Došlo k problému. Vaše organizace nepodporuje tuto verzi Windows.  (0x80180014)"

**Způsobit** Registrace Windows MDM je v tenantovi Intune zakázaná.

#### <a name="resolution"></a>Řešení
Pokud chcete tento problém vyřešit v samostatném prostředí Intune, postupujte takto: 
 
1. Přihlaste se k [Azure Portal](https://portal.azure.com/) jako správce.    
2. Na levé straně vyberte Intune a pak použijte**omezení registrace** ****  > zařízení.    
3. V nabídce **omezení typu zařízení**klikněte **na platformy**a pak vyberte možnost **Povolení** pro **Windows (MDM)** .    
4. Klikněte na **Uložit**.    
 
Pokud chcete tento problém vyřešit v hybridním MDM s Intune a Configuration Manager, postupujte takto: 
1. Otevřete konzolu Configuration Manager.    
2. Vyberte **Správa**a pak vyberte **Cloud Services**.    
3. Klikněte pravým tlačítkem na **Microsoft Intune předplatné**a pak vyberte **Konfigurovat platformy > Windows**.    
4. Zaškrtněte **možnost Povolit registraci** >  > zařízení se systémem Windows**OK**.  


### <a name="a-setup-failure-has-occurred-during-bulk-enrollment"></a>Při hromadné registraci došlo k chybě instalace.

**Způsobit** Uživatelské účty Azure AD v balíčku účtů (Package_GUID) pro příslušný zřizovací balíček neumožňují připojení zařízení ke službě Azure AD. Tyto účty Azure AD se automaticky vytvoří při nastavení zřizovacího balíčku pomocí nástroje Windows Configuration Designer (WCD) nebo nastavení aplikace školních počítačů. tyto účty se pak použijí pro připojení zařízení k Azure AD.

#### <a name="resolution"></a>Řešení
1. Přihlaste se k [Azure Portal](https://portal.azure.com/) jako správce.    
2. Přejít na **Azure Active Directory > zařízení > nastavení zařízení**.    
3. Nastavení uživatelé můžou ke **všem** nebo vybraným uživatelům připojovat ****  **zařízení do Azure AD** .

   Pokud zvolíte **vybrané** **, klikněte na**vybrat a potom kliknutím na **přidat členy** přidejte všechny uživatele, kteří se můžou ke svým zařízením připojit do Azure AD. Ujistěte se, že jsou přidané všechny účty Azure AD pro zřizovací balíček.
 
Další informace o tom, jak vytvořit zřizovací balíček pro Windows Configuration Designer, najdete v tématu [Vytvoření zřizovacího balíčku pro Windows 10](https://docs.microsoft.com/windows/configuration/provisioning-packages/provisioning-create-package).

Další informace o tom, jak nainstalovat aplikaci školních počítačů, najdete v tématu [použití aplikace s nastavením školních počítačů](https://docs.microsoft.com/education/windows/use-set-up-school-pcs-app).


### <a name="auto-mdm-enroll-failed"></a>Automatická registrace MDM: Selhalo 

Při automatickém pokusu o registraci zařízení s Windows 10 pomocí Zásady skupiny dojde k následujícím problémům: 
- V Plánovač úloh v části **Microsoft** > **Windows** > **EnterpriseMgmt**byl poslední výsledek spuštění **plánu vytvořeného klientem registrace pro automatické registraci v MDM z úlohy AAD** následující: **Automatická registrace MDM pro událost 76: Neúspěšné (Neznámý kód chyby Win32: 0x8018002b)**       
- V Prohlížeč událostí se v protokolech aplikací a služeb zaprotokolují následující události **/Microsoft/Windows/DeviceManagement-Enterprise-Diagnostics-Provider/admin**:   
    ```asciidoc
    Log Name: Microsoft-Windows-DeviceManagement-Enterprise-Diagnostics-Provider/Admin
    Source: DeviceManagement-Enterprise-Diagnostics-Provider
    Event ID: 76
    Level: Error
    Description: Auto MDM Enroll: Failed (Unknown Win32 Error code: 0x80180002b)
    ```
**Způsobit** Platí jedna z následujících podmínek: 
- Hlavní název uživatele obsahuje neověřenou nebo Nesměrovatelné domény, například. Local (jako joe@contoso.local).    
- **Obor uživatele MDM**je nastavený na **None (žádné**).  

#### <a name="resolution"></a>Řešení
Pokud hlavní název uživatele obsahuje neověřenou nebo Nesměrovatelné domény, použijte následující postup: 

1. Na serveru, na kterém Active Directory Domain Services (služba AD DS) běží na, otevřete modul **Uživatelé a počítače služby Active Directory** zadáním **DSA. msc** v dialogovém okně **Spustit** a pak klikněte na **OK**.    
2. Klikněte na **Uživatelé** ve vaší doméně a pak postupujte takto:  
    - Pokud existuje jenom jeden ovlivněný uživatel, klikněte na něj pravým tlačítkem a pak klikněte na **vlastnosti**. Na kartě **účet** v rozevíracím seznamu PŘÍPONa UPN v části **přihlašovací jméno uživatele**vyberte platnou příponu UPN, třeba contoso.com, a pak klikněte na **OK**.    
    - Pokud existuje více ovlivněných uživatelů, vyberte uživatele v nabídce **Akce** klikněte na možnost **vlastnosti**. Na kartě **účet** zaškrtněte políčko přípona **UPN** , v rozevíracím seznamu vyberte platnou příponu upn, jako je contoso.com, a pak klikněte na **OK**.
3. Počkejte na další synchronizaci nebo vynuťte rozdílovou synchronizaci z synchronizačního serveru spuštěním následujících příkazů v příkazovém řádku PowerShellu se zvýšenými oprávněními:
    ```powershell
    Import-Module ADSync
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

Pokud je  **obor uživatele MDM**nastavený na **None (žádné**), postupujte takto: 
 
1. Přihlaste se k [Azure Portal](https://portal.azure.com/)a pak vyberte **Azure Active Directory**.
2. Vyberte **mobilita (MDM a mam)** a pak vyberte **Microsoft Intune**.    
3. Nastavte **obor uživatele MDM** na **vše**. Nebo nastavte **obor uživatele MDM** na **nějaké**a vyberte skupiny, které můžou automaticky registrovat svoje zařízení s Windows 10.    
4. Nastavte **obor uživatele mam** na **žádný**.


## <a name="next-steps"></a>Další postup

- [Řešení potíží s registrací zařízení v Intune](troubleshoot-device-enrollment-in-intune.md)
- [Zeptejte se fóra služby Intune](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Podívejte se na blog týmu podpory Microsoft Intune.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Podívejte se na blog Microsoft Enterprise mobility and Security.](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
- [Získat podporu pro Microsoft Intune](https://docs.microsoft.com/intune/get-support) 