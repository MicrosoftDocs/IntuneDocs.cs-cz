---
title: Nastavení registrace Intune pro zařízení s Androidem Enterprise s plnou správou
titleSuffix: Microsoft Intune
description: Přečtěte si, jak zaregistrovat zařízení s Androidem Enterprise s plnou správou v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2018
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 0035f8d5cd67a995924f7d07a662d8c0671bf063
ms.sourcegitcommit: c19584b36448bbd4c8638d7cab552fe9b3eb3408
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/20/2019
ms.locfileid: "71163782"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-fully-managed-devices"></a>Nastavení registrace Intune pro plně spravovaná zařízení s Androidem Enterprise 

Zařízení se systémem Android Enterprise Standarded jsou zařízení vlastněná společností, která jsou přidružená k jednomu uživateli a používána výhradně pro práci a nikoli pro osobní použití. Správci můžou spravovat celé zařízení a vynutilit ovládací prvky zásad nedostupné pro pracovní profily, jako třeba:
- Povolí instalaci aplikace jenom ze spravovaných Google Play.
- Blokuje odinstalaci spravovaných aplikací.
- Zabraňte uživatelům v obnovení továrního nastavení zařízení atd.

Intune vám pomůže nasadit aplikace a nastavení na zařízení s Androidem Enterprise, včetně zařízení se systémem Android Enterprise s plnou správou. Konkrétní podrobnosti o Androidu Enterprise najdete v tématu [požadavky na Android Enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

## <a name="technical-requirements"></a>Technické požadavky

Abyste mohli spravovat plně spravovaná zařízení s Androidem Enterprise, musíte mít samostatného tenanta Intune. Plně spravovaná Správa zařízení není k dispozici v režimu hybridního (Configuration Managerho připojení) nebo ve starší konzole pro správu Silverlight.

Zařízení musí splňovat tyto požadavky, aby je bylo možné spravovat jako plně spravované zařízení s Androidem Enterprise:

- Operační systém Android verze 6,0 a vyšší.
- Zařízení musí spustit sestavení Androidu, které má připojení Google Mobile Services (GMS). Zařízení musí mít dostupnou službu GMS a musí být schopna se k této službě připojit.

Pokud jsou splněné výše uvedené požadavky, není na výrobci zařízení/OEM žádné omezení.

## <a name="set-up-android-enterprise-fully-managed-device-management"></a>Nastavení správy plně spravovaného zařízení s Androidem Enterprise

Pokud chcete nastavit správu plně spravovaného zařízení s Androidem Enterprise, postupujte podle těchto kroků:

1. Pro přípravu na správu mobilních zařízení musíte [nastavit autoritu správy mobilních zařízení (MDM) na **Microsoft Intune**](mdm-authority-set.md). Tato možnost se nastavuje jenom jednou při prvním nastavování Intune pro správu mobilních zařízení.
2. [Připojte svůj účet tenanta Intune ke svému účtu Android Enterprise](connect-intune-android-enterprise.md).
3. [Povolit zařízení uživatelů vlastněná společností](#enable-corporate-owned-user-devices)
4. [Zaregistrujte plně spravovaná zařízení](#enroll-the-fully-managed-devices).

### <a name="enable-corporate-owned-user-devices"></a>Povolit uživatelská zařízení ve vlastnictví firmy

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a vyberte **registrace** > zařízení registrace zařízení s**Androidem** > **ve vlastnictví firmy, plně spravovaná uživatelská zařízení**.
2. V části **dovolit uživatelům registrovat zařízení uživatelů vlastněná společností**vyberte **Ano**.

> [!NOTE]
> Pokud máte definované zásady podmíněného přístupu Azure AD, které používají nastavení *vyžadovat, aby zařízení bylo označené jako vyhovující* a platí pro **všechny cloudové aplikace**, **Android** a **prohlížeče** – musíte vyloučit **Microsoft Intune** cloudová aplikace z těchto zásad Důvodem je to, že procesy instalace Androidu k ověřování uživatelů během registrace používají kartu Chrome. Další informace najdete v [dokumentaci k podmíněnému přístupu v Azure AD](https://docs.microsoft.com/azure/active-directory/conditional-access/).

Pokud je toto nastavení nastaveno na **Ano**, poskytne vám token pro zápis (náhodný řetězec) a kód QR pro vašeho tenanta Intune. Tento token jediného zápisu je platný pro všechny uživatele a nevyprší jeho platnost. V závislosti na operačním systému Android a verzi zařízení můžete použít buď token, nebo kód QR k registraci beznabídkového zařízení.

## <a name="enroll-the-fully-managed-devices"></a>Registrace plně spravovaných zařízení
Teď můžete [svá plně spravovaná zařízení zaregistrovat](android-dedicated-devices-fully-managed-enroll.md).

## <a name="next-steps"></a>Další kroky
- [Přidat zásady konfigurace zařízení s plnou správou pro Android Enterprise](device-restrictions-android-for-work.md#device-owner-only)
- [Konfigurace zásad konfigurace aplikací pro plně spravovaná zařízení s Androidem Enterprise](app-configuration-policies-use-android.md)

