---
title: "Registrace zařízení s Androidem v Intune"
titleSuffix: Intune on Azure
description: "Zjistěte, jak zaregistrovat zařízení s Androidem v Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f276d98c-b077-452a-8835-41919d674db5
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 183e60af4d6174c18fc3883f2cdd9827505d2aba
ms.sourcegitcommit: 2ee1e8248814d74cef80b609a8e43f59fa0b2618
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/09/2017
---
# <a name="enroll-android-devices"></a>Registrace zařízení s Androidem

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune vám jako správci Intune umožňuje spravovat zařízení s Androidem včetně zařízení používajících Samsung Knox Standard. Můžete také spravovat pracovní profily na [zařízeních s Androidem for Work](#enable-enrollment-of-android-for-work-devices).

U zařízení, která používají Samsung KNOX Standard, je podporována správa více uživatelů pomocí Intune. To znamená, že koncoví uživatelé se můžou k zařízení přihlašovat a ze zařízení odhlašovat pomocí svých přihlašovacích údajů Azure AD. Zařízení je centrálně spravované bez ohledu na to, jestli se zrovna používá. Když se koncoví uživatelé přihlásí, mají přístup k aplikacím a také se na ně aplikují všechny zásady. Po odhlášení uživatelů se všechna data aplikací vymažou.

## <a name="prerequisite"></a>Předpoklad

Při přípravě na správu mobilních zařízení musíte nastavit autoritu MDM na **Microsoft Intune**. Pokyny k tomu najdete v článku [Nastavení autority MDM](mdm-authority-set.md). Tato možnost se nastavuje jenom jednou při prvním nastavování Intune pro správu mobilních zařízení.

## <a name="set-up-android-enrollment"></a>Nastavení registrace zařízení s Androidem

Standardně je služba Intune nastavená tak, aby umožňovala registraci zařízení používajících Android a Samsung Knox Standard.

Pokud chcete blokovat registraci zařízení s Androidem nebo blokovat jenom zařízení s Androidem v osobním vlastnictví, přečtěte si téma [Nastavení omezení typu zařízení](enrollment-restrictions-set.md).

Aby bylo možné povolit správu zařízení, musí uživatelé zaregistrovat svoje zařízení tak, že si stáhnou aplikaci Intune Company Portal, která je dostupná na Google Play, a pak otevřou tuto aplikaci a zaregistrují se podle pokynů. Když jsou zařízení s Androidem spravována, můžete [přiřadit zásady dodržování předpisů](compliance-policy-create-android.md), [spravovat aplikace](app-management.md) a další.

## <a name="enable-enrollment-of-android-for-work-devices"></a>Povolení registrace zařízení s Androidem for Work

Pokud chcete umožnit správu pracovního profilu na zařízeních, která [podporují Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012), musíte do Intune přidat vazbu na Android for Work. Abyste mohli registrovat zařízení, která podporují Android for Work, ale byla předtím zaregistrovaná jako běžná zařízení s Androidem, musíte registraci těchto zařízení zrušit a pak je znovu zaregistrovat.

## <a name="add-android-for-work-binding-for-intune"></a>Přidání vazby na Android for Work do Intune

1. **Nastavení Intune MDM**<br>
Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](mdm-authority-set.md) na **Microsoft Intune**.
2. **Konfigurace vazby na Android for Work**<br>
    Jako správce Intune na portálu Azure Portal vyberte **Další služby** > **Monitorování + správa** > **Intune**.

    1. V okně **Intune** vyberte **Registrace zařízení** > **Registrace Androidu for Work**, klikněte na **Konfigurovat** a otevřete web Androidu for Work na Google Play. Tento web se otevře v nové záložce prohlížeče.
  ![Snímek obrazovky zobrazující odkaz na konfiguraci vazby na Android for Work](./media/android-work-bind.png)

    2. **Přihlášení ke Googlu**<br>
   Na přihlašovací stránce Googlu zadejte účet Google, který bude přidružený ke všem úlohám správy Androidu for Work v tomto tenantovi. Jedná se o účet Google sdílený správci IT ve vaší organizaci, kteří spravovali a publikovali aplikace v konzole Play for Work.

    3. **Zadání podrobností o organizaci**<br>
   Do pole **Název organizace** zadejte název své organizace. Jako **Poskytovatel EMM (Enterprise Mobility Management)** by se měl zobrazit *Microsoft Intune*. Vyjádřete souhlas se smlouvou pro Android for Work a klikněte na **Potvrdit**. Vaše žádost bude zpracována.

