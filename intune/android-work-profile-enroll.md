---
title: Registrace zařízení s Androidem Enterprise pracovním profilem v Intune
titlesuffix: Microsoft Intune
description: Informace o registraci Androidu Enterprise pracovní profil zařízení v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 6/21/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 554bf209b71d03a95245d656f19a029af6e67a52
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57394967"
---
# <a name="set-up-enrollment-of-android-enterprise-work-profile-devices"></a>Nastavení registrace zařízení s Androidem Enterprise pracovním profilem

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune vám pomůže nasadit aplikace a nastavení pro zařízení s Androidem Enterprise pracovním profilem zajistit, že jsou oddělené pracovní a osobní údaje. Konkrétní podrobnosti o Androidu Enterprise, najdete v části [požadavky na Androidu Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Nastavení správy pracovních profilů Androidu Enterprise, postupujte podle těchto kroků:

1. [Připojení účtu tenanta Intune ke svému účtu Androidu Enterprise](connect-intune-android-enterprise.md).
2. Zadejte nastavení registrace pracovní profil Androidu Enterprise. Pracovní profily androidu Enterprise jsou [podporován pouze některá zařízení s Androidem](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012%20style=%22target=new_window%22). Jakékoli zařízení, které podporuje pracovní profily Androidu Enterprise podporuje také správu konvenčního Androidu. Intune umožňuje určit, jak se mají spravovat zařízení podporující Android Enterprise profiles práce v rámci [omezení registrace](enrollment-restrictions-set.md).
    - **Blok (ve výchozím nastavení)**:  Všechna zařízení s Androidem včetně zařízení podporujících Android Enterprise profiles práce, se zaregistrují jako zařízení s konvenčním Androidem.
    - **Povolit**: Všechna zařízení, která podporují Android Enterprise pracovních profilů se zaregistrují jako Android Enterprise pracovní profil zařízení. Jakékoli zařízení s Androidem, která nepodporuje pracovní profily Androidu Enterprise se zaregistrují jako zařízení s konvenčním Androidem.
3. [Sdělte uživatelům, jak mají svá zařízení zaregistrovat](/intune-user-help/enroll-your-device-in-intune-android).


Pokud chcete zaregistrovat zařízení pomocí pracovních profilů Androidu Enterprise, ale tato zařízení jsou už zaregistrovaná jako běžná zařízení s Androidem, tato zařízení musíte nejprve zrušit jeho registraci a pak znova zapsat.

Pokud se při registraci zařízení s Androidem Enterprise pracovním profilem pomocí [správce registrace zařízení](device-enrollment-manager-enroll.md) účtu, platí omezení maximálně 10 zařízení, které se dají zaregistrovat na jeden účet.

Další informace najdete v článku [Data z Intune odesílaná Googlu](data-intune-sends-to-google.md).

## <a name="approve-the-company-portal-app-in-the-managed-google-play-store"></a>Schválení aplikace portál společnosti v úložišti spravovaný obchod Google Play

Aby bylo zajištěno, že uživatelé mají vždy přístup k nejnovější verzi aplikace portál společnosti, musí schválit aplikace portál společnosti pro Android v úložišti spravovaný obchod Google Play. Jejím schválením zajistíte, aby všichni uživatelé dostávali automatické aktualizace. Pokud ji neschválíte, bude Portál společnosti časem zastaralý a nemusí dostávat důležité opravy chyb a nové funkce, které Microsoft vydává.

Při schvalování Portálu společnosti Intune postupujte takto:

1.  Přechod do aplikace portál společnosti na [spravovaný obchod Google Play store](https://play.google.com/work/apps/details?id=com.microsoft.windowsintune.companyportal).
2.  Přihlaste se spravovaný obchod Google Play storu pomocí stejného účtu Google, který jste použili ke konfiguraci vazby pro Android Enterprise.
3.  Klikněte na **Approve** (Schválit) a otevře se nové dialogové okno.
4.  Zkontrolujte oprávnění v tomto dialogu a pak klikněte na **Approve** (Schválit). Aby aplikace Portál společnosti mohla spravovat pracovní profil v daném zařízení, je nutné povolit tato oprávnění.
5.  Vyberte **Keep approved when app requests new permissions** (Pokud aplikace vyžaduje nová oprávnění, zachovat jako schválené) a pak klikněte na **Save** (Uložit).

## <a name="next-steps-for-android-enterprise-work-profiles"></a>Další kroky pro Android Enterprise pracovní profily
- [Nasazení aplikací pro Android Enterprise pracovní profil](apps-add-android-for-work.md)
- [Přidání zásad Konfigurace pracovní profil Androidu Enterprise](device-profiles.md)
