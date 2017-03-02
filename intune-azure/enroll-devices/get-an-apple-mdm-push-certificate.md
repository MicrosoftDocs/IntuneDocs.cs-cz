---
title: "Získání certifikátu Apple MDM Push Certificate | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si postup, jak získat certifikát Apple MDM Push Certificate pro správu zařízení s iOSem v Intune."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: a6ac1074055892f5ec42fb4057e47e9349fb5a33
ms.lasthandoff: 02/15/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Získání certifikátu Apple MDM Push Certificate 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

V Intune můžete spravovat tato mobilní zařízení: iPady, iPhony a zařízení s Mac OS X. Intune uživatelům nabízí přístup k firemnímu e-mailu a aplikacím. Intune potřebuje pro správu zařízení s iOSem a MacOS certifikát APNs (Apple Push Notification service) od společnosti Apple. Po přidání certifikátu do Intune si uživatelé můžou nainstalovat aplikaci Portál společnosti, aby mohli zaregistrovat svá zařízení. Můžete také nastavit správu zařízení s iOSem patřících společnosti.

**Získání certifikátu Apple MDM Push Certificate:**<br>
Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**. V okně Intune zvolte možnost **Registrovat zařízení** > **Apple MDM Push Certificate** a pak na portálu Azure Portal postupujte podle níže uvedených očíslovaných kroků.

**Krok 1: Stáhněte si žádost o podepsání certifikátu (CSR) pro Intune, která je potřebná k vytvoření certifikátu Apple MDM Push Certificate.**<br>
Vyberte **Stáhnout CSR** a uložte si soubor .csr místně. Soubor .csr slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Push Certificates Portal.

**Krok 2: Vytvořte certifikát Apple MDM Push Certificate.**<br>
Vyberte **Vytvořit certifikát MDM Push Certificate**. Tím přejdete na Apple Push Certificates Portal. Přihlaste se pod Apple ID vaší společnosti, abyste mohli vytvořit certifikát Push Certificate pomocí souboru .csr. Když na portálu Apple Push Certificate Portal zvolíte **Upload** (Nahrát), získáte soubor .json. Tento soubor nepoužívejte pro certifikát Push Certificate. Dokončete stahování a vraťte se na portál Apple Push Certificates Portal do nabídky certifikátů pro servery třetích stran a zvolte **Download** (Stáhnout). Stáhněte si certifikát Push Certficate (soubor .pem) a uložte si ho místně.
Poznámka

**Krok 3: Zadejte Apple ID, které jste použili k vytvoření certifikátu Apple MDM Push Certificate.**

**Krok 4: Procházením vyhledejte certifikát Apple MDM Push Certificate, který chcete nahrát.**<br>
Přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Nahrát**. S certifikátem Push Certificate může Intune registrovat a spravovat zařízení s iOSem a vynucovat zásady na zaregistrovaných mobilních zařízeních.

