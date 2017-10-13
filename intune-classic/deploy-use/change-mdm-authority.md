---
title: "Změna autority MDM na Configuration Manager (hybridní MDM)"
description: "Zjistěte, jak změnit autoritu MDM ze samostatného Intune na Configuration Manager (hybridní MDM)."
keywords: 
author: dougeby
manager: angrobe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1b4bce3-7932-4a0d-aa92-6dacc7060f42
ms.reviewer: 
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9119c9ece21117e916a5b30a6a8d80e518047b5e
ms.sourcegitcommit: 001577b700f634da2fec0b44af2a378150d1f7ac
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2017
---
# <a name="change-the-mdm-authority"></a>Změna autority MDM
Od Configuration Manageru verze 1610 můžete změnit autoritu MDM, aniž by bylo nutné kontaktovat podporu Microsoftu a rušit registraci a následně nově registrovat stávající spravovaná zařízení. Toto téma představuje kroky ke změně existujícího tenanta Microsoft Intune nakonfigurovaného z Intune a s autoritu MDM nastavenou na **Microsoft Intune** (samostatně) na **Configuration Manager** (hybridní MDM), aniž byste museli zrušit registraci existujících spravovaných zařízení a znovu je zaregistrovat.

> [!Note]    
> Pokud chcete změnit existujícího tenanta Microsoft Intune nakonfigurovaného z konzoly Configuration Manageru (hybridní) a s autoritu MDM nastavenou na **Configuration Manager** (hybridní) na **Microsoft Intune** (samostatně), přečtěte si téma o [změně autority MDM z Configuration Manageru (hybridní MDM) na samostatné Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority). 


## <a name="key-considerations"></a>Klíčové aspekty
Po přechodu na novou autoritu MDM pravděpodobně nastane přechodná doba (až osm hodin), než se zařízení ohlásí a synchronizuje se službou. Je potřeba nakonfigurovat nastavení nové autority MDM (hybridní), aby zaregistrovaná zařízení byla i po provedení změny dál spravovaná a chráněná. 
- Zařízení se musí ke službě po změně připojit, aby nastavení z nové autority MDM (Intune samostatně) nahradila stávající nastavení v zařízení.
- Po změně autority MDM některá základní nastavení (například profily) z předchozí autority MDM (Intune samostatně) zůstanou v zařízení po dobu až sedmi dnů nebo do doby, než se zařízení ke službě poprvé připojí. Doporučujeme co nejdříve nakonfigurovat aplikace a nastavení (zásady, profily, aplikace atd.) v nové autoritě MDM (hybridní) a nasadit nastavení do skupin uživatelů obsahujících uživatele, kteří mají stávající zaregistrovaná zařízení. Jakmile se zařízení ke službě po změně autority MDM připojí, obdrží nová nastavení z nové autority MDM a zabrání se mezerám ve správě a ochraně.
- Přestože existují stejné kategorie zařízení v Intune i v Configuration Manageru, žádné přiřazené kategorie zařízení se po přepnutí na novou autoritu MDM nepřenesou. Pokud chcete i nadále používat kategorie zařízení, musí se migrovaná zařízení přidat do příslušných kolekcí ručně poté, co dojde ke změně autority MDM a zařízení se zobrazí v konzole Configuration Manageru.
- Zařízení, která nemají přiřazené uživatele (obvykle v případě programu registrace zařízení s iOSem nebo hromadné registrace), nebudou na novou autoritu MDM migrována. Pro taková zařízení musíte zavolat podporu, aby vám s přesunem do nové autority MDM pomohla.

