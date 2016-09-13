---
title: "Registrace zařízení s Windows 10 v Intune | Microsoft Intune"
description: "Popisuje registraci mobilních nebo desktopových zařízení s Windows 10 v Intune."
keywords: 
author: Staciebarker
manager: angrobe
ms.date: 06/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 36250832-c6fd-4e8d-b681-de735023ebc3
ms.reviewer: priyar
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 02287eb01598c28906045fd8def9e8b4660e3da5
ms.openlocfilehash: 8806231f8d02885a192053a35559694a8984d2f5


---


# Registrace zařízení s Windows 10 Mobile nebo Windows 10 Desktop v Intune

Pokud vaše společnost nebo škola používá Microsoft Intune, můžete svá zařízení zaregistrovat, a získat tak přístup k e-mailům, souborům a dalším prostředkům společnosti. Registrace zařízení umožňuje vaší organizaci zabezpečit podniková data. Další informace o registraci najdete v tématu [Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení v Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-windows.md) a v tématu [Co má a nemá správce IT oprávnění vidět na vašem zařízení](what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows.md).


Registrace zařízení s Windows 10 Mobile nebo Windows 10 Desktop:

1.  Ve Windows přejděte do **Nastavení** a klepněte na **Účty**.

    ![settings-accounts](./media/w10-enroll-rs1-settings-accounts.png)

2.  Podívejte se na další dvě obrazovky a najděte tu, která vypadá stejně jako to, co vidíte ve svém zařízení. Použijte postup odpovídající této obrazovce.

    Pokud se zobrazí tato obrazovka, použijte postup v tématu [Postup, pokud se zobrazí Přístup do práce nebo do školy](#steps-to-follow-if-you-see-access-work-or-school).

    ![connect-to-work-or-school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Pokud se zobrazí tato obrazovka, použijte postup v tématu [Postup, pokud se zobrazí Váš účet](#steps-to-follow-if-you-see-your-account).

    ![your-account](./media/w10-enroll-2-accounts-your-account.png)

## Postup, pokud se zobrazí Přístup do práce nebo do školy

1.  Klepněte na **Přístup do práce nebo do školy**.

    ![tap-access-work-school-account](./media/w10-enroll-rs1-connect-to-work-or-school.png)

2.  Zadejte svůj pracovní nebo školní e-mail a klepněte na **Další**.

    ![enter-your-work-or-school-account](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

3. Přihlaste se k Intune ze svého pracovního nebo školního účtu.

    ![add-work-school-account](./media/w10-enroll-rs1-enter-your-credentials.png)

    Zobrazí se zpráva, že organizace nebo škola registruje vaše zařízení.

4. Když se zobrazí stránka **Všechno máte nastavené**, klepněte na **Zavřít**. Máte hotovo.

  ![tap-close-on-you-are-all-set-screen](./media/w10-enroll-rs1-youre-all-set.png)

5. Pokud chcete zkontrolovat, že připojení je v pořádku, vraťte se k **Nastavení** a přesvědčte se, že je tam váš pracovní nebo školní účet uvedený.

    ![validate-that-connection-was-set-up-correctly](./media/w10-enroll-rs1-validate-successful-enrollment.png)

Pokud jste použili výše uvedené kroky, ale pořád nemáte přístup ke svému pracovnímu e-mailu nebo souborům, použijte kroky v části [Postup řešení potíží, pokud se zobrazí Přístup do práce nebo do školy](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).


## Postup, pokud se zobrazí Váš účet

1.  Ve Windows přejděte do **Nastavení** a klepněte na **Účty**.

    ![go-to-settings-accounts](./media/W10-enroll-1-settings-accounts.png)

2.  Klepněte na **Váš účet**.

    ![tap-your-account](./media/W10-enroll-2-accounts-your-account.png)

3.  Klepněte na **Přidat pracovní nebo školní účet**.

    ![add-work-or-school-account](./media/w10-enroll-3-add-work-school-acct.png)

4.  Přihlaste se pomocí přihlašovacích údajů svého pracovního nebo školního účtu.

    ![sign-in](./media/W10-enroll-4-sign-in.png)

Pokud jste použili výše uvedené kroky, ale pořád nemáte přístup ke svému pracovnímu e-mailu, souborům a dalším datům, použijte kroky v části [Postup řešení potíží, pokud se zobrazí Váš účet](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account).

Doporučujeme také nainstalovat aplikaci Portál společnosti, která vám umožní snadno identifikovat a instalovat podnikové aplikace, které jsou relevantní pro vás i vaši roli. V závislosti na tom, jak vaše společnost službu Intune nakonfigurovala, už aplikace Portál společnosti může být nainstalovaná jako součást procesu registrace. Pokud chcete zjistit, jestli aplikaci máte, hledejte v seznamu aplikací aplikaci **Portál společnosti**. Pokud aplikaci Portál společnosti v seznamu nenajdete, nainstalujte ji podle následujícího postupu.

1.  Klepněte na **Start** &gt; **Store**.

2.  Klepněte na **Hledat** a napište **portál společnosti**.

3.  V seznamu výsledků klepněte na **Portál společnosti** &gt; **Instalovat**.

4.  Klepněte buď na **Instalovat**, nebo na **Zdarma**. To, která z možností se zobrazuje, závisí na tom, jak vaše společnost aplikaci nakonfigurovala.

Potřebujete ještě další pomoc? Obraťte se na správce IT. Jeho kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).

### Související témata
[Použití zařízení Windows s Intune](using-your-windows-device-with-intune.md)



<!--HONumber=Aug16_HO3-->


