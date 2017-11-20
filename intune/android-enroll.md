---
title: "Registrace zařízení s Androidem v Intune | Microsoft Docs"
titlesuffix: Azure portal
description: "Přečtěte si, jak zaregistrovat zařízení s Androidem v Intune."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 68d93fe98b89f27c947e07d79eca9a0e02dea582
ms.sourcegitcommit: ce35790090ebe768d5f75c108e8d5934fd19c8c7
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="enroll-android-devices"></a>Registrace zařízení s Androidem

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako správce Intune můžete spravovat zařízení s Androidem včetně zařízení používajících Samsung Knox Standard. Můžete také spravovat pracovní profily na [zařízeních s Androidem for Work](#enable-enrollment-of-android-for-work-devices).

U zařízení, která používají Samsung Knox Standard, se podporuje správa více uživatelů pomocí Intune. To znamená, že uživatelé se můžou přihlásit k zařízení pomocí svých přihlašovacích údajů Azure AD a odhlásit se od něho. Zařízení je centrálně spravované bez ohledu na to, jestli se používá. Když se uživatelé přihlásí, mají přístup k aplikacím a také se na ně vztahují všechny zásady. Po odhlášení uživatelů se všechna data aplikací vymažou.

## <a name="prerequisite"></a>Předpoklad

Při přípravě na správu mobilních zařízení musíte nastavit autoritu pro správu mobilních zařízení (MDM) na **Microsoft Intune**. Pokyny k tomu najdete v článku [Nastavení autority MDM](mdm-authority-set.md). Tato možnost se nastavuje jenom jednou při prvním nastavování Intune pro správu mobilních zařízení.

## <a name="set-up-android-enrollment"></a>Nastavení registrace zařízení s Androidem

Standardně je služba Intune nastavená tak, aby umožňovala registraci zařízení používajících Android a Samsung Knox Standard.

Pokud chcete blokovat registraci zařízení s Androidem nebo blokovat jenom zařízení s Androidem v osobním vlastnictví, přečtěte si téma [Nastavení omezení typu zařízení](enrollment-restrictions-set.md).

Aby bylo možné povolit správu zařízení, musí uživatelé zaregistrovat svoje zařízení tak, že si stáhnou aplikaci Portál společnosti Intune (je dostupná na Google Play) a pak otevřou tuto aplikaci a budou postupovat podle pokynů. Když jsou zařízení s Androidem spravovaná, můžete [přiřazovat zásady dodržování předpisů](compliance-policy-create-android.md), [spravovat aplikace](app-management.md) a provádět další akce.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Povolení registrace zařízení s Androidem for Work

Pokud chcete umožnit správu pracovního profilu na zařízeních, která [podporují Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), musíte do Intune přidat vazbu na Android for Work. Abyste mohli registrovat zařízení, která podporují Android for Work, ale byla předtím zaregistrovaná jako běžná zařízení s Androidem, musíte registraci těchto zařízení zrušit a pak je znovu zaregistrovat.

Při registraci zařízení s Androidem for Work pomocí účtu [správce registrace zařízení](device-enrollment-manager-enroll.md) platí omezení, že pomocí jednoho účtu je možné zaregistrovat maximálně 10 zařízení.

## <a name="add-android-for-work-binding-for-intune"></a>Přidání vazby na Android for Work do Intune

1. **Nastavení Intune MDM**<br>
Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](mdm-authority-set.md) na **Microsoft Intune**.
2. **Konfigurace vazby na Android for Work**<br>
    Jako správce Intune na portálu Azure Portal vyberte **Další služby** > **Monitorování + správa** > **Intune**.

   a. V okně **Intune** vyberte **Registrace zařízení** > **Registrace Androidu for Work**, zvolte **Konfigurovat** a otevřete web Androidu for Work na Google Play. Web se otevře v prohlížeči na nové kartě.
   ![Snímek obrazovky zobrazující odkaz na konfiguraci vazby na Android for Work](./media/android-work-bind.png)

   b. **Přihlášení ke Googlu**<br>
   Na přihlašovací stránce Googlu zadejte účet Google, který bude přidružený ke všem úlohám správy Androidu for Work v tomto tenantovi. Jedná se o účet Google, který správci IT ve vaší společnosti sdílejí a používají ke správě a publikování aplikací v konzole Play for Work.

   c. **Zadání podrobností o organizaci**<br>
   Do pole **Název organizace** zadejte název vaší společnosti. Jako **Poskytovatel EMM (Enterprise Mobility Management)** by se měl zobrazit **Microsoft Intune**. Vyjádřete souhlas se smlouvou pro Android for Work a zvolte **Potvrdit**. Vaše žádost bude zpracována.

