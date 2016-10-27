---
title: "Nastavení zásad pro Windows Phone 8.1 | Microsoft Intune"
description: "Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete konfigurovat v zařízeních s Windows Phone 8.1. Navíc můžete určit hodnoty OMA-URI k vytvoření vlastních nastavení, která nejsou k dispozici prostřednictvím Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 83f7469c-272e-43f2-8139-b0d7bc34f43f
ms.reviewer: heenamac
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: e95db6d0ccbe350984f11ce08749b700c2f5ad01
ms.openlocfilehash: 3c9c75e5e9e19574a5b4525688103dc95e3d6b9b


---

# Nastavení zásad pro Windows Phone 8.1 v Microsoft Intune

Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete konfigurovat v zařízeních s Windows Phone 8.1. Navíc můžete určit hodnoty OMA-URI (Open Mobile Alliance Uniform Resource Identifier) k vytvoření vlastních nastavení, která nejsou k dispozici prostřednictvím Intune.

## Obecné nastavení konfigurace

Ke konfiguraci následujících nastavení pro zařízení s Windows Phone 8.1 použijte **obecné zásady konfigurace pro Windows Phone (Windows Phone 8.1 a novější)**:

-   **Nastavení zabezpečení mobilního zařízení** – Zvolte ze seznamu předdefinovaných nastavení, která umožňují v zařízení ovládat celou řadu funkcí.

-   **Seznam aplikací dodržujících a nedodržujících předpisy** – Určete seznam aplikací, které splňují nebo nesplňují předpisy ve vaší společnosti. Zařízení Windows Phone můžou instalaci těchto aplikací blokovat nebo povolit.

### Nastavení použitelnosti

|Název nastavení|Podrobnosti|
|----------------|----------------------------------|
|**Použít všechny konfigurace ve Windows 10**|Povolí nasazení těchto zásad kromě zařízení s Windows Phone 8.1 také pro zařízení s Windows 10 Mobile.|

### Nastavení hesla

|Název nastavení|Podrobnosti|
|----------------|------|
|**Vyžadovat heslo k odemknutí mobilních zařízení**|Zadejte, jestli uživatelé při přístupu ke svému zařízení musí zadat heslo.|
|**Vyžadovaný typ hesla**|Určuje typ hesla, které se bude vyžadovat, například jenom číslice nebo alfanumerické znaky.|
|**Vyžadovaný typ hesla – Minimální počet znakových sad**|Určuje, kolik různých znakových sad musí být v hesle zahrnutých. Používají se čtyři znakové sady: malá písmena, velká písmena, číslice a symboly. Pro zařízení s iOS ale toto nastavení určuje počet symbolů, které musí heslo obsahovat.|
|**Minimální délka hesla**|Určuje minimální počet znaků, které heslo musí obsahovat.|
|**Povolit jednoduchá hesla**|Umožňuje použití jednoduchých hesel, jako je 0000 nebo 1234.|
|**Počet povolených opakovaných neúspěšných přihlášení, než bude zařízení vymazáno**|Určuje, kolikrát může uživatel zadat nesprávné heslo, než se zařízení vymaže.|
|**Počet minut nečinnosti před vypnutím displeje**|Určuje dobu, po kterou musí zařízení zůstat v nečinnosti, než se automaticky uzamkne jeho obrazovka.|
|**Omezená platnost hesla (ve dnech)**|Určuje počet dní, než bude nutné změnit heslo zařízení.|Ano|Ano|
|**Pamatovat si historii hesel**|Určuje, jestli se dříve použitá hesla pamatují, aby je uživatelé nemohli použít znovu.|
|**Pamatovat si historii hesel** – **Zabránit opětovnému použití předchozích hesel**|Určuje, kolik dříve použitých hesel se pamatuje.|

### Nastavení šifrování

|Název nastavení|Podrobnosti|
|----------------|------|
|**Vyžadovat šifrování u mobilního zařízení**|Vyžaduje, aby data na podporovaných mobilních zařízeních byla šifrovaná.|

### Nastavení systému

|Název nastavení|Podrobnosti|
|----------------|-----|
|**Povolit snímek obrazovky**|Povolí uživateli zachytit obsah obrazovky jako obrázek.|
|**Povolit odeslání diagnostických dat**|Povolí zařízení odesílat diagnostické informace Microsoftu.|

### Nastavení cloudu – účty a synchronizace

|Název nastavení|Podrobnosti|
|----------------|------|
|**Povolit účet Microsoft**|Povolí propojení účtu Microsoft se zařízením.|

### Nastavení e-mailu

|Název nastavení|Podrobnosti|
|----------------|-----|
|**Povolit vlastní e-mailové účty**|Povolí zařízení připojit se k e-mailovým účtům jiným než Microsoftu.|

### Nastavení aplikace – prohlížeč

|Název nastavení|Podrobnosti|
|----------------|-----|
|**Povolit webový prohlížeč**|Povolí nebo zablokuje integrovaný webový prohlížeč v zařízeních.|

### Nastavení aplikace – aplikace

|Název nastavení|Podrobnosti|
|----------------|-----|
|**Povolit obchod s aplikacemi**|Umožňuje uživatelům připojit se ze zařízení k obchodu s aplikacemi.|

### Nastavení možností zařízení – hardware

