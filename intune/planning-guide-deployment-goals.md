---
title: Vymezení cílů, úkolů a problémů při nasazení
titleSuffix: Microsoft Intune
description: Tento článek pomáhá vymezit cíle, úkoly a problémy spojené s cloudovou implementací Microsoft Intune.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/02/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8cc4a109aac22617f2785a74de701e4d1d7bdf09
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "67885019"
---
# <a name="determine-deployment-goals-objectives-and-challenges"></a>Vymezení cílů, úkolů a problémů při nasazení

Dobrý plán nasazení začíná identifikací cílů, úkolů a potenciálních problémů spojených s nasazením řešení v organizaci. Pojďme se na jednotlivé oblasti podívat podrobněji.

## <a name="deployment-goals"></a>Cíle nasazení

Cíle nasazení jsou dlouhodobé výsledky, kterých chcete nasazením Intune v organizaci dosáhnout. Tady je několik příkladů takových cílů, včetně jejich popisu a obchodní hodnoty.

- **Integrace s Office 365 a podpora použití mobilních aplikací Office**

  - **Popis:** Poskytněte úzkou integraci se sadou Office 365 a používání mobilních aplikací Office s ochranou aplikací.

  - **Obchodní hodnota:** Zabezpečte a vylepšili uživatelské prostředí tím, že uživatelům umožníte používat aplikace, které znají a upřednostňují.

- **Zpřístupnění interních firemních služeb na mobilních zařízeních**

  - **Popis:** Umožněte zaměstnancům, aby byli produktivní všude, kde potřebují pracovat, a podle toho, která zařízení jsou pro ně vhodná. Projekt má zajistit mobilní produktivitu a bezpečný přístup k firemním datům.

  - **Obchodní hodnota:** Umožnění, aby zaměstnanci byli agilní a pracovali tam, kde potřebují, umožňují, aby firma byla větší konkurenceschopná a poskytovala efektivnější pracovní prostředí.

- **Zajištění ochrany dat v mobilních zařízeních**

  - **Popis:** Když jsou data uložená v mobilním zařízení, měla by být chráněná před škodlivou a náhodnou ztrátou nebo sdílením.

  - **Obchodní hodnota:** Ochrana dat je důležitá, aby bylo zajištěno, že zůstane konkurenční a že budeme považovat za naše klienty a jejich data s nejvyšší opatrností.

- **Snižování nákladů**

  - **Popis:** Pokud je to možné, projekt snižuje náklady na nasazení a provoz.

  - **Obchodní hodnota:** Efektivní využití prostředků umožňuje podniku investovat do jiných oblastí, efektivněji soutěžit a poskytovat lepší služby klientům.

## <a name="deployment-objectives"></a>Úkoly nasazení

Úkoly nasazení jsou akce, které musí organizace provést, aby dosáhla cílů nasazení Intune. Tady jsou některé příklady úkolů při nasazení, včetně způsobu jejich plnění.

- **Snížení počtu řešení pro správu zařízení**

  - **Provádění** Konsolidujte do jednoho řešení pro správu mobilních zařízení: Microsoft Intune pro ochranu podnikových dat aplikací a zařízení.

- **Zajištění zabezpečeného přístup k Exchangi a SharePointu Online**

  - **Provádění** Použijte podmíněný přístup pro Exchange a SharePoint Online.

- **Zabránění ukládání nebo přeposílání firemních dat v mobilním zařízení jiným než firemním službám**

  - **Provádění** Použijte zásady ochrany aplikací Intune pro systém Microsoft Office a obchodní aplikace.

- **Zajistit možnost vymazání firemních dat ze zařízení**

  - **Provádění** Registrace zařízení do Intune V případě potřeby si tím zajistíte možnost vzdáleného vymazání firemních dat a prostředků.

## <a name="deployment-challenges"></a>Aspekty nasazení

Problémy při nasazení mají pro organizaci nejvyšší prioritu, protože mohou negativně ovlivnit nasazení. Někdy souvisejí s minulými problémy z předchozích projektů, kterým byste se chtěli vyhnout, nebo s novými problémy, které se týkají současného nasazení. Tady jsou příklady problémů při nasazení Intune spolu s možnostmi, jak je zmírnit.

- Při úvodním stanovení rozsahu projektu se nepřihlédlo k připravenosti podpory a zkušenostem koncových uživatelů. To vede k nedostatečnému osvojení koncovými uživateli a k problémům s podporou v organizaci.

  - **Zmírnění** Zahrňte školení podpory. Doplnit plán nasazení o ověření zkušeností koncových uživatelů prostřednictvím měřítek úspěšnosti.

- Nedostatek jasně definovaných cílů a měřítek úspěšnosti vede k nedefinovatelným výsledkům. Při vzniku problémů se organizace může dostat do situace, kdy na ně reaguje dodatečně.

  - **Zmírnění** Definujte své cíle a metriky úspěšnosti na začátku v rámci rozsahu projektu a pomocí těchto datových bodů rozveďte své další fáze zavedení. Zajistěte, aby cíle vyhovovaly pravidlu SMART (Specific = konkrétní, Measurable = měřitelné, Attainable = dosažitelné, Realistic = reálné a Timely = včas). V každé fázi naplánujte měření cílů, abyste zajistili průběh projektu podle plánu.

- Opomenete vytvořit , ověřit a důsledně sdílet jasný návrh přidané hodnoty, který zajistí podporu celé organizace. Častým důsledkem je omezené osvojení a nedostatečná návratnost investic (ROI).

  - **Zmírnění** I když se můžete pustit do projektu, ujistěte se, že jste jasně definovali vaše cíle a cíle. Ty pak uvádějte na všech propagačních akcích a školeních, abyste pomohli uživatelům pochopit, proč organizace vybrala Intune.

## <a name="next-steps"></a>Další postup

Teď, když jste identifikovali cíle, cíle a potenciální problémy s nasazením, pojďme přejít k další části: [Identifikujte scénáře použití](planning-guide-scenarios.md).
