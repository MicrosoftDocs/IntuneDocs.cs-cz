---
title: Řešení potíží s e-mailových profilů v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Problémy s e-mailovými profily a způsoby, jak je vyřešit
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 6/14/2018
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: ''
ms.reviewer: tscott
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 02eac7eaa42f6f9c97426e0536e48a4bc399ed08
ms.sourcegitcommit: fb2ca28ab0cf89202c935da3f9d98adcea20566d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57461018"
---
# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a>Řešení potíží s e-mailovými profily v Microsoft Intune

Projděte si některé běžné problémy, e-mailových profilu a jak je vyřešit.

Pokud vám tyto informace nepomohly, můžete také [získat podporu pro Microsoft Intune](get-support.md).

## <a name="unable-to-send-images-from--email-account"></a>Z e-mailového účtu nelze odesílat obrázky
Platí pro Intune na portálu Azure classic.

Uživatelé s automaticky nakonfigurovanými e-mailovými účty nemohou ze svých zařízení odesílat obrázky. V tomto scénáři může dojít, pokud **povolit odesílání e-mailů z aplikací třetí strany** není povolená.

### <a name="intune-solution"></a>Řešení Intune

1. Otevřete konzolu pro správu Microsoft Intune, vyberte **zásady** úloh > **zásady konfigurace**.

2. Vyberte e-mailový profil a zvolte **Upravit**.

3. Vyberte **Povolit odesílání e-mailů z aplikací třetí strany.**

### <a name="configuration-manager-integrated-with-intune-solution"></a>Configuration Manager integrovaný s řešením Intune

1. Otevřete konzolu nástroje Configuration Manager > **prostředky a Kompatibilita**.

2. Rozbalte **přehled** > **nastavení dodržování předpisů** > **přístup k prostředkům společnosti**a vyberte **e-mailové profily**.

3. Klikněte pravým tlačítkem na e-mailový profil a otevřete **Vlastnosti**.

4. Na kartě **Nastavení synchronizace** vyberte **Povolit odesílání e-mailů z aplikací třetí strany**.

## <a name="device-already-has-an-email-profile-installed"></a>Zařízení už má nainstalovaný e-mailový profil

Pokud si uživatel nainstaloval e-mailový profil před provisionining profil Intune, výsledek nasazení e-mailových profilu Intune závisí na platformě zařízení:

- **iOS**: Intune detekuje existující duplicitní profil e-mailu, do na základě názvu hostitele a e-mailové adresy. Duplicitní e-mailový profil vytvořený uživatelem blokuje nasazení profilu Intune vytvořeného správcem. To je běžný problém jako iOS uživatelům obvykle vytvořit e-mailový profil a potom se zaregistrují. Uživatele, že nejsou kompatibilní, protože jejich ručně nakonfigurované e-mailového profilu a vyzve uživatele k odebrání profilu aktualizaci aplikace portál společnosti. Uživatel musí svůj e-mailový profil odebrat, aby mohl být nasazen profil Intune. Tomuto problému předejít, požádejte své uživatele k registraci a Intune povolili nasazení profilu. Nainstalujte uživatel vytvořil e-mailový profil.

- **Windows:** Intune detekuje existující duplicitní profil e-mailu, do na základě názvu hostitele a e-mailové adresy. Intune přepíše existující e-mailový profil vytvořený uživatelem.

- **Samsung KNOX Standard**: Intune rozpozná duplicitní e-mailový účet na základě e-mailové adresy a přepíše se profilem Intune. Pokud uživatel tento účet nakonfiguruje, ho znovu přepíše profilem Intune. To může způsobit jisté zmatení uživatele, jehož účet konfigurace se přepíše.

Samsung KNOX nepoužívá k identifikaci profilu název hostitele. Doporučujeme vám, že nevytvoříte více e-mailových profilů pro nasazení do stejné e-mailovou adresou na různých hostitelích, protože jejich by se vzájemně přepisovaly.

## <a name="error--0x87d1fde8-for-knox-standard-device"></a>Chyba 0x87D1FDE8 v zařízení KNOX Standard
**Problém**: Po vytvoření a nasazení protokolu Exchange Active Sync e-mailový profil pro Samsung KNOX Standard pro různá zařízení s Androidem, chyba **0x87D1FDE8** nebo **náprava se nezdařila** se použije v hlášení v zařízení Vlastnosti > kartu zásad.

Zkontrolujte konfiguraci svého profilu EAS pro zařízení Samsung KNOX a zdroj zásad. Už není dostupná podpora možnosti synchronizace poznámek Samsung a ve vašem profilu by tato možnost neměla být vybraná. Ujistěte se, že zařízení mají dostatek času na zpracování zásady, až na 24 hodin.

## <a name="next-steps"></a>Další postup
Pokud vám tyto informace nepomohly, můžete také [získat podporu pro Microsoft Intune](get-support.md).
