---
title: "Přidání aplikací pro Windows Store do Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si, jak přidat aplikace z Windows Storu do Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 812bdf5bde724798289668937ed2502438c524e0
ms.sourcegitcommit: 1c71fff769ca0097faf46fc2b58b953ff28386e8
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2017
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Přidání aplikací pro Windows Store do Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Spravovat aplikace**.
4. V úloze **Mobilní aplikace** zvolte **Spravovat** > **Aplikace**.
5. Nad seznamem aplikací zvolte **Přidat**.
6. V okně **Přidat aplikaci** zvolte **Informace o aplikaci**.
7. V okně **Upravit aplikaci** nakonfigurujte následující údaje. Až skončíte, klikněte na **Přidat**. V závislosti na zvolené aplikaci mohou být některé hodnoty v tomto okně vyplněny automaticky:
    - **Název aplikace** – zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis aplikace** – zadejte popis aplikace. Zobrazí se uživatelům na portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele aplikace.
    - **Adresa URL obchodu s aplikacemi** – zadejte adresu URL obchodu s aplikacemi pro aplikaci, kterou chcete vytvořit.
    - **Minimální operační systém** – v seznamu zvolte minimální verzi operačního systému, na kterou lze aplikaci nainstalovat. Pokud aplikaci přiřadíte k zařízení se starším operačním systémem, nenainstaluje se.
    - **Kategorie (volitelné)** – vyberte jednu nebo několik předdefinovaných nebo vytvořených kategorií. Uživatelé ji budou moct při procházení portálu snáz najít.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací** – volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů** – volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář** – volitelně zadejte jméno vývojáře aplikace.
    - **Vlastník** – volitelně zadejte vlastníka aplikace, například **Personální oddělení**.
    - **Poznámky** – zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
    - **Nahrát ikonu** – nahrajte ikonu, která bude spojená s aplikací. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
8. Až skončíte, zvolte v okně **Přidat aplikaci** možnost **Uložit**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřadit ke zvoleným skupinám. Nápovědu najdete v článku [Přiřazení aplikací do skupin](apps-deploy.md).

## <a name="manually-assign-windows-10-company-portal-app"></a>Ruční přiřazení aplikace Portál společnosti pro Windows 10
Koncoví uživatelé můžou aplikaci Portál společnosti ke správě zařízení a instalaci aplikací nainstalovat z Microsoft Storu. Pokud ale potřeby vaší firmy vyžadují přiřazení aplikace Portál společnosti, můžete aplikaci Portál společnosti pro Windows 10 ručně přiřadit přímo z Intune, i když službu Intune nemáte integrovanou s Microsoft Storem pro firmy.

 > [!NOTE]
 > Tato možnost vyžaduje ruční přiřazení aktualizace pokaždé, když se vydá aktualizace aplikace.

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
  ![Závislost aplikace systému Windows pro tento instalační soubor softwaru nebyla nalezena ve složce aplikací. Můžete pokračovat ve vytvoření a přiřazení této aplikace, nespustíte ji ale, dokud nebude poskytnuta chybějící závislost aplikace pro Windows.](./media/Win10CP-error-message.png)
6. Vraťte se do Intune a nahrajte aplikaci Portál společnosti jako novou aplikaci. Přiřaďte ji jako povinnou aplikaci k požadované sadě cílových uživatelů.  

Další informace o tom, jak Intune nakládá se závislostmi pro univerzální aplikace, najdete v článku [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Nasazení souboru appxbundle se závislostmi prostřednictvím Microsoft Intune MDM).  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Jak mám aktualizovat Portál společnosti na zařízeních uživatelů, pokud si už nainstalovali starší aplikace ze Storu?
Pokud si uživatelé nainstalovali aplikace Portál společnosti pro Windows 8.1 nebo Windows Phone 8.1 ze Storu, měly by se tyto aplikace automaticky aktualizovat na novou verzi. Není tedy třeba provádět žádnou akci. Pokud k aktualizaci nedojde, požádejte uživatele, aby zkontrolovali, jestli mají na svých zařízeních povolené automatické aktualizace pro aplikace ze Storu.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak mám upgradovat aplikaci Portál společnosti pro Windows 8.1 nainstalovanou bokem na aplikaci Portál společnosti pro Windows 10?
Doporučujeme následující způsob migrace – odstraňte přiřazení aplikace Portál společnosti pro Windows 8.1 nastavením akce přiřazení na možnost Odinstalovat. Až to uděláte, můžete aplikaci Portál společnosti pro Windows 10 přiřadit některou z předchozích možností.  

Pokud potřebujete aplikaci nainstalovat bokem a Portál společnosti pro Windows 8.1 jste přiřadili bez podepsání certifikátem Symantec, dokončete upgrade podle pokynů ve výše uvedené části věnované přímému přiřazení prostřednictvím Intune.

Pokud potřebujete aplikaci nainstalovat bokem a Portál společnosti pro Windows 8.1 jste podepsali a přiřadili prostřednictvím certifikátu Symantec pro podepisování kódu, postupujte podle pokynů v níže uvedené části.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak mám upgradovat podepsanou a bokem nainstalovanou aplikaci Portál společnosti pro Windows Phone 8.1 nebo aplikaci Portál společnosti pro Windows 8.1 na aplikaci Portál společnosti pro Windows 10?
Doporučujeme následující způsob migrace – odstraňte existující přiřazení aplikace Portál společnosti pro Windows Phone 8.1 nebo aplikace Portál společnosti pro Windows 8.1 nastavením akce přiřazení na možnost Odinstalovat. Až to uděláte, můžete aplikaci Portál společnosti pro Windows 10 přiřadit normálním způsobem.  

Jinak musí být aplikace Portál společnosti pro Windows 10 náležitě aktualizovaná a podepsaná, abyste dodrželi patřičný způsob upgradu.  

Pokud je aplikace Portál společnosti pro Windows 10 podepsaná a přiřazená tímto způsobem, budete muset tento proces opakovat pro každou novou aktualizaci aplikace, až bude ve Storu k dispozici. Aplikace se při aktualizaci Storu automaticky neaktualizuje.  

Aplikaci můžete tímto způsobem podepsat a přiřadit takto:

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
Po ukončení běhu tohoto skriptu bude jeho výstupem podepsaná verze aplikace Portál společnosti pro Windows 10. Potom můžete podepsanou verzi aplikace přiřadit jako obchodní aplikaci přes Intune. Tím se aktuálně přiřazené verze upgradují na tuto novou aplikaci.  
