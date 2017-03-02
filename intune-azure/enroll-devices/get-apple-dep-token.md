---
title: "Získání certifikátu Apple DEP pro Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si pokyny ke konfiguraci a nahrání certifikátu MDM Push Certificate, který je potřebný pro správu zařízení Apple v Intune. "
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e5c79c5-2883-4841-9be6-74cba16ee447
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08dad848a48adad7d9c6f0b5b3286f6550a266bd
ms.openlocfilehash: b2c79e92f6378825bdaac03d2d9be699bdaca95b
ms.lasthandoff: 02/15/2017

---

# <a name="get-an-apple-dep-certificate"></a>Získání certifikátu Apple DEP 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Abyste mohli v programu DEP registrovat zařízení s iOSem vlastněná společností, potřebujete od společnosti Apple token DEP. Token umožňuje Intune synchronizovat informace o zařízeních vlastněných společností, která se účastní programu DEP. Token taky umožňuje Intune odesílat společnosti Apple registrační profil a přiřazovat k těmto profilům zařízení.

Pokud chce organizace ke správě zařízení s iOS, která jsou v jejím vlastnictví, používat program DEP (Device Enrollment Program) společnosti Apple, musí se do tohoto programu zaregistrovat a získat zařízení jeho prostřednictvím. Podrobnosti o tomto procesu najdete na https://deploy.apple.com. Výhodou tohoto programu je bezobslužné nastavení zařízení bez připojení každého zařízení k počítači kabelem USB.

> [!NOTE]
> Tuto poznámku si přečtěte jenom v případě, že jste zákazník, který migroval z konzoly pro správu Intune na portál Azure Portal. Pokud jste během migrace odstranili token Apple DEP z konzoly pro správu Intune, můžete zjistit, že se token DEP ve vašem účtu Intune obnovil. Pokud se to stane, můžete token DEP jednoduše odstranit z portálu Azure Portal. 

**Získání certifikátu Apple DEP**</br>
Na portálu Azure Portal zvolte **Další služby** > **Monitorování + správa** > **Intune**. V okně Intune zvolte možnost **Registrovat zařízení** > **Token DEP Apple** a pak na portálu Azure Portal postupujte podle níže uvedených očíslovaných kroků.

**Krok 1: Stáhněte si certifikát veřejného klíče služby Intune, který je potřebný pro vytvoření tokenu DEP Apple.**<br>
Vyberte **Stáhnout certifikát veřejného klíče** a stáhněte si a místně uložte soubor šifrovacího klíče (.pem). Soubor .pem slouží k vyžádání certifikátu vztahu důvěryhodnosti z portálu Apple Device Enrollment Program.

**Krok 2: Stáhněte si token DEP Apple z příslušného webu Apple.**<br>
Vyberte [Vytvořit token DEP prostřednictvím Apple Deployment Programs](https://deploy.apple.com). Dostanete se na https://deploy.apple.com, kde se přihlaste svým firemním Apple ID. Toto Apple ID budete muset použít také k obnovení tokenu DEP.

   1.  Na [portálu programu DEP (Device Enrollment Program)](https://deploy.apple.com) přejděte na **Program DEP (Device Enrollment Program)** &gt; **Spravovat servery** a pak zvolte **Přidat server MDM**.

   2.  Zadejte **název serveru MDM** a zvolte **Další**. Název serveru slouží pro vaši informaci, abyste mohli identifikovat server pro správu mobilních zařízení (MDM). Není to název serveru Microsoft Intune ani jeho URL.

   3.  Otevře se dialog **Přidat server &lt;název_serveru&gt;**. Vyberte **Zvolit soubor**, abyste mohli nahrát soubor .pem, a pak zvolte **Další**.

   4.  V dialogovém okně **Přidat server &lt;název_serveru&gt;** se zobrazí odkaz s **tokenem vašeho serveru**. Stáhněte si soubor tokenu serveru (.p7m) do svého počítače a potom zvolte **Hotovo**.

    Soubor certifikátu (.p7m) se používá k navázání vztahu důvěryhodnosti mezi serverem Intune a serverem programu DEP (Device Enrollment Program) společnosti Apple.

**Krok 3: Zadejte Apple ID, které jste použili k vytvoření tokenu Apple DEP. Toto ID můžete použít také k obnovení tokenu Apple DEP.**

**Krok 4: Procházením vyhledejte token Apple DEP, který chcete nahrát. Služba Intune se bude automaticky synchronizovat s vaším účtem DEP.**<br>
Přejděte k souboru certifikátu (.pem), zvolte **Otevřít** a pak zvolte **Nahrát**. S certifikátem Push Certificate může Intune registrovat a spravovat zařízení s iOSem a vynucovat zásady na zaregistrovaných mobilních zařízeních.

