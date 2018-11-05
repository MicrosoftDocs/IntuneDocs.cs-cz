---
title: 'Kurz: Použití Autopilotu k registraci zařízení v Intune'
titleSuffix: Microsoft Intune
description: V tomto kurzu nastavíte Windows Autopilot pro registraci zařízení v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/19/2018
ms.topic: tutorial
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
Customer intent: As an Intune admin, I want to set up Windows Autopilot so that users can enroll in Intune.
ms.openlocfilehash: a90f53bfc5841cc0f773751e7df917d8fc8b6cf8
ms.sourcegitcommit: cff65435df070940da390609d6376af6ccdf0140
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2018
ms.locfileid: "49431912"
---
# <a name="tutorial-use-autopilot-to-enroll-windows-devices-in-intune"></a>Kurz: Použití Autopilotu k registraci zařízení s Windows v Intune
Windows Autopilot zjednodušuje registraci zařízení. S Microsoft Intune a Autopilotem můžete nová zařízení koncovým uživatelům poskytovat, aniž by bylo nutné vlastní image operačního systému vytvářet, udržovat a aplikovat. 

V tomto kurzu se naučíte:
> [!div class="checklist"]
> * Přidat zařízení do Intune
> * Vytvořit skupinu zařízení Autopilot
> * Vytvořit profil nasazení Autopilotu
> * Přiřadit profil nasazení Autopilotu ke skupině zařízení
> * Distribuovat zařízení s Windows uživatelům

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

Přehled výhod, scénáře a požadavky Autopilotu najdete v [přehledu Windows Autopilotu](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot).


## <a name="prerequisites"></a>Požadavky
- [Nastavení automatické registrace Windows](quickstart-setup-auto-enrollment.md)
- [Předplatné Azure Active Directory Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) <!--&#40;[trial subscription](http://go.microsoft.com/fwlink/?LinkID=816845)&#41;-->


## <a name="add-devices"></a>Přidání zařízení

Prvním krokem při nastavení Windows Autopilotu je přidání zařízení s Windows do Intune. Nemusíte dělat nic více, než vytvořit soubor CSV a naimportovat ho do Intune.

1. V libovolném textovém editoru vytvořte seznam hodnot oddělených čárkami (CSV), které identifikují zařízení s Windows. Použijte tento formát:
    
    *sériové_číslo*, *ID_produktu_windows*, *hodnota_hash_hardwaru*, *volitelné_ID_pořadí*
    
    První tři položky jsou povinné, ale ID pořadí je volitelné.

2. Soubor CSV uložte.

3. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Zařízení** > **Importovat**.

    ![Snímek obrazovky se zařízeními Windows Autopilot](media/enrollment-autopilot/autopilot-import-device.png)

4. V části **Přidat zařízení Windows Autopilot** vyhledejte uložený soubor CSV.

    ![Snímek obrazovky s přidáním zařízení Windows Autopilot](media/enrollment-autopilot/autopilot-import-device2.png)

5. Pomocí **Importovat** zahajte import informací o zařízeních. Import může trvat několik minut.

4. Po dokončení importu vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Windows Autopilot** >  **Zařízení** > **Synchronizovat**. Zobrazí se zpráva, že synchronizace probíhá. Dokončení procesu může trvat několik minut v závislosti na tom, kolik zařízení synchronizujete.

5. Aktualizováním zobrazení zobrazte nová zařízení.

## <a name="create-an-autopilot-device-group"></a>Vytvoření skupiny zařízení Autopilot

Dále vytvořte skupinu zařízení a přidejte do ní zařízení Autopilot, která jste právě načetli.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) zvolte **Skupiny** > **Nová skupina**.
2. V okně **Skupina**:
    1. Pro **Typ skupiny** zvolte **Zabezpečení**.
    2. Jako **Název skupiny** zadejte *Skupina Autopilot*. Jako **Popis skupiny** zadejte *Testovací skupina pro zařízení Autopilot*.
    3. Pro **Typ členství** zvolte **Přiřazeno**.
