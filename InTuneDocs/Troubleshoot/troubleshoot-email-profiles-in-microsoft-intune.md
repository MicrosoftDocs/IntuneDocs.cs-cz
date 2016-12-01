---
title: "Řešení potíží s e-mailovými profily | Microsoft Intune"
description: "Problémy s e-mailovými profily a způsoby, jak je vyřešit"
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 08/01/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ms.reviewer: tscott
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1b6fcf0cae23581c0391009fd7d63498d3c7eb2d
ms.openlocfilehash: 504714c09815d8c6fed6515cf7a27b841d77eb57


---

# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a>Řešení potíží s e-mailovými profily v Microsoft Intune
Tady najdete některé problémy s e-mailovými profily a způsoby, jak je vyřešit.

Pokud tyto informace váš problém nevyřeší, přečtěte si téma [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md), ve kterém najdete další způsoby, jak získat nápovědu.


## <a name="unable-to-send-images-from-email-account"></a>Z e-mailového účtu nelze odesílat obrázky
Uživatelé s automaticky nakonfigurovanými e-mailovými účty nemohou ze svých zařízení odesílat obrázky.
K tomu dojde, když není povolená možnost **Povolit odesílání e-mailů z aplikací třetí strany**.

### <a name="intune-solution"></a>Řešení Intune

1.  Otevřete konzolu pro správu Microsoft Intune, vyberte úlohu **Zásady** &gt; **Zásady konfigurace**.

2.  Vyberte e-mailový profil a zvolte **Upravit**.

3.  Vyberte **Povolit odesílání e-mailů z aplikací třetí strany.**

### <a name="configuration-manager-integrated-with-intune-solution"></a>Configuration Manager integrovaný s řešením Intune

1.  Otevřete konzolu Configuration Manageru &gt;**Prostředky a kompatibilita**.

2.  Rozbalte **Přehled** -&gt; **Nastavení dodržování předpisů** -&gt; **Přístup k prostředkům společnosti** a vyberte **E-mailové profily**.

3.  Klikněte pravým tlačítkem na e-mailový profil a otevřete **Vlastnosti**.

4.  Na kartě **Nastavení synchronizace** vyberte **Povolit odesílání e-mailů z aplikací třetí strany**.


## <a name="device-already-has-an-email-profile-installed"></a>Zařízení už má nainstalovaný e-mailový profil

Pokud uživatel nainstaloval e-mailový profil dřív, než profil zřídila služba Intune, výsledek nasazení e-mailového profilu Intune bude záviset na platformě zařízení:

-**iOS**: Intune detekuje stávající duplicitní e-mailový profil na základě názvu hostitele a e-mailové adresy. Duplicitní e-mailový profil vytvořený uživatelem bude blokovat nasazení profilu Intune vytvořeného správcem. Tento problém je běžný, protože uživatelé s iOS obvykle vytvoří e-mailový profil a potom se zaregistrují. Portál společnosti bude uživatele informovat o tom, že požadavky nejsou splněny kvůli ručně nakonfigurovanému e-mailovému profilu a vyzve uživatele k odebrání příslušného profilu. Uživatel by měl svůj e-mailový profil odebrat, aby bylo možné nasadit profil Intune. Pokud chcete problémům zabránit, požádejte své uživatele, aby se zaregistrovali před instalací e-mailového profilu a aby Intune povolili nasazení profilu.

-**Windows**: Intune detekuje stávající duplicitní e-mailový profil na základě názvu hostitele a e-mailové adresy. Intune přepíše existující e-mailový profil vytvořený uživatelem.

-**Samsung KNOX Standard**: Intune rozpozná duplicitní e-mailový profil na základě e-mailové adresy a přepíše ho profilem Intune. Pokud uživatel tento účet nakonfiguruje, profil Intune ho znovu přepíše. Poznámka: Uživateli potom nemusí být úplně jasné, která konfigurace účtu se přepíše.

Vzhledem k tomu, že Samsung KNOX nevyužívá k identifikaci profilu název hostitele, doporučujeme nevytvářet několik e-mailových profilů pro nasazení se stejnou e-mailovou adresou na různých hostitelích, protože by se vzájemně přepsaly.

## <a name="error-0x87d1fde8-for-knox-standard-device"></a>Chyba 0x87D1FDE8 v zařízení KNOX Standard
**Problém**: Po vytvoření a nasazení e-mailového profilu Exchange Active Sync pro Samsung KNOX Standard do různých zařízení se systémem Android hlásí zařízení na kartě vlastností a zásad chybu **0x87D1FDE8** nebo že se **náprava nezdařila**.

Zkontrolujte konfiguraci svého profilu EAS pro zařízení Samsung KNOX a zdroj zásad. Už není dostupná podpora možnosti synchronizace poznámek Samsung a ve vašem profilu by tato možnost neměla být vybraná. Dopřejte zařízením dostatek času na zpracování zásady, a to až 24 hodin.

## <a name="next-steps"></a>Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).



<!--HONumber=Nov16_HO1-->


