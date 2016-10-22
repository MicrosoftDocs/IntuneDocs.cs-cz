---
title: "Nasazení aplikací na zařízení s Androidem for Work | Microsoft Intune"
description: "Pomocí tohoto tématu můžete synchronizovat a pak nasadit aplikaci do zařízení s Androidem for Work z obchodu Google Play for Work."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32bded5047b1a08738418e3e36382eeae1a5f3b4
ms.openlocfilehash: f3b7c3a07ef3530805f4f951bcdb99cc5f7eb93d


---

# Jak nasadit aplikace do zařízení s Androidem for Work pomocí Intune

Na zařízení s Androidem for Work se aplikace nasazují jiným způsobem než na zařízení se standardním Androidem. Všechny aplikace, které instalujete pro Android for Work, pocházejí z obchodu Google Play for Work. Do tohoto obchodu se přihlásíte, prohlédnete si požadované aplikace, a schválíte je.
Aplikace se pak objeví v uzlu **Multilicenční aplikace** konzoly Intune. Odsud můžete nasazení aplikace spravovat stejným způsobem, jakým byste nasadili jakoukoli jinou aplikaci.
Pokud jste vytvořili své vlastní firemní aplikace, můžete je také nasadit. K tomu si potřebujete zaregistrovat vývojářský účet Google, který umožňuje publikování aplikací do privátní oblasti obchodu Google Play a jejich synchronizaci s Intune.

## Než začnete

1. Ověřte, že jste na kartě **Správce** konzoly Intune nakonfigurovali vzájemnou spolupráci Intune a Androidu for Work.

## Synchronizace aplikace z obchodu Google Play for Work


1. Přejděte do [obchodu Google Play for Work](https://play.google.com/work). Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work.
2. Vyhledejte v obchodě aplikaci, kterou chcete nasadit pomocí Intune.
3. Na stránce se zvolenou aplikací vyberte **Schválit**. V tomto příkladu je zvolená aplikace Microsoft Excel.<br>
  ![Příklad schválení aplikace](/intune/deploy-use/media/approve.png)
4. Otevře se okno s žádostí, abyste této aplikaci udělili oprávnění k provádění různých operací. Před pokračováním musíte zvolit možnost **Schválit**.<br>
  ![Příklad schválení oprávnění aplikace](/intune/deploy-use/media/approve-app-permissions.png)
5. Za okamžik se zobrazí zpráva s potvrzením, že aplikace je schválená a dostupná v konzole pro správu. 

## Publikování a synchronizace firemní aplikace z obchodu Google Play for Work 

1. Přejděte do konzoly pro vývojáře Google Play na adrese [play.google.com/apps/publish](play.google.com/apps/publish).
2. Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work. Pokud se přihlašujete poprvé, musíte se zaregistrovat a zaplatit poplatek, abyste se stali členy programu pro vývojáře Google.
3. V této konzole zvolte **Přidat novou aplikaci**.
4. Informace o vaší aplikaci nahrajete a zadáte stejným způsobem jako při publikování jakékoli jiné aplikace v obchodě Google Play. Musíte ale vybrat nastavení **Zpřístupnit tuto aplikaci pouze pro moji organizaci (<*název organizace*>)**, jak je znázorněno níže.<br>
  ![Možnost zpřístupnění aplikace jen pro organizaci](/intune/deploy-use/media/restrict.png)<br>
Tím zajistíte, aby tato aplikace byla dostupná jenom vaší organizaci a nebyla dostupná ve veřejném obchodě Google Play.
Další informace o nahrávání a publikování aplikací pro Android najdete v [nápovědě ke konzole pro vývojáře Google](https://support.google.com/googleplay/android-developer/answer/113469).
5. Po publikování aplikace přejděte do [obchodu Google Play for Work](https://play.google.com/work). Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work. 
6. Ověřte, že se v uzlu **Aplikace** tohoto obchodu zobrazuje aplikace, kterou jste publikovali. Můžete si všimnout, že u ní byla automaticky schválena synchronizace s Intune.

## Nasazení aplikace pro Android for Work

Intune se s obchodem Google Play for Work synchronizuje zpravidla dvakrát denně. Pokud jste aplikaci v tomto obchodě schválili, ale ještě ji nevidíte v uzlu **Multilicenční aplikace** pracovního prostoru **Aplikace**, můžete tímto způsobem vynutit okamžitou synchronizaci:

1. V [konzole pro správce Intune](https://manage.microsoft.com) zvolte **Správce** > **Správa mobilních zařízení** > **Android for Work**.
2. Na stránce **Nastavení správy mobilních zařízení Android for Work** zvolte **Synchronizovat**.
3. Na této stránce se zobrazuje také čas a stav poslední synchronizace.

Když se aplikace objeví v uzlu **Multilicenční aplikace** pracovního prostoru **Aplikace**, můžete ji [nasadit stejně jako jakoukoli jinou aplikaci](deploy-apps-in-microsoft-intune.md). Tuto aplikaci můžete nasadit jenom skupinám uživatelů. V současnosti můžete vybrat jenom akce **Požadováno** a **Odinstalovat**. Od října 2016 začneme do nových tenantů přidávat akci nasazení **K dispozici**. 

Po nasazení se aplikace nainstaluje na zařízení, která jste určili. Uživatel zařízení nebude požádán o schválení.



<!--HONumber=Oct16_HO2-->


