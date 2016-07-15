---
title: "Zařízení nemá požadovaný certifikát | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: jeffgilb
ms.date: 05/31/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 0bb435b87c937ea118a0794c8332b9a8f268d36e
ms.openlocfilehash: 6e887d226228d073dc136b50ba9320ada996a6cd


---


# Zařízení nemá požadovaný certifikát
Pokud zařízení s Androidem není zaregistrované v Intune a chybí mu certifikát, který je obvykle nainstalovaný v telefonu, nebudete se k aplikaci Portál společnosti pro Android moct přihlásit. Při pokusu o přihlášení se zobrazí tato zpráva:

![andr-cert-install-cert-missing](./media/andr-cert_install-1-cert_missing.png)

Pokud chcete problém vyřešit a získat požadovaný certifikát:

1.  V prohlížeči přejděte na tuto [stránku certifikátu Digicert](https://www.digicert.com/digicert-root-certificates.htm).

2.  Vyhledejte certifikát Baltimore CyberTrust Root (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt) a stáhněte ho.

3.  Přetažením dolů otevřete oznámení a v jejich seznamu klepněte na **BaltimoreCyberTrustRoot.crt**.

4.  Na obrazovce **Název certifikátu** přijměte výchozí název certifikátu.

5. Ujistěte se, že **Použití přihlašovacích údajů** je nastavené na **Použito pro VPN a aplikace**, a potom klepněte na **OK**.

    ![andr-cert-install-add-cert-name](./media/andr-cert_install-2-add_cert_name.png)

6. Zavřete webový prohlížeč a aplikaci Portál společnosti.

7. Aplikaci Portál společnosti znovu otevřete. Teď už by mělo být možné se k aplikaci Portál společnosti přihlásit. Pokud potřebujete pomoc, obraťte se na správce IT.

Potřebujete ještě další pomoc? Obraťte se na správce IT. Jeho kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).


<!--HONumber=Jun16_HO4-->


