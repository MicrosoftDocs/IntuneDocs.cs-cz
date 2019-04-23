---
title: Aplikace pro prostředí s vysokou GCC a ministerstva obrany USA
titleSuffix: Microsoft Intune
description: Další informace o aplikacích zahrnující GCC vysoké a ministerstva obrany prostředí pomocí Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/18/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 29329f86-1aa5-434f-9925-8dc28bf35348
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 43df4d72cda3830f9793f591eebcb4d2a1ec284f
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61507167"
---
# <a name="deploying-apps-using-intune-on-the-gcc-high-and-dod-environments"></a>Nasazení aplikace pomocí Intune v GCC vysoké a ministerstva obrany USA prostředí 

Microsoft Intune umožňuje správci tenanta distribuovat aplikace pro jejich pracovní síly. Pracovní síly stále zaměstnancem společnosti uživatelům aplikace. Existuje mnoho typů aplikací, které se dají nasadit z Intune na vysokou GCC nebo prostředí ministerstva obrany USA. Pokud správce potřebuje k nahrání a distribuovat aplikace s Windows určené pro vysoké GCC nebo cílová skupina amerického ministerstva obrany, který je vlastní, vytvořené pomocí jiných dodavatelů, nebo jako offline aplikace stažené z [Microsoft Store pro firmy](https://businessstore.microsoft.com/store), Správce může vybrat, zda jej jako distribuovat [– obchodní aplikace](apps-add.md#app-types-in-microsoft-intune).  

> [!NOTE]
> Pro obchodní prostředí správce tenanta můžete synchronizovat jejich Store pro firmy v Intune, ale pro prostředí s vysokou GCC a ministerstva obrany USA, tato služba není k dispozici. Správci v této situaci musíte nasadit aplikaci tak, že nahrajete přímo do Intune.  

## <a name="add-line-of-business-apps-using-intune"></a>Přidat z obchodních aplikací pomocí Intune 

Chcete-li přidat – obchodní aplikace určená pro prostředí s vysokou GCC nebo ministerstva obrany USA pomocí Intune, můžete postupovat podle [Windows obchodní aplikaci pro](lob-apps-windows.md) pokyny. Můžete nejprve nasadit portál společnosti z Microsoft Store pro firmy. Pokud se rozhodnete používat portál společnosti, můžete ručně nainstalovat a nasadit aplikaci portál společnosti. Další informace najdete v tématu [konfigurace aplikace portál společnosti Microsoft Intune](company-portal-app.md). 

## <a name="distribute-offline-apps-from-the-store-for-business-using-intune"></a>Distribuovat do režimu Offline aplikace z Store pro firmy pomocí Intune  

Pokud potřebujete [stažení offline licencované aplikace](https://docs.microsoft.com/microsoft-store/distribute-offline-apps#download-an-offline-licensed-app) z Microsoft Store pro firmy, postupujte podle těchto kroků a stáhněte aplikaci: 

1. Přihlaste se k [Store pro firmy](https://businessstore.microsoft.com/).
2. Vyberte **spravovat** > **nastavení**.
3. V části **nákupní prostředí**, nastavte **zobrazení offline aplikací** k **na**.

Při nákupu pro aplikace, pokud je k dispozici offline verze, můžete změnit typ licence na offline. Po získání aplikace, pak ji můžete spravovat tak, že vyberete **spravovat** > **produkty a služby** v [Store pro firmy](https://businessstore.microsoft.com/). Kromě toho si můžete stáhnout aplikaci a její závislosti. Potom nasaďte Tuto staženou aplikaci (a jeho závislosti) pro uživatele, kteří používají Intune.  

## <a name="syncing-intune-to-the-store-for-business"></a>Synchronizaci Intune pro Store pro firmy 

V komerčním prostředí (bez státní správu) můžete synchronizovat Správce Intune a Microsoft Store pro firmy. Není k dispozici funkce v prostředích státní správy. Podrobnosti o rozdílech mezi Intune v komerčním prostředí a Intune pro státní správu prostředí najdete v tématu [Enterprise Mobility + Security for US Government popis služby](https://docs.microsoft.com/enterprise-mobility-security/solutions/ems-govt-service-description).  

Pokud chcete synchronizovat Intune do vaší Store pro firmy, přečtěte si téma [Správa aplikací koupených z Microsoft Store pro firmy v Microsoft Intune](windows-store-for-business.md).  

## <a name="compliance"></a>Dodržování předpisů 

Přečtěte si prohlášení o ochraně osobních údajů a dodržování předpisů aplikací a jejich porovnání s požadavky dodržování předpisů, zabezpečení a ochrana osobních údajů vaší organizace při posuzování řádném používání těchto služeb.   

## <a name="next-steps"></a>Další postup

Další informace o nasazení a přiřazení aplikací najdete v tématu [přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md).

 
