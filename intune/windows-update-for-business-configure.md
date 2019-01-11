---
title: Konfigurace služby Windows Update pro firmy v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si, jak upravit nastavení aktualizací softwaru na profilu a vytvořit aktualizační kanál, zkontrolujte dodržování předpisů a zjistěte, jak pozastavit aktualizace v nastavení služby Windows Update pro firmy pomocí Microsoft Intune na zařízeních s Windows 10.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/09/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
search.appverid: MET150
ms.openlocfilehash: c0ab63ab8832db69ecf27361dc4fe4c9a1196db3
ms.sourcegitcommit: 4a7421470569ce4efe848633bd36d5946f44fc8d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2019
ms.locfileid: "54203480"
---
# <a name="manage-software-updates-in-intune"></a>Správa softwarových aktualizací v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Windows jako služba představuje způsob, jak aktualizovat zařízení s Windows 10. Ve Windows 10 obsahují nové aktualizace funkcí a aktualizace pro zvýšení kvality obsah všech předchozích aktualizací. Pokud si nainstalujete nejnovější aktualizaci, máte jistotu, že jsou vaše zařízení s Windows 10 aktuální. Na rozdíl od předchozích verzí Windows je teď nutné nainstalovat celou aktualizaci (a ne jenom její část).

Služba Windows Update pro firmy vám zjednodušuje správu aktualizací. Nemusíte tak schvalovat jednotlivé aktualizace pro skupiny zařízení. Konfigurací vhodné strategie zavádění aktualizací budete mít pod kontrolou řízení rizik ve svém prostředí. Služba Windows Update při tom zajistí, aby se aktualizace nainstalovaly ve správný čas. Prostřednictvím Microsoft Intune můžete na zařízeních nakonfigurovat nastavení aktualizací a pozdržet instalaci aktualizací. V Intune nejsou uložené samotné aktualizace, ale jenom přiřazení zásad aktualizací. Zařízení kvůli aktualizacím přistupují přímo k webu Windows Update. Použijte Intune ke konfiguraci a správě **aktualizačních kanálů Windows 10**. Aktualizační kanál obsahuje skupinu nastavení, která konfigurují, kdy a jak se budou aktualizace Windows 10 instalovat. Můžete například nakonfigurovat následující nastavení:

- **Kanál pro údržbu Windows 10**: Zvolte kanál pro údržbu ze kterého mají skupiny zařízení přijímat aktualizace. K dispozici jsou tyto kanály: 
  - Půlroční kanál
  - Půlroční kanál (vybraní uživatelé)
  - Windows Insider – Fast
  - Windows Insider – Slow
  - Windows Insider – Release 
      
  Podrobnosti o dostupných kanálech pro údržbu najdete v tématu [Základní informace o Windows jako službě](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels).
- **Nastavení odložení**: Nakonfigurujte nastavení odložení aktualizací ke zpoždění instalací aktualizací pro skupiny zařízení. Tato nastavení vám umožní rozfázovat zavádění aktualizací, abyste mohli kontrolovat jeho průběh.
- **Pozastavení**: Pokud se vyskytl problém během zavádění aktualizací, můžete odložit instalaci aktualizací. 
- **Časové období údržby**: Konfigurujte hodiny, ve kterých se můžou aktualizace instalovat.
- **Typ aktualizace**: Vyberte typy aktualizací, které se nainstalují. Například aktualizace pro zvýšení kvality, aktualizace funkcí nebo ovladače.
- **Chování při instalaci**: Nakonfiguruje, jak se aktualizace nainstaluje. Třeba jestli se zařízení po instalaci automaticky restartuje.
- **Partnerské stahování**: Můžete nakonfigurovat partnerské stahování. Pokud ho nakonfigurujete, pak po dokončení stahování aktualizace jedním zařízením můžou aktualizaci z tohoto zařízení stahovat ostatní zařízení. Toto nastavení proces stahování urychlí.

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

    Buď můžete toto nastavení nakonfigurovat ručně, nebo použít profil Intune pro Windows 10 a novější (**Omezení zařízení** > **Vytváření sestav a telemetrie** > nastavte **Sdílet data o využití**  na alespoň **Základní**). Další informace o profilech zařízení najdete v tématu [Konfigurace nastavení omezení zařízení](device-restrictions-configure.md).