3. V okně **Skupina** zvolte **Členové** a do skupiny přidejte zařízení Autopilot. Zařízení Autopilot, která ještě nejsou zaregistrovaná, jsou zařízení, jejichž název se rovná sériovému číslu zařízení.
4. Zvolte **Vytvořit**.  

## <a name="create-an-autopilot-deployment-profile"></a>Vytvoření profilu nasazení Autopilotu

Po vytvoření skupiny zařízení musíte vytvořit profil nasazení, abyste mohli zařízení Autopilot nakonfigurovat.

1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > **Vytvořit profil**.
2. Jako **Název** zadejte *Profil Autopilot*. Jako **Popis skupiny** zadejte *Testovací profil pro zařízení Autopilot*.
3. Nastavte možnost **Převést všechna cílová zařízení na Autopilot** na **Ano**. Toto nastavení zajistí, že všechna zařízení v seznamu se zaregistrují pomocí služby nasazení Autopilot. Vyřízení registrace trvá 48 hodin.
4. Jako **Režim nasazení** zvolte **Řízení uživatelem**. Zařízení s tímto profilem se přidruží k uživateli, který zařízení registruje. Při registraci zařízení se musí zadat přihlašovací údaje uživatele.
5. V poli **Připojit k Azure AD jako** zvolte **Připojeno k Azure AD**.
6. Vyberte **Software spouštěný při prvním zapnutí zařízení** a nakonfigurujte následující možnosti. Ostatní možnosti ponechejte ve výchozím nastavení a potom zvolte **Uložit**:
    - **Licenční smlouva s koncovým uživatelem (EULA)**: **Skrýt**
    - **Nastavení ochrany osobních údajů**: **Zobrazit**
    - **Typ uživatelského účtu**: **Standard**

6. Výběrem možnosti **Vytvořit** vytvořte profil. Profil nasazení Autopilotu je teď možné přiřazovat zařízením.

## <a name="assign-an-autopilot-deployment-profile-to-a-device-group"></a>Přiřazení profilu nasazení Autopilotu ke skupině zařízení

Teď, když máte vytvořený profil nasazení, můžete ho přiřadit ke skupině zařízení.
1. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal) vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Profily nasazení** > vyberte profil.
2. V okně zvoleného profilu vyberte **Přiřazení**. 
3. Zvolte **Vybrat skupiny**, v okně **Vybrat skupiny** zvolte **Skupina Autopilot** a zvolte **Vybrat**.

## <a name="distribute-devices-to-users"></a>Distribuce zařízení uživatelům

Nyní můžete distribuovat zařízení s Windows uživatelům. Při prvním přihlášení systém Autopilot automaticky zařízení zaregistruje a nakonfiguruje. 

## <a name="clean-up-resources"></a>Vyčištění prostředků

Pokud už nechcete zařízení Autopilot dále používat, můžete je odstranit.

1. Pokud jsou zařízení registrována v Intune, musíte je nejdřív [odstranit z portálu služby Azure Active Directory](devices-wipe.md#delete-devices-from-the-azure-active-directory-portal).

2. V [Intune na portálu Azure Portal](https://aka.ms/intuneportal), vyberte **Registrace zařízení** > **Registrace zařízení s Windows** > **Zařízení**.

3. V části **Zařízení Windows Autopilot** vyberte zařízení, která chcete odstranit, a pak vyberte **Odstranit**.

4. Potvrďte odstranění pomocí **Ano**. Odstranění může trvat několik minut.

## <a name="next-steps"></a>Další kroky

Můžete si přečíst další informace o dalších možnostech dostupných pro Windows Autopilot.

> [!div class="nextstepaction"]
> [Článek s podrobnými informacemi o registraci pomocí Autopilotu](enrollment-autopilot.md)

