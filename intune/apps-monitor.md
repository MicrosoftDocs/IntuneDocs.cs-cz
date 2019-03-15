---
title: Monitorování informací a přiřazení aplikace
titlesuffix: Microsoft Intune
description: Po přiřazení aplikace uživatelům nebo zařízením můžete tyto informace použít, aby vám usnadnily monitorování jejího stavu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/10/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 675409bfbd482ec9935db511e569d8bc174b9a30
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57682653"
---
# <a name="monitor-app-information-and-assignments-with-microsoft-intune"></a>Monitorování informací a přiřazení aplikace pomocí Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune poskytuje několik způsobů, jak monitorovat vlastnosti spravovaných aplikací a spravovat stav jejich přiřazení.

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V nabídce **Intune** zvolte **Klientské aplikace**.
4. V části nabídky **Spravovat** vyberte **Aplikace**.
5. V seznamu aplikací vyberte aplikaci, která se má monitorovat. Zobrazí se podokno aplikace s přehledem stavu zařízení a uživatele.

> [!NOTE]
> Aplikace Android Store, které jsou nasazeny jako **dostupné** a s Androidem obchodní aplikace nasazené jako **k dispozici s registrací i bez** nehlásí stav instalace.

## <a name="app-overview-pane"></a>Podokno přehledu aplikace

V podokně aplikace si můžete zkontrolovat podrobnosti o stavu aplikace ve vašem prostředí.

### <a name="essentials"></a>Základy
Část **Základy** obsahuje následující informace o aplikaci:

 | **Podrobnosti aplikace**            | **Popis**                                                      |
|------------------------|------------------------------------------------------------------|
| **Publisher**          | Vydavatel aplikace                                            |
| **Operační systém**   | Operační systém aplikace (Windows, iOS, Android atd.) |
| **Vytvořeno**             | Datum a čas vytvoření této revize <b>**Poznámka:**: Tato hodnota datum aktualizuje, když správce IT změní metadata aplikace, jako je například změna kategorie aplikace nebo popis aplikace.                        |
| **Přiřazeno**           | Jestli byla aplikace přiřazena (**Ano** nebo **Ne**)                  |

### <a name="device-and-user-status-graphs"></a>Grafy stavu zařízení a uživatele
Grafy zobrazují počet aplikací pro následující stav:

| **Stav zařízení**       | **Popis**                                       |
|-----------------------|-------------------------------------------------------|
| **Nainstalovat**         | Počet nainstalovaných aplikací                         |
| **Nenainstalováno**     | Počet nenainstalovaných aplikací                     |
| **Se nezdařilo**            | Počet neúspěšných instalací                   |
| **Instalace čeká**   | Počet aplikací, které se právě instalují |
| **Není k dispozici**           | Počet aplikací, u nichž není stav k dispozici            |

> [!NOTE]
> Počet zjištěných aplikací nemusí odpovídat stavovému počtu instalací aplikací. K příčinám nekonzistencí můžou patřit tyto:
>    - Změna cílení nainstalované spravované aplikace může způsobit, že se počet instalací ve stavovém okně sníží, bude ale dál hlášený mezi zjištěnými aplikacemi.
>    - Cílení více instancí téže aplikace v tenantovi povede k různým počtům kvůli možnému překrývání uživatelů nebo zařízení. Každá instance aplikace započítá překrývající se uživatele, ale zjištěné aplikace budou mít duplicitní počty.
>    - Zjištěné aplikace a stavy aplikací se shromažďují v různých časových intervalech, což může způsobit nesoulad v počtech aplikací.
> 
> Také, mějte na paměti, že aplikace pro Android nasadit jako **k dispozici s registrací i bez** jenom nahlásit stav instalace aplikace pro zaregistrovaná zařízení. Stav instalace aplikace není k dispozici pro zařízení, která nejsou zaregistrovaná v Intune.

### <a name="device-install-status"></a>Stav instalace zařízení

Seznam stavů zařízení se zobrazí, když v části nabídky **Monitorovat** vyberete **Stav instalace zařízení**. Tabulka s podrobnostmi obsahuje následující sloupce:

| **Sloupec zařízení**      | **Popis**                                                                                                                                                                                                                                            |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Název zařízení**      | Název zařízení na platformách, které umožňují pojmenování zařízení. Na ostatních platformách Intune vytvoří název z dalších vlastností. Tento atribut není k dispozici žádnému jinému zařízení.                                                                       |
| **Uživatelské jméno**        | Jméno uživatele                                                                                                                                                                                                                                      |
| **Platforma**         | Operační systém zařízení (Windows, iOS, Android atd.)                                                                                                                                                                                           |
| **Verze**          | Číslo verze aplikace. Pro aplikace – obchodní (LOB) se zobrazí celé číslo verze aplikace. Celé číslo verze identifikuje konkrétní vydanou verzi aplikace. Číslo se zobrazí jako _Verze_(_build_). Příklad: 2.2(2.2.17560800) Pro aplikace pro Store jsou uvedeny žádné verze. |
| **Stav**           | Stav aplikace                                                                                                                                                                                                                                     |
| **Podrobnosti stavu**   | Podrobnosti o stavu                                                                                                                                                                                                                                     |
| **Poslední vrácení se změnami**    | Datum, kdy se zařízení naposledy synchronizovalo s Intune                                                                                                                                                                                                                  |


### <a name="user-install-status"></a>Stav instalace uživatele

Seznam stavů uživatele se zobrazí, když v části nabídky **Monitorovat** vyberete **Stav instalace uživatele**. Tabulka s podrobnostmi obsahuje následující sloupce:

| **Sloupec uživatele**     | **Popis**                           |
|---------------------|-------------------------------------------|
| **Název**            | Jméno uživatele ve službě Azure Active Directory         |
| **Uživatelské jméno**       | Jedinečné jméno uživatele              |
| **Instalace**   | Počet aplikací, které nainstaloval uživatel |
| **Chyby**        | Počet nezdařených instalací aplikace pro uživatele     |
| **Nenainstalováno**   | Počet aplikací, které nenainstaloval uživatel |


## <a name="next-steps"></a>Další postup

- Další informace o práci s daty Intune najdete v článku [Použití datového skladu Intune](reports-nav-create-intune-reports.md).
- Další informace o zásadách konfigurace aplikací najdete v tématu [Zásady konfigurace aplikací v Intune](app-configuration-policies-overview.md).
