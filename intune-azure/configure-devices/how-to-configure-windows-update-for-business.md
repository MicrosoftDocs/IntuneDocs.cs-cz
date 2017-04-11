---
title: "Konfigurace nastavení Windows Update pro firmy – Intune | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Zjistěte, jak v Intune konfigurovat nastavení Windows Update pro firmy k řízení aktualizací zařízení s Windows 10."
keywords: 
author: dougeby
ms.author: dougeby
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08f659cf-715e-4e10-9ab2-1bac3c6f2366
ms.reviewer: coryfe
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 911d2887791cf16d4290c3ac5189aa44086f4603
ms.openlocfilehash: 5e2516611b933bb9c74c2b8dc973f85e1d82237f
ms.lasthandoff: 03/11/2017


---

# <a name="how-to-configure-windows-update-for-business-settings-with-microsoft-intune"></a>Jak konfigurovat nastavení Windows Update pro firmy pomocí Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

## <a name="introduction"></a>Úvod
Windows jako služba představuje nový způsob poskytování aktualizací pro Windows 10. Od verze Windows 10 budou všechny nové aktualizace funkcí a aktualizace pro zvýšení kvality zahrnovat obsah všech předchozích aktualizací. To znamená, že pokud si nainstalujete nejnovější aktualizaci, máte jistotu, že jsou vaše zařízení s Windows 10 zcela aktuální. Na rozdíl od předchozích verzí Windows je teď nutné nainstalovat celou aktualizaci (a ne jenom její část).

Pomocí služby Windows Update pro firmy můžete zjednodušit správu aktualizací, abyste nemuseli schvalovat jednotlivé aktualizace pro skupiny zařízení. Můžete nakonfigurovat strategii zavádění aktualizací, abyste měli pod kontrolou řízení rizik ve vašem prostředí, a služba Windows Update zajistí, aby se aktualizace nainstalovaly ve správný čas. Prostřednictvím Microsoft Intune můžete na zařízeních nakonfigurovat nastavení aktualizací a pozdržet instalaci aktualizací. V Intune nejsou uložené samotné aktualizace, ale jenom přiřazení zásad aktualizací. Zařízení získávají aktualizace přímo ze služby Windows Update. Pomocí Intune můžete nakonfigurovat a spravovat **aktualizační kanály Windows 10**. Aktualizační kanál obsahuje skupinu nastavení, která konfigurují, kdy a jak se budou aktualizace Windows 10 instalovat. Můžete třeba nakonfigurovat:

- **Obslužná větev Windows 10**: Zvolte, jestli mají skupiny zařízení dostávat aktualizace z Aktuální větve nebo z Aktuální větve pro firmy.  
- **Nastavení odložení**: Nakonfigurujte nastavení odložení aktualizací ke zpoždění instalací aktualizací pro skupiny zařízení. Budete pak mít rozfázované zavádění aktualizací, abyste mohli kontrolovat jeho průběh.
- **Pozastavení**: Odložte instalaci aktualizací, pokud kdykoli během zavádění aktualizací zjistíte problém.
- **Časové období údržby**: Konfigurujte hodiny, kdy se můžou aktualizace instalovat.
- **Typ aktualizace**: Vyberte typy aktualizací, které se nainstalují. Například aktualizace pro zvýšení kvality, aktualizace funkcí nebo ovladače.
- **Chování při instalaci**: Nastavuje, jak se aktualizace nainstaluje. Třeba jestli se zařízení po instalaci automaticky restartuje.
- **Partnerské stahování**: Můžete určit, jestli se má nakonfigurovat partnerské stahování. Pokud ho nakonfigurujete, pak po dokončení stahování aktualizace jedním zařízením můžou aktualizaci z tohoto zařízení stahovat ostatní zařízení. Tím se proces stahování urychlí.

