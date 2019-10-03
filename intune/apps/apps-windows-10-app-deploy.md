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
ms.localizationpriority: high
ms.technology: ''
ms.assetid: abebfb5e-054b-435a-903d-d1c31767bcf2
ms.reviewer: priyar
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 04e943f573fb2485a2ef7f1e3245f08d4222d142
ms.sourcegitcommit: fc356fd69beaeb3d69982b47e2bdffb6f7127f8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/03/2019
ms.locfileid: "71830560"
---
# <a name="windows-10-app-deployment-using-microsoft-intune"></a>Nasazení aplikací pro Windows 10 pomocí Microsoft Intune 

Microsoft Intune aktuálně podporuje různé typy aplikací a scénáře nasazení na zařízeních s Windows 10. Po přidání aplikace do Intune můžete aplikaci přiřadit uživatelům a zařízením. Následující informace obsahují další podrobnosti týkající se podporovaných scénářů Windows 10. Kromě toho následující informace obsahují klíčové informace, které je třeba poznamenat při nasazování aplikací do systému Windows. 

Obchodní aplikace (LOB) a Microsoft Store pro firmy jsou typy aplikací podporované na zařízeních s Windows 10. Mezi přípony souborů pro aplikace pro Windows patří soubory **. msi**, **. appx**a **. appxbundle**.  