## <a name="specify-android-for-work-enrollment-settings"></a>Nastavení registrace Androidu for Work
   Android for Work se podporuje jenom na určitých zařízeních s Androidem. Přečtěte si [požadavky Googlu na Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window"). Zařízení, které podporuje Android for Work, podporuje také správu konvenčního Androidu. Intune umožňuje určit, jak se mají spravovat zařízení podporující Android for Work:

   - **Spravovat všechna zařízení jako Android for Work:** Všechna zařízení s Androidem včetně zařízení podporujících Android for Work se zaregistrují jako zařízení s konvenčním Androidem.
   - **Spravovat podporovaná zařízení jako Android for Work:** Všechna zařízení, která podporují Android for Work, se zaregistrují jako zařízení s Androidem for Work. Jakékoli zařízení s Androidem, které nepodporuje Android for Work, se zaregistruje jako zařízení s konvenčním Androidem.
   - **Spravovat podporovaná zařízení pro uživatele v těchto skupinách jako Android for Work:** Můžete pro správu Androidu for Work určit omezenou sadu uživatelů. Jen zařízení členů vybraných skupin, kteří zaregistrují zařízení podporující Android for Work, se zaregistrují jako zařízení s Androidem for Work. Všechna ostatní se zaregistrují jako zařízení s Androidem. To se hodí při pilotním nasazení Androidu for Work.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům

Informujte uživatele, že mají přejít na web Google Play, stáhnout si aplikaci Portál společnosti Intune a pak tuto aplikaci otevřít a zaregistrovat svoje zařízení podle pokynů. Aplikace provede uživatele procesem registrace a zobrazí informace o tom, co můžou očekávat a co uvidí nebo neuvidí správci IT na svých zařízeních.

Uživatelům také můžete poslat odkaz na postup online registrace: [Zaregistrujte svoje zařízení se systémem Android v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Informace o dalších uživatelských úkolech najdete v článcích:

- [Materiály o prostředí Microsoft Intune pro koncové uživatele](end-user-educate.md)
- [Použití zařízení Android s Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbind-your-android-for-work-administrative-account"></a>Zrušení vazby na účet pro správu Androidu for Work

Registraci a správu Androidu for Work můžete vypnout. Výběrem možnosti **Zrušit vazbu** v konzole pro správu Intune se odebere registrace všech zaregistrovaných zařízení s Androidem for Work. Odebere se tím také vztah mezi účtem Androidu for Work a Intune.

### <a name="to-unbind-an-android-for-work-account"></a>Zrušení vazby na účet Androidu for Work

1. **Zrušení vazby na Android for Work**<br>
    Jako správce Intune na portálu Azure Portal vyberte **Další služby** > **Monitorování + správa** > **Intune**.  V okně **Intune** zvolte **Registrace zařízení** > **Registrace Androidu for Work** a pak **Zrušit vazbu**.

2. **Souhlas s odstraněním vazby na Android for Work**<br>
  Výběrem možnosti **Ano** odstraníte vazbu a zrušíte v Intune registraci všech zařízení s Androidem for Work.
