---
title: "Konfigurace nastavení vzdělávání Intune pro Windows 10"
titleSuffix: Azure portal
description: "Naučte se pomocí služby Intune nakonfigurovat nastavení vzdělávání pro Windows 10 na zařízení, která spravujete."
keywords: 
author: barlanmsft
ms.author: barlan
manager: dougeby
ms.date: 02/23/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 18987c65c7ad0443c8bf3dc268284306cf64080d
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Konfigurace nastavení vzdělávání pro Windows 10 ve službě Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Vzdělávací profily vám umožňují určit podrobnosti, které nakonfigurují aplikaci Windows Zkuste si test, včetně podrobností účtu a adresy URL testu. Jakmile bude konfigurace hotová, otevře se aplikace Zkuste si test s vámi určeným testem a žádná jiná aplikace nepůjde na zařízení spustit, dokud se test nedokončí.

Podrobnosti o aplikaci Zkuste si test najdete v článku o [používání testů ve Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Vytvoření profilu zařízení obsahujícího nastavení vzdělávacího profilu

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Konfigurace zařízení**.
2. V podokně **Konfigurace zařízení** v části **Spravovat** zvolte **Profily**.
3. V podokně profilů zvolte **Vytvořit profil**.
4. V podokně **Vytvořit profil** zadejte **Název** a **Popis** profilu pro omezení zařízení.
5. V rozevíracím seznamu **Platforma** vyberte **Windows 10 a novější**.
6. Z rozevíracího seznamu **Typ profilu** zvolte **Vzdělávací profil**. 
7. Zvolte **Nastavení > Konfigurace** a pak v podokně **Zkuste si test** nakonfigurujte toto:
    - **Typ účtu** – z rozevíracího pole vyberte typ účtu.
    - **Uživatelské jméno účtu** – zadejte uživatelské jméno účtu pro aplikaci Zkuste si test. Tím může být doménový účet, účet Azure Active Directory (AAD) nebo účet místního počítače.
    - **Adresa URL hodnocení** – zadejte adresu URL testu, který mají uživatelé absolvovat. Další informace najdete v dokumentaci k aplikaci Zkuste si test.
    - **Monitorování obrazovky** – určete, zda chcete mít možnost monitorovat aktivitu na obrazovce, zatímco uživatelé absolvují test.
    - **Návrh textu** – povolení nebo blokování textových návrhů, když uživatelé absolvují test.
8. Až to budete mít, vraťte se do podokna **Vytvořit profil** a klikněte na **Vytvořit**.

Profil se vytvoří a zobrazí se v podokně se seznamem profilů.

## <a name="next-steps"></a>Další kroky

Pokud chcete pokračovat a přiřadit tento profil ke skupinám, podívejte se na téma [Jak přiřadit profily zařízení](device-profile-assign.md).