## <a name="prepare-to-change-the-mdm-authority-to-configuration-manager-hybrid"></a>Příprava na změnu autority MDM na Configuration Manager (hybridní)
V rámci přípravy na změnu autority MDM zkontrolujte následující informace:
- Aby byla možnost změnit autoritu MDM k dispozici, musíte mít Configuration Manager ve verzi 1610.
- Může trvat až 8 hodin, než se zařízení po změně na novou autoritu MDM ke službě připojí.
- Vytvořte kolekci uživatelů Configuration Manageru se všemi uživateli aktuálně spravovanými samostatným Intune, kterou použijete při zřizování předplatného Intune v konzole Configuration Manageru. Pomůže to zajistit, že uživatel se svými zařízeními bude mít po změně na autoritu MDM přiřazenou licenci Configuration Manageru a bude v hybridním prostředí spravován.
- V této kolekci uživatelů musí být také uživatel s rolí správce IT.  
- Před změnou se bude autorita MDM v konzole pro správu Intune zobrazovat jako **Nastavit na Microsoft Intune** (samostatně).
- Autorita MDM by před změnou autority MDM měla v konzole pro správu Microsoft Intune zobrazovat **Nastavit na Microsoft Intune** (samostatný tenant).
    > [!NOTE]    
    > Pokud vaše autorita MDM zobrazuje **Spravováno přes Intune a Office 365**, pak už vaše zařízení MDM spravovaná přes Office 365 po změně autority MDM na **Configuration Manager** (hybridní) spravovaná nejsou. Doporučujeme, abyste takové uživatele před změnou autority MDM licencovali pro Intune nebo Enterprise Mobility Suite.   

