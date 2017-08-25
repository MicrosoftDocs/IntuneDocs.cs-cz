---
title: "Instalace aplikací pro Windows a Windows Phone bokem"
description: "Tady je postup, jak zaregistrovat obchodní aplikace, aby je bylo možné nasadit pomocí Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: e44f1756-52e1-4ed5-bf7d-0e80363a8674
ms.custom: intune-classic
ms.openlocfilehash: 2a8754d684896f2c945e11ed0fc2577114459069
ms.sourcegitcommit: 4034ac474bfed358270a32459a2cf2fe02f44e45
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/15/2017
---
# <a name="sign-line-of-business-apps-so-they-can-be-deployed-to-windows-devices-with-intune"></a>Registrace obchodních aplikací, aby je bylo možné nasadit na zařízení s Windows pomocí Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Jako správce Intune můžete nasazovat obchodní aplikace (včetně aplikace Portál společnosti) na mobilní zařízení s Windows a Windows 10. Pokud chcete nasadit aplikace .appx nebo .xap do Windows 10 a na mobilní zařízení s Windows 10 nebo nasadit obchodní aplikaci do Windows 8.1 nebo na zařízení s Windows Phone 8.1, budete potřebovat **Certifikát podepisování mobilního kódu Symantec Enterprise**. Pro tyto aplikace v příslušných zařízeních s Windows je důvěryhodný jenom certifikát Symantec. Pro aplikace pro Windows 10 a tzv. univerzální aplikace můžete používat svou vlastní certifikační autoritu. Tento certifikát se vyžaduje, aby se dalo:

-   Zaregistrovat aplikaci Portál společnosti pro nasazení na počítače s Windows, mobilní zařízení s Windows 10 a zařízení Windows Phone

-   Zaregistrovat firemní obchodní aplikace, aby je služba Intune mohla nasadit na zařízení s Windows

Následující postup vám pomůže získat požadovaný certifikát a podepsat aplikace. Bude potřeba se zaregistrovat jako vývojář Microsoftu a následně si certifikát Symantec zakoupit.


