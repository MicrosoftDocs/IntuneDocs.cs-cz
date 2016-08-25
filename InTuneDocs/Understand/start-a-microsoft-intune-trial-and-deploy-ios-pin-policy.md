---
title: "Spuštění zkušební verze Microsoft Intune a nasazení zásady PIN kódu pro iOS | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 06cb9a73-0f17-44b3-b334-86c98020316e
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 7f3985b10ac9612c8c1efc4756eb25cdcf29b023
ms.openlocfilehash: 6787d0c35621b2bc94bfe376dfd1669e9dfe46db


---

# Spuštění zkušební verze Microsoft Intune a nasazení zásady PIN kódu pro iOS
Tyto podrobné pokyny vám pomůžou nastavit zkušební verzi Intune a nakonfigurovat zásadu PIN kódu pro zařízení s iOS. Seznam dalších běžných úloh zkušebního používání Intune, které můžete vyzkoušet, najdete v tématu [Běžné úlohy hodnocení služby Microsoft Intune](common-microsoft-intune-evaluation-tasks.md).



## Kontrola požadavků pro tento scénář

-   Počítač s Windows s aplikací Internet Explorer k provádění úloh správy

-   Zařízení se systémem iOS 7.1 nebo novějším ke zkušebnímu ověření zásad uživatele

-   Telefon, abyste mohli provést ověření při zkušebním přihlášení

## Vytvoření bezplatného zkušebního účtu Intune
> [!NOTE]
> Pokud už máte předplatné Intune, tuto část přeskočte a přejděte k další části.

1.  Na počítači s Windows klikněte pravým tlačítkem myši na **Internet Explorer** (IE) a vyberte **Procházení se službou InPrivate**.

    ![Spuštění procházení InPrivate](../media/30-day-trial-walkthrus/30day-start-trial-1-InPrivate.png)

2.  Přejděte na stránku [Registrační portál Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1), zadejte požadované informace a klikněte na **Další**.

    ![Registrace pro účet](../media/30-day-trial-walkthrus/30day-start-trial-2-abt-you.png)

3.  Zadejte uživatelské ID a heslo účtu správce a klikněte na **Další**. Pomocí tohoto ID se budete přihlašovat k portálu Intune, abyste mohli provádět úlohy správy.

    ![Vytvoření ID](../media/30-day-trial-walkthrus/30day-start-trial-3-createID.png)

4.  Zadejte svoje číslo mobilního telefonu a kliknutím na **Poslat mi SMS** proveďte jeho ověření.

    ![Ověření vašich podrobností](../media/30-day-trial-walkthrus/30day-start-trial-4-textme.png)

5.  Uložte si informace uvedené na obrazovce a potom klikněte na **Teď se můžete pustit do práce…**

    ![Jste připraveni...](../media/30-day-trial-walkthrus/30day-start-trial-5-ReadyToGo.png)

## Vytvoření zkušebního uživatele

1.  Na počítači s Windows klikněte na tlačítko **Start** a přejdete na stránku správy uživatelů.

    ![Přechod na stránku správy uživatelů](../media/30-day-trial-walkthrus/30day-crt-user-6-click-start.png)

2.  Kliknutím na tlačítko **+** přidejte uživatele.

    ![Přidání uživatele](../media/30-day-trial-walkthrus/30day-crt-user-7-click-plus.png)

3.  Na stránce **Vytvořit nový uživatelský účet**:

    1.  Zadejte informace o zkušebním uživateli.

    2.  Vyberte možnost **Zadejte heslo**.

    3.  Zrušte zaškrtnutí políčka **Při příštím přihlášení musí tento uživatel heslo změnit**.

    4.  Klikněte na **Vytvořit**.

    ![Vytvoření nového uživatelského účtu](../media/30-day-trial-walkthrus/30day-crt-user-8-add-user-info.png)

4.  Na stránce pro potvrzení vytvoření uživatele klikněte na **Zavřít**.

    ![Stránka pro potvrzení vytvoření uživatele](../media/30-day-trial-walkthrus/30day-crt-user-9-close-confirm.png)

