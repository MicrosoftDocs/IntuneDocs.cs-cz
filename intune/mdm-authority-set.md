---
title: Nastavení autority pro správu mobilních zařízení
titleSuffix: Microsoft Intune
description: Nastavte autoritu pro správu mobilních zařízení v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/30/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 898c4eee19aa50136736f4ee72c55e4e8931317d
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59894769"
---
# <a name="set-the-mobile-device-management-authority"></a>Nastavení autority pro správu mobilních zařízení

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Nastavení autority pro správu mobilních zařízení (MDM) určuje způsob správy zařízení. Jako správce IT musíte nastavit autoritu MDM, aby uživatelé mohli registrovat zařízení pro správu.

Možné konfigurace:

- **Intune Standalone** – jedná se o pouze cloudovou správu, kterou můžete nakonfigurovat pomocí portálu Azure Portal. Zahrnuje celou sadu možností, které Intune nabízí. [Nastavte autoritu MDM v konzole Intune](#set-mdm-authority-to-intune).

- **Společná správa Intune** -integraci cloudového řešení Intune s nástrojem System Center Configuration Manager pro zařízení s Windows 10. Intune můžete konfigurovat pomocí konzoly Configuration Manager. [Konfigurace automatické registrace zařízení v Intune](https://docs.microsoft.com/sccm/comanage/tutorial-co-manage-clients#configure-auto-enrollment-of-devices-to-intune). 

    > [!Important]
    >Registrace nové zákazníky hybridní MDM je zastaralá. Další informace najdete v tématu [přesunout z hybridní správy mobilních zařízení do Intune na Azure](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Move-from-Hybrid-Mobile-Device-Management-to-Intune-on-Azure/ba-p/280150) blogový příspěvek.

- **Správa mobilních zařízení pro Office 365** – jedná se o integraci Office 365 s cloudovým řešením Intune. Intune můžete konfigurovat z centra pro správu vašich služeb Microsoft 365. Zahrnuje dílčí sadu možností, které jsou dostupné s Intune Standalone. Nastavte autoritu MDM v Centru pro správu Microsoftu 365.

> [!IMPORTANT]
> V Configuration Manageru verze 1610 a vyšší a v Microsoft Intune verze 1705 můžete změnit autoritu pro správu mobilních zařízení bez kontaktování podpory Microsoftu a bez rušení registrace a následné nové registrace stávajících spravovaných zařízení. Podrobnosti najdete v tématu [připravit na změny autority MDM na Configuration Manager](mdm-authority-set.md#prepare-to-change-the-mdm-authority-to-configuration-manager).

## <a name="set-mdm-authority-to-intune"></a>Nastavení autority MDM na Intune

Pokud jste ještě nenastavili autoritu MDM, proveďte postup uvedený níže. Pokud chcete změnit jednu autoritu MDM na jinou, podívejte se níže na část [Změna autority MDM](#prepare-to-change-the-mdm-authority-to-configuration-manager).

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Výběrem oranžové informační zprávy otevřete nastavení **Autorita pro správu mobilních zařízení**. Oranžová informační zpráva se zobrazí jenom v případě, že jste autoritu MDM ještě nenastavili.
4. V oblasti **Autorita pro správu mobilních zařízení** zvolte některou autoritu MDM z následujících možností:
   - **Autorita MDM Intune**
   - **Autorita MDM Configuration Manageru**
   - **Žádné**

   ![Snímek obrazovky Intune s nastavením autority pro správu mobilních zařízení](media/set-mdm-auth.png)

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

## <a name="prepare-to-change-the-mdm-authority-to-configuration-manager"></a>Příprava změny autority MDM na Configuration Manager

V rámci přípravy na změnu autority MDM zkontrolujte následující informace:
- Aby byla možnost změnit autoritu MDM k dispozici, musíte mít Configuration Manager ve verzi 1610.
- Může trvat až 8 hodin, než se zařízení po změně na novou autoritu MDM ke službě připojí.
- Vytvořte kolekci uživatelů Configuration Manageru se všemi uživateli aktuálně spravovanými samostatným Intune, kterou použijete při zřizování předplatného Intune v konzole Configuration Manageru. Tato kolekce pomůže zajistit, že uživatel se svými zařízeními bude mít po změně na autoritu MDM přiřazenou licenci Configuration Manageru a bude v hybridním prostředí spravován.
- V této kolekci uživatelů musí být také uživatel s rolí správce IT.  
- Před změnou se bude autorita MDM v konzole pro správu Intune zobrazovat jako **Nastavit na Microsoft Intune** (samostatně).
- Autorita MDM by před změnou autority MDM měla v konzole pro správu Microsoft Intune zobrazovat **Nastavit na Microsoft Intune** (samostatný tenant).
    > [!NOTE]    
    > Pokud vaše autorita MDM zobrazuje **Spravováno přes Intune a Office 365**, pak už vaše zařízení MDM spravovaná přes Office 365 po změně autority MDM na **Configuration Manager** (hybridní) spravovaná nejsou. Doporučujeme, abyste takové uživatele před změnou autority MDM licencovali pro Intune nebo Enterprise Mobility Suite.   

- V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) odeberte roli správce registrace zařízení. Podrobnosti najdete v sekci [Odstranění správce registrace zařízení ze služby Intune](device-enrollment-manager-enroll.md#remove-device-enrollment-manager-permissions).
- Vypněte všechna mapování skupin zařízení, která jsou nakonfigurovaná. Podrobnosti najdete v článku [Kategorizace zařízení pomocí mapování skupin zařízení v Microsoft Intune](device-group-mapping.md).
- Během změny autority MDM by nemělo dojít k žádnému znatelnému dopadu na koncové uživatele. Změnu byste ale měli uživatelům oznámit, aby se zajistilo, že jejich zařízení budou brzy po provedení změny zapnutá a připojí se ke službě. Toto opatření zajistí, že se ke službě co nejdříve přihlásí a prostřednictvím nové autority zaregistruje co nejvíce zařízení.
- Pokud před změnou autority MDM používáte samostatnou službu Intune ke správě zařízení s iOSem, musíte zajistit, aby se stejný certifikát služby Apple Push Notification Service (APNs), který se předtím používal v Intune, obnovil a znovu použil k nastavení tenanta v Configuration Manageru (hybridním).    

    > [!IMPORTANT]  
    > Pokud se pro hybridní autoritu používá jiný certifikát APNs, pak se registrace VŠECH dřív zaregistrovaných zařízení s iOSem zruší a budete muset projít procesem jejich opětovné registrace. Před provedením změny autority MDM se ujistěte, že přesně víte, jaký certifikát APNs se ke správě zařízení s iOSem v Intune používal. Najděte stejný certifikát uvedený na Apple Push Certificates Portalu (https://identity.apple.com) a ujistěte se, že v rámci změny na novou autoritu MDM je k obnovení stejného certifikátu APNs identifikován a dostupný stejný uživatel, jehož Apple ID se použilo k vytvoření původního certifikátu APNs.

## <a name="change-the-mdm-authority-to-configuration-manager"></a>Změna autority MDM na Configuration Manager

1. V konzole Configuration Manageru přejděte na **Správa** &gt; **Přehled** &gt; **Cloudové služby** &gt; **Předplatné Microsoft Intune**  a přidejte předplatné Intune tím, že ho vyberte.
2. Přihlaste se do tenanta Intune, kterého jste původně použili při nastavení autority MDM v Intune, a klikněte na **Další**.
3. Vyberte **Změnit moji autoritu MDM na Configuration Manager** a klikněte na **Další**.
4. Vyberte kolekci uživatelů, aby obsahovala všechny uživatele, kteří budou dál spravovaní novou hybridní autoritou MDM.
5. Klikněte na tlačítko **Další** a dokončete průvodce. Autorita MDM je teď změněná na **Configuration Manager**.
6. Přihlaste se pomocí stejného tenanta Intune do [konzoly pro správu Microsoft Intune](http://manage.microsoft.com) a zkontrolujte, jestli se autorita MDM změnila na **Nastavit na nástroj Configuration Manager**.
7. Jakmile změníte autoritu MDM na Configuration Manager, můžete nastavit [registraci iOS](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-ios-mac) a [registraci Androidu](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-android).
8. V konzole Configuration Manageru nakonfigurujte a nasaďte nová nastavení a aplikace z nové autority MDM (hybridní).

Při příštím připojení ke službě se zařízení synchronizují a z nové autority MDM obdrží nová nastavení.

## <a name="change-mdm-authority-to-office-365"></a>Změna autority MDM na Office 365

Pokud chcete kromě stávající služby Intune aktivovat také Office 365 MDM, přejděte na [https://protection.office.com](https://protection.office.com), zvolte **Ochrana před únikem informací** > **Zásady zabezpečení zařízení** > **Zobrazit seznam spravovaných zařízení** > **Můžeme začít**.

Další informace najdete v článku o [nastavení správy mobilních zařízení (MDM) v Office 365](https://support.office.com/en-us/article/Set-up-Mobile-Device-Management-MDM-in-Office-365-dd892318-bc44-4eb1-af00-9db5430be3cd).

Pokud chcete ke správě koncových uživatelů používat jenom Office 365 MDM, aktivujte Office 365 MDM a pak odeberte přiřazené licence Intune a/nebo EMS.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Vyčištění mobilních zařízení po vypršení platnosti certifikátu MDM

Certifikát MDM se obnovuje automaticky, když mobilní zařízení komunikují se službou Intune. Když se mobilní zařízení vymažou nebo se jim po určitou dobu nedaří komunikovat se službou Intune, certifikát MDM se neobnoví. Zařízení se z portálu Azure Portal odebere po uplynutí 180 dnů od vypršení platnosti certifikátu MDM.

## <a name="remove-mdm-authority"></a>Odebrání autority MDM

Autoritu MDM nemůžete změnit zpátky na neznámou. Servery Microsoftu používají autoritu MDM k tomu, aby zjistily, na jaký portál mají zaregistrovaná zařízení posílat hlášení (ConfigMGR, Azure Intune, Office 365 MDM).

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
    - Profil Wi-Fi
    - Konfigurační profily
- Po změně na novou autoritu MDM může trvat až týden, než budou data o dodržování předpisů v konzole pro správu Microsoft Intune přesná. Stavy dodržování předpisů v Azure Active Directory a na zařízení však přesné budou, takže zařízení je i nadále chráněné.
- Zajistěte, aby nová nastavení, která mají přepsat stávající nastavení, měla stejný název jako ta předchozí, aby se původní nastavení skutečně přepsala. Jinak může mít zařízení nadbytečné profily a zásady.    

  > [!TIP]    
  > Osvědčený postup je takový, že všechna nastavení a konfigurace správy vytvoříte a nasazení provedete krátce po dokončení změny autority MDM. To vám pomáhá zajistit, aby byla zařízení v přechodném období chráněná a aktivně spravovaná.

-  Po změně autority MDM pomocí následujících kroků zkontrolujte, jestli se nová zařízení do nové autority úspěšně zaregistrovala:   
    - Zaregistrujte nové zařízení.
    - Zkontrolujte, jestli se nově zaregistrované zařízení zobrazuje v konzole Configuration Manageru.
    - Proveďte z konzoly pro správu na zařízení akci, jako je vzdálené uzamčení. Pokud je akce úspěšná, zařízení je spravované novou autoritou MDM.
- Pokud máte problémy s konkrétními zařízeními, můžete zrušit jejich registraci a znovu je zaregistrovat, aby se co nejdříve připojila k nové autoritě a byla spravována.

## <a name="next-steps"></a>Další postup

Po nastavení autority MDM můžete zahájit [registraci zařízení](device-enrollment.md).
