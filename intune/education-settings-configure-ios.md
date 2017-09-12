---
title: "Nastavení Intune pro aplikaci Classroom pro iOS"
titlesuffix: Azure portal
description: "Přečtěte si o nastaveních Intune, pomocí kterých můžete ovládat nastavení aplikace Classroom na zařízeních s iOSem."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: derriw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1ea9c38fc7d2dd82171d4018cfe1048c8f139386
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-configure-intune-settings-for-the-ios-classroom-app"></a>Jak nakonfigurovat nastavení Intune pro aplikaci Classroom pro iOS

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a>Úvod
[Classroom](https://itunes.apple.com/app/id1085319084) je aplikace, která učitelům umožňuje vést výuku a ovládat zařízení studentů v učebně. Tato aplikace učitelům například umožňuje:

- Otevírat aplikace na zařízeních studentů
- Zamykat a odemykat obrazovku iPadu
- Prohlížet obrazovku iPadu studenta
- Přejít v iPadech studentů na záložku nebo kapitolu v knize
- Ukázat obrazovku iPadu studenta na Apple TV

S využitím **vzdělávacího** profilu zařízení s iOSem v Intune a informací v tomto tématu nastavíte aplikaci Classroom a zařízení, na kterých se bude používat.

## <a name="before-you-start"></a>Než začnete

Než tato nastavení začnete konfigurovat, zvažte následující skutečnosti:

- iPady učitelů i studentů musí být zaregistrované v Intune.
- Zajistěte, aby na zařízení učitele byla nainstalovaná aplikace [Apple Classroom](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8). Můžete aplikaci nainstalovat buď ručně, nebo přes [správu aplikací Intune](app-management.md).
- Musíte nakonfigurovat certifikáty pro ověření připojení mezi zařízeními učitelů a studentů (viz krok 2).
- iPady učitelů a studentů musí být ve stejné Wi-Fi síti a musí mít povolené Bluetooth.
- Aplikace Classroom běží na iPadech s iOSem 9.3 nebo novější verzí, které jsou pod dohledem.
- V této verzi podporuje Intune správu scénáře 1:1, kdy má každý student svůj vlastní vyhrazený iPad.


## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>Krok 1 – Import školních dat do služby Azure Active Directory

Pomocí služby Microsoft SDS (School Data Sync) naimportujte školní záznamy z existujícího studentského informačního systému (SIS) do služby Azure Active Directory (Azure AD).
Služba SDS synchronizuje informace z vašeho systému SIS a uloží je do služby Azure AD. Azure AD je systém správy od Microsoftu, který pomáhá s organizací uživatelů a zařízení. Tato data vám pak pomohou se správou vašich studentů a zařízení. [Přečtěte si další informace o nasazení SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>Jak naimportovat data pomocí SDS

Informace můžete do SDS naimportovat jednou z následujících metod:

- [Soubory CSV](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1) – ruční export a sestavení textových souborů s oddělovačem (.csv)
- [PowerSchool API](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f) – poskytovatel SIS, který zjednodušuje synchronizaci se službou Azure AD
- [Clever API](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae) – řešení pro správu identit, které se synchronizuje přímo se službou Azure AD
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab) – formát CSV, který můžete exportovat a konvertovat pro synchronizaci se službou Azure AD

### <a name="find-out-more"></a>Další informace

- [Další informace o úplné synchronizaci místních školních dat se službou Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [Další informace o službě Microsoft SDS (School Data Sync](https://sds.microsoft.com/)
- [Další informace o licencování ve službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)

## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>Krok 2 – Vytvoření a přiřazení vzdělávacího profilu iOS v Intune

### <a name="configure-general-settings"></a>Konfigurace obecných nastavení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3.  V okně **Intune** zvolte **Konfigurovat zařízení**.
4.  V okně **Konfigurace zařízení** zvolte **Spravovat** > **Profily**.
5.  V okně profilů zvolte **Vytvořit profil**.
6.  V okně **Vytvořit profil** zadejte **Název** a **Popis** vzdělávacího profilu iOS.
7.  Z rozevíracího seznamu **Platforma** zvolte **iOS**.
8.  Z rozevíracího seznamu **Typ profilu** zvolte **Vzdělávání**.
9.  Zvolte **Nastavení** > **Konfigurovat**.


Dále potřebujete certifikáty k navázání vztahu důvěryhodnosti mezi iPady učitelů a studentů. Certifikáty se používají k bezproblémovému a bezobslužnému ověřování připojení mezi zařízeními bez nutnosti zadávání uživatelských jmen a hesel.

>[!IMPORTANT]
>Použité certifikáty učitelů a studentů musí být vystavené odlišnými certifikačními autoritami (CA). Musíte vytvořit dvě nové podřízené certifikační autority propojené s vaší existující certifikační infrastrukturou; jednu pro učitele a druhou pro studenty.

Vzdělávací profily iOS podporují pouze certifikáty PFX. Certifikáty SCEP podporovány nejsou.

Certifikáty, které vytvoříte, musí kromě ověřování uživatelů podporovat také ověřování serverů.

### <a name="configure-teacher-certificates"></a>Konfigurace certifikátů učitelů

V okně **Vzdělávání** zvolte **Certifikáty učitelů**.

#### <a name="configure-teacher-root-certificate"></a>Konfigurace kořenového certifikátu učitele

V části **Kořenový certifikát učitele** vyberte tlačítkem Procházet kořenový certifikát učitele s příponou .cer (DER nebo s kódováním Base64) nebo .P7B (s úplným řetězem nebo bez).

#### <a name="configure-teacher-pkcs12-certificate"></a>Konfigurace certifikátu PKCS#12 učitele

V části **Certifikát PKCS#12 učitele** nakonfigurujte následující hodnoty:

- **Formát názvu subjektu** – Intune automaticky přidá k běžnému názvu certifikátu předponu **leader** pro certifikát učitele a předponu **member** pro certifikát studenta.
- **Certifikační autorita** – Certifikační autorita organizace (CA), která běží na verzi Enterprise systému Windows Server 2008 R2 nebo novější. Samostatná certifikační autorita není podporovaná. 
- **Název certifikační autority** – Zadejte název certifikační autority.
- **Název šablony certifikátu** – Zadejte název šablony certifikátu, která byla přidána k vystavující certifikační autoritě. 
- **Prahová hodnota obnovení (%)** – Zadejte procento doby životnosti certifikátu zbývající v okamžiku, kdy zařízení požádá o obnovení certifikátu.
- **Období platnosti certifikátu** – Zadejte zbývající dobu do vypršení platnosti certifikátu.
Zadat můžete hodnotu nižší, než je období platnosti zadané v šabloně certifikátu, ne však vyšší. Pokud je třeba období platnosti certifikátu v šabloně certifikátu dva roky, můžete zadat hodnotu jeden rok, ale ne pět let. Tato hodnota musí být zároveň nižší než zbývající doba platnosti certifikátu vystavující certifikační autority.

Po dokončení konfigurace certifikátů zvolte **OK**.

### <a name="configure-student-certificates"></a>Konfigurace certifikátů studentů

1.  V okně **Vzdělávání** zvolte **Certifikáty studentů**.
2.  V okně **Certifikáty studentů** zvolte v seznamu **Typ certifikátů studentských zařízení** možnost **1:1**.

#### <a name="configure-student-root-certificate"></a>Konfigurace kořenového certifikátu studenta

V části **Kořenový certifikát studenta** vyberte tlačítkem Procházet kořenový certifikát studenta s příponou .cer (DER nebo s kódováním Base64) nebo .P7B (s úplným řetězem nebo bez).

#### <a name="configure-student-pkcs12-certificate"></a>Konfigurace certifikátu PKCS#12 studenta

V části **Certifikát PKCS#12 studenta** nakonfigurujte následující hodnoty:

- **Formát názvu subjektu** – Intune automaticky přidá k běžnému názvu certifikátu předponu **leader** pro certifikát učitele a předponu **member** pro certifikát studenta.
- **Certifikační autorita** – Certifikační autorita organizace (CA), která běží na verzi Enterprise systému Windows Server 2008 R2 nebo novější. Samostatná certifikační autorita není podporovaná. 
- **Název certifikační autority** – Zadejte název certifikační autority.
- **Název šablony certifikátu** – Zadejte název šablony certifikátu, která byla přidána k vystavující certifikační autoritě. 
- **Prahová hodnota obnovení (%)** – Zadejte procento doby životnosti certifikátu zbývající v okamžiku, kdy zařízení požádá o obnovení certifikátu.
- **Období platnosti certifikátu** – Zadejte zbývající dobu do vypršení platnosti certifikátu.
Zadat můžete hodnotu nižší, než je období platnosti zadané v šabloně certifikátu, ne však vyšší. Pokud je třeba období platnosti certifikátu v šabloně certifikátu dva roky, můžete zadat hodnotu jeden rok, ale ne pět let. Tato hodnota musí být zároveň nižší než zbývající doba platnosti certifikátu vystavující certifikační autority.

Až dokončíte konfiguraci certifikátů, zvolte **OK**.

## <a name="finish-up"></a>Dokončení

1.  V okně **Vzdělávání** zvolte OK.
2.  V okně **Vytvořit profil** zvolte **Vytvořit**.
    
Profil se vytvoří a zobrazí se v okně se seznamem profilů.

Přiřaďte profil ke studentským zařízením ve skupinách učebny, které se vytvořily při synchronizaci školních dat se službou Azure AD (viz [Přiřazení profilů zařízení](device-profile-assign.md)).

## <a name="next-steps"></a>Další kroky

Když teď učitel použije aplikaci Classroom, bude mít plnou kontrolu nad zařízeními studentů.

Další informace o aplikaci Classroom najdete v [nápovědě pro Classroom](https://help.apple.com/classroom/ipad/2.0/) na webu Applu.

Pokud chcete konfigurovat sdílená zařízení iPad pro studenty, podívejte se na článek o [konfiguraci nastavení vzdělávání Intune pro sdílená zařízení s iOSem](education-settings-configure-ios-shared.md).
