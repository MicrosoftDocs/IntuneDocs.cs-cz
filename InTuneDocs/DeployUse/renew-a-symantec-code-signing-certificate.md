---
title: "Obnovení certifikátu Symantec Enterprise pro podpis kódu pro použití s Microsoft Intune | Microsoft Intune"
description: 
keywords: 
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c4813044-a925-4273-b0ec-e992fd55850a
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: 566a226c19825990c6a34bffbbd9d1cd6a242ddb


---

# Obnovení certifikátu Symantec Enterprise pro podpis kódu pro použití s Microsoft Intune

Certifikát od Symantecu použitý ke správě určitých mobilních zařízení s Windows a Windows Phone se musí pravidelně obnovovat. Pro zařízení Windows Phone 8.0 se pro registraci zařízení potřebuje podepsaná aplikace Portál společnosti a certifikát pro podpis kódu. Novější zařízení Windows Phone může používat aplikaci firemního portálu staženou z Windows Store. Certifikát pro podpis kódu se vyžaduje i pro nasazení obchodních aplikací.

## Jak obnovit certifikát Symantec Enterprise pro podpis kódu

1.  Najděte e-mail s informacemi o obnovení, který vám Symantec poslal přibližně 14 dnů před vypršením platnosti certifikátu. V tomto e-mailu jsou pokyny od Symantecu o obnovení vašeho podnikového certifikátu.

    Další informace o certifikátech Symantec získáte na webu [www.symantec.com](http://www.symantec.com) nebo telefonním čísle 1-877-438-8776 nebo 1-650-426-3400.

2.  Přejděte na web (příklad: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) a přihlaste se s ID vydavatele od Symantecu a e-mailovou adresou spojenou s certifikátem. Ke spuštění obnovení musíte použít stejný počítač, který použijete ke stažení certifikátu.

3.  Po schválení a zaplacení obnovení si stáhněte certifikát.

## Jak nainstalovat aktualizovaný certifikát pro Windows Phone 8.0

1.  Stáhněte si a podepište nejnovější Portál společnosti Windows Phone, který najdete tady: [http://www.microsoft.com/cs-cz/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Otevřete konzolu pro správu Intune ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)), přejděte na **Správce**, **Správa mobilních zařízení** &gt; **Windows Phone** a klikněte na **Nahrát podepsanou aplikaci**.

3.  Nahrajte nově podepsaný firemní portál. Budete potřebovat nově podepsaný soubor SSP.xap a nový soubor .PFX, který jste dostali od Symantecu, nebo token pro zápis aplikace vytvořený pomocí tohoto nového souboru .PFX.

4.  Až se nahrávání dokončí, odeberte předchozí verzi aplikace Portál společnosti v pracovní prostoru **Software** v konzole pro správu Intune.

5.  Podepište znovu všechny podnikové a firemní aplikace stejným certifikátem a nahrajte a nahraďte stávající aplikace.

Poskytnutí podepsaného souboru SSP.xap je aktuálně jedinou možností, jak poskytnout aktualizovaný certifikát pro podepisování kódu. Aby byla zajištěná podpora podepsaných obchodních aplikací, je nutné podepsat a nahrát aplikaci Portál společnosti i v případě, že si uživatelé nainstalují aplikaci Portál společnosti ze Storu.

## Jak nainstalovat aktualizovaný certifikát pro zařízení s Windows Phone 8.1 a novějším systémem

1.  Stáhněte si a podepište nejnovější Portál společnosti Windows Phone z webu Stažení softwaru, který najdete tady: [http://www.microsoft.com/cs-cz/download/details.aspx?id=36060](http://www.microsoft.com/en-us/download/details.aspx?id=36060).

2.  Otevřete konzolu pro správu Intune ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)), přejděte na **Správce**, &gt;Správa mobilních zařízení** ** &gt; **Windows Phone** a klikněte na **Nahrát podepsanou aplikaci**.

3.  Nahrajte nově podepsaný firemní portál. Budete potřebovat nově podepsaný soubor SSP.xap a nový soubor .PFX, který jste dostali od Symantecu, nebo token pro zápis aplikace vytvořený pomocí tohoto nového souboru .PFX.

4.  Po dokončení nahrávání odeberte předchozí verzi aplikace Portál společnosti v pracovním prostoru **Software**  .

5.  Zaregistrujte všechny nové a aktualizované podnikové aplikace pomocí nového certifikátu. Stávající aplikace není nutné znovu podepisovat a nasazovat.


### Související témata
[Nastavení správy pro zařízení Windows Phone 8.0](set-up-windows-phone-8.0-management-with-microsoft-intune.md)
[Nastavení správy pro zařízení Windows Phone](set-up-windows-phone-management-with-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


