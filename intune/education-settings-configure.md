---
title: "Konfigurace nastavení vzdělávání Intune pro Windows 10"
titleSuffix: Azure portal
description: "Naučte se pomocí služby Intune nakonfigurovat nastavení vzdělávání pro Windows 10 na zařízení, která spravujete."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 12e36761320557f6af9554d3b671fc133253c13c
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Konfigurace nastavení vzdělávání pro Windows 10 ve službě Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Vzdělávací profily vám umožňují určit podrobnosti, které nakonfigurují aplikaci Windows Zkuste si test, včetně podrobností účtu a adresy URL testu. Jakmile bude konfigurace hotová, otevře se aplikace Zkuste si test s vámi určeným testem a žádná jiná aplikace nepůjde na zařízení spustit, dokud se test nedokončí.

Podrobnosti o aplikaci Zkuste si test najdete v článku o [používání testů ve Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení vzdělávacího profilu

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
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

## <a name="next-steps"></a>Další kroky

Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).



