---
title: Konfigurace služby Windows Update pro firmy v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si, jak upravit nastavení aktualizací softwaru na profilu a vytvořit aktualizační kanál, zkontrolujte dodržování předpisů a zjistěte, jak pozastavit aktualizace v nastavení služby Windows Update pro firmy pomocí Microsoft Intune na zařízeních s Windows 10.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
ms.openlocfilehash: 58a55c9162076af1e2e763a9799c7c1f756d80ce
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="manage-software-updates-in-intune"></a>Správa softwarových aktualizací v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows jako služba představuje způsob, jak aktualizovat zařízení s Windows 10. Ve Windows 10 obsahují nové aktualizace funkcí a aktualizace pro zvýšení kvality obsah všech předchozích aktualizací. Pokud si nainstalujete nejnovější aktualizaci, máte jistotu, že jsou vaše zařízení s Windows 10 aktuální. Na rozdíl od předchozích verzí Windows je teď nutné nainstalovat celou aktualizaci (a ne jenom její část).

Služba Windows Update pro firmy vám zjednodušuje správu aktualizací. Nemusíte tak schvalovat jednotlivé aktualizace pro skupiny zařízení. Konfigurací vhodné strategie zavádění aktualizací budete mít pod kontrolou řízení rizik ve svém prostředí. Služba Windows Update při tom zajistí, aby se aktualizace nainstalovaly ve správný čas. Prostřednictvím Microsoft Intune můžete na zařízeních nakonfigurovat nastavení aktualizací a pozdržet instalaci aktualizací. V Intune nejsou uložené samotné aktualizace, ale jenom přiřazení zásad aktualizací. Zařízení kvůli aktualizacím přistupují přímo k webu Windows Update. Použijte Intune ke konfiguraci a správě **aktualizačních kanálů Windows 10**. Aktualizační kanál obsahuje skupinu nastavení, která konfigurují, kdy a jak se budou aktualizace Windows 10 instalovat. Můžete třeba nakonfigurovat následující nastavení:

