---
title: Registrace zařízení s Androidem v Intune
titleSuffix: Microsoft Intune
description: Přečtěte si, jak zaregistrovat zařízení s Androidem v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 7/23/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 7dcde377dbf3e97e94957ab5c984aa6dfede9136
ms.sourcegitcommit: 74911a263944f2dbd9b754415ccda6c68dae0759
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/17/2019
ms.locfileid: "71303928"
---
# <a name="enroll-android-devices"></a>Registrace zařízení s Androidem

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce Intune můžete zařízení s Androidem registrovat následujícími způsoby:
- Android Enterprise (nabízí sadu možností registrace, které uživatelům poskytují nejaktuálnější a zabezpečené funkce):
    - [**Pracovní profil Android Enterprise**](android-work-profile-enroll.md): Osobní zařízení udělila oprávnění k přístupu k podnikovým datům. Správci můžou spravovat pracovní účty, aplikace a data. Osobní údaje na zařízení jsou oddělené od pracovních dat a správci neovládají osobní nastavení ani data. 
    - [**Vyhrazený pro Android Enterprise**](android-kiosk-enroll.md): Pro zařízení vlastněná podnikem, jako je digitální podpis, tisk lístku nebo Správa inventáře. Správci omezí použití zařízení na omezenou sadu aplikací a webových odkazů. Uživatelé zároveň nemůžou na tomto zařízení přidávat jiné aplikace ani provádět jiné akce.
    - [**Plně spravovaná platforma Android Enterprise**](android-fully-managed-enroll.md): Pro zařízení vlastněná společností, která používají výhradně pro práci a nikoli pro osobní použití. Správci můžou spravovat celé zařízení a vynutilit ovládací prvky zásad nedostupné pro pracovní profily. 
- [**Správce zařízení s Androidem**](android-enroll-device-administrator.md), včetně zařízení se zabezpečením Samsung KNOX Standard a [zařízení Zebra](android-zebra-mx-overview.md). 

## <a name="prerequisites"></a>Požadavky

Při přípravě na správu mobilních zařízení musíte nastavit autoritu pro správu mobilních zařízení (MDM) na **Microsoft Intune**. Pokyny k tomu najdete v článku [Nastavení autority MDM](mdm-authority-set.md). Tato možnost se nastavuje jenom jednou při prvním nastavování Intune pro správu mobilních zařízení.

Pro zařízení vyráběná technologiemi Zebra může být potřeba udělit Portál společnosti dodatečná oprávnění v závislosti na možnostech konkrétního zařízení. [Rozšíření mobility na zařízeních Zebra](android-zebra-mx-overview.md) obsahují další podrobnosti.

Pro zařízení se zabezpečením Samsung KNOX Standard jsou k dispozici [Další požadavky](android-samsung-knox-mobile-enroll.md).

## <a name="next-steps"></a>Další kroky

- [Nastavení registrace pracovních profilů pro Android Enterprise](android-work-profile-enroll.md)
- [Nastavení registrace zařízení se systémem Android Enterprise vyhrazené](android-kiosk-enroll.md)
- [Nastavení plně spravovaných registrů pro Android Enterprise](android-fully-managed-enroll.md)
- [Nastavení registrace Správce zařízení s Androidem](android-enroll-device-administrator.md)

