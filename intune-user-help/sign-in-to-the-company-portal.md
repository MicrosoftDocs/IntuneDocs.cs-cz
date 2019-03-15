---
title: Přihlášení do aplikace Portál společnosti | Dokumentace Microsoftu
description: Zjistěte, jak se přihlásit do aplikace Portál společnosti na více platformách.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: cfd214bc-f072-4808-af2e-a3cbf7af9bca
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 370d6372cf3df2ff807069fe8d54f30da23e7ba2
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "55842605"
---
# <a name="how-do-i-sign-in-to-the-company-portal-app---user-story-1132123--"></a>Jak se mám do aplikace Portál společnosti přihlásit? <!--User Story 1132123-->

Aplikaci Portál společnosti používáte pro přístup k prostředkům společnosti, jako je e-mail nebo podnikové aplikace. Jsou dva hlavní způsoby, jak se k Portálu společnosti přihlásit:

* Použijte svou pracovní e-mailovou adresu a heslo
* Přihlaste se z jiného zařízení

Následující obrázky se sice vztahují k systému iOS, ale proces je prakticky totožný pro zařízení s Androidem a s Windows.

## <a name="signing-in-with-your-email-address-and-password"></a>Přihlaste se pomocí pracovní e-mailové adresy a hesla

1. Otevřete na zařízení aplikaci Portál společnosti a klepněte na **Přihlásit se**.

   ![Přihlašovací stránka Portálu společnosti s ikonou osoby před grafickým znázorněním webu. Dole se nachází text „Získejte přístup k prostředkům společnosti a zajistěte jejich zabezpečení“ a přihlašovací tlačítko. Odkaz dole vede na informace Microsoftu o ochraně osobních údajů a souborech cookie.](/intune-user-help/media/cp_ios_aad_signin_after_1804_001.png)

   Nemáte ještě aplikaci Portál společnosti? Zjistěte, jak ji nainstalovat a stáhnout pro systém [iOS](install-and-sign-in-to-the-intune-company-portal-app-ios.md) nebo [Android](install-the-company-portal-app-android.md).

2. Zadejte svůj **pracovní nebo školní účet** a klepněte na **Další**.

   ![Uživatel je vyzván, aby zadal jenom e-mailovou adresu místo zadání e-mailu a hesla na stejné obrazovce.](/intune-user-help/media/cp_ios_aad_signin_after_1804_002.png)

3. Zadejte heslo a klepněte na **Přihlásit se**.

   ![Po přijetí e-mailové adresy je uživatel vyzván k zadání hesla.](/intune-user-help/media/cp_ios_aad_signin_after_1804_003.png)

4. Jakmile Portál společnosti přijme vaše přihlašovací údaje, proběhne přihlášení a vy získáte přístup k prostředkům vaší společnosti.   

   ![Po absolvování procesu ověřování aplikace Portál společnosti zobrazí pruh načítání a přihlásí se.](/intune-user-help/media/cp_ios_aad_signin_after_1804_004.png)

## <a name="signing-in-with-certificate-based-authentication"></a>Přihlášení pomocí ověřování na základě certifikátu

1.  Na svém zařízení otevřete aplikaci Portál společnosti.

2.  Zadejte svůj **Pracovní nebo školní účet**.

3.  Klepněte na odkaz **Přihlásit se pomocí certifikátu**.

4.  Klepnutím na **Pokračovat** certifikát použijte.

## <a name="signing-in-from-another-device"></a>Přihlaste se z jiného zařízení

Pokud pro přihlašování k prostředkům společnosti nepoužíváte heslo, můžete použít jiné zařízení na potvrzení toho, že jste ten správný člověk se správnou úrovní přístupu. Pokud se ve vaší společnosti používají pro přístup k počítačům čipové karty, je pravděpodobné, že se budete muset přihlásit pomocí jiného zařízení.

1. Místo zadávání e-mailové adresy vyberte odkaz **Přihlásit z jiného zařízení** pod textovým polem pro zadání e-mailové adresy.

   ![Přihlašovací stránka Portálu společnosti zobrazí výzvu, aby uživatel zadal e-mailovou adresu.  Pod ní se nachází tlačítko Další a odkaz na přihlášení z jiného zařízení. K dispozici je také odkaz „Nedaří se vám přihlásit?“ Odkaz dole vede na informace Microsoftu o ochraně osobních údajů a souborech cookie.](/intune-user-help/media/cp_ios_aad_signin_after_1804_005.png)

2. Obdržíte jedinečný jednorázový kód pro přihlášení k Portálu společnosti.

   ![Zobrazí se pokyny, abyste ze svého pracovního počítače přešli na stránku https://microsoft.com/devicelogin, kde najdete jedinečný přístupový kód, a ten pak použili k přihlášení.](/intune-user-help/media/cp_ios_aad_signin_after_1804_006.png)

3. Na druhém zařízení otevřete prohlížeč a přejděte na stránku [https://microsoft.com/devicelogin](https://microsoft.com/devicelogin), kde zadejte kód.

   ![Obrázek uživatelova prohlížeče na pracovním počítači místo aplikace Portál společnosti. Zobrazená stránka „Přihlášení na zařízení“ uživatele vyzve k zadání kódu, který dostal v aplikaci Portál společnosti.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_004.png)

4. Jakmile stránka **Přihlášení na zařízení** kód ověří, vyberte __Pokračovat__ a umožněte Portálu společnosti provést přihlášení na vašem druhém zařízení.

   ![Uživatel zadal svůj jedinečný kód do pole a web „Přihlášení na zařízení“ požádal o potvrzení, že je Portál společnosti Intune správnou aplikací, která má získat ověření pro přihlášení.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_005.png)

5. Jakmile se kód ověří, můžete okno zavřít.

   ![Potvrzovací stránka, která uvádí, že se uživatel na svém zařízení přihlásil k aplikaci Portál společnosti a že tuto stránku může zavřít.](/intune/media/cp_ios_aad_signin_from_another_device_after_1704_006.png)

6. Na vašem původním zařízení začne v aplikaci Portálu společnosti probíhat přihlašování.

   ![Po absolvování procesu ověřování aplikace Portál společnosti zobrazí pruh načítání a přihlásí se.](/intune-user-help/media/cp_ios_aad_signin_after_1804_007.png)

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).
