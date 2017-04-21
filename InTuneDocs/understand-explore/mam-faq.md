---
title: "Časté otázky ke správě mobilních aplikací (MAM) a ochraně aplikací"
description: "Tento článek poskytuje odpovědi na některé časté otázky ke správě mobilních aplikací (MAM) Intune a ochraně aplikací Intune."
keywords: 
author: oydang
ms.author: oydang
manager: mtillman
ms.date: 01/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 149def73-9d08-494b-97b7-4ba1572f0623
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ab6d9b6b296fb4e1fb0aaa9496fede28976728dc
ms.openlocfilehash: aea41c86e1fe784d6234f4ff90e299632b2a6d5f
ms.lasthandoff: 04/14/2017


---

# <a name="frequently-asked-questions-about-mam-and-app-protection"></a>Časté otázky ke správě mobilních aplikací (MAM) a ochraně aplikací

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Tento článek poskytuje odpovědi na některé časté otázky ke správě mobilních aplikací (MAM) Intune a ochraně aplikací Intune.

## <a name="mam-basics"></a>Základní informace o MAM


**Co je MAM?** [Správa mobilních aplikací (MAM) Intune](../deploy-use/overview-of-app-lifecycle-in-microsoft-intune.md) představuje sadu funkcí Intune pro správu, s kterými můžete publikovat, doručovat, konfigurovat, zabezpečovat, monitorovat a aktualizovat mobilní aplikace pro uživatele.

**Jaké jsou výhody ochrany aplikací pomocí MAM?** MAM chrání data organizace v rámci aplikace. Díky funkci MAM bez registrace zařízení (MAM-WE) jde pracovní nebo školní aplikaci, která obsahuje citlivá data, spravovat prakticky na jakémkoliv zařízení, včetně osobních zařízení, která uživatelé používají pracovně (BYOD, bring-your-own-device). Mnoho kancelářských aplikací, jako jsou například aplikace Microsoft Office, jde spravovat přes Intune MAM. Podívejte se do oficiálního seznamu [aplikací podporujících Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps), který je veřejně přístupný.

**Jaké konfigurace zařízení MAM podporuje?** Intune MAM podporuje dvě konfigurace:
  1. **Intune MDM + MAM:** Toto je první konfigurace podporovaná správou MAM při prvním spuštění. Správci IT můžou spravovat aplikace pomocí MAM a zásad ochrany aplikací jenom na zařízeních, která jsou zaregistrovaná ve správě mobilních zařízení Intune (MDM). Pokud zákazníci chtějí spravovat aplikace pomocí MDM + MAM, měli by používat samostatnou konzolu Intune na http://manage.microsoft.com.

  2. **MAM bez registrace zařízení:** MAM bez registrace zařízení, neboli MAM-WE, umožňuje správcům IT spravovat aplikace pomocí MAM a zásad ochrany aplikací na zařízeních, která nejsou zaregistrovaná ve správě mobilních zařízení Intune. To znamená, že aplikace je možné spravovat pomocí Intune na zařízeních, která jsou zaregistrovaná u jiných poskytovatelů EMM. Pokud zákazníci chtějí spravovat aplikace pomocí MAM-WE, měli by používat konzolu Intune na portálu Azure na stránce http://portal.azure.com.


## <a name="app-protection-policies"></a>Zásady ochrany aplikací

**Co jsou zásady ochrany aplikací**? Zásady ochrany aplikací jsou pravidla, která zajistí, že data organizace budou zabezpečená nebo vázaná ve spravované aplikaci. Zásada může být pravidlo, které je vynuceno, když se uživatel pokusí pracovat s firemními daty nebo je přesunout, nebo sada akcí, které jsou zakázané nebo monitorované, pokud je uživatel uvnitř aplikace.

**Jaké jsou příklady zásad ochrany aplikací?** Podrobné informace o každém nastavení zásad ochrany aplikací najdete v tématech [Nastavení zásad ochrany aplikací pro Android](../deploy-use/android-mam-policy-settings.md) a [Nastavení zásad ochrany aplikací pro iOS](../deploy-use/ios-mam-policy-settings.md).

## <a name="apps-you-can-manage-with-app-protection-policies"></a>Aplikace, které se dají spravovat pomocí zásad ochrany aplikací