- Portál Azure Classic má také omezený počet dalších nastavení aktualizací Windows 10 v profilu konfigurace zařízení. Pokud jsou během migrace na Azure Portal některá z těchto nastavení nakonfigurovaná, důrazně doporučujeme postupovat takto:

  1. Na portále Azure Portal vytvořte aktualizační kanály Windows 10 s nastaveními, která potřebujete. Nastavení **Povolit funkce v předběžné verzi** není na webu Azure Portal podporované, protože už pro nejnovější buildy Windows 10 neplatí. Při vytváření aktualizačních kanálů můžete nakonfigurovat ostatní nastavení i další nastavení aktualizací Windows 10.

   > [!NOTE]
   > Nastavení aktualizací Windows 10 vytvořená na klasickém portálu se na Azure Portalu po migraci nezobrazí. Tato nastavení se ale použijí. Pokud jste některá z nich migrovali a migrované zásady z Azure Portalu upravíte, tato nastavení se ze zásad odeberou.

  2. Odstraňte nastavení aktualizací na klasickém portálu. Po migraci na Azure Portal a přidání stejných nastavení do aktualizačního kanálu odstraňte tato nastavení na portálu Classic, aby se zabránilo možným konfliktům zásad. Pokud je například stejné nastavení nakonfigurované s odlišnými hodnotami, dojde ke konfliktu. Ten ale nejde snadno rozpoznat, protože nastavení nakonfigurované na portálu Classic neexistuje na webu Azure Portal.

## <a name="create-and-assign-update-rings"></a>Vytvoření a přiřazení aktualizačních kanálů

