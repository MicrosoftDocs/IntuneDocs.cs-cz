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
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 06b568ee7cc2dc55a8d44cf04b96078b47d8c4b3
ms.sourcegitcommit: 77a1047f5d93c1924e5c9ea243454532881be031
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/28/2018
ms.locfileid: "52579162"
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
  - Profil certifikátu se odebere z přiřazení skupiny

- K odvolání certifikátu SCEP dojde, když:
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
  - Profil certifikátu se odebere z přiřazení skupiny


## <a name="ios-devices"></a>zařízení s Iosem

#### <a name="scep-certificates"></a>Certifikáty SCEP

- K odvoláni *a* odebrání certifikátu SCEP dojde, když:

  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).
  - Zařízení je odebrané ze skupiny Azure Active Directory (AD).
  - Profil certifikátu se odebere z přiřazení skupiny

- K odvolání certifikátu SCEP dojde, když:
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

- K odebrání certifikátu PKCS dojde, když:
  - Profil certifikátu se odebere z přiřazení skupiny
  
- K odebrání kořenového certifikátu dojde, když:
  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).

- Certifikáty PKCS **zůstanou** v zařízení (nebudou odvolané ani odebrané), když:
  - Koncový uživatel ztratí licenci Intune.
  - Správce si vezme zpět licenci Intune.
  - Správce odebere uživatele nebo skupinu z Azure AD.
  - Správce změní nebo aktualizuje profil PKCS.

## <a name="android-knox-devices"></a>Zařízení s Androidem KNOX

#### <a name="scep-certificates"></a>Certifikáty SCEP

- K odvoláni *a* odebrání certifikátu SCEP dojde, když:
  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vymazání](devices-wipe.md#wipe).

- K odvolání certifikátu SCEP dojde, když:
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).
  - Zařízení je odebrané ze skupiny Azure Active Directory (AD).
  - Profil certifikátu se odebere z přiřazení skupiny
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
  - Profil certifikátu se odebere z přiřazení skupiny
  
  
> [!NOTE]
> Zařízení s Androidem for Work se ve výše uvedených situacích neověřují. Na starších zařízeních s Androidem (jakékoli zařízení od jiného výrobce než Samsung bez pracovního profilu) nelze certifikát odebrat. 

## <a name="macos-certificates"></a>Certifikáty macOS

#### <a name="scep-certificates"></a>Certifikáty SCEP

- K odvoláni *a* odebrání certifikátu SCEP dojde, když:
  - Koncový uživatel zruší registraci.
  - Správce spustí akci [vyřazení](devices-wipe.md#retire).
  - Zařízení je odebrané ze skupiny Azure Active Directory (AD).
  - Profil certifikátu se odebere z přiřazení skupiny

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

