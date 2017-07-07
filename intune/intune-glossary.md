---
title: "Glosář služby Intune"
titleSuffix: Intune on Azure
description: "Přečtěte si něco o terminologii používané v Microsoft Intune."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd7b5613-ee9f-4dc3-990c-ab4c1d40720d
ms.custom: intune-azure
ms.openlocfilehash: a9b43fc1a1877a3fc8bf4c5ee00e02dfee3cdea8
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="microsoft-intune-glossary"></a>Glosář Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="a"></a>A

|||
|-|-|
|přiřazení aplikací|Umožňuje uživatelům [vyhledat, stáhnout a nainstalovat](/intune/app-management) aplikace, které potřebují. Toto se dřív označovalo jako *nasazení aplikací*.|
|konfigurační profil aplikace|Nakonfiguruje konkrétní nastavení aplikace pro [iOS](/intune/app-configuration-policies-use-ios) nebo [Android](/intune/app-configuration-policies-use-android) před jejím spuštěním.|
|monitorování aplikace|Umožňuje [zobrazit poslední stav a aktivitu](/intune/apps-monitor) související s přiřazením aplikace.|
|úloha odebrání dat ochrany aplikace|[Odebere data aplikace](/intune/app-protection-policies) ze zařízení uživatele.|
|zásady ochrany aplikací|Zajišťují, aby aplikace uživatele odpovídaly [firemním zásadám ochrany dat](/intune/app-protection-policies).|
|App SDK (sada)|Sada [Microsoft Intune App SDK](/intune/app-sdk) vám umožní do vámi vytvářených aplikací přidat funkce, díky kterým bude tyto aplikace možné spravovat prostřednictvím zásad ochrany aplikací v Intune.|
|akce odinstalace aplikace|Umožňuje [odinstalovat aplikace](/intune/apps-deploy) ze zařízení uživatele.|
|App Wrapping Tool|[Aplikace příkazového řádku](/intune/apps-prepare-mobile-application-management), která vytvoří kolem obchodní aplikace obálku. Tato obálka potom umožní správu aplikace pomocí zásad ochrany aplikací v Intune.|
|akce přiřazení|Volba, kterou provádíte při [přiřazení aplikace](/intune/apps-deploy). Můžete zvolit, jestli bude instalace aplikace povinná (požadovaná), volitelná (dostupná), nebo jestli se aplikace odinstaluje.|
|dostupná instalace|Když přiřadíte aplikaci s touto akcí, aplikace se zobrazí na podnikovém portálu a uživatelé ji můžou [instalovat na vyžádání](/intune/apps-deploy).|
|Azure Portal|Nová konzola pro Intune. [Další informace](/intune/what-is-intune).|

## <a name="b"></a>B
|||
|-|-|
|uživatelé s vlastním zařízením (BYOD)|Anglický akronym je z [Bring Your Own Device](/intune/device-enrollment). Uživatelé si mohou nainstalovat aplikaci Portál společnosti služby Intune na své vlastní zařízení a potom své zařízení zaregistrovat. Tím získají přístup k prostředkům společnosti, jako jsou e-mail, firemní aplikace, firemní data a podpora.|

## <a name="c"></a>C
|||
|-|-|
|profil certifikátu|Tento typ zásad slouží k [zabezpečení přístupu k prostředkům společnosti](/intune/certificates-configure) pomocí certifikátů při používání profilů pro Wi-Fi, e-mail nebo VPN.|
|zařízení vlastněná společností (COD)|Anglický akronym je z [Company Owned Devices](/intune/device-enrollment). Tato zařízení je možné registrovat několika různými způsoby v závislosti na potřebách organizace a typech spravovaných zařízení.|
|Portál společnosti|Aplikace nebo web, který poskytují uživatelům [přístup k firemním datům a aplikacím](/intune/company-portal-customize).|
|zásady dodržování předpisů|Tyto zásady zajišťují, že zařízení [dodržují určitá pravidla](/intune/device-compliance), například že přístup k zařízení je chráněný kódem PIN a data ukládaná do zařízení jsou šifrována.|
|Kompatibilní a nekompatibilní aplikace|Součást [profilu omezení zařízení](/intune/device-restrictions-configure). Tato nastavení umožňují definovat seznam aplikací, které uživatelé můžou nebo nemůžou spustit. Intune vás pak prostřednictvím sestav informuje, když byla nějaká nekompatibilní aplikace nainstalována nebo spuštěna. Pro některé platformy může Intune i zablokovat instalaci nekompatibilní aplikace.|
|podmíněný přístup|[Povoluje přístup k e-mailu společnosti, Office 365 a dalším službám](/intune/conditional-access) pouze ze zařízení, která splňují vámi nastavená pravidla.|
|vlastní zásady|[Tyto zásady použijete](/intune/custom-settings-configure), když obecné zásady konfigurace neobsahují vestavěná nastavení, která byste potřebovali. Vlastní zásady je možné použít k vytvoření nastavení jinými způsoby (Apple Configurator nebo OMA-URI).|

