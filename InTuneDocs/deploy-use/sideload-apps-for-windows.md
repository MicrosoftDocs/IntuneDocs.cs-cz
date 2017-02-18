---
title: "Instalace aplikací pro Windows a Windows Phone bokem | Dokumentace Microsoftu"
description: "Tady je postup, jak zaregistrovat obchodní aplikace, aby je bylo možné nasadit pomocí Intune."
keywords: 
author: robstackmsft
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: b6d5ea579b675d85d4404f289db83055642ffddd
ms.openlocfilehash: 2e8220f850e3b38a24aa4c48bcc3a59088251c24


---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Registrace obchodních aplikací, aby je bylo možné nasadit na zařízení s Windows pomocí Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Jako správce Intune můžete nasazovat obchodní aplikace (včetně aplikace Portál společnosti) na mobilní zařízení s Windows a Windows 10. Pokud chcete nasadit aplikace .appx nebo .xap do Windows 10 a na mobilní zařízení s Windows 10 nebo nasadit obchodní aplikaci do Windows 8.1 nebo na zařízení s Windows Phone 8.1, budete potřebovat **Certifikát podepisování mobilního kódu Symantec Enterprise**. Pro tyto aplikace v příslušných zařízeních s Windows je důvěryhodný jenom certifikát Symantec. Pro aplikace pro Windows 10 a tzv. univerzální aplikace můžete používat svou vlastní certifikační autoritu. Tento certifikát se vyžaduje, aby se dalo:

-   Zaregistrovat aplikaci Portál společnosti pro nasazení na počítače s Windows, mobilní zařízení s Windows 10 a zařízení Windows Phone

-   Zaregistrovat firemní obchodní aplikace, aby je služba Intune mohla nasadit na zařízení s Windows

Následující postup vám pomůže získat požadovaný certifikát a podepsat aplikace. Budete potřebovat účet Centrum vývojářů pro Windows Phone a pak budete muset zakoupit certifikát Symantec.


