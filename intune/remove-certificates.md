---
title: Odebrání certifikátů SCEP a PKCS v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Správci můžou k odebrání certifikátů z Microsoft Intune použít akce vymazání nebo vyřazení. Při některých scénářích, třeba při zrušení registrace zařízení nebo při odebrání zásady dodržování předpisů, se certifikát odebere automaticky. Při jiných scénářích naopak certifikáty zůstanou v zařízení, třeba při ztrátě nebo odebrání licence v Intune. Podívejte se na různé způsoby u zařízení se systémy Android, Android Enterprise, iOS, macOS a Windows.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/23/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d4287322fd494c97cf24feb8cc16435a4405f2af
ms.sourcegitcommit: 7a649a5995600fb91817643e20a5565caedbb8f2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/26/2018
ms.locfileid: "50150099"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>Odebrání certifikátů SCEP a PKCS v Microsoft Intune

V Microsoft Intune přidáváte zařízením certifikáty SCEP a PKCS. Tyto certifikáty můžete také odebrat tím, že zařízení [vymažete](devices-wipe.md#wipe) nebo [vyřadíte](devices-wipe.md#retire). Při některých scénářích se certifikáty odeberou automaticky. Při jiných naopak zůstanou v zařízení.

V tomto článku najdete nejčastější scénáře, které mají vliv na certifikáty PKCS a SCEP.

> [!NOTE]
> Pokud chcete odebrat a odvolat certifikáty uživatele, kterého odebíráte z Active Directory (AD) nebo z Azure AD, použijte následující postup (v uvedeném pořadí):
>
>    1. Vymažte zařízení uživatele nebo ho vyřaďte.
>    2. Odeberte uživatele z AD nebo Azure AD.

## <a name="windows-devices"></a>Zařízení s Windows

#### <a name="scep-certificates"></a>Certifikáty SCEP

- K odvoláni *a* odebrání certifikátu SCEP dojde, když:

  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).
  - Zařízení je odebrané ze skupiny Azure Active Directory (AD).
  - Z přiřazené skupiny je odebraná zásada dodržování předpisů.
  - Z přiřazené skupiny je odebraný konfigurační profil.

- K odvolání certifikátu SCEP dojde, když:
  - Správce změní nebo aktualizuje profil SCEP.

- K odebrání kořenového certifikátu dojde, když:
  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).
  - Z přiřazené skupiny je odebraná zásada dodržování předpisů.

- Certifikáty SCEP **zůstanou** v zařízení (nebudou odvolané ani odebrané), když:
  - Koncový uživatel ztratí licenci Intune.
  - Správce si vezme zpět licenci Intune.
  - Správce odebere uživatele nebo skupinu z Azure AD.

#### <a name="pkcs-certificates"></a>Certifikáty PKCS

- K odvoláni *a* odebrání certifikátu PKCS dojde, když:

  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).

- K odebrání kořenového certifikátu dojde, když:
  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).

- Certifikáty PKCS **zůstanou** v zařízení (nebudou odvolané ani odebrané), když:
  - Koncový uživatel ztratí licenci Intune.
  - Správce si vezme zpět licenci Intune.
  - Správce odebere uživatele nebo skupinu z Azure AD.
  - Správce změní nebo aktualizuje profil PKCS.
  - Z přiřazené skupiny je odebraný konfigurační profil.
  - Z přiřazené skupiny je odebraná zásada dodržování předpisů. 


## <a name="ios-devices"></a>Zařízení se systémem iOS

#### <a name="scep-certificates"></a>Certifikáty SCEP

- K odvoláni *a* odebrání certifikátu SCEP dojde, když:

  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).
  - Zařízení je odebrané ze skupiny Azure Active Directory (AD).
  - Z přiřazené skupiny je odebraná zásada dodržování předpisů.
  - Z přiřazené skupiny je odebraný konfigurační profil.

- K odvolání certifikátu SCEP dojde, když:
  - Správce změní nebo aktualizuje profil SCEP.

