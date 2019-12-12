---
title: Konfigurace S/MIME pomocí Outlooku pro iOS v Microsoft Intune
description: Principy S/MIME s Outlookem pro iOS v Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 11/21/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: apps
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: lance
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: c9572f4accb1be232d4667d99b98beff90d81379
ms.sourcegitcommit: edd06a494a241d198ca9b0d3030c92195976e0d3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/11/2019
ms.locfileid: "75000410"
---
# <a name="configure-smime-with-outlook-for-ios"></a>Konfigurace S/MIME pomocí Outlooku pro iOS

Standard S/MIME (Secure/Multipurpose Internet Mail Extensions) poskytuje úroveň zabezpečení pro odesílání e-mailů z účtu Exchange ActiveSync (EAS) a z něj. [Aplikace Microsoft Outlook](https://aka.ms/omsmime) může využívat S/MIME k šifrování odchozích zpráv i příloh, aby bylo zajištěno, že při použití účtů Office 365 může číst a přistupovat k obsahu zpráv pouze zamýšlený příjemce. Uživatelé můžou také digitálně podepsat zprávu, která příjemcům umožňuje ověřit identitu odesilatele a potvrdit, že zpráva nebyla úmyslně poškozena. Tato funkce je možná díky využití certifikátů. Další informace najdete v tématu [porozumění S/MIME](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65)?redirectedfrom=MSDN).

> [!NOTE]
> Tato funkce byla zpožděna, ale brzy bude vydána.

> [!NOTE]
> Toto téma popisuje způsob nasazení důvěryhodných kořenových certifikátů přes [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431). Microsoft Endpoint Manager je jediná integrovaná platforma pro správu koncových bodů pro správu všech vašich koncových bodů. Toto centrum pro správu Microsoft Endpoint Manageru integruje nástroj ConfigMgr a Microsoft Intune.

## <a name="about-message-encryption"></a>Šifrování zpráv
Uživatelé můžou poslat šifrovanou zprávu lidem v jejich organizaci a lidem mimo svou organizaci, pokud mají veřejnou část šifrovacích certifikátů. Privátní klíče přidružené k šifrovacím certifikátům by měly být vždy chráněné a zabezpečené příjemcem zašifrované zprávy. Privátní klíč šifrovacího certifikátu slouží k dešifrování zprávy příjemcem.

Šifrované zprávy můžou číst jenom příjemci, kteří mají certifikát odpovídající zašifrované zprávě. Pokud se pokusíte odeslat šifrovanou zprávu příjemcům, jejichž šifrovací certifikát není k dispozici, aplikace vás vyzve k odebrání těchto příjemců před odesláním e-mailu.

## <a name="about-digital-signatures"></a>O digitálních podpisech
Digitálně podepsaná zpráva přeručí příjemce, že zpráva nebyla zfalšována a totožnost odesílatele je platná. Příjemci můžou digitální podpis ověřit jenom v případě, že používají e-mailového klienta, který podporuje S/MIME.

## <a name="prerequisites"></a>Požadované součásti
- Outlook pro iOS podporuje jenom S/MIME na účtech Office 365.
- Pro Office 365 musí být nakonfigurovaná přípona S/MIME. Další informace najdete v tématu [Postup konfigurace S/MIME v sadě Office 365](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/How-to-Configure-S-MIME-in-Office-365/ba-p/584516).
- Musíte mít certifikační autoritu, která může vystavovat certifikáty, které se dají použít k podepisování a šifrování.
- Nasazení důvěryhodných kořenových certifikátů prostřednictvím Správce koncových bodů. Další informace najdete v tématu [vytváření profilů důvěryhodných certifikátů](~/protect/certificates-configure.md#create-trusted-certificate-profiles).
- Šifrovací certifikáty se musí importovat do správce koncových bodů. Další informace najdete v tématu [Konfigurace a používání importovaných certifikátů PKCS pomocí Intune](~/protect/certificates-imported-pfx-configure.md).
- Nainstalujte a nakonfigurujte konektor PFX pro Microsoft Intune. Další informace najdete v tématech [stažení, instalace a konfigurace Certificate Connectoru PFX pro Microsoft Intune](~/protect/certificates-imported-pfx-configure.md#download-install-and-configure-the-pfx-certificate-connector-for-microsoft-intune).
- Zařízení musí být zaregistrovaná v MDM pro příjem důvěryhodných kořenových certifikátů a certifikátů S/MIME z správce koncových bodů.

> [!IMPORTANT]
> Aktualizovaný konektor PFX (verze 6.1911.11.0 nebo novější) je nutné stáhnout a nainstalovat, aby Microsoft Intune používal certifikáty šifrování S/MIME v aplikaci Outlook pro iOS.

## <a name="smime-support-in-outlook-for-ios"></a>Podpora S/MIME v Outlooku pro iOS
Outlook pro iOS podporuje podepisování S/MIME a šifrování zpráv pomocí certifikátů. Mnoho zákazníků má samostatné podpisové a šifrovací certifikáty, na rozdíl od jednoho certifikátu, který podporuje podepisování i šifrování. Podpisové certifikáty jsou všeobecně jedinečné v rámci zaregistrovaných zařízení jednotlivých uživatelů, zatímco šifrovací certifikáty se sdílejí napříč registrovanými zařízeními jednotlivých uživatelů. Uživatelé budou často používat S/MIME po rocích a při obnovení certifikátů budou v průběhu času používat jiné šifrovací certifikáty. V zařízení uživatele musí být k dispozici historie šifrovacích certifikátů, včetně jejich privátních klíčů, aby bylo možné přečíst e-mail, který mohl být zašifrovaný pomocí kteréhokoli z těchto certifikátů v minulosti. Je také možné, že máte jeden certifikát, který podporuje podepisování a šifrování.

Outlook pro iOS podporuje dva způsoby doručování certifikátů do zařízení, aby je bylo možné použít pro S/MIME:

- **Uživatelé** můžou zaregistrovat certifikáty s/MIME sami sebe a instalovat je z příloh v Outlooku pro iOS na jejich mobilních zařízeních.
- **Správci** můžou importovat historie šifrovacích certifikátů z jakékoli certifikační autority do správce koncových bodů. Správce koncových bodů pak tyto certifikáty automaticky doručí do libovolného zařízení, které uživatel zaregistruje. K podpisovým certifikátům se obecně používá Simple Certificate Enrollment Protocol (SCEP). Pomocí protokolu SCEP se privátní klíč vygeneruje a uloží na zaregistrovaném zařízení a na každé zařízení, které uživatel zaregistruje, se doručí jedinečný certifikát, který se dá použít k Neodmítnutí. Správci naimportují historie šifrovacích certifikátů pro své uživatele do správce koncových bodů. tím se všechny šifrovací certifikáty uživatele zapisují do libovolného zařízení, které zaregistruje. A konečně správce koncových bodů podporuje odvozená pověření pro zákazníky, kteří potřebují podporu standardu NIST 800-157. V systému iOS se Portál společnosti používá k načtení podpisových a šifrovacích certifikátů z Intune.

## <a name="configuring-outlook-for-ios-smime-in-endpoint-manager"></a>Konfigurace Outlooku pro iOS S/MIME ve Správci koncových bodů
Pokud chcete konfigurovat Outlook pro iOS S/MIME ve Správci koncových bodů, včetně automatického doručování certifikátů S/MIME, které může používat Outlook pro iOS, použijte následující postup:

### <a name="add-the-microsoft-outlook-app"></a>Přidat aplikaci Microsoft Outlook
1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Přidejte aplikaci Microsoft Outlook pro iOS z App Storu do správce koncových bodů nebo synchronizujte Outlook pro iOS z Apple Volume Purchase Program. Další informace najdete v tématu [Přidání aplikací pro iOS Store do Microsoft Intune](~/apps/store-apps-ios.md) nebo [Správa aplikací pro iOS a MacOS zakoupených prostřednictvím Apple Volume purchase program pomocí Microsoft Intune](~/apps/vpp-apps-ios.md).

### <a name="create-the-outlook-for-ios-smime-configuration-policy"></a>Vytvoření zásady konfigurace Outlook pro iOS S/MIME

Následující postup vám umožní vytvořit a nakonfigurovat zásadu Outlook pro iOS S/MIME ve Správci koncových bodů. Tato nastavení poskytují automatizované doručování podpisových a šifrovacích certifikátů.

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a vyberte **aplikace** > **aplikace zásady konfigurace** > **Přidat**.<br>
Zobrazí se podokno **Přidat zásady konfigurace** .
2. Zadejte **název** a **Popis** zásady konfigurace.
3. Jako **typ registrace zařízení**vyberte **spravovaná zařízení** .
4. Jako **platformu**vyberte **iOS/iPadOS** .
5. Klikněte na **vybrat požadovanou aplikaci** pro vyhledání a přidružení aplikace Microsoft Outlook pro iOS, kterou jste přidali dříve. 
6. Kliknutím na **nastavení konfigurace** přidejte nastavení konfigurace. 
    - Vyberte **použít návrháře konfigurace** vedle **Možnosti formát nastavení konfigurace** a přijměte výchozí nastavení. Další informace najdete v tématu [nastavení konfigurace aplikace Microsoft Outlook](~/apps/app-configuration-policies-outlook.md).
7. Kliknutím na možnost **S/MIME** zobrazte **nastavení aplikace Outlook S/MIME**.
8. Nastavte **Povolit s/MIME** na **Ano**.
9. Nastavte si **nasazení certifikátů S/MIME z Intune** na **Ano**.
10. V části **podpisové certifikáty** vedle položky **typ profilu certifikátu**vyberte jednu z následujících možností:
    - **SCEP** – vytvoří certifikát, který je jedinečný pro zařízení a uživatele, které může používat Microsoft Outlook k podepisování. Související informace najdete v tématu [Konfigurace infrastruktury pro podporu protokolu SCEP s Intune](~/protect/certificates-scep-configure.md) a [Vytvoření profilu certifikátu SCEP](~/protect/certificates-profile-scep.md#create-a-scep-certificate-profile). 
    - **Importovaná certifikát PKCS** – používá certifikát, který je jedinečný pro uživatele, ale může být sdílený napříč zařízeními a byl importován do správce koncových bodů správcem jménem uživatele. Certifikát se doručuje na jakékoli zařízení, které uživatel zaregistruje. Správce koncových bodů automaticky vybere importovaný certifikát, který podporuje podepisování k doručování do zařízení, odpovídá zaregistrovanému uživateli.
    - **Odvozené přihlašovací údaje** – používá certifikát, který je už na zařízení, který se dá použít k podepisování. Certifikát se musí na zařízení načíst pomocí odvozených toků přihlašovacích údajů v Intune.
11. V části **šifrovací certifikáty** vedle položky **typ profilu certifikátu**vyberte jednu z následujících možností:
    - **Importovaná certifikát PKCS** – poskytuje všechny šifrovací certifikáty, které se naimportovaly do správce koncových bodů správcem v jakémkoli zařízení, které uživatel zaregistruje. správce koncových bodů automaticky vybere importovaný certifikát nebo certifikáty, které podporují šifrování pro doručení do zařízení, které odpovídá zaregistrovanému uživateli.
    - **Odvozené přihlašovací údaje** – používá certifikát, který je už na zařízení, který se dá použít k podepisování. Certifikát se musí na zařízení načíst pomocí odvozených toků přihlašovacích údajů v Intune.
12. Vedle **oznámení koncových uživatelů**zvolte **portál společnosti** nebo **e-mailu** pro načtení certifikátů s/MIME pro Outlook pro iOS, a vyberte upozornění koncovým uživatelům.

    V systému iOS musí uživatelé použít aplikaci Portál společnosti k načtení certifikátů S/MIME. Správce koncových bodů bude informovat uživatele, že musí spustit Portál společnosti pro načtení certifikátů S/MIME prostřednictvím části oznámení v Portál společnosti, nabízeného oznámení a/nebo e-mailu. Kliknutím na jedno z oznámení převezme uživatel na úvodní stránku, která je informuje o průběhu získávání certifikátů. Po načtení certifikátů může uživatel podepsat a šifrovat e-mail pomocí standardu S/MIME v aplikaci Microsoft Outlook pro iOS.
    
    Oznámení koncových uživatelů zahrnují následující možnosti:
       - **Portál společnosti** – Pokud je tato možnost vybrána, budou uživatelé na svém zařízení dostávat nabízená oznámení, která přejdou na cílovou stránku v portál společnosti kam se budou načíst certifikáty S/MIME.
        - **E-mail** – pošle koncovému uživateli e-mail s upozorněním, že musí spustit portál společnosti pro načtení certifikátů S/MIME. Pokud je uživatel na zaregistrovaném zařízení s iOS, když klikne na odkaz v e-mailu, přesměruje se na Portál společnosti pro načtení svých certifikátů.
    
13. Vyberte **přiřazení** a přiřaďte zásady konfigurace aplikací ke SKUPINÁM Azure AD. Další informace najdete v článku [Přiřazení aplikací do skupin pomocí Microsoft Intune](~/apps/apps-deploy.md).

## <a name="next-steps"></a>Další kroky

- Další informace najdete v tématu [zásady konfigurace aplikací pro Microsoft Intune](app-configuration-policies-overview.md).
