---
title: "Přiřazení aplikací zařízení s Androidem for Work"
titlesuffix: Microsoft Intune
description: "Naučte se synchronizovat a přiřadit aplikace zařízením s Androidem for Work z obchodu Google Play for Work."
keywords: 
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/07/2018
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e3b5a742fb480cf9c4c77106b849eebb95ad2439
ms.sourcegitcommit: 8a235b7af6ec3932c29a76d0b1aa481d983054bc
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="how-to-assign-apps-to-android-for-work-devices-with-intune"></a>Přiřazení aplikací zařízení s Androidem for Work pomocí Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Android for Work je program pro zařízení s Androidem. Všechny aplikace, které instalujete na zařízení s Androidem for Work, pocházejí z obchodu Google Play for Work. Zařízením s Androidem for Work se aplikace přiřazují jiným způsobem než zařízením se standardním Androidem. Do tohoto obchodu se přihlásíte, prohlédnete si požadované aplikace a schválíte je. Aplikace se pak objeví v uzlu **Licencované aplikace** Azure Portalu. Odsud můžete přiřazení aplikace spravovat stejným způsobem, jakým byste přiřadili jakoukoli jinou aplikaci.

Pokud jste vytvořili své vlastní obchodní aplikace, můžete je také přiřadit tímto způsobem:
- Zaregistrujte si vývojářský účet Google, který umožňuje publikování aplikací do privátní oblasti obchodu Google Play.
- Synchronizujte aplikace s Intune.

## <a name="before-you-start"></a>Než začnete

Ověřte, že jste v úloze **Registrace zařízení** Azure Portalu nakonfigurovali vzájemnou spolupráci Intune a Androidu for Work.

## <a name="synchronize-an-app-from-the-google-play-for-work-store"></a>Synchronizace aplikace z obchodu Google Play for Work

1. Přejděte do [obchodu Google Play for Work](https://play.google.com/work). Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work.
2. Vyhledejte a vyberte v obchodě aplikaci, kterou chcete přiřadit pomocí Intune.
3. Na stránce zobrazující aplikaci vyberte **Schválit**. Následující příklady ukazují zvolenou aplikaci Microsoft Excel.</br>

    ![Příklad – schválení aplikace v obchodu Google Play for Work](media/approve.png)</br>
    
  Otevře se okno s žádostí, abyste této aplikaci udělili oprávnění k provádění různých operací. 

4. Pokud chcete přijmout oprávnění aplikace a pokračovat, vyberte **Schválit**.</br>

    ![Příklad – schválení oprávnění aplikace](media/approve-app-permissions.png)

5. Vyberte, jak se mají zpracovávat nové žádosti oprávnění aplikace. Potom vyberte **Uložit** a uložte způsob zpracování nových žádostí oprávnění aplikace.</br>

    ![Příklad – uložení nové žádosti oprávnění aplikace](media/approve-app-settings.png)</br>

    Aplikace se schválí a zobrazí v konzole pro správu. Teď můžete [aplikaci Android for Work synchronizovat se službou Intune](apps-add-android-for-work.md#sync-an-android-for-work-app-with-intune). 

## <a name="sync-an-android-for-work-app-with-intune"></a>Synchronizace aplikace Android for Work s Intune

Pokud jste aplikaci v tomto obchodě schválili, ale nevidíte ji v uzlu **Licencované aplikace** úlohy **Mobilní aplikace**, vynuťte tímto způsobem okamžitou synchronizaci:

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Na stránce **Intune** zvolte **Mobilní aplikace**.
4. V úloze **Mobilní aplikace** zvolte v části **Nastavení** možnost **Android for Work**.
5. V podokně Android for Work vyberte **Synchronizovat**. Stránka aktualizuje čas a stav poslední synchronizace.
6. V úloze **Mobilní aplikace** vyberte **Aplikace** a zobrazte nově dostupnou aplikaci Android for Work.

Když se aplikace objeví v uzlu **Licence aplikací** úlohy **Mobilní aplikace**, můžete ji [přiřadit stejně jako jakoukoli jinou aplikaci](/intune-azure/manage-apps/deploy-apps). Tuto aplikaci můžete přiřadit jenom skupinám uživatelů.

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

## <a name="working-with-a-line-of-business-app-from-the-google-play-for-work-store"></a>Používání obchodní aplikace z obchodu Google Play for Work

1. Přejděte do konzoly pro vývojáře Google Play na adrese [play.google.com/apps/publish](https://play.google.com/apps/publish).
2. Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work. Pokud se přihlašujete poprvé, musíte se zaregistrovat a zaplatit poplatek, abyste se stali členy programu pro vývojáře Google.
3. V této konzole zvolte **Přidat novou aplikaci**.
4. Informace o vaší aplikaci nahrajete a zadáte stejným způsobem jako při publikování jakékoli jiné aplikace v obchodě Google Play. Musíte ale vybrat nastavení **Zpřístupnit tuto aplikaci pouze pro moji organizaci (<*název organizace*>)**:</br>

    ![Možnost zpřístupnění aplikace jen pro organizaci](media/restrict.png)</br>

Tím zajistíte, aby tato aplikace byla dostupná jen vaší organizaci a nebyla dostupná ve veřejném obchodě Google Play.
Další informace o nahrávání a publikování aplikací pro Android najdete v [nápovědě ke konzole pro vývojáře Google](https://support.google.com/googleplay/android-developer/answer/113469).
5. Po publikování aplikace přejděte do [obchodu Google Play for Work](https://play.google.com/work). Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidem for Work.
6. Ověřte, že se v uzlu **Aplikace** tohoto obchodu zobrazuje aplikace, kterou jste publikovali. Synchronizace s Intune bude automaticky schválená.

## <a name="next-steps"></a>Další kroky

- [Postup přiřazení aplikací do skupin](apps-deploy.md)

