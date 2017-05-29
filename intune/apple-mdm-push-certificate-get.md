---
title: "Získání certifikátu Apple MDM Push Certificate"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si postup, jak získat certifikát Apple MDM Push Certificate pro správu zařízení s iOSem v Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: e3ff50fa65eff897147081f2ec9ab366dbf50140
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="get-an-apple-mdm-push-certificate"></a>Získání certifikátu Apple MDM Push Certificate

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

V Intune můžete spravovat tato mobilní zařízení: iPady, iPhony a počítače Mac. Intune uživatelům nabízí přístup k firemnímu e-mailu a aplikacím. Pro správu zařízení s iOSem a počítačů Mac potřebuje Intune certifikát MDM Push. Po přidání certifikátu do Intune si uživatelé můžou nainstalovat aplikaci Portál společnosti, aby si mohli zaregistrovat zařízení. Můžete také nastavit správu zařízení s iOSem vlastněných společností pomocí Device Enrollment Programu společnosti Apple nebo zařízení zaregistrovat například pomocí Apple Configuratoru. Další informace o možnostech registrace najdete v článku o [způsobech registrace zařízení s iOSem](enrollment-method-choose-ios.md).

## <a name="steps-to-get-your-certificate"></a>Kroky k získání certifikátu
Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**. V okně Intune zvolte možnost **Registrovat zařízení** > **Registrace Apple** **Apple MDM Push Certificate** a pak na portálu Azure Portal postupujte podle níže uvedených očíslovaných kroků.

**Krok 1: Stáhněte si žádost o podepsání certifikátu (CSR) pro Intune, která je potřebná k vytvoření certifikátu Apple MDM Push Certificate.**<br>
Vyberte **Stáhnout CSR** a uložte si soubor .csr místně. Soubor .csr slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Push Certificates Portal.

**Krok 2: Vytvořte certifikát Apple MDM Push Certificate.**<br>
Vyberte **Vytvořit certifikát MDM Push Certificate**. Tím přejdete na Apple Push Certificates Portal. Přihlaste se pod Apple ID vaší společnosti, abyste mohli vytvořit certifikát Push Certificate pomocí souboru .csr. Když na portálu Apple Push Certificate Portal zvolíte **Upload** (Nahrát), získáte soubor .json. Tento soubor nepoužívejte pro certifikát Push Certificate. Dokončete stahování a vraťte se na portál Apple Push Certificates Portal do nabídky certifikátů pro servery třetích stran a zvolte **Download** (Stáhnout). Stáhněte si certifikát Push Certficate (soubor .pem) a uložte si ho místně.

> [!NOTE]
> Certifikát je přidružený k Apple ID, pomocí kterého byl vytvořen. Doporučujeme použít Apple ID společnosti pro úlohy správy. Nikdy nepoužívejte svoje osobní Apple ID.

**Krok 3: Zadejte Apple ID, které jste použili k vytvoření certifikátu Apple MDM Push Certificate.**

**Krok 4: Procházením vyhledejte certifikát Apple MDM Push Certificate, který chcete nahrát.**<br>
Přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Nahrát**. S certifikátem Push Certificate může Intune registrovat a spravovat zařízení s iOSem a vynucovat zásady na zaregistrovaných mobilních zařízeních.

## <a name="renew-apple-mdm-push-certificate"></a>Obnovení certifikátu Apple MDM Push Certificate
Certifikát Apple MDM Push Certificate je platný po dobu jednoho roku a je potřeba ho každý rok obnovit, aby nedošlo k přerušení správy zařízení s iOSem a macOS. Pokud platnost certifikátu vyprší, nelze zaregistrovaná zařízení Apple kontaktovat.

Certifikát je přidružený k Apple ID, pomocí kterého byl vytvořen. Obnovte MDM Push Certificate pomocí stejného Apple ID, které jste použili k jeho vytvoření.

> [!NOTE]
> Certifikát je přidružený k Apple ID, pomocí kterého byl vytvořen. Doporučujeme použít Apple ID společnosti pro úlohy správy. Nikdy nepoužívejte svoje osobní Apple ID.

1. Na [portálu Azure Intune](https://portal.azure.com) zvolte **Registrace zařízení** > **Registrace Apple** a potom vyberte **Apple MDM Push Certificate**.
2. Vyberte **Stáhnout CSR** a uložte si soubor .csr místně. Soubor .csr slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Push Certificates Portal.
3. Najděte certifikát, který chcete obnovit, a vyberte **Obnovit**.
4. Na obrazovce **Obnovit certifikát push** zadejte poznámky, které vám v budoucnosti pomůžou certifikát identifikovat, vyberte **Zvolit soubor**, přejděte na nový soubor .csr, který jste stáhli, a zvolte **Nahrát**.
5. Na obrazovce **Potvrzení** vyberte **Stáhnout** a uložte si soubor .pem místně.
6. Na portálu Azure Intune vyberte ikonu procházení **Apple MDM Push Certificate**, vyberte soubor .pem stažený z webu společnosti Apple a zvolte **Nahrát**.

Apple MDM Push Certificate se zobrazí se stavem **Aktivní** a do vypršení jeho platnosti zbývá 365 dnů.

