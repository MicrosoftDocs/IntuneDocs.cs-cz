---
title: Ruční přidání aplikace Portál společnosti pro Windows 10
titleSuffix: Microsoft Intune
description: Přečtěte si, jak ručně přidat aplikaci Portál společnosti pro Windows 10.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 09/14/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 7808d9c189f429e15cdf916d18412ba951c7e696
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52190264"
---
# <a name="manually-add-the-windows-10-company-portal-app-by-using-microsoft-intune"></a>Ruční přidání aplikace Portál společnosti pro Windows 10 pomocí Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Vaši uživatelé si mohou nainstalovat aplikaci Portál společnosti sami z Microsoft Storu, aby mohli spravovat zařízení a instalovat aplikace. Pokud potřeby vaší firmy vyžadují, abyste jim aplikaci Portál společnosti přiřadili vy, můžete aplikaci Portál společnosti pro Windows 10 také přiřadit ručně přímo z Intune. Můžete to udělat, i když nemáte službu Intune integrovanou s Microsoft Storem pro firmy.

 > [!NOTE]
 > Možnost popsaná v tomto článku vyžaduje, abyste přiřadili ruční aktualizace vždy, když je vydána aktualizace aplikace.

## <a name="configure-settings-to-show-offline-apps"></a>Konfigurace nastavení k zobrazení offline aplikací
1. Přihlaste se k [Microsoft Storu pro firmy](https://www.microsoft.com/business-store) pomocí svého účtu správce.
2. Vyberte kartu **Spravovat** v horní části okna.
3. V levém podokně vyberte **Nastavení**.
4. V části **Prostředí nakupování** nastavte **Zobrazovat offline aplikace** na **Zapnuto**.  
    Zobrazí se aplikace licencované offline.

## <a name="download-the-offline-company-portal-app"></a>Stažení offline aplikace Portál společnosti
1. Vyhledejte a vyberte aplikaci **Portál společnosti**.
2. Nastavte **Typ licence** na **Offline**.
3. Výběrem možnosti **Získat aplikaci** offline aplikaci Portál společnosti získejte a přidejte do svého inventáře.
4. Na stránce aplikace **Portál společnosti** vyberte **Spravovat**.
5. Jako **Platformu** vyberte **Windows 10 – všechna zařízení**, potom vyberte příslušné hodnoty **Minimální verze**, **Architektury** a **Stáhnout metadata aplikace**. 
6. Výběrem možnosti **Stáhnout** uložte soubor na místní počítač.

    ![Podrobnosti balíčku Windows 10 – všechna zařízení a Architektura x86 vybraného ke stažení](./media/Win10CP-all-devices.png)

7. Vyberte **Stáhnout** a stáhněte všechny balíčky v části Požadované platformy.  
    Tuto akci je nutné provést pro architektury x86, x64 a ARM – celkem 12 balíčků.
8. Než nahrajete aplikaci Portál společnosti do Intune, vytvořte složku (například C:\Portál společnosti) s takto strukturovanými balíčky:
   - Umístěte balíček Portálu společnosti do složky C:\Portál společnosti. V tomto umístění vytvořte také podsložku *Závislosti*.  

     ![Složka Závislosti uložená se souborem APPXBUN](./media/Win10CP-Dependencies-save.png)

   - Umístěte balíčky závislostí do složky *Závislosti*. 

     > [!NOTE]
     > Pokud nebudou závislosti umístěné ve správném formátu, Intune je při nahrávání balíčku nerozpozná a nenahraje soubory. Nahrávání se nezdaří a zobrazí se chyba.

9. V Microsoft Intune na portálu Azure Portal nahrajte aplikaci Portál společnosti jako novou aplikaci. 
10. Přiřaďte aplikaci Portál společnosti vybrané skupině cílových uživatelů jako požadovanou aplikaci.  

Další informace o tom, jak Intune nakládá se závislostmi pro univerzální aplikace, najdete v článku [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Nasazení souboru appxbundle se závislostmi prostřednictvím Microsoft Intune MDM).  

## <a name="frequently-asked-questions"></a>Nejčastější dotazy 
### <a name="how-do-i-update-the-company-portal-app-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Jak mám aktualizovat aplikaci Portál společnosti na zařízeních uživatelů, pokud si už nainstalovali starší aplikace ze Storu?
Pokud si uživatelé nainstalovali aplikace Portál společnosti pro Windows 8.1 nebo Windows Phone 8.1 z Microsoft Storu, měly by se tyto aplikace automaticky aktualizovat na nejnovější verzi. Není tedy třeba provádět žádnou akci. Pokud k aktualizaci nedojde, požádejte uživatele, aby zkontrolovali, jestli mají na svých zařízeních povolené automatické aktualizace pro aplikace ze Storu.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak mám upgradovat aplikaci Portál společnosti pro Windows 8.1 nainstalovanou bokem na aplikaci Portál společnosti pro Windows 10?
Doporučujeme následující způsob migrace – odstraňte přiřazení aplikace Portál společnosti pro Windows 8.1 nastavením akce přiřazení na možnost **Odinstalovat**. Po výběru tohoto nastavení můžete přiřadit aplikaci Portál společnosti pro Windows 10 prostřednictvím některé ze zmíněných možností.  

Pokud potřebujete aplikaci nainstalovat bokem a Portál společnosti pro Windows 8.1 jste přiřadili bez podepsání certifikátem Symantec, dokončete upgrade podle pokynů v předchozích částech tohoto článku.

Pokud potřebujete aplikaci nainstalovat bokem a aplikaci Portál společnosti pro Windows 8.1 jste podepsali a přiřadili prostřednictvím certifikátu Symantec pro podepisování kódu, postupujte podle pokynů v následující části.

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak mám upgradovat podepsanou a bokem nainstalovanou aplikaci Portál společnosti pro Windows Phone 8.1 nebo aplikaci Portál společnosti pro Windows 8.1 na aplikaci Portál společnosti pro Windows 10?
Doporučujeme následující způsob migrace – odstraňte existující přiřazení aplikace Portál společnosti pro Windows Phone 8.1 nebo aplikace Portál společnosti pro Windows 8.1 nastavením akce přiřazení na možnost **Odinstalovat**. Po výběru tohoto nastavení můžete aplikaci Portál společnosti pro Windows 10 přiřadit běžným způsobem.  

Jinak musí být aplikace Portál společnosti pro Windows 10 náležitě aktualizovaná a podepsaná, abyste dodrželi patřičný způsob upgradu.  

Pokud aplikaci Portál společnosti pro Windows 10 podepíšete a přiřadíte tímto způsobem, budete muset tento proces opakovat pro každou novou aktualizaci aplikace, až bude ve Storu k dispozici. Aplikace se při aktualizaci Storu automaticky neaktualizuje.  

Aplikaci můžete tímto způsobem podepsat a přiřadit takto:

1. Stáhněte si [podepisovací skript Microsoft Intune pro aplikaci Portál společnosti pro Windows 10](https://aka.ms/win10cpscript).  
    Tento skript vyžaduje, aby na hostitelském počítači byla nainstalovaná sada Windows SDK pro Windows 10. [Stáhněte si sadu Windows SDK pro Windows 10](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Stáhněte si aplikaci Portál společnosti pro Windows 10 z Microsoft Storu pro firmy, jak je popsáno v předchozích částech.  
3. Pokud chcete podepsat aplikaci Portál společnosti pro Windows 10, spusťte skript se vstupními parametry popsanými v hlavičce skriptu, jak je uvedeno v následující tabulce.  
    Závislosti není nutné do skriptu předávat. Jsou vyžadované jenom v případě, že aplikaci nahráváte do konzoly pro správu Intune.

| Parametr |  Popis  |
|---|---|
| InputWin10AppxBundle  |  Cesta ke zdrojovému souboru appxbundle |
| OutputWin10AppxBundle | Výstupní cesta pro podepsaný soubor appxbundle 
| Win81Appx  | Cesta k souboru Portálu společnosti pro Windows 8.1 nebo Windows Phone 8.1 (.APPX) |
| PfxFilePath  |  Cesta k souboru certifikátu Symantec Enterprise Mobile Code Signing Certificate (.PFX)  |
| PfxPassword  | Heslo certifikátu Symantec Enterprise Mobile Code Signing Certificate |
| PublisherId | ID vydavatele dané organizace. Pokud chybí, použije se pole Subject certifikátu Symantec Enterprise Mobile Code Signing Certificate. |
| SdkPath | Cesta ke kořenové složce sady Windows SDK pro Windows 10. Tento argument je volitelný a jeho výchozí hodnota je ${env:ProgramFiles(x86)}\Windows Kits\10.  |

Po dokončení běhu tohoto skriptu bude jeho výstupem podepsaná verze aplikace Portál společnosti pro Windows 10. Potom můžete podepsanou verzi aplikace přiřadit jako obchodní aplikaci přes Intune. Tím se aktuálně přiřazené verze upgradují na tuto novou aplikaci.  

## <a name="next-steps"></a>Další postup

- [Přiřazení aplikací skupinám](apps-deploy.md)

