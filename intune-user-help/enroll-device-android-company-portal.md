---
title: Registrace zařízení s Androidem pomocí Portál společnosti Intune | Microsoft Docs
description: Popisuje, jak zaregistrovat zařízení s Androidem pomocí Portál společnosti Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 04/19/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: ''
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1670ddf9299d12312f09d188e4410d14ac40fbe7
ms.sourcegitcommit: 9013f7442bbface78feecde2922e8e546a622c16
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/16/2019
ms.locfileid: "72506335"
---
# <a name="enroll-your-device-with-company-portal"></a>Registrace zařízení pomocí Portál společnosti  
Pokud chcete získat zabezpečený přístup k firemnímu e-mailu, aplikacím a datům, zaregistrujte své osobní nebo firemní zařízení s Androidem. Portál společnosti podporuje zařízení s Androidem, včetně Samsung KNOX, se systémem Android 4,4 a novějším.  
</br>
> [!VIDEO https://www.youtube.com/embed/k0Q_sGLSx6o?rel=0]

> [!NOTE]
> Samsung KNOX je typ zabezpečení, který některá zařízení Samsung využívají k další ochraně mimo rámec toho, co poskytuje nativní Android. Pokud chcete zjistit, jestli máte zařízení Samsung KNOX, > Přejít na **nastavení** > **o zařízení**. Pokud se tam uvedená **verze Knox** nezobrazuje, máte nativní zařízení s Androidem.

## <a name="enroll-device"></a>Registrace zařízení  
Nezapomeňte si [z Google Play nainstalovat bezplatnou aplikaci Portál společnosti Intune](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal). 

Během registrace můžete být požádáni, abyste zvolili kategorii, která nejlépe popisuje způsob používání zařízení. Vaše firemní podpora používá vaši odpověď ke kontrole aplikací, ke kterým máte přístup.  

1. Otevřete aplikaci Portál společnosti.  

3. Na **úvodní** obrazovce aplikace Portál společnosti klepněte na **Přihlásit se** a pak se přihlaste pomocí svého pracovního nebo školního účtu.

   ![Uvítací stránka aplikace Portál společnosti pro Android, která uživatele žádá, aby se přihlásili pomocí svého požadované pracovního nebo školního účtu. Také varuje, že se nedá použít účet Microsoft ani jiné osobní účty.](./media/and-enroll-0-welcome-screen.png)   

4. Pokud se zobrazí výzva, abyste přijali podmínky a ujednání vaší organizace, klepněte na **přijmout**. Tato obrazovka může být trochu odlišná od ukázkového snímku obrazovky níže. 

   ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5. Přihlaste se k aplikaci Portál společnosti zadáním svého pracovního nebo školního účtu a hesla a potom klepněte na **Přihlásit se**.

   ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6. Na obrazovce **Nastavení firemního přístupu** klepněte na **POKRAČOVAT**.

   ![Obrazovka nastavení přístupu společnosti](/intune/media/android_cp_enroll_01_1709_new.png)

   > [!NOTE]
   > Žluté trojúhelníky neznamenají, že už došlo k chybě. Tyto ikony označují, že ještě existují kroky, které se musí v procesu registrace dokončit.

7. Prohlédněte si seznam toho, co firemní podpora na vašem zařízení uvidí nebo neuvidí, a klepněte na **POKRAČOVAT**.

   ![Nastavení ochrany osobních údajů](/intune/media/android_cp_enroll_02_after_1710.png)

8. Na obrazovce **Co dál?** si přečtěte, co probíhá během registrace, a potom klepněte na **REGISTROVAT**.

   ![Obrazovka Co dál](/intune/media/android_cp_enroll_03_after_1710.png)

9. Pokud používáte Android 6.0 nebo novější, proveďte tento krok. V opačném případě přejděte k dalšímu kroku.

   Pokud firemní podpora nastavila konkrétní zásady, mohou se zobrazit následující zprávy:
   - **Povolit pro Portál společnosti telefonování a správu telefonních hovorů?**

     ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

   Pokud se zobrazí tato zpráva, klepněte na **POVOLIT**. Na POVOLIT můžete bezpečně klepnout, protože **Microsoft za vás nikdy netelefonuje, ani nespravuje vaše telefonní hovory**. Text zprávy určuje společnost Google a Microsoft ho nemůže změnit. Pokud přístup povolíte, umožníte, aby zařízení poslalo do Intune svoje číslo IMEI (International Mobile Equipment Identity). Číslo IMEI je něco jako sériové číslo, které jednoznačně identifikuje mobilní zařízení.

   Pokud přístup odepřete, při příštím přihlášení k Portál společnosti se tato zpráva zobrazí znovu. Pokud chcete vypnout budoucí zprávy, vyberte příště **nedotazovat**se. Chcete-li změnit oprávnění k přístupu, přejděte do **nastavení** > **aplikace** > **portál společnosti**@no__t **-5 @no__t**-7**Phone**a pak toto oprávnění zapněte.  

   - **Povolit pro Portál společnosti přístup k vašim kontaktům?**

     ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

     Pokud se zobrazí tato zpráva, klepněte na **POVOLIT**. Na POVOLIT můžete bezpečně klepnout, protože **Microsoft nikdy nevyužívá přístup k vašim kontaktům**. Text zprávy určuje společnost Google a Microsoft ho nemůže změnit. Pokud přístup povolíte, umožníte aplikaci Portál společnosti jenom vytvářet, používat a spravovat váš pracovní účet.

     Pokud přístup odmítnete, zobrazí se tato zpráva znovu při příštím přihlášení k portálu společnosti, ale další zprávy můžete vypnout zaškrtnutím políčka **Příště se už neptat**. Pokud se později rozhodnete povolit přístup, použijte možnost **Nastavení** &gt; **Aplikace** &gt; **Portál společnosti** &gt; **Oprávnění** &gt; **Telefon** a tato oprávnění aktivujte.

10. Na obrazovce **Aktivovat správce zařízení** klepněte na **Aktivovat**.

    ![Obrazovka Aktivovat správce zařízení](./media/and-enroll-5-activate.png)

    Portál společnosti potřebuje ke správě vašeho zařízení roli správce zařízení. Ta umožňuje vašemu správci například zobrazit si, kolikrát jste se pokusili odemknout obrazovku a provést nějaké akce.    

    Microsoft tuto zprávu nemůže nijak ovlivnit a rozumíme, že její formulace se může zdát poněkud radikální. Neexistuje žádný způsob, kterým by Portál společnosti mohl zobrazovat omezení a přístup, které jsou relevantní pouze pro vaši organizaci. Na této obrazovce je udělujete všechny najednou. Pokud máte otázky týkající se použití konkrétně ve své organizaci, požádejte o další informace firemní podporu (pomocí kontaktních informací na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980)).  