- **Kanál pro údržbu Windows 10**: Zvolte kanál pro údržbu, ze kterého mají skupiny zařízení přijímat aktualizace. K dispozici jsou tyto kanály: 
  - Půlroční kanál
  - Půlroční kanál (vybraní uživatelé)
  - Windows Insider – Fast
  - Windows Insider – Slow
  - Windows Insider – Release 
      
  Podrobnosti o dostupných kanálech pro údržbu najdete v tématu [Základní informace o Windows jako službě](https://docs.microsoft.com/en-us/windows/deployment/update/waas-overview#servicing-channels).
- **Nastavení odložení**: Nakonfigurujte nastavení odložení aktualizací ke zpoždění instalací aktualizací pro skupiny zařízení. Tato nastavení vám umožní rozfázovat zavádění aktualizací, abyste mohli kontrolovat jeho průběh.
- **Pozastavení**: Odložte instalaci aktualizací, pokud kdykoli během zavádění aktualizací zjistíte problém.
- **Časové období údržby**: Konfigurujte hodiny, kdy se můžou aktualizace instalovat.
- **Typ aktualizace**: Vyberte typy aktualizací, které se nainstalují. Například aktualizace pro zvýšení kvality, aktualizace funkcí nebo ovladače.
- **Chování při instalaci**: Nastavuje, jak se aktualizace nainstaluje. Třeba jestli se zařízení po instalaci automaticky restartuje.
- **Partnerské stahování**: Můžete vybrat, jestli se má nakonfigurovat partnerské stahování. Pokud ho nakonfigurujete, pak po dokončení stahování aktualizace jedním zařízením můžou aktualizaci z tohoto zařízení stahovat ostatní zařízení. Toto nastavení proces stahování urychlí.

Po vytvoření aktualizačních kanálů je přiřadíte skupinám zařízení. Pomocí aktualizačních kanálů můžete vytvořit strategii aktualizace, která odráží vaše firemní potřeby. Další informace najdete v tématu o [správě aktualizací pomocí Windows Update pro firmy](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="before-you-start"></a>Než začnete

- Abyste mohli aktualizovat počítače s Windows 10, musí na nich být aspoň Windows 10 Pro s aktualizací Windows Anniversary Update.

- Windows Update podporuje následující verze Windows 10:
  - Windows 10
  - Windows 10 Team (pro zařízení Surface Hubu)
  - [Windows Holographic for Business](#windows-holographic-for-business-support)

  Zařízení s Windows 10 Mobile nejsou podporovaná.

- Na zařízení s Windows musí být **Zpětná vazba a diagnostika** > **Diagnostika a data o používání** nastavené aspoň na **Základní**.

    ![Nastavení Windows pro diagnostiku a data o používání](./media/telemetry-basic.png)

    Toto nastavení můžete nakonfigurovat ručně nebo můžete použít profil omezení zařízení Intune pro Windows 10 a novější. To uděláte tak, že nastavení **Obecné** > **Odeslání diagnostických dat** nakonfigurujete aspoň na možnost **Základní**. Další informace o profilech zařízení najdete v tématu [Konfigurace nastavení omezení zařízení](device-restrictions-configure.md).

- V konzole pro správu Intune jsou čtyři nastavení, která řídí chování aktualizací softwaru. Tato nastavení jsou součástí zásad obecné konfigurace pro počítače a mobilní zařízení s Windows 10:
  - **Povolit automatické aktualizace**
  - **Povolit předběžné verze funkcí**
  - **Den plánované instalace**
  - **Čas plánované instalace**

  Portál Azure Classic má také omezený počet dalších nastavení aktualizací Windows 10 v profilu konfigurace zařízení. Pokud máte některá z těchto nastavení nakonfigurovaná při migraci na Azure Portal, důrazně doporučujeme, abyste udělali toto:

1. Na portále Azure Portal vytvořte aktualizační kanály Windows 10 s nastaveními, která potřebujete. Nastavení **Povolit funkce v předběžné verzi** není na portálu Azure Portal podporované, protože už pro nejnovější buildy Windows 10 neplatí. Při vytvoření aktualizačních kanálů můžete nakonfigurovat ostatní tři nastavení i další nastavení aktualizace Windows 10.

   > [!NOTE]
   > Nastavení aktualizací Windows 10 vytvořená na klasickém portálu se na Azure Portalu po migraci nezobrazí. Tato nastavení se ale použijí. Pokud jste některá z nich migrovali a migrované zásady z Azure Portalu upravíte, tato nastavení se ze zásad odeberou.

2. Odstraňte nastavení aktualizací na klasickém portálu. Po migraci na Azure Portal a přidání stejných nastavení do aktualizačního kanálu musíte nastavení na portálu Classic odstranit, aby se zabránilo možným konfliktům zásad. Pokud je například stejné nastavení nakonfigurované s odlišnými hodnotami, dojde ke konfliktu. Ten ale nejde snadno rozpoznat, protože nastavení nakonfigurované na portálu Classic se na Azure Portalu nezobrazuje.

## <a name="create-and-assign-update-rings"></a>Vytvoření a přiřazení aktualizačních kanálů

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a potom vyberte **Microsoft Intune**.
3. Vyberte **Aktualizace softwaru** > **Aktualizační kanály Windows 10** > **Vytvořit**.
4. Zadejte název a popis (volitelný) a potom zvolte **Konfigurovat**.
5. V části **Nastavení** zadejte například tyto informace:

   - **Kanál pro údržbu**: Nastavte kanál, ze kterého má zařízení přijímat aktualizace Windows.
   - **Aktualizace produktů Microsoftu**: Zvolte, jestli se mají kontrolovat aktualizace aplikací z webu Microsoft Update.
   - **Ovladače Windows**: Zvolte, jestli chcete při aktualizacích vyloučit ovladače Windows Update.
   - **Chování automatické aktualizace**: Vyberte, jak se mají automatické aktualizace instalovat a kdy se má zařízení restartovat. Podrobnosti najdete v popisu nastavení [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#update-allowautoupdate).
     - **Frekvence automatického chování**: Pokud jako chování aktualizací vyberete **Automaticky nainstalovat a restartovat v plánovaném čase**, zobrazí se toto nastavení. Pomocí něj můžete naplánovat, kdy se aktualizace nainstalují (můžete určit týden, den a čas).

   - **Kontroly při restartu**:Ve výchozím nastavení jsou povoleny. Po restartu zařízení se provádí některé kontroly, například zjišťování aktivních uživatelů, stavu baterie, spuštěných her a další. Pokud tyto kontroly chcete přeskočit, zvolte **Přeskočit**.

   - **Odložení aktualizace kvality (ve dnech)**: Zadejte, kolik dní se budou odkládat aktualizace kvality. Příjem těchto aktualizací kvality můžete odložit až o 30 dní od jejich vydání.

     Aktualizace kvality jsou obecně opravy a vylepšení stávajících funkcí Windows a vydávají se první úterý v každém měsíci. Microsoft je ale může vydávat i kdykoli jindy. Můžete určit, jestli a jak dlouho chcete přijímání aktualizací kvality po jejich zveřejnění na webu Windows Update odkládat.

   - **Odložení aktualizace funkcí (ve dnech)**: Zadejte, kolik dní se budou odkládat aktualizace funkcí. Příjem těchto aktualizací funkcí můžete odložit až o 180 dní od jejich vydání.

     Aktualizace funkcí jsou zpravidla nové funkce pro Windows. Když nakonfigurujete nastavení **Kanál pro údržbu**, můžete určit, jestli a na jak dlouho chcete odkládat příjem aktualizací funkcí po tom, co je Microsoft zpřístupní na webu Windows Update.

     Například: **Kanál pro údržbu je nastavený na Půlroční kanál (cílený) a odložení aktualizace je nastavené na 30 dní**: Řekněme, že aktualizace funkcí X je nejdříve veřejně dostupná na webu Windows Update jako Půlroční kanál (cílený) v lednu. Zařízení aktualizaci přijme až v únoru – o 30 dní později.

     **Kanál pro údržbu je nastavený na Půlroční kanál a odložení aktualizace je nastavené na 30 dní**: Řekněme, že aktualizace funkcí X je nejdříve veřejně dostupná na webu Windows Update jako Půlroční kanál (cílený) v lednu. O čtyři měsíce později, v dubnu, je Aktualizace funkcí X vydána do Půlročního kanálu. Zařízení přijme aktualizaci funkcí 30 dní po tomto vydání do Půlročního kanálu a bude se aktualizovat v květnu.

   - **Režim stahování pro optimalizaci doručení**: Zvolte metodu, pro kterou budou zařízení stahovat aktualizace Windows. Podrobnosti najdete v části [DeliveryOptimization/DODownloadMode](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#download-mode).

6. Po dokončení zvolte **OK**. V podokně **Vytvořit aktualizační kanál** vyberte **Vytvořit**.

Nový aktualizační kanál se zobrazí v seznamu aktualizačních kanálů.

1. Pokud chcete přiřadit kanál, vyberte kanál ze seznamu aktualizačních kanálů a pak na kartě <*název kanálu*> vyberte **Přiřazení**.
2. Na další kartě zvolte **Vybrat skupiny, které se zahrnou** a pak vyberte skupiny, kterým chcete kanál přiřadit.
3. Až s tím budete hotoví, zvolte **Vybrat**. Tím přiřazení dokončíte.

## <a name="update-compliance-reporting"></a>Generování sestav dodržování předpisů pro aktualizace
Dodržování předpisů pro aktualizace můžete sledovat v Intune nebo pomocí bezplatného řešení v Operations Management Suite (OMS), které se jmenuje Update Compliance.

### <a name="review-update-compliance-in-intune"></a>Kontrola dodržování předpisů pro aktualizace v Intune 
<!-- 1352223 -->
Zkontrolujte sestavu zásad, abyste viděli stav nasazení pro nakonfigurované aktualizační kanály Windows 10.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Aktualizace softwaru** > **Přehled**. Uvidíte obecné informace o stavu všech aktualizačních kanálů, které jste přiřadili.
4. Otevřete jednu z těchto sestav:

   **Pro všechny aktualizační kanály nasazení**:  
   1. V podokně **Aktualizace softwaru** > **Aktualizační kanály Windows 10**
   2. V **sekci Monitorování** zvolte **Stav nasazení podle kruhu aktualizace**.

   **Pro konkrétní aktualizační kanály nasazení**:  
   1. V podokně **Aktualizace softwaru** > **Aktualizační kanály Windows 10** zvolte aktualizační kanál nasazení, který chcete zkontrolovat.
   2. Pokud chcete zobrazit podrobnější informace o aktualizačním kanálu, v sekci **Monitorování** zvolte z těchto sestav:
      - **Stav zařízení**
      - **Stav uživatele**

### <a name="review-update-compliance-using-oms"></a>Kontrola dodržování předpisů pro aktualizace pomocí OMS
Zavádění aktualizací Windows 10 můžete sledovat pomocí bezplatného řešení v Operations Management Suite (OMS), které se jmenuje Update Compliance. Podrobnosti najdete v článku o [monitorování aktualizací Windows pomocí Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Když toto řešení použijete, můžete nasadit komerční ID do libovolného z vašich zařízení s Windows 10 spravovaných pomocí Intune, pro které chcete generovat sestavy o dodržování předpisů pro aktualizace.

V konzole Intune můžete ke konfiguraci komerčního ID použít nastavení OMA-URI vlastní zásady. Podrobnosti najdete v článku [Nastavení zásad Intune pro zařízení s Windows 10 v Microsoft Intune](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune).   

Cesta OMA-URI (s rozlišováním velkých a malých písmen) pro konfiguraci komerčního ID je: ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID

V nastavení **Přidat nebo upravit nastavení OMA-URI** můžete použít třeba následující hodnoty:

- **Název nastavení**: Komerční ID pro analýzu Windows
- **Popis nastavení**: Konfigurace komerčního ID pro řešení pro analýzu Windows
- **OMA-URI** (s rozlišováním velkých a malých písmen): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Datový typ:** Řetězec
- **Hodnota**: <*Použijte identifikátor GUID zobrazený na kartě Telemetrie Windows v pracovním prostoru OMS*>

![Nastavení OMA-URI – Upravit řádek](./media/commID-edit.png)

> [!NOTE]
> Podrobnosti o MS DM Serveru najdete v tématu [Poskytovatel konfiguračních služeb DMClient](https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="pause-updates"></a>Pozastavení aktualizací
Je možné pozastavit příjem aktualizací funkcí nebo aktualizací kvality zařízením až na 35 dní od okamžiku pozastavení aktualizací. Po uplynutí maximálního počtu dní funkce pozastavení automaticky vyprší a zařízení zkontroluje dostupné aktualizace ve Windows Update. Po této kontrole můžete aktualizace znovu pozastavit.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Aktualizace softwaru** > **Aktualizační kanály Windows 10**.
4. V seznamu aktualizačních kanálů vyberte kanál, který chcete pozastavit, a potom zvolte **...**  > **Pozastavit kvalitu** > nebo **Pozastavit funkci** v závislosti na typu aktualizací, které se mají pozastavit.

> [!IMPORTANT]
> Když vydáte příkaz k pozastavení, zařízení ho obdrží při dalším přihlášení ke službě. Je možné, že před přihlášením ke službě nainstalují plánovanou aktualizaci.
> Kromě toho platí, že pokud je cílové zařízení při vydání příkazu k pozastavení vypnuté, může po zapnutí stáhnout a nainstalovat plánované aktualizace před tím, než se přihlásí k Intune.

## <a name="windows-holographic-for-business-support"></a>Podpora Windows Holographic for Business

Windows Holographic for Business podporuje následující nastavení:

- **Chování automatické aktualizace**
- **Aktualizace produktů Microsoftu**
- **Kanál pro údržbu**