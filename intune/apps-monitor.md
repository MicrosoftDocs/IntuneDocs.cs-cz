---
title: Postup monitorování informací a přiřazení aplikace
titlesuffix: Microsoft Intune
description: Po přiřazení aplikace uživatelům nebo zařízením můžete použít tyto informace, které vám usnadní monitorování jejího stavu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/09/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 01b7972a6a4dbb641f4c656190324d8572f9010c
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a>Postup monitorování informací a přiřazení aplikace pomocí Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune poskytuje několik způsobů, jak můžete monitorovat vlastnosti vámi spravovaných aplikací a stav jejich přiřazení.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází ve skupině **Monitorování a správa**.
3. Zvolte **Mobilní aplikace** a pak ve skupině **Spravovat** zvolte možnost **Aplikace**.
5. V seznamu aplikací zvolte aplikaci, kterou chcete monitorovat. Zobrazí se okno aplikace s přehledem stavu zařízení a uživatele.

## <a name="app-overview-blade"></a>Přehled okna aplikací

V okně konkrétní aplikace si můžete zkontrolovat podrobnosti o stavu aplikace ve vašem prostředí.

### <a name="essentials"></a>Essentials
Část **Základy** obsahuje následující informace o aplikaci:

 | **Podrobnosti aplikace**            | **Popis**                                                      |
|------------------------|------------------------------------------------------------------|
| **Vydavatel**          | Vydavatel aplikace                                            |
| **Operační systém**   | Operační systém aplikace (Windows, iOS, Android atd.) |
| **Vytvořeno**             | Datum a čas vytvoření této revize                         |
| **Přiřazeno**           | Označuje, zda byla aplikace přiřazena – **Ano** nebo **Ne**.                  |

### <a name="device-and-user-status-graphs"></a>Grafy stavu zařízení a uživatele
Grafy zobrazují počty pro následující stav:

| **Stav zařízení**       | **Popis**                                       |
|-----------------------|-------------------------------------------------------|
| **Instalováno**         | Počet nainstalovaných aplikací                         |
| **Nenainstalováno**     | Počet nenainstalovaných aplikací                     |
| **Neúspěch**            | Počet neúspěšných instalací                   |
| **Instalace čeká**   | Počet aplikací, které se právě instalují |
| **Není k dispozici**           | Počet aplikací, u nichž není stav k dispozici            |

### <a name="device-install-status"></a>Stav instalace zařízení

Seznam stavů zařízení se zobrazí, když v části **Monitorovat** vyberete **Stav instalace zařízení**. Tabulka s podrobnostmi obsahuje následující sloupce:

| **Sloupec zařízení**      | **Popis**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Název zařízení**      | Název zařízení na platformách, které umožňují pojmenování zařízení. Na ostatních platformách Intune vytvoří název z dalších vlastností. Tento atribut nemusí být dostupný pro všechna zařízení.                                                                       |
| **Uživatelské jméno**        | Jméno uživatele                                                                                                                                                                                                                                      |
| **Platforma**         | Operační systém zařízení (Windows, iOS, Android atd.)                                                                                                                                                                                           |
| **Verze**          | Číslo verze aplikace. U obchodních aplikací se zobrazuje celé číslo verze aplikace. Celé číslo verze identifikuje konkrétní vydanou verzi aplikace. Číslo se zobrazí jako _Verze_(_build_). Příklad: 2.2(2.2.17560800) |
| **Stav**           | Stav aplikace                                                                                                                                                                                                                                     |
| **Podrobnosti stavu**   | Podrobnosti o stavu                                                                                                                                                                                                                                     |
| **Poslední vrácení se změnami**    | Datum, kdy se zařízení naposledy synchronizovalo s Intune                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>Stav instalace uživatele

Seznam stavů uživatele se zobrazí, když v části **Monitorovat** vyberete **Stav instalace uživatele**. Tabulka s podrobnostmi obsahuje následující sloupce:

| **Sloupec uživatele**     | **Popis**                           |
|---------------------|-------------------------------------------|
| **Název**            | Jméno uživatele ve službě Azure AD         |
| **Uživatelské jméno**       | Jedinečné jméno uživatele              |
| **Instalace**   | Počet instalací aplikace použitých uživatelem |
| **Chyby**        | Počet neúspěšných instalací uživatelem     |
| **Nenainstalováno**   | Počet aplikací, které nenainstaloval uživatel |


## <a name="next-steps"></a>Další kroky

- Další informace o práci s daty Intune najdete v tématu [Použití datového skladu Intune](reports-nav-create-intune-reports.md).
- Další informace o zásadách konfigurace aplikací najdete v tématu [Zásady konfigurace aplikací v Intune](app-configuration-policies-overview.md).