---
title: "Registrace zařízení iOS vlastněných společností | Microsoft Intune"
description: "Registrace zařízení iOS vlastněných společností pomocí programu Apple DEP (Device Enrollment Program) nebo nástroje Apple Configurator"
keywords: 
author: NathBarn
manager: angrobe
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2d3ca4ab-f20c-4d56-9413-f8ef19cf0722
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 9b7b8f6e5182e228458f5ea75e804a638f1e2a2b
ms.openlocfilehash: ca05e94e72269c11db24b667f1d113c794cd8b23


---

# Registrace zařízení iOS vlastněných společností v Microsoft Intune
Microsoft Intune podporuje registraci firemních zařízení iOS prostřednictvím programu Apple Device Enrollment Program (DEP) nebo pomocí nástroje [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) spuštěného na počítači Mac.

**Předpoklad:**  [Certifikát služby Apple Push Notification](set-up-ios-and-mac-management-with-microsoft-intune.md)

Existují tři způsoby registrace firmou zaregistrovaných zařízení iOS:

-   **Apple Configurator** – Zařízení s iOS lze registrovat exportováním podnikového registračního profilu a následným připojením těchto mobilních zařízení k nástroji Apple Configurator spuštěném na počítači Mac. Apple Configurator podporuje dva způsoby registrace:

    - **Registrace v průvodci nastavením** – Obnoví tovární nastavení a připraví zařízení k nastavení jeho novým uživatelem. Tato metoda vyžaduje, aby se správce pomocí USB připojil k počítači Mac, na kterém je spuštěný nástroj [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), a předkonfiguroval registraci. Zařízení jsou potom doručovaná uživatelům, kteří spustí proces průvodce nastavením a nakonfigurují zařízení svými pracovními nebo školními pověřovacími údaji a dokončí proces registrace. [Registrace zařízení s iOS pomocí nástroje Apple Configurator a Průvodce nastavením](ios-setup-assistant-enrollment-in-microsoft-intune.md)

    - **Přímá registrace** – Vytvoří soubor kompatibilní s Apple Configuratorem, který můžete použít při přípravě zařízení. Zaregistrované zařízení nemá obnovené tovární nastavení a nemá přiřazeného uživatele. Tato metoda vyžaduje, aby se správce pomocí USB připojil k počítači Mac, na kterém je spuštěný nástroj [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), a zaregistroval zařízení. [Registrace zařízení s iOS pomocí přímé registrace nástroje Apple Configurator](ios-direct-enrollment-in-microsoft-intune.md)

-   **Program registrace zařízení (DEP)** – Nasadí do zařízení koupeného prostřednictvím programu registrace zařízení Apple profil pro registraci „vzduchem“. Když uživatel na zařízení spustí průvodce nastavením, zařízení se registruje v Intune.  U zařízení zaregistrovaných v programu DEP uživatelé nemůžou registraci zrušit. [Registrace zařízení s iOS pomocí programu registrace zařízení DEP](ios-device-enrollment-program-in-microsoft-intune.md)

## Použití Portálu společnosti v zařízeních zaregistrovaných v programu DEP nebo Apple Configuratoru

Zařízení nakonfigurovaná s přidružením uživatele umožňují instalaci a spuštění aplikace Portál společnosti, která slouží ke stahování aplikací a správě zařízení. Až uživatelé obdrží zařízení, musí provést určitý počet dodatečných kroků, aby dokončili postup Pomocníka s nastavením a nainstalovali aplikaci Portál společnosti.

Postup registrace zařízení s iOS vlastněných společností s přidružením uživatele
1. Když uživatel zapne své zařízení, zobrazí se výzva k dokončení postupu Pomocníka s nastavením. Během nastavování se uživateli zobrazí výzva k zadání přihlašovacích údajů. Uživatel musí použít přihlašovací údaje (tj. jedinečné osobní jméno nebo hlavní název uživatele) přidružené k jeho předplatnému Intune.

2. Během nastavování se uživateli zobrazí výzva k zadání Apple ID. Apple ID je potřeba zadat proto, aby mohlo zařízení nainstalovat aplikaci Portál společnosti. Apple ID se dá zadat i po dokončení nastavení, a to v nabídce nastavení iOS.

3. Po dokončení nastavení musí zařízení s iOS nainstalovat aplikaci Portálu společnosti z App Storu, třeba aplikaci Portál společnosti.

4. Uživatel se teď může přihlásit k portálu společnosti pomocí hlavního názvu uživatele, který použil při nastavování zařízení.

5. Po přihlášení se uživateli zobrazí výzva k registraci zařízení. Prvním krokem je identifikace zařízení. Aplikace zobrazí seznam zařízení s iOS, která jsou už ve společnosti registrovaná a mají přiřazený účet Intune koncového uživatele. Vyberte odpovídající zařízení.

  Pokud zařízení ještě není ve společnosti zaregistrované, vyberte „Nové zařízení“ a pokračujte standardním postupem registrace.

6. Na další obrazovce musí uživatel potvrdit sériové číslo nového zařízení. Uživatel může klepnout na odkaz „Potvrďte sériové číslo“. Tím se spustí aplikace Nastavení, která sériové číslo ověří. Potom musí uživatel zadat poslední 4 znaky sériového čísla do aplikace Portál společnosti.

  Tento krok ověřuje, jestli se jedná o firemní zařízení zaregistrované v Intune. Pokud sériové číslo zařízení neodpovídá, znamená to, že došlo k výběru nesprávného zařízení. Vraťte se na předchozí obrazovku a vyberte jiné zařízení.

7. Po ověření sériového čísla aplikace Portál společnosti přesměruje uživatele na web Portál společnosti pro dokončení registrace a potom zobrazí výzvu k návratu do aplikace.

8. Registrace je u konce. Teď můžete na zařízení používat kompletní sadu funkcí.

### O firemních spravovaných zařízeních bez přidružení uživatele

Zařízení nakonfigurovaná bez přidružení uživatele nepodporují aplikaci Portál společnosti a ta by se na ně neměla instalovat. Portál společnosti je určený pro uživatele, kteří mají firemní přihlašovací údaje a potřebují přístup k podnikovým prostředkům podle svých potřeb (třeba k e-mailu). Zařízení zaregistrovaná bez přidružení uživatele nejsou určená k tomu, aby se k nim přihlašoval jeden konkrétní uživatel. Typickými případy použití zařízení zaregistrovaných bez přidružení uživatele jsou zařízení veřejných terminálů, pokladny nebo sdílená zařízení. Pokud je potřeba přidružení uživatele, před registrací uživatele zkontrolujte, jestli je u registračního profilu daného zařízení vybraná možnost Přidružení uživatele. Pokud chcete stav přidružení zařízení změnit, musíte zařízení nejdřív vyřadit a potom ho znovu zaregistrovat.



### Související témata
[Příprava registrace zařízení v Microsoft Intune](get-ready-to-enroll-devices-in-microsoft-intune.md)



<!--HONumber=Aug16_HO1-->


