---
title: Přiřazení aplikací spravovaný obchod Google Play na zařízení s Androidem Enterprise
titleSuffix: Microsoft Intune
description: Naučte se synchronizovat a přiřadit aplikace do zařízení s Androidem Enterprise v spravovaný obchod Google Play storu.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 2f6c06bf-e29a-4715-937b-1d2c7cf663d4
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: b977d60c982a43e4465cd451cc2fc24b4e69f4cf
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59898103"
---
# <a name="add-managed-google-play-apps-to-android-enterprise-devices-with-intune"></a>Přidání aplikací pro spravovaný obchod Google Play do podnikových zařízení s Androidem v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android Enterprise je program pro zařízení s pracovním profilem, vyhrazené/veřejný terminál pro zařízení a plně spravovaná zařízení. Pro zařízení s pracovním profilem Androidu Enterprise je sada funkcí a služeb, které oddělují osobní aplikace a data z pracovním aplikacím a datům. Android Enterprise poskytuje možnosti pro další správa a ochrana osobních údajů, když uživatelé používají při práci svoje zařízení s Androidem. Nasazením aplikací a nastavení do zařízení s pracovním profilem Androidu vám Intune pomůže zajistit, aby byly pracovní a osobní informace oddělené. Všechny aplikace, které instalujete do zařízení s pracovním profilem Androidu, pocházejí ze spravovaného obchodu Google Play. Zařízením s pracovním profilem Androidu se aplikace přiřazují jiným způsobem než zařízením se standardním Androidem. Do tohoto obchodu se přihlásíte, prohlédnete si požadované aplikace a schválíte je. Aplikace se pak zobrazí v uzlu **Licencované aplikace** na portálu Azure Portal a můžete spravovat přiřazení aplikace stejně jako u jakékoli jiné aplikace.

Pokud jste vytvořili své vlastní obchodní aplikace, můžete je také přiřadit tímto způsobem:
- Zaregistrujte si vývojářský účet Google, který umožňuje publikování aplikací do privátní oblasti obchodu Google Play.
- Synchronizujte aplikace s Intune.

## <a name="before-you-start"></a>Než začnete

Ověřte, že jste v úloze **Registrace zařízení** na Azure Portalu nakonfigurovali vzájemnou spolupráci Intune a pracovních profilů Androidu. Další informace najdete v tématu [Registrace zařízení s Androidem](android-work-profile-enroll.md).

>[!NOTE]
>Při práci s Microsoft Intune doporučujeme používat prohlížeč Microsoft Edge nebo Google Chrome.

