---
title: Zařízení nemá požadovaný certifikát | Dokumentace Microsoftu
titlesuffix: Microsoft Intune
description: Vašemu zařízení chybí certifikát, který vyžaduje firemní podpora.
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 12/06/2018
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
ms.custom: intune-enduser; seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: cc86a53dd790059297430fd6b08f1a699aafbc84
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "55850654"
---
# <a name="your-device-is-missing-a-required-certificate"></a>Zařízení nemá požadovaný certifikát

## <a name="whats-a-certificate"></a>Co je certifikát?

[Kryptografie](https://technet.microsoft.com/library/cc962030.aspx) je věda, jak poskytovat zabezpečení informacím. V tradičním pojetí kryptografie sloužila k předávání zakódovaných zpráv, což mělo [zajistit utajení komunikace](https://technet.microsoft.com/library/cc962019.aspx). Šifrování v podobě simplist nahradí nebo transponuje písmena vytvoří zakódovanou zprávu do zprávy nečitelná, utajená nebo skrytá. Jenom člověk s dekódovacím klíčem, neboli _certifikátem_, může zakódovanou zprávu převést zpět do její původní čitelné formy. Vaše zařízení s Androidem používá certifikáty s Intune, aby se zajistilo, že komunikace mezi zařízením a prostředky organizace, jako je e-mail a dokumenty, byla zabezpečená na jednom konci, po dobu přenosu i na druhém konci.

## <a name="fixing-certificate-issues"></a>Oprava problémů s certifikáty

Pokud zařízení s Androidem nemáte zaregistrované v Intune a chybí mu konkrétní certifikát, který vyžaduje firemní podpora, nebudete se k aplikaci Portál společnosti moct přihlásit. Při pokusu o přihlášení se zobrazí tato zpráva:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

První možnost, kterou byste měli zkusit, je zjistit, jestli v zařízení [nechybí certifikát, který je na něm obvykle předinstalovaný](your-device-is-missing-a-preinstalled-certificate-android.md).

Pokud řešení problémů s certifikáty nebude fungovat, může vaše firemní podpora [vyžadují, abyste si nainstalovali druhý certifikát ke zvýšení zabezpečení](your-device-is-missing-an-IT-required-certificate-android.md).

Potřebujete ještě další pomoc? Obraťte se na podporu ve vaší společnosti. Kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980).
