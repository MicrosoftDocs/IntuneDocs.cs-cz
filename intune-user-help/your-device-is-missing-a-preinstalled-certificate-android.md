---
title: "Zařízení nemá certifikát | Dokumentace Microsoftu"
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
ms.assetid: df973b18-9166-417d-8aa3-49edd2bda256
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 63595e9905a220c326c315f5932379a9b743d3de
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017

---

# <a name="your-android-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone"></a>Ve vašem zařízení s Androidem chybí certifikát, který je v telefonu obvykle nainstalovaný

Pokud zařízení není zaregistrované v Intune a chybí mu certifikát, který je v telefonu obvykle nainstalovaný, nebudete se k aplikaci Portál společnosti moct přihlásit. Při pokusu o přihlášení se zobrazí tato zpráva:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Tento problém můžete opravit, když si požadovaný certifikát stáhnete ze [stránky certifikátů Digicertu](https://www.digicert.com/digicert-root-certificates.htm).

1. Vyhledejte a stáhněte si certifikát __Baltimore CyberTrust Root__. Můžete si ho také stáhnout přímo [odsud](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).

2. Přetažením dolů z horní části obrazovky zobrazte seznam s posledními oznámeními a klepněte na **BaltimoreCyberTrustRoot.crt**.

3. Vaše zařízení vás vyzve k **pojmenování certifikátu**. Neměňte výchozí název certifikátu, který se zobrazí.

4. Ujistěte se, že **Použití přihlašovacích údajů** je nastavené na **Použito pro VPN a aplikace**, a potom klepněte na **OK**.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

5. Zavřete prohlížeč a aplikaci Portál společnosti.

6. Aplikaci Portál společnosti znovu otevřete. Teď už by mělo být možné se k aplikaci Portál společnosti přihlásit. Pokud stále nemůžete aplikaci Portál společnosti použít, kontaktujte svého správce IT pomocí informací uvedených na [webu Portál společnosti](http://portal.manage.microsoft.com), aby vám sdělil další pokyny.

>[!NOTE]
> Pokud instalace tohoto certifikátu problém nevyřeší a zobrazí se vám jiná zpráva o chybějícím certifikátu, bude nutné provést další kroky k [instalaci chybějícího certifikátu](your-device-is-missing-an-IT-required-certificate-android.md).

Potřebujete ještě další pomoc? Obraťte se na správce IT. Kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).

