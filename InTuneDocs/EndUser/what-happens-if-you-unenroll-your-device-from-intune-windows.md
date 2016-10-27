---
title: "Co se stane, když zrušíte registraci zařízení s Windows v Intune? | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 08/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 08f31db90f324ef5f93076c4e13bfa5328a15adc
ms.openlocfilehash: ebd1300c490f3d69110a5f1920fd25d1dc5cb850


---


# Co se stane, když zrušíte registraci zařízení s Windows v Intune?

Pomocí odkazů na pravé straně této stránky v části „V tomto článku“ najdete informace o typu zařízení, které používáte.


## Windows 10, Windows 8.1, Windows 8, Windows 7, Vista

-   Vaše zařízení se už nebude zobrazovat na Portálu společnosti a z tohoto portálu už nebudete moct instalovat aplikace.

-   Pokud jste nainstalovali klientský software Intune, bude z počítače odebrán.

-   Z počítače se odebere software Intune Endpoint Protection. Pokud je v počítači nainstalovaný jiný software antivirové ochrany a je zakázaný, může být po odebrání softwaru Intune Endpoint Protection znovu povolený. Po odebrání počítače z portálu společnosti byste měli počítač zkontrolovat.

    > [!IMPORTANT]
    > Pokud tento jiný software antivirové ochrany nebude znovu povolen a nebude nainstalován žádný jiný software antivirové ochrany, může být počítač od daného okamžiku ohrožen a zvýší se tím riziko napadení viry a malwarem.

-   Už nebudou platit nastavení, která se v zařízení změnila od jeho přidání (třeba zakázání fotoaparátu/kamery).

-   Počítač se už nebude automaticky aktualizovat prostřednictvím aktualizací softwaru nebo antivirového programu ze služby Intune. V závislosti na tom, jak je počítač nakonfigurován, však může počítač nadále získávat aktualizace prostřednictvím služeb Windows Server Update Services, Windows Update či Microsoft Update.

Kromě toho pro Windows 8.1 platí:

-   Nebudete již moci v zařízení používat aplikace a data společnosti.

-   Některé e-mailové aplikace, například Windows Pošta, nebudou mít přístup k e-mailům společnosti, které jsou uloženy v zařízení.

-   Je možné, že se nebudete schopni připojit k podnikové síti pomocí sítě Wi-Fi nebo virtuální privátní sítě (VPN).

-   Je možné, že již v zařízení nebudete mít přístup k některým prostředkům společnosti, jako jsou sdílené složky nebo interní weby.

## Windows 10 Mobile a Windows Phone 8.1

-   Ze zařízení se odinstaluje aplikace Portál společnosti. To znamená, že už se vaše zařízení nebude zobrazovat na Portálu společnosti a nebudete moct instalovat aplikace z aplikace nebo webu Portál společnosti.

-   Nebudete již moci v zařízení používat aplikace a data společnosti.

-   Nastavení, která byla v zařízení změněna od jeho přidání, například zakázání fotoaparátu/kamery nebo vyžadování určité délky hesla, již nebudou platit.

    > [!IMPORTANT]
    > Jedinou výjimkou jsou zde zásady šifrování, které budou platit stále. Pokud zásady vaší společnosti vyžadovaly, aby byl váš Windows Phone zašifrovaný, jde v telefonu šifrování zrušit jedině obnovením telefonu do výchozího továrního nastavení pomocí nabídky **Nastavení** ve Windows Phonu.

## Windows RT s Windows 8.1

-   Ze zařízení se odinstaluje aplikace Portál společnosti. To znamená, že už se vaše zařízení nebude zobrazovat na Portálu společnosti a nebudete z něj moct instalovat aplikace.

-   Nebudete již moci v zařízení používat aplikace a data společnosti.

-   Nastavení, která byla v zařízení změněna od jeho přidání, například zakázání fotoaparátu/kamery nebo vyžadování určité délky hesla, již nebudou platit.

-   Je možné, že se již nebudete schopni připojit k podnikové síti pomocí sítě Wi-Fi nebo virtuální privátní sítě (VPN).

-   Je možné, že již v zařízení nebudete mít přístup k některým prostředkům společnosti, jako jsou sdílené složky nebo interní weby.

-   Některé e-mailové aplikace, například Windows Pošta, nebudou mít přístup k e-mailům společnosti, které jsou uloženy v zařízení.

Při odebrání zařízení se systémem Windows RT dojde k následujícímu:

-   Ze zařízení se odinstaluje aplikace Portál společnosti. To znamená, že už se vaše zařízení nebude zobrazovat na Portálu společnosti a nebudete z něj moct instalovat aplikace.

-   Nebudete již moci v zařízení používat aplikace a data společnosti.

-   Nastavení, která byla v zařízení změněna od jeho přidání, například zakázání fotoaparátu/kamery nebo vyžadování určité délky hesla, již nebudou platit.

Pokud máte otázky, na které byste potřebovali odpověď, obraťte se na správce IT. Jeho kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).




<!--HONumber=Oct16_HO2-->