1. **Registrace jako vývojář Microsoftu**<br>
   [Zaregistrujte se jako vývojář Microsoftu](http://go.microsoft.com/fwlink/?LinkId=268442) pomocí informací o firemním účtu, které jste použili při přihlašování k zakoupení firemního účtu. Certifikát pro podepisování kódu obdržíte až po schválení žádosti vedoucím pracovníkem společnosti.

2. **Získejte pro společnost certifikát Symantec**<br>
  Pomocí ID společnosti Symantec zakupte certifikát z [webu společnosti Symantec](http://go.microsoft.com/fwlink/?LinkId=268441) . Po zakoupení certifikátu obdrží schvalovatel, kterého jste uvedli při registraci jako vývojář Microsoftu, e-mail požadující schválení žádosti o certifikát. Další informace o požadavku na certifikát Symantec najdete v tématu [Proč Windows Phone vyžaduje certifikát Symantec?](https://technet.microsoft.com/library/dn764959.aspx#BKMK_Symantec) Nejčastější dotazy k registraci zařízení Windows

3.  **Import certifikátů**<br>
    Jakmile se žádost schválí, obdržíte e-mail s pokyny k importování certifikátů. Postupujte podle pokynů v e-mailu pro import certifikátů.

4.  **Ověření importovaných certifikátů**<br>
    Chcete-li ověřit, zda byly certifikáty správně naimportovány, přejděte k modulu snap-in **Certifikáty**, klikněte pravým tlačítkem na položku **Certifikáty** a vyberte možnost **Hledat certifikáty**. Do pole **Obsahuje** zadejte Symantec a klikněte na **Najít**. Importované certifikáty by se měly zobrazit ve výsledcích.

    ![Hledání certifikátu Symantec](./media/wit.gif)

5. **Export podpisového certifikátu**<br>
    Jakmile ověříte, že jsou certifikáty dostupné, můžete exportovat soubor .pfx a podepsat Portál společnosti. Vyberte certifikát Symantec se **zamýšleným účelem** „podepisování kódu”. Klikněte pravým tlačítkem na certifikát pro podpis kódu a vyberte **Exportovat**.

    ![Export podpisového certifikátu](./media/wit-walk-cert2.gif)

    V **Průvodci exportem certifikátu**vyberte **Ano, exportovat soukromý klíč** a klikněte na **Další**. Vyberte **Formát Personal Information Exchange – PKCS č. 12 (.PFX)** a zaškrtněte políčko **Zahrnout všechny certifikáty na cestě k certifikátu, pokud je to možné**. Dokončete průvodce. Další informace naleznete v tématu [Exportování certifikátu se soukromým klíčem](http://go.microsoft.com/fwlink/?LinkID=203031).

6.  **Nahrání aplikace do Intune**<br>
    Nahráním podepsaného souboru aplikace a svého certifikátu pro podpis kódu zpřístupníte aplikaci vašim koncovým uživatelům.

    1.  Na portálu Intune klikněte na **Správa** &gt; **Windows Phone**.

    2.  Klikněte na **Nahrát podepsaný soubor aplikace** a přihlaste se svým ID správce pro Intune.

    3.  Přidejte soubor certifikátu (.pfx), který jste exportovali do **certifikátu pro podpis kódu** a vytvořte pro tento certifikát heslo.

    4.  Dokončete průvodce.

## <a name="example-download-sign-and-deploy-the-company-portal-app-for-windows-devices"></a>Příklad: Stažení, podepsání a nasazení aplikace Portál společnosti pro zařízení s Windows

Aplikaci Portál společnosti můžete místo instalace z Microsoft Storu nasadit na zařízení s Windows, včetně zařízení Windows Phone a mobilních zařízení s Windows 10, pomocí Intune. Musíte si stáhnout aplikaci Portál společnosti a podepsat ji svým certifikátem.  To je nutné pouze v případě, že uživatelé nebudou používat Store společnosti a chcete nasadit firemní portál na zařízení Windows Phone 8.1.


1.  **Stáhněte Portál společnosti**

    Pokud chcete aplikaci Portál společnosti nasadit pomocí Intune, můžete si stáhnout [aplikaci Portál společnosti Microsoft Intune pro Windows Phone 8.1](http://go.microsoft.com/fwlink/?LinkId=615799) z webu služby Stažení softwaru a spustit samorozbalovací soubor (.exe). Tento soubor obsahuje dva soubory:

    -   CompanyPortal.appx – instalační aplikace Portálu společnosti pro Windows Phone 8.1

    -   WinPhoneCompanyPortal.ps1 – Powershellový skript, který můžete použít k podepsání aplikace Portál společnosti, aby se dala nasadit na zařízení s Windows Phone 8.1

    Alternativně si můžete stáhnout Portál společnosti pro Windows Phone 8.1 (offline licencovaný balíček) nebo Portál společnosti pro Windows 10 (offline licencovaný balíček) z [Microsoft Storu pro firmy](http://businessstore.microsoft.com/). Aplikaci Portál společnosti bude nutné si pořídit s offline licencí a příslušným balíčkem staženým pro offline použití. Platformy Windows 8 a Windows Phone 8 uvedené ve výběru odkazují na své ekvivalenty 8.1. Podrobnosti o tom, jak to provést v Intune, najdete v tématu [Správa aplikací zakoupených v Microsoft Storu pro firmy](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune).

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

6.  Nasazení aplikace Portál společnosti Windows Phone 8.1 (SSP.appx) Pokyny najdete v tématu [Přidání obchodních aplikací pro Windows Phone](lob-apps-windows-phone.md) ([klasická konzola](/intune-classic/deploy-use/deploy-apps-in-microsoft-intune)).

## <a name="how-to-renew-the-symantec-enterprise-code-signing-certificate"></a>Jak obnovit certifikát Symantec Enterprise pro podpis kódu

Certifikát Symantecu, který se používá k nasazení mobilních aplikací pro Windows a Windows Phone, je potřeba pravidelně obnovovat.

1.  Najděte e-mail s informacemi o obnovení, který vám Symantec poslal přibližně 14 dnů před vypršením platnosti certifikátu. V tomto e-mailu jsou pokyny od Symantecu o obnovení vašeho podnikového certifikátu.

    Další informace o certifikátech Symantec získáte na webu [www.symantec.com](http://www.symantec.com) nebo telefonním čísle 1-877-438-8776 nebo 1-650-426-3400.

2.  Přejděte na web (příklad: [https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do](https://products.websecurity.symantec.com/orders/enrollment/microsoftCert.do)) a přihlaste se s ID vydavatele od Symantecu a e-mailovou adresou spojenou s certifikátem. Ke spuštění obnovení musíte použít stejný počítač, který použijete ke stažení certifikátu.

3.  Po schválení a zaplacení obnovení si stáhněte certifikát.

### <a name="how-to-install-the-updated-certificate-for-line-of-business-lob-apps"></a>Jak nainstalovat aktualizovaný certifikát pro obchodní aplikace

1.  Zaregistrujte nejnovější verzi své obchodní aplikace.

2.  Otevřete konzolu Intune, přejděte na **Správce** &gt; **Správa mobilních zařízení** &gt; **Windows Phone** a klikněte na **Nahrát podepsanou aplikaci**.

3.  Nahrajte nově podepsaný firemní portál. Budete potřebovat nově podepsaný soubor SSP.xap a nový soubor .PFX, který jste dostali od Symantecu, nebo token pro zápis aplikace vytvořený pomocí tohoto nového souboru .PFX.

4.  Po dokončení nahrávání odeberte předchozí verzi aplikace Portál společnosti v pracovním prostoru **Software**  .

5.  Zaregistrujte všechny nové a aktualizované podnikové aplikace pomocí nového certifikátu. Stávající aplikace není nutné znovu podepisovat a nasazovat.

## <a name="manually-deploy-windows-10-company-portal-app"></a>Ruční nasazení aplikace Portál společnosti pro Windows 10
Aplikaci Portál společnosti pro Windows 10 můžete ručně nasadit přímo z Intune, i když službu Intune nemáte integrovanou s Microsoft Storem pro firmy.

 > [!NOTE]
 > Tato možnost vyžaduje, abyste ručně nasazovali aktualizace pokaždé, když je vydaná aktualizace aplikace.

1. Přihlaste se ke svému účtu v [Microsoft Storu pro firmy](https://www.microsoft.com/business-store) a získejte verzi aplikace Portál společnosti s **offline licencí** .  
2. Jakmile aplikaci získáte, vyberte ji na stránce **Inventář**.  
3. Vyberte **Windows 10 – všechna zařízení** jako **platformu**, potom vyberte příslušnou **architekturu** a stahujte. Pro tuto aplikaci není nutné mít soubor s licencí aplikace.
![Windows 10 – všechna zařízení a architektura x86 – obrázek s podrobnostmi balíčku ke stažení](./media/Win10CP-all-devices.png)
4. Stáhněte všechny balíčky v části Požadované platformy. To je nutné provést pro architektury x86, x64 a ARM – celkem 9 balíčků, jak je vidět na následujícím obrázku.

![Obrázek souborů závislostí ke stažení ](./media/Win10CP-dependent-files.png)
5. Než nahrajete aplikaci Portál společnosti do Intune, vytvořte složku (například C:&#92;Portál společnosti) s balíčky strukturovanými následovně:
  1. Umístěte balíček Portálu společnosti do složky C:\Portál společnosti. V tomto umístění vytvořte také podsložku Závislosti.  
  ![Obrázek složky Závislosti uložené se souborem APPXBUN](./media/Win10CP-Dependencies-save.png)
  2. Umístěte devět balíčků závislostí do složky Závislosti.  
  Pokud nebudou závislosti umístěné v tomto formátu, Intune je při nahrávání balíčku nerozpozná a nenahraje a nahrávání se nezdaří s následující chybou.  
  ![Závislost aplikace systému Windows pro tento instalační soubor softwaru nebyla nalezena ve složce aplikací. Můžete sice pokračovat, vytvořit a nasadit tuto aplikaci, nebude však možné ji spustit, dokud nebude poskytnuta chybějící závislost aplikace systému Windows.](./media/Win10CP-error-message.png)
6. Vraťte se do Intune a nahrajte aplikaci Portál společnosti jako novou aplikaci. Nasaďte ji jako požadovanou aplikaci pro vybranou skupinu cílových uživatelů.  

Další informace o tom, jak Intune nakládá se závislostmi pro univerzální aplikace, najdete v článku [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Nasazení souboru appxbundle se závislostmi prostřednictvím Microsoft Intune MDM).  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Jak mám aktualizovat Portál společnosti na zařízeních uživatelů, pokud si už nainstalovali starší aplikace ze Storu?
Pokud si uživatelé nainstalovali aplikace Portál společnosti pro Windows 8.1 nebo Windows Phone 8.1 ze Storu, měly by se tyto aplikace automaticky aktualizovat na novou verzi. Není tedy třeba provádět žádnou akci. Pokud k aktualizaci nedojde, požádejte uživatele, aby zkontrolovali, jestli mají na svých zařízeních povolené automatické aktualizace pro aplikace ze Storu.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak mám upgradovat aplikaci Portál společnosti pro Windows 8.1 nainstalovanou bokem na aplikaci Portál společnosti pro Windows 10?
Doporučujeme následující způsob migrace – odstraňte nasazení pro aplikaci Portál společnosti pro Windows 8.1 nastavením akce nasazení na možnost Odinstalovat. Až to provedete, můžete aplikaci Portál společnosti pro Windows 10 nasadit některým z výše uvedených způsobů.  

Pokud potřebujete aplikaci nainstalovat bokem a nasadili jste Portál společnosti pro Windows 8.1 bez podepisování certifikátem Symantec, postupujte podle pokynů ve výše uvedené části věnované přímému nasazení prostřednictvím Intune a proveďte upgrade.

Pokud potřebujete aplikaci nainstalovat bokem a Portál společnosti pro Windows 8.1 jste podepsali a nasadili prostřednictvím certifikátu Symantec pro podepisování kódu, postupujte podle pokynů v níže uvedené části.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak mám upgradovat podepsanou a bokem nainstalovanou aplikaci Portál společnosti pro Windows Phone 8.1 nebo aplikaci Portál společnosti pro Windows 8.1 na aplikaci Portál společnosti pro Windows 10?
Doporučujeme následující způsob migrace – odstraňte existující nasazení pro aplikaci Portál společnosti pro Windows Phone 8.1 nebo aplikaci Portál společnosti pro Windows 8.1 nastavením akce nasazení na možnost Odinstalovat. Až to provedete, můžete aplikaci Portál společnosti pro Windows 10 nasadit normálním způsobem.  

Jinak musí být aplikace Portál společnosti pro Windows 10 náležitě aktualizovaná a podepsaná, abyste dodrželi patřičný způsob upgradu.  

Pokud je aplikace Portál společnosti pro Windows 10 podepsaná a nasazená tímto způsobem, budete muset tento proces opakovat pro každou novou aktualizaci aplikace, až bude ve Storu k dispozici. Aplikace se při aktualizaci Storu automaticky neaktualizuje.  

Aplikaci můžete tímto způsobem podepsat a nasadit takto:

1. Stáhněte si podepisovací skript Microsoft Intune pro aplikaci Portál společnosti pro Windows 10 z webu [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript).  Tento skript vyžaduje, aby na hostitelském počítači byla nainstalovaná sada Windows SDK pro Windows 10. Sadu Windows SDK pro Windows 10 si můžete stáhnout z webu [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Stáhněte si aplikaci Portál společnosti pro Windows 10 z Microsoft Storu pro firmy (podrobnosti jsou uvedené výše).  
3. Spusťte skript se vstupními parametry popsanými v hlavičce skriptu, abyste podepsali aplikaci Portál společnosti pro Windows 10 (extrahovanou níže). Závislosti není nutné do skriptu předávat. Jsou vyžadované jenom v případě, když aplikaci nahráváte do konzoly pro správu Intune.

|Parametr | Popis|
| ------------- | ------------- |
|InputWin10AppxBundle |Cesta k umístění zdrojového souboru appxbundle |
|OutputWin10AppxBundle |Výstupní cesta pro podepsaný soubor appxbundle  Win81Appx Cesta k umístění souboru Portálu společnosti pro Windows 8.1 nebo Windows Phone 8.1 (.APPX)|
|PfxFilePath |Cesta k souboru certifikátu Symantec Enterprise Mobile Code Signing Certificate (.PFX) |
|PfxPassword| Heslo certifikátu Symantec Enterprise Mobile Code Signing Certificate |
|PublisherId |ID vydavatele dané organizace. Pokud chybí, použije se pole Subject certifikátu Symantec Enterprise Mobile Code Signing Certificate.|
|SdkPath | Cesta ke kořenové složce sady Windows SDK pro Windows 10. Tento argument je volitelný a jeho výchozí hodnota je ${env:ProgramFiles(x86)}\Windows Kits\10.|
Po ukončení běhu tohoto skriptu bude jeho výstupem podepsaná verze aplikace Portál společnosti pro Windows 10. Potom můžete podepsanou verzi aplikace nasadit jako obchodní aplikaci prostřednictvím Intune. Tím se aktuálně nasazené verze upgradují na tuto novou aplikaci.  
