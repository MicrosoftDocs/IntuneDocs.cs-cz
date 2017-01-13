---
title: "Zařízení nemá požadovaný certifikát | Dokumentace Microsoftu"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: d6fcfac7c8bd469f5163ec9b4017ae8c3d486428
ms.openlocfilehash: 92f698cb0616838b4dac5b1a889ad4569d94b956

---


# <a name="your-device-is-missing-a-required-certificate"></a>Zařízení nemá požadovaný certifikát

## <a name="whats-a-certificate"></a>Co je certifikát?

[Kryptografie](https://technet.microsoft.com/en-us/library/cc962030.aspx) je věda, jak poskytovat zabezpečení informacím. V tradičním pojetí kryptografie sloužila k předávání zakódovaných zpráv, což mělo [zajistit utajení komunikace](https://technet.microsoft.com/en-us/library/cc962019.aspx). Ve zjednodušené podobě kryptografie nahrazuje neboli transponuje písmena a tím vytvoří zakódovanou zprávu, která je nečitelná, utajená nebo skrytá. Jenom člověk s dekódovacím klíčem, neboli _certifikátem_, může zakódovanou zprávu převést zpět do její původní čitelné formy. Vaše zařízení s Androidem používá certifikáty s Intune, aby se zajistilo, že komunikace mezi zařízením a prostředky organizace, jako je e-mail a dokumenty, byla zabezpečená na jednom konci, po dobu přenosu i na druhém konci.

Pokud zařízení s Androidem nemáte zaregistrované v Intune a chybí mu konkrétní certifikát, který vyžaduje správce IT, nebudete se k aplikaci Portál společnosti moct přihlásit. Při pokusu o přihlášení se zobrazí tato zpráva:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

První možnost, kterou byste měli zkusit, je zjistit, jestli v zařízení [nechybí certifikát, který je na něm obvykle předinstalovaný](your-device-is-missing-a-preinstalled-certificate-android.md). Pokud to nepomůže, váš správce IT by vás mohl [požádat, abyste si nainstalovali druhý certifikát ke zvýšení zabezpečení](your-device-is-missing-an-IT-required-certificate-android.md).

Potřebujete ještě další pomoc? Obraťte se na správce IT. Kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).



<!--HONumber=Jan17_HO1-->


