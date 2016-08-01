---
title: "Zařízení nemá požadovaný certifikát | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: angrobe
ms.date: 7/7/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9081b1d8-50e8-4bc2-ba37-766421364213
ROBOTS: noindex,nofollow
ms.reviewer: arnab
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 618e2abda642c3b9b2e813824dfd4235c9309faa
ms.openlocfilehash: 220d877763352e62c4057494b69633356ef081c6


---


# Zařízení nemá požadovaný certifikát


## Ve vašem zařízení chybí certifikát, který je obvykle nainstalovaný v telefonu
Pokud zařízení s Androidem není zaregistrované v Intune a chybí mu certifikát, který je obvykle nainstalovaný v telefonu, nebudete se k aplikaci Portál společnosti pro Android moct přihlásit. Při pokusu o přihlášení se zobrazí tato zpráva:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Pokud chcete problém vyřešit a získat požadovaný certifikát:

1.  V prohlížeči přejděte na tuto [stránku certifikátu Digicert](https://www.digicert.com/digicert-root-certificates.htm).

2.  Vyhledejte certifikát Baltimore CyberTrust Root (https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt) a stáhněte ho.

3.  Přetažením dolů otevřete oznámení a v jejich seznamu klepněte na **BaltimoreCyberTrustRoot.crt**.

4.  Na obrazovce **Název certifikátu** přijměte výchozí název certifikátu.

5. Ujistěte se, že **Použití přihlašovacích údajů** je nastavené na **Použito pro VPN a aplikace**, a potom klepněte na **OK**.

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

6. Zavřete webový prohlížeč a aplikaci Portál společnosti.

7. Aplikaci Portál společnosti znovu otevřete. Teď už by mělo být možné se k aplikaci Portál společnosti přihlásit. Pokud potřebujete pomoc, obraťte se na správce IT.

## Ve vašem zařízení chybí certifikát, který vyžaduje správce IT
Pokud zařízení s Androidem není zaregistrované v Intune a chybí mu certifikát, který vyžaduje správce IT, nebudete se k aplikaci Portál společnosti pro Android moct přihlásit. Při pokusu o přihlášení se zobrazí tato zpráva:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

>[!NOTE]
> Pokud se vám už zobrazila zpráva typu Chybějící certifikát a použili jste postup popsaný v části [Ve vašem zařízení chybí certifikát, který je obvykle nainstalovaný v telefonu](#your-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone), nic se neděje. Je to jiná zpráva a také jiný certifikát. Proto pokračujte a k získání chybějícího certifikátu použijte postup v této části.

Pokud chcete tyto potíže vyřešit a získat požadovaný certifikát, musíte udělat dva hlavní kroky:

- Určit chybějící certifikát pomocí pracovního nebo školního počítače.
- Pomocí vašeho zařízení stáhnout chybějící certifikát z internetu.

### Určení chybějícího certifikátu pomocí pracovního nebo školního počítače

1. Na počítači otevřete aplikaci Internet Explorer. Pokud nemáte počítač, který byste k těmto účelům mohli využít, obraťte se na správce IT. Kontaktní údaje správce IT najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).

2. Přejděte na [web Portál společnosti](http://portal.manage.microsoft.com) a přihlaste se pomocí pracovních nebo školních přihlašovacích údajů.

3. Na adresním řádku prohlížeče klikněte nejvíce vpravo na symbol, který vypadá jako visací zámek (viz následující obrázek). Pokud se symbol visacího zámku nezobrazuje, přestaňte a kontaktujte správce IT. Zámek znamená, že jste úspěšně přihlášení. Proto byste neměli pokračovat, dokud tento symbol neuvidíte.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

4. Klikněte na **Zobrazit certifikáty**.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. V dialogovém okně **Certifikáty** klikněte na kartu **Cesta k certifikátu** a potom určete certifikát, který potřebujete získat z internetu. Název certifikátu, který potřebujete se zobrazí na stejné pozici jako název zvýrazněný výš na snímku obrazovky s příkladem.

### Stažení a instalace chybějícího certifikátu na mobilním zařízení s Androidem

1. Pomocí vyhledávacího webu jako Bing nebo Google vyhledejte název chybějícího certifikátu, který jste určili v předchozí části. Název certifikátu může mít různé přípony, třeba .crt nebo .pem.

2. Stáhněte si kořenový certifikát z webu.

3. Po stažení certifikátu si přetažením dolů z horní části zařízení otevřete oznámení a potom v seznamu oznámení klepněte na název požadovaného certifikátu.

4. Na obrazovce **Název certifikátu** přijměte výchozí název certifikátu.

5. Ujistěte se, že **Použití přihlašovacích údajů** je nastavené na **Použito pro VPN a aplikace**, a potom klepněte na **OK**.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Zavřete aplikaci Portál společnosti.

7. Aplikaci Portál společnosti znovu otevřete. Teď už by mělo být možné se k aplikaci Portál společnosti přihlásit. Pokud potřebujete pomoc, obraťte se na správce IT.

Pokud se vám stejná zpráva typu Chybějící certifikát už zobrazila a už jste použili postup popsaný výš, pravděpodobně to znamená, že je ještě další certifikát, s jehož instalací vám musí pomoct správce IT. Kontaktujte správce IT a poskytněte mu tento [odkaz](/intune/troubleshoot/troubleshoot-device-enrollment-in-intune#android-certificate-issues), který obsahuje kroky pro řešení těchto potíží.

### Související témata
[Použití zařízení Windows s Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Jul16_HO4-->