- K odebrání kořenového certifikátu dojde, když:
  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).
  - Z přiřazené skupiny je odebraná zásada dodržování předpisů.

- Certifikáty SCEP **zůstanou** v zařízení (nebudou odvolané ani odebrané), když:
  - Koncový uživatel ztratí licenci Intune.
  - Správce si vezme zpět licenci Intune.
  - Správce odebere uživatele nebo skupinu z Azure AD.

#### <a name="pkcs-certificates"></a>Certifikáty PKCS

- K odvoláni *a* odebrání certifikátu PKCS dojde, když:

  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).

- K odebrání certifikátu PKCS dojde, když:
  - Z přiřazené skupiny je odebraná zásada dodržování předpisů.
  - Z přiřazené skupiny je odebraný konfigurační profil.
  
- K odebrání kořenového certifikátu dojde, když:
  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).

- Certifikáty PKCS **zůstanou** v zařízení (nebudou odvolané ani odebrané), když:
  - Koncový uživatel ztratí licenci Intune.
  - Správce si vezme zpět licenci Intune.
  - Správce odebere uživatele nebo skupinu z Azure AD.
  - Správce změní nebo aktualizuje profil PKCS.

## <a name="android--android-enterprise-devices"></a>Zařízení se systémy Android a Android Enterprise

#### <a name="scep-certificates"></a>Certifikáty SCEP

- K odvoláni *a* odebrání certifikátu SCEP dojde, když:
  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).

- K odvolání certifikátu SCEP dojde, když:
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).
  - Zařízení je odebrané ze skupiny Azure Active Directory (AD).
  - Z přiřazené skupiny je odebraná zásada dodržování předpisů.
  - Z přiřazené skupiny je odebraný konfigurační profil.
  - Správce odebere uživatele nebo skupinu z Azure Active Directory (AD).
  - Správce změní nebo aktualizuje profil SCEP.

- K odebrání kořenového certifikátu dojde, když:
  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).

- Certifikáty SCEP **zůstanou** v zařízení (nebudou odvolané ani odebrané), když:
  - Koncový uživatel ztratí licenci Intune.
  - Správce si vezme zpět licenci Intune.
  - Správce odebere uživatele nebo skupinu z Azure AD.

#### <a name="pkcs-certificates"></a>Certifikáty PKCS

- K odvoláni *a* odebrání certifikátu PKCS dojde, když:

  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).

- K odebrání kořenového certifikátu dojde, když:
  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).

- Certifikáty PKCS **zůstanou** v zařízení (nebudou odvolané ani odebrané), když:
  - Koncový uživatel ztratí licenci Intune.
  - Správce si vezme zpět licenci Intune.
  - Správce odebere uživatele nebo skupinu z Azure AD.
  - Správce změní nebo aktualizuje profil PKCS.
  - Z přiřazené skupiny je odebraný konfigurační profil.
  - Z přiřazené skupiny je odebraná zásada dodržování předpisů. 

## <a name="macos-certificates"></a>Certifikáty macOS

#### <a name="scep-certificates"></a>Certifikáty SCEP

- K odvoláni *a* odebrání certifikátu SCEP dojde, když:
  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).
  - Zařízení je odebrané ze skupiny Azure Active Directory (AD).
  - Z přiřazené skupiny je odebraná zásada dodržování předpisů.
  - Z přiřazené skupiny je odebraný konfigurační profil.

- K odvolání certifikátu SCEP dojde, když:
  - Správce změní nebo aktualizuje profil SCEP.

- Certifikáty SCEP **zůstanou** v zařízení (nebudou odvolané ani odebrané), když:
  - Koncový uživatel ztratí licenci Intune.
  - Správce si vezme zpět licenci Intune.
  - Správce odebere uživatele nebo skupinu z Azure AD.

> [!NOTE]
> U zařízení s macOS není podporované obnovení továrního nastavení akcí [vymazání](devices-wipe.md#wipe).

#### <a name="pkcs-certificates"></a>Certifikáty PKCS

Zařízení s macOS nepodporují certifikáty PKCS.
