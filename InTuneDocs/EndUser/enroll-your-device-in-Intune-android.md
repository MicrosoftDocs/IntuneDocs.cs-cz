---
title: "Registrace zařízení s Androidem v Intune | Microsoft Intune"
description: 
keywords: 
author: staciebarker
manager: jeffgilb
ms.date: 06/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
ms.reviewer: arnab
ms.suite: ems
ms.sourcegitcommit: 0bb435b87c937ea118a0794c8332b9a8f268d36e
ms.openlocfilehash: 76cc1a43e09039285be76858155ef22f7b41cf9b


---


# Registrace zařízení se systémem Android do Intune

Pokud vaše společnost nebo škola používá Microsoft Intune, můžete svoje zařízení s Androidem zaregistrovat a získat tak přístup k e-mailům, souborům a dalším prostředkům společnosti. Registrace zařízení umožní vašemu IT oddělení spravovat tyto školní nebo firemní prostředky a zajistit jejich zabezpečení a současně vám dá volnost, abyste ke své práci využívali zařízení, kterému dáváte přednost. Další informace o registraci najdete v tématu [Co se stane, když nainstaluji aplikaci Portál společnosti a zaregistruji zařízení](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md).

Tyto pokyny pro registraci jsou určené pro zařízení Samsung Knox s Androidem a „nativní“ zařízení s Androidem (jiná než Samsung Knox). Pokud chcete zjistit, jestli máte zařízení Samsung Knox, přejděte na **Nastavení** &gt; **O zařízení**. Pokud se tu nezobrazí verze Knoxu, máte nativní zařízení s Androidem.

Před registrací nebo po ní se může zobrazit výzva k výběru kategorie, která nejlépe vystihuje způsob použití vašeho zařízení. Váš správce IT pomocí této aplikace určuje, ke kterým aplikacím máte mít přístup.

Pokud při pokusu o registraci zařízení do služby Intune dojde k chybě, projděte si téma [Odeslání chyb při registraci správci IT](send-enrollment-errors-to-your-it-administrator-android.md).

**Postup při registraci zařízení se systémem Android:**

1.  Nainstalujte si bezplatnou aplikaci Portál společnosti Intune z [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).

2.  Otevřete aplikaci Portál společnosti Microsoft Intune.

3.  Na **úvodní** obrazovce portálu společnosti klepněte na **Přihlásit** a pak se přihlaste pomocí svého pracovního nebo školního účtu.

    ![android-company-portal-sign-in](./media/and-enroll-0-welcome-screen.png)   

4.  Pokud váš správce IT nastavil firemní podmínky a ujednání, přijměte je klepnutím na **PŘIJMOUT**.

    ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5.  Pokud používáte Android 6.0 nebo novější, proveďte tento krok. V opačném případě přejděte k dalšímu kroku. 

    Pokud správce IT nastavil konkrétní zásady, mohou se zobrazit následující zprávy:
    -   **Povolit pro Portál společnosti telefonování a správu telefonních hovorů?**

    ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

    Pokud se zobrazí tato zpráva, klepněte na **POVOLIT**. Klepnout na POVOLIT je bezpečné, protože **Microsoft nikdy netelefonuje ani nespravuje telefonní hovory**. Text zprávy určuje společnost Google a Microsoft ho nemůže změnit. Když povolíte přístup, povolíte na svém zařízení jenom zápis datových protokolů na kartu SD zařízení, takže tyto protokoly můžete přesouvat pomocí kabelu USB.

    Pokud přístup odepřete, při příštím přihlášení k portálu společnosti se zpráva zobrazí znovu, ale další zprávy už můžete vypnout zaškrtnutím políčka **Příště se už neptat**.  Pokud se později rozhodnete povolit přístup, použijte možnost **Nastavení** &gt; **Aplikace** &gt; **Portál společnosti** &gt; **Oprávnění** &gt; **Telefon** a tato oprávnění aktivujte.

    -   **Povolit pro Portál společnosti přístup k vašim kontaktům?**

    ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

    Pokud se zobrazí tato zpráva, klepněte na **POVOLIT**. Klepnout na POVOLIT je bezpečné, protože **Microsoft nikdy nevyužívá přístup k vašim kontaktům**. Text zprávy určuje společnost Google a Microsoft ho nemůže změnit. Když povolíte přístup, umožňuje aplikaci Portál společnosti jenom vytvářet, používat a spravovat váš pracovní účet.

    Pokud přístup odepřete, při příštím klepnutí na **Odeslat data** se zpráva zobrazí znovu, ale další zprávy už můžete vypnout zaškrtnutím políčka **Příště se už neptat**. Pokud se později rozhodnete povolit přístup, použijte možnost **Nastavení** &gt; **Aplikace** &gt; **Portál společnosti** &gt; **Oprávnění** &gt; **Úložiště** a pak tato oprávnění aktivujte.

6.  Přihlaste se k aplikaci Portál společnosti zadáním svého pracovního nebo školního účtu a hesla a potom klepněte na **Přihlásit**.

    ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

7.  Na obrazovce **Nastavení firemního přístupu** klepněte na **ZAČÍT**.

    ![Obrazovka nastavení přístupu společnosti](./media/and-enroll-4a-comp-access-setup.png)

8.  Na obrazovce **Proč zařízení registrovat?** si přečtěte informace o tom, co vám registrace zařízení umožní, a potom klepněte na **POKRAČOVAT**.

    ![Obrazovka Proč zařízení registrovat](./media/and-enroll-4b-why-enroll.png)

9.  Přečtěte si informace o tom, co správce IT uvidí nebo neuvidí ve vašem zařízení, a klepněte na **POKRAČOVAT**.

    ![Nastavení ochrany osobních údajů](./media/and-enroll-4c-we-care-privacy.png)

10.  Na obrazovce **Co dál?** si přečtěte, co probíhá při registraci, a potom klepněte na **REGISTROVAT**.

    ![Obrazovka Co dál](./media/and-enroll-4d-what-comes-next.png)

11.  Na obrazovce **Aktivovat správce zařízení** klepněte na **Aktivovat**.

    ![Obrazovka Aktivovat správce zařízení](./media/and-enroll-5-activate.png)

12.  Podle pokynů zadejte kód PIN nebo heslo. Pokud jste už kód PIN nebo heslo v daném zařízení nastavili, tato obrazovka se buď neobjeví, nebo budete muset zadat nový kód PIN a heslo.

    ![Zadání kódu PIN nebo hesla](./media/and-enroll-6-PIN-native.png)

13.  Postupujte podle pokynů níže, které odpovídají typu používaného zařízení (nativní Android nebo Samsung Knox). Pokud chcete zjistit, jestli máte zařízení Samsung Knox, přejděte na **Nastavení** &gt; **O zařízení**. Pokud se tu nezobrazí verze Knoxu, máte nativní zařízení s Androidem.

    -   Nativní zařízení (jiné než Samsung Knox): Na obrazovce **Název certifikátu** přijměte výchozí certifikát klepnutím na **OK**.

    ![Obrazovka Název certifikátu](./media/and-enroll-7-cert-native.png)

    -   Zařízení Samsung Knox: Přijměte zásady ochrany osobních údajů a klepněte na **POTVRDIT**.

    ![Zásady ochrany osobních údajů Samsung KNOX](./media/and-enroll-7-knox-privacy-policy.png)

    Při registraci zařízení v Intune se na obrazovce zobrazí tato zpráva.

    ![Obrazovka registrace zařízení](./media/and-enroll-8-device-enrolling.png)

14. Když se zobrazí stránka **Nastavení firemního přístupu**, klepněte na **POKRAČOVAT**. Pokud se zobrazí zpráva, že vaše zařízení nesplňuje předpisy, podle příslušných pokynů daný problém opravte a potom klepněte na **POKRAČOVAT**.

    ![Obrazovka nastavení přístupu společnosti](./media/and-enroll-9-comp-access-setup.png)  

11. Na obrazovce **Nastavení firemního přístupu je hotové** klepněte na **HOTOVO**. Právě jste svoje zařízení zaregistrovali.

    ![Obrazovka Nastavení firemního přístupu je hotové](./media/and-enroll-10-comp-access-setup-complete.png)

Než začnete instalovat firemní aplikace, přejděte na **Nastavení** &gt; **Zabezpečení** a zapněte **Neznámé zdroje**. Pokud před zahájením instalace firemních aplikací tuto možnost nezapnete, zobrazí se zpráva „Instalace blokována. Z důvodů zabezpečení je v zařízení nastavené blokování instalací pro aplikace získané z neznámého zdroje.“ Klepnutím na **Nastavení** v chybovém dialogovém okně můžete přejít na možnost **Neznámé zdroje**.

Potřebujete ještě další pomoc? Obraťte se na správce IT. Jeho kontaktní údaje najdete na [webu Portál společnosti](http://portal.manage.microsoft.com).

### Související témata
[Použití zařízení Android s Intune](using-your-android-device-with-intune.md)



<!--HONumber=Jun16_HO2-->


