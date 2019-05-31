---
title: Řešení potíží s e-mailových profilů v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Podívejte se běžné problémy a řešení s využitím e-mailových profilů v Microsoft Intune, včetně duplicitní e-mailové profily a chyby na zařízení Samsung KNOX Standard s androidem.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 05/29/2019
ms.topic: troubleshooting
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
ms.openlocfilehash: e0fe37deb63457fef869df0f7263970a4e53cb29
ms.sourcegitcommit: a97b6139770719afbd713501f8e50f39636bc202
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/30/2019
ms.locfileid: "66402708"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Běžné problémy a řešení s e-mailových profilů v Microsoft Intune

Projděte si některé běžné problémy, e-mailových profilu a jak je vyřešit.

## <a name="device-already-has-an-email-profile-installed"></a>Zařízení už má nainstalovaný e-mailový profil

Pokud uživatelé vytvářet e-mailový profil, před registrací v Intune, e-mailový profil Intune se nemusí fungovat podle očekávání:

- **iOS**: Intune detekuje existující duplicitní profil e-mailu, do na základě názvu hostitele a e-mailové adresy. Uživatel vytvořil e-mailový profil zablokuje nasazení profilu Intune vytvořeného. To je běžný problém jako iOS uživatelům obvykle vytvořit e-mailový profil a potom se zaregistrují. Aplikace portál společnosti hlásí, že uživatel není kompatibilní se může vyzvat uživatele k odebrání e-mailový profil.

  Uživatel by měl jejich e-mailový profil odebrat, tak je možné nasadit profil Intune. Tomuto problému předejít, požádejte své uživatele k registraci a Intune povolili nasazení profilu e-mailu. Uživatelé pak mohou vytvářet jejich e-mailový profil.

- **Windows:** Intune detekuje existující duplicitní profil e-mailu, do na základě názvu hostitele a e-mailové adresy. Intune přepíše existující e-mailový profil vytvořený uživatelem.

- **Samsung KNOX Standard**: Intune rozpozná duplicitní e-mailový účet na základě e-mailové adresy a přepíše se profilem Intune. Pokud uživatel tento účet nakonfiguruje, ho znovu přepíše profilem Intune. To může způsobit jisté zmatení uživatele, jehož účet konfigurace se přepíše.

Samsung KNOX nepoužívá k identifikaci profilu název hostitele. Doporučujeme že nevytvářet více e-mailových profilů pro nasazení do stejné e-mailovou adresou na různých hostitelích, jako jsou by se vzájemně přepisovaly.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>Chyba 0x87D1FDE8 v zařízení KNOX Standard

**Problém**: Po vytvoření a nasazení protokolu Exchange Active Sync e-mailový profil pro Samsung KNOX Standard různých zařízeních s Androidem, **0x87D1FDE8** nebo **náprava se nezdařila** na zařízení zobrazí chyba Vlastnosti > kartu zásad.

Zkontrolujte konfiguraci svého profilu EAS pro zařízení Samsung KNOX a zdroj zásad. Možnosti synchronizace poznámek Samsung již není podporována a neměla by být vybrána tato možnost ve vašem profilu. Ujistěte se, že zařízení mají dostatek času na zpracování zásady, až na 24 hodin.

## <a name="unable-to-send-images-from--email-account"></a>Z e-mailového účtu nelze odesílat obrázky

Platí pro Intune na portálu Azure classic.

Uživatelé, kteří mají e-mailové účty se automaticky nakonfiguruje nelze odesílat obrázky ze svých zařízení. V tomto scénáři může dojít, pokud **povolit odesílání e-mailů z aplikací třetí strany** není povolená.

### <a name="intune-solution"></a>Řešení Intune

1. Otevřete konzolu pro správu Microsoft Intune, vyberte **zásady** úloh > **zásady konfigurace**.

2. Vyberte e-mailový profil a zvolte **Upravit**.

3. Vyberte **Povolit odesílání e-mailů z aplikací třetí strany.**

### <a name="configuration-manager-integrated-with-intune-solution"></a>Configuration Manager integrovaný s řešením Intune

1. Otevřete konzolu nástroje Configuration Manager > **prostředky a Kompatibilita**.

2. Rozbalte **přehled** > **nastavení dodržování předpisů** > **přístup k prostředkům společnosti**a vyberte **e-mailové profily**.

3. Klikněte pravým tlačítkem na e-mailový profil a otevřete **Vlastnosti**.

4. Na kartě **Nastavení synchronizace** vyberte **Povolit odesílání e-mailů z aplikací třetí strany**.

## <a name="next-steps"></a>Další postup

Získat [podpory Microsoftu](get-support.md), nebo použijte [komunitní fóra](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).