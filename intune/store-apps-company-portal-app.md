---
title: Ruční přidání aplikace Portál společnosti pro Windows 10
titleSuffix: Microsoft Intune
description: Přečtěte si, jak ručně přidat aplikaci Portál společnosti pro Windows 10.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bfe1a2d3-f611-4dbb-adef-c0dff4d7b810
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f2c7e449e9931bccd5e736bd09c33e0b42c623e9
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="manually-add-the-windows-10-company-portal-app-using-microsoft-intune"></a>Ruční přidání aplikace Portál společnosti pro Windows 10 pomocí Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Koncoví uživatelé můžou aplikaci Portál společnosti ke správě zařízení a instalaci aplikací nainstalovat z Microsoft Storu. Pokud ale potřeby vaší firmy vyžadují přiřazení aplikace Portál společnosti, můžete aplikaci Portál společnosti pro Windows 10 ručně přiřadit přímo z Intune, i když službu Intune nemáte integrovanou s Microsoft Storem pro firmy.

 > [!NOTE]
 > Tato možnost vyžaduje ruční přiřazení aktualizace pokaždé, když se vydá aktualizace aplikace.

## <a name="configure-settings-to-show-offline-apps"></a>Konfigurace nastavení k zobrazení offline aplikací
1. Přejděte na [Microsoft Store pro firmy](https://www.microsoft.com/business-store) a zkontrolujte, jestli jste přihlášení pomocí účtu správce.
2. Vyberte kartu **Spravovat** v horní části okna.
3. Vyberte **Nastavení** v levém navigačním sloupci.
4. Nastavte **Zobrazovat offline aplikace** v části **Prostředí nakupování** na **Zapnuto**. Tím se v Microsoft Store pro firmy zobrazí aplikace licencované offline.

## <a name="download-the-offline-company-portal-app"></a>Stažení offline aplikace Portál společnosti
1. Vyhledejte a vyberte aplikaci **Portál společnosti**.
2. Nastavte **Typ licence** na **Offline**.
3. Kliknutím na **Získat aplikaci** offline aplikaci Portál společnosti získejte a přidejte do svého inventáře.
4. Klikněte na **Spravovat** na stránce aplikace **Portál společnosti**.
5. Jako **Platformu** vyberte **Windows 10 – všechna zařízení**, pak vyberte příslušné hodnoty **Minimální verze**, **Architektury** a Stáhnout metadata aplikace**. 
6. Kliknutím na **Stáhnout** uložte soubor do místního počítače.

    ![Obrázek znázorňující podrobnosti balíčku Windows 10 – všechna zařízení a Architektura x86 ke stažení](./media/Win10CP-all-devices.png)

7. Stáhněte všechny balíčky v části Požadované platformy. To je nutné provést pro architektury x86, x64 a ARM – celkem 12 balíčků.
8. Než nahrajete aplikaci Portál společnosti do Intune, vytvořte složku (například C:&#92;Portál společnosti) s takto strukturovanými balíčky:
   - Umístěte balíček Portálu společnosti do složky C:\Portál společnosti. V tomto umístění vytvořte také podsložku Závislosti.  

     ![Obrázek složky Závislosti uložené se souborem APPXBUN](./media/Win10CP-Dependencies-save.png)

   - Umístěte balíčky závislostí do složky *Závislosti*. 

     > [!NOTE]
     > Pokud nebudou závislosti umístěné ve správném formátu, Intune je při nahrávání balíčku nerozpozná a nenahraje soubory. Nahrávání se nezdaří a zobrazí se chyba.

9. Vraťte se do Microsoft Intune na portálu Azure Portal.
10. Nahrajte aplikaci Portál společnosti jako novou aplikaci. Přiřaďte ji jako povinnou aplikaci k požadované sadě cílových uživatelů.  

Další informace o tom, jak Intune nakládá se závislostmi pro univerzální aplikace, najdete v článku [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Nasazení souboru appxbundle se závislostmi prostřednictvím Microsoft Intune MDM).  

## <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Jak mám aktualizovat Portál společnosti na zařízeních uživatelů, pokud si už nainstalovali starší aplikace ze Storu?
Pokud si uživatelé nainstalovali aplikace Portál společnosti pro Windows 8.1 nebo Windows Phone 8.1 ze Storu, měly by se tyto aplikace automaticky aktualizovat na novou verzi. Není tedy třeba provádět žádnou akci. Pokud k aktualizaci nedojde, požádejte uživatele, aby zkontrolovali, jestli mají na svých zařízeních povolené automatické aktualizace pro aplikace ze Storu.   

## <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak mám upgradovat aplikaci Portál společnosti pro Windows 8.1 nainstalovanou bokem na aplikaci Portál společnosti pro Windows 10?
Doporučujeme následující způsob migrace – odstraňte přiřazení aplikace Portál společnosti pro Windows 8.1 nastavením akce přiřazení na možnost „Odinstalovat“. Až to nastavíte, můžete aplikaci Portál společnosti pro Windows 10 přiřadit některou z předchozích možností.  

Pokud potřebujete aplikaci nainstalovat bokem a Portál společnosti pro Windows 8.1 jste přiřadili bez podepsání certifikátem Symantec, dokončete upgrade podle pokynů ve výše uvedené části věnované přímému přiřazení prostřednictvím Intune.

Pokud potřebujete aplikaci nainstalovat bokem a Portál společnosti pro Windows 8.1 jste podepsali a přiřadili prostřednictvím certifikátu Symantec pro podepisování kódu, postupujte podle pokynů v níže uvedené části.  

## <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Jak mám upgradovat podepsanou a bokem nainstalovanou aplikaci Portál společnosti pro Windows Phone 8.1 nebo aplikaci Portál společnosti pro Windows 8.1 na aplikaci Portál společnosti pro Windows 10?
Doporučujeme následující způsob migrace – odstraňte existující přiřazení aplikace Portál společnosti pro Windows Phone 8.1 nebo aplikace Portál společnosti pro Windows 8.1 nastavením akce přiřazení na možnost Odinstalovat. Až to nastavíte, můžete aplikaci Portál společnosti pro Windows 10 přiřadit normálním způsobem.  

Jinak musí být aplikace Portál společnosti pro Windows 10 náležitě aktualizovaná a podepsaná, abyste dodrželi patřičný způsob upgradu.  

Pokud je aplikace Portál společnosti pro Windows 10 podepsaná a přiřazená tímto způsobem, budete muset tento proces opakovat pro každou novou aktualizaci aplikace, až bude ve Storu k dispozici. Aplikace se při aktualizaci Storu automaticky neaktualizuje.  

Aplikaci můžete tímto způsobem podepsat a přiřadit takto:

1. Z webu [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript) si stáhněte podepisovací skript Microsoft Intune pro aplikaci Portál společnosti pro Windows 10.  Tento skript vyžaduje, aby na hostitelském počítači byla nainstalovaná sada Windows SDK pro Windows 10. Sadu Windows SDK pro Windows 10 si můžete stáhnout z webu [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296).
2. Stáhněte si aplikaci Portál společnosti pro Windows 10 z Microsoft Storu pro firmy (podrobnosti jsou uvedené výše).  
3. Spusťte skript se vstupními parametry popsanými v hlavičce skriptu, abyste podepsali aplikaci Portál společnosti pro Windows 10 (extrahovanou níže). Závislosti není nutné do skriptu předávat. Jsou vyžadované jenom v případě, když aplikaci nahráváte do konzoly pro správu Intune.

|       Parametr       |                                                                        Popis                                                                        |
|-----------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| InputWin10AppxBundle  |                                                  Cesta k umístění zdrojového souboru appxbundle                                                  |
| OutputWin10AppxBundle | Výstupní cesta pro podepsaný soubor appxbundle  Win81Appx Cesta k umístění souboru Portálu společnosti pro Windows 8.1 nebo Windows Phone 8.1 (.APPX) |
|      PfxFilePath      |                                       Cesta k souboru certifikátu Symantec Enterprise Mobile Code Signing Certificate (.PFX)                                        |
|      PfxPassword      |                                         Heslo certifikátu Symantec Enterprise Mobile Code Signing Certificate                                          |
|      PublisherId      |          ID vydavatele dané organizace. Pokud chybí, použije se pole Subject certifikátu Symantec Enterprise Mobile Code Signing Certificate.           |
|        SdkPath        |     Cesta ke kořenové složce sady Windows SDK pro Windows 10. Tento argument je volitelný a jeho výchozí hodnota je ${env:ProgramFiles(x86)}\Windows Kits\10.     |

Po ukončení běhu tohoto skriptu bude jeho výstupem podepsaná verze aplikace Portál společnosti pro Windows 10. Potom můžete podepsanou verzi aplikace přiřadit jako obchodní aplikaci přes Intune. Tím se aktuálně přiřazené verze upgradují na tuto novou aplikaci.  

## <a name="next-steps"></a>Další kroky

- [Postup přiřazení aplikací do skupin](apps-deploy.md)

