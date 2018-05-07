---
title: Přiřazení aplikací zařízení s Androidem for Work
titlesuffix: Microsoft Intune
description: Naučte se synchronizovat a přiřadit aplikace zařízením s Androidem for Work z obchodu Google Play for Work.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1742c33642667a9e7b8ca2f780094345959cd86c
ms.sourcegitcommit: dbea918d2c0c335b2251fea18d7341340eafd673
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="assign-apps-to-android-for-work-devices-with-intune"></a>Přiřazení aplikací zařízení s Androidem for Work pomocí Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android for Work je program pro zařízení s Androidem. Všechny aplikace, které instalujete na zařízení s Androidem for Work, pocházejí z obchodu Google Play for Work. Zařízením s Androidem for Work se aplikace přiřazují jiným způsobem než zařízením se standardním Androidem. Do tohoto obchodu se přihlásíte, prohlédnete si požadované aplikace a schválíte je. Aplikace se pak zobrazí v uzlu **Licencované aplikace** na portálu Azure Portal a můžete spravovat přiřazení aplikace stejně jako u jakékoli jiné aplikace.

Pokud jste vytvořili své vlastní obchodní aplikace, můžete je také přiřadit tímto způsobem:
- Zaregistrujte si vývojářský účet Google, který umožňuje publikování aplikací do privátní oblasti obchodu Google Play.
- Synchronizujte aplikace s Intune.

## <a name="before-you-start"></a>Než začnete

Ověřte, že jste v úloze **Registrace zařízení** Azure Portalu nakonfigurovali vzájemnou spolupráci Intune a Androidu for Work.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronizace aplikace z obchodu Google Play for Work

1. Přejděte do [obchodu Google Play for Work](https://play.google.com/work). Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work.
2. Vyhledejte a vyberte v obchodě aplikaci, kterou chcete přiřadit pomocí Intune.
3. Na stránce s aplikací vyberte **Schválit**.  
    Na tomto příkladu jsme zvolili Microsoft Excel.

    ![Tlačítko Schválit v obchodu Google Play for Work](media/approve.png)
    
   Otevře se okno s žádostí, abyste této aplikaci udělili oprávnění k provádění různých operací. 

4. Pokud chcete přijmout oprávnění aplikace a pokračovat, vyberte **Schválit**.

    ![Na tlačítko Schválit pro oprávnění aplikace](media/approve-app-permissions.png)

5. Vyberte způsob zpracovávání nových žádostí oprávnění aplikace a potom zvolte **Uložit**.

    ![Možnosti zpracovávání nových žádostí oprávnění aplikace](media/approve-app-settings.png)

    Aplikace se schválí a zobrazí v konzole pro správu. Teď můžete [aplikaci Android for Work synchronizovat se službou Intune](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-an-android-for-work-app-with-intune"></a>Synchronizace aplikace Android for Work s Intune

Pokud jste aplikaci v tomto obchodě schválili, ale nevidíte ji v uzlu **Licencované aplikace** úlohy **Mobilní aplikace**, vynuťte tímto způsobem okamžitou synchronizaci:

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Mobilní aplikace**.
4. V podokně úloh **Mobilní aplikace** vyberte v části **Nastavení** možnost **Android for Work**.
5. V podokně **Android for Work** vyberte **Synchronizovat**.  
    Stránka aktualizuje čas a stav poslední synchronizace.
6. V podokně úloh **Mobilní aplikace** vyberte **Aplikace**.  
    Zobrazí se nově dostupná aplikace Android for Work.

Když se aplikace objeví v uzlu **Licence aplikací** podokna úloh **Mobilní aplikace**, můžete ji [přiřadit stejně jako jakoukoli jinou aplikaci](/intune-azure/manage-apps/deploy-apps). Tuto aplikaci můžete přiřadit jenom skupinám uživatelů.

Po přiřazení se aplikace nainstaluje na zařízení, která jste určili. Uživatel zařízení nebude požádán o schválení instalace.

## <a name="manage-android-for-work-app-permissions"></a>Správa oprávnění aplikací pro Android for Work
Android for Work vyžaduje, abyste aplikace ve webové konzole spravované Google Play schválili, než je synchronizujete s Intune a přiřadíte uživatelům. Protože přes Android for Work můžete nepozorovaně a automaticky nainstalovat tyto aplikace do zařízení uživatelů, musíte oprávnění aplikací schválit za všechny svoje uživatele. Uživatelé neuvidí při instalaci žádná oprávnění aplikací, takže je důležité, abyste si tato oprávnění prostudovali a porozuměli jim.

Když vývojář aplikace publikuje novou verzi aplikace s aktualizovanými oprávněními, nejsou tato oprávnění přijata automaticky, i když jste dřívější oprávnění schválili. Zařízení s předchozí verzí aplikace ji mohou dál používat. Dokud ale oprávnění neschválíte, nebude se aplikace upgradovat. Na zařízení, ve kterých tato aplikace není nainstalovaná, nejde aplikace nainstalovat, dokud neschválíte její nová oprávnění.

### <a name="update-app-permissions"></a>Aktualizace oprávnění aplikace

Pravidelně navštěvujte spravovanou konzolu Google Play a kontrolujte nová oprávnění. Obchod Google Play můžete nastavit tak, aby byl vám nebo jiným uživatelům zaslán e-mail, pokud bude schválená aplikace vyžadovat nová oprávnění. Pokud přiřadíte aplikaci a zjistíte, že není na zařízeních nainstalovaná, zkontrolujte tímto způsobem nová oprávnění:

1. Přejděte na [Google Play](http://play.google.com/work).
2. Přihlaste se pod účtem Google, který jste použili k publikování a schválení aplikací.
3. Vyberte kartu **Aktualizace** a zkontrolujte, jestli některé aplikace nevyžadují aktualizaci.  
    Všechny zde uvedené aplikace vyžadují nová oprávnění a nepřiřadí se, dokud nebudou použita.

Případně ale můžete obchod Google Play nastavit tak, aby automaticky schvaloval nová oprávnění pro každou z aplikací. 

## <a name="working-with-a-line-of-business-app-from-the-google-play-for-work-store"></a>Používání obchodní aplikace z obchodu Google Play for Work

1. Přihlaste se ke [konzole pro vývojáře Google Play](https://play.google.com/apps/publish) pod stejným účtem, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work.  
    Pokud se přihlašujete poprvé, musíte se zaregistrovat a zaplatit poplatek, abyste se stali členy programu pro vývojáře Google.
2. V této konzole zvolte **Přidat novou aplikaci**.
3. Informace o vaší aplikaci nahrajete a zadáte stejným způsobem jako při publikování jakékoli jiné aplikace v obchodě Google Play. Musíte ale vybrat **Zpřístupnit tuto aplikaci pouze pro moji organizaci (<*název organizace*>)**.

    ![Zpřístupnění aplikace jen pro vaši organizaci](media/restrict.png)

    Tím zajistíte, aby tato aplikace byla dostupná jen vaší organizaci a nebyla dostupná ve veřejném obchodě Google Play.

    Další informace o nahrávání a publikování aplikací pro Android najdete v [nápovědě ke konzole pro vývojáře Google](https://support.google.com/googleplay/android-developer/answer/113469).
4. Po publikování aplikace se přihlaste do [obchodu Google Play for Work](https://play.google.com/work) pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work.
5. Ověřte si, že se v uzlu **Aplikace** tohoto obchodu zobrazuje aplikace, kterou jste publikovali.  
    Synchronizace s Intune bude automaticky schválená.

## <a name="next-steps"></a>Další kroky

- [Přiřazení aplikací skupinám](apps-deploy.md) 