## <a name="d"></a>D
|||
|-|-|
|nasazení|Odeslání aplikace nebo zásady do zařízení nebo na uživatele, které spravujete. Tato akce se teď označuje jako *přiřazení*.|
|správce registrace zařízení|Organizace můžou pomocí Intune spravovat velké počty mobilních zařízení s jediným uživatelským účtem. Účet [správce registrace zařízení ](/intune/device-enrollment-program-enroll-ios) (DEM – Device Enrollment Manager) je speciální účet Intune, který může zaregistrovat až 1 000 zařízení.|
|profily zařízení|[Tyto profily](/intune/device-profile-create) umožňují na spravovaná zařízení nakonfigurovat široký rozsah zabezpečení, funkcí a nastavení přístupu.|

## <a name="e"></a>E
|||
|-|-|
|e-mailový profil|Tyto zásady lze použít ke konfiguraci [nastavení přístupu k e-mailu](/intune/email-settings-configure) na mobilních zařízeních. Minimalizují se tak nároky na nastavení, která musí provést koncový uživatel.|
|EMS|Microsoft Enterprise Mobility + Security (dříve Enterprise Mobility Suite) chrání vaše podniková data, a přitom vašim uživatelům umožňuje [přístup k aplikacím a obsahu, který potřebují](https://www.microsoft.com/cloud-platform/enterprise-mobility).|
|koncový uživatel|[Uživatelé zařízení (jako jsou telefony nebo počítače)](/intune/end-user-educate) spravovaných pomocí Intune|
|registrace|Microsoft Intune využívá [registraci](/intune/device-enrollment) k začlenění zařízení do správy a povolení přístupu k prostředkům.|

## <a name="f"></a>F
|||
|-|-|
|FastTrack|[Služba společnosti Microsoft](https://technet.microsoft.com/library/mt228265.aspx) pro uživatele Intune se 150 licencemi v plánu splňujícím podmínky. V rámci této služby vám specialisté od Microsoftu můžou pomoct s nastavením a zprovozněním služby Intune.|

## <a name="g"></a>G
|||
|-|-|
|skupiny|Skupiny vám umožňují [logicky seskupit uživatele nebo zařízení](/intune/groups-get-started). Můžete například vytvořit skupinu všech počítačů s Windows. Těmto skupinám je pak možné přiřazovat aplikace a profily.|

## <a name="h"></a>H
|||
|-|-|
|hybridní|Konfigurace, kdy můžete spravovat zařízení registrovaná do Intune prostřednictvím konzoly System Center Configuration Manager.|

## <a name="i"></a>I
|||
|-|-|
|portál Intune|Portál Azure Portal, který používáte k většině operací správy Intune.|
|softwarový klient Intune|Alternativní způsob [správy některých počítačů s Windows](/intune-classic/get-started/choose-how-to-manage-devices), který vám pomůže zvolit vhodnou metodu|
|Intune Software Publisher|Nástroj k [definování aplikací, které chcete nasadit, a jejich nahrání do cloudového úložiště](/intune-classic/deploy-use/add-apps)|
|inventář|Slouží k zobrazení [hardwaru a nainstalovaného softwaru](/intune/device-inventory) v zařízeních, která spravujete.|

## <a name="k"></a>K
|||
|-|-|
|Celoobrazovkový režim|Tento režim se konfiguruje v rámci [profilu omezení zařízení](/intune/device-restrictions-configure) a umožňuje uzamknout zařízení jen pro určitý účel. Můžete například zařízení v prodejně nakonfigurovat tak, aby na něm běžely jen některé aplikace.|

## <a name="m"></a>M
|||
|-|-|
|spravovaný prohlížeč|[Aplikace na procházení webu](/intune/app-configuration-managed-browser), kterou můžete přiřadit v organizaci pomocí Intune. Zásady spravovaného prohlížeče konfigurují seznam povolených nebo blokovaných webů. Tyto seznamy omezují weby, které můžou uživatelé spravovaného prohlížeče navštívit.|
|autorita pro správu mobilních zařízení (MDM)|[Autorita MDM](/intune/mdm-authority-set) definuje službu správy s oprávněním ke správě určité sady zařízení. Příklady možných autorit MDM zahrnují Intune samostatně a Configuration Manager s Intune.|
|zásady konfigurace mobilních aplikací|Zásady pro [iOS](/intune/app-configuration-policies-use-ios) nebo [Android](/intune/app-configuration-policies-use-android), které slouží k předávání nastavení do kompatibilních aplikací při jejich spuštění – například mohou dodávat název společnosti nebo serverovou adresu.|
|Zásady zřizování mobilních aplikací|Zásady pro iOS, které pomáhají zajistit, že [zřizovacím profilům](/intune/app-provisioning-profile-ios) aplikací pro iOS, které přiřadíte, nevyprší platnost.|
|Správa mobilních aplikací|[Správa mobilních aplikací (MAM)](/intune/app-lifecycle) umožňuje publikovat, doručovat, konfigurovat, zabezpečovat, monitorovat a aktualizovat mobilní aplikace pro uživatele.
|Správa mobilních zařízení|[Správa mobilních zařízení (MDM)](/intune/device-lifecycle) umožňuje registrovat zařízení do Intune, takže můžete tato zařízení zřizovat, konfigurovat, monitorovat a spravovat.



## <a name="o"></a>O
|||
|-|-|
|OMA-DM|Open Mobile Alliance Device Management. Oborový standard, protokol správy zařízení používaný řadou výrobců hardwaru. Umožňuje ovládat určité funkce mobilních zařízení a počítačů.|
|OMA-URI|Open Mobile Alliance Uniform Resource Identifier. Tyto položky identifikují jednotlivá nastavení v zařízeních, která se řídí standardem OMA-DM. Tato nastavení je možné použít ve [vlastních profilech Intune](/intune/custom-settings-configure), když není k dispozici vestavěné nastavení, které byste právě potřebovali.|

## <a name="p"></a>P
|||
|-|-|
|resetování hesla|Funkce služby Intune, která na podporovaných zařízeních umožňuje vynutit, aby si koncoví uživatelé [resetovali heslo](/intune/device-passcode-reset).|

## <a name="r"></a>R
|||
|-|-|
|vzdálené uzamčení|Funkce služby Intune, která vám umožňuje [uzamknout podporovaná zařízení](/intune/device-remote-lock), i když dané zařízení právě nemáte k dispozici.|
|povinná instalace|Když přiřadíte aplikaci s touto akcí, nevyžaduje se k dokončení instalace žádný [zásah uživatele](/intune/apps-deploy). Na některých platformách je možné, že koncový uživatel musí tuto instalaci potvrdit.|


## <a name="s"></a>S
|||
|-|-|
|selektivní vymazání|[Selektivní vymazání](/intune/device-company-data-remove) odebere ze zařízení jenom firemní data, včetně případných dat správy mobilních aplikací (MAM), nastavení a e-mailových profilů. Při selektivním vymazání se osobní údaje uživatele na zařízení ponechají.|
|Zkušební načtení před prodejem|Akce instalace obchodní aplikace, aniž by k ní byl přístup v App Storu.|
|Předplatné|Zadaná smlouva, která vám umožňuje přístup ke klientovi Intune.|

## <a name="t"></a>T
|||
|-|-|
|TeamViewer|Aplikace třetí strany, která funguje s Intune a poskytuje [možnosti vzdálené pomoci](/intune/device-profile-android-teamviewer) pro zařízení s Androidem, které spravujete přes Intune.|
|Klient|Jedna instance služby Intune, ke které můžete přistupovat díky předplatnému.|
|podmínky a ujednání|Typ zásad, které se přiřazují uživatelům. Obsahují informace, které uživatelé musí [přečíst a přijmout](/intune/terms-and-conditions-create) předtím, než budou moct používat Portál společnosti k registraci a přístupu ke své práci.|

## <a name="v"></a>V
|||
|-|-|
|hromadně zakoupené aplikace a knihy|Některé App Story umožňují zakoupit více licencí pro aplikace nebo knihy, které chcete používat ve vaší společnosti. Intune vám pomůže spravovat aplikace a knihy, které jste [zakoupili prostřednictvím takového programu](/intune/vpp-apps). Můžete importovat licenční informace z App Storu, sledovat, kolik licencí jste už použili, a zabraňovat v instalaci více kopií aplikace, než na kolik máte licence.|
|profil VPN|Zásady, které přiřazují [nastavení VPN](/intune/vpn-settings-configure) do vámi spravovaných zařízení. Minimalizují se tak nároky na nastavení, která musí provést koncový uživatel.|

## <a name="w"></a>W
|||
|-|-|
|Wi-Fi profil|Zásady, které přiřazují [nastavení bezdrátové sítě](/intune/wi-fi-settings-configure) do zařízení. Uživatelé se tak můžou připojovat k podnikové síti, aniž by museli znát a konfigurovat nějaká nastavení.