---
title: Registrace zařízení pomocí Windows Autopilotu
titleSuffix: Microsoft Intune
description: Zjistěte, jak registrovat zařízení s Windows 10 pomocí Windows Autopilotu.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: high
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.reviewer: spshumwa
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5066afdaf303a1cef20f80d3134f2382f718d86b
ms.sourcegitcommit: 2fddb293d37453736ffa54692d03eca642f3ab58
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/22/2019
ms.locfileid: "74390734"
---
# <a name="enroll-windows-devices-in-intune-by-using-the-windows-autopilot"></a>Enroll Windows devices in Intune by using the Windows Autopilot  
The Windows Autopilot simplifies enrolling devices in Intune. Vytváření a udržování přizpůsobených imagí operačního systému je proces, který zabere hodně času. Další čas můžete také strávit aplikováním těchto vlastních imagí operačního systému na nová zařízení, abyste je připravili k použití, než je předáte koncovým uživatelům. S Microsoft Intune a Autopilotem můžete nová zařízení koncovým uživatelům poskytovat, aniž by bylo nutné vlastní image operačního systému vytvářet, udržovat a aplikovat na zařízení. Když zařízení s Autopilotem spravujete pomocí Intune, můžete v zařízeních po registraci spravovat zásady, profily, aplikace a mnoho dalšího. Přehled výhod, scénáře a požadavky najdete v [přehledu Windows Autopilotu](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

There are four types of Autopilot deployment:
- [Self Deploying Mode](https://docs.microsoft.com/windows/deployment/windows-autopilot/self-deploying) for kiosks, digital signage, or a shared device
- [White Glove](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove) enables partners or IT staff to pre-provision a Windows 10 PC so that it's fully configured and business-ready -[Autopilot for existing devices](https://docs.microsoft.com/windows/deployment/windows-autopilot/existing-devices) enables you to easily deploy the latest version of Windows 10 to your existing devices
- [User Driven Mode](https://docs.microsoft.com/windows/deployment/windows-autopilot/user-driven) for traditional users. 


## <a name="prerequisites"></a>Požadované součásti
- [Intune subscription](../fundamentals/licenses.md)
- [Povolená automatická registrace pro Windows](windows-enroll.md#enable-windows-10-automatic-enrollment)
- [Azure Active Directory Premium subscription](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>How to get the CSV for Import in Intune

For more information, see the understanding powershell cmdlet.

- [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)

## <a name="add-devices"></a>Přidání zařízení

Zařízení Windows Autopilot můžete přidat importováním souboru CSV s jejich informacemi.

1. In the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), choose **Device enrollment** > **Windows enrollment** > **Devices** > **Import**.

    ![Snímek obrazovky se zařízeními Windows Autopilot](./media/enrollment-autopilot/autopilot-import-device.png)

2. V části **Přidat zařízení Windows AutoPilot** přejděte na soubor CSV se seznamem zařízení, která chcete přidat. The CSV file should list the serial numbers, Windows product IDs, hardware hashes, optional group tags, and optional assigned user. You can have up to 500 rows in the list. Use the header and line format shown below:

    `Device Serial Number,Windows Product ID,Hardware Hash,Group Tag,Assigned User`</br>
    `<serialNumber>,<ProductID>,<hardwareHash>,<optionalGroupTag>,<optionalAssignedUser>`

    ![Snímek obrazovky s přidáním zařízení Windows Autopilot](./media/enrollment-autopilot/autopilot-import-device2.png)

    >[!IMPORTANT]
    > When you use CSV upload to assign a user, make sure that you assign valid UPNs. If you assign an invalid UPN (incorrect username), your device may be inaccessible until you remove the invalid assignment. During CSV upload the only validation we perform on the **Assigned User** column is to check that the domain name is valid. We're unable to perform individual UPN validation to ensure that you're assigning an existing or correct user.

3. Pomocí **Importovat** zahajte import informací o zařízeních. Import může trvat několik minut.

4. After import is complete, choose **Device enrollment** > **Windows enrollment** > **Windows Autopilot** > **Devices** > **Sync**. A message displays that the synchronization is in progress. Dokončení procesu může trvat několik minut v závislosti na tom, kolik zařízení se synchronizuje.

5. Aktualizováním zobrazení zobrazte nová zařízení.

## <a name="create-an-autopilot-device-group"></a>Vytvořit skupinu zařízení Autopilot

1. In the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), choose **Groups** > **New group**.
2. V okně **Skupina**:
    1. Pro **Typ skupiny** zvolte **Zabezpečení**.
    2. Zadejte **Název skupiny** a **Popis skupiny**.
    3. Pro **Typ členství** zvolte buď **Přiřazené** nebo **Dynamické zařízení**.
3. Pokud jste v předchozím kroku pro **Typ členství** vybrali **Přiřazené**, potom v okně **Skupina** zvolte **Členové** a přidejte do skupiny zařízení Autopilot.
    Zařízení Autopilot, která ještě nejsou zaregistrovaná, jsou zařízení, jejichž název se rovná sériovému číslu zařízení.
4. Pokud jste výše pro **Typ členství** zvolili **Dynamické zařízení**, potom v okně **Skupina** zvolte **Členové s dynamickými zařízeními** a do pole **Pokročilé pravidlo** zadejte některý z následujících kódů. Only Autopilot devices are gathered by these rules, because they target attributes that are only possessed by Autopilot devices. Creating a group based off non-autopilot attributes won't guarantee that devices included in the group are actually registered to Autopilot.
    - If you want to create a group that includes all of your Autopilot devices, type: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Intune's group tag field maps to the OrderID attribute on Azure AD devices. If you want to create a group that includes all of your Autopilot devices with a specific group tag (the Azure AD device OrderID), you must type: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881")`
    - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení Autopilot s konkrétním ID nákupní objednávky, zadejte: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Po přidání kódu do pole **Pokročilé pravidlo** zvolte **Uložit**.
5. Zvolte **Vytvořit**.  

## <a name="create-an-autopilot-deployment-profile"></a>Vytvořit profil nasazení Autopilotu
Profily nasazení Autopilotu slouží ke konfiguraci zařízení s AutoPilotem. You can create up to 350 profiles per tenant.
1. In the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), choose **Device enrollment** > **Windows enrollment** > **Deployment Profiles** > **Create Profile**.
2. On the **Basics** page, type a **Name** and optional **Description**.

    ![Screenshot of Basics page](./media/enrollment-autopilot/create-profile-basics.png)

3. Pokud chcete, aby se všechna zařízení v přiřazených skupinách automaticky převedla na Autopilot, nastavte možnost **Převést všechna cílová zařízení na Autopilot** na **Ano**. All corporate owned, non-Autopilot devices in assigned groups will register with the Autopilot deployment service. Personally owned devices will not be converted to Autopilot. Vyřízení registrace trvá 48 hodin. Jakmile bude registrace zařízení zrušena a zařízení bude resetováno, Autopilot ho zaregistruje. Jakmile se zařízení tímto způsobem zaregistruje, nedojde zakázáním této možnosti ani odebráním přiřazení profilu k odebrání zařízení ze služby nasazení Autopilot. [Zařízení musíte odebrat přímo](enrollment-autopilot.md#delete-autopilot-devices).
4. Vyberte **Další**.
5. On the **Out-of-box experience (OOBE)** page, for **Deployment mode**, choose one of these two options:
    - **Řízení uživatelem**: Zařízení s tímto profilem se přidruží k uživateli, který zařízení registruje. Při registraci zařízení se musí zadat přihlašovací údaje uživatele.
    - **Self-deploying (preview)** : (requires Windows 10, version 1809 or later) Devices with this profile aren't associated with the user enrolling the device. Při registraci zařízení se nevyžadují přihlašovací údaje uživatele. When a device has no user associated with it, user-based compliance policies don't apply to it. When using self-deploying mode, only compliance policies targeting the device will be applied.

    ![Screenshot of OOBE page](./media/enrollment-autopilot/create-profile-outofbox.png)

6. V poli **Připojit k Azure AD jako** zvolte **Připojeno k Azure AD**.
7. Configure the following options:
    - **Licenční smlouva s koncovým uživatelem (EULA)** : (Windows 10 verze 1709 nebo novější) Vyberte, jestli se má uživatelům zobrazit EULA.
    - **Nastavení ochrany osobních údajů**: Vyberte, jestli se mají uživatelům zobrazit nastavení ochrany osobních údajů.
    >[!IMPORTANT]
    >The default value for the Diagnostic Data setting varies between Windows versions. For devices running Windows 10, version 1903, the default value is set to Full during the out-of-box experience. For more information, see [Windows Diagnostics Data](https://docs.microsoft.com/windows/privacy/windows-diagnostic-data) <br>
    
    - **Hide change account options (requires Windows 10, version 1809 or later)** : Choose **Hide** to prevent change account options from displaying on the company sign-in and domain error pages. Tato možnost vyžaduje, [aby v Azure Active Directory byla nakonfigurována funkce Branding společnosti](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding).
    - **Typ uživatelského účtu**: Vyberte typ účtu uživatele (**Správce** nebo **Standardní** uživatel). We allow the user joining the device to be a local Administrator by adding them to the local Admin group. We don't enable the user as the default administrator on the device.
    - **Allow White Glove OOBE** (requires Windows 10, version 1903 or later; [additional physical requirements](https://docs.microsoft.com/windows/deployment/windows-autopilot/white-glove#prerequisites)): Choose **Yes** to allow white glove support.
    - **Apply device name template** (requires Windows 10, version 1809 or later, and Azure AD join type): Choose **Yes** to create a template to use when naming a device during enrollment. Názvy musí být maximálně 15 znaků dlouhé a mohou obsahovat písmena, číslice a pomlčky. Nemohou být ale tvořené jen číslicemi. Pomocí [makra %SERIAL%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) můžete přidat sériové číslo specifické pro určitý hardware. Nebo můžete použít [makro %RAND:x%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp), které přidá náhodný řetězec číslic (x značí počet přidaných číslic). You can only provide a pre-fix for hybrid devices in a [domain join profile](windows-autopilot-hybrid.md#create-and-assign-a-domain-join-profile). 
    - **Jazyk (oblast)** \*: Zvolte jazyk, který chcete použít pro dané zařízení. Tato možnost je k dispozici, jen pokud jste si pro **Režim nasazení** zvolili **Nasazení sebou samým**.
    - **Automatically configure keyboard**\*: If a **Language (Region)** is selected, choose **Yes** to skip the keyboard selection page. Tato možnost je k dispozici, jen pokud jste si pro **Režim nasazení** zvolili **Nasazení sebou samým**.
8. Vyberte **Další**.
9. On the **Scope tags** page, optionally add the scope tags you want to apply to this profile. For more information about scope tags, see [Use role-based access control and scope tags for distributed IT](../fundamentals/scope-tags.md).
10. Vyberte **Další**.
11. On the **Assignments** page, choose **Selected groups** for **Assign to**.

    ![Screenshot of Assignments page](./media/enrollment-autopilot/create-profile-assignments.png)

12. Choose **Select groups to include**, and choose the groups you want to include in this profile.
13. If you want to exclude any groups, choose **Select groups to exclude**, and choose the groups you want to exclude.
14. Vyberte **Další**.
15. On the **Review + Create** page, choose **Create** to create the profile.

    ![Screenshot of Review page](./media/enrollment-autopilot/create-profile-review.png)

> [!NOTE]
> Intune will periodically check for new devices in the assigned groups, and then begin the process of assigning profiles to those devices. This process can take several minutes to complete. Before deploying a device, ensure that this process has completed.  You can check under **Device enrollment** > **Windows enrollment** > **Devices** where you should see the profile status change from "Unassigned" to "Assigning" and finally to "Assigned."

## <a name="edit-an-autopilot-deployment-profile"></a>Úprava profilu nasazení Autopilotu
Po vytvoření profilu nasazení Autopilotu můžete některé části profilu nasazení upravit.   

1. In the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), choose **Device enrollment**.
2. V části **Registrace zařízení s Windows** v části **Windows Autopilot** zvolte **Profily nasazení**.
3. Vyberte profil, který chcete upravit.
4. Pokud chcete změnit název nebo popis nasazení profilu, klikněte vlevo na **Vlastnosti**. Po provedení změn klikněte na **Uložit**.
5. Pokud chcete provést změny nastavení softwaru spuštěného při prvním zapnutí zařízení, klikněte na **Nastavení**. Po provedení změn klikněte na **Uložit**.

> [!NOTE]
> Změny profilu se použijí na zařízeních, která jsou přiřazena k tomuto profilu. Aktualizovaný profil se ale nepoužije na zařízení, které je už v Intune zaregistrované, dokud se zařízení neresetuje a znovu nezaregistruje.

## <a name="edit-autopilot-device-attributes"></a>Edit Autopilot device attributes
After you've uploaded an Autopilot device, you can edit certain attributes of the device.

1. In Intune in the Azure portal, choose **Device enrollment**.
2. Under **Windows enrollment**, in the **Windows Autopilot** section, choose **Devices**.
3. Select the device you want to edit.
4. In the pane on the right of the screen, you can edit the device name, group tag, or User Friendly Name (if you've assigned a user).
5. Vyberte **Uložit**.

> [!NOTE]
> Device names can be configured for all devices, but are ignored in Hybrid Azure AD joined deployments. Device name still comes from the domain join profile for Hybrid Azure AD devices.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Alerts for Windows Autopilot unassigned devices  <!-- 163236 -->  

Upozornění zobrazí, kolik zařízení programu Autopilot nemá profily nasazení Autopilotu. Na základě informací v upozornění můžete vytvořit profily a přiřadit je potřebným zařízením. Když na upozornění kliknete, zobrazí se úplný seznam zařízení Windows Autopilotu a podrobné informace o zařízeních.

Pokud chcete zobrazit upozornění na nepřiřazená zařízení, v [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Přehled** > **Nepřiřazená zařízení**.  

## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Přiřazení uživatele ke konkrétnímu zařízení Autopilot

K zařízení Autopilot můžete přiřadit uživatele. Díky přiřazení se během instalace systému Windows uživatel předem vyplní na přihlašovací stránce s [firemním brandingem](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) ze služby Azure Active Directory. Také můžete nastavit vlastní uvítací název. Ten se předem nevyplňuje, ani neupravuje přihlašování ve Windows. Způsobem popsaným níže lze přiřadit jen uživatele s licencí pro službu Intune.

Prerequisites: Azure Active Directory Company Portal has been configured and Windows 10, version 1809 or later.

1. In the [Microsoft Endpoint Manager Admin Center](https://go.microsoft.com/fwlink/?linkid=2109431), choose **Device enrollment** > **Windows enrollment** > **Devices** > choose the device > **Assign user**.

    ![Snímek obrazovky s možností Přiřadit uživatele](./media/enrollment-autopilot/assign-user.png)

2. Vyberte uživatele Azure s licencí pro používání služby Intune a zvolte **Vybrat**.

    ![Snímek obrazovky s vybraným uživatelem](./media/enrollment-autopilot/select-user.png)

3. V poli **Jednoduchý název** zadejte jednoduchý popisný název, nebo přijměte výchozí návrh. Tento řetězec je popisný název, který se zobrazí, když se uživatel přihlásí během instalace systému Windows.

    ![Snímek obrazovky s popisným názvem](./media/enrollment-autopilot/friendly-name.png)

4. Vyberte **OK**.

## <a name="autopilot-deployments-report"></a>Autopilot deployments report
You can see details on each device deployed through Windows Autopilot.
To see the report, go to **Intune** and, under **Monitor**, choose **Autopilot deployments**.
The data is available for 30 days after deployment.


## <a name="delete-autopilot-devices"></a>Odstranění zařízení Autopilot

You can delete Windows Autopilot devices that aren't enrolled into Intune:

- Delete the devices from Windows Autopilot at **Device enrollment** > **Windows enrollment** > **Devices**. Choose the devices you want to delete, then choose **Delete**. Windows Autopilot device deletion can take a few minutes to complete.

Completely removing a device from your tenant requires you to delete the Intune device, the Azure Active Directory device, and the Windows Autopilot device records. This can all be done from Intune:

1. If the devices are enrolled in Intune, you must first [delete them from the Intune All devices blade](../remote-actions/devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. Delete the devices in Azure Active Directory devices at **Devices** > **Azure AD devices**.

3. Delete the devices from Windows Autopilot at **Device enrollment** > **Windows enrollment** > **Devices**. Choose the devices you want to delete, then choose **Delete**. Windows Autopilot device deletion can take a few minutes to complete.

## <a name="using-autopilot-in-other-portals"></a>Použití Autopilotu na jiných portálech
Pokud nemáte zájem o správu mobilních zařízení, můžete Autopilot používat na jiných portálech. I když je používání na jiných portálech možné, doporučujeme ke správě nasazení Autopilotu používat jenom Intune. Pokud používáte Intune a jiný portál, nemůže Intune:  

- Zobrazit změny v profilech vytvořených v Intune, ale upravených na jiném portálu
- Synchronizovat profily vytvořené na jiném portálu
- Zobrazit změny v přiřazeních profilu provedených na jiném portálu
- Synchronizovat přiřazení profilu provedená na jiném portálu
- Zobrazit změny v seznamu zařízení, které byly provedeny na jiném portálu

## <a name="windows-autopilot-for-existing-devices"></a>Windows Autopilot pro existující zařízení

Zařízení s Windows můžete seskupit podle ID korelátoru, pokud se registrují s použitím [Autopilotu pro existující zařízení](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) v nástroji Configuration Manager. ID korelátoru je parametr konfiguračního souboru Autopilotu. [Atribut enrollmentProfileName zařízení služby Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#rules-for-devices) se automaticky nastaví tak, aby odpovídal nastavení OfflineAutopilotprofile-\<ID korelátoru\>. Umožní se tím, aby se vytvořily libovolné dynamické skupiny Azure AD na základě ID korelátoru pomocí atributu enrollmentprofileName.

>[!WARNING] 
> ID korelátoru není v Intune přednastavené, takže zařízení může ohlásit libovolné ID korelátoru. Pokud uživatel vytvoří ID korelátoru odpovídající názvu profilu Autopilot nebo Apple DEP, přidá se zařízení do libovolné dynamické skupiny Azure AD na základě atributu enrollmentProfileName. Pokud se chcete tomuto konfliktu vyhnout:
> - Vytvářejte pravidla dynamických skupin vždy tak, aby se porovnávala *celá* hodnota atributu enrollmentProfileName.
> - Nikdy nedávejte profilům Autopilot nebo Apple DEP název, který začíná textem „OfflineAutopilotprofile-“.

## <a name="next-steps"></a>Další kroky
Po konfiguraci Windows Autopilotu pro registrovaná zařízení s Windows 10 zjistěte, jak taková zařízení spravovat. Další informace najdete v článku [Co je správa zařízení v Microsoft Intune](../remote-actions/device-management.md).