|Název nastavení|Podrobnosti|
|----------------|-----|
|**Povolit fotoaparát**|Povolí nebo zablokuje fotoaparát zařízení.|
|**Povolit vyměnitelné úložiště**|Povolí použití vyměnitelného úložiště v zařízení, třeba SD karty.|
|**Povolit Wi-Fi**|Povolí nebo zakáže funkce sítě Wi-Fi v zařízení.|
|**Povolit sdílení internetového připojení přes Wi-Fi**|Povolí sdílení mobilního internetového připojení přes Wi-Fi na zařízení.|
|**Povolit automatické připojení k bezplatným Wi-Fi hotspotům**|Povolí zařízení automaticky se připojovat k bezplatným Wi-Fi hotspotům a automaticky přijímat jakékoli podmínky použití.|
|**Povolit oznamování Wi-Fi hotspotů**|Umožní odesílání informací o připojeních Wi-Fi, aby uživatel mohl nacházet možnosti připojení v okolí.|
|**Povolit zeměpisnou polohu**|Umožní zařízení využívat informace o poloze.|
|**Povolit komunikaci NFC**|Umožní operace, které používají bezkontaktní komunikaci.|
|**Povolit Bluetooth**|Povolí nebo zakáže funkce Bluetooth v zařízení.|

### Nastavení možností zařízení – funkce

|Název nastavení|Podrobnosti|
|----------------|----|
|**Povolit kopírování a vkládání**|Povolí funkci kopírování a vkládání na zařízeních.|

### Nastavení pro povolené a blokované aplikace
V seznamu **Povolené a blokované aplikace** zadejte seznam aplikací, které chcete povolit nebo blokovat, s využitím těchto informací:

> [!NOTE]
> Jedna zásada může obsahovat seznam jenom povolených, nebo jenom blokovaných aplikací. Nejde zadat oba seznamy v jedné zásadě.

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Blokovat otevírání vypsaných aplikací ze zařízení**|Zobrazí seznam aplikací, které Intune nespravuje a které nemají uživatelé dovolené nainstalovat a spustit.|
|**Povolit zařízením instalovat jenom uvedené aplikace**|Zobrazí seznam aplikací, které mají uživatelé dovoleno instalovat. Uživatelé nemůžou instalovat žádné další aplikace. Aplikace, které spravuje Intune, jsou povolené automaticky.|
|**Přidat**|Přidá aplikaci do vybraného seznamu. Zadejte název podle své volby, volitelně vydavatele aplikaci a adresu URL aplikace v úložišti aplikací. Další nápovědu najdete v části Určení adres URL na obchody s aplikacemi dál v tomto tématu.
|**Importovat aplikace**|Importuje seznam aplikací, které jste zadali v souboru hodnot oddělených čárkami. V souboru použijte formát: název aplikace, vydavatel a adresa URL aplikace.|
|**Upravit**|Tady můžete upravit název, vydavatele a adresu URL vybrané aplikace.|
|**Odstranit**|Odstraní vybranou aplikaci ze seznamu.|
> [!IMPORTANT]
> Pokud zadáváte seznam aplikací povolených pro zařízení Windows Phone 8.1, je potřeba přidat do tohoto seznamu aplikaci Portál společnosti, jinak se zablokuje.


### Referenční informace pro povolené a blokované aplikace

#### Určení adres URL na obchody s aplikacemi
Pokud chcete zadat adresu URL aplikace do seznamu povolených a blokovaných aplikací, použijte následující formát:

Na stránce [Aplikace a hry pro Windows Phone](http://www.windowsphone.com/en-us/store/overview) najděte aplikaci, kterou chcete použít.

Otevřete stránku aplikace a zkopírujte adresu URL do schránky. Tu teď můžete použít jako adresu URL v seznamu povolených nebo blokovaných aplikací.

**Příklad:** Vyhledání aplikace Skype ve Storu. Použijete adresu URL **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.

## Nastavení vlastních zásad
Pomocí možnosti Microsoft Intune **Zásady vlastní konfigurace pro Windows Phone** nasaďte nastavení OMA-URI, které se dá používat k ovládání funkcí na zařízeních s **Windows Phone 8.1**. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Díky této vlastnosti můžete nasadit nastavení Windows Phone, která nejdou konfigurovat obecnými zásadami konfigurace Intune. Informace o nastaveních, která můžete pomocí těchto zásad konfigurovat, najdete v tématu [Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).

Nápovědu k vytváření nastavení OMA-URI pro zařízení Windows Phone, najdete v části [Dokumentace k MDM protokolu pro Windows Phone 8.1](http://technet.microsoft.com/library/dn499787.aspx).

### Obecná nastavení

|Název nastavení|Podrobnosti|
|----------------|--------------------|
|**Název**|Zadejte jedinečný název vlastní zásady, abyste ji mohli v konzole Intune snadno identifikovat.|
|**Popis**|Zadejte popis, který zásadu vystihne, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.|

### Nastavení OMA-URI

V části **Nastavení OMA-URI** přidejte nastavení kliknutím na **Přidat**. Můžete taky upravit nebo odstranit existující nastavení.

V dialogovém okně **Přidat nebo upravit nastavení OMA-URI** zadejte následující informace:

|Název nastavení|Podrobnosti|
    |--------|--------------------|
    |**Název nastavení**|Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.|
    |**Popis nastavení**|Zadejte popis, který nastavení přehledně vystihne, a další důležité informace, které vám ho pomůžou najít.|
    |**Datový typ**|Vyberte datový typ, ve kterém toto nastavení OMA-URI určíte. Vybírejte z těchto možností:<br /><br />-   **Řetězec**<br />-   **Řetězec (XML)**<br />-   **Datum a čas**<br />-   **Celé číslo**<br />-   **Číslo s plovoucí desetinnou čárkou**<br />-   **Logická hodnota**|
    |**OMA-URI (rozlišuje velká a malá písmena)**|Zadejte OMA-URI, pro který chcete zadat nastavení.|
    |**Hodnota**|Zadejte hodnotu pro přidružení k OMA-URI, který jste zadali dřív.|

### Související témata
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)



<!--HONumber=Oct16_HO2-->


