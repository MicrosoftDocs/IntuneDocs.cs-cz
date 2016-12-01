---
title: "Nastavení správy pro Android for Work | Microsoft Intune"
description: "Pomocí Microsoft Intune můžete u zařízení s Androidem for Work povolit správu mobilních zařízení (MDM)."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b2fdcea9-9ad7-4d73-88e2-854b7a774bb2
translationtype: Human Translation
ms.sourcegitcommit: 56988f0a69e6ff281439e6e77d1814ec130c8b49
ms.openlocfilehash: d5000db99bf2325e062274e29bc663f20d37d369


---

# <a name="enable-enrollment-of-android-for-work-devices"></a>Povolení registrace zařízení s Androidem for Work

[!INCLUDE[wit_nextref](../includes/afw_rollout_disclaimer.md)]

Pokud chcete umožnit správu zařízení s Androidem for Work, musíte do Intune přidat vazbu na Android for Work. Abyste mohli registrovat zařízení, která podporují Android for Work, ale byla předtím zaregistrovaná jako zařízení s běžným Androidem, musíte zrušit registraci těchto zařízení a pak je znovu zaregistrovat.

## <a name="add-android-for-work-binding-for-intune"></a>Přidání vazby na Android for Work do Intune

1. **Nastavení Intune**<br>
Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](prerequisites-for-enrollment.md#set-mobile-device-management-authority) na **Microsoft Intune** a nastavením správy MDM.

2. **Konfigurace vazby na Android for Work**<br>
   Přihlaste se jako správce a otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com), přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **Android for Work** a klikněte na **Konfigurovat**. Otevře se web Android for Work v obchodě Google Play. Tento web se otevře v nové záložce prohlížeče.

3. **Přihlášení ke Googlu**<br>
   Na přihlašovací stránce Googlu zadejte účet Google, který bude přidružený ke všem úlohám správy Androidu for Work v tomto tenantovi. Může to být účet Google sdílený mezi správci, kteří spravují Intune. Jedná se o účet Google, který vaše organizace používá ke správě a publikování aplikací v konzole Play for Work.

4. **Zadání podrobností o organizaci**<br>
   Do pole **Název organizace** zadejte název své organizace. Jako **Poskytovatel EMM (Enterprise Mobility Management)** by se měl zobrazit *Microsoft Intune*. Vyjádřete souhlas se smlouvou pro Android for Work a klikněte na **Potvrdit**. Vaše žádost bude zpracována.

## <a name="specify-android-for-work-enrollment-settings"></a>Nastavení registrace Androidu for Work
   Android for Work je podporovaný jen na určitých zařízeních s Androidem. Přečtěte si [požadavky Googlu na Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window").  Zařízení, které podporuje Android for Work, bude podporovat také správu konvenčního Androidu.  Intune umožňuje určit, jak se mají spravovat zařízení podporující Android for Work:

   - **Spravovat všechna zařízení jako Android** – (zakázáno): Všechna zařízení s Androidem, včetně zařízení podporujících Android for Work, se zaregistrují jako zařízení s konvenčním Androidem.
   - **Spravovat podporovaná zařízení jako Android for Work** – (povoleno): Všechna zařízení, která podporují Android for Work, se zaregistrují jako zařízení s Androidem for Work. Jakékoli zařízení s Androidem, které nepodporuje Android for Work, se zaregistruje jako zařízení s konvenčním Androidem.
   - **Spravovat podporovaná zařízení pro uživatele v těchto skupinách jako Android for Work** – (testovací): Umožňuje zacílit správu Androidu for Work na omezenou sadu uživatelů. Jen zařízení členů vybraných skupin, kteří zaregistrují zařízení podporující Android for Work, se zaregistrují jako zařízení s Androidem for Work. Všechna ostatní se zaregistrují jako zařízení s Androidem.

## <a name="next-steps-for-android-for-work"></a>Další postup pro Android for Work
Po konfiguraci vazby na Android for Work a nastavení následně můžete:
- [Nasadit aplikace pro Android for Work](android-for-work-apps.md)
- [Přidat zásady konfigurace Androidu for Work](android-for-work-policy-settings-in-microsoft-intune.md)

## <a name="unbinding-your-android-for-work-administrative-account"></a>Zrušení vazby na účet pro správu Androidu for Work

Registraci a správu Androidu for Work můžete vypnout. Při kliknutí na **Zrušit vazbu** se zruší registrace všech zaregistrovaných zařízení s Androidem for Work a odebere se vztah mezi účtem Android for Work a službou Intune.

### <a name="how-to-unbind-an-android-for-work-account"></a>Jak zrušit vazbu na účet Android for Work

1. **Zrušení vazby na Android for Work**<br>
    Přihlaste se jako správce a otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com), přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **Android for Work** a klikněte na **Zrušit vazbu**.

2. **Souhlas s odstraněním vazby na Android for Work**<br>
  Kliknutím na **Ano** odstraníte vazbu a zrušíte v Intune registraci všech zařízení s Androidem for Work.



<!--HONumber=Nov16_HO1-->