> [!Note]
> Minimální potřebné aktualizace Windows 10 pro nasazení moderních aplikací jsou následující:
> - Pro Windows 10 1803, [Květen 23, 2018 – KB4100403 (sestavení operačního systému 17134,81)](https://support.microsoft.com/help/4100403/windows-10-update-kb4100403).
> - Pro Windows 10 1709, [21. června 2018 – KB4284822 (Build OS 16299,522)](https://support.microsoft.com/help/4284822).
>
> Pouze systémy Windows 10 1803 a novější podporují instalaci aplikací, pokud není k dispozici žádný primární uživatel.
>
> U zařízení s Windows 10 Home Edition se nasazení aplikace LOB nepodporuje.

## <a name="windows-10-line-of-business-apps"></a>Obchodní aplikace pro Windows 10

Obchodní aplikace pro Windows 10 jsou podepsané a nahrané do konzoly pro správu Intune a můžou zahrnovat moderní aplikace, jako jsou aplikace Univerzální platforma Windows (UWP) a balíčky aplikací pro Windows (AppX), a taky aplikace pro Win 32, jako jsou například jednoduché soubory balíčku Instalační služby systému Microsoft (MSI). Aktualizace obchodních aplikací se musí ručně nahrát a nasadit správcem. Nasazené aktualizace se automaticky nainstalují na zařízení koncových uživatelů, ve kterých je nainstalovaná aplikace bez zásahu uživatele. Uživatel nemá žádnou kontrolu nad aktualizacemi. 

## <a name="microsoft-store-for-business-apps"></a>Microsoft Store pro obchodní aplikace

Microsoft Store pro obchodní aplikace jsou moderní aplikace zakoupené z portálu pro správu Microsoft Store pro firmy a pak se synchronizují s Microsoft Intune pro správu. Aplikace můžou být buď **online licencované** , nebo **offline**. Aktualizace Microsoft Store pro obchodní aplikace se spravují přímo pomocí Microsoft Store, a to bez další akce, kterou vám vyžaduje správce. Můžete taky zabránit aktualizacím konkrétních aplikací pomocí vlastního identifikátoru URI (Uniform Resource Identifier). Další informace najdete v tématu [Správa podnikových aplikací – zabránění aplikacím v automatických aktualizacích](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). Na zařízení může koncový uživatel také zakázat aktualizace pro všechny Microsoft Store pro obchodní aplikace na zařízení. 

### <a name="categorize-microsoft-store-for-business-apps"></a>Kategorizace Microsoft Store pro obchodní aplikace 
K kategorizaci Microsoft Store pro obchodní aplikace použijte následující postup: 

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte aplikace **klienta**@no__t **-1 >** vyberte**kategorii**Microsoft Store pro firmy > **informace o aplikaci** > . 
3. V rozevírací nabídce vyberte kategorii.

## <a name="installing-apps-on-windows-10-devices"></a>Instalace aplikací na zařízení s Windows 10
V závislosti na typu aplikace je možné aplikaci nainstalovat na zařízení s Windows 10 jedním ze dvou způsobů:

- **Kontext uživatele**: když se aplikace nasadí v uživatelském kontextu, nainstaluje se tato spravovaná aplikace pro daného uživatele na zařízení, když se uživatel přihlásí k zařízení. Všimněte si, že instalace aplikace nebude úspěšná, až se uživatel přihlásí k zařízení. 
  - Moderní obchodní aplikace a aplikace pro Microsoft Store pro firmy (online i offline) se dají nasadit v kontextu uživatele a budou podporovat jak požadovaný, tak i dostupný záměr.
  - Aplikace Win32 sestavené jako **uživatelský režim** nebo **duální režim** lze nasadit v kontextu uživatele a budou podporovat **požadovaný** a **dostupný** záměr. 
- **Kontext zařízení**: při nasazení aplikace v kontextu zařízení se spravovaná aplikace nainstaluje do zařízení přímo přes Intune.
  - Pouze moderní obchodní aplikace a offline licencované Microsoft Store pro podnikové aplikace lze nasadit v kontextu zařízení a budou podporovat pouze požadovaný záměr.
  - Aplikace Win32 sestavené jako **režim počítače** nebo **duální režim** lze nasadit v kontextu uživatele a budou podporovat pouze **požadovaný** záměr.

> [!NOTE]
> Pro aplikace Win32 sestavené jako aplikace s **duálním režimem** bude nutné (správce) vybrat, jestli bude aplikace fungovat jako **uživatelský režim** nebo aplikace v **režimu počítače** pro všechna přiřazení přidružená k této instanci. Kontext nasazení nelze změnit na jedno přiřazení.  

Když se aplikace nasadí v kontextu zařízení, instalace bude úspěšná jenom v případě, že se zaměří na zařízení, které podporuje kontext zařízení. Kromě toho nasazení v kontextu zařízení podporuje následující podmínky:
- Pokud je aplikace nasazená v kontextu zařízení a zacílená na uživatele, instalace se nezdaří a v konzole pro správu se zobrazí chyba s následujícím stavem a chybou:
  - Stav: neúspěšné.
  - Chyba: uživatel se nemůže zaměřit na instalaci kontextu zařízení.
- Pokud je aplikace nasazená v kontextu zařízení, ale je zaměřená na zařízení, které nepodporuje kontext zařízení, instalace selže a v konzole pro správu se zobrazí následující stav a chyba:
  - Stav: neúspěšné.
  - Chyba: Tato platforma nepodporuje instalaci kontextu zařízení. 

> [!Note]
> Po uložení přiřazení aplikace s určitým nasazením nejde kontext pro toto přiřazení změnit, s výjimkou moderních aplikací. V případě moderní aplikace je možné kontext změnit z kontextu uživatele na kontext zařízení. 

V případě konfliktu zásad na jednom uživateli nebo zařízení jsou k dispozici priority zásad, které se použijí k určení konečných zásad:
- Zásada kontextu zařízení je vyšší Priorita než zásada kontextu uživatele. 
- Zásada instalace má vyšší prioritu než zásada odinstalace.

Další informace o přiřazování aplikací pomocí Microsoft Intune najdete v článku [přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md) a [zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](apps-inc-exl-assignments.md). Další informace o typech aplikací v Intune najdete v tématu [Přidání aplikací do Microsoft Intune](apps-add.md).

## <a name="next-steps"></a>Další kroky

- Další informace o přiřazování aplikací do skupin najdete v článku [přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md).
- Další informace o monitorování přiřazení aplikací najdete v tématu monitorování [aplikací](apps-monitor.md).
