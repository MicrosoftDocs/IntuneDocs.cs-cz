---
title: Registrace zařízení pomocí Windows Autopilotu
titleSuffix: Microsoft Intune
description: Zjistěte, jak registrovat zařízení s Windows 10 pomocí Windows Autopilotu.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/5/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6e2fd0cadefbb1cbf90e6fc81a4ba32311b23d0f
ms.sourcegitcommit: 727c3ae7659ad79ea162250d234d7730f840c731
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/07/2019
ms.locfileid: "55842639"
---
# <a name="enroll-windows-devices-in-intune-by-using-the-windows-autopilot"></a>Registrace zařízení s Windows v Intune pomocí Windows Autopilot  
Windows Autopilot usnadňuje registraci zařízení v Intune. Vytváření a udržování přizpůsobených imagí operačního systému je proces, který zabere hodně času. Další čas můžete také strávit aplikováním těchto vlastních imagí operačního systému na nová zařízení, abyste je připravili k použití, než je předáte koncovým uživatelům. S Microsoft Intune a Autopilotem můžete nová zařízení koncovým uživatelům poskytovat, aniž by bylo nutné vlastní image operačního systému vytvářet, udržovat a aplikovat na zařízení. Když zařízení s Autopilotem spravujete pomocí Intune, můžete v zařízeních po registraci spravovat zásady, profily, aplikace a mnoho dalšího. Přehled výhod, scénáře a požadavky najdete v [přehledu Windows Autopilotu](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).


