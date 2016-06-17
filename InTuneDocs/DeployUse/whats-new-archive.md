---
# required metadata

title: Archiv novinek | Microsoft Intune
description:
keywords:
author: Lindavr
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ed2db991-4729-49a7-a1e6-be2ffa0d03d1

# optional metadata

ROBOTS: noindex,nofollow
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---


## Září 2015
### Aktualizace správy mobilních zařízení a aplikací
**Všechny funkce všechny správy systému iOS v Intune teď podporují iOS 9**
Podrobnosti o možnostech správy systému iOS 9 najdete v [tomto příspěvku na blogu](http://blogs.technet.com/b/microsoftintune/archive/2015/09/09/day-zero-support-for-ios-9-with-intune.aspx)..

**Nové zásady konfigurace mobilních aplikací pro iOS**
Nová zásada konfigurace mobilních aplikací umožňuje automaticky zadat nastavení, které můžou aplikace iOS vyžadovat při spuštění. Můžete třeba zadat síťový port nebo uživatelské jméno. Podrobnosti najdete v tématu [Konfigurace aplikací pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)..

**Snazší správa aplikací pro uživatele iOS 9**
 V této verzi můžete zahrnout už nasazené aplikace uživatelů systému iOS 9 pod správu službou Intune. U starších verzí systému iOS platí, že pokud nasazujete aplikaci a na zařízení je už nainstalovaná nespravovaná verze aplikace, budete nejdřív muset požádat uživatele, aby aplikaci ručně odinstaloval, a teprve potom bude moct služba Intune nainstalovat spravovanou aplikaci.

 Od této verze služby Intune ale můžete uživatele zařízení se systémem iOS 9 vyzvat, aby službě Intune umožnili převzít správu aplikace, a použít všechny příslušné zásady správy mobilních aplikací.

 **Správa systému Windows 10** Pomocí nové [obecné zásady konfigurace pro Windows 10](https://technet.microsoft.com/library/mt404697.aspx) můžete konfigurovat heslo, zařízení, prohlížeč a další nastavení pro zaregistrovaná zařízení se systémy Windows 10 a Windows 10 Mobile.

 **Vytváření a nasazení aplikací do zaregistrovaných zařízení s Windows 10** Nový typ instalačního programu softwaru, Instalační služba systému Windows přes MDM (&#42;.msi), umožňuje vytvářet a nasazovat aplikace Instalační služby systému Windows pro zaregistrovaná zařízení se systémem Windows 10. Podrobnosti najdete v tématu [Začínáme s nasazováním aplikací v Microsoft Intune](https://technet.microsoft.com/library/dn646955.aspx)..

### Změny a aktualizace aplikací portálů společnosti Microsoft
V této verzi se provedly následující změny aplikací portálu společnosti:

**iOS**
* Microsoft automaticky shromažďuje anonymní informace o výkonu a využití portálu společnosti za účelem zlepšení svých produktů a služeb. Koncoví uživatelé můžou na svém zařízení shromažďování dat vypnout v nastavení dat o využití, ale správci nemají nad shromažďováním dat žádnou kontrolu a nemůžou toto nastavení koncového uživatele nijak změnit.
* Podpora rozlišení celoobrazovkového režimu na zařízeních iPhone 6 a 6 Plus
* Opravy chyb pro vylepšení zabezpečení

### Novinky v dokumentaci Intune – září 2015
**Nová témata**

|Název|Podrobnosti|
|----|--------|
|[Nastavení zásad konfigurace Windows 10 v Microsoft Intune](https://technet.microsoft.com/library/mt404697.aspx)|Toto je nová zásada konfigurace, která umožňuje spravovat nastavení a funkce v zařízeních se systémy Windows 10 a Windows 10 Mobile.
| [Konfigurace aplikací pomocí zásad konfigurace mobilních aplikací v Microsoft Intune](https://technet.microsoft.com/library/mt481447.aspx)|Jedná se o nový typ zásady umožňující automaticky poskytovat zásady, které se můžou požadovat, když uživatel spustí aplikaci pro iOS. |

**Aktualizovaná témata**

|Název|Podrobnosti|
|----|-------|
|[Použití zásad ke správě počítačů a mobilních zařízení s Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)|Došlo k přidání nejnovějších informací, které vám pomůžou pochopit a vytvářet zásady.|

## Srpen 2015
### Aktualizace správy mobilních zařízení a aplikací
* **Podmínky a ujednání** pro registraci v rámci služby Intune a přístup společnosti [jsou teď spravované pomocí zásad](https://technet.microsoft.com/library/mt405893.aspx). Můžete zacílit různé sady podmínek a ujednání, které budou odpovídat požadavkům konkrétní skupiny uživatelů. Například můžete nasadit podmínky a ujednání v různých jazycích pro geograficky vymezené uživatelské skupiny. Můžete také [upravit podmínky a ujednání](https://technet.microsoft.com/library/mt405893.aspx#BKMK_TCVers) a rozhodnout, jestli se má zvýšit číslo verze, a vyžádat si souhlas uživatelů s novými podmínkami a ujednáními před použitím portálu společnosti.
* **Řada zásad Intune byla přejmenovaná** , aby byly víc konzistentní v rámci celého produktu a snáz se vyhledávaly. Seznam všech dostupných zásad služby Intune najdete v tématu [Používání zásad ke správě počítačů a mobilních zařízení pomocí Microsoft Intune](https://technet.microsoft.com/library/dn743712.aspx)..
* **Profily certifikátů PKCS #12 (.PFX)** jsou dostupné pro Android 4.0 nebo novější a pro Windows 10 (ve verzi pro stolní počítače i mobilní zařízení) a novější. Použití .PFX nevyžaduje server NDES. V tématu [Povolení přístupu k firemním prostředkům pomocí profilů certifikátů v Microsoft Intune](http://technet.microsoft.com/library/dn818904.aspx) se naučíte používat profily certifikátů .PFX.
* **Nastavení hranic podnikové sítě pro stolní počítače a mobilní zařízení s Windows 10** umožňuje podrobné nastavení sítě VPN, jak se píše v tématu [Pomoc uživatelům s připojením k práci pomocí profilů sítě VPN v Microsoft Intune](https://technet.microsoft.com/library/dn818905.aspx).
* **Aplikace OneDrive pro Android nově podporuje víc identit**. Tato a další aktualizace zásad správy mobilních aplikací jsou popsané [v seznamu aplikací Microsoftu, které můžete spravovat](https://technet.microsoft.com/library/dn708489.aspx)..
* **Vyřazení zámku aktivace na zařízeních iOS**. Pokud je zařízení s iOS, které je majetkem společnosti, chráněné tzv. zámkem aktivace, musíte před vymazáním a opětovnou aktivací zařízení zadat Apple ID a heslo uživatele. To může být problém, pokud již uživatel ze společnosti odešel a vrátil zařízení vlastněné společností, aniž by zámek aktivace vypnul. Problém můžete vyřešit tak, že použijete funkci [Vynechat zámek aktivace služby Intune](https://technet.microsoft.com/library/mt414176.aspx).

### Podmíněný přístup pro osobní počítače
Nově můžete konfigurovat zásady podmíněného přístupu pro osobní počítače. To umožňuje desktopovým aplikacím Office přístup k online službám Exchange Online a SharePointu.
Pokud chcete povolit zásady podmíněného přístupu pro osobní počítače, počítač musí být buď připojený k doméně, nebo splňovat předpisy.
* V části **Začínáme** v tématu [Správa přístupu k e-mailu a službě SharePoint v Microsoft Intune](http://technet.microsoft.com/library/dn818907).aspx) najdete úplný seznam požadavků na povolení podmíněného přístupu pro počítače.
* Podmínky, které můžete nastavit pro povolení podmíněného přístupu pro přístup k e-mailu, najdete v tématu [Správa přístupu k e-mailu v Microsoft Intune](https://technet.microsoft.com/library/dn705841.aspx).
* Možnosti, které můžete nastavit pro povolení podmíněného přístupu do služby SharePoint Online, najdete v tématu [Správa přístupu ke službě SharePoint Online v Microsoft Intune](https://technet.microsoft.com/library/dn705844.aspx).

### Změny a aktualizace aplikací portálů společnosti Microsoft
V této verzi se provedly následující změny aplikací portálu společnosti:

**Android**

Uživatelům se teď po přihlášení zobrazí pokyny k registraci zařízení, pokud zařízení ještě nezaregistrovali pro správu.

### Novinky v dokumentaci Intune – srpen 2015
**Nová témata**

|Název|Podrobnosti|
|-----|-------|
|[Pomoc při ochraně zařízení s iOS pomocí funkce Vynechat zámek aktivace pro Microsoft Intune](https://technet.microsoft.com/library/mt414176.aspx)|Zjistěte, jak se pomocí Intune dá obejít na zařízeních iOS Zámek aktivace v případě, kdy uživatel odejde od společnosti a vrátí zařízení uzamčené.|

**Aktualizovaná témata**

|Název|Podrobnosti|
|-----|-------|
|[Aplikace Microsoftu, které můžete použít se zásadami správy mobilních aplikací služby Microsoft Intune](https://technet.microsoft.com/library/dn708489.aspx)|Doplněné o nejnovější informace o aplikacích, které můžete spravovat pomocí zásad správy mobilních aplikací.
|[Použití zásad ke správě počítačů a mobilních zařízení s Microsoft Intune](http://technet.microsoft.com/library/dn743712.aspx)|Aktualizované o nejnovější zásady přidané do služby Intune.|
<!---
## July 2015
July updates for Intune are limited to behind-the-scenes enhancements that allow us to continue providing you with a high-quality service experience. New features are not included in this service update.

### Intune Onboarding benefit
Microsoft offers the Intune Onboarding benefit for eligible plans. The Onboarding benefit lets you work remotely with Microsoft specialists to get your Intune environment ready for use. For more information, see [Microsoft Intune Onboarding benefit description](https://technet.microsoft.com/library/mt228266.aspx)
### Changes and updates to Microsoft Company Portal apps
The following changes have been made to the company portal apps in this release.

**Android**

Microsoft automatically collects anonymous data about the performance and use of the company portal to improve Microsoft products and services. End users can turn off data collection by using the Usage Data setting on their device, but administrators have no control over the data collection and cannot change the end user’s selection for this setting.--->


<!--HONumber=May16_HO1-->


