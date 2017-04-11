---
title: "Konfigurace nastavení vzdělávání Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Naučte se pomocí služby Intune nakonfigurovat nastavení vzdělávání pro zařízení, která spravujete."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: ca4f1adc5704ecd66d2af7823f95ca63ec20469e
ms.openlocfilehash: 5c73719c4fd2805f91c6af3ba48c39f5d798aaeb
ms.lasthandoff: 03/17/2017


---

# <a name="how-to-configure-education-settings-in-microsoft-intune"></a>Konfigurace nastavení vzdělávání ve službě Microsoft Intune

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




