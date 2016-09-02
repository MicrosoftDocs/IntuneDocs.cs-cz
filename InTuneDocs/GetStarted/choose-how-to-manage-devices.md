---
title: "Volba způsobu správy zařízení | Microsoft Intune"
description: "Přečtěte si o různých způsobech, jakými můžete registrovat a spravovat zařízení."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 07/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: angrobe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: c329bd08aaf72ae2acaa03dcb12c911d84b46b4e
ms.openlocfilehash: cfd9df3814d0d306a254a5566155a91ce5d0ca16


---

# Volba způsobu správy zařízení
Intune umožňuje spravovat řadu zařízení tím, že je *zaregistruje*. Uživatelé pak můžou použít *portál společnosti* k provedení řady operací, jako je třeba registrace zařízení, procházení a instalace aplikací, zajištění kompatibility zařízení se zásadami společnosti a kontaktování podpory IT.

## Způsoby správy mobilních zařízení
Intune může spravovat tyto platformy zařízení:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

> [!NOTE]
> Pokud jste dřív registrovali zařízení, která používají starší verzi systému iOS, než je uvedená podporovaná verze, zůstanou tato zařízení zaregistrovaná. V dokumentaci ověřte, že funkce podporuje danou verzi iOS.

Intune může spravovat zařízení uživatelů (často se používá označení „Přineste si vlastní zařízení“, BYOD – Bring Your Own Device). Umožňuje také spravovat zařízení v majetku společnosti, včetně situací, kdy dá společnost uživatelům seznam zařízení, ze kterého mohou vybírat (CYOD – Choose Your Own Device).

### Registrace zařízení do správy
Mobilní zařízení s operačními systémy včetně systému iOS, Android a Windows Phone musíte vždycky registrovat. Způsob registrace zařízení závisí na potřebách vaší organizace:

|Typ registrace|Uživatelé s vlastním zařízením|Uživatelé s firemním zařízením|Sdílené zařízení s účtem správce|Sdílené zařízení bez účtu správce|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Popis**|Osobní zařízení zaregistrované pomocí Microsoft Intune|Zařízení jediného uživatele vlastněné společností|Zařízení vlastněné společností, sdílené mnoha uživateli a spravované účtem správce|Zařízení bez uživatele vlastněné společností a používané mnoha uživateli|
|**Uživatel zařízení**|Vlastník|Přiřazený uživatel|Žádný účet specifický pro uživatele|Bez konkrétního uživatele|
|**Kdo se registruje**|Vlastník|Správce|Správce zařízení|Kdokoliv|
|**Kdo ruší registraci**|Vlastník nebo správce|Platforma |Správce nebo uživatel|Správce nebo uživatel|
|**Kdo může resetovat**|Vlastník nebo správce|Správce|Správce|Správce|

Další informace najdete v článku [Volba způsobu registrace mobilních zařízení](/intune/get-started/choose-how-to-enroll-devices1).

> [!NOTE]
> Úplný seznam možností, které vám registrace zařízení dává, najdete v tématu [Možnosti správy mobilních zařízení](mobile-device-management-capabilities-in-microsoft-intune.md).

## Způsob správy počítačů s Windows
Intune může spravovat počítače se systémem Windows Vista a novějšími systémy Windows pomocí počítačového klienta Intune. U počítačů s Windows si můžete zvolit, jestli je zaregistrujete nebo jestli nainstalujete počítačový klientský software Intune, který nabízí několik možností, které při registraci zařízení nejsou k dispozici. Ve většině scénářů si svoje zařízení s Windows zaregistrujete ve službě Microsoft Intune, která poskytuje větší sadu funkcí než počítačový klient.

Použití počítačového klienta Intune zvažte, pokud chcete:

- Použít libovolnou z funkcí podporovaných počítačovým klientem Microsoft Intune ke správě svých počítačů s Windows.
- Spravovat počítač s Windows, ve kterém běží operační systém, pro který není registrace podporovaná.

> [!NOTE]
> Úplný seznam funkcí, které vám instalace počítačového klienta Intune do počítače s Windows dává, najdete v tématu [Možnosti správy počítačů s Windows](windows-pc-management-capabilities-in-microsoft-intune.md).

## Správa Exchange ActiveSync
Ke správě zařízení můžete taky využít Exchange ActiveSync. Vyžaduje to instalaci konektoru On-Premises Connector nebo použití integrovaného konektoru Service to Service Connector pro připojení k Exchange Serveru.

Další informace o požadavcích na hardware a software pro instalaci softwaru On-Premises Connector najdete v tématu [Požadavky na konektor On-Premises Connector](/intune/deploy-use/intune-on-premises-exchange-connector#requirements-for-the-on-premises-connector).

Další informace o použití softwaru On-Premises Connector nebo Service to Service Connector se serverem Exchange najdete v tématu [Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).



## Další kroky
Nyní jste se seznámili s některými možnostmi, které můžete použít při registraci zařízení v [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Potom budete muset [zaregistrovat svá zařízení](/intune/deploy-use/enroll-devices-in-microsoft-intune). Po dokončení registrace zařízení můžete využít výhod všech funkcí, o kterých jste se v tomto tématu dočetli. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->



<!--HONumber=Aug16_HO3-->


