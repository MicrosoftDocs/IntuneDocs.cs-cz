---
title: Zařízení nemá požadovaný certifikát | Dokumentace Microsoftu
description: ''
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 03/16/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
searchScope:
- User help
ROBOTS: ''
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: c61a4807e55c3af5038c67c05157b9ad14002347
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="your-device-is-missing-a-required-certificate"></a>Zařízení nemá požadovaný certifikát

## <a name="whats-a-certificate"></a>Co je certifikát?

[Kryptografie](https://technet.microsoft.com/library/cc962030.aspx) je věda, jak poskytovat zabezpečení informacím. V tradičním pojetí kryptografie sloužila k předávání zakódovaných zpráv, což mělo [zajistit utajení komunikace](https://technet.microsoft.com/library/cc962019.aspx). Ve zjednodušené podobě kryptografie nahrazuje neboli transponuje písmena a tím vytvoří zakódovanou zprávu, která je nečitelná, utajená nebo skrytá. Jenom člověk s dekódovacím klíčem, neboli _certifikátem_, může zakódovanou zprávu převést zpět do její původní čitelné formy. Vaše zařízení s Androidem používá certifikáty s Intune, aby se zajistilo, že komunikace mezi zařízením a prostředky organizace, jako je e-mail a dokumenty, byla zabezpečená na jednom konci, po dobu přenosu i na druhém konci.

## <a name="fixing-certificate-issues"></a>Oprava problémů s certifikáty

Pokud zařízení s Androidem nemáte zaregistrované v Intune a chybí mu konkrétní certifikát, který vyžaduje firemní podpora, nebudete se k aplikaci Portál společnosti moct přihlásit. Při pokusu o přihlášení se zobrazí tato zpráva:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

První možnost, kterou byste měli zkusit, je zjistit, jestli v zařízení [nechybí certifikát, který je na něm obvykle předinstalovaný](your-device-is-missing-a-preinstalled-certificate-android.md).

Pokud to nepomůže, vaše firemní podpora by vás mohla [požádat, abyste si nainstalovali druhý certifikát ke zvýšení zabezpečení](your-device-is-missing-an-IT-required-certificate-android.md).

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://portal.manage.microsoft.com#HelpDeskDialog).
