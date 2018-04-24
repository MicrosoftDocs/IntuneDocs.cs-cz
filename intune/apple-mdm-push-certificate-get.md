---
title: Získání certifikátu Apple MDM Push Certificate
titlesuffix: Microsoft Intune
description: Přečtěte si postup, jak získat certifikát Apple MDM Push Certificate pro správu zařízení s iOSem v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/08/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 28eb86a1924dc72df4c77cc3f8a05aacd61e0fbd
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="get-an-apple-mdm-push-certificate"></a>Získání certifikátu Apple MDM Push Certificate

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

V Intune můžete spravovat tato mobilní zařízení: iPady, iPhony a počítače Mac. Intune uživatelům nabízí přístup k firemnímu e-mailu a aplikacím. Pro správu zařízení s iOSem a macOS potřebuje Intune certifikát Apple MDM Push. Po přidání certifikátu do Intune si uživatelé můžou zaregistrovat zařízení pomocí:

- aplikace Portál společnosti,

- nástrojů hromadné registrace Apple, jako je Program registrace zařízení, Apple School Manager nebo Apple Configurator.

Další informace o možnostech registrace najdete v článku o [způsobech registrace zařízení s iOSem](enrollment-method-choose-ios.md).

Když platnost certifikátu Push vyprší, je nutné ho obnovit. Při obnovování je třeba použít stejné Apple ID jako při prvním vytvoření certifikátu Push.


## <a name="steps-to-get-your-certificate"></a>Kroky k získání certifikátu
Na portálu [Azure Portal](https://portal.azure.com) zvolte **Registrace zařízení** > **Registrace Apple** > **Apple MDM Push Certificate** a pak na portálu [Azure Portal](https://portal.azure.com) postupujte podle těchto kroků.

### <a name="step-1-grant-microsoft-permission-to-send-user-and-device-information-to-apple"></a>Krok 1: Udělte Microsoftu oprávnění k odesílání informací o uživatelích a zařízeních společnosti Apple.
Vyberte možnost **Souhlasím.** a udělte tak Microsoftu oprávnění posílat data do Applu.

![Obrazovka Konfigurace certifikátu MDM Push Certificate s nenastaveným certifikátem MDM Push](./media/create-mdm-push-certificate.png)

### <a name="step-2-download-the-intune-certificate-signing-request-required-to-create-an-apple-mdm-push-certificate"></a>Krok 2: Stáhněte si žádost o podepsání certifikátu (CSR) pro Intune, která je potřebná k vytvoření certifikátu Apple MDM Push Certificate.
Vyberte **Stáhnout CSR** a uložte si soubor žádosti .csr místně. Soubor slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Push Certificates Portal.

  ### <a name="step-3-create-an-apple-mdm-push-certificate"></a>Krok 3: Vytvořte certifikát Apple MDM Push Certificate.
Vyberte **Vytvořit certifikát MDM Push Certificate**. Tím přejdete na Apple Push Certificates Portal. Přihlaste se pomocí Apple ID společnosti a potom klikněte na **Vytvořit certifikát**. Vyberte **Vybrat soubor**, procházením vyhledejte soubor žádosti o podepsání certifikátu a potom zvolte **Nahrát**. Na stránce Potvrzení vyberte **Stáhnout**, stáhněte soubor certifikátu (.pem) a uložte ho do místního umístění.

> [!NOTE]
> Certifikát je přidružený k Apple ID, pomocí kterého byl vytvořen. Osvědčeným postupem je použití Apple ID společnosti pro úlohy správy a zajištění toho, že je poštovní schránka monitorována více osobami jako distribuční seznam. Nikdy nepoužívejte svoje osobní Apple ID.

### <a name="step-4-enter-the-apple-id-used-to-create-your-apple-mdm-push-certificate"></a>Krok 4: Zadejte Apple ID, které jste použili k vytvoření certifikátu Apple MDM Push Certificate.
Poznamenejte si toto ID jako připomenutí na dobu, kdy bude třeba obnovit tento certifikát.

### <a name="step-5-browse-to-your-apple-mdm-push-certificate-to-upload"></a>Krok 5: Procházením vyhledejte certifikát Apple MDM Push Certificate, který chcete nahrát.
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