## <a name="prerequisites"></a>Požadavky
- [Povolená automatická registrace pro Windows](windows-enroll.md#enable-windows-10-automatic-enrollment)
- [Předplatné Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="how-to-get-the-csv-for-import-in-intune"></a>Jak získat sdílený svazek clusteru pro Import do služby Intune

Projděte si vysvětlující powershellovou rutinu, která vám poskytne další informace o tom, jak tuto funkci používat.

- [Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo/1.3/Content/Get-WindowsAutoPilotInfo.ps1)

## <a name="add-devices"></a>Přidání zařízení

Zařízení Windows Autopilot můžete přidat importováním souboru CSV s jejich informacemi.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Zařízení** > **Importovat**.

    ![Snímek obrazovky se zařízeními Windows Autopilot](media/enrollment-autopilot/autopilot-import-device.png)

2. V části **Přidat zařízení Windows AutoPilot** přejděte na soubor CSV se seznamem zařízení, která chcete přidat. Soubor by měl obsahovat sériová čísla, identifikátory produktů Windows, hodnoty hash hardwaru a volitelná ID objednávek zařízení.

    ![Snímek obrazovky s přidáním zařízení Windows Autopilot](media/enrollment-autopilot/autopilot-import-device2.png)

3. Pomocí **Importovat** zahajte import informací o zařízeních. Import může trvat několik minut.

4. Po dokončení importu vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Windows Autopilot** >  **Zařízení** > **Synchronizovat**. Zobrazí se zpráva, že synchronizace probíhá. Dokončení procesu může trvat několik minut v závislosti na tom, kolik zařízení se synchronizuje.

5. Aktualizováním zobrazení zobrazte nová zařízení.

## <a name="create-an-autopilot-device-group"></a>Vytvoření skupiny zařízení Autopilot

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Skupiny** > **Nová skupina**.
2. V okně **Skupina**:
    1. Pro **Typ skupiny** zvolte **Zabezpečení**.
    2. Zadejte **Název skupiny** a **Popis skupiny**.
    3. Pro **Typ členství** zvolte buď **Přiřazené** nebo **Dynamické zařízení**.
3. Pokud jste v předchozím kroku pro **Typ členství** vybrali **Přiřazené**, potom v okně **Skupina** zvolte **Členové** a přidejte do skupiny zařízení Autopilot.
    Zařízení Autopilot, která ještě nejsou zaregistrovaná, jsou zařízení, jejichž název se rovná sériovému číslu zařízení.
4. Pokud jste výše pro **Typ členství** zvolili **Dynamické zařízení**, potom v okně **Skupina** zvolte **Členové s dynamickými zařízeními** a do pole **Pokročilé pravidlo** zadejte některý z následujících kódů.
    - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení Autopilot, zadejte: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení Autopilot s konkrétním ID objednávky, zadejte: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení Autopilot s konkrétním ID nákupní objednávky, zadejte: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Po přidání kódu do pole **Pokročilé pravidlo** zvolte **Uložit**.
5. Zvolte **Vytvořit**.  

## <a name="create-an-autopilot-deployment-profile"></a>Vytvoření profilu nasazení Autopilotu
Profily nasazení Autopilotu slouží ke konfiguraci zařízení s AutoPilotem.
1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > **Vytvořit profil**.
2. Zadejte **název** a volitelný **popis**.
3. Pokud chcete, aby se všechna zařízení v přiřazených skupinách automaticky převedla na Autopilot, nastavte možnost **Převést všechna cílová zařízení na Autopilot** na **Ano**. Všechna zařízení v přiřazených skupinách bez Autopilotu se zaregistrují se službou nasazení Autopilot. Vyřízení registrace trvá 48 hodin. Jakmile bude registrace zařízení zrušena a zařízení bude resetováno, Autopilot ho zaregistruje. Jakmile se zařízení tímto způsobem zaregistruje, nedojde zakázáním této možnosti ani odebráním přiřazení profilu k odebrání zařízení ze služby nasazení Autopilot. [Zařízení musíte odebrat přímo](enrollment-autopilot.md#delete-autopilot-devices).
4. Pro **Režim nasazení** zvolte jednu z těchto dvou možností:
    - **User-driven**: Zařízení s tímto profilem se přidruží k uživateli, který zařízení registruje. Při registraci zařízení se musí zadat přihlašovací údaje uživatele.
    - **Místním nasazení (preview)**: (vyžaduje Windows 10, verze 1809 nebo novější) zařízení s tímto profilem nejsou přidruženy s uživatelem, registrace zařízení. Při registraci zařízení se nevyžadují přihlašovací údaje uživatele.
5. V poli **Připojit k Azure AD jako** zvolte **Připojeno k Azure AD**.
6. Vyberte **Software spouštěný při prvním zapnutí zařízení**, nakonfigurujte následující možnosti a pak zvolte **Uložit**:
    - **Jazyk (oblast)**\*: Zvolte jazyk, který chcete použít pro dané zařízení. Tato možnost je k dispozici, jen pokud jste si pro **Režim nasazení** zvolili **Nasazení sebou samým**.
    - **Automaticky nakonfigurovat klávesnici**\*: Pokud **jazyk (oblast)** je vybraná, zvolte **Ano** přeskočit stránka pro výběr klávesnice. Tato možnost je k dispozici, jen pokud jste si pro **Režim nasazení** zvolili **Nasazení sebou samým**.
    - **Licenční smlouva s koncovým uživatelem (EULA)**: (Windows 10 verze 1709 nebo novější) Zvolte, pokud chcete uživatelům zobrazit EULA.
    - **Nastavení ochrany osobních údajů**: Zvolte, pokud chcete zobrazit nastavení ochrany osobních údajů pro uživatele.
    - **Skrýt možnosti změnu účtu (vyžaduje Windows 10, verze 1809 nebo novější)**: Zvolte **skrýt** zabránit změnit možnosti účet ze zobrazení na stránkách společnosti přihlašovací jméno a doména chyby. Tato možnost vyžaduje, [aby v Azure Active Directory byla nakonfigurována funkce Branding společnosti](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding).
    - **Typ uživatelského účtu**: Zvolte typ účtu uživatele (**správce** nebo **standardní** uživatele).
    - **Použít šablonu název počítače (vyžaduje Windows 10, verze 1809 nebo novější)**: Zvolte **Ano** k vytvoření šablony pro použití při pojmenování zařízení během registrace. Názvy musí být maximálně 15 znaků dlouhé a mohou obsahovat písmena, číslice a pomlčky. Nemohou být ale tvořené jen číslicemi. Pomocí [makra %SERIAL%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp) můžete přidat sériové číslo specifické pro určitý hardware. Nebo můžete použít [makro %RAND:x%](https://docs.microsoft.com/windows/client-management/mdm/accounts-csp), které přidá náhodný řetězec číslic (x značí počet přidaných číslic). 

6. Výběrem možnosti **Vytvořit** vytvořte profil. Profil nasazení Autopilotu je teď možné přiřazovat zařízením.

* Oba **jazyk (oblast)** a **automaticky nakonfigurovat klávesnici** jsou k dispozici, pokud jste zvolili pouze **místním nasazení (preview)** pro **režim nasazení**  (vyžaduje Windows 10, verze 1809 nebo novější).


## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Přiřazení profilu nasazení Autopilotu ke skupině zařízení

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > vyberte profil.
2. V okně zvoleného profilu vyberte **Přiřazení**. 
3. Zvolte **Vybrat skupiny**, pak v okně **Vybrat skupiny** vyberte skupiny, ke kterým chcete přiřadit profil, a zvolte **Vybrat**.

> [!NOTE]
> Intune bude pravidelně kontrolovat nová zařízení v přiřazených skupin a potom zahájit proces přiřazení profilů zařízení. Tento proces může trvat několik minut. Před nasazením zařízení, ujistěte se, že tento proces dokončil.  Můžete zkontrolovat v části **registrace zařízení** > ** Registrace Windows ** > **zařízení** kam byste měli vidět stav profilu změnit z "Unassigned" na "Přiřazení" a nakonec na "Přiřazeno."

## <a name="edit-an-autopilot-deployment-profile"></a>Úprava profilu nasazení Autopilotu
Po vytvoření profilu nasazení Autopilotu můžete některé části profilu nasazení upravit.   

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení**.
2. V části **Registrace zařízení s Windows** v části **Windows Autopilot** zvolte **Profily nasazení**.
3. Vyberte profil, který chcete upravit.
4. Pokud chcete změnit název nebo popis nasazení profilu, klikněte vlevo na **Vlastnosti**. Po provedení změn klikněte na **Uložit**.
5. Pokud chcete provést změny nastavení softwaru spuštěného při prvním zapnutí zařízení, klikněte na **Nastavení**. Po provedení změn klikněte na **Uložit**.

> [!NOTE]
> Změny profilu se použijí na zařízeních, která jsou přiřazena k tomuto profilu. Aktualizovaný profil se ale nepoužije na zařízení, které je už v Intune zaregistrované, dokud se zařízení neresetuje a znovu nezaregistruje.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Upozornění na zařízení, která nemají přiřazený Windows Autopilot <!-- 163236 -->  

Upozornění zobrazí, kolik zařízení programu Autopilot nemá profily nasazení Autopilotu. Na základě informací v upozornění můžete vytvořit profily a přiřadit je potřebným zařízením. Když na upozornění kliknete, zobrazí se úplný seznam zařízení Windows Autopilotu a podrobné informace o zařízeních.


Pokud chcete zobrazit upozornění na nepřiřazená zařízení, v [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Přehled** > **Nepřiřazená zařízení**.  


## <a name="assign-a-user-to-a-specific-autopilot-device"></a>Přiřazení uživatele ke konkrétnímu zařízení Autopilot

K zařízení Autopilot můžete přiřadit uživatele. Díky přiřazení se během instalace systému Windows uživatel předem vyplní na přihlašovací stránce s [firemním brandingem](https://docs.microsoft.com/azure/active-directory/fundamentals/customize-branding) ze služby Azure Active Directory. Také můžete nastavit vlastní uvítací název. Ten se předem nevyplňuje, ani neupravuje přihlašování ve Windows. Způsobem popsaným níže lze přiřadit jen uživatele s licencí pro službu Intune.

Požadavky: Portál Azure Active Directory společnosti byl nakonfigurován a Windows 10, verze 1809 nebo novější.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Zařízení** > zvolte zařízení > **Přiřadit uživatele**.

    ![Snímek obrazovky s možností Přiřadit uživatele](media/enrollment-autopilot/assign-user.png)

2. Vyberte uživatele Azure s licencí pro používání služby Intune a zvolte **Vybrat**.

    ![Snímek obrazovky s vybraným uživatelem](media/enrollment-autopilot/select-user.png)

3. V poli **Jednoduchý název** zadejte jednoduchý popisný název, nebo přijměte výchozí návrh. Tento řetězec je popisný název, který se zobrazí, když se uživatel přihlásí během instalace systému Windows.

    ![Snímek obrazovky s popisným názvem](media/enrollment-autopilot/friendly-name.png)

4. Vyberte **OK**.


## <a name="delete-autopilot-devices"></a>Odstranění zařízení Autopilot

Zařízení Windows Autopilot, která nejsou zaregistrovaná, můžete odstranit.

1. Pokud jsou zařízení registrována v Intune, musíte je nejdřív [odstranit z portálu služby Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal), vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Zařízení**.

3. V části **Zařízení Windows Autopilot** vyberte zařízení, která chcete odstranit, a pak vyberte **Odstranit**.

4. Potvrďte odstranění pomocí **Ano**. Odstranění může trvat několik minut.

## <a name="using-autopilot-in-other-portals"></a>Použití Autopilotu na jiných portálech
Pokud nemáte zájem o správu mobilních zařízení, můžete Autopilot používat na jiných portálech. I když je používání na jiných portálech možné, doporučujeme ke správě nasazení Autopilotu používat jenom Intune. Pokud používáte Intune a jiný portál, nemůže Intune:  

- Zobrazit změny v profilech vytvořených v Intune, ale upravených na jiném portálu
- Synchronizovat profily vytvořené na jiném portálu
- Zobrazit změny v přiřazeních profilu provedených na jiném portálu
- Synchronizovat přiřazení profilu provedená na jiném portálu
- Zobrazit změny v seznamu zařízení, které byly provedeny na jiném portálu

## <a name="windows-autopilot-for-existing-devices"></a>Windows Autopilot pro existující zařízení

Zařízení s Windows můžete seskupit podle ID korelátoru, pokud se registrují s použitím [Autopilotu pro existující zařízení](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/New-Windows-Autopilot-capabilities-and-expanded-partner-support/ba-p/260430) v nástroji Configuration Manager. ID korelátoru je parametr konfiguračního souboru Autopilotu. [Atribut enrollmentProfileName zařízení služby Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership#using-attributes-to-create-rules-for-device-objects) se automaticky nastaví tak, aby odpovídal nastavení OfflineAutopilotprofile-\<ID korelátoru\>. Umožní se tím, aby se vytvořily libovolné dynamické skupiny Azure AD na základě ID korelátoru pomocí atributu enrollmentprofileName.

>[!WARNING] 
> ID korelátoru není v Intune přednastavené, takže zařízení může ohlásit libovolné ID korelátoru. Pokud uživatel vytvoří ID korelátoru odpovídající názvu profilu Autopilot nebo Apple DEP, přidá se zařízení do libovolné dynamické skupiny Azure AD na základě atributu enrollmentProfileName. Pokud se chcete tomuto konfliktu vyhnout:
> - Vytvářejte pravidla dynamických skupin vždy tak, aby se porovnávala *celá* hodnota atributu enrollmentProfileName.
> - Nikdy nedávejte profilům Autopilot nebo Apple DEP název, který začíná textem „OfflineAutopilotprofile-“.

## <a name="next-steps"></a>Další postup
Po konfiguraci Windows Autopilotu pro registrovaná zařízení s Windows 10 zjistěte, jak taková zařízení spravovat. Další informace najdete v článku [Co je správa zařízení v Microsoft Intune](https://docs.microsoft.com/intune/device-management).