## <a name="managed-google-play-app-type"></a>Typ aplikace Google Play spravované
**Spravované Google Play** typ aplikace vám umožní konkrétně přidat [spravovaný obchod Google Play aplikace](https://play.google.com/work/search?q=microsoft&c=apps) do Intune. Jako správce Intune můžete nyní procházet, Hledat, schválit, synchronizovat a přiřadit schválené spravovaného obchodu Google Play aplikací v Intune.  Už nemusíte procházet spravovanou konzolu Google Play samostatně a donutit k už máte.

> [!NOTE]
> Pokud chcete synchronizovat aplikace na spravovaný obchod Google Play s Intune, přečtěte si téma [synchronizuje aplikace s spravovaný obchod Google Play s Intune](apps-add-android-for-work.md#synchronize-a-managed-google-play-app-with-intune-alternative)

## <a name="add-a-managed-google-play-app-using-intune"></a>Přidat aplikaci spravovaný obchod Google Play pomocí Intune

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**.  
    Intune se nachází v části **Monitorování a správa**.
3. V **Intune** vyberte **klientské aplikace** > **aplikace**.
5. V podokně **Aplikace** vyberte **Přidat**.
6. V **typ aplikace** rozevíracím seznamu vyberte **spravovaný obchod Google Play**.
7. Vyberte **spravovaný obchod Google Play – schválení** otevřete katalogu spravované Google Play.
8. Slouží k vyhledání aplikace, které chcete zahrnout do vyhledávacího pole.
9. Klikněte na tlačítko **schválit** schvalovat aplikace spravovaného obchodu Google Play a klikněte na tlačítko **schválit** přijmout oprávnění aplikace.
10. Vyberte **zachovat schválené, pokud aplikace vyžaduje nová oprávnění** v okně Nastavení schválení a pak klikněte na tlačítko **Uložit**. Pokud tuto možnost nevyberete, musíte ručně schválit všechny nová oprávnění, pokud vývojář aplikace publikuje aktualizace. To způsobí instalacích a aktualizacích aplikace k zastavení nedojde, dokud oprávnění neschválí. Z tohoto důvodu doporučujeme vybrat možnost, aby automaticky schvaloval nová oprávnění. 
11. Klikněte na tlačítko **OK** zahrnout aplikace, které jste schválili.
12. Klikněte na tlačítko **synchronizace** na **aplikací** podokně na synchronizaci se službou spravovaný obchod Google Play.

## <a name="synchronize-a-managed-google-play-app-with-intune-alternative"></a>Synchronizace aplikace spravovaného obchodu Google Play s Intune (alternativní)
Pokud chcete synchronizovat aplikace na spravovaný obchod Google Play s Intune, nikoli přidáním přímo pomocí Intune, postupujte následovně.

> [!IMPORTANT]
> Informace zobrazené dole je alternativní metoda pro přidání aplikace spravovaný obchod Google Play pomocí Intune, jak je popsáno výše.

### <a name="synchronize-an-app-from-the-managed-google-play-store"></a>Synchronizace aplikace ze spravovaného obchodu Google Play

1. Přejděte na [spravovaný obchod Google Play](https://play.google.com/work). Přihlaste se pomocí stejného účtu, který jste použili ke konfiguraci propojení mezi Intune a Androidu Enterprise.
2. Vyhledejte a vyberte v obchodě aplikaci, kterou chcete přiřadit pomocí Intune.
3. Na stránce s aplikací vyberte **Schválit**.  
    Na tomto příkladu jsme zvolili Microsoft Excel.

    ![Tlačítko Schválit ve spravovaném obchodu Google Play](media/approve.png)

   Otevře se okno s žádostí, abyste této aplikaci udělili oprávnění k provádění různých operací.

4. Pokud chcete přijmout oprávnění aplikace a pokračovat, vyberte **Schválit**.

    ![Na tlačítko Schválit pro oprávnění aplikace](media/approve-app-permissions.png)

5. Vyberte způsob zpracovávání nových žádostí oprávnění aplikace a potom zvolte **Uložit**.

    ![Možnosti zpracovávání nových žádostí oprávnění aplikace](media/approve-app-settings.png)

    Aplikace se schválí a zobrazí v konzole pro správu. Dále můžete [synchronizovat aplikaci v pracovním profilu Androidu s Intune](apps-add-android-for-work.md#sync-a-managed-google-play-app-with-intune).

### <a name="sync-a-managed-google-play-app-with-intune"></a>Synchronizace aplikace ze spravovaného obchodu Google Play s Intune

Pokud jste aplikaci v tomto obchodě schválili, ale nevidíte ji v uzlu **Licencované aplikace** úlohy **Klientské aplikace**, vynuťte tímto způsobem okamžitou synchronizaci:

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Klientské aplikace**.
4. V podokně úlohy **Klientské aplikace** vyberte **Spravovaný obchod Google Play** v části **Nastavení**.
5. V podokně **Spravovaný obchod Google Play** zvolte **Aktualizovat**.  
    Stránka aktualizuje čas a stav poslední synchronizace.
6. V podokně úloh **Klientské aplikace** vyberte **Aplikace**.  
    Zobrazí se nově dostupná aplikace ze spravovaného obchodu Google Play.

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-work-profile-devices"></a>Přiřazení aplikace na spravovaný obchod Google Play na zařízení s Androidem Enterprise pracovním profilem

Když se aplikace objeví v **licence aplikací** uzlu **klientské aplikace** podokně úloh můžete [přiřadit stejně jako byste přiřadili jakoukoli jinou aplikaci](/intune-azure/manage-apps/deploy-apps) přiřazením na aplikaci skupiny uživatelů.

Po přiřazení se aplikace nainstaluje na zařízení, která jste určili. Uživatel zařízení nebude požádán o schválení instalace. Další informace o zařízení s Androidem Enterprise pracovním profilem, naleznete v tématu [nastavení registrace zařízení s Androidem Enterprise pracovním profilem](android-work-profile-enroll.md).

## <a name="assigning-a-managed-google-play-app-to-android-enterprise-fully-managed-devices"></a>Přiřazení spravovaný obchod Google Play aplikaci Android Enterprise plně spravovaných zařízení

[Plně spravovaná zařízení s androidem Enterprise](android-fully-managed-enroll.md) jsou přidružené k na jednoho uživatele a použít slouží výhradně pro pracovní a ne osobní zařízení vlastněných společností. Uživatelé na plně spravovaných zařízeních můžete získávají svoje aplikace k dispozici společnosti ze spravované aplikace Google Play na zařízení.

Ve výchozím nastavení plně spravovaná zařízení s Androidem Enterprise neumožní zaměstnanci k instalaci nějaké aplikace, které nejsou schválené organizací. Také zaměstnanci nebude možné odebrat všechny nainstalované aplikace proti zásad. Pokud chcete uživatelům povolit přístup k obchodu Google Play úplné instalaci aplikací, místo jenom pro přístup k schválených aplikací s spravovaný obchod Google Play storu, můžete nastavit **povolit přístup ke všem aplikacím v obchodě Google Play** k  **Povolit**. Toto nastavení má uživatel přístup všechny aplikace v obchodu Google Play pomocí firemního účtu, ale může nákupy omezená. Tím, že uživatelům přidávat nové účty do zařízení můžete odebrat omezení omezené nákupy. Tím se povolit koncovým uživatelům se budou moct koupit aplikace z obchodu Google Play pomocí osobní účty, jakož i provádět nákupy v aplikaci. Další informace najdete v tématu [nastavení zařízení s Androidem Enterprise a povolení nebo zakázání funkcí pomocí Intune](device-restrictions-android-for-work.md). 

> [!NOTE]
> Aplikace pro Microsoft Intune a aplikaci Microsoft Authenticator se nainstaluje jako požadované aplikace do všech plně spravovaná zařízení během registrace. Tyto aplikace automaticky nainstaluje podporuje podmíněný přístup a Microsoft Intune app uživatelé viděli a vyřešit problémy dodržování předpisů. 

## <a name="manage-android-enterprise-app-permissions"></a>Správa oprávnění aplikací Androidu Enterprise
Android Enterprise vyžaduje, abyste aplikace ve webové konzole spravované Google Play schválili, než je synchronizujete s Intune a přiřadíte uživatelům. Protože přes Android Enterprise můžete nepozorovaně a automaticky nainstalovat aplikace do zařízení uživatelů, je nutné přijmout oprávnění aplikací schválit za všechny svoje uživatele. Uživatelé neuvidí při instalaci žádná oprávnění aplikací, takže je důležité, abyste těmto oprávněním porozuměli.

Když vývojář aplikace aktualizuje oprávnění v nové verzi aplikace, nejsou tato oprávnění přijata automaticky, i když jste dřívější oprávnění schválili. Zařízení s předchozí verzí aplikace ji mohou dál používat. Dokud ale oprávnění neschválíte, nebude se aplikace upgradovat. Na zařízení, ve kterých tato aplikace není nainstalovaná, nejde aplikace nainstalovat, dokud neschválíte její nová oprávnění. 

### <a name="update-app-permissions"></a>Aktualizace oprávnění aplikace

Pravidelně navštěvujte spravovanou konzolu Google Play a kontrolujte nová oprávnění. Obchod Google Play můžete nastavit tak, aby byl vám nebo jiným uživatelům zaslán e-mail, pokud bude schválená aplikace vyžadovat nová oprávnění. Pokud přiřadíte aplikaci a zjistíte, že není na zařízeních nainstalovaná, zkontrolujte tímto způsobem nová oprávnění:

1. Přejděte na [Google Play](https://play.google.com/work).
2. Přihlaste se pod účtem Google, který jste použili k publikování a schválení aplikací.
3. Vyberte kartu **Aktualizace** a zkontrolujte, jestli některé aplikace nevyžadují aktualizaci.  
    Všechny zde uvedené aplikace vyžadují nová oprávnění a nepřiřadí se, dokud nebudou použita.

Případně ale můžete obchod Google Play nastavit tak, aby automaticky schvaloval nová oprávnění pro každou z aplikací.

## <a name="additional-managed-google-play-app-reporting-for-android-enterprise-work-profile-devices"></a>Vytváření sestav pro zařízení s Androidem Enterprise pracovním profilem dalších aplikace spravovaný obchod Google Play

Pro spravovaný obchod Google Play aplikace nasazené na zařízení s Androidem Enterprise pracovním profilem můžete zobrazit číslo verze konkrétní aplikace nainstalované v zařízení. To platí pro pouze požadované aplikace. 

## <a name="working-with-a-line-of-business-app-from-the-managed-google-play-store"></a>Používání obchodní aplikace ze spravovaného obchodu Google Play

1. Přihlaste se k [konzole pro vývojáře Google Play](https://play.google.com/apps/publish) pod stejným účtem, který jste použili ke konfiguraci propojení mezi Intune a Androidu Enterprise.  
    Pokud se přihlašujete poprvé, musíte se zaregistrovat a zaplatit poplatek, abyste se stali členy programu pro vývojáře Google.
2. V této konzole zvolte **Přidat novou aplikaci**.
3. Informace o vaší aplikaci nahrajete a zadáte stejným způsobem jako při publikování jakékoli jiné aplikace v obchodě Google Play. Musíte ale vybrat **Zpřístupnit tuto aplikaci pouze pro moji organizaci (<*název organizace*>)**.

    ![Zpřístupnění aplikace jen pro vaši organizaci](media/restrict.png)

    Tato operace zpřístupní aplikaci ve vaší organizaci. Nebude dostupná ve veřejném obchodu Google Play.

    Další informace o nahrávání a publikování aplikací pro Android najdete v [nápovědě ke konzole pro vývojáře Google](https://support.google.com/googleplay/android-developer/answer/113469).
4. Po publikování vaší aplikace, přihlaste se k [spravovaný obchod Google Play storu](https://play.google.com/work) pod stejným účtem, který jste použili ke konfiguraci propojení mezi Intune a Androidu Enterprise.
5. Ověřte si, že se v uzlu **Aplikace** tohoto obchodu zobrazuje aplikace, kterou jste publikovali.  
    Synchronizace s Intune bude automaticky schválená.

## <a name="delete-managed-google-play-apps"></a>Odstranění aplikace spravovaného obchodu Google Play
Pokud je to nezbytné, můžete odstranit spravované aplikace Google Play v Microsoft Intune. Pokud chcete odstranit spravovanou aplikaci služby Google Play, otevřete Microsoft Intune v Azure portal a vyberte **klientské aplikace** > **aplikace**. Ze seznamu aplikací vyberte symbol tří teček (...) napravo od spravované aplikace Google Play a potom vyberte **odstranit** ze zobrazeného seznamu. Když odstraníte spravované aplikace Google Play ze seznamu aplikací, je automaticky neschválených spravované aplikace Google Play.

## <a name="next-steps"></a>Další postup

- [Přiřazení aplikací skupinám](apps-deploy.md)
