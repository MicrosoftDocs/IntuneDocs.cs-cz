---

title: "Nastavení zásad pro Android for Work | Microsoft Intune"
description: "Vytvořte zásady, které řídí nastavení a funkce na zařízeních s Androidem for Work, která spravujete pomocí Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 10/12/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 35a53076-74d6-486d-b201-e0da2e170008
ms.reviewer: chrisbal
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 32bded5047b1a08738418e3e36382eeae1a5f3b4
ms.openlocfilehash: f7c676b25f5dd5b7ee1d1d7c1b51b75a41b5c102


---

# Nastavení zásad pro Android for Work v Microsoft Intune

Intune poskytuje řadu předdefinovaných obecných nastavení, která můžete konfigurovat na zařízeních s Androidem for Work.

## Zásady obecné konfigurace

Pomocí **zásad obecné konfigurace Androidu for Work** v Intune můžete pro zařízení s Androidem for Work nakonfigurovat nastavení zabezpečení a pracovního profilu.

Pokud se v tomto tématu nezobrazí nastavení, které hledáte, je možné, že ho budete moct vytvořit pomocí vlastních zásad pro Android, které vám k řízení zařízení umožňuje použít nastavení OMA-URI. Další informace najdete v části [Nastavení vlastních zásad](#custom-policy-settings) dál v tomto tématu.

> [!TIP]
> Při zřízení pracovního profilu se zařízení automaticky zašifrují. Toto nastavení nejde změnit.

### Nastavení hesla

|Název nastavení|Podrobnosti|
|----------------|-|
|**Vyžadovat heslo k odemknutí mobilních zařízení**|Určuje, jestli se u spravovaných zařízení vyžaduje heslo. Vybírejte z těchto možností:<br><br>- **Složité** – vyžaduje alespoň jedno písmeno, číslici a symbol.<br>- **Alfanumerické** – vyžaduje alespoň jednu číslici a jeden abecední znak.<br>- **Abecední** – vyžaduje alespoň písmena nebo symboly.<br>- **Složité číselné** – vyžaduje číselné znaky, které se neopakují ani nejsou posloupné.<br>- **Číselné**<br><br>Pokud toto nastavení není povolené, nejsou na složitost žádné požadavky.|
|**Minimální délka hesla**|Určuje minimální počet znaků nebo číslic v hesle.|
|**Počet minut nečinnosti před uzamčením zařízení**|Určuje počet minut bez aktivity uživatele, než se zařízení automaticky zamkne.|
|**Povolit Smart Lock a další důvěryhodné agenty**<br>(Android 6 a novější)|Umožňuje řídit funkci Smart Lock v kompatibilních zařízeních s Androidem. Tato funkce telefonů, které se někdy říká agent pro určování důvěryhodnosti, umožňuje zakázat nebo obejít heslo uzamčené obrazovky zařízení, pokud se zařízení nachází v důvěryhodném umístění (například pokud je připojené k určitému zařízení Bluetooth nebo když se nachází blízko značky NFC). Pomocí tohoto nastavení můžete uživatelům zabránit v konfiguraci funkce Smart Lock.|
|**Počet opakovaných neúspěšných přihlášení, než se pracovní profil odebere**|Určuje povolený počet neúspěšných přihlášení, než se ze zařízení odebere pracovní profil. Nedojde přitom k úplnému vymazání zařízení.|
|**Pamatovat si historii hesel**|Zabraňuje opětovnému použití předchozích hesel.|
|**Pamatovat si historii hesel** - **Zabránit opětovnému použití předchozích hesel**|Určuje počet dříve použitých hesel, která se pamatují.|
|**Omezená platnost hesla (ve dnech)**|Určuje počet dní, než bude nutné změnit heslo zařízení.|
|**Povolit odemknutí otiskem prstu**<br>(Android 6 a novější)|Umožňuje odemknout zařízení, která to umožňují, otiskem prstu.|


### Nastavení pracovního profilu

|Název nastavení|Podrobnosti|
|----------------|-|
|**Povolit sdílení dat mezi pracovními a osobními profily**|Umožňuje aplikacím v pracovním profilu sdílet data s aplikacemi v osobním profilu uživatele. Vybírejte z těchto možností:<br><br>- **Zakázat sdílení přes hranice**<br>- **Aplikace v pracovním profilu můžou zpracovat žádost o sdílení z osobního profilu**<br>- **Žádná omezení sdílení**|
|**Skrýt oznámení z pracovního profilu, když je zařízení zamčené**<br>(Android 6 a novější)|Určuje, jestli se mají zobrazit oznámení z pracovního profilu, když je zařízení zamčené.|
|**Nastavit zásady pro výchozí oprávnění aplikací**<br>(Android 6 a novější)|Umožňuje nastavit zásady výchozích oprávnění pro všechny aplikace v pracovním profilu.|




## Nastavení vlastních zásad
Pomocí **zásad vlastní konfigurace pro Android for Work** v Microsoft Intune nasaďte nastavení OMA-URI, která se dají používat k ovládání funkcí na zařízeních s Androidem for Work. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Díky této vlastnosti můžete nasadit nastavení Androidu, která nejde konfigurovat se zásadami Intune.

> [!NOTE]
> Vlastní zásady Androidu v současné době podporují konfiguraci nastavení Wi-Fi jenom pro taková zařízení s Androidem, která obsahují předsdílený klíč.

### Obecná nastavení

|Název nastavení|Podrobnosti|
    |----------------|--------------------|
    |**Název**|Zadejte jedinečný název vlastní zásady pro Android, abyste ji mohli v konzole Intune snadno identifikovat.|
    |**Popis**|Zadejte popis, který bude shrnovat účel vlastní zásady pro Android, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.|

### Nastavení OMA-URI

   |Název nastavení|Podrobnosti|
    |--------|--------------------|
    |**Název nastavení**|Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.|
    |**Popis nastavení**|Zadejte popis, který nastavení přehledně vystihne, a další důležité informace, které vám ho pomůžou najít.|
    |**Datový typ**|Vyberte datový typ, ve kterém toto nastavení OMA-URI určíte. Vyberte z možností **Řetězec, Řetězec (XML), Datum a čas, Celé číslo, Číslo s plovoucí desetinnou čárkou** nebo **Logická hodnota**.|
    |**OMA-URI (rozlišuje velká a malá písmena)**|Zadejte OMA-URI, pro který chcete zadat nastavení.|
    |**Hodnota**|Zadejte hodnotu pro přidružení k OMA-URI, který jste zadali dřív.|

### Příklady

- [Vytvoření profilu Wi-Fi s předsdíleným klíčem](pre-shared-key-wi-fi-profile.md)
- [Použití vlastních zásad pro vytvoření profilu sítě VPN pro aplikaci pro zařízení se systémem Android](per-app-vpn-for-android-pulse-secure.md)

### Viz taky
[Správa nastavení a funkcí v zařízeních pomocí zásad Microsoft Intune](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)


<!--HONumber=Oct16_HO2-->