1. **Připojení k centru vývojářů pro Windows Phone**<br>
   Až se budete přihlašovat k zakoupení firemního účtu, připojte se k [Centru vývojářů pro Windows Phone](http://go.microsoft.com/fwlink/?LinkId=268442) pomocí informací o firemním účtu. Certifikát pro podepisování kódu obdržíte až po schválení žádosti vedoucím pracovníkem společnosti.

2. **Získejte pro společnost certifikát Symantec**<br>
  Pomocí ID společnosti Symantec zakupte certifikát z [webu společnosti Symantec](http://go.microsoft.com/fwlink/?LinkId=268441) . Po zakoupení certifikátu obdrží schvalovatel, kterého jste uvedli v účtu Windows Phone Dev Center, e-mail požadující schválení žádosti o certifikát. Další informace o požadavku na certifikát Symantec najdete v tématu [Proč Windows Phone vyžaduje certifikát Symantec?](https://technet.microsoft.com/en-us/library/dn764959.aspx#BKMK_Symantec) Nejčastější dotazy k registraci zařízení Windows

3.  **Import certifikátů**<br>
    Jakmile se žádost schválí, obdržíte e-mail s pokyny k importování certifikátů. Postupujte podle pokynů v e-mailu pro import certifikátů.

4.  **Ověření importovaných certifikátů**<br>
    Chcete-li ověřit, zda byly certifikáty správně naimportovány, přejděte k modulu snap-in **Certifikáty**, klikněte pravým tlačítkem na položku **Certifikáty** a vyberte možnost **Hledat certifikáty**. Do pole **Obsahuje** zadejte Symantec a klikněte na **Najít**. Importované certifikáty by se měly zobrazit ve výsledcích.

    ![Hledání certifikátu Symantec](./media/wit.gif)

5. **Export podpisového certifikátu**<br>
    Po ověření, že jsou certifikáty dostupné, můžete vyexportovat soubor .pfx a podepsat Portál společnosti. Vyberte certifikát Symantec se **zamýšleným účelem** „podepisování kódu”. Klikněte pravým tlačítkem na certifikát pro podpis kódu a vyberte **Exportovat**.

    ![Export podpisového certifikátu](./media/wit-walk-cert2.gif)

    V **Průvodci exportem certifikátu**vyberte **Ano, exportovat soukromý klíč** a klikněte na **Další**. Vyberte **Formát Personal Information Exchange – PKCS č. 12 (.PFX)** a zaškrtněte políčko **Zahrnout všechny certifikáty na cestě k certifikátu, pokud je to možné**. Dokončete průvodce. Další informace naleznete v tématu [Exportování certifikátu se soukromým klíčem](http://go.microsoft.com/fwlink/?LinkID=203031).

6.  **Nahrání aplikace do Intune**<br>
    Nahráním podepsaného souboru aplikace a svého certifikátu pro podpis kódu zpřístupníte aplikaci vašim koncovým uživatelům.

    1.  V [konzole pro správu Intune](http://manage.microsoft.com) klikněte na **Správa** &gt; **Windows Phone**.

    2.  Klikněte na **Nahrát podepsaný soubor aplikace** a přihlaste se svým ID správce pro Intune.

    3.  Přidejte soubor certifikátu (.pfx), který jste exportovali do **certifikátu pro podpis kódu** a vytvořte pro tento certifikát heslo.

    4.  Dokončete průvodce.

## <a name="example-download-sign-and-deploy-the-company-portal-app-for-windows-devices"></a>Příklad: Stažení, podepsání a nasazení aplikace Portál společnosti pro zařízení s Windows

Aplikaci Portál společnosti můžete nasadit na zařízení s Windows, včetně zařízení Windows Phone a mobilní zařízení s Windows 10, pomocí služby Intune místo instalace z Windows Storu. Musíte si stáhnout aplikaci Portál společnosti a podepsat ji svým certifikátem.  To je nutné pouze v případě, že uživatelé nebudou používat Store společnosti a chcete nasadit firemní portál na zařízení Windows Phone 8.1.


1.  **Stáhněte Portál společnosti**

    Pokud chcete aplikaci Portál společnosti nasadit pomocí Intune, můžete si stáhnout [aplikaci Portál společnosti Microsoft Intune pro Windows Phone 8.1](http://go.microsoft.com/fwlink/?LinkId=615799) z webu služby Stažení softwaru a spustit samorozbalovací soubor (.exe). Tento soubor obsahuje dva soubory:

    -   CompanyPortal.appx – instalační aplikace Portálu společnosti pro Windows Phone 8.1

    -   WinPhoneCompanyPortal.ps1 – Powershellový skript, který můžete použít k podepsání aplikace Portál společnosti, aby se dala nasadit na zařízení s Windows Phone 8.1

    Alternativně si můžete stáhnout Portál společnosti pro Windows Phone 8.1 (offline licencovaný balíček) nebo Portál společnosti pro Windows 10 (offline licencovaný balíček) z [Windows Storu pro firmy](http://businessstore.microsoft.com/). Aplikaci Portál společnosti bude nutné si pořídit s offline licencí a příslušným balíčkem staženým pro offline použití. Platformy Windows 8 a Windows Phone 8 uvedené ve výběru odkazují na své ekvivalenty 8.1. Podrobnosti o tom, jak to provést v Intune, najdete v tématu [Správa aplikací zakoupených ve Windows Store pro firmy](manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune.md).

2.  **Stažení sady Windows Phone SDK** Stáhněte si sadu Windows Phone SDK 8.0 (http://go.microsoft.com/fwlink/?LinkId=615570) a nainstalujte si ji do počítače. Potřebujete ji k vygenerování tokenu pro registraci aplikace.

3.  **Generování souboru AETX** Pomocí programu AETGenerator.exe, který je součástí sady Windows Phone SDK 8.0, vygenerujte soubor tokenu pro registraci aplikace (.aetx) ze souboru Symantec PFX. Pokyny, jak vytvořit soubor AETX, najdete v tématu [Jak vygenerovat token pro registraci aplikace pro Windows Phone](https://msdn.microsoft.com/library/windows/apps/jj735576.aspx).

4.  **Stažení sady Windows SDK pro Windows 8.1** Stáhněte a nainstalujte sadu [Windows Phone SDK](http://go.microsoft.com/fwlink/?LinkId=613525) (http://go.microsoft.com/fwlink/?LinkId=613525). Všimněte si, že powershellový skript dodaný spolu s aplikací Portál společnosti používá výchozí umístění instalace `${env:ProgramFiles(x86)}\Windows Kits\8.1`. Pokud máte instalaci jinde, musíte její umístění zahrnout jako parametr rutiny.

5.  **Opatření aplikace podpisem kódu pomocí prostředí PowerShell** Jako správce otevřete na hostitelském počítači, na kterém je nainstalovaná sada Windows SDK a certifikát Symantec Enterprise Mobile Code Signing Certificate, prostředí **Windows PowerShell**, přejděte na soubor Sign-WinPhoneCompanyPortal.ps1 a spusťte skript.

    **Příklad 1**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -AetxPath 'C:\signing\cert.aetx'
    ```
    Tento příklad podepíše CompanyPortal.appx ve složce C:\temp\ a vytvoří soubor CompanyPortalEnterpriseSigned.appx. Použije heslo PFX 1234 a přečte ID vydavatele ze souboru PFX. Kromě toho přečte i ID organizace ze souboru cert.aetx.

    **Příklad 2**

    ```
    .\Sign-WinPhoneCompanyPortal.ps1 -InputAppx 'C:\temp\CompanyPortal.appx' -OutputAppx 'C:\temp\CompanyPortalEnterpriseSigned.appx' -PfxFilePath 'C:\signing\cert.pfx' -PfxPassword '1234' -PublisherId 'OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1' -EnterpriseId 1000000001
    ```
    Tento příklad podepíše CompanyPortal.appx ve složce C:\temp\ a vytvoří soubor CompanyPortalEnterpriseSigned.appx. Použije heslo PFX 1234 a zadané ID vydavatele.

    **Parametry:**

    -   `-InputAppx` – Místní cesta k souboru CompanyPortal.appx v jednoduchých uvozovkách Například 'C:\temp\CompanyPortal.appx'.

    -   `-OutputAppx` – Místní cesta a název souboru podepsané aplikace Portál společnosti v jednoduchých uvozovkách Například 'C:\temp\CompanyPortalEnterpriseSigned.appx'.

    -   `-PfxFilePath` – Místní cesta a název souboru pro exportovaný soubor PFX certifikátu Symantec. Například 'C:\signing\cert.pfx'.

    -   `-PfxPassword` – Heslo použité k podepsání souboru PFX v jednoduchých uvozovkách. Například '1234'.

    -   `-AetxPath` – Místní cesta k souboru .aetx, který se používá k přečtení ID organizace, pokud se nedefinuje argument EnterpriseId. Zadat se musí buď tento argument, nebo EnterpriseId. Například 'C:\signing\cert.aetx'.

    -   `-PublisherId` – ID vydavatele dané organizace Pokud chybí, použije se pole Subject certifikátu Symantec Enterprise Mobile Code Signing Certificate. Například OID.0.9.2342.19200300.100.1.1=1000000001, CN="Test, Inc.", OU=Test 1

    -   `-SdkPath` – Cesta ke kořenové složce sady Windows SDK pro Windows 8.1 Tento argument je volitelný a jeho výchozí hodnota je ${env:ProgramFiles(x86)}\Windows Kits\8.1.

    -   `-EnterpriseId` – ID organizace Musí se zadat buď tento argument, nebo AetxPath. Pokud se tento argument nezadá, ID organizace se přečte ze souboru AETX. Například 1000000001.

6.  Nasazení aplikace Portál společnosti Windows Phone 8.1 (SSP.appx) Pokyny najdete v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps-in-microsoft-intune.md).

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>Jak obnovit certifikát Symantec Enterprise pro podpis kódu

Certifikát Symantecu, který se používá k nasazení mobilních aplikací pro Windows a Windows Phone, je potřeba pravidelně obnovovat.

1.  Najděte e-mail s informacemi o obnovení, který vám Symantec poslal přibližně 14 dnů před vypršením platnosti certifikátu. V tomto e-mailu jsou pokyny od Symantecu o obnovení vašeho podnikového certifikátu.

    Další informace o certifikátech Symantec získáte na webu [www.symantec.com](http://www.symantec.com) nebo telefonním čísle 1-877-438-8776 nebo 1-650-426-3400.

2.  Přejděte na web (příklad: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) a přihlaste se s ID vydavatele od Symantecu a e-mailovou adresou spojenou s certifikátem. Ke spuštění obnovení musíte použít stejný počítač, který použijete ke stažení certifikátu.

3.  Po schválení a zaplacení obnovení si stáhněte certifikát.

### <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>Jak nainstalovat aktualizovaný certifikát pro obchodní aplikace

1.  Zaregistrujte nejnovější verzi své obchodní aplikace.

2.  Otevřete konzolu pro správu Intune ([https://admin.manage.microsoft.com](https://admin.manage.microsoft.com)), přejděte na **Správce**, &gt;Správa mobilních zařízení** ** &gt; **Windows Phone** a klikněte na **Nahrát podepsanou aplikaci**.

3.  Nahrajte nově podepsaný firemní portál. Budete potřebovat nově podepsaný soubor SSP.xap a nový soubor .PFX, který jste dostali od Symantecu, nebo token pro zápis aplikace vytvořený pomocí tohoto nového souboru .PFX.

4.  Po dokončení nahrávání odeberte předchozí verzi aplikace Portál společnosti v pracovním prostoru **Software**  .

5.  Zaregistrujte všechny nové a aktualizované podnikové aplikace pomocí nového certifikátu. Stávající aplikace není nutné znovu podepisovat a nasazovat.



<!--HONumber=Dec16_HO2-->


