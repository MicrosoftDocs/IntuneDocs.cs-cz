---
title: "Přiřazení aplikací zařízením s Androidem for Work"
titlesuffix: Microsoft Intune
description: "Naučte se synchronizovat a přiřadit aplikace zařízením s Androidem for Work z obchodu Google Play for Work."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 01/02/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6a0b488120ed62031f8af5b8b65d9e90ea6d252b
ms.sourcegitcommit: aafed032492c1b5861d7097a335f9bbb29ce3221
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Přiřazení aplikací zařízením s Androidem for Work pomocí Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Android for Work je program pro zařízení s Androidem. Všechny aplikace, které instalujete na zařízení s Androidem for Work, pocházejí z obchodu Google Play for Work. Zařízením s Androidem for Work se aplikace přiřazují jiným způsobem než zařízením se standardním Androidem. Do tohoto obchodu se přihlásíte, prohlédnete si požadované aplikace a schválíte je. Aplikace se pak objeví v uzlu **Licencované aplikace** Azure Portalu. Odsud můžete přiřazení aplikace spravovat stejným způsobem, jakým byste přiřadili jakoukoli jinou aplikaci.

Pokud jste vytvořili své vlastní obchodní aplikace, můžete je také přiřadit tímto způsobem:
- Zaregistrujte si vývojářský účet Google, který umožňuje publikování aplikací do privátní oblasti obchodu Google Play.
- Synchronizujte aplikace s Intune.

## <a name="before-you-start"></a>Než začnete

Ověřte, že jste v úloze **Registrace zařízení** Azure Portalu nakonfigurovali vzájemnou spolupráci Intune a Androidu for Work.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronizace aplikace z obchodu Google Play for Work

1. Přejděte do [obchodu Google Play for Work](https://play.google.com/work). Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work.
2. Vyhledejte v obchodě aplikaci, kterou chcete přiřadit pomocí Intune.
3. Na stránce se zvolenou aplikací vyberte **Schválit**. V tomto příkladu je zvolená aplikace Microsoft Excel.<br>
  ![Příklad schválení aplikace](media/approve.png)
4. Otevře se okno s žádostí, abyste této aplikaci udělili oprávnění k provádění různých operací. Pokračujte výběrem možnosti **Schválit**.<br>
  ![Příklad schválení oprávnění aplikace](media/approve-app-permissions.png)
5. Aplikace se schválí a zobrazí v konzole pro správu.

## <a name="publish-then-synchronize-a-line-of-business-app-from-the-google-play-for-work-store"></a>Publikování a synchronizace obchodní aplikace z obchodu Google Play for Work

1. Přejděte do konzoly pro vývojáře Google Play na adrese [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work. Pokud se přihlašujete poprvé, musíte se zaregistrovat a zaplatit poplatek, abyste se stali členy programu pro vývojáře Google.
3. V této konzole zvolte **Přidat novou aplikaci**.
4. Informace o vaší aplikaci nahrajete a zadáte stejným způsobem jako při publikování jakékoli jiné aplikace v obchodě Google Play. Musíte ale vybrat nastavení **Zpřístupnit tuto aplikaci pouze pro moji organizaci (<*název organizace*>)**:<br>
  ![Možnost zpřístupnění aplikace jen pro organizaci](media/restrict.png)<br>
Tím zajistíte, aby tato aplikace byla dostupná jen vaší organizaci a nebyla dostupná ve veřejném obchodě Google Play.
Další informace o nahrávání a publikování aplikací pro Android najdete v [nápovědě ke konzole pro vývojáře Google](https://support.google.com/googleplay/android-developer/answer/113469).
5. Po publikování aplikace přejděte do [obchodu Google Play for Work](https://play.google.com/work). Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work.
6. Ověřte, že se v uzlu **Aplikace** tohoto obchodu zobrazuje aplikace, kterou jste publikovali. Synchronizace s Intune bude automaticky schválená.

## <a name="assign-an-android-for-work-app"></a>Přiřazení aplikace pro Android for Work

Pokud jste aplikaci v tomto obchodě schválili, ale nevidíte ji v uzlu **Licencované aplikace** úlohy **Mobilní aplikace**, vynuťte tímto způsobem okamžitou synchronizaci:

1. Přihlaste se k portálu Azure Portal.
2. V okně **Intune** zvolte **Mobilní aplikace**.
3. V úloze **Mobilní aplikace** zvolte **Nastavení** > **Android for Work**.
4. V okně Android for Work zvolte **Synchronizovat nyní**.
5. Na této stránce se zobrazuje také čas a stav poslední synchronizace.

Když se aplikace objeví v uzlu **Licencované aplikace** úlohy **Mobilní aplikace**, můžete ji [přiřadit stejně jako jakoukoli jinou aplikaci](/intune-azure/manage-apps/deploy-apps). Tuto aplikaci můžete přiřadit jenom skupinám uživatelů.

Po přiřazení se aplikace nainstaluje na zařízení, která jste určili. Uživatel zařízení nebude požádán o schválení instalace.

## <a name="manage-android-for-work-app-permissions"></a>Správa oprávnění aplikací pro Android for Work
Android for Work vyžaduje, abyste aplikace ve webové konzole Play spravované Googlem schválili, než je synchronizujete s Intune a přiřadíte koncovým uživatelům.  Protože přes Android for Work můžete nepozorovaně a automaticky nainstalovat tyto aplikace do zařízení uživatelů, musíte oprávnění aplikací schválit za všechny svoje uživatele.  Koncoví uživatelé neuvidí při instalaci žádná oprávnění aplikací, je proto důležité, abyste si tato oprávnění prostudovali a porozuměli jim.

Když vývojář aplikace publikuje novou verzi aplikace s aktualizovanými oprávněními, nejsou tato oprávnění přijata automaticky, i když jste dřívější oprávnění schválili. Zařízení se starší verzí aplikace ji mohou dál používat. Dokud ale oprávnění neschválíte, nebude se aplikace upgradovat. Na zařízení, ve kterých tato aplikace není nainstalovaná, nejde aplikace nainstalovat, dokud neschválíte její nová oprávnění.

### <a name="how-to-update-app-permissions"></a>Jak aktualizovat oprávnění aplikace

Pravidelně navštěvujte spravovanou konzolu Google Play a kontrolujte nová oprávnění. Obchod Google Play můžete nastavit tak, aby byl vám nebo jiným uživatelům zaslán e-mail, pokud bude schválená aplikace vyžadovat nová oprávnění. Pokud přiřadíte nějakou aplikaci a zjistíte, že není nainstalovaná na všech zařízeních, zkontrolujte následujícím postupem nová oprávnění:

1. Navštivte stránku http://play.google.com/work.
2. Přihlaste se pod účtem Google, který jste použili k publikování a schválení aplikací.
3. Přejděte na kartu **Aktualizace** a zjistěte, jestli některé aplikace vyžadují aktualizaci.  Všechny zde uvedené aplikace vyžadují nová oprávnění a nepřiřadí se, dokud nebudou použita.  

Případně ale můžete obchod Google Play nastavit tak, aby automaticky schvaloval nová oprávnění pro každou z aplikací. 