Po vytvoření aktualizačních kanálů je přiřadíte skupinám zařízení. Pomocí aktualizačních kanálů můžete vytvořit strategii aktualizace, která odráží vaše firemní potřeby. Další informace najdete v tématu o [správě aktualizací pomocí Windows Update pro firmy](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="before-you-start"></a>Než začnete

- Abyste mohli aktualizovat počítače s Windows 10, musí na nich být aspoň Windows 10 Pro s aktualizací Windows Anniversary Update.

- Windows Update podporuje následující verze Windows 10:
    - Windows 10
    - Windows 10 Team (pro zařízení Surface Hubu)

 Zařízení se systémem Windows 10 Mobile a Windows 10 Holographic nejsou podporovaná.

- Na zařízení s Windows musí být **Zpětná vazba a diagnostika** > **Diagnostika a data o používání** nastavené aspoň na **Základní**.

    ![Nastavení Windows pro diagnostiku a data o používání](./media/telemetry-basic.png)

    Toto nastavení můžete nakonfigurovat ručně nebo můžete použít profil omezení zařízení Intune pro Windows 10 a novější. To uděláte tak, že nastavení **Obecné** > **Odeslání diagnostických dat** nakonfigurujete aspoň na možnost **Základní**. Další informace o profilech zařízení najdete v tématu [Konfigurace nastavení omezení zařízení](/intune-azure/configure-devices/how-to-configure-device-restrictions).

- V klasické konzole pro správu Intune jsou čtyři nastavení, která řídí chování aktualizací softwaru. Tato nastavení jsou součástí zásad obecné konfigurace pro počítače a mobilní zařízení s Windows 10:
    - **Povolit automatické aktualizace**
    - **Povolit předběžné verze funkcí**
    - **Den plánované instalace**
    - **Čas plánované instalace**

  Tato klasická konzola má také omezený počet dalších nastavení aktualizace Windows 10 v profilu konfigurace zařízení. Pokud máte některé z těchto nastavení v klasické konzole pro správu Intune nakonfigurované při migraci na portál Azure Portal, důrazně doporučujeme, abyste udělali toto:

1. Na portále Azure Portal vytvořte aktualizační kanály Windows 10 s nastaveními, která potřebujete. Nastavení **Povolit funkce v předběžné verzi** není na portálu Azure Portal podporované, protože už pro nejnovější buildy Windows 10 neplatí. Při vytvoření aktualizačních kanálů můžete nakonfigurovat ostatní tři nastavení i další nastavení aktualizace Windows 10.

  > [!NOTE]
  > Nastavení aktualizace Windows 10 vytvořená v klasické konzole se na portále Azure Portal po migraci nevytvoří. Tato nastavení se ale dál používají. Pokud jste některé z těchto nastavení migrovali a migrované zásady z portálu Azure Portal upravíte, tato nastavení se ze zásad odeberou.

2. Odstraňte nastavení aktualizace v klasické konzole. Po migraci na portál Azure Portal a přidání stejných nastavení do aktualizačního kanálu musíte nastavení na klasickém portálu odstranit, aby se zabránilo možným konfliktům zásad. Pokud je třeba stejné nastavení nakonfigurované s různými hodnotami, dojde ke konfliktu, který nepůjde snadno poznat, protože nastavení nakonfigurované v klasické konzole se na portálu Azure Portal nezobrazuje.

## <a name="how-to-create-and-assign-update-rings"></a>Vytvoření a přiřazení aktualizačních kanálů

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Aktualizace softwaru**.
4. V okně **Aktualizace softwaru** zvolte **Spravovat** > **Aktualizační kanály Windows 10**.
5. V okně se seznamem aktualizačních kanálů zvolte **Vytvořit**.
6. V okně **Vytvořit aktualizační kanál** zadejte název a volitelný popis aktualizačního kanálu a pak zvolte **Nastavení**.
7. V okně **Nastavení** nakonfigurujte následující údaje:
    - **Obslužná větev**: Nastavte větev, pro kterou bude zařízení dostávat aktualizace Windows (Aktuální větev nebo Aktuální větev pro firmy).
    - **Aktualizace Microsoft**: Zvolte, jestli se mají kontrolovat aktualizace aplikací z webu Microsoft Update.
    - **Ovladače Windows**: Zvolte, jestli chcete při aktualizacích vyloučit ovladače Windows Update.
    - **Chování automatické aktualizace**: Zvolte, jak se má spravovat chování automatické aktualizace pro kontrolu, stahování a instalaci aktualizací. Podrobnosti najdete v popisu nastavení [Update/AllowAutoUpdate](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#update-allowautoupdate).
    - **Odložení aktualizace kvality (ve dnech)**: Zadejte, kolik dní budou aktualizace kvality odložené. Příjem těchto aktualizací kvality můžete odložit až o 30 dní od jejich vydání.  

      Aktualizace kvality jsou obecně opravy a vylepšení stávajících funkcí Windows a jsou obvykle vydávané první úterý v každém měsíci. Microsoft je ale může vydávat i kdykoli jindy. Můžete definovat, jestli a jak dlouho chcete přijímání aktualizací kvality po jejich vydání odkládat.
    - **Odložení aktualizace funkcí (ve dnech)**: Zadejte, kolik dní budou aktualizace funkcí odložené. Příjem těchto aktualizací funkcí můžete odložit až o 180 dní od jejich vydání.

    Aktualizace funkcí jsou obecně nové funkce pro Windows. Po dokončení konfigurace nastavení **Obslužná větev** (**CB** (Aktuální větev) nebo **CBB** (Aktuální větev pro firmy) pak můžete definovat, jestli a na jak dlouho chcete odložit příjem aktualizací funkcí po tom, co je Microsoft zpřístupní na webu Windows Update.

    Například:  
    **Pokud je obslužná větev nastavená na CB (Aktuální větev) a doba odložení je 30 dní**: Řekněme, že aktualizace funkce X je poprvé veřejně dostupná na webu Windows Update jako CB (Aktuální větev) v lednu. Zařízení aktualizaci přijme až v únoru – o 30 dní později.

    **Pokud je obslužná větev nastavená na CBB (Aktuální větev pro firmy) a doba odložení je 30 dní**: Řekněme, že aktualizace funkce X je poprvé veřejně dostupná na webu Windows Update jako CB (Aktuální větev) v lednu. O čtyři měsíce později, v dubnu, je aktualizace funkce X vydána pro CBB (Aktuální větev pro firmy). Zařízení obdrží aktualizaci funkce 30 dnů po vydání této Aktuální větve pro firmy a aktualizuje se v květnu.

    - **Optimalizace doručení**: Zvolte metodu, pro kterou budou zařízení stahovat aktualizace Windows. Podrobnosti najdete v popisu nastavení [DeliveryOptimization/DEDownloadMode](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#deliveryoptimization-dodownloadmode).
8. Po dokončení klikněte na **OK** a pak v okně **Vytvořit aktualizační kanál** klikněte na **Vytvořit**.

Nový aktualizační kanál se zobrazí v seznamu aktualizačních kanálů.

1. Pokud chcete přiřadit kanál, vyberte kanál ze seznamu aktualizačních kanálů a pak na kartě <*název kanálu*> vyberte **Přiřazení**.
2. Na další kartě zvolte **Vybrat skupiny** a pak vyberte skupiny, kterým chcete kanál přiřadit.
3. Až s tím budete hotoví, zvolte **Vybrat**. Tím přiřazení dokončíte.



## <a name="update-compliance-reporting"></a>Generování sestav dodržování předpisů pro aktualizace
Zavádění aktualizací Windows 10 můžete sledovat pomocí bezplatného řešení v Operations Management Suite (OMS), které se jmenuje Update Compliance. Podrobnosti najdete v článku o [monitorování aktualizací Windows pomocí Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Když toto řešení použijete, můžete nasadit komerční ID do libovolného z vašich zařízení s Windows 10 spravovaných pomocí Intune, pro které chcete generovat sestavy o dodržování předpisů pro aktualizace.

V konzole Intune můžete ke konfiguraci komerčního ID použít nastavení OMA-URI vlastní zásady. Podrobnosti najdete v článku [Nastavení zásad Intune pro zařízení s Windows 10 v Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

Cesta OMA-URI (s rozlišováním velkých a malých písmen) pro konfiguraci komerčního ID je: ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID

V nastavení **Přidat nebo upravit nastavení OMA-URI** můžete použít třeba následující hodnoty:

- **Název nastavení**: Komerční ID pro analýzu Windows
- **Popis nastavení**: Konfigurace komerčního ID pro řešení pro analýzu Windows
- **Datový typ:** Řetězec
- **OMA-URI** (s rozlišováním velkých a malých písmen): ./Vendor/MSFT/DMClient/Provider/ProviderID/CommercialID
- **Hodnota**: <*Použijte identifikátor GUID zobrazený na kartě Telemetrie Windows v pracovním prostoru OMS*>

![Nastavení Windows pro diagnostiku a data o používání](./media/commID.png)

<!--
1. Sign into the Azure portal.
2. Choose **More Services** > **Monitoring + Management** > **Intune**.
3. On the **Intune** blade, choose **Software Updates**.
4. On the **Software Updates** blade, choose **Overview**. From here you can see general information about the status of any update rings you assigned.
4. On the **Windows 10 Updates** blade, choose **Monitor** > **Update ring deployment for devices**, **Update ring deployment for users**, or **Per-setting deployment state** to view more detailed information about update ring assignments.
-->





## <a name="how-to-pause-updates"></a>Pozastavení aktualizací
Je možné pozastavit příjem aktualizací funkcí nebo aktualizací kvality zařízením až na 35 dní od okamžiku pozastavení aktualizací. Po uplynutí maximálního počtu dní funkce pozastavení automaticky vyprší a zařízení zkontroluje dostupné aktualizace ve Windows Update. Po této kontrole můžete aktualizace znovu pozastavit.
1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Aktualizace softwaru**.
4. V okně **Aktualizace softwaru** zvolte **Spravovat** > **Aktualizační kanály Windows 10**.
5. V okně zobrazujícím seznam aktualizačních kanálů zvolte kanál, který chcete pozastavit, a pak zvolte **...**  >  **Pozastavit kvalitu** > nebo **Pozastavit funkci** v závislosti na typu aktualizací, které chcete pozastavit.

> [!IMPORTANT]
> Když vydáte příkaz k pozastavení, zařízení ho obdrží při dalším přihlášení ke službě. Je možné, že před přihlášením ke službě nainstalují plánovanou aktualizaci.
> Kromě toho platí, že pokud je cílové zařízení při vydání příkazu k pozastavení vypnuté, může po zapnutí stáhnout a nainstalovat plánované aktualizace před tím, než se přihlásí k Intune.

