---
title: "Popis služby | Dokumentace Microsoftu"
description: "Intune je cloudová služba, která pomáhá spravovat zařízení s Windows, iOS, Mac OS X, Androidem a Windows Mobile."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 09/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40fa5a2e-6c0f-4150-9740-d5ddc0cdbda0
ms.reviewer: cacamp
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: f268cf29461447306d0f5c3ca06d541d9a03a49d
ms.openlocfilehash: 8e8257a426bd6b9a99e21e928b08c84f162d5da3


---

# <a name="microsoft-intune-service-description"></a>Popis služby Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Microsoft Intune je cloudová služba, která pomáhá spravovat zařízení s Windows, Mac OS X, iOS, Androidem a Windows Mobile. Intune také pomáhá chránit podnikové aplikace a data. Intune můžete používat samostatně, nebo integrovat se System Center Configuration Managerem, abyste získali další možnosti správy.

Microsoft nabízí pro Intune adaptační benefity pro příslušné služby v rámci příslušných plánů. Adaptační benefity vám umožní vzdáleně pracovat s odborníky Microsoftu na přípravě vašeho prostředí Intune k použití. Další informace o adaptačních benefitech najdete v tématu [Popis adaptačních benefitů pro Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=619281).

Můžete začít používat 30denní bezplatnou zkušební verzi Intune, která zahrnuje 100 uživatelských licencí. Jestli chcete začít používat bezplatnou zkušební verzi, [přejděte na registrační stránku Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/). Jestli má organizace uzavřenou smlouvu Enterprise nebo jinou rovnocennou multilicenční smlouvu, požádejte o nastavení bezplatné zkušební verze zástupce Microsoftu.

> [!NOTE]
> Pokud má vaše organizace pracovní nebo školní účet služeb Microsoft Online Services a po skončení zkušební doby budete chtít toto předplatné Intune používat v produkčním prostředí, vyberte na této stránce možnost **Přihlásit se** a přihlaste se pod účtem globálního správce organizace. Tím zajistíte, že se zkušební verze Intune propojí s vaším stávajícím pracovním nebo školním účtem.

Seznam konfigurovatelných nastavení mobilních zařízení je tady:

-   [Možnosti správy zaregistrovaných zařízení v Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune)

-   [Hybridní správa mobilních zařízení (MDM) s nástrojem System Center Configuration Manager a Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx)

Další informace o System Center Configuration Manageru najdete v tématu [Dokumentace pro nástroj System Center Configuration Manager](https://technet.microsoft.com/library/mt346023.aspx).

## <a name="learn-how-intune-service-updates-affect-you"></a>Vysvětlení vlivu aktualizací služby Intune
Intune je online služba, a proto ji společnost Microsoft může pravidelně aktualizovat.

Informace v tomto článku vám pomůžou dozvědět se o četnosti těchto aktualizací služby a předběžných oznámeních, která od nás dostanete v případě, že by mohla mít některá aktualizace vliv na použití služby.

Informace o změnách ve službě Intune najdete v tématu [Co je nového v Microsoft Intune](/intune/deploy-use/whats-new-in-microsoft-intune). Změny ve službě se probírají také na [blogu Microsoft Intune](http://blogs.technet.com/b/microsoftintune/). Najdete tam i užitečné tipy, jak Intune využívat na maximum.

O důležitých aktualizacích softwaru se také dozvíte prostřednictvím centra zpráv na [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx). Pokud si nainstalujete doprovodnou [mobilní aplikaci pro správu Office 365](https://support.office.com/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a), můžete přijímat oznámení na svém mobilním zařízení.

> [!NOTE]
> Stav služby Intune je možné monitorovat na [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx). Zvolte **Stav služby** v levém podokně.  

Toto jsou typy oznámení, které společnost Microsoft o službě Intune poskytuje:
-   Abychom vám pomohli připravit se na změny služby, upozorníme vás minimálně 30–90 dní před upgradem služby (v závislosti na závažnosti dopadu změn). Oznámení proběhne prostřednictvím komunikačních kanálů v produktu, jako jsou výstrahy na vývěsce. Tyto změny mohou zahrnovat:
    * Aktualizace s možným dopadem na dodržování předpisů nebo zákonných požadavků
    * Změny činnosti koncového uživatele, uživatelského rozhraní a pracovních postupů
    * Nové nebo změněné rozhraní API – upozornění, že je potřeba provést testování, aby se zajistila zpětná kompatibilita vlastních aplikací
    * Změny požadavků na systém, například minimální požadované verze prohlížeče
    * Aktualizace, které od vás vyžadují zásah, abyste funkci povolili nebo zabránili přerušení služby
-   Microsoft poskytuje informace o nových funkcích a vylepšeních stávajících funkcí jako součást měsíční aktualizace služeb. Obecně platí, že Microsoft vydává aktualizace služeb zhruba v půlce měsíce. Aktualizace jsou popsané v tématu [Co je nového v Microsoft Intune](/intune/deploy-use/whats-new-in-microsoft-intune).
    -   V případě vyřazení služby Intune byste dostali upozornění 12 měsíců předem.

## <a name="choose-the-management-solution-thats-right-for-you"></a>Výběr správného řešení pro správu
Intune můžete pro účely správy a ochrany firemních mobilních zařízení a počítačů (v tomto článku označovaných jako **zařízení**) nastavit různými způsoby.

-**Samostatná konfigurace Intune.** Ke správě zařízení organizace v Intune se používá webová konzola pro správu. Intune můžete používat i bez místní infrastruktury IT. Když Intune používáte se službou Active Directory Domain Services, můžete v Intune použít doménové uživatelské účty spravované ve službě Domain Services.

-**Intune se System Center Configuration Managerem.** Ke správě počítačů a mobilních zařízení organizace se používá konzola pro správu Configuration Manageru. Při této konfiguraci můžete ke správě všech zařízení organizace používat jedinou konzolu správce Configuration Manageru. Configuration Manager podporuje velké počty mobilních zařízení, serverů a počítačů. Další informace o Configuration Manageru najdete v tématu [Hybridní správa mobilních zařízení (MDM) s nástrojem System Center Configuration Manager a Microsoft Intune](https://technet.microsoft.com/library/mt627883.aspx). Další pomoc při rozhodování o tom, jaký přístup je pro vás správný, najdete v tématu [Volba mezi samostatnou a hybridní správou mobilních zařízení v Microsoft Intune s nástrojem Configuration Manager](https://technet.microsoft.com/en-us/library/mt706478.aspx).


## <a name="learn-more-about-intune"></a>Další informace o Intune
Další informace o službě Intune můžete získat z těchto zdrojů:

- [Centrum zabezpečení pro Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/intune-trust-center/) poskytuje informace o zabezpečení, ochraně osobních údajů a dodržování předpisů v Intune a obsahuje také popis některých certifikátů Intune.

- [Možnosti správy zaregistrovaných zařízení v Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune)

### <a name="see-also"></a>Viz taky
[Microsoft Intune](https://docs.microsoft.com/intune/)
[Knihovna dokumentace k System Center 2012 Configuration Manageru](https://technet.microsoft.com/library/gg682041.aspx)

[Co je nového v Microsoft Intune](/intune/deploy-use/whats-new-in-microsoft-intune)



<!--HONumber=Dec16_HO3-->