5.  Klikněte na **Aktualizovat**, aby se zobrazil uživatel, kterého jste vytvořili.

    ![Potvrzení účtu](../media/30-day-trial-walkthrus/30day-crt-user-10-refresh-user.png)

## Konfigurace zásady systému iOS pro PIN kód pro testovacího uživatele

1.  Na počítači s Windows nastavte Intune jako autoritu pro správu mobilních zařízení (MDM):

    1.  Přejděte na stránku [konzoly pro správu Intune](http://manage.microsoft.com/), přihlaste se pomocí účtu správce a klikněte na **Zahájení správy mobilních zařízení**. Otevře se stránka autority pro správu mobilních zařízení.

        ![Začínáme s konzolou Intune](../media/30-day-trial-walkthrus/30day-cfg-pol-11-start-mg-mobl-dev.png)

    2.  Klikněte na odkaz **Nastavit autoritu správy mobilních zařízení**.

        ![Nastavení autority pro správu mobilních zařízení](../media/30-day-trial-walkthrus/30day-cfg-pol-12-link-set-mdm.png)

2.  Povolte registraci zařízení s iOS. Tento proces vytvoří důvěryhodný certifikát mezi službou APNs (Apple Push Notification Service) a vaším předplatným Intune.

    1.  Klikněte na **Povolit platformu iOS a Mac OS X**.

        ![Povolení registrace se systémy iOS a Mac OS X](../media/30-day-trial-walkthrus/30day-cfg-pol-13-enbl-ios-plat.png)

    2.  Klikněte na **Stáhnout žádost certifikátu služby APNs**.

        ![Stažení certifikátu služby APN](../media/30-day-trial-walkthrus/30day-cfg-pol-14-dwnld-cert-reqst.png)

    3.  Zadejte název souboru a umístění žádosti o podepsání certifikátu a potom klikněte na **Uložit**. Tento soubor obsahuje veřejný klíč, který odpovídá soukromému klíči uchovávaném vaším předplatným Intune.

        ![Určení žádosti o podepsání certifikátu](../media/30-day-trial-walkthrus/30day-cfg-pol-15-cert-name-loc.png)

    4.  Klikněte na **Portál Apple Push Certificates Portal**. Otevře se nová karta.

        ![Přechod na stránku certifikátů služby APN](../media/30-day-trial-walkthrus/30day-cfg-pol-16-cert-portl-link.png)

    5.  Zadejte svoje Apple ID a heslo a klikněte na **Přihlásit**. Může se jednat o ID, které používáte na svém zařízení s iOS při získávání aplikací z iOS App Storu.

        ![Přihlášení k portálu Apple Push Certificates](../media/30-day-trial-walkthrus/30day-cfg-pol-17-id-passw-signin.png)

    6.  Klikněte na **Vytvořit certifikát**.

        ![Vytvoření certifikátu služby APN](../media/30-day-trial-walkthrus/30day-cfg-pol-18-create-cert.png)

    7.  Přečtěte si podmínky použití společnosti Apple, zaškrtněte příslušné políčko a klikněte na **Přijmout**.

        ![Přijetí podmínek použití](../media/30-day-trial-walkthrus/30day-cfg-pol-19-TOU.png)

    8.  Klikněte na **Procházet**.

        ![Přechod k uloženému certifikátu](../media/30-day-trial-walkthrus/30day-cfg-pol-20-browse.png)

    9. Vyberte soubor žádosti o podepsání certifikátu, který jste předtím uložili, a klikněte na **Otevřít**.

        ![Otevření certifikátu](../media/30-day-trial-walkthrus/30day-cfg-pol-21-CSRfile-open.png)

    10. Klikněte na tlačítko **Odeslat**.

        ![Odeslání certifikátu](../media/30-day-trial-walkthrus/30day-cfg-pol-22-upld-reqst.png)

    11. Po zobrazení výzvy ke stažení souboru JSON klikněte na **Uložit jako**.

        ![Uložení souboru JSON](../media/30-day-trial-walkthrus/30day-cfg-pol-23-json-saveas.png)

    12. Zadejte umístění souboru JSON a klikněte na **Uložit**.

        ![Určení místa k uložení souboru JSON](../media/30-day-trial-walkthrus/30day-cfg-pol-24-json-save-loc.png)

        Pokud se stránka po pár sekundách automaticky nepřesměruje, klikněte na **Storno**.

        ![Zrušení, pokud nedojde k přesměrování stránky](../media/30-day-trial-walkthrus/30day-cfg-pol-25-json-pg-cancel.png)

    13. Pokud chcete načíst nově vytvořený soubor certifikátu, klikněte na **Stáhnout**.

        ![Stažení certifikátu](../media/30-day-trial-walkthrus/30day-cfg-pol-26-dwnld-retrv-cert.png)

    14. Po zobrazení výzvy ke stažení souboru PEM klikněte na **Uložit jako**.

        ![Stažení souboru PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-27-pem-saveas.png)

    15. Zadejte umístění souboru PEM a klikněte na **Uložit**.

        ![Uložení souboru PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-28-pem-save-loc.png)

    16. Vraťte se na kartu konzoly pro správu Intune a klikněte na **Nahrát na server certifikát služby APN**.

        ![Nahrání certifikátu služby APN](../media/30-day-trial-walkthrus/30day-cfg-pol-29-upld-cert.png)

    17. Zadejte svoje Apple ID a klikněte na **Procházet**.

        ![Zadání Apple ID](../media/30-day-trial-walkthrus/30day-cfg-pol-30-app-id-browse.png)

    18. Vyberte soubor PEM, který jste právě uložili, a klikněte na **Otevřít**.

        ![Otevření souboru PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-31-sel-pem-open.png)

    19. Instalaci dokončíte kliknutím na **Nahrát**.

        ![Nahrání souboru PEM](../media/30-day-trial-walkthrus/30day-cfg-pol-32-pem-upload.png)

        Certifikát služby APNs je nakonfigurovaný.

        ![Konfigurace certifikátu služby APN je hotová](../media/30-day-trial-walkthrus/30day-cfg-pol-33-apns-confgd.png)

3.  Vytvořte zkušební skupinu uživatelů pro cílové zásady:

    1.  V levém podokně klikněte na **Skupiny**.

        ![Otevření skupin](../media/30-day-trial-walkthrus/30day-cfg-pol-34-clk-groups.png)

    2.  Úplně vpravo klikněte na **Vytvořit skupinu**.

        ![Vytvoření skupiny](../media/30-day-trial-walkthrus/30day-cfg-pol-35-crt-group.png)

    3.  Zadejte název skupiny, vyberte nadřazenou skupinu **Všichni uživatelé** a klikněte na **Další**.

        ![Výběr všech uživatelů jako nadřazené skupiny](../media/30-day-trial-walkthrus/30day-cfg-pol-36-name-group.png)

    4.  V poli **Začít členství ve skupině s** vyberte možnost **Všichni uživatelé v nadřazené skupině** a klikněte na **Dokončit**.

        ![Začít členství ve skupině s nadřazenou skupinou](../media/30-day-trial-walkthrus/30day-cfg-pol-37-all-users-group.png)

4.  Vytvořte zásadu PIN kódu PIN pro iOS a zaměřte ji na zkušební skupinu uživatelů:

    1.  V levém podokně klikněte na **Zásada**.

        ![Otevření pracovního prostoru zásady](../media/30-day-trial-walkthrus/30day-cfg-pol-38-clk-policy.png)

    2.  Úplně vpravo klikněte na **Přidat zásadu**.

        ![Přidání zásady](../media/30-day-trial-walkthrus/30day-cfg-pol-39-add-policy.png)

    3.  Rozbalte uzel iOS, vyberte řádek **Všeobecná konfigurace** a klikněte na **Vytvořit zásadu**.

        ![Vytvoření obecných zásad konfigurace pro iOS](../media/30-day-trial-walkthrus/30day-cfg-pol-40-gen_cfg_pol.png)

    4.  Zadejte název zásady, zapněte možnost **Vyžadovat heslo k odemknutí mobilních zařízení** a u položky **Minimální délka hesla** nastavte hodnotu **4**.

        ![Konfigurace nastavení pro hesla](../media/30-day-trial-walkthrus/30day-cfg-pol-41-name-policy.png)

    5.  Nasaďte zásadu kliknutím na **Ano**.

        ![Nasazení zásady](../media/30-day-trial-walkthrus/30day-cfg-pol-42-yes-deploy-pol.png)

    6.  Klikněte na skupinu uživatelů, kterou jste předtím vytvořili, klikněte na **Přidat** a potom klikněte na **OK**.

        ![Výběr skupiny pro zásadu](../media/30-day-trial-walkthrus/30day-cfg-pol-43-add-pol-to-grp.png)

        Teď máte zásadu PIN kódu pro iOS, která se zaměřuje na zkušební skupinu uživatelů.

        ![Nastavení zásady je dokončené](../media/30-day-trial-walkthrus/30day-cfg-pol-44-policy-applied.png)

## Kontrola vynucování zásady na zařízení s iOS

1.  Na iPadu spusťte iOS App Store, nainstalujte bezplatnou aplikaci **Portál společnosti Microsoft Intune** a otevřete ji.

    ![Instalace Portálu společnosti](../media/30-day-trial-walkthrus/30day-cfg-pol-45-cportal-installed.png)

2.  Zadejte název účtu zkušebního uživatele a heslo a klepněte na **Přihlásit**.

    ![Zadejte svoje přihlašovací údaje](../media/30-day-trial-walkthrus/30day-cfg-pol-46-cportal-signin.png)

3.  Klepnutím na **Zaregistrovat** spusťte registraci zařízení v Intune.

    ![Zahájení registrace](../media/30-day-trial-walkthrus/30day-cfg-pol-47-tap-enroll.jpg)

4.  Na obrazovce **Instalace profilu** klepněte na **Instalovat**.

    ![Instalace profilu](../media/30-day-trial-walkthrus/30day-cfg-pol-48-profile-install-1.jpg)

5.  V dialogovém okně **Instalace profilu** klepněte na **Instalovat**.

    ![Pokračování v instalaci profilu](../media/30-day-trial-walkthrus/30day-cfg-pol-49-profile-install-2.jpg)

6.  Na obrazovce **Upozornění** klepněte na **Instalovat**.

    ![Přijetí upozornění](../media/30-day-trial-walkthrus/30day-cfg-pol-50-warning-install-3.png)

7.  V dialogovém okně **Vzdálená správa** klepněte na **Důvěřovat**.

    ![Důvěřování vzdálené správě](../media/30-day-trial-walkthrus/30day-cfg-pol-51-remt-mgmt-trust.jpg)

8.  Po dokončení instalace profilu pro správu klepněte na **Hotovo**. Registrace je hotová.

    ![Registrace je hotová](../media/30-day-trial-walkthrus/30day-cfg-pol-52-profile-done.jpg)

9. Po dokončení registrace klepněte na **OK** a potom aplikaci Portál společnosti zavřete.

    ![Zavření aplikace Portál společnosti klepnutím na OK](../media/30-day-trial-walkthrus/30day-cfg-pol-53-devc-enrolled-ok.png)

10. Po zobrazení výzvy ke konfiguraci hesla klepněte na **Pokračovat**.

    ![Přijetí výzvy ke konfiguraci hesla](../media/30-day-trial-walkthrus/30day-cfg-pol-54-passcode-req-cont.png)

11. Zadejte svoje heslo, klepněte na **Pokračovat**, znovu zadejte heslo a klepněte na **Uložit**.

    ![Zadání hesla](../media/30-day-trial-walkthrus/30day-cfg-pol-55-passcode-enter.jpg)

12. Stisknutím tlačítka napájení zamkněte iPad a potom ho posunutím prstem odemkněte. Zjistíte, že k odemknutí zařízení teď musíte zadat heslo.

### Související témata
[Příručka pro testování Intune](get-started-with-a-30-day-trial-of-microsoft-intune.md)



<!--HONumber=Jun16_HO4-->


