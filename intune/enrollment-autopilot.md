---
title: Registrace zařízení pomocí Windows AutoPilotu
titleSuffix: Microsoft Intune
description: Zjistěte, jak registrovat zařízení s Windows 10 pomocí Windows AutoPilotu.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: b3c374e4ce6baeab8cc6fde3f6c45c63c48e34dd
ms.sourcegitcommit: d99def6e4ceb44f3e7ca10fe7cdd7f222cf814c8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/24/2018
ms.locfileid: "42903071"
---
# <a name="enroll-windows-devices-by-using-the-windows-autopilot"></a>Registrace zařízení s Windows pomocí Windows AutoPilotu
Windows AutoPilot zjednodušuje zřizování zařízení. Vytváření a udržování přizpůsobených imagí operačního systému je proces, který zabere hodně času. Další čas můžete také strávit aplikováním těchto vlastních imagí operačního systému na nová zařízení, abyste je připravili k použití, než je předáte koncovým uživatelům. S Microsoft Intune a AutoPilotem můžete nová zařízení koncovým uživatelům poskytovat, aniž by bylo nutné vlastní image operačního systému vytvářet, udržovat a aplikovat na zařízení. Když zařízení s AutoPilotem spravujete pomocí Intune, můžete v zařízeních po registraci spravovat zásady, profily, aplikace a mnoho dalšího. Přehled výhod, scénáře a požadavky najdete v [přehledu Windows AutoPilotu](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).

