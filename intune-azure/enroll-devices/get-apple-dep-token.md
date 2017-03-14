---
title: "Získání certifikátu Apple DEP pro Intune"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Přečtěte si pokyny ke konfiguraci a nahrání certifikátu MDM Push Certificate, který je potřebný pro správu zařízení Apple v Intune. "
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 153cce3809e24303b8f88a833e2fc7bdd9428a4a
ms.openlocfilehash: 8edc42bb86e3856ac6568cc3c1acc5d757978e79
ms.lasthandoff: 02/18/2017

---

# <a name="get-an-apple-dep-certificate"></a>Získání certifikátu Apple DEP

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Abyste mohli v Programu registrace zařízení (DEP) registrovat zařízení s iOSem vlastněná společností, potřebujete od společnosti Apple token DEP. Token umožňuje Intune synchronizovat informace o zařízeních vlastněných společností, která se účastní programu DEP. Token také umožňuje Intune odesílat společnosti Apple registrační profily a přiřazovat k těmto profilům zařízení.

Pokud chcete zařízení s iOSem vlastněná společností spravovat pomocí Programu registrace zařízení (DEP) společnosti Apple, musí se vaše společnost do tohoto programu zaregistrovat a získat zařízení jeho prostřednictvím. Podrobnosti o tomto procesu najdete na https://deploy.apple.com. Výhodou tohoto programu je bezobslužné nastavení zařízení bez připojení každého zařízení k počítači kabelem USB.

> [!NOTE]
> Tato poznámka se týká pouze zákazníků služby Intune, u kterých proběhla migrace z konzoly pro správu Intune na portál Azure Portal. Pokud jste během migrace odstranili token Apple DEP z konzoly pro správu Intune, můžete zjistit, že se token DEP ve vašem účtu Intune obnovil. Pokud se to stane, můžete token DEP jednoduše odstranit z portálu Azure Portal.

## <a name="steps-to-get-the-apple-dep-certificate"></a>Postup získání certifikátu Apple DEP
Na portálu Azure Portal zvolte **Další služby** > **Monitorování a správa** > **Intune**. V okně Intune zvolte možnost **Registrovat zařízení** > **Token DEP Apple** a pak na portálu Azure Portal postupujte podle níže uvedených očíslovaných kroků.

**Krok 1: Stáhněte si certifikát veřejného klíče služby Intune, který je potřebný pro vytvoření tokenu DEP Apple.**<br>
Vyberte **Stáhnout certifikát veřejného klíče** a stáhněte si a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.

**Krok 2: Stáhněte si token DEP Apple z příslušného webu Apple.**<br>
Vyberte [Vytvořit token DEP prostřednictvím Apple Deployment Programs](https://deploy.apple.com). Dostanete se na https://deploy.apple.com, kde se přihlaste svým firemním Apple ID. Toto Apple ID budete muset použít také k obnovení tokenu DEP.

   a.  Na [portálu programu DEP (Device Enrollment Program)](https://deploy.apple.com) přejděte na **Program DEP (Device Enrollment Program)** &gt; **Spravovat servery** a pak zvolte **Přidat server MDM**.

   b.  Zadejte **název serveru MDM** a zvolte **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název serveru Microsoft Intune ani jeho URL.

   c.  Otevře se dialog **Přidat server &lt;název_serveru&gt;**. Vyberte **Zvolit soubor**, abyste mohli nahrát soubor .pem, a pak zvolte **Další**.

   d.  V dialogovém okně **Přidat server &lt;název_serveru&gt;** se zobrazí odkaz s **tokenem vašeho serveru**. Stáhněte si soubor tokenu serveru (.p7m) do svého počítače a potom zvolte **Hotovo**.

    This certificate (.p7m) file is used to establish a trust relationship between Intune and Apple’s Device Enrollment Program servers.

**Krok 3: Zadejte Apple ID, které jste použili k vytvoření tokenu Apple DEP. Toto ID můžete použít také k obnovení tokenu Apple DEP.**

**Krok 4: Procházením vyhledejte token Apple DEP, který chcete nahrát. Služba Intune se bude automaticky synchronizovat s vaším účtem DEP.**<br>
Přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Nahrát**. S certifikátem Push Certificate může Intune registrovat a spravovat zařízení s iOSem a vynucovat zásady na zaregistrovaných mobilních zařízeních.

