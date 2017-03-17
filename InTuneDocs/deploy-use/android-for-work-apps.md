---
title: "Nasazení aplikací na zařízení s Androidem for Work | Dokumentace Microsoftu"
description: "Pomocí tohoto tématu můžete synchronizovat a pak nasadit aplikaci do zařízení s Androidem for Work z obchodu Google Play for Work."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd0bbd90-d3fe-4efc-83fd-d1f3f86800d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: 0936051b5c33a2e98f275ef7a3a32be2e8f5a8b0
ms.openlocfilehash: 3b608d42f04b9fce457b6b61587d05ab5d59bb0a
ms.lasthandoff: 03/10/2017


---

# <a name="how-to-deploy-apps-to-android-for-work-devices-with-intune"></a>Jak nasadit aplikace do zařízení s Androidem for Work pomocí Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Na zařízení s Androidem for Work se aplikace nasazují jiným způsobem než na zařízení se standardním Androidem. Všechny aplikace, které instalujete pro Android for Work, pocházejí z obchodu Google Play for Work. Do tohoto obchodu se přihlásíte, prohlédnete si požadované aplikace, a schválíte je.
Aplikace se pak objeví v uzlu **Multilicenční aplikace** konzoly Intune. Odsud můžete nasazení aplikace spravovat stejným způsobem, jakým byste nasadili jakoukoli jinou aplikaci.

Pokud jste vytvořili své vlastní firemní aplikace, můžete je také nasadit. K tomu si potřebujete zaregistrovat vývojářský účet Google, který umožňuje publikování aplikací do privátní oblasti obchodu Google Play a jejich synchronizaci s Intune.

## <a name="before-you-start"></a>Než začnete

1. Ověřte, že jste na kartě **Správce** konzoly Intune nakonfigurovali vzájemnou spolupráci Intune a Androidu for Work.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronizace aplikace z obchodu Google Play for Work


1. Přejděte do [obchodu Google Play for Work](https://play.google.com/work). Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work.
2. Vyhledejte v obchodě aplikaci, kterou chcete nasadit pomocí Intune.
3. Na stránce se zvolenou aplikací vyberte **Schválit**. V tomto příkladu je zvolená aplikace Microsoft Excel.<br>
  ![Příklad schválení aplikace](media/approve.png)
4. Otevře se okno s žádostí, abyste této aplikaci udělili oprávnění k provádění různých operací. Před pokračováním musíte zvolit možnost **Schválit**.<br>
  ![Příklad schválení oprávnění aplikace](media/approve-app-permissions.png)
5. Za okamžik se zobrazí zpráva s potvrzením, že aplikace je schválená a dostupná v konzole pro správu.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Publikování a synchronizace firemní aplikace z obchodu Google Play for Work

1. Přejděte do konzoly pro vývojáře Google Play na adrese [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work. Pokud se přihlašujete poprvé, musíte se zaregistrovat a zaplatit poplatek, abyste se stali členy programu pro vývojáře Google.
3. V této konzole zvolte **Přidat novou aplikaci**.
4. Informace o vaší aplikaci nahrajete a zadáte stejným způsobem jako při publikování jakékoli jiné aplikace v obchodě Google Play. Musíte ale vybrat nastavení **Zpřístupnit tuto aplikaci pouze pro moji organizaci (<*název organizace*>)**, jak je znázorněno níže.<br>
  ![Možnost zpřístupnění aplikace jen pro organizaci](media/restrict.png)<br>
Tím zajistíte, aby tato aplikace byla dostupná jenom vaší organizaci a nebyla dostupná ve veřejném obchodě Google Play.
Další informace o nahrávání a publikování aplikací pro Android najdete v [nápovědě ke konzole pro vývojáře Google](https://support.google.com/googleplay/android-developer/answer/113469).
5. Po publikování aplikace přejděte do [obchodu Google Play for Work](https://play.google.com/work). Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work.
6. Ověřte, že se v uzlu **Aplikace** tohoto obchodu zobrazuje aplikace, kterou jste publikovali. Můžete si všimnout, že u ní byla automaticky schválena synchronizace s Intune.

## <a name="deploy-an-android-for-work-app"></a>Nasazení aplikace pro Android for Work

Pokud jste aplikaci v tomto obchodě schválili, ale ještě ji nevidíte v uzlu **Multilicenční aplikace** pracovního prostoru **Aplikace**, můžete tímto způsobem vynutit okamžitou synchronizaci:

1. V [konzole pro správce Intune](https://manage.microsoft.com) zvolte **Správce** > **Správa mobilních zařízení** > **Android for Work**.
2. Na stránce **Nastavení správy mobilních zařízení Android for Work** zvolte **Synchronizovat**.
3. Na této stránce se zobrazuje také čas a stav poslední synchronizace.

Když se aplikace objeví v uzlu **Multilicenční aplikace** pracovního prostoru **Aplikace**, můžete ji [nasadit stejně jako jakoukoli jinou aplikaci](deploy-apps-in-microsoft-intune.md). Tuto aplikaci můžete nasadit jenom skupinám uživatelů. V současnosti můžete vybrat jenom akce **Požadováno** a **Odinstalovat**.

Možnost nasadit nějakou aplikaci jako **dostupnou** využívá nové prostředí pro vytváření skupin a cílení. Nově zřízené účty Intune budou tuto funkci moci využívat hned po vydání. Stávající zákazníci Intune mohou tuto funkci používat, jakmile bude jejich tenant migrován na Intune Azure Portal. Stávající zákazníci si mohou vytvořit zkušební účet Intune, aby před migrací tenanta mohli tuto funkci naplánovat a otestovat.

Po nasazení se aplikace nainstaluje na zařízení, která jste určili. Uživatel zařízení nebude požádán o schválení.

## <a name="manage-app-permissions"></a>Správa oprávnění aplikací
Android for Work vyžaduje, abyste aplikace ve webové konzole Play spravované Googlem schválili, než je synchronizujete s Intune a nasadíte koncovým uživatelům.  Protože přes Android for Work můžete nepozorovaně a automaticky nainstalovat tyto aplikace do zařízení uživatelů, musíte oprávnění aplikací schválit za všechny svoje uživatele.  Koncoví uživatelé neuvidí při instalaci žádná oprávnění aplikací, je proto důležité, abyste si tato oprávnění prostudovali a porozuměli jim.

Když vývojář aplikace publikuje novou verzi aplikace s aktualizovanými oprávněními, nejsou tato oprávnění přijata automaticky, i když jste dřívější oprávnění schválili. Zařízení, na kterých je starší verze této aplikace, ji mohou pořád používat, ale tato aplikace se neupgraduje, dokud se nová oprávnění neschválí. Do zařízení, ve kterých tato aplikace není nainstalovaná, nejde aplikace nainstalovat, dokud neschválíte její nová oprávnění.

### <a name="how-to-update-app-permissions"></a>Jak aktualizovat oprávnění aplikace

Měli byste pravidelně navštěvovat spravovanou konzolu Google Play a zjišťovat nová oprávnění. Pokud nasadíte nějakou aplikaci a zjistíte, že není nainstalovaná na všech zařízeních, zkontrolujte následujícím postupem nová oprávnění:

1. Navštivte stránku http://play.google.com/work.
2. Přihlaste se pod účtem Google, který jste použili k publikování a schválení aplikací.
3. Přejděte na kartu **Aktualizace** a zjistěte, jestli některé aplikace vyžadují aktualizaci.  Všechny zde uvedené aplikace vyžadují nová oprávnění a nenasadí se, dokud je neschválíte.  