## <a name="specify-android-for-work-enrollment-settings"></a>Nastavení registrace Androidu for Work
   Android for Work je podporovaný jen na určitých zařízeních s Androidem. Přečtěte si [požadavky Googlu na Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window"). Zařízení, které podporuje Android for Work, bude podporovat také správu konvenčního Androidu.  Intune umožňuje určit, jak se mají spravovat zařízení podporující Android for Work:

   - **Spravovat všechna zařízení jako Android** – Všechna zařízení s Androidem, včetně zařízení podporujících Android for Work, se zaregistrují jako zařízení s konvenčním Androidem.
   - **Spravovat podporovaná zařízení jako Android for Work** – Všechna zařízení, která podporují Android for Work, se zaregistrují jako zařízení s Androidem for Work. Jakékoli zařízení s Androidem, které nepodporuje Android for Work, se zaregistruje jako zařízení s konvenčním Androidem.
   - **Spravovat podporovaná zařízení pro uživatele v těchto skupinách jako Android for Work** – Umožňuje zacílit správu Androidu for Work na omezenou sadu uživatelů. Jen zařízení členů vybraných skupin, kteří zaregistrují zařízení podporující Android for Work, se zaregistrují jako zařízení s Androidem for Work. Všechna ostatní se zaregistrují jako zařízení s Androidem. To se hodí při pilotním nasazení Androidu for Work.

<!--  ## Next steps for Android for Work
After configuring the Android for Work binding and settings, you can do the following:
- [Deploy Android for Work apps](android-for-work-apps.md)
- [Add Android for Work configuration policies](android-for-work-policy-settings-in-microsoft-intune.md)  -->

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a>Informujte uživatele, jak můžou svá zařízení zaregistrovat, aby získali přístup k firemním prostředkům

Budete muset říct koncovým uživatelům, že mají přejít na web Google Play a stáhnout si aplikaci Portál společnosti služby Intune a pak aplikaci otevřít a zaregistrovat svá zařízení podle pokynů. Aplikace provede uživatele procesem registrace a zobrazí informace o tom, co můžou očekávat a co uvidí nebo neuvidí správci IT na svých zařízeních.

Uživatelům také můžete poslat odkaz na postup online registrace: [Zaregistrujte svoje zařízení se systémem Android v Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).

Informace o dalších úlohách koncových uživatelů najdete v článcích:

- [Materiály o prostředí Microsoft Intune pro koncové uživatele](end-user-educate.md)
- [Použití zařízení Android s Intune](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Zrušení vazby na účet pro správu Androidu for Work

Registraci a správu Androidu for Work můžete vypnout. Při kliknutí na možnost pro **zrušení vazby** v konzole pro správu Intune se zruší registrace všech zaregistrovaných zařízení s Androidem for Work a odebere se vztah mezi účtem Android for Work a službou Intune.

### <a name="how-to-unbind-an-android-for-work-account"></a>Jak zrušit vazbu na účet Android for Work

1. **Zrušení vazby na Android for Work**<br>
    Jako správce Intune na portálu Azure Portal vyberte **Další služby** > **Monitorování + správa** > **Intune**.  V okně **Intune** zvolte **Registrace zařízení** > **Registrace Androidu for Work** a klikněte na **Zrušit vazbu**.

2. **Souhlas s odstraněním vazby na Android for Work**<br>
  Kliknutím na **Ano** odstraníte vazbu a zrušíte v Intune registraci všech zařízení s Androidem for Work.