11. Podle pokynů zadejte kód PIN nebo heslo. Pokud jste už kód PIN nebo heslo v daném zařízení nastavili, tato obrazovka se buď neobjeví, nebo budete muset zadat nový kód PIN a heslo.  

    ![Zadání kódu PIN nebo hesla](./media/and-enroll-6-PIN-native.png)

12. Pokud používáte zařízení s funkcí Samsung Knox, klepněte na **Potvrdit** a zobrazí se zpráva o registraci zařízení. Pokud používáte nativní zařízení s Androidem, všimnete si jenom následující obrazovky, která označuje, že vaše zařízení se registruje.

    ![Zásady ochrany osobních údajů Samsung Knox](./media/and-enroll-7-knox-privacy-policy.png)

    Tato obrazovka informuje o registraci zařízení.

    ![Obrazovka registrace zařízení](./media/and-enroll-8-device-enrolling.png)

13. Když se zobrazí stránka **Nastavení firemního přístupu**, klepněte na **POKRAČOVAT**. Pokud se zobrazí zpráva, že vaše zařízení nedodržuje předpisy, podle pokynů tento problém vyřešte a pak klepněte na **POKRAČOVAT**.

    ![Zařízení nedodržuje předpisy, ale je zaregistrované.](/intune/media/android_cp_enroll_05_post_1709.png)

    ![Zobrazí se problémy zařízení s dodržením předpisů, které je potřeba vyřešit.](/intune/media/android_cp_enroll_03_post_1709.png)

    Další informace o problémech zjistíte, když na ně klepnete.

    ![Rozbalené problémy zařízení s dodržením předpisů](/intune/media/android_cp_enroll_04_post_1709.png)

    ![Obrazovka nastavení přístupu společnosti](./media/and-enroll-9d-comp-access-setup.png)  

14. Na obrazovce **Nastavení firemního přístupu je hotové** klepněte na **HOTOVO**. Právě jste svoje zařízení zaregistrovali.

    ![Obrazovka Nastavení firemního přístupu je hotové](./media/and-enroll-10-comp-access-setup-complete.png)

## <a name="next-steps"></a>Další kroky  

Než se pokusíte nainstalovat firemní aplikace, pokračujte na **nastavení** > **zabezpečení**a zapněte **neznámé zdroje**. Pokud před instalací firemních aplikací tuto možnost nezapnete, zobrazí se tato zpráva: „Instalace blokována. Z důvodů zabezpečení je v zařízení nastavené blokování instalací pro aplikace získané z neznámého zdroje.“ Klepnutím na **Nastavení** v dialogovém okně s chybou můžete přejít na možnost **Neznámé zdroje**.  

> [!Note]
> Pokud vaše organizace používá software pro správu telekomunikačních výdajů (Telecom Expense Management), budete muset před úplnou registrací zařízení provést několik dalších kroků. Další informace najdete [tady](enroll-your-device-with-telecom-expense-management-android.md).

Pokud při pokusu o registraci zařízení do služby Intune dojde k chybě, můžete [Odeslat e-mailovou podporu společnosti](send-logs-to-your-it-admin-by-email-android.md).  

Potřebujete ještě další pomoc? Obraťte se na svou firemní podporu (kontaktní údaje najdete na [webu Portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980)) nebo napište <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">týmu Microsoft Android</a>.
