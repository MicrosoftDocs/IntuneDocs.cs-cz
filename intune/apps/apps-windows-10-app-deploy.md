---
title: Nasazení aplikací pro Windows 10 pomocí Microsoft Intune
titleSuffix: ''
description: Přečtěte si o scénářích nasazení aplikací pro Windows 10, které jsou dostupné v Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c8ce24081eae1808d3db0c5078026b306fd209d5
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72507250"
---
# <a name="windows-10-app-deployment-by-using-microsoft-intune"></a>Nasazení aplikací pro Windows 10 pomocí Microsoft Intune 

Microsoft Intune podporuje různé typy aplikací a scénáře nasazení na zařízeních s Windows 10. Po přidání aplikace do Intune ji můžete přiřadit uživatelům a zařízením. Tento článek obsahuje další informace o podporovaných scénářích Windows 10 a také obsahuje důležité informace, které je třeba poznamenat při nasazování aplikací do systému Windows. 

Obchodní aplikace (LOB) a aplikace pro Microsoft Store pro firmy jsou na zařízeních s Windows 10 podporované. Mezi přípony souborů pro aplikace pro Windows patří soubory. msi,. appx a. appxbundle.  

> [!Note]
> K nasazení moderních aplikací potřebujete aspoň tyto:
> - Pro Windows 10 1803: [KB4100403 z 23. května 2018 (číslo sestavení operačního systému 17134.81)](https://support.microsoft.com/help/4100403/windows-10-update-kb4100403)
> - Pro Windows 10 1709: [KB4284822 z 21. června 2018 (číslo sestavení operačního systému 16299.522)](https://support.microsoft.com/help/4284822)
>
> Jenom Windows 10 1803 a novější podporují instalaci aplikací, když není přidružený žádný primární uživatel.
>
> Nasazení aplikace LOB se nepodporuje na zařízeních s Windows 10 Home Edition.

## <a name="windows-10-lob-apps"></a>Obchodní aplikace pro Windows 10

Do konzoly pro správu Intune můžete podepisovat a nahrávat obchodní aplikace pro Windows 10. Ty můžou zahrnovat moderní aplikace, jako jsou aplikace Univerzální platforma Windows (UWP) a balíčky aplikací pro Windows (AppX), a také aplikace pro Win 32, jako jsou například jednoduché soubory balíčku Instalační služby společnosti Microsoft (MSI). Správce musí ručně nahrávat a nasazovat aktualizace obchodních aplikací. Tyto aktualizace se automaticky nainstalují na uživatelská zařízení, ve kterých je nainstalovaná aplikace. Není vyžadován žádný zásah uživatele a uživatel nemá žádnou kontrolu nad aktualizacemi. 

## <a name="microsoft-store-for-business-apps"></a>Aplikace pro Microsoft Store pro firmy

Microsoft Store pro obchodní aplikace jsou moderní aplikace zakoupené na portálu pro správu Microsoft Store pro firmy. Pak se synchronizují s Microsoft Intune pro správu. Aplikace můžou být buď online licencované, nebo offline. Microsoft Store přímo spravuje aktualizace bez dalších akcí, které správce vyžaduje. Aktualizace konkrétních aplikací můžete také zabránit pomocí vlastního identifikátoru URI (Uniform Resource Identifier). Další informace najdete v tématu o [správě podnikových aplikací a zabránění jejich automatické aktualizace](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). Uživatel může také zakázat aktualizace pro všechny Microsoft Store pro obchodní aplikace na zařízení. 

### <a name="categorize-microsoft-store-for-business-apps"></a>Kategorizace Microsoft Store pro obchodní aplikace 
Kategorizace Microsoft Store pro obchodní aplikace: 

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **klientské aplikace** > **aplikace**. Vyberte Microsoft Store pro obchodní aplikaci. Pak vyberte **informace o aplikaci** > **kategorie**. 
3. Vyberte kategorii.

## <a name="install-apps-on-windows-10-devices"></a>Instalace aplikací na zařízení s Windows 10
V závislosti na typu aplikace můžete aplikaci nainstalovat na zařízení s Windows 10 jedním ze dvou způsobů:

- **Kontext uživatele**: když se aplikace nasadí v uživatelském kontextu, nainstaluje se tato spravovaná aplikace pro daného uživatele na zařízení, když se uživatel přihlásí k zařízení. Všimněte si, že instalace aplikace neproběhne úspěšně, dokud se uživatel přihlásí k zařízení. 
  - Moderní obchodní aplikace a Microsoft Store pro obchodní aplikace (online i offline) se dají nasadit v kontextu uživatele. Aplikace podporují požadovaný i dostupný záměr.
  - Aplikace Win32 sestavené jako uživatelský režim nebo duální režim lze nasadit v kontextu uživatele a podporují jak požadované, tak i dostupné záměry. 
- **Kontext zařízení**: při nasazení aplikace v kontextu zařízení se spravovaná aplikace nainstalují přímo do zařízení pomocí Intune.
  - V kontextu zařízení je možné nasadit jenom moderní obchodní aplikace a offline licencované Microsoft Store pro obchodní aplikace. Tyto aplikace podporují jenom požadovaný záměr.
  - Aplikace Win32 sestavené jako režim počítače nebo duální režim mohou být nasazeny v kontextu zařízení a podporují pouze požadovaný záměr.

> [!NOTE]
> Pro aplikace Win32 sestavené jako aplikace v duálním režimu musí správce zvolit, jestli bude aplikace fungovat jako uživatelský režim nebo aplikace v režimu počítače pro všechna přiřazení přidružená k této instanci. Kontext nasazení nejde změnit na přiřazení.  

Když se aplikace nasadí v kontextu zařízení, instalace bude úspěšná jenom při cílení na zařízení, které podporuje kontext zařízení. Kromě toho nasazení v kontextu zařízení obsahuje následující podmínky:
- Pokud je aplikace nasazená v kontextu zařízení a cílí na uživatele, instalace se nepovede. V konzole pro správu se zobrazí následující stav a chyba:
  - Stav: Neúspěšné.
  - Chyba: uživatel se nemůže zaměřit na instalaci kontextu zařízení.
- Pokud je aplikace nasazená v kontextu zařízení, ale je zaměřená na zařízení, které nepodporuje kontext zařízení, instalace se nezdařila. V konzole pro správu se zobrazí následující stav a chyba:
  - Stav: Neúspěšné.
  - Chyba: Tato platforma nepodporuje instalaci v kontextu zařízení. 

> [!Note]
> Po uložení přiřazení aplikace pomocí konkrétního nasazení nemůžete změnit kontext tohoto přiřazení, s výjimkou moderních aplikací. Pro moderní aplikace můžete změnit kontext z kontextu uživatele na kontext zařízení. 

Pokud dojde ke konfliktu v zásadách pro jednoho uživatele nebo zařízení, platí následující priority:
- Zásady kontextu zařízení mají vyšší prioritu než zásady kontextu uživatele. 
- Zásady instalace mají vyšší prioritu než zásady odinstalace.

Podrobnosti najdete v tématu [Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](apps-inc-exl-assignments.md). Další informace o typech aplikací v Intune najdete v tématu [Přidání aplikací do Microsoft Intune](apps-add.md).

## <a name="next-steps"></a>Další kroky

- [Přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md)
- [Jak monitorovat aplikace](apps-monitor.md)
