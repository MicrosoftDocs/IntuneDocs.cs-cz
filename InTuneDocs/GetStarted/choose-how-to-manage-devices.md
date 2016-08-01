---
title: "Volba způsobu správy zařízení | Microsoft Intune"
description: 
keywords: 
author: jeffgilb
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 770aad50-fd7a-4cf1-a793-f95fe47fc3f8
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4a7c6d8f4e47f050888e9fcf5edfa586c4a24065
ms.openlocfilehash: 502a08c1bf49057220917d929a8ffe0b98d3de2a


---

# Volba způsobu správy zařízení
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] umožňuje spravovat řadu zařízení tím, že je *zaregistruje*. Uživatelé pak můžou použít *portál společnosti* k provedení řady operací, jako je třeba registrace zařízení, procházení a instalace aplikací, zajištění kompatibility zařízení se zásadami společnosti a kontaktování podpory IT.

## Způsoby správy mobilních zařízení
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] může spravovat tyto platformy zařízení:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tip</h5>
  <p>Pokud jste dřív registrovali zařízení, která používají starší verzi systému iOS, než je uvedená podporovaná verze, zůstanou tato zařízení zaregistrovaná. V dokumentaci pro službu [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] ale zkontrolujte, že tato verze iOS se pro příslušnou funkci podporuje.</p>
</div>

[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] umožňuje spravovat zařízení uživatelů (často se používá označení „Přineste si vlastní zařízení“ (BYOD – Bring Your Own Device). Umožňuje také spravovat zařízení v majetku společnosti, včetně situací, kdy dá společnost uživatelům seznam zařízení, ze kterého mohou vybírat (CYOD – Choose Your Own Device).

### Registrace zařízení do správy
Mobilní zařízení s operačními systémy včetně systému iOS, Android a Windows Phone musíte vždycky registrovat. Způsob registrace zařízení ale závisí na potřebách vaší organizace:

|Typ registrace|Uživatelé s vlastním zařízením|Uživatelé s firemním zařízením|Sdílené zařízení s účtem správce|Sdílené zařízení bez účtu správce|
|-------------------|--------|--------|--------------------------------------|----------------------------------------|
|**Popis**|Osobní zařízení zaregistrované pomocí Microsoft Intune|Zařízení jediného uživatele vlastněné společností|Zařízení vlastněné společností, sdílené mnoha uživateli a spravované účtem správce|Zařízení bez uživatele vlastněné společností a používané mnoha uživateli|
|**Uživatel zařízení**|Vlastník|Přiřazený uživatel|Žádný účet specifický pro uživatele|Bez konkrétního uživatele|
|**Kdo se registruje**|Vlastník|Správce|Správce zařízení|Kdokoliv|
|**Kdo ruší registraci**|Vlastník nebo správce|Správce|Správce|Správce|
|**Kdo může resetovat**|Vlastník nebo správce|Správce|Správce|Správce|

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tip</h5>
  <p>Úplný seznam možností, které vám registrace zařízení dává, najdete v tématu [Možnosti správy mobilních zařízení](mobile-device-management-capabilities-in-microsoft-intune.md).</p>
</div>



## Způsob správy počítačů s Windows
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] může spravovat počítače se systémem Windows Vista a novějšími systémy Windows pomocí počítačového klienta Intune. U počítačů s Windows si můžete zvolit, jestli je zaregistrujete nebo jestli nainstalujete počítačový klientský software [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], který nabízí několik možností, které při registraci zařízení nejsou k dispozici. Ve většině scénářů si svoje zařízení s Windows zaregistrujete ve službě Microsoft Intune, která poskytuje větší sadu funkcí než počítačový klient.

Použití počítačového klienta Intune zvažte, pokud chcete:
<ul>
<li>Použít libovolnou z funkcí podporovaných počítačovým klientem Microsoft Intune ke správě svých počítačů s Windows.</li>
<li>Spravovat počítač s Windows, ve kterém běží operační systém, pro který není podporovaná registrace.</li>
</ul>

<div class="alert alert-tip">
  <h5><span class="icon-tip"></span> Tip</h5>
  <p>Úplný seznam funkcí, které vám instalace počítačového klienta Intune do počítače s Windows dává, najdete v tématu [Možnosti správy počítačů s Windows](windows-pc-management-capabilities-in-microsoft-intune.md).</p>
</div>

## Správa Exchange ActiveSync
Ke správě zařízení můžete taky využít Exchange ActiveSync. Vyžaduje to instalaci konektoru On-Premises Connector nebo použití integrovaného konektoru Service to Service Connector pro připojení k Exchange Serveru.

Další informace o požadavcích na hardware a software pro instalaci softwaru On-Premises Connector najdete v tématu [Požadavky na konektor On-Premises Connector](/intune/deploy-use/intune-on-premises-exchange-connector#requirements-for-the-on-premises-connector).

Další informace o použití softwaru On-Premises Connector nebo Service to Service Connector se serverem Exchange najdete v tématu [Správa mobilních zařízení pomocí protokolu Exchange ActiveSync a služby Microsoft Intune](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune).



## Další kroky
Nyní jste se seznámili s některými možnostmi, které můžete použít při registraci zařízení v [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Potom budete muset [zaregistrovat svá zařízení](/intune/deploy-use/enroll-devices-in-microsoft-intune). Po dokončení registrace zařízení můžete využít výhod všech funkcí, o kterých jste se v tomto tématu dočetli. <!--lindavr: There's a logical flaw in our "get to know/get started" content. You can take the path in this topic or you can take the path in the What to know before your get started topic. And they don't cover the same ground. -->



<!--HONumber=Jul16_HO3-->


