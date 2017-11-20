---
title: "Registrace zařízení s Windows pomocí programu Windows AutoPilot Deployment"
description: "Zjistěte, jak registrovat nová zařízení s Windows 10 pomocí programu Windows AutoPilot Deployment."
keywords: 
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a2dc5594-a373-48dc-ba3d-27aff0c3f944
ms.openlocfilehash: 736eda24e355024e2abadd57206c0f0423e6d4b4
ms.sourcegitcommit: af958afce3070a3044aafea490c8afc55301d9df
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="enroll-windows-devices-using-windows-autopilot-deployment-program"></a>Registrace zařízení s Windows pomocí programu Windows AutoPilot Deployment
Program Windows AutoPilot Deployment zjednodušuje zřizování zařízení. Vytváření a udržování přizpůsobených imagí operačního systému dnes zabírá hodně času. Mnoho času můžete také strávit aplikováním těchto vlastních imagí operačního systému na nová zařízení, abyste je připravili k použití, než je předáte koncovým uživatelům. S Microsoft Intune a AutoPilotem můžete nová zařízení koncovým uživatelům poskytovat, aniž by bylo nutné vlastní image operačního systému vytvářet, udržovat a aplikovat na zařízení. Když zařízení s AutoPilotem spravujete pomocí Intune, můžete v zařízeních po registraci spravovat zásady, profily, aplikace atd. Přehled výhod, scénáře a požadavky najdete v [přehledu Windows AutoPilotu](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot).

