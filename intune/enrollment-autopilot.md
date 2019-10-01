---
title: Registrace zařízení pomocí automatických pilotů Windows
titleSuffix: Microsoft Intune
description: Naučte se registrovat zařízení s Windows 10 pomocí automatických pilotů Windows.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 3a08fb08792e4095235161079594ab40cf110e31
ms.sourcegitcommit: 2be16108b759caa8e067e8217e53a100d2880637
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/30/2019
ms.locfileid: "71681693"
---
# <a name="enroll-windows-devices-in-intune-by-using-the-windows-autopilot"></a>Registrace zařízení s Windows v Intune pomocí automatických pilotů Windows  
Automatický pilotní modul Windows zjednodušuje registraci zařízení v Intune. Sestavování a udržování přizpůsobených imagí operačního systému je časově náročný proces. Můžete také ztrácet čas uplatněním těchto vlastních imagí operačního systému na nová zařízení, abyste je připravili k použití, než je přidělíte koncovým uživatelům. Pomocí Microsoft Intune a autopilotního projektu můžete koncovým uživatelům poskytnout nová zařízení, aniž byste museli vytvářet, udržovat a používat vlastní image operačních systémů na zařízeních. Pokud ke správě zařízení s automatickým pilotem používáte Intune, můžete po registraci spravovat zásady, profily, aplikace a další. Přehled výhod, scénářů a požadavků najdete v tématu [Přehled Windows autopilotu](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

Existují čtyři typy nasazení autopilotu:
- [Režim automatického nasazení](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) pro veřejné terminály, digitální podpisy nebo sdílené zařízení
- [Bílá šetrnější](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove) umožňuje partnerům nebo pracovníkům IT předem zřídit počítač s Windows 10, aby byl plně nakonfigurovaný a připravený pro přípravu vlastního[projektu pro stávající zařízení](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) vám umožní snadno nasadit nejnovější verzi Windows 10 na vaše stávající zařízení.
- [Režim řízený uživatelem](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) pro tradiční uživatele. 


## <a name="prerequisites"></a>Předpoklady
- [Předplatné Intune](licenses.md)
- [Automatický zápis systému Windows povolen](windows-enroll.md#enable-windows-10-automatic-enrollment)
- [Předplatné Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>Jak získat sdílený svazek clusteru pro import v Intune

Další informace najdete v tématu Principy rutiny prostředí PowerShell.

- [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)

## <a name="add-devices"></a>Přidat zařízení

Zařízení s Windows autopilot můžete přidat tak, že naimportujete soubor CSV s jejich informacemi.

1. V [Intune v Azure Portal](https://aka.ms/intuneportal)vyberte možnost **registrace zařízení** > **registrace Windows** > **zařízení** > **importu**.

    ![Snímek obrazovky zařízení s Windows autopilotem](media/enrollment-autopilot/autopilot-import-device.png)

2. V části **Přidat zařízení s Windows autopilotem**přejděte do souboru CSV se seznamem zařízení, která chcete přidat. Soubor CSV by měl zobrazovat sériová čísla, ID produktů Windows, hodnoty hash hardwaru, volitelné značky skupin a volitelného přiřazeného uživatele. V seznamu můžete mít až 500 řádků. Použijte formát záhlaví a čáry zobrazený níže:

    `Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User`</br>
    `<serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>`

    ![Snímek obrazovky přidávání zařízení s Windows autopilotem](media/enrollment-autopilot/autopilot-import-device2.png)

    >[!IMPORTANT]
    > Pokud k přiřazení uživatele použijete nahrávání sdíleného svazku clusteru, ujistěte se, že přiřadíte platné hlavní názvy uživatelů (UPN). Pokud přiřadíte neplatný hlavní název uživatele (UPN) (nesprávné uživatelské jméno), může být zařízení nedostupné, dokud neodeberete neplatné přiřazení. Během nahrávání sdíleného svazku clusteru je jediným ověřováním, které jsme provedli ve sloupci **přiřazený uživatel** , kontrola platnosti názvu domény. Nemůžeme provést individuální ověření UPN, abyste se ujistili, že přiřazujete stávajícího nebo správného uživatele.

3. Vyberte **importovat** a začněte importovat informace o zařízení. Import může trvat několik minut.

4. Po dokončení importu vyberte možnost **registrace zařízení** > **registrace Windows** > **Windows autopilot** > **zařízení** > **Sync**. Zobrazí se zpráva, že synchronizace probíhá. Dokončení procesu může trvat několik minut v závislosti na tom, kolik zařízení se synchronizuje.

5. Aktualizujte zobrazení, aby se zobrazila nová zařízení.

## <a name="create-an-autopilot-device-group"></a>Vytvoření skupiny zařízení autopilot

1. V [Intune v Azure Portal](https://aka.ms/intuneportal)vyberte **skupiny** > **Nová skupina**.
2. V okně **Skupina** :
    1. Jako **typ skupiny**vyberte **zabezpečení**.
    2. Zadejte **název skupiny** a **Popis skupiny**.
    3. Jako **typ členství**vyberte buď **přiřazené** , nebo **dynamické zařízení**.
3. Pokud jste v předchozím kroku zvolili možnost **přiřazeno** pro **typ členství** , pak v okně **Skupina** zvolte **Členové** a do skupiny přidejte zařízení autopilot.
    Zařízení s automatickým pilotem, která ještě nejsou zaregistrovaná, jsou zařízení, kde se název rovná sériovému číslu zařízení.
4. Pokud jste zvolili možnost **Dynamická zařízení** pro **typ členství** výše, pak v okně **Skupina** zvolte **dynamické členy zařízení** a do pole **Upřesnit pravidlo** zadejte libovolný z následujících kódů. Tato pravidla shromažďují jenom zařízení s autopilotem, protože cílí na atributy, které mají jenom zařízení s autopilotem.
    - Pokud chcete vytvořit skupinu, která zahrnuje všechna vaše zařízení autopilota, zadejte: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Pole značky skupiny v Intune se mapuje na atribut ČísloObjednávky na zařízeních Azure AD. Pokud chcete vytvořit skupinu, která bude obsahovat všechna vaše zařízení autopilotu s konkrétní značkou skupiny (ČísloObjednávky pro zařízení Azure AD), musíte zadat: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`.
    - Pokud chcete vytvořit skupinu, která bude obsahovat všechna vaše zařízení autopilotu s určitým ID nákupní objednávky, zadejte: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`.
    
    Po přidání **pokročilého kódu pravidla** klikněte na **Uložit**.
5. Zvolte **Vytvořit**.  

## <a name="create-an-autopilot-deployment-profile"></a>Vytvoření profilu nasazení autopilotu
Profily nasazení autopilotu slouží ke konfiguraci zařízení autopilotu.
1. V [Intune v Azure Portal](https://aka.ms/intuneportal)vyberte v části **registrace zařízení**@no__t **-2** **profily nasazení** >   > **vytvořit profil**.
2. Na stránce **základy** zadejte **název** a volitelný **Popis**.

    ![Snímek stránky základy](media/enrollment-autopilot/create-profile-basics.png)

3. Pokud chcete, aby se všechna zařízení v přiřazených skupinách automaticky převedla na Automatický pilot, nastavte **převést všechna cílová zařízení na autopilot** na **Ano**. Všechna vlastněná podniková zařízení, která nejsou v přiřazených skupinách, se budou registrovat v rámci služby nasazení autopilotu. Zařízení v osobním vlastnictví nebudou převedena na autopilot. Povolí zpracování registrace 48 hodin. Když je zařízení odregistrované a resetované, připíše ho autopilot. Po zaregistrování zařízení tímto způsobem zakážete tuto možnost nebo odebráním přiřazení profilu zařízení odeberete ze služby pro nasazení autopilotu. Místo toho musíte [zařízení odebrat přímo](enrollment-autopilot.md#delete-autopilot-devices).
4. Vyberte **Další**.
5. Na stránce spouštěné při **prvním spuštění počítače (OOBE)** pro **režim nasazení**vyberte jednu z těchto dvou možností:
    - **Na základě uživatele**: zařízení s tímto profilem jsou přidružená k zaregistrování zařízení uživatelem. K registraci zařízení se vyžadují přihlašovací údaje uživatele.
    - **Samoobslužné nasazování (Preview)** : (vyžaduje zařízení s Windows 10, verze 1809 nebo novější), která s tímto profilem nejsou přidružená k uživateli, který registruje zařízení. K registraci zařízení se nevyžadují přihlašovací údaje uživatele. Pokud k zařízení není přidružený žádný uživatel, zásady dodržování předpisů na základě uživatele se na něj nevztahují. Při použití režimu samostatného nasazení se použijí jenom zásady dodržování předpisů, které cílí na toto zařízení.

    ![Snímek obrazovky se stránkou OOBE](media/enrollment-autopilot/create-profile-outofbox.png)

6. V poli **připojit ke službě Azure AD** vyberte možnost **připojeno k Azure AD**.
7. Nakonfigurujte následující možnosti:
    - **Licenční smlouva s koncovým uživatelem (EULA)** : (Windows 10, verze 1709 nebo novější) vyberte, jestli chcete uživatelům zobrazit smlouvu EULA.
    - **Nastavení ochrany osobních údajů**: tuto možnost vyberte, pokud chcete uživatelům zobrazit nastavení ochrany osobních údajů.
    >[!IMPORTANT]
    >Výchozí hodnota pro nastavení diagnostických dat se liší mezi verzemi systému Windows. U zařízení s Windows 10 verze 1903 je výchozí hodnota nastavená na úplné během nastavování předem připraveného prostředí. Další informace najdete v tématu [diagnostická data Windows](https://docs.microsoft.com/windows/privacy/windows-diagnostic-data) . <br>
    
    - **Skrýt změnu možností účtu (vyžaduje Windows 10 verze 1809 nebo novější)** : Pokud chcete zabránit tomu, aby se možnosti změny účtu zobrazovaly na stránce pro přihlášení a na chybové stránky domény, vyberte **Skrýt** . Tato možnost vyžaduje, [aby byl v Azure Active Directory nakonfigurovaný Branding společnosti](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding).
    - **Typ uživatelského účtu**: Vyberte typ účtu uživatele (**správce** nebo **standardní** uživatel). Umožníme uživateli připojit se k zařízení jako místní správce přidáním do místní skupiny správců. Nepovolujeme uživatele jako výchozího správce na zařízení.
    - **Povolit White šetrnější OOBE** (vyžaduje Windows 10 verze 1903 nebo novější; [další fyzické požadavky](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove#prerequisites)): Pokud chcete povolit podporu bílé šetrnější, vyberte **Ano** .
    - **Použít šablonu názvu zařízení** (vyžaduje Windows 10 verze 1809 nebo novější): Pokud chcete vytvořit šablonu, která se má použít při pojmenování zařízení během registrace, klikněte na **Ano** . Název musí mít maximálně 15 znaků a může obsahovat písmena, číslice a spojovníky. Názvy nemůžou být všechna čísla. K přidání sériového čísla specifického pro hardware použijte [makro% Serial%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) . Nebo použijte [makro% Rand: x%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) k přidání náhodného řetězce čísel, kde x se rovná počtu číslic, které se mají přidat. 
    - **Language (oblast)** \*: Vyberte jazyk, který chcete pro zařízení použít. Tato možnost je k dispozici pouze v případě, že jste vybrali možnost **samoobslužné nasazení** pro **režim nasazení**.
    - **Automaticky konfigurovat klávesnici**\*: Pokud je vybraná možnost **jazyk (region)** , můžete stránku výběru klávesnice přeskočit kliknutím na **Ano** . Tato možnost je k dispozici pouze v případě, že jste vybrali možnost **samoobslužné nasazení** pro **režim nasazení**.
8. Vyberte **Další**.
9. Na stránce **značky oboru** můžete volitelně přidat značky oboru, které chcete použít pro tento profil. Další informace o značkách oboru najdete v tématu [použití značek řízení přístupu na základě role a rozsahu pro distribuci IT](scope-tags.md).
10. Vyberte **Další**.
11. Na stránce **přiřazení** vyberte **vybrané skupiny** pro **přiřazení**.

    ![Snímek obrazovky se stránkou přiřazení](media/enrollment-autopilot/create-profile-assignments.png)

12. Zvolte **Vybrat skupiny, které se mají zahrnout**, a zvolte skupiny, které chcete zahrnout do tohoto profilu.
13. Pokud chcete vyloučit jakékoli skupiny, zvolte **Vybrat skupiny, které se mají vyloučit**, a zvolte skupiny, které chcete vyloučit.
14. Vyberte **Další**.
15. Na stránce **Revize + vytvořit** vyberte **vytvořit** a vytvořte profil.

    ![Snímek obrazovky se stránkou Revize](media/enrollment-autopilot/create-profile-review.png)

> [!NOTE]
> Intune bude pravidelně kontrolovat nová zařízení v přiřazených skupinách a pak začít proces přiřazování profilů těmto zařízením. Dokončení tohoto procesu může trvat několik minut. Před nasazením zařízení se ujistěte, že tento proces byl dokončen.  V části **registrace zařízení** > **registrace**zařízení s Windows @no__t **-3,** kde byste měli vidět změnu stavu profilu z "Nepřiřazeno" na "přiřazení" a nakonec na "přiřazeno".

## <a name="edit-an-autopilot-deployment-profile"></a>Úprava profilu nasazení autopilotu
Po vytvoření profilu nasazení autopilotu můžete upravit některé části profilu nasazení.   

1. V [Intune v Azure Portal](https://aka.ms/intuneportal)vyberte **registrace zařízení**.
2. V části **registrace systému Windows**v části **Windows autopilot** vyberte **profily nasazení**.
3. Vyberte profil, který chcete upravit.
4. Chcete-li změnit název nebo popis profilu nasazení, klikněte na tlačítko **vlastnosti** vlevo. Po provedení změn klikněte na **Uložit** .
5. Kliknutím na **Nastavení** provedete změny nastavení OOBE. Po provedení změn klikněte na **Uložit** .

> [!NOTE]
> Změny profilu se aplikují na zařízení přiřazená k tomuto profilu. Aktualizovaný profil se ale nepoužije na zařízení, které už je zaregistrované v Intune, až po resetování a nové registraci zařízení.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Výstrahy pro zařízení s nepřiřazeným autopilotem Windows autopilot  <!-- 163236 -->  

Výstrahy zobrazí, kolik zařízení programu autopilotu nemají profily nasazení autopilotu. Pomocí informací z výstrahy vytvořte profily a přiřaďte je nepřiřazeným zařízením. Když kliknete na výstrahu, zobrazí se úplný seznam zařízení s Windows autopilotem a podrobné informace o nich.


Pokud chcete zobrazit výstrahy pro Nepřiřazená zařízení, v [Intune v Azure Portal](https://aka.ms/intuneportal)vyberte **registrace zařízení** >  –**Přehled** > **Nepřiřazená zařízení**.  


## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Přiřazení uživatele ke konkrétnímu zařízení autopilotu

Můžete přiřadit uživatele ke konkrétnímu zařízení s autopilotem. Toto přiřazení předem vyplní uživatele z Azure Active Directory na přihlašovací stránce [firemních značek](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) během instalace systému Windows. Také vám umožní nastavit název vlastního pozdravu. Neumožňuje předem vyplnit ani změnit přihlášení k systému Windows. Tímto způsobem lze přiřadit pouze licencované uživatele Intune.

Požadavky: Azure Active Directory Portál společnosti byl nakonfigurován a Windows 10 verze 1809 nebo novější.

1. V [Intune v Azure Portal](https://aka.ms/intuneportal)vyberte **registrace zařízení** > **zařízení** se**systémem Windows** >  > vyberte zařízení > **přiřadit uživatele**.

    ![Snímek obrazovky přiřazení uživatele](media/enrollment-autopilot/assign-user.png)

2. Zvolte uživatele Azure licencovaného k používání Intune a zvolte **Vybrat**.

    ![Snímek obrazovky s vybraným uživatelem](media/enrollment-autopilot/select-user.png)

3. Do pole **popisný název uživatele** zadejte popisný název, nebo pouze přijměte výchozí nastavení. Tento řetězec je popisný název, který se zobrazí, když se uživatel přihlásí během instalace systému Windows.

    ![Snímek obrazovky s popisným názvem](media/enrollment-autopilot/friendly-name.png)

4. Vyberte **OK**.


## <a name="delete-autopilot-devices"></a>Odstranit zařízení autopilotu

Můžete odstranit zařízení Windows autopilot, která nejsou zaregistrovaná v Intune:

- Odstraňte zařízení z Windows autopilotu při **zápisu zařízení** > **zařízení**s**Windows registrace** > . Vyberte zařízení, která chcete odstranit, a pak zvolte **Odstranit**. Dokončení odstraňování zařízení Windows autopilotu může trvat několik minut.

Úplné odebrání zařízení z vašeho tenanta vyžaduje, abyste odstranili zařízení Intune, zařízení Azure Active Directory a záznamy zařízení Windows autopilot. To se dá udělat z Intune:

1. Pokud jsou zařízení zaregistrovaná v Intune, musíte je nejdřív [Odstranit v okně Intune všechna zařízení](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Odstraňte zařízení v **Azure Active Directory zařízeních v zařízeních @no__t-** 1**zařízení Azure AD**.

3. Odstraňte zařízení z Windows autopilotu při **zápisu zařízení** > **zařízení**s**Windows registrace** > . Vyberte zařízení, která chcete odstranit, a pak zvolte **Odstranit**. Dokončení odstraňování zařízení Windows autopilotu může trvat několik minut.

## <a name="using-autopilot-in-other-portals"></a>Použití autopilotu na jiných portálech
Pokud nemáte zájem o správu mobilních zařízení, můžete použít autopilotu na jiných portálech. I když používáte jiné portály, doporučujeme, abyste ke správě nasazení autopilotů používali jenom Intune. Když použijete Intune a jiný portál, Intune nebude moct:  

- Zobrazení změn v profilech vytvořených v Intune, ale upravené na jiném portálu
- Synchronizovat profily vytvořené na jiném portálu
- Zobrazit změny v přiřazení profilu provedené na jiném portálu
- Synchronizace přiřazení profilu se dokončila na jiném portálu.
- Zobrazit změny v seznamu zařízení, které byly vytvořeny na jiném portálu

## <a name="windows-autopilot-for-existing-devices"></a>Windows autopilot pro existující zařízení

Zařízení s Windows můžete seskupit pomocí ID korelace při registraci pomocí [autopilotu pro existující zařízení](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) prostřednictvím Configuration Manager. ID korelace je parametrem konfiguračního souboru autopilotu. [Atribut zařízení Azure AD enrollmentProfileName](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) se automaticky nastaví na hodnotu "OfflineAutopilotprofile-\<correlator ID @ no__t-2". To umožňuje vytvoření libovolných dynamických skupin Azure AD na základě ID korelace pomocí atributu enrollmentprofileName.

>[!WARNING] 
> Vzhledem k tomu, že ID korelace není v Intune předem uvedené, může zařízení hlásit jakékoli ID korelace, které chtějí. Pokud uživatel vytvoří ID korelace, které odpovídá autopilotu nebo názvu profilu Apple DEP, zařízení se přidá do jakékoli dynamické skupiny zařízení Azure AD na základě atributu enrollmentProfileName. Chcete-li se tomuto konfliktu vyhnout:
> - Vždy vytvářet dynamická pravidla skupiny, která odpovídají *celé* hodnotě enrollmentProfileName
> - Nikdy Nejmenujte autopilot nebo profily Apple DEP začínající na "OfflineAutopilotprofile-".

## <a name="next-steps"></a>Další kroky
Po konfiguraci Windows autopilotu pro registrovaná zařízení s Windows 10 se naučíte spravovat tato zařízení. Další informace najdete v tématu [co je Správa zařízení Microsoft Intune?](device-management.md)