**Které aplikace se dají spravovat pomocí zásad ochrany aplikací?** Zásadami ochrany aplikací Intune se dá spravovat každá aplikace, u které byla tato podpora povolena sadou [Intune App SDK](../develop/intune-app-sdk.md) nebo která byla zabalena nástrojem [Intune App Wrapping](../deploy-use/decide-how-to-prepare-apps-for-mobile-application-management-with-microsoft-intune.md). Podívejte se do oficiálního seznamu [aplikací podporujících Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-apps), který je veřejně přístupný.

**Jaké jsou základní požadavky na používání zásad ochrany aplikací v aplikaci s podporou Intune?**
  1. Koncový uživatel musí mít účet Azure Active Directory (AAD). Pokud se chcete dozvědět, jak se vytvářejí uživatelé Intune v Azure Active Directory, přečtěte si [Přidání uživatelů a udělení oprávnění pro správu v Intune](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3.md).

  2. Koncový uživatel musí mít ke svému účtu Azure Active Directory přiřazenou licenci pro Microsoft Intune. Informace o tom, jak se přiřazují licence Intune koncovým uživatelům, najdete v článku [Správa licencí Intune](../get-started/start-with-a-paid-subscription-to-microsoft-intune-step-4.md).

  3. Koncový uživatel musí patřit do skupiny zabezpečení, která je cílem zásady ochrany aplikace. Stejná zásada ochrany aplikace musí mít za cíl konkrétní používanou aplikaci. Zásady ochrany aplikací se dají vytvářet a nasazovat v konzole Intune na [portálu Azure](http://portal.azure.com). Skupiny zabezpečení se aktuálně dají vytvářet na [portálu Office](http://portal.office.com).

  4. Koncový uživatel se musí do aplikace přihlásit pomocí svého účtu AAD.

**Jaké jsou další požadavky na používání [mobilní aplikace Outlook](https://www.microsoft.com/outlook-com/mobile/)?**

  1. Koncový uživatel musí mít v zařízení nainstalovanou mobilní aplikaci Outlook.

  2. Koncový uživatel musí mít poštovní schránku [Office 365 Exchange Online](https://products.office.com/exchange/exchange-online) a licenci propojenou se svým účtem Azure Active Directory.

  >[!NOTE]
  > Mobilní aplikace Outlook aktuálně podporuje jenom Microsoft Exchange Online a nepodporuje místní Exchange nebo Exchange v Office 365 Dedicated.

**Jaké jsou další požadavky na používání aplikací [Word, Excel a PowerPoint](https://products.office.com/business/office)?**

  1. Koncový uživatel musí mít licenci pro [Office 365 Business nebo Enterprise](https://products.office.com/business/compare-more-office-365-for-business-plans) propojenou se svým účtem Azure Active Directory. Předplatné musí obsahovat aplikace Office na mobilních zařízeních a účet pro ukládání na cloud se službou [OneDrive pro firmy](https://onedrive.live.com/about/business/). Licence na Office 365 se dají přiřadit na [portálu Office](http://portal.office.com) podle těchto [pokynů](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc).

  2. Koncový uživatel musí mít v zařízení nainstalovanou aplikaci [OneDrive](https://onedrive.live.com/about/) a přihlásit se se svým účtem AAD.

  3. Aplikace OneDrive musí být cílem pro zásadu ochrany aplikace nasazenou pro koncového uživatele.

  >[!NOTE]
  > Mobilní aplikace Office aktuálně podporují jenom SharePoint Online a ne místní SharePoint.

**Proč je pro Office nutný OneDrive?** Intune označuje veškerá data v aplikaci jako podniková (firemní) nebo osobní. Data se považují za podniková, když pocházejí z firemního umístění. U aplikací Office považuje Intune za firemní následující umístění: e-mail (Exchange) nebo cloudové úložiště (aplikace OneDrive s účtem OneDrive pro firmy).

**Jaké jsou další požadavky na používání Skypu pro firmy?** Viz licenční požadavky [Skypu pro firmy](https://products.office.com/skype-for-business/it-pros).
  >[!NOTE]
  > Mobilní aplikace Skype pro firmy aktuálně podporuje jenom Online Skype pro firmy.

## <a name="app-protection-features"></a>Funkce ochrany aplikací

**Co je podpora více identit?** Podpora více identit je schopnost sady Intune App SDK použít zásady ochrany aplikací jenom na pracovní nebo školní účet přihlášený k aplikaci. Pokud se k aplikaci přihlásí osobní účet, zůstanou data nedotčená.

**Co je účelem podpory více identit?** Podpora více identit umožňuje, aby se aplikace pro podnikové i běžné zákazníky (tj. aplikace Office) vydávaly veřejně s funkcemi ochrany aplikací Intune pro podnikové účty.

**Kdy se zobrazí obrazovka s PINem?** Obrazovka s PINem Intune se zobrazí jenom tehdy, když se uživatel pokusí v aplikaci získat přístup k podnikovým datům. Například v aplikacích Word, Excel a PowerPoint se zobrazí, když se koncový uživatel pokusí otevřít dokument z OneDrivu pro firmy (za předpokladu, že jste úspěšně nasadili zásadu ochrany aplikace, která vynucuje PIN).

**Jak je na tom aplikace Outlook s více identitami?** Outlook má kombinované zobrazení osobních a podnikových e-mailů, proto při spuštění zobrazí výzvu k zadání PINu Intune.

**Co je PIN aplikace Intune?** Osobní identifikační číslo (PIN) je heslo, kterým se ověřuje, že s daty organizace pracuje v aplikaci správný uživatel.

  1. **Když je uživatel vyzván k zadání PINu?** Intune vyzve uživatele k zadání PINu aplikace, když se uživatel chystá pracovat s podnikovými daty. V aplikacích s více identitami, jako Word, Excel a PowerPoint, bude uživatel vyzván k zadání PINu při pokusu o otevření podnikového souboru nebo dokumentu. V aplikacích s jednou identitou, například obchodní aplikace podporované díky nástroji Intune App Wrapping, se PIN vyžaduje při spuštění, protože sada Intune App SDK ví, že prostředí uživatele v aplikaci bude vždy podnikové.

  2. **Je PIN bezpečný?** PIN slouží k tomu, aby v aplikaci povolil pracovat s daty organizace jenom správnému uživateli. Proto se koncový uživatel musí přihlásit s pracovním nebo školním účtem, aby mohl nastavit nebo resetovat PIN pro aplikaci Intune. Toto ověření zpracovává Azure Active Directory prostřednictvím zabezpečené výměny tokenu a sada Intune App SDK do procesu nevidí. Z hlediska zabezpečení je nejlepší ochranou pracovních nebo školních dat jejich šifrování. Šifrování nesouvisí s PINem aplikace, ale jde o vlastní zásadu ochrany aplikace.

  3. **Jak Intune chrání PIN před útoky hrubou silou?** Jako součást zásady pro PIN aplikace může správce IT nastavit maximální počet pokusů, které uživatel má k ověření PINu před uzamčením aplikace. Po vyčerpání pokusů může sada Intune App SDK vymazat podniková data v aplikaci.

**A co šifrování?** Správci IT můžou nasadit zásadu ochrany aplikace, která vyžaduje šifrování dat aplikace. Jako součást této zásady může správce IT také určit, kdy se obsah bude šifrovat.

  1. **Jak Intune šifruje data?** Podrobné informace o nastavení zásady ochrany aplikace šifrováním najdete v tématech [Nastavení zásad ochrany aplikací pro Android](../deploy-use/android-mam-policy-settings.md) a [Nastavení zásad ochrany aplikací pro iOS](../deploy-use/ios-mam-policy-settings.md).

  2. **Co se šifruje?** Šifrují se jenom data označená jako podniková, a to podle zásady ochrany aplikace správce IT. Data se považují za podniková, když pocházejí z firemního umístění. U aplikací Office považuje Intune za firemní následující umístění: e-mail (Exchange) nebo cloudové úložiště (aplikace OneDrive s účtem OneDrive pro firmy). U obchodních aplikací kompatibilních s nástrojem Intune App Wrapping se za podniková považují všechna data aplikace.

**Jak může Intune vzdáleně smazat data?** Intune může data aplikace smazat třemi způsoby: úplným vymazáním zařízení, selektivním vymazáním pro MDM nebo selektivním vymazáním pro MAM. Další informace o vzdáleném vymazání pro MDM najdete v článku [Lepší ochrana dat s využitím plného nebo selektivního vymazání pomocí Microsoft Intune](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md). Další informace o selektivním vymazání pro MAM najdete v článku [Vymazání dat spravovaných aplikací společnosti s Microsoft Intune](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md)

  1. **Co je úplné vymazání?** [Úplné vymazání](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#full-wipe) odebere veškerá uživatelská data a nastavení ze **zařízení** pomocí obnovení výchozího továrního nastavení v zařízení. Zařízení se odebere ze služby Intune.
  >[!NOTE]
  > Úplného vymazání jde dosáhnout jenom na zařízeních zaregistrovaných ve správě mobilních zařízení (MDM) Intune.

  2. **Co je selektivní vymazání pro MDM?** O selektivním vymazání si můžete přečíst v článku [Lepší ochrana dat s využitím plného nebo selektivního vymazání pomocí Microsoft Intune](../deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune.md#selective-wipe).

  3. **Co je selektivní vymazání pro MAM?** Selektivní vymazání pro MAM jednoduše odebere data aplikace společnosti z aplikace. Žádost se inicializuje pomocí portálu Intune Azure Portal. Informace o tom, jak inicializovat žádost o vymazání, najdete v článku [Vymazání dat spravovaných aplikací společnosti s Microsoft Intune](../deploy-use/wipe-managed-company-app-data-with-microsoft-intune.md).

  4. **Jak rychle selektivní vymazání pro MAM proběhne?** Pokud uživatel používá aplikaci, když je zahájeno selektivní vymazání, sada Intune App SDK kontroluje každých 30 minut žádost o selektivní vymazání ze služby Intune MAM. Selektivní vymazání také kontroluje tehdy, když uživatel spustí aplikaci poprvé a přihlásí se pomocí pracovního nebo školního účtu.

**Proč místní služby nepracují s aplikacemi chráněnými službou Intune?** Ochrana aplikací Intune závisí na identitě uživatele, aby byla konzistentní mezi aplikací a sadou Intune App SDK. Jediná cesta, která to může zaručit, je moderní ověřování. Jsou situace, kdy aplikace můžou fungovat s místní konfigurací, ale nejsou konzistentní ani nic nezaručují.

**Existuje bezpečný způsob, jak otevírat webové odkazy ze spravovaných aplikací?** Ano. Správce IT může nasadit a nastavit zásadu ochrany aplikace pro [aplikaci Intune Managed Browser](../deploy-use/manage-internet-access-using-managed-browser-policies.md), což je webový prohlížeč vyvinutý týmem Microsoft Intune, který se dá snadno spravovat přes Intune. Správce IT může vyžadovat, aby se všechny webové odkazy v aplikacích podporujících Intune otvíraly v aplikaci Managed Browser.


## <a name="app-experience-on-android"></a>Prostředí aplikací na Androidu

**Proč je potřeba aplikace Portál společnosti, aby ochrana aplikací Intune fungovala na zařízeních s Androidem?** Většina funkcí ochrany aplikací je integrovaná do aplikace Portál společnosti. I když aplikace Portál společnosti se vždycky vyžaduje, registrace zařízení se _nevyžaduje_. U správy mobilních aplikací bez registrace (MAM-WE) je jenom nutné, aby měl koncový uživatel aplikaci Portál společnosti na zařízení nainstalovanou.

## <a name="app-experience-on-ios"></a>Prostředí aplikací v iOS

**Můžu pomocí rozšíření pro sdílení v iOS otevírat pracovní nebo školní data v nespravovaných aplikacích, i když je zásada přenosu dat nastavená na „jenom spravované aplikace“ nebo „žádné aplikace“. Nemůže při tom dojít k úniku dat?** Zásady ochrany aplikací pro Intune nemůžou ovládat rozšíření pro sdílení v iOS, když dané zařízení nespravují. Proto Intune _**podniková data před jejich sdílením mimo příslušnou aplikaci zašifruje**_. Můžete si to ověřit tak, že si zkusíte otevřít podnikový soubor mimo spravovanou aplikaci. Měl by být zašifrovaný a mimo spravovanou aplikaci by ho nemělo být možné otevřít.

### <a name="see-also"></a>Související témata
- [Nastavení zásad správy mobilních aplikací pro Android v Microsoft Intune](../deploy-use/android-mam-policy-settings.md)
- [Nastavení zásad správy mobilních aplikací pro iOS](../deploy-use/ios-mam-policy-settings.md)
- [Jak ověřit nastavení správy mobilních aplikací](../deploy-use/validate-mobile-application-management.md)
- [Příprava před konfigurací zásad správy mobilních aplikací pomocí Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Jak získat podporu pro Microsoft Intune](../troubleshoot/how-to-get-support-for-microsoft-intune.md)

