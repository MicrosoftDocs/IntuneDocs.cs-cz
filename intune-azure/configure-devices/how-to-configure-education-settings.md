---
title: "Konfigurace nastavení vzdělávání Intune pro Windows 10"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se pomocí služby Intune nakonfigurovat nastavení vzdělávání pro Windows 10 na zařízení, která spravujete."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: e5dd7cb5b320df7f443b52a1b502027fa3c4acaf
ms.openlocfilehash: d3fdf8884a0b7c035cde89da930ef74172b76873
ms.lasthandoff: 04/19/2017


---

# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Konfigurace nastavení vzdělávání pro Windows 10 ve službě Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Vzdělávací profily vám umožňují určit podrobnosti, které nakonfigurují aplikaci Windows Zkuste si test, včetně podrobností účtu a adresy URL testu. Jakmile bude konfigurace hotová, otevře se aplikace Zkuste si test s vámi určeným testem a žádná jiná aplikace nepůjde na zařízení spustit, dokud se test nedokončí.

Informace v tomto tématu vás seznámí se základy konfigurace profilů omezení zařízení. Pak si můžete přečíst další témata pro jednotlivé platformy, kde najdete podrobnosti o specifikách různých zařízení.

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení vzdělávacího profilu

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
3. V okně profilů zvolte **Vytvořit profil**.
4. V okně **Vytvořit profil** zadejte **Název** a **Popis** profilu pro omezení zařízení.
5. V rozevíracím seznamu **Platforma** vyberte **Windows 10 a novější**.
6. Z rozevíracího seznamu **Typ profilu** zvolte **Vzdělávací profil**. 
7. Zvolte Nastavení > Konfigurace a potom v okně **Zkuste si test** nakonfigurujte následující:
    - **Uživatelské jméno účtu** – zadejte uživatelské jméno účtu pro aplikaci Zkuste si test. Tím může být doménový účet, účet Azure Active Directory (AAD) nebo účet místního počítače.
    - **Adresa URL hodnocení** – zadejte adresu URL testu, který mají uživatelé absolvovat. Další informace najdete v dokumentaci k aplikaci Zkuste si test.
    - **Monitorování obrazovky** – určete, zda chcete mít možnost monitorovat aktivitu na obrazovce, zatímco uživatelé absolvují test.
    - **Návrh textu** – povolení nebo blokování textových návrhů, když uživatelé absolvují test.
8. Až to budete mít, vraťte se do okna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v okně se seznamem profilů.
Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](how-to-assign-device-profiles.md).




