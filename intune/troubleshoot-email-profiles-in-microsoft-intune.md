---
title: Řešení potíží s e-mailových profilů v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Podívejte se běžné problémy a řešení s využitím e-mailových profilů v Microsoft Intune, včetně duplicitní e-mailové profily a chyby na zařízení Samsung KNOX Standard s androidem.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/17/2019
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
ms.openlocfilehash: 2246e3f6faa853f620327558a7faf4dc9d6a6e85
ms.sourcegitcommit: 43ba5a05b2e1dc1997126d3574884f65cde449c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/18/2019
ms.locfileid: "67197516"
---
# <a name="common-issues-and-resolutions-with-email-profiles-in-microsoft-intune"></a>Běžné problémy a řešení s e-mailových profilů v Microsoft Intune

Projděte si některé běžné problémy, e-mailových profilu a jak je vyřešit.

## <a name="what-you-need-to-know"></a>Co je potřeba vědět

- E-mailové profily se nasadí pro uživatele, který zaregistroval zařízení. Pokud chcete nakonfigurovat e-mailový profil, Intune využívá Azure Active Directory (AD) vlastnosti v e-mailový profil uživatele během registrace. [Přidat nastavení e-mailu pro zařízení](email-settings-configure.md) může být dobrým zdrojem informací je.
- Po provedení migrace z hybridní prostředí Configuration managera na samostatnou službu Intune, e-mailový profil ze hybridní prostředí Configuration managera zůstává v zařízení po dobu 7 dní. Toto je očekávané chování. Pokud potřebujete e-mailový profil odebrat dříve, obraťte se na [podpory služby Intune](get-support.md).
- Pro Android Enterprise nasaďte Gmail nebo devět pro práci pomocí spravovaných Store Google Play. [Přidání aplikací pro spravovaný obchod Google Play](apps-add-android-for-work.md) jsou uvedené kroky.
- Aplikace Microsoft Outlook pro iOS a Android nepodporuje e-mailové profily. Místo toho nasaďte zásady Konfigurace aplikací. Další informace najdete v tématu [nastavení konfigurace aplikace Outlook](app-configuration-policies-outlook.md).
- E-mailové profily cílené na skupiny zařízení (ne skupiny uživatelů) nemusí být doručit do zařízení. Pokud má zařízení primárními uživateli, by měly fungovat cílení na zařízení. Pokud e-mailový profil obsahuje uživatelské certifikáty, je nutné do cílových skupin uživatelů.
- Uživatelé můžou opakovaně vyzváni k zadání hesla pro e-mailový profil. V tomto scénáři zkontrolujte všechny certifikáty, které jsou uvedené v e-mailový profil. Pokud jeden z certifikátů není zacílený na uživatele, pak Intune pokusí znovu nasadit e-mailový profil.

## <a name="device-already-has-an-email-profile-installed"></a>Zařízení už má nainstalovaný e-mailový profil

Pokud uživatelé vytvářet e-mailový profil, před registrací v Intune nebo Office 365 MDM, e-mailový profil nasadit pomocí Intune nemusí fungovat podle očekávání:

- **iOS**: Intune detekuje existující duplicitní profil e-mailu, do na základě názvu hostitele a e-mailové adresy. Uživatel vytvořil e-mailový profil zablokuje nasazení profilu Intune vytvořeného. To je běžný problém jako iOS uživatelům obvykle vytvořit e-mailový profil a potom se zaregistrují. Aplikace portál společnosti hlásí, že uživatel není kompatibilní se může vyzvat uživatele k odebrání e-mailový profil.

  Uživatel by měl jejich e-mailový profil odebrat, tak je možné nasadit profil Intune. Tomuto problému předejít, požádejte své uživatele k registraci a Intune povolili nasazení profilu e-mailu. Uživatelé pak mohou vytvářet jejich e-mailový profil.

- **Windows:** Intune detekuje existující duplicitní profil e-mailu, do na základě názvu hostitele a e-mailové adresy. Intune přepíše existující e-mailový profil vytvořený uživatelem.

- **Samsung KNOX Standard**: Intune rozpozná duplicitní e-mailový účet na základě e-mailové adresy a přepíše se profilem Intune. Pokud uživatel tento účet nakonfiguruje, ho znovu přepíše profilem Intune. To může způsobit jisté zmatení uživatele, jehož účet konfigurace se přepíše.

Samsung KNOX nepoužívá k identifikaci profilu název hostitele. Doporučujeme že nevytvářet více e-mailových profilů pro nasazení do stejné e-mailovou adresou na různých hostitelích, jako jsou by se vzájemně přepisovaly.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>Chyba 0x87D1FDE8 v zařízení KNOX Standard

**Problém**: Po vytvoření a nasazení protokolu Exchange Active Sync e-mailový profil pro Samsung KNOX Standard různých zařízeních s Androidem, **0x87D1FDE8** nebo **náprava se nezdařila** na zařízení zobrazí chyba Vlastnosti > kartu zásad.

Zkontrolujte konfiguraci svého profilu EAS pro zařízení Samsung KNOX a zdroj zásad. Možnosti synchronizace poznámek Samsung již není podporována a neměla by být vybrána tato možnost ve vašem profilu. Ujistěte se, že zařízení mají dostatek času na zpracování zásady, až na 24 hodin.

## <a name="unable-to-send-images-from--email-account"></a>Z e-mailového účtu nelze odesílat obrázky

Uživatelé, kteří mají e-mailové účty se automaticky nakonfiguruje nelze odesílat obrázky ze svých zařízení. V tomto scénáři může dojít, pokud **povolit odesílání e-mailů z aplikací třetí strany** není povolená.

### <a name="intune-solution"></a>Řešení Intune

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **konfigurace zařízení** > **profily**.
3. Vyberte e-mailový profil > **vlastnosti** > **nastavení**.
4. Nastavte **povolit odesílání e-mailů z aplikací třetí strany** nastavení **povolit**.

### <a name="configuration-manager-hybrid"></a>Hybridní prostředí Configuration managera

1. Otevřete konzolu nástroje Configuration Manager > **prostředky a Kompatibilita**.

2. Rozbalte **přehled** > **nastavení dodržování předpisů** > **přístup k prostředkům společnosti**a vyberte **e-mailové profily**.

3. Klikněte pravým tlačítkem na e-mailový profil a otevřete **Vlastnosti**.

4. Na kartě **Nastavení synchronizace** vyberte **Povolit odesílání e-mailů z aplikací třetí strany**.

## <a name="next-steps"></a>Další postup

Získat [podpory Microsoftu](get-support.md), nebo použijte [komunitní fóra](https://social.technet.microsoft.com/Forums/en-US/home?category=microsoftintune).
