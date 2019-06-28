---
title: Odebrání certifikátů SCEP a PKCS v Microsoft Intune – Azure | Microsoft Docs
titleSuffix: ''
description: Správci můžou k odebrání certifikátů z Microsoft Intune použít akce vymazání nebo vyřazení. Při některých scénářích, třeba při zrušení registrace zařízení nebo při odebrání zásady dodržování předpisů, se certifikát odebere automaticky. Při jiných scénářích naopak certifikáty zůstanou v zařízení, třeba při ztrátě nebo odebrání licence v Intune. Podívejte se na různé způsoby u zařízení se systémy Android, Android Enterprise, iOS, macOS a Windows.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 06/27/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.reviewer: lacranda
ms.openlocfilehash: de2f201e6a7d0181847db5d212625c9eed9ea698
ms.sourcegitcommit: 9c06d8071b9affeda32e367bfe85d89bc524ed0b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/27/2019
ms.locfileid: "67413776"
---
# <a name="remove-scep-and-pkcs-certificates-in-microsoft-intune"></a>Odebrání certifikátů SCEP a PKCS v Microsoft Intune

Certifikát protokolu SCEP (Simple Enrollment) a Public Key Cryptography Standards (PKCS) profilů certifikátů v Microsoft Intune slouží k přidání certifikáty do zařízení. 