## <a name="prerequisites"></a>Požadavky
- [Zařízení musí být zaregistrovaná pro vaši organizaci](https://docs.microsoft.com/windows/deployment/windows-10-auto-pilot#registering-devices-to-your-organization)
- [Povolená automatická registrace pro Windows](https://docs.microsoft.com/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune#enable-windows-10-automatic-enrollment)
- [Předplatné Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->

## <a name="synchronize-devices"></a>Synchronizace zařízení
Synchronizujte registrovaná zařízení do Intune, abyste je mohli nakonfigurovat.

1. Přihlaste se k [Azure](https://portal.azure.com/).
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Registrace zařízení**.
4. V okně **Registrace zařízení s Windows** v sekci **Program Windows AutoPilot Deployment** zvolte **Zařízení**.
5. Kliknutím na **Synchronizovat** importujte zaregistrovaná zařízení. Zobrazí se zpráva, že synchronizace probíhá.
6. Aktualizováním zobrazení zobrazte nová zařízení. Dokončení procesu může trvat několik minut v závislosti na tom, kolik zařízení se synchronizuje.  

## <a name="create-an-autopilot-deployment-profile"></a>Vytvoření profilu nasazení AutoPilotu
Profily nasazení AutoPilotu slouží ke konfiguraci zařízení s AutoPilotem.
1. Přihlaste se k [Azure](https://portal.azure.com/). 
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Registrace zařízení**.
4. V okně **Registrace zařízení s Windows** v sekci **Program Windows AutoPilot Deployment** zvolte **Profily nasazení**.
5. Klikněte na **Vytvořit profil**a zvolte název a volitelný popis. 
6. Jako **Typ spojení** vyberte **Připojeno k Azure AD**.
7. Pro **Software spuštěný při prvním zapnutí zařízení** nakonfigurujte následující možnosti a pak klikněte na **OK**: 
   - **Nastavení ochrany osobních údajů**: vyberte, jestli se mají uživatelům zobrazit nastavení ochrany osobních údajů. 
   - **Licenční smlouva s koncovým uživatelem (EULA)**: vyberte, jestli se má uživatelům zobrazit EULA.
   - **Typ uživatelského účtu**: vyberte, jestli je typ účtu uživatele **Správce** nebo **Standardní** uživatel.

     > [!Note]    
     > Toto nastavení se nevztahuje na účty Globální správce ani Správce společnosti. Tyto účty nemůžou být standardními uživateli, protože mají přístup ke všem funkcím pro správu v Azure AD.
8. Kliknutím na **Vytvořit** vytvořte profil. Profil nasazení AutoPilotu je teď možné přiřazovat zařízením.
     
> [!Note]    
> Ve všech profilech nasazení AutoPilotu jsou nakonfigurovaná tato nastavení:
> - Přeskočení stránek nastavení registrace Cortana, OneDrive a OEM
> - Automatické nastavení pro práci nebo školu
> - Prostředí pro přihlašování se značkou společnosti nebo školy    

## <a name="alerts-for-windows-autopilot-unassigned-devices-----163236---"></a>Upozornění na zařízení, která nemají přiřazený Windows AutoPilot <!-- 163236 -->
Z upozornění můžete zjistit, kolik zařízení z programu AutoPilot nemá přiřazené profily nasazení AutoPilotu. Na základě informací v upozornění můžete vytvořit profily a přiřadit je potřebným zařízením. Když na upozornění kliknete, zobrazí se úplný seznam zařízení Windows AutoPilotu a podrobné informace o zařízeních. 
1. Přihlaste se k [Azure](https://portal.azure.com/). 
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Registrace zařízení**.
4. Zvolte **Přehled** a uvidíte upozornění. Klikněte na upozornění a uvidíte seznam zařízení AutoPilotu.  

## <a name="assign-an-autopilot-deployment-profile"></a>Přiřazení profilu nasazení AutoPilotu
Po vytvoření profilů nasazení AutoPilotu je můžete přiřadit vybraným zařízením.

1. Přihlaste se k [Azure](https://portal.azure.com/). 
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Registrace zařízení**.
4. V okně **Registrace zařízení s Windows** v sekci **Program Windows AutoPilot Deployment** zvolte **Zařízení**.
5. Vyberte zařízení, kterým chcete profil nasazení přiřadit. Zařízení bez přiřazeného profilu snadno najdete pomocí filtrování ve sloupci **Stav**. 
6. Klikněte na **Přiřadit profil**, vyberte profil nasazení AutoPilotu a pak klikněte na **Přiřadit**. Zobrazí se zpráva, že přiřazování probíhá.
7. Aktualizováním zobrazení zobrazíte, že byl profil zařízením přiřazen. Dokončení procesu může trvat několik minut v závislosti na tom, kolik zařízení jste vybrali. 

> [!Note]
> Nový profil se přiřadí zařízení. Profil se ale nepoužije na zařízení, která jsou už v Intune zaregistrovaná, dokud se zařízení neresetuje a znovu nezaregistruje.

### <a name="assign-a-different-autopilot-deployment-profile"></a>Přiřazení jiného profilu nasazení AutoPilotu
Pokud se po přiřazení profilu nasazení AutoPilotu rozhodnete přiřadit zařízení jiný profil, přiřaďte mu nový profil.  

## <a name="edit-an-autopilot-deployment-profile"></a>Úprava profilu nasazení AutoPilotu 
Po vytvoření profilu nasazení AutoPilotu můžete některé části profilu nasazení upravit.   
1. Přihlaste se k [Azure](https://portal.azure.com/). 
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Registrace zařízení**.
4. V okně **Registrace zařízení s Windows** v sekci **Program Windows AutoPilot Deployment** zvolte **Profily nasazení**. 
5. Vyberte profil, který chcete upravit. 
6. Pokud chcete změnit název nebo popis nasazení profilu, klikněte vlevo na **Vlastnosti**. Po provedení změn klikněte na **Uložit**. 
7. Pokud chcete provést změny nastavení softwaru spuštěného při prvním zapnutí zařízení, klikněte na **Nastavení**. Po provedení změn klikněte na **Uložit**. 

> [!NOTE]
> Aktualizovaný profil se přiřadí zařízením. Aktualizovaný profil se ale nepoužije na zařízení, které je už v Intune zaregistrované, dokud se zařízení neresetuje a znovu nezaregistruje. 

## <a name="using-autopilot-in-other-portals"></a>Použití AutoPilotu na jiných portálech
Pokud nemáte zájem o správu mobilních zařízení, máte možnost AutoPilot používat třeba v Microsoft Storu pro firmy. I když je používání na jiných portálech možné, doporučujeme ke správě nasazení AutoPilotu používat jenom Intune. Pokud používáte Intune a jiný portál, nemůže Intune:
- Zobrazit změny v profilech vytvořených v Intune, ale upravených na jiném portálu
- Synchronizovat profily vytvořené na jiném portálu
- Zobrazit změny v přiřazeních profilu provedených na jiném portálu
- Synchronizovat přiřazení profilu provedená na jiném portálu

## <a name="next-steps"></a>Další kroky
Po konfiguraci Windows AutoPilotu pro registrovaná zařízení s Windows 10 zjistěte, jak taková zařízení spravovat. Podrobnosti najdete v článku [Co je správa zařízení v Microsoft Intune?](https://docs.microsoft.com/intune/device-management)