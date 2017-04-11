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
ms.assetid: f0ba4cbb-ef0a-4335-86bf-f1d006867fa2
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
translationtype: Human Translation
ms.sourcegitcommit: d6fcfac7c8bd469f5163ec9b4017ae8c3d486428
ms.openlocfilehash: 88770ba06718a767f8229e1b5aa4d543c87bc852
ms.lasthandoff: 01/05/2017

---

# <a name="your-android-device-is-missing-a-certificate-required-by-your-it-admin"></a>Ve vašem zařízení s Androidem chybí certifikát, který vyžaduje správce IT

Pokud zařízení nemáte zaregistrované v Intune a chybí mu konkrétní certifikát, který vyžaduje správce IT, nebudete se moct přihlásit k aplikaci Portál společnosti. Při pokusu o přihlášení se zobrazí tato zpráva:

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

Pokud chcete tyto potíže vyřešit a získat požadovaný certifikát, musíte udělat dva hlavní kroky:

- Určit chybějící certifikát pomocí pracovního nebo školního počítače.
- Pomocí vašeho zařízení stáhnout chybějící certifikát z internetu.

## <a name="identify-the-missing-certificate-by-looking-on-a-company-or-school-pc"></a>Určení chybějícího certifikátu pomocí pracovního nebo školního počítače

1. Na počítači otevřete aplikaci Internet Explorer. Pokud nemáte počítač, který byste k těmto účelům mohli využít, obraťte se na správce IT. Kontaktní informace na svého správce IT najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).

2. Přejděte na [web Portál společnosti](http://portal.manage.microsoft.com) a přihlaste se pomocí pracovních nebo školních přihlašovacích údajů.

3. Na adresním řádku prohlížeče vyberte úplně vpravo symbol, který vypadá jako visací zámek, jak je vidět na následujícím snímku obrazovky.

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

    Pokud se symbol visacího zámku nezobrazuje, přestaňte a kontaktujte správce IT. Zámek znamená, že jste úspěšně přihlášení. Proto byste neměli pokračovat, dokud tento symbol neuvidíte.

4. Vyberte **Zobrazit certifikáty**.

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. V dialogovém okně **Certifikáty** vyberte kartu **Cesta k certifikátu** a potom určete certifikát, který potřebujete získat z internetu. Název certifikátu, který potřebujete, se zobrazí na stejné pozici jako název zvýrazněný na předchozím snímku obrazovky s příkladem.

## <a name="download-and-install-the-missing-certificate-on-your-android-mobile-device"></a>Stažení a instalace chybějícího certifikátu na mobilním zařízení s Androidem

1. Pomocí vyhledávacího webu jako Bing nebo Google vyhledejte název chybějícího certifikátu, který jste určili v předchozí části. Název certifikátu může mít různé přípony, třeba .crt nebo .pem.

2. Stáhněte si kořenový certifikát z webu.

3. Po stažení certifikátu si přetažením dolů z horní části zařízení otevřete oznámení a potom v seznamu oznámení klepněte na název požadovaného certifikátu.

4. V dialogovém okně **Název certifikátu** zobrazeném na následujícím snímku obrazovky přijměte výchozí název certifikátu.

5. Ujistěte se, že **Použití přihlašovacích údajů** je nastavené na **Použito pro VPN a aplikace**, a potom klepněte na **OK**.

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. Zavřete aplikaci Portál společnosti.

7. Aplikaci Portál společnosti znovu otevřete. Teď už by mělo být možné se k aplikaci Portál společnosti přihlásit. Pokud potřebujete pomoc, obraťte se na správce IT.

Pokud se vám stejná zpráva typu Chybějící certifikát už zobrazila a už jste použili popsaný postup, pravděpodobně je ještě další certifikát, s jehož instalací vám musí pomoct správce IT. Obraťte se o pomoc na správce IT pomocí kontaktních informací, které jsou dostupné na [webu Portál společnosti](http://portal.manage.microsoft.com).

