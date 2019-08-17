---
title: Nasazení aplikací pro Windows 10 pomocí Intune
titleSuffix: ''
description: Přečtěte si o scénářích nasazení aplikací pro Windows 10, které jsou dostupné v Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 07/29/2019
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
ms.openlocfilehash: c853608f46bb01263ddd08193f729cdfb018fed9
ms.sourcegitcommit: b78793ccbef2a644a759ca3110ea73e7ed6ceb8f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69550064"
---
# <a name="windows-10-app-deployment-using-microsoft-intune"></a>Nasazení aplikací pro Windows 10 pomocí Intune 

Microsoft Intune aktuálně na zařízeních s Windows 10 podporuje různé typy aplikací a scénářů nasazení. Po přidání aplikace do Intune ji můžete přiřadit uživatelům a zařízením. Následující informace poskytují další podrobnosti týkající se podporovaných scénářů pro Windows 10. Kromě toho také poskytují klíčové podrobnosti, které byste při nasazování aplikací do systému Windows neměli opomenout. 

Obchodní aplikace (LOB) a aplikace pro Microsoft Store pro firmy jsou na zařízeních s Windows 10 podporované. Mezi přípony souborů aplikací pro Windows patří **.msi**, **.appx** a **.appxbundle**.  

> [!Note]
> Minimálními potřebnými aktualizacemi Windows 10 pro nasazování moderních aplikací jsou tyto:
> - Pro Windows 10 1803: [KB4100403 z 23. května 2018 (číslo sestavení operačního systému 17134.81)](https://support.microsoft.com/help/4100403/windows-10-update-kb4100403)
> - Pro Windows 10 1709: [KB4284822 z 21. června 2018 (číslo sestavení operačního systému 16299.522)](https://support.microsoft.com/help/4284822)
>
> Pouze systémy Windows 10 1803 a novější podporují instalaci aplikací, pokud není k dispozici žádný primární uživatel.

## <a name="windows-10-line-of-business-apps"></a>Obchodní aplikace pro Windows 10

Obchodní aplikace pro Windows 10 jsou podepsané a nahrané v konzole správce Intune a mohou obsahovat jak moderní aplikace, jako jsou aplikace Univerzální platformy Windows (UWP) a balíčky aplikace systému Windows (AppX), tak i aplikace Win 32, jako jsou jednoduché soubory balíčku Microsoft Installer (MSI). Aktualizace obchodních aplikací se musí pokaždé ručně nahrát a nasadit správcem. Nasazené aktualizace se automaticky bez zásahu uživatele nainstalují na zařízení koncových uživatelů, kteří mají aplikaci nainstalovanou. Uživatel nemá nad aktualizacemi žádnou kontrolu. 

## <a name="microsoft-store-for-business-apps"></a>Aplikace pro Microsoft Store pro firmy

Microsoft Store pro obchodní aplikace jsou moderní aplikace zakoupené z portálu pro správu Microsoft Store pro firmy a pak se synchronizují s Microsoft Intune pro správu. Tyto aplikace mohou mít **online licenci** nebo **offline licenci**. Aktualizace Microsoft Store pro obchodní aplikace se spravují přímo pomocí Microsoft Store, a to bez další akce, kterou vám vyžaduje správce. Můžete taky zabránit aktualizacím konkrétních aplikací pomocí vlastního identifikátoru URI (Uniform Resource Identifier). Další informace najdete v tématu o [správě podnikových aplikací a zabránění jejich automatické aktualizace](https://docs.microsoft.com/windows/client-management/mdm/enterprise-app-management#prevent-app-from-automatic-updates). Koncový uživatel může na svém zařízení automatické aktualizace aplikací z Microsoft Storu pro firmy také zakázat. 

### <a name="categorize-microsoft-store-for-business-apps"></a>Kategorizace Microsoft Store pro obchodní aplikace 
K kategorizaci Microsoft Store pro obchodní aplikace použijte následující postup: 

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte**aplikace** **klienta** > aplikace > vyberte**kategorii**aplikace Microsoft Store pro firmy > **informace** > . 
3. V rozevírací nabídce vyberte kategorii.

## <a name="installing-apps-on-windows-10-devices"></a>Instalace aplikací na zařízeních s Windows 10
V závislosti na typu aplikace můžete aplikace na zařízení s Windows 10 instalovat jedním ze dvou způsobů:

- **Kontext uživatele**: Když se aplikace nasadí v uživatelském kontextu, nainstaluje se tato spravovaná aplikace pro daného uživatele na zařízení, když se uživatel přihlásí k zařízení. Instalace aplikace úspěšné neproběhne, dokud se uživatel k zařízení nepřihlásí. 
  - V kontextu uživatele je možné nasadit moderní obchodní aplikace a aplikace pro Microsoft Store pro firmy (online i offline) s podporou záměru Povinné i K dispozici.
  - V kontextu uživatele je možné nasadit aplikace Win32 vytvořené v **uživatelském režimu** nebo v **duálním režimu** s podporou záměru **Povinné** i **K dispozici**. 
- **Kontext zařízení**: Když se aplikace nasadí v kontextu zařízení, spravovaná aplikace se nainstaluje přímo do zařízení přes Intune.
  - Pouze moderní obchodní aplikace a offline licencované Microsoft Store pro podnikové aplikace lze nasadit v kontextu zařízení a budou podporovat pouze požadovaný záměr.
  - V kontextu uživatele je možné nasadit aplikace Win32 vytvořené v **režimu počítače** nebo v **duálním režimu** jenom s podporou záměru **Povinné**.

> [!NOTE]
> U aplikací Win32 vytvořených jako aplikace **duálního režimu** budete muset vy (správce) vybrat, jestli bude příslušná aplikace pro všechna přiřazení spojená s danou instancí fungovat jako aplikace **uživatelského režimu** nebo **režimu počítače**. Kontext nasazení nelze změnit pro jednotlivé přiřazení.  

Když se aplikace nasadí v kontextu zařízení, instalace proběhne úspěšně pouze v případě, že zařízení kontext zařízení podporuje. Kromě toho nasazení v kontextu zařízení obsahuje následující podmínky:
- Pokud se aplikace nasadí v kontextu zařízení a cílí na uživatele, instalace se nezdaří a v konzole pro správu se zobrazí následující stav a chyba:
  - Stav: Nepovedlo se.
  - Chyba: Uživatel se nemůže zaměřit na instalaci kontextu zařízení.
- Pokud se aplikace nasadí v kontextu zařízení a cílí na zařízení, které kontext zařízení nepodporuje, instalace se nezdaří a v konzole pro správu se zobrazí následující stav a chyba:
  - Stav: Nepovedlo se.
  - Chyba: Tato platforma nepodporuje instalaci kontextu zařízení. 

> [!Note]
> Jakmile se přiřazení aplikace uloží pod konkrétním nasazením, není možné u daného přiřazení kontext změnit (s výjimkou moderních aplikací). V případě moderních aplikací můžete kontext změnit z kontextu uživatele na kontext zařízení. 

V případě, že u jednoho uživatele nebo zařízení dojde ke konfliktu mezi zásadami, určí se konečná zásada podle následujících priorit:
- Zásady kontextu zařízení mají vyšší prioritu než zásady kontextu uživatele. 
- Zásady instalace mají vyšší prioritu než zásady odinstalace.

Další informace o přiřazování aplikací pomocí Microsoft Intune najdete v tématech [Přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md) a [Zahrnutí a vyloučení přiřazení aplikací v Microsoft Intune](apps-inc-exl-assignments.md). Další informace o typech aplikací v Intune najdete v tématu [Přidání aplikací do Microsoft Intune](apps-add.md).

## <a name="next-steps"></a>Další postup

- Další informace o přiřazení aplikací ke skupinám najdete v článku [Přiřazení aplikací do skupin pomocí Microsoft Intune](apps-deploy.md).
- Další informace o sledování přiřazení aplikací najdete v článku o [monitorování aplikací](apps-monitor.md).
