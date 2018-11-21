---
title: Registrace zařízení s pracovním profilem Androidu v Intune
titlesuffix: Microsoft Intune
description: Zjistěte, jak v Intune zaregistrovat zařízení s pracovním profilem Androidu.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: b3592ceb2b1a4e7ba32fc0a8b3de53e0f0329d8b
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52179724"
---
# <a name="set-up-enrollment-of-android-work-profile-devices"></a>Nastavení registrace zařízení s pracovním profilem Androidu

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Nasazením aplikací a nastavení do zařízení s pracovním profilem Androidu vám Intune pomůže zajistit, aby byly pracovní a osobní informace oddělené. Konkrétní podrobnosti o Androidu Enterprise najdete v tématu [Požadavky na Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Správu pracovního profilu Androidu nastavíte tímto postupem:

1. [Propojte účet tenanta Intune s účtem Androidu Enterprise](connect-intune-android-enterprise.md).
2. Určete nastavení registrace pracovního profilu Androidu. Pracovní profily Androidu jsou [podporované jen na určitých zařízeních s Androidem](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Jakékoli zařízení, které podporuje pracovní profily Androidu, podporuje také správu konvenčního Androidu. Intune umožňuje určit, jak se mají spravovat zařízení podporující pracovní profily Androidu v rámci [Omezení registrace](enrollment-restrictions-set.md).
    - **Blokovat (standardně nastaveno)**: Všechna zařízení s Androidem včetně zařízení podporujících pracovní profily Androidu se zaregistrují jako zařízení s konvenčním Androidem.
    - **Povolit**: Všechna zařízení podporující pracovní profily Androidu se zaregistrují jako zařízení s pracovním profilem Androidu. Jakékoli zařízení s Androidem, které nepodporuje pracovní profily Androidu, se zaregistruje jako zařízení s konvenčním Androidem.
3. [Sdělte uživatelům, jak mají svá zařízení zaregistrovat](/intune-user-help/enroll-your-device-in-intune-android).


Pokud chcete zaregistrovat zařízení s pracovním profilem Androidu, ale tato zařízení jsou už zaregistrovaná jako zařízení s běžným Androidem, musí se registrace těchto zařízení nejprve zrušit a pak se musí znovu zaregistrovat.

Při registraci zařízení s pracovním profilem Androidu pomocí účtu [správce registrace zařízení](device-enrollment-manager-enroll.md) platí omezení, že pomocí jednoho účtu je možné zaregistrovat maximálně 10 zařízení.

Další informace najdete v článku [Data z Intune odesílaná Googlu](data-intune-sends-to-google.md).

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Schválení aplikace Portál společnosti ve spravovaném obchodu Google Play

Aby měli uživatelé vždy přístup k aktuální verzi aplikace Portál společnosti, musíte aplikaci Portál společnosti pro Android schválit ve spravovaném obchodu Google Play. Jejím schválením zajistíte, aby všichni uživatelé dostávali automatické aktualizace. Pokud ji neschválíte, bude Portál společnosti časem zastaralý a nemusí dostávat důležité opravy chyb a nové funkce, které Microsoft vydává.

Při schvalování Portálu společnosti Intune postupujte takto:

1.  Ve [spravovaném obchodě Google Play](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal) přejděte na aplikaci Portál společnosti.
2.  Přihlaste se do spravovaného obchodu Google Play pomocí stejného účtu Google, který jste použili ke konfiguraci vazby pro Android Enterprise.
3.  Klikněte na **Approve** (Schválit) a otevře se nové dialogové okno.
4.  Zkontrolujte oprávnění v tomto dialogu a pak klikněte na **Approve** (Schválit). Aby aplikace Portál společnosti mohla spravovat pracovní profil v daném zařízení, je nutné povolit tato oprávnění.
5.  Vyberte **Keep approved when app requests new permissions** (Pokud aplikace vyžaduje nová oprávnění, zachovat jako schválené) a pak klikněte na **Save** (Uložit).

## <a name="next-steps-for-android-work-profiles"></a>Další kroky pro pracovní profily Androidu
- [Nasazení aplikací do pracovního profilu Androidu](apps-add-android-for-work.md)
- [Přidání zásad konfigurace pracovního profilu Androidu](device-profiles.md)