Tyto certifikáty se dají použít odebrány při vám [vymazat](devices-wipe.md#wipe) nebo [vyřazení](devices-wipe.md#retire) zařízení. Existují také scénáře, ve kterém se automaticky odeberou certifikáty a scénáře, ve kterém certifikáty zůstanou v zařízení. V tomto článku najdete nejčastější scénáře, které mají vliv na certifikáty PKCS a SCEP.

> [!NOTE]
> Odebrat a odvolání certifikátů pro uživatele, který je odebrán z místní služby Active Directory nebo Azure Active Directory (Azure AD), postupujte podle těchto kroků v uvedeném pořadí:
>
> 1. Vymazání nebo vyřazení zařízení uživatele.
> 2. Odebrání uživatele z místní služby Active Directory nebo Azure AD.

## <a name="manually-deleted-certificates"></a>Ručně odstranil certifikáty  

Ruční odstranění certifikátu je tento scénář platí napříč platformami a zřídit pomocí profilů certifikátů SCEP nebo PKCS certifikáty. Uživatel může například odstranit certifikát ze zařízení, když bude zařízení dál cílí Zásady certifikátů.  

V tomto scénáři po odstranění certifikátu, které se zařízení zaregistruje pomocí Intune zjistí-li být nesplňuje předpisy, protože chybí očekávaný certifikát. Intune pak vydá nový certifikát zařízení obnovíte dodržování předpisů. Chcete-li obnovit certifikát není vyžadována žádná další akce.  


## <a name="windows-devices"></a>Zařízení Windows

#### <a name="scep-certificates"></a>Certifikáty SCEP

K odvoláni *a* odebrání certifikátu SCEP dojde, když:

- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.
- Zařízení se odebere ze skupiny Azure AD.
- Profil certifikátu se odebere z přiřazení skupiny.

K odvolání certifikátu SCEP dojde, když:
- Správce změn nebo aktualizuje profil SCEP.

Odebrání kořenového certifikátu při:
- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.

Certifikáty SCEP *zůstat* na zařízení (certifikátů není odvolaný nebo odebrat) při:
- Uživatel ztratí licence Intune.
- Správce stáhne licence Intune.
- Správce odebere uživatele nebo skupiny z Azure AD.

#### <a name="pkcs-certificates"></a>Certifikáty PKCS

K odvoláni *a* odebrání certifikátu PKCS dojde, když:

- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.

Odebrání kořenového certifikátu při:
- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.

Certifikáty PKCS *zůstat* na zařízení (certifikátů není odvolaný nebo odebrat) při:
- Uživatel ztratí licence Intune.
- Správce stáhne licence Intune.
- Správce odebere uživatele nebo skupiny z Azure AD.
- Správce změn nebo aktualizuje profil PKCS.
- Profil certifikátu se odebere z přiřazení skupiny.


## <a name="ios-devices"></a>Zařízení se systémem iOS

#### <a name="scep-certificates"></a>Certifikáty SCEP

K odvoláni *a* odebrání certifikátu SCEP dojde, když:

- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.
- Zařízení se odebere ze skupiny Azure AD.
- Profil certifikátu se odebere z přiřazení skupiny.

K odvolání certifikátu SCEP dojde, když:
- Správce změn nebo aktualizuje profil SCEP.

Odebrání kořenového certifikátu při:
- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.

Certifikáty SCEP *zůstat* na zařízení (certifikátů není odvolaný nebo odebrat) při:
- Uživatel ztratí licence Intune.
- Správce stáhne licence Intune.
- Správce odebere uživatele nebo skupiny z Azure AD.

#### <a name="pkcs-certificates"></a>Certifikáty PKCS

K odvoláni *a* odebrání certifikátu PKCS dojde, když:

- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.

K odebrání certifikátu PKCS dojde, když:
- Profil certifikátu se odebere z přiřazení skupiny.
  
Odebrání kořenového certifikátu při:
- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.

Certifikáty PKCS *zůstat* na zařízení (certifikátů není odvolaný nebo odebrat) při:
- Uživatel ztratí licence Intune.
- Správce stáhne licence Intune.
- Správce odebere uživatele nebo skupiny z Azure AD.
- Správce změn nebo aktualizuje profil PKCS.

## <a name="android-knox-devices"></a>Zařízení s Androidem KNOX

#### <a name="scep-certificates"></a>Certifikáty SCEP

K odvoláni *a* odebrání certifikátu SCEP dojde, když:
- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.

K odvolání certifikátu SCEP dojde, když:
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.
- Zařízení se odebere ze skupiny Azure AD.
- Profil certifikátu se odebere z přiřazení skupiny.
- Správce odebere uživatele nebo skupiny z Azure AD.
- Správce změn nebo aktualizuje profil SCEP.

Odebrání kořenového certifikátu při:
- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.

Certifikáty SCEP *zůstat* na zařízení (certifikátů není odvolaný nebo odebrat) při:
- Uživatel ztratí licence Intune.
- Správce stáhne licence Intune.
- Správce odebere uživatele nebo skupiny z Azure AD.

#### <a name="pkcs-certificates"></a>Certifikáty PKCS

K odvoláni *a* odebrání certifikátu PKCS dojde, když:

- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.

Odebrání kořenového certifikátu při:
- Zruší registraci uživatele.
- Správce spustí [vymazání](devices-wipe.md#wipe) akce.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.

Certifikáty PKCS *zůstat* na zařízení (certifikátů není odvolaný nebo odebrat) při:
- Uživatel ztratí licence Intune.
- Správce stáhne licence Intune.
- Správce odebere uživatele nebo skupiny z Azure AD.
- Správce změn nebo aktualizuje profil PKCS.
- Profil certifikátu se odebere z přiřazení skupiny.
  
  
> [!NOTE]
> Zařízení Android for Work se neověřuje uvedených scénářů. Starší verze zařízení s androidem (žádné jiné než Samsung, mimo pracovní profil zařízení) nejsou povolené pro odstranění certifikátu. 

## <a name="macos-certificates"></a>Certifikáty macOS

#### <a name="scep-certificates"></a>Certifikáty SCEP

K odvoláni *a* odebrání certifikátu SCEP dojde, když:
- Zruší registraci uživatele.
- Správce spustí [vyřazení](devices-wipe.md#retire) akce.
- Zařízení se odebere ze skupiny Azure AD.
- Profil certifikátu se odebere z přiřazení skupiny.

K odvolání certifikátu SCEP dojde, když:
- Správce změn nebo aktualizuje profil SCEP.

Certifikáty SCEP *zůstat* na zařízení (certifikátů není odvolaný nebo odebrat) při:
- Uživatel ztratí licence Intune.
- Správce stáhne licence Intune.
- Správce odebere uživatele nebo skupiny z Azure AD.

> [!NOTE]
> U zařízení s macOS není podporované obnovení továrního nastavení akcí [vymazání](devices-wipe.md#wipe).

#### <a name="pkcs-certificates"></a>Certifikáty PKCS

Zařízení s macOS nepodporují certifikáty PKCS.

