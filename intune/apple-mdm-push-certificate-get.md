---
title: "Získání certifikátu Apple MDM Push Certificate"
titlesuffix: Microsoft Intune
description: "Přečtěte si postup, jak získat certifikát Apple MDM Push Certificate pro správu zařízení s iOSem v Intune."
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 504f2431754aa88ddf79bef4a201cbf7aa032834
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="get-an-apple-mdm-push-certificate"></a>Získání certifikátu Apple MDM Push Certificate

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 V Intune můžete spravovat tato mobilní zařízení: iPady, iPhony a počítače Mac. Intune uživatelům nabízí přístup k firemnímu e-mailu a aplikacím. Pro správu zařízení s iOSem a počítačů Mac potřebuje Intune certifikát MDM Push. Po přidání certifikátu do Intune si uživatelé můžou nainstalovat aplikaci Portál společnosti, aby si mohli zaregistrovat zařízení. Můžete také nastavit správu zařízení s iOSem vlastněných společností pomocí Device Enrollment Programu společnosti Apple nebo zařízení zaregistrovat například pomocí Apple Configuratoru. Další informace o možnostech registrace najdete v článku o [způsobech registrace zařízení s iOSem](enrollment-method-choose-ios.md).

## <a name="steps-to-get-your-certificate"></a>Kroky k získání certifikátu
Na portálu [Azure Portal](https://portal.azure.com) zvolte **Registrace zařízení** > **Registrace Apple** > **Apple MDM Push Certificate** a pak na portálu [Azure Portal](https://portal.azure.com) postupujte podle těchto kroků.

**Krok 1: Stáhněte si žádost o podepsání certifikátu (CSR) pro Intune, která je potřebná k vytvoření certifikátu Apple MDM Push Certificate.**<br>
Vyberte **Stáhnout CSR** a uložte si soubor žádosti .csr místně. Soubor slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Push Certificates Portal.

  ![Obrazovka Konfigurace certifikátu MDM Push Certificate s nenastaveným certifikátem MDM Push](./media/create-mdm-push-certificate.png)

**Krok 2: Vytvořte certifikát Apple MDM Push Certificate.**<br>
Vyberte **Vytvořit certifikát MDM Push Certificate**. Tím přejdete na Apple Push Certificates Portal. Přihlaste se pomocí Apple ID společnosti a potom klikněte na **Vytvořit certifikát**. Vyberte **Vybrat soubor**, procházením vyhledejte soubor žádosti o podepsání certifikátu a potom zvolte **Nahrát**. Na stránce Potvrzení vyberte **Stáhnout**, stáhněte soubor certifikátu (.pem) a uložte ho do místního umístění.

> [!NOTE]
> Certifikát je přidružený k Apple ID, pomocí kterého byl vytvořen. Osvědčeným postupem je použití Apple ID společnosti pro úlohy správy a zajištění toho, že je poštovní schránka monitorována více osobami jako distribuční seznam. Nikdy nepoužívejte svoje osobní Apple ID.

**Krok 3: Zadejte Apple ID, které jste použili k vytvoření certifikátu Apple MDM Push Certificate.**<br>
Poznamenejte si toto ID jako připomenutí na dobu, kdy bude třeba obnovit tento certifikát.

**Krok 4: Procházením vyhledejte certifikát Apple MDM Push Certificate, který chcete nahrát.**<br>
Přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Nahrát**. Pomocí certifikátu Push Certificate může Intune zaregistrovat a spravovat zařízení Apple.

## <a name="renew-apple-mdm-push-certificate"></a>Obnovení certifikátu Apple MDM Push Certificate
Certifikát Apple MDM Push Certificate je platný po dobu jednoho roku a je potřeba ho každý rok obnovit, aby nedošlo k přerušení správy zařízení s iOSem a macOS. Pokud platnost certifikátu vyprší, nelze zaregistrovaná zařízení Apple kontaktovat.

Certifikát je přidružený k Apple ID, pomocí kterého byl vytvořen. Obnovte MDM Push Certificate pomocí stejného Apple ID, které jste použili k jeho vytvoření.

1. Na portálu [Azure Portal](https://portal.azure.com) zvolte **Registrace zařízení** > **Registrace Apple** a pak zvolte dlaždici **Apple MDM Push Certificate** v oblasti podrobností.
2. Vyberte **Stáhnout CSR** a uložte si soubor žádosti .csr místně. Soubor slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Push Certificates Portal.
3. Vyberte **Vytvořit certifikát MDM Push Certificate**. Tím přejdete na Apple Push Certificates Portal. Najděte certifikát, který chcete obnovit, a vyberte **Obnovit**.
4. Na obrazovce **Prodloužit platnost certifikátu MDM Push Certificate** zadejte poznámky, které vám v budoucnosti pomůžou certifikát identifikovat, vyberte **Zvolit soubor**, přejděte na nový soubor žádosti, který jste stáhli, a zvolte **Nahrát**.
   > [!TIP]
   > Certifikát je možné identifikovat podle jeho UID. Identifikátor GUID, který je součástí identifikátoru UID, najdete v podrobnostech certifikátu v **ID subjektu**. Můžete také na zaregistrovaném zařízení s iOSem přejít na **Nastavení** > **Obecné** > **Správa** **zařízení** > **Profil správy** > **Další podrobnosti** > **Profil správy**. Položka na druhém řádku, **Téma**, obsahuje jedinečný identifikátor GUID, který můžete porovnat s certifikátem na portálu Apple Push Certificates.
 
6. Na obrazovce **Potvrzení** vyberte **Stáhnout** a uložte si soubor .pem místně.
7. Na portálu [Azure Portal](https://portal.azure.com) vyberte ikonu procházení **Apple MDM Push Certificate**, vyberte soubor .pem stažený z webu společnosti Apple a zvolte **Nahrát**.

Apple MDM Push Certificate se zobrazí se stavem **Aktivní** a do vypršení jeho platnosti zbývá 365 dnů.
