---
title: Povolení zásad dodržování předpisů pro Google Play Protect v Microsoft Intune
titleSuffix: ''
description: Naučte se vytvořit zásadu dodržování předpisů pro zařízení s Androidem, která bude platit pro službu Google Play Protect.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/22/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22
ms.reviewer: muhosabe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 6c92115b3e5b5c0f13f60b7483905fef2f73c637
ms.sourcegitcommit: cb93613bef7f6015a4c4095e875cb12dd76f002e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2019
ms.locfileid: "57230665"
---
# <a name="how-to-create-a-device-compliance-policy-to-enable-google-play-protect"></a>Jak vytvořit zásadu dodržování předpisů zařízeními pro službu Google Play Protect

Můžete vytvořit novou zásadu dodržování předpisů pro platformu Android, která bude kontrolovat dodržování předpisů službou Google Play Protect (GPP).

Zásadu dodržování předpisů, která vyžaduje potřebná nastavení, můžete potom zacílit na skupinu uživatelů nebo zařízení s Androidem. Pokud zařízení nebude mít povolená požadovaná nastavení, bude se považovat za nedodržující předpisy.

## <a name="create-a-compliance-policy"></a>Tvorba zásady dodržování předpisů

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
2. Ve skupině **Spravovat** zvolte **Dodržování předpisů zařízením**. 
3. Zvolte **Zásady** a pak **Vytvořit zásadu**.
4. Zadejte pro zásadu **Název** a **Popis**.
5. Jako platformu vyberte **Android**.
6. Zvolte **Nastavení** > **Stav zařízení**.
7. Nakonfigurujte nastavení **Google Play Protect**.
8. Po nakonfigurování nastavení Google Play Protect zadejte nastavení **Zabezpečení systému** a **Vlastnosti zařízení**. Když jste hotovi, klikněte na **OK**.

## <a name="configure-the-google-play-protect-settings"></a>Konfigurace nastavení Google Play Protect

 - **Aplikace Služby Google Play je nakonfigurovaná**  
   Vyžaduje, aby byla nainstalovaná a povolená aplikace Služby Google Play. Aplikace Služby Google Play umožňuje instalaci aktualizací zabezpečení a je základní závislostí pro mnoho funkcí zabezpečení na zařízeních s certifikací Google.
 - **Aktualizovaný poskytovatel zabezpečení**  
   Vyžaduje, aby aktualizovaný poskytovatel zabezpečení chránil zařízení před známými chybami zabezpečení.
 - **Kontrola ohrožení aplikací**  
   Vyžaduje, aby byla povolená funkce Androidu **Ověřovat aplikace**.
    > [!Note]  
    > Na starších verzích platformy Android tato funkce představuje nastavení dodržování předpisů. Intune může jenom zkontrolovat, jestli je toto nastavení povolené na úrovni zařízení. Na zařízeních s pracovními profily Androidu je toto nastavení dostupné jako nastavení zásad konfigurace. To správcům umožňuje povolit nastavení pro zařízení.

    Pokud vaše společnost používá pracovní profily Androidu, můžete nastavení **Kontrola ohrožení aplikací** povolit pro zaregistrovaná zařízení. Vytvořte profil zařízení a vyžadujte v něm toto nastavení zabezpečení systému. Další informace najdete v článku o [nastavení omezení zařízení s pracovním profilem Androidu v Microsoft Intune](device-restrictions-android-for-work.md).

 - **Ověření zařízení SafetyNet**  
   Nastavuje úroveň integrity, které musí zařízení dosáhnout při ověření SafetyNet. Mezi možné úrovně patří **Nenakonfigurováno**, **Zkontrolovat základní integritu** a **Zkontrolovat základní integritu a certifikovaná zařízení**.




## <a name="next-steps"></a>Další postup

Další informace o práci se zásadami dodržování předpisů pro zařízení v Intune najdete v článku [Začínáme se zásadami dodržování předpisů zařízeními v Intune](device-compliance-get-started.md).
