---
title: Nastavení autority pro správu mobilních zařízení
titleSuffix: Microsoft Intune
description: Nastavte autoritu pro správu mobilních zařízení v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: fundamentals
ms.localizationpriority: high
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 19d02694ab5e53dc43e0861c6a427a044bf50648
ms.sourcegitcommit: ebf72b038219904d6e7d20024b107f4aa68f57e6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/05/2019
ms.locfileid: "72502630"
---
# <a name="set-the-mobile-device-management-authority"></a>Nastavení autority pro správu mobilních zařízení

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Nastavení autority pro správu mobilních zařízení (MDM) určuje způsob správy zařízení. Jako správce IT musíte nastavit autoritu MDM, aby uživatelé mohli registrovat zařízení pro správu.

Možné konfigurace:

- **Intune Standalone** – jedná se o pouze cloudovou správu, kterou můžete nakonfigurovat pomocí portálu Azure Portal. Zahrnuje celou sadu možností, které Intune nabízí. [Nastavte autoritu MDM v konzole Intune](#set-mdm-authority-to-intune).

- **Spoluspráva Intune** – integrace cloudového řešení Intune s System Center Configuration Manager pro zařízení s Windows 10. Intune můžete konfigurovat pomocí konzoly Configuration Manager. [Nakonfigurujte automatickou registraci zařízení v Intune](https://docs.microsoft.com/sccm/comanage/tutorial-co-manage-clients#configure-auto-enrollment-of-devices-to-intune). 

    > [!Important]
    >Připojování nových zákazníků hybridních MDM se už nepoužívá. Další informace najdete v příspěvku na blogu o [přesunu z hybridní správy mobilních zařízení do Intune v Azure](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) .

- **Správa mobilních zařízení pro Office 365** – jedná se o integraci Office 365 s cloudovým řešením Intune. Intune se konfiguruje v centru pro správu Microsoft 365. Zahrnuje dílčí sadu možností, které jsou dostupné s Intune Standalone. Nastavte autoritu MDM v centru pro správu Microsoft 365.

- **Koexistence Office 365 MDM** V tenantovi můžete aktivovat a používat současně službu MDM pro Office 365 i Intune a nastavit autoritu pro správu na Intune nebo MDM pro Office 365 pro každého uživatele, aby využíval, která služba se bude používat ke správě mobilních zařízení. Autorita pro správu uživatele je definovaná na základě licence přiřazené uživateli. Další informace najdete v tématu [Microsoft Intune souběžná existence s MDM pro Office 365](https://blogs.technet.microsoft.com/configmgrdogs/2016/01/04/microsoft-intune-co-existence-with-mdm-for-office-365) .

## <a name="set-mdm-authority-to-intune"></a>Nastavení autority MDM na Intune

Pokud jste ještě nenastavili autoritu MDM, proveďte postup uvedený níže. Pokud chcete přejít z SCCM, přečtěte si téma [migrace uživatelů a zařízení hybridní MDM do samostatného Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

1. V [Intune v Azure Portal](https://aka.ms/intuneportal)kliknutím na oranžový banner otevřete nastavení **autority pro správu mobilních zařízení** . Oranžová informační zpráva se zobrazí jenom v případě, že jste autoritu MDM ještě nenastavili.
2. V oblasti **Autorita pro správu mobilních zařízení** zvolte některou autoritu MDM z následujících možností:
   - **Autorita MDM Intune**
   - **Žádné**

   ![Snímek obrazovky Intune s nastavením autority pro správu mobilních zařízení](./media/mdm-authority-set/set-mdm-auth.png)

   Zobrazí se zpráva, že jste úspěšně nastavili autoritu MDM na Intune.

### <a name="workflow-of-intune-administration-ui"></a>Pracovní postup pro uživatelské rozhraní pro správu Intune
Pokud je povolená správa zařízení s Androidem nebo zařízení Apple, odesílá Intune informace o zařízení a uživateli, aby byla možná integrace služeb třetích stran a správa příslušných zařízení.

Mezi scénáře, pro které se přidává souhlas se sdílením dat, patří:
- Povolení pracovních profilů Androidu
- Povolení a nahrání certifikátů Apple MDM Push Certificate
- Povolení některé ze služeb Apple, jako jsou například Program registrace zařízení, School Manager a Volume Purchase Program

V každém případě je vyjádření souhlasu omezeno výhradně na spouštění služby správy mobilního zařízení. Jedná se například o potvrzení, že správce IT má autorizaci k registraci zařízení Google nebo Apple. Dokumentaci obsahující informace, které se po přechodu na nové pracovní postupy budou sdílet, najdete v následujících umístěních:
- [Data z Intune odesílaná Googlu](https://aka.ms/Data-intune-sends-to-google)
- [Data z Intune odesílaná Applu](https://aka.ms/data-intune-sends-to-apple)

## <a name="key-considerations"></a>Klíčové aspekty
Po přechodu na novou autoritu MDM pravděpodobně nastane přechodná doba (až osm hodin), než se zařízení ohlásí a synchronizuje se službou. Je potřeba nakonfigurovat nastavení nové autority MDM (hybridní), aby zaregistrovaná zařízení byla i po provedení změny dál spravovaná a chráněná. 
- Zařízení se musí ke službě po změně připojit, aby nastavení z nové autority MDM (Intune samostatně) nahradila stávající nastavení v zařízení.
- Po změně autority MDM některá základní nastavení (například profily) z předchozí autority MDM (Intune samostatně) zůstanou v zařízení po dobu až sedmi dnů nebo do doby, než se zařízení ke službě poprvé připojí. Doporučujeme co nejdříve nakonfigurovat aplikace a nastavení (zásady, profily, aplikace atd.) v nové autoritě MDM (hybridní) a nasadit nastavení do skupin uživatelů obsahujících uživatele, kteří mají stávající zaregistrovaná zařízení. Jakmile se zařízení ke službě po změně autority MDM připojí, obdrží nová nastavení z nové autority MDM a zabrání se mezerám ve správě a ochraně.
- Přestože existují stejné kategorie zařízení v Intune i v Configuration Manageru, žádné přiřazené kategorie zařízení se po přepnutí na novou autoritu MDM nepřenesou. Pokud chcete i nadále používat kategorie zařízení, musí se migrovaná zařízení přidat do příslušných kolekcí ručně poté, co dojde ke změně autority MDM a zařízení se zobrazí v konzole Configuration Manageru.
- Zařízení, která nemají přiřazené uživatele (obvykle v případě programu registrace zařízení s iOSem nebo hromadné registrace), nebudou na novou autoritu MDM migrována. Pro taková zařízení musíte zavolat podporu, aby vám s přesunem do nové autority MDM pomohla.

## <a name="change-mdm-authority-to-office-365"></a>Změna autority MDM na Office 365

Pokud chcete aktivovat Office 365 MDM (nebo pokud chcete společně s vaší stávající službou Intune povolit koexistenci MDM), použijte [https://protection.office.com](https://protection.office.com), vyberte možnost **prevence ztráty dat** > **zásady zabezpečení zařízení** > **Zobrazit seznam spravovaných zařízení** > **Pojďme začít**.

Další informace najdete v článku o [nastavení správy mobilních zařízení (MDM) v Office 365](https://support.office.com/en-us/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd).

Pokud chcete ke správě koncových uživatelů používat jenom Office 365 MDM, aktivujte Office 365 MDM a pak odeberte přiřazené licence Intune a/nebo EMS.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Vyčištění mobilních zařízení po vypršení platnosti certifikátu MDM

Certifikát MDM se obnovuje automaticky, když mobilní zařízení komunikují se službou Intune. Když se mobilní zařízení vymažou nebo se jim po určitou dobu nedaří komunikovat se službou Intune, certifikát MDM se neobnoví. Zařízení se z portálu Azure Portal odebere po uplynutí 180 dnů od vypršení platnosti certifikátu MDM.

## <a name="remove-mdm-authority"></a>Odebrání autority MDM

Autoritu MDM nemůžete změnit zpátky na neznámou. Autorita pro správu mobilních zařízení používá službu k určení, která zařízení zaregistrovaná na portálu se budou hlásit (Microsoft Intune nebo Office 365 MDM).

## <a name="what-to-expect-after-changing-the-mdm-authority"></a>Co očekávat po změně autority MDM

- Když služba Intune zjistí, že se autorita MDM tenanta změnila, odešle do všech zaregistrovaných zařízení zprávu s oznámením, aby se ohlásila a synchronizovala se službou (mimo interval pravidelně naplánovaných ohlášení). Proto po změně autority MDM pro tenanta ze samostatného Intune na hybridní se všechna zařízení, která jsou zapnutá a online, připojí ke službě, obdrží novou autoritu MDM a budou spravována hybridní autoritou. Správa a ochrana těchto zařízení se nijak nepřeruší.
- I když jsou zařízení při změně autority MDM (nebo krátce po ní) zapnutá a online, může trvat až osm hodin, než se do služby zaregistrují pod novou autoritou MDM (záleží na načasování příští naplánované pravidelné registrace).    

  > [!IMPORTANT]    
  > V době mezi změnou autority MDM a nahráním obnoveného certifikátu APNs do nové autority se nové registrace a ohlášení zařízení s iOSem nezdaří. Proto je důležité certifikát APNs zkontrolovat a do nové autority nahrát co nejdřív po změně autority MDM.

- Uživatelé můžou na novou autoritu MDM rychle přejít ručním spuštěním registrace zařízení do služby. Tuto změnu uživatelé snadno provedou pomocí aplikace Portál společnosti a inicializováním kontroly dodržování předpisů zařízením.
- Pokud chcete zkontrolovat, jestli po ohlášení a synchronizaci zařízení se službou po změně autority MDM všechno správně funguje, vyhledejte zařízení v konzole Configuration Manageru. Zařízení, která byla dřív spravovaná pomocí Intune, se nyní zobrazují jako spravovaná zařízení v konzole Configuration Manageru.    
- Během změny autority MDM a ohlašování zařízení do služby bude zařízení přechodně offline. Aby se zajistilo, že zařízení během tohoto přechodného období zůstane chráněné a funkční, zůstanou v zařízení po dobu až sedmi dnů (nebo dokud se zařízení nepřipojí k nové autoritě MDM a neobdrží nová nastavení, která přepíší ta stávající) následující profily:
  - E-mailový profil
  - Profil VPN
  - Profil certifikátu
  - profil Wi-Fi
  - Konfigurační profily
- Po změně na novou autoritu MDM může trvat až týden, než budou data o dodržování předpisů v konzole pro správu Microsoft Intune přesná. Stavy dodržování předpisů v Azure Active Directory a na zařízení však přesné budou, takže zařízení je i nadále chráněné.
- Zajistěte, aby nová nastavení, která mají přepsat stávající nastavení, měla stejný název jako ta předchozí, aby se původní nastavení skutečně přepsala. Jinak může mít zařízení nadbytečné profily a zásady.    

  > [!TIP]    
  > Osvědčený postup je takový, že všechna nastavení a konfigurace správy vytvoříte a nasazení provedete krátce po dokončení změny autority MDM. To vám pomáhá zajistit, aby byla zařízení v přechodném období chráněná a aktivně spravovaná.

- Po změně autority MDM pomocí následujících kroků zkontrolujte, jestli se nová zařízení do nové autority úspěšně zaregistrovala:   
  - Zaregistrujte nové zařízení.
  - Zkontrolujte, jestli se nově zaregistrované zařízení zobrazuje v konzole Configuration Manageru.
  - Proveďte z konzoly pro správu na zařízení akci, jako je vzdálené uzamčení. Pokud je akce úspěšná, zařízení je spravované novou autoritou MDM.
- Pokud máte problémy s konkrétními zařízeními, můžete zrušit jejich registraci a znovu je zaregistrovat, aby se co nejdříve připojila k nové autoritě a byla spravována.

## <a name="next-steps"></a>Další kroky

Po nastavení autority MDM můžete zahájit [registraci zařízení](../enrollment/device-enrollment.md).