## <a name="prerequisites"></a>Požadavky
- [Povolená automatická registrace pro Windows](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Předplatné Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="add-devices"></a>Přidání zařízení

Zařízení Windows AutoPilot můžete přidat importováním souboru CSV s jejich informace.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Zařízení** > **Importovat**.

    ![Snímek obrazovky se zařízeními Windows AutoPilot](media/enrollment-autopilot/autopilot-import-device.png)

2. V části **Přidat zařízení Windows AutoPilot** přejděte na soubor CSV se seznamem zařízení, která chcete přidat. Soubor by měl obsahovat sériová čísla, identifikátory produktů Windows, hodnoty hash hardwaru a volitelná ID objednávek zařízení.

    ![Snímek obrazovky s přidáním zařízení Windows AutoPilot](media/enrollment-autopilot/autopilot-import-device2.png)

3. Pomocí **Importovat** zahajte import informací o zařízeních. Import může trvat několik minut.

4. Po dokončení importu vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Windows AutoPilot** >  **Zařízení** > **Synchronizovat**. Zobrazí se zpráva, že synchronizace probíhá. Dokončení procesu může trvat několik minut v závislosti na tom, kolik zařízení se synchronizuje.

5. Aktualizováním zobrazení zobrazte nová zařízení.

## <a name="create-an-autopilot-device-group"></a>Vytvoření skupiny zařízení AutoPilot

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Skupiny**.
2. V okně **Skupina**:
    1. Pro **Typ skupiny** zvolte **Zabezpečení**.
    2. Zadejte **Název skupiny** a **Popis skupiny**.
    3. Pro **Typ členství** zvolte buď **Přiřazené** nebo **Dynamické zařízení**.
3. Pokud jste v předchozím kroku pro **Typ členství** vybrali **Přiřazené**, potom v okně **Skupina** zvolte **Členové** a přidejte do skupiny zařízení AutoPilot.
    Zařízení AutoPilot, která ještě nejsou zaregistrovaná, jsou zařízení, jejich název se rovná sériovému číslu zařízení.
4. Pokud jste výše pro **Typ členství** zvolili **Dynamické zařízení**, potom v okně **Skupina** zvolte **Členové s dynamickými zařízeními** a do pole **Pokročilé pravidlo** zadejte některý z následujících kódů.
    - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení AutoPilot, zadejte: `(device.devicePhysicalIDs -any _ -contains "[ZTDId]")`
    - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení AutoPilot s konkrétním ID objednávky, zadejte: `(device.devicePhysicalIds -any _ -eq "[OrderID]:179887111881") `
    - Pokud chcete vytvořit skupinu, která obsahuje všechna vaše zařízení AutoPilot s konkrétním ID nákupní objednávky, zadejte: `(device.devicePhysicalIds -any _ -eq "[PurchaseOrderId]:76222342342")`
    
    Po přidání kódu do pole **Pokročilé pravidlo** zvolte **Uložit**.
5. Zvolte **Vytvořit**.



## <a name="create-an-autopilot-deployment-profile"></a>Vytvoření profilu nasazení AutoPilotu
Profily nasazení AutoPilotu slouží ke konfiguraci zařízení s AutoPilotem.
1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > **Vytvořit profil**.
2. Zadejte **název** a volitelný **popis**.
3. Pro **Režim nasazení** zvolte jednu z těchto dvou možností:
    - **Řízení uživatelem**: Zařízení s tímto profilem se přidruží k uživateli, který zařízení registruje. Při zřizování zařízení se musí zadat přihlašovací údaje uživatele.
    - **Nasazení sebou samým (Preview)**: (sestavení Windows 10 Insider Preview 17672 nebo novější) Zařízení s tímto profilem nejsou přidružená k uživateli, který je registruje. Při zřizování zařízení se nevyžadují přihlašovací údaje uživatele.
4. V poli **Připojit k Azure AD jako** zvolte **Připojeno k Azure AD**.
5. Vyberte **Software spouštěný při prvním zapnutí zařízení**, nakonfigurujte následující možnosti a pak zvolte **Uložit**:
    - **Jazyk (oblast)**\*: Zvolte jazyk, který chcete použít pro dané zařízení. Tato možnost je k dispozici, jen pokud jste si pro **Režim nasazení** zvolili **Nasazení sebou samým**.
    - **Automaticky nakonfigurovat klávesnici**\*: Pokud je vybrána možnost **Jazyk (oblast)**, přeskočte stránku pro výběr klávesnice. Tato možnost je k dispozici, jen pokud jste si pro **Režim nasazení** zvolili **Nasazení sebou samým**.
    - **Licenční smlouva s koncovým uživatelem (EULA)**: (Windows 10 verze 1709 nebo novější) Vyberte, jestli se má uživatelům zobrazit EULA.
    - **Nastavení ochrany osobních údajů**: Vyberte, jestli se mají nebo nemají uživatelům zobrazit nastavení ochrany osobních údajů.
    - **Typ uživatelského účtu**: Vyberte, jestli je typ účtu uživatele **správce** nebo **standardní** uživatel. 

6. Výběrem možnosti **Vytvořit** vytvořte profil. Profil nasazení AutoPilotu je teď možné přiřazovat zařízením.

*Možnosti **Jazyk (oblast)** a **Automaticky nakonfigurovat klávesnici** jsou k dispozici, jen pokud jste si pro **Režim nasazení** zvolili **Nasazení sebou samým (Preview)** (sestavení Windows 10 Insider Preview 17672 nebo novější).


## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Přiřazení profilu nasazení AutoPilotu ke skupině zařízení

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > vyberte profil.
2. V okně zvoleného profilu vyberte **Přiřazení**. 
3. Zvolte **Vybrat skupiny**, pak v okně **Vybrat skupiny** vyberte skupiny, ke kterým chcete přiřadit profil, a zvolte **Vybrat**.

## <a name="edit-an-autopilot-deployment-profile"></a>Úprava profilu nasazení AutoPilotu
Po vytvoření profilu nasazení AutoPilotu můžete některé části profilu nasazení upravit.   

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení**.
2. V části **Registrace zařízení s Windows** v sekci **Windows AutoPilot** zvolte **Profily nasazení**.
3. Vyberte profil, který chcete upravit.
4. Pokud chcete změnit název nebo popis nasazení profilu, klikněte vlevo na **Vlastnosti**. Po provedení změn klikněte na **Uložit**.
5. Pokud chcete provést změny nastavení softwaru spuštěného při prvním zapnutí zařízení, klikněte na **Nastavení**. Po provedení změn klikněte na **Uložit**.

> [!NOTE]
> Změny profilu se použijí na zařízeních, která jsou přiřazena k tomuto profilu. Aktualizovaný profil se ale nepoužije na zařízení, které je už v Intune zaregistrované, dokud se zařízení neresetuje a znovu nezaregistruje.

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Upozornění na zařízení, která nemají přiřazený Windows AutoPilot <!-- 163236 -->
Může se vám zobrazit upozornění oznamující, kolik zařízení z programu AutoPilot nemá přiřazené profily nasazení AutoPilotu. Na základě informací v upozornění můžete vytvořit profily a přiřadit je potřebným zařízením. Když na upozornění kliknete, zobrazí se úplný seznam zařízení Windows AutoPilotu a podrobné informace o zařízeních.

Pokud chcete zobrazit upozornění na nepřiřazená zařízení, v [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Registrace zařízení** > **Přehled** > **Nepřiřazená zařízení**.  

## <a name="delete-autopilot-devices"></a>Odstranění zařízení AutoPilot

Zařízení Windows AutoPilot, která nejsou zaregistrovaná, můžete odstranit.

1. Pokud jsou zařízení registrována v Intune, musíte je nejdřív [odstranit z portálu služby Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal), vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Zařízení**.

3. V části **Zařízení Windows AutoPilot** vyberte zařízení, která chcete odstranit, a pak vyberte **Odstranit**.

4. Potvrďte odstranění pomocí **Ano**. Odstranění může trvat několik minut.

## <a name="using-autopilot-in-other-portals"></a>Použití AutoPilotu na jiných portálech
Pokud nemáte zájem o správu mobilních zařízení, můžete AutoPilot používat třeba v Microsoft Storu pro firmy. I když je používání na jiných portálech možné, doporučujeme ke správě nasazení AutoPilotu používat jenom Intune. Pokud používáte Intune a jiný portál, nemůže Intune:
- Zobrazit změny v profilech vytvořených v Intune, ale upravených na jiném portálu
- Synchronizovat profily vytvořené na jiném portálu
- Zobrazit změny v přiřazeních profilu provedených na jiném portálu
- Synchronizovat přiřazení profilu provedená na jiném portálu
- Zobrazit změny v seznamu zařízení, které byly provedeny na jiném portálu

## <a name="next-steps"></a>Další kroky
Po konfiguraci Windows AutoPilotu pro registrovaná zařízení s Windows 10 zjistěte, jak taková zařízení spravovat. Další informace najdete v článku [Co je správa zařízení v Microsoft Intune](https://docs.microsoft.com/intune/device-management).