- V [konzole pro správu Microsoft Intune](http://manage.microsoft.com) odeberte roli správce registrace zařízení. Podrobnosti najdete v sekci [Odstranění správce registrace zařízení ze služby Intune](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune#delete-a-device-enrollment-manager-from-intune).
- Vypněte všechna mapování skupin zařízení, která jsou nakonfigurovaná. Podrobnosti najdete v článku [Kategorizace zařízení pomocí mapování skupin zařízení v Microsoft Intune](/intune-classic/deploy-use/categorize-devices-with-device-group-mapping-in-microsoft-intune).
- Během změny autority MDM by nemělo dojít k žádnému znatelnému dopadu na koncové uživatele. Změnu byste ale měli uživatelům oznámit, aby se zajistilo, že jejich zařízení budou brzy po provedení změny zapnutá a připojí se ke službě. To zajistí, že se ke službě co nejdříve přihlásí a prostřednictvím nové autority zaregistruje co nejvíce zařízení.
- Pokud před změnou autority MDM používáte samostatné Intune ke správě zařízení s iOSem, musíte zajistit, aby se stejný certifikát služby Apple Push Notification (APNs), který se předtím používal v Intune, obnovil a znovu použil k nastavení tenanta v Configuration Manageru (hybridním).    

    > [!IMPORTANT]  
    > Pokud se pro hybridní autoritu používá jiný certifikát APNs, pak se registrace VŠECH dřív zaregistrovaných zařízení s iOSem zruší a budete muset projít procesem jejich opětovné registrace. Před provedením změny autority MDM se ujistěte, že přesně víte, jaký certifikát APNs se ke správě zařízení s iOSem v Intune používal. Najděte stejný certifikát uvedený na Apple Push Certificates Portalu (https://identity.apple.com) a ujistěte se, že v rámci změny na novou autoritu MDM je k obnovení stejného certifikátu APNs identifikován a dostupný stejný uživatel, jehož Apple ID se použilo k vytvoření původního certifikátu APNs.  

## <a name="change-the-mdm-authority-to-configuration-manager"></a>Změna autority MDM na Configuration Manager
Proces změny autority MDM na Configuration Manager (hybridní) zahrnuje tento postup vysoké úrovně:  
- V konzole Configuration Manageru přidejte předplatné Microsoft Intune.
- Nakonfigurujte certifikát Apple APNs pomocí stejného certifikátu APNS, který jste obnovili.
- V konzole Configuration Manageru nakonfigurujte a nasaďte nová nastavení a aplikace z nové autority MDM (hybridní).
- Při příštím připojení ke službě se zařízení synchronizují a z nové autority MDM obdrží nová nastavení.

#### <a name="to-change-the-mdm-authority-to-configuration-manager"></a>Postup změny autority MDM na Configuration Manager
1. V konzole Configuration Manageru přejděte na **Správa** &gt; **Přehled** &gt; **Cloudové služby** &gt; **Předplatné Microsoft Intune**  a přidejte předplatné Intune tím, že ho vyberte.
2. Přihlaste se do tenanta Intune, kterého jste původně použili při nastavení autority MDM v Intune, a klikněte na **Další**.
3. Vyberte **Změnit moji autoritu MDM na Configuration Manager** a klikněte na **Další**.
4. Vyberte kolekci uživatelů, aby obsahovala všechny uživatele, kteří budou dál spravovaní novou hybridní autoritou MDM.
5. Klikněte na tlačítko **Další** a dokončete průvodce. Autorita MDM je teď změněná na **Configuration Manager**.
6. Přihlaste se pomocí stejného tenanta Intune do [konzoly pro správu Microsoft Intune](http://manage.microsoft.com) a zkontrolujte, jestli se autorita MDM změnila na **Nastavit na nástroj Configuration Manager**.


## <a name="enable-ios-enrollment"></a>Povolení registrace zařízení se systémem iOS
Pokud máte zařízení s iOSem, musíte nakonfigurovat certifikát APNs v Configuration Manageru.

#### <a name="to-enable-ios-enrollment-and-configure-the-apns-certificate"></a>Povolení registrace zařízení s iOSem a konfigurace certifikátu APNs

1. **Stáhněte žádost o podepsání certifikátu**

    1. V konzole Configuration Manageru přejděte na **Správa** &gt; **Cloudové služby** &gt; **Předplatné Microsoft Intune** a vyberte **Vytvořit žádost o certifikát APNs**. Tím se otevře dialogové okno **Podat žádost o podepsání certifikátu APNs**.  
    2. Pomocí možnosti**Procházet** přejděte k cestě, kam chcete uložit nový soubor žádosti o podepsání certifikátu (.csr). Uložte soubor žádosti o podepsání certifikátu (.csr) místně.  
    3. Klikněte na tlačítko **Download**(Stáhnout). Configuration Manager stáhne a uloží nový soubor .csr služby Microsoft Intune.   

    > [!IMPORTANT]
    > Musíte stáhnout novou žádost o podepsání certifikátu. Nepoužívejte stávající soubor, nebo se postup nezdaří.  

2.  Přejděte na [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844) a přihlaste se pomocí **stejného** Apple ID, jaké se použilo k předchozímu vytvoření a obnovení certifikátu APNs, který jste použili v samostatném Intune.

    ![Přihlašovací stránka Apple Push Certificates Portalu](../media/mdm-change-apns-portal.png)

3. Vyberte certifikát APNs, který jste použili v samostatném Intune, a pak klikněte na **Renew** (Obnovit).

    ![Dialogové okno obnovení APNs](../media/mdm-change-renew-apns.png)

4. Vyberte soubor žádosti o podepsání certifikátu APNs (.csr), který máte místně stažený, a pak klikněte na **Upload** (Nahrát).

    ![Přihlašovací stránka Apple Push Certificates Portalu](../media/mdm-change-renew-apns-upload.png)
 
5. Vyberte stejné služby APNs a pak klikněte na **Download** (Stáhnout). Stáhněte si certifikát služby APN ( soubor .pem) a uložte ho místně.  

    ![Přihlašovací stránka Apple Push Certificates Portalu](../media/mdm-change-renew-apns-download.png)

6. Nahrajte obnovený certifikát APNs do hybridního tenanta pomocí stejného Apple ID jako předtím.

    1.  V konzole Configuration Manageru přejděte na **Správa** &gt; **Cloudové služby** &gt; **Předplatné Microsoft Intune** a vyberte **Konfigurovat platformy** &gt; **iOS**.  
    2.  V dialogovém okně **Vlastnosti předplatného Microsoft Intune** vyberte kartu **Certifikát APNs** a zaškrtněte políčko **Povolit zápis zařízení se systémy iOS a Mac OS X (MDM)**.  
    3.  Klikněte na tlačítko **Procházet**a přejděte na soubor certifikátu APNs (.cer) stažený od společnosti Apple. Configuration Manager zobrazí informace o tomto certifikátu APNs. Kliknutím na **OK** uložte certifikát APNs do služby Intune.  

        ![Stránka vlastností předplatného Intune – iOS](../media/mdm-change-subscription-properties-ios.png)

## <a name="enable-android-enrollment"></a>Povolení registrace zařízení s Androidem
1. V konzole Configuration Manageru přejděte na **Správa** &gt; **Cloudové služby** &gt; **Předplatné Microsoft Intune** a vyberte **Konfigurovat platformy** &gt; **Android**.  
2. Vyberte **Povolit registraci zařízení se systémem Android** a klikněte na **OK**.

### <a name="enable-windows-enrollment"></a>Povolení registrace zařízení s Windows
1. V konzole Configuration Manageru přejděte na **Správa** &gt; **Cloudové služby** &gt; **Předplatné Microsoft Intune** a vyberte **Konfigurovat platformy** &gt; **Windows**.  
2. Vyberte **Povolit registraci zařízení se systémem Windows** a klikněte na **OK**.

### <a name="enable-windows-phone-enrollment"></a>Registrace zařízení s Windows Phonem
1. V konzole Configuration Manageru přejděte na **Správa** &gt; **Cloudové služby** &gt; **Předplatné Microsoft Intune** a vyberte **Konfigurovat platformy** &gt; **Windows Phone**.  
2. Vyberte platformu, kterou chcete povolit, a klikněte na **OK**.


## <a name="next-steps"></a>Další kroky
Po dokončení změny autority MDM si projděte tyto kroky:
- Když služba Intune zjistí, že se autorita MDM tenanta změnila, odešle do všech zaregistrovaných zařízení zprávu s oznámením, aby se ohlásila a synchronizovala se službou (mimo interval pravidelně naplánovaných ohlášení). Proto po změně autority MDM pro tenanta ze samostatného Intune na hybridní se všechna zařízení, která jsou zapnutá a online, připojí ke službě, obdrží novou autoritu MDM a budou spravována hybridní autoritou. Správa a ochrana těchto zařízení se nijak nepřeruší.
- I v případě zařízení, která jsou během změny autority MDM (nebo brzy po ní) zapnutá a online, bude trvat až osm hodin (v závislosti na načasování dalšího naplánovaného pravidelného ohlášení), než budou zařízení ve službě pod novou autoritou MDM zaregistrovaná.    

  > [!IMPORTANT]    
  > V době mezi změnou autority MDM a nahráním obnoveného certifikátu APNs do nové autority se nové registrace a ohlášení zařízení s iOSem nezdaří. Proto je důležité certifikát APNs zkontrolovat a do nové autority nahrát co nejdřív po změně autority MDM.

- Uživatelé můžou na novou autoritu MDM rychle přejít ručním spuštěním ohlášení zařízení do služby. To uživatelé snadno udělají pomocí aplikace Portál společnosti a inicializováním kontroly dodržování předpisů zařízením.
- Pokud chcete zkontrolovat, jestli po ohlášení a synchronizaci zařízení se službou po změně autority MDM všechno správně funguje, vyhledejte zařízení v konzole Configuration Manageru. Zařízení, která byla dřív spravovaná pomocí Intune, se nyní zobrazují jako spravovaná zařízení v konzole Configuration Manageru.    
- Během změny autority MDM a ohlašování zařízení do služby bude zařízení přechodně offline. Aby se zajistilo, že zařízení během tohoto přechodného období zůstane chráněné a funkční, zůstanou v zařízení po dobu až sedmi dnů (nebo dokud se zařízení nepřipojí k nové autoritě MDM a neobdrží nová nastavení, která přepíší ta stávající) následující profily:
    - E-mailový profil
    - profil VPN
    - Profil certifikátu
    - Wi-Fi profil
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