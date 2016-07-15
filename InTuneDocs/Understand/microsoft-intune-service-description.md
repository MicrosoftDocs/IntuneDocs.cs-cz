---
title: "Popis služby | Microsoft Intune"
description: 
keywords: 
author: Nbigman
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40fa5a2e-6c0f-4150-9740-d5ddc0cdbda0
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 4794a22b3bdd1f28e6951b81e8379dc208fffc89
ms.openlocfilehash: 6cab0bacd9157323e342662609de8c9f20550d78


---

# Popis služby Microsoft Intune

Microsoft Intune je cloudová služba, která pomáhá spravovat počítače se systémem Windows a mobilní zařízení se systémy iOS, Android a Windows. Intune také pomáhá chránit podnikové aplikace a data. Službu Intune můžete používat samostatně, nebo ji integrovat s nástrojem System Center 2012 R2 Configuration Manager, abyste získali další možnosti správy.

Microsoft nabízí pro Intune adaptační benefity pro příslušné služby v rámci příslušných plánů. Adaptační benefity vám umožní vzdáleně pracovat s odborníky Microsoftu na přípravě vašeho prostředí Intune k použití. Další informace najdete v tématu [Popis adaptačních benefitů pro Microsoft Intune](http://go.microsoft.com/fwlink/?LinkId=619281).

Můžete začít používat 30denní bezplatnou zkušební verzi Intune, která zahrnuje 100 uživatelských licencí. Jestli chcete začít používat bezplatnou zkušební verzi, [kliknutím sem navštivte registrační stránku Intune](http://www.microsoft.com/en-us/server-cloud/products/microsoft-intune/). Jestli má organizace uzavřenou smlouvu Enterprise nebo jinou rovnocennou multilicenční smlouvu, požádejte o nastavení bezplatné zkušební verze zástupce Microsoftu.

> [!NOTE]
> Pokud vaše organizace má pracovní nebo školní účet služeb Microsoft Online Services a po skončení zkušební doby budete chtít toto předplatné Intune používat v ostrém provozu, klikněte na této stránce na možnost **Přihlásit se** a přihlaste se pod účtem globálního správce organizace. Tím zajistíte, že se zkušební verze Intune propojí s vaším stávajícím pracovním nebo školním účtem.

Seznam konfigurovatelných nastavení mobilních zařízení je tady:

-   [Možnosti správy mobilních zařízení v Microsoft Intune](/intune/get-started/mobile-device-management-capabilities-in-microsoft-intune)

-   [Obecná nastavení pro mobilní zařízení v nástroji Configuration Manager](https://technet.microsoft.com/en-us/library/dn376523.aspx)

Informace o System Center 2012 R2 Configuration Manageru najdete v tématu [Knihovna dokumentace pro System Center 2012 Configuration Manager](https://technet.microsoft.com/library/gg682041.aspx).

## Vysvětlení vlivu aktualizací služby Intune
Intune je online služba, a proto ji společnost Microsoft může pravidelně aktualizovat.

Informace v tomto tématu vám pomůžou pochopit četnost těchto aktualizací služby a předběžná oznámení, která od nás dostanete v případě, že by mohla mít některá aktualizace vliv na použití služby.

Informace o změnách ve službě Intune najdete v tématu [Co je nového v Microsoft Intune](/intune/deploy-use/Whats-new-in-microsoft-intune.md). Změny ve službě se probírají také na [blogu Microsoft Intune](http://blogs.technet.com/b/microsoftintune/). Najdete tam i užitečné tipy, jak využívat Intune na maximum.

O důležitých aktualizacích softwaru se také dozvíte prostřednictvím centra zpráv na [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx). Pokud si nainstalujete doprovodnou [mobilní aplikaci pro správu Office 365](https://support.office.com/en-us/article/Office-365-Admin-Mobile-App-e16f6421-2a1a-4142-bf9d-9846600a060a), můžete dostat oznámení na svém mobilním zařízení.

> [!NOTE] Stav služby Intune je možné monitorovat na [portálu pro správu Office 365](https://portal.office.com/Admin/Default.aspx). Zvolte **Stav služby** v levém podokně.  

Toto jsou typy oznámení, které společnost Microsoft o službě Intune poskytuje:
-   Abychom vám pomohli připravit se na změny služby, upozorníme vás minimálně 30–90 dní před upgradem služby, v závislosti na závažnosti dopadu změn. Oznámení proběhne prostřednictvím komunikačních kanálů v produktu, jako jsou výstrahy na vývěsce. Tyto změny mohou zahrnovat:
* Aktualizace s možným dopadem na dodržování předpisů nebo zákonných požadavků
* Změny činnosti koncového uživatele, uživatelského rozhraní a pracovních postupů
* Nové nebo změněné rozhraní API – upozornění, že je potřeba provést testování, aby se zajistila zpětná kompatibilita vlastních aplikací
* Změny požadavků na systém, například minimální požadované verze prohlížeče
* Aktualizace, které od vás vyžadují zásah, abyste funkci povolili nebo zabránili přerušení služby
-   Microsoft poskytuje informace o nových funkcích a vylepšeních stávajících funkcí jako součást měsíční aktualizace služeb. Obecně platí, že Microsoft vydává aktualizace služeb zhruba v půlce měsíce. Aktualizace jsou popsané v tématu [Co je nového v Microsoft Intune](/intune/deploy-use/whats-new-in-microsoft-intune).
-   V případě vyřazení služby Intune byste dostali upozornění 12 měsíců předem.

## Výběr správného řešení pro správu
Službu Intune můžete pro účely správy a ochrany firemních mobilních zařízení a počítačů (v tomto dokumentu označovaných jako **zařízení**) nakonfigurovat různými způsoby.

-   **Samostatná konfigurace Intune.** Ke správě zařízení organizace v Intune se používá webová konzola pro správu. Intune můžete použít i bez místní infrastruktury IT, ale když Intune použijete se službou Active Directory Domain Services, můžete v Intune použít doménové uživatelské účty spravované ve službě Domain Services.

-   **Intune s nástrojem System Center Configuration Manager.** Ke správě počítačů a mobilních zařízení organizace se používá konzola pro správu Configuration Manageru. Při této konfiguraci můžete ke správě všech zařízení organizace používat jedinou konzolu správce Configuration Manageru. Configuration Manager podporuje velké počty mobilních zařízení, serverů a počítačů. Další informace najdete v tématu [Správa mobilních zařízení pomocí Configuration Manageru a Microsoft Intune](http://go.microsoft.com/fwlink/?LinkID=271118) v [knihovně dokumentace k System Center 2012 Configuration Manageru](https://technet.microsoft.com/library/gg682041.aspx).  Další pomoc při rozhodování o tom, jaký přístup je pro vás správný, najdete v tématu [Volba mezi samostatnou a hybridní správou mobilních zařízení v Microsoft Intune s nástrojem Configuration Manager](https://technet.microsoft.com/en-us/library/mt706478.aspx).


## Další informace o Intune
Další informace o službě Intune můžete získat z těchto zdrojů:

-   [Centrum zabezpečení pro Microsoft Intune](http://www.microsoft.com/en-us/server-cloud/products/intune-trust-center/) poskytuje informace o zabezpečení, ochraně osobních údajů a dodržování předpisů ve službě Intune a obsahuje také popis některých certifikátů služby Intune.

-   [Možnosti správy mobilních zařízení v Microsoft Intune](/intune/understand-explore/mobile-device-management-capabilities-in-microsoft-intune)

### Související témata
[Microsoft Intune](https://docs.microsoft.com/intune/)
[Knihovna dokumentace k System Center 2012 Configuration Manageru](https://technet.microsoft.com/library/gg682041.aspx)

[Co je nového v Microsoft Intune](/intune/deploy-use/whats-new-in-microsoft-intune)



<!--HONumber=Jun16_HO5-->


