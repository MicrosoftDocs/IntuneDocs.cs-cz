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
ms.sourcegitcommit: 519b66c94f3d056e060ed11e1a3d7d6d118a94fb
ms.openlocfilehash: 5f48303dd28627f961f8c2cfd38f8977354e2724


---

# Povolení registrace zařízení s Androidem for Work

Pokud chcete umožnit správu zařízení s Androidem for Work, musíte do Intune přidat vazbu na Android for Work. Abyste mohli registrovat zařízení, která podporují Android for Work, ale byla předtím zaregistrovaná jako zařízení s běžným Androidem, musíte zrušit registraci těchto zařízení a pak je znovu zaregistrovat.

## Přidání vazby na Android for Work do Intune

1. **Nastavení Intune**<br>
Pokud jste to ještě neudělali, připravte se na správu mobilních zařízení [nastavením autority pro správu mobilních zařízení](prerequisites-for-enrollment.md#set-mobile-device-management-authority) na **Microsoft Intune** a nastavením správy MDM.

2. **Konfigurace vazby na Android for Work**<br>
    Jako správce otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com), přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **Android for Work** a kliknutím na **Konfigurovat** otevřete web Google Play for Work pro Android. Tento web se otevře v nové záložce prohlížeče.

3. **Přihlášení ke Googlu**<br>
   Na přihlašovací stránce Googlu zadejte účet Google, který bude přidružený ke všem úlohám správy Androidu for Work v tomto tenantovi. Může to být účet Google sdílený mezi správci, kteří spravují Intune. Jedná se o účet Google, který vaše organizace používá ke správě a publikování aplikací v konzole Play for Work.

4. **Zadání podrobností o organizaci**<br>
   Do pole **Název organizace** zadejte název své organizace. Jako **Poskytovatel EMM (Enterprise Mobility Management)** by se měl zobrazit *Microsoft Intune*. Vyjádřete souhlas se smlouvou pro Android for Work a klikněte na **Potvrdit**. Vaše žádost bude zpracována.

## Nastavení registrace Androidu for Work
   Android for Work je podporovaný jen na určitých zařízeních s Androidem. Přečtěte si [požadavky Googlu na Android for Work](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012 style="target=new_window").  Zařízení, které podporuje Android for Work, bude podporovat také správu konvenčního Androidu.  Intune umožňuje určit, jak se mají spravovat zařízení podporující Android for Work:

   - **Spravovat všechna zařízení jako Android** – (zakázáno): Všechna zařízení s Androidem, včetně zařízení podporujících Android for Work, se zaregistrují jako zařízení s konvenčním Androidem.
   - **Spravovat podporovaná zařízení jako Android for Work** – (povoleno): Všechna zařízení, která podporují Android for Work, se zaregistrují jako zařízení s Androidem for Work. Jakékoli zařízení s Androidem, které nepodporuje Android for Work, se zaregistruje jako zařízení s konvenčním Androidem.
   - **Spravovat podporovaná zařízení pro uživatele v těchto skupinách jako Android for Work** – (testovací): Umožňuje zacílit správu Androidu for Work na omezenou sadu uživatelů. Jen zařízení členů vybraných skupin, kteří zaregistrují zařízení podporující Android for Work, se zaregistrují jako zařízení s Androidem for Work. Všechna ostatní se zaregistrují jako zařízení s Androidem.

## Další postup pro Android for Work
Po konfiguraci vazby na Android for Work a nastavení následně můžete:
- [Nasadit aplikace pro Android for Work](android-for-work-apps.md)
- [Přidat zásady konfigurace pro Android for Work](android-for-work-policy-settings-in-microsoft-intune.md)

## Zrušení vazby na účet pro správu Androidu for Work

Registraci a správu Androidu for Work můžete vypnout. Při kliknutí na **Zrušit vazbu** se zruší registrace všech zaregistrovaných zařízení s Androidem for Work a odebere se vztah mezi účtem Android for Work a službou Intune.

### Jak zrušit vazbu na účet Android for Work

1. **Zrušení vazby na Android for Work**<br>
    Jako správce otevřete [konzolu pro správu Microsoft Intune](http://manage.microsoft.com), přejděte na **Správa** &gt; **Správa mobilních zařízení** &gt; **Android for Work** a klikněte na **Zrušit vazbu**.

2. **Souhlas s odstraněním vazby na Android for Work**<br>
  Kliknutím na **Ano** odstraníte vazbu a zrušíte v Intune registraci všech zařízení s Androidem for Work.



<!--HONumber=Oct16_HO2-->