1. Na webu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Aktualizace softwaru** > **Aktualizační kanály Windows 10** > **Vytvořit**.
3. Zadejte název a popis (volitelný) a potom zvolte **Konfigurovat**.
4. V části **Nastavení** zadejte například tyto informace:  

   **Aktualizovat nastavení**  
   - **Kanál pro údržbu**: Nastavte kanál, ze kterého má zařízení přijímat aktualizace Windows.
   - **Aktualizace produktů Microsoftu**: Zvolte kontrolovat aktualizace aplikací z webu Microsoft Update.
   - **Ovladače Windows**: Zvolte při aktualizacích vyloučit ovladače Windows Update.
   - **Odložení aktualizace kvality (ve dnech)**: Zadejte počet dní, pro které budou aktualizace kvality odložené. Příjem těchto aktualizací kvality můžete odložit až o 30 dní od jejich vydání.

     Aktualizace pro zvýšení kvality jsou zpravidla opravy a vylepšení stávajících funkcí Windows a vydávají se druhé úterý v každém měsíci. Aktualizace pro zvýšení kvality přes Windows Update pro firmy dostávají jen tyto aktualizace (vydání „B“), ačkoli Microsoft může kdykoli vydat jiné aktualizace. Můžete určit, jestli a na jak dlouho chcete odložit příjem aktualizací pro zvýšení kvality po jejich zpřístupnění ve službě Windows Update. Další informace najdete v článku o [nasazení aktualizací pomocí služby Windows Update pro firmy](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb).

   - **Odložení aktualizace funkcí (ve dnech)**: Zadejte počet dní, pro které budou aktualizace funkcí odložené. Příjem těchto aktualizací funkcí můžete odložit až o 180 dní od jejich vydání.

     Aktualizace funkcí jsou zpravidla nové funkce pro Windows. Po konfiguraci nastavení **Kanál pro údržbu** můžete určit, jestli a na jak dlouho chcete odložit příjem aktualizací funkcí po jejich zpřístupnění ve službě Windows Update.

     Příklad: **Pokud kanál pro údržbu je nastavený na půlroční kanál (cílený) a odložení je 30 dní**: Řekněme, že aktualizace funkcí X je nejdříve veřejně dostupná na webu Windows Update jako půlroční kanál (cílený) v lednu. Zařízení tuto aktualizaci přijme až v únoru – o 30 dní později.

     **Pokud kanál pro údržbu je nastavený na půlroční kanál a odložení je 30 dní**: Řekněme, že aktualizace funkcí X je nejdříve veřejně dostupná na webu Windows Update jako půlroční kanál (cílený) v lednu. O čtyři měsíce později, v dubnu, je Aktualizace funkcí X vydána do Půlročního kanálu. Zařízení přijme aktualizaci funkcí 30 dní po tomto vydání do Půlročního kanálu a bude se aktualizovat v květnu.  

   **Nastavení činnosti koncového uživatele**
   
   - **Chování automatické aktualizace**: Zvolte, jak automatické aktualizace jsou nainstalovány, pokud má zařízení restartovat. Podrobnosti najdete v popisu nastavení [Update/AllowAutoUpdate](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider#update-allowautoupdate).

     Nastavení *obnovit výchozí* obnoví původní nastavení automatických aktualizací na počítačů s Windows 10, které běží *aktualizace z října 2018* nebo novější.  

     - **Frekvence automatického chování**: Pokud vyberete **automaticky nainstalovat a restartovat v naplánovaném čase** chování aktualizací, toto nastavení se zobrazí. Pomocí něj můžete naplánovat, kdy se aktualizace nainstalují (můžete určit týden, den a čas).

   - **Kontroly při restartu**: Ve výchozím nastavení zapnuté. Po restartu zařízení se provádí některé kontroly, například zjišťování aktivních uživatelů, stavu baterie, spuštěných her a další. Pokud tyto kontroly chcete přeskočit, zvolte **Přeskočit**.

   - **Brání uživateli ve pozastavení aktualizací Windows**: Ve výchozím nastavení povolený. Pomocí tohoto nastavení můžete blokovat nebo povolit uživatelům k pozastavení instalace aktualizace z *nastavení* jejich počítačů. 
      
   - **Režim stahování pro optimalizaci doručení**: Zvolte metodu, pro kterou zařízení stahovat aktualizace Windows. Podrobnosti najdete v části [DeliveryOptimization/DODownloadMode](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization#download-mode).

5. Po dokončení zvolte **OK**. V podokně **Vytvořit aktualizační kanál** vyberte **Vytvořit**.

Nový aktualizační kanál se zobrazí v seznamu aktualizačních kanálů.

1. Pokud chcete přiřadit kanál, vyberte kanál ze seznamu aktualizačních kanálů a pak na kartě <*název kanálu*> vyberte **Přiřazení**.
2. Na další kartě zvolte **Vybrat skupiny, které se zahrnou** a pak vyberte skupiny, kterým chcete kanál přiřadit.
3. Až budete hotovi, volbou příkazu **Vybrat** přiřazení dokončete.

## <a name="update-compliance-reporting"></a>Generování sestav dodržování předpisů pro aktualizace
Dodržování předpisů pro aktualizace můžete sledovat v Intune nebo pomocí bezplatného řešení, které se jmenuje Update Compliance.

### <a name="review-update-compliance-in-intune"></a>Kontrola dodržování předpisů pro aktualizace v Intune 
<!-- 1352223 --> Zkontrolujte sestavu zásad, abyste viděli stav nasazení pro nakonfigurované aktualizační kanály Windows 10.

1. Na webu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Aktualizace softwaru** > **Přehled**. Uvidíte obecné informace o stavu všech aktualizačních kanálů, které jste přiřadili.
3. Otevřete jednu z těchto sestav:

   **Pro všechny aktualizační kanály nasazení**:  
   1. V podokně **Aktualizace softwaru** > **Aktualizační kanály Windows 10**
   2. V **sekci Monitorování** zvolte **Stav nasazení podle kruhu aktualizace**.

   **Pro konkrétní aktualizační kanály nasazení**:  
   1. V podokně **Aktualizace softwaru** > **Aktualizační kanály Windows 10** zvolte aktualizační kanál nasazení, který chcete zkontrolovat.
   2. Pokud chcete zobrazit podrobnější informace o aktualizačním kanálu, v sekci **Monitorování** zvolte z těchto sestav:
      - **Stav zařízení**
      - **Stav uživatele**

### <a name="review-update-compliance-using-oms"></a>Kontrola dodržování předpisů pro aktualizace pomocí OMS
Zavádění aktualizací Windows 10 můžete sledovat pomocí bezplatného řešení, které se jmenuje Update Compliance. Podrobnosti najdete v článku o [monitorování aktualizací Windows pomocí Update Compliance](https://technet.microsoft.com/itpro/windows/manage/update-compliance-monitor). Když toto řešení použijete, můžete nasadit komerční ID do libovolného z vašich zařízení s Windows 10 spravovaných pomocí Intune, pro které chcete generovat sestavy o dodržování předpisů pro aktualizace.

V Intune můžete ke konfiguraci komerčního ID použít nastavení OMA-URI vlastní zásady. Podrobnosti najdete v článku [Nastavení zásad Intune pro zařízení s Windows 10 v Microsoft Intune](custom-settings-windows-10.md).   

Cesta OMA-URI (s rozlišováním velkých a malých písmen) pro konfiguraci komerčního ID je: ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID

V nastavení **Přidat nebo upravit nastavení OMA-URI** můžete použít třeba následující hodnoty:

- **Název nastavení**: Komerční ID pro analýzu Windows
- **Popis nastavení**: Konfigurace řešení pro komerční ID pro analýzu Windows
- **OMA-URI** (s rozlišováním velkých a malých písmen): ./Vendor/MSFT/DMClient/Provider/MS DM Server/CommercialID
- **Datový typ**: Řetězec
- **Hodnota**: <*Použijte identifikátor GUID zobrazený na kartě Telemetrie Windows v pracovním prostoru OMS*>

![Nastavení OMA-URI – Upravit řádek](./media/commID-edit.png)

> [!NOTE]
> Podrobnosti o MS DM Serveru najdete v tématu [Poskytovatel konfiguračních služeb DMClient](https://docs.microsoft.com/windows/client-management/mdm/dmclient-csp).

## <a name="pause-updates"></a>Pozastavení aktualizací
Je možné pozastavit příjem aktualizací funkcí nebo aktualizací kvality zařízením až na 35 dní od okamžiku pozastavení aktualizací. Po uplynutí maximálního počtu dní funkce pozastavení automaticky vyprší a zařízení zkontroluje dostupné aktualizace ve Windows Update. Po této kontrole můžete aktualizace znovu pozastavit.

1. Na webu [Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Vyberte **Aktualizace softwaru** > **Aktualizační kanály Windows 10**.
3. V seznamu aktualizačních kanálů vyberte kanál, který chcete pozastavit, a potom zvolte **...**  > **Pozastavit kvalitu** > nebo **Pozastavit funkci** v závislosti na typu aktualizací, které se mají pozastavit.

> [!IMPORTANT]
> Když vydáte příkaz k pozastavení, zařízení ho obdrží při dalším přihlášení ke službě. Je možné, že před přihlášením ke službě nainstalují plánovanou aktualizaci.
> Kromě toho platí, že pokud je cílové zařízení při vydání příkazu k pozastavení vypnuté, může po zapnutí stáhnout a nainstalovat plánované aktualizace před tím, než se přihlásí k Intune.

### <a name="uninstall-the-latest-from-windows-10-software-updates"></a>Odinstalace nejnovější aktualizace softwaru Windows 10 
Pokud na počítačích s Windows 10 najdete problém způsobující chybu, můžete se rozhodnout odinstalovat (vrátit zpět) nejnovější aktualizaci funkcí nebo nejnovější aktualizaci pro zvýšení kvality. Odinstalace aktualizace funkcí nebo kvality je dostupná jenom pro kanál pro údržbu, ve kterém se dané zařízení nachází. Při odinstalaci se aktivují zásady, které na počítačích s Windows 10 obnoví předchozí aktualizaci. Konkrétně u aktualizací funkcí je možné omezit dobu 2 až 60 dnů, po kterou lze provést odinstalaci nejnovější verze. Možnosti odinstalace aktualizací softwaru nastavíte takto:

1. V Intune vyberte **Aktualizace softwaru**.
2. Vyberte **Aktualizační kanály Windows 10**, vyberte existující aktualizační kanál a potom **Odinstalovat**.

> [!NOTE]
> Poté, co se aktualizace kvality úspěšně vrátí zpět, na počítačích s Windows 10 ji koncoví uživatelé uvidí i nadále uvedenou v části **Nastavení Windows** > **Aktualizace** > **Historie aktualizací**.

## <a name="windows-holographic-for-business-support"></a>Podpora Windows Holographic for Business

Windows Holographic for Business podporuje následující nastavení:

- **Chování automatické aktualizace**
- **Aktualizace produktů Microsoftu**
- **Kanál pro údržbu**: Podporuje **pololetní kanál** a **pololetní kanál (cílený)** možnosti
