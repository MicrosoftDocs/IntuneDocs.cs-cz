---
title: Konfigurace služby Windows Update pro firmy v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si, jak upravit nastavení aktualizací softwaru na profilu a vytvořit aktualizační kanál, zkontrolujte dodržování předpisů a zjistěte, jak pozastavit aktualizace v nastavení služby Windows Update pro firmy pomocí Microsoft Intune na zařízeních s Windows 10.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/03/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: c7e144c91f91da998a868868880e9a12d2370e81
ms.sourcegitcommit: 7c251948811b8b817e9fe590b77f23aed95b2d4e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/15/2019
ms.locfileid: "71302441"
---
# <a name="manage-software-updates-in-intune"></a>Správa softwarových aktualizací v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Pomocí Intune definujte aktualizační kanály, které určují, jak a kdy Windows jako služba aktualizuje vaše zařízení s Windows 10. Aktualizační kanály jsou zásady, které přiřadíte ke skupinám zařízení. Pomocí aktualizačních kanálů můžete vytvořit strategii aktualizace, která odráží vaše firemní potřeby. Další informace najdete v tématu o [správě aktualizací pomocí Windows Update pro firmy](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

Ve Windows 10 obsahují nové aktualizace funkcí a aktualizace pro zvýšení kvality obsah všech předchozích aktualizací. Pokud si nainstalujete nejnovější aktualizaci, máte jistotu, že jsou vaše zařízení s Windows 10 aktuální. Na rozdíl od předchozích verzí Windows je teď nutné nainstalovat celou aktualizaci (a ne jenom její část).


Služba Windows Update pro firmy vám zjednodušuje správu aktualizací. Nemusíte tak schvalovat jednotlivé aktualizace pro skupiny zařízení. Konfigurací vhodné strategie zavádění aktualizací budete mít pod kontrolou řízení rizik ve svém prostředí. Intune poskytuje možnost konfigurovat na zařízeních [nastavení aktualizací](windows-update-settings.md) a poskytuje možnost odložit instalaci aktualizací. V Intune nejsou uložené samotné aktualizace, ale jenom přiřazení zásad aktualizací. Zařízení kvůli aktualizacím přistupují přímo k webu Windows Update. Tato kolekce nastavení, která konfigurují, kdy se aktualizace Windows 10 nainstaluje, se označuje jako *aktualizační kanál Windows 10*.

Aktualizační kanály Windows 10 podporují [značky oboru](scope-tags.md). Pomocí značek Scope s aktualizačními kroužky můžete filtrovat a spravovat sady konfigurací, které používáte.

## <a name="prerequisites"></a>Požadavky  

Aby se pro zařízení s Windows 10 v Intune používaly aktualizace Windows, musí se splnit následující požadavky.  

- Na počítačích s Windows 10 musí běžet aspoň Windows 10 pro s aktualizací Windows výročí nebo novější (verze 1607 nebo novější).
- Web Windows Update podporuje následující edice Windows 10:
  - Windows 10
  - Windows 10 Team (pro zařízení Surface Hubu)
  - Windows Holographic for Business  

    Windows Holografick pro firmy podporuje podmnožinu nastavení pro aktualizace Windows, včetně:
    - **Chování automatické aktualizace**
    - **Aktualizace produktů Microsoftu**
    - **Kanál pro údržbu**: Podporuje možnosti **s půlročním** a **půlročním kanálem (cílené)** . Další informace najdete v tématu [Správa Windows holografické](windows-holographic-for-business.md).  

    > [!NOTE]  
    > **Nepodporované verze a edice**:
    > - Windows 10 Mobile  
    > - Windows 10 Enterprise LTSC. Web Windows Update for Business (WUfB) v současné době nepodporuje *dlouhodobé vydáváníy kanálů služby* . Naplánujte použití alternativních metod oprav, jako je WSUS nebo Configuration Manager.  

- Na zařízeních s Windows musí být **Zpětná vazba &**  > **diagnostická Diagnostika a data o použití** nastavena na **Basic**, **Enhanced**nebo **Full**.  

  Nastavení *dat diagnostiky a použití* můžete nakonfigurovat pro zařízení s Windows 10 ručně nebo použít profil omezení zařízení Intune pro Windows 10 a novější. Pokud použijete profil omezení zařízení, nastavte [Nastavení omezení pro zařízení](device-restrictions-windows-10.md#reporting-and-telemetry) **sdílet data o využití** aspoň na **Basic**. Toto nastavení najdete pod kategorií **vytváření sestav a telemetrie** při konfiguraci zásad omezení pro zařízení s Windows 10 nebo novějším.

  Další informace o profilech zařízení najdete v tématu [Konfigurace nastavení omezení zařízení](device-restrictions-configure.md).  

- Pokud používáte portál Azure Classic, [migrujte nastavení do Azure Portal](#migrate-update-settings-to-the-azure-portal).  


## <a name="create-and-assign-update-rings"></a>Vytvoření a přiřazení aktualizačních kanálů

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
3. Vyberte **Aktualizace softwaru** > **Aktualizační kanály Windows 10** > **Vytvořit**.
4. Zadejte název a popis (volitelný) a potom zvolte **Konfigurovat**.
5. V **Nastavení**nakonfigurujte nastavení pro své obchodní potřeby. Informace o dostupných nastaveních najdete v tématu [nastavení služby Windows Update](windows-update-settings.md).  
6. Po dokončení zvolte **OK**. V podokně **Vytvořit aktualizační kanál** vyberte **Vytvořit**. Nový aktualizační kanál se zobrazí v seznamu aktualizačních kanálů.
7. Chcete-li přiřadit prstence, v seznamu aktualizačních kanálů vyberte prstenec a na \<kartě název > Ring zvolte **přiřazení**.
8. Kartu **Zahrnout** a **vyloučit** použijte k definování skupin, ke kterým je tento prstenec přiřazený, a pak výběrem **Uložit** dokončete přiřazení.

## <a name="manage-your-windows-10-update-rings"></a>Správa aktualizačních kanálů Windows 10
Na portálu můžete vybrat aktualizační kanál Windows 10 a otevřít jeho podokno **přehledu** . V tomto podokně si můžete zobrazit stav přiřazení vyzvánění a provést další akce ke správě tohoto prstence. 
### <a name="to-view-an-updates-rings-overview-pane"></a>Postup zobrazení podokna s přehledem aktualizačních kroužků: 
1. Přihlaste se k portálu Azure.
2. Přejděte na > **aktualizace**softwaruIntuneaktualizačníkanályWindows10. > 
3. Vyberte aktualizační kanál, který chcete zobrazit nebo spravovat.  

Kromě zobrazení stavu přiřazení můžete vybrat následující akce z horní části podokna přehled a spravovat aktualizační kanál:  
- [Odstranění](#delete)  
- [Chvíli](#pause)  
- [Opakované](#resume)  
- [Zvětšení](#extend)  
- [Uninstall](#uninstall)  

![Dostupné akce](./media/windows-update-for-business-configure/overview-actions.png)

### <a name="delete"></a>Odstranění  
Výběrem možnosti **Odstranit** zabráníte vynucování nastavení vybraného aktualizačního kanálu Windows 10. Odstraněním prstence se odebere jeho konfigurace z Intune, aby se už Intune nepoužíval a tato nastavení se neuplatní.  

Při odstranění prstence z Intune se nezmění nastavení na zařízeních, kterým se přiřadil aktualizační kanál.  Místo toho zařízení udržuje aktuální nastavení. Důvodem je to, že zařízení neudržují historický záznam o tom, jaká nastavení byla dříve zavedena a že zařízení může přijímat nastavení z dalších aktualizačních kanálů, které zůstávají aktivní.  

#### <a name="to-delete-a-ring"></a>Odstranění prstence  
1. Při prohlížení stránky přehled pro aktualizační kanál vyberte možnost **Odstranit**.  
2. Vyberte **OK**.  

### <a name="pause"></a>Pozastavení  
Vyberte **pozastavit** , pokud chcete, aby zařízení nepřijímala aktualizace funkcí nebo aktualizace kvality až 35 dní od času, kdy jste okruh zastavili. Po uplynutí maximálního počtu dní funkce pozastavení automaticky vyprší a zařízení zkontroluje dostupné aktualizace ve Windows Update. Po této kontrole můžete aktualizace znovu pozastavit. Pokud obnovíte pozastavený aktualizační kanál a pak tento prstenec znovu zastavíte, doba pozastavení se resetuje na 35 dní.  

#### <a name="to-pause-a-ring"></a>Pozastavení vyzvánění  
1. Při prohlížení stránky přehled pro aktualizační kanál vyberte **pozastavit**.  
2. Vyberte buď **funkci** , nebo **kvalitu** , aby se tento typ aktualizace zastavil, a pak vyberte **OK**.  
3. Po pozastavení jednoho typu aktualizace můžete vybrat možnost pozastavit znovu a pozastavit jiný typ aktualizace.  

Když je typ aktualizace pozastaven, zobrazuje podokno přehled pro tento prstenec, kolik dní zbývá před tím, než se tento typ aktualizace obnoví.

> [!IMPORTANT]  
> Po vystavení příkazu pozastavit zařízení dostanou tento příkaz při příští kontrole služby. Je možné, že před přihlášením ke službě nainstalují plánovanou aktualizaci. Kromě toho platí, že pokud je cílové zařízení při vydání příkazu k pozastavení vypnuté, může po zapnutí stáhnout a nainstalovat plánované aktualizace před tím, než se přihlásí k Intune.

### <a name="resume"></a>Obnovit  
Když je aktualizační kanál pozastaven, můžete vybrat možnost **pokračovat** a obnovit aktualizace funkcí a kvality pro daný okruh na aktivní operaci. Po pokračování aktualizačního kanálu můžete tento prstenec pozastavit znovu.  

#### <a name="to-resume-a-ring"></a>Obnovení prstence  
1. Při prohlížení stránky přehled pro pozastavený aktualizační kanál vyberte **pokračovat**.  
2. Vyberte z dostupných možností, aby se obnovily buď aktualizace **funkcí** , nebo **kvality** , a pak vyberte **OK**.  
3. Po obnovení jednoho typu aktualizace můžete znovu vybrat pokračovat a obnovit jiný typ aktualizace.  

### <a name="extend"></a>Rozšíření  
Když je aktualizační kanál pozastaven, můžete vybrat možnost **Rozšířené** a resetovat dobu pozastavení pro aktualizace funkcí a kvality pro daný aktualizační kanál na 35 dní.  

#### <a name="to-extend-the-pause-period-for-a-ring"></a>Prodloužení doby pozastavení pro okruh  
1. Při prohlížení stránky přehled pro pozastavený aktualizační kanál vyberte možnost **Zvětšit**. 
2. Vyberte z dostupných možností, aby se obnovily buď aktualizace **funkcí** , nebo **kvality** , a pak vyberte **OK**.  
3. Po rozšíření pozastavení pro jeden typ aktualizace můžete vybrat rozšířit znovu a rozšířit jiný typ aktualizace.  

### <a name="uninstall"></a>Odinstalace  
Správce Intune může pomocí **odinstalace** odinstalovat (vrátit zpátky) nejnovější aktualizaci *funkcí* nebo nejnovější aktualizaci *kvality* pro aktivní nebo pozastavený aktualizační kanál. Po odinstalování jednoho typu můžete odinstalovat jiný typ. Intune nepodporuje nebo nespravuje možnost uživatelů odinstalovat aktualizace.  

K úspěšnému odinstalaci:  
- V zařízení musí běžet aktualizace Windows 10 z dubna 2018 (verze 1803) nebo novější.  

Zařízení musí mít nainstalovanou nejnovější aktualizaci. Vzhledem k tomu, že aktualizace jsou kumulativní, budou mít zařízení, která instalují nejnovější aktualizaci, nejnovější funkce a aktualizace kvality. Příkladem použití této možnosti je vrácení poslední aktualizace, pokud byste zjistili, že došlo k zásadnímu problému na počítačích s Windows 10.  

Při použití nástroje Uninstall Vezměte v úvahu následující skutečnosti:  
- Odinstalace aktualizace funkcí nebo kvality je dostupná jenom pro kanál pro údržbu, ve kterém se dané zařízení nachází.  

- Použití funkce odinstalovat pro aktualizace funkcí nebo kvality aktivuje zásadu pro obnovení předchozí aktualizace na počítačích s Windows 10.  

- Po úspěšném vrácení aktualizace kvality na zařízení s Windows 10 se koncovým uživatelům dál zobrazí aktualizace uvedená v části >  **Nastavení** > systému Windows**Historie** **aktualizací.**  

- V případě aktualizací funkcí je čas, kdy můžete odinstalovat aktualizaci funkcí, omezen na 2-60 dní, jak je nakonfigurováno nastavením aktualizace aktualizačních kroužků **nastavit interval odinstalace aktualizací funkcí (2 – 60 dnů)** . Aktualizaci funkcí, která je nainstalovaná na zařízení, se nedá vrátit zpátky, pokud je aktualizace funkcí nainstalovaná déle než nakonfigurované období odinstalace.  

  Představte si například aktualizační kanál s dobou odinstalace aktualizace funkcí o 20 dní. Po 25 dnech se rozhodnete vrátit nejnovější aktualizaci funkcí a použít možnost odinstalace.  Zařízení, na která se nainstalovala aktualizace funkcí víc než 20 dní, ji nemůžou odinstalovat, protože v rámci údržby odebrala nezbytné bity. Zařízení, u kterých se tato funkce nainstalovala jenom do 19 dnů, ale můžou aktualizaci odinstalovat, pokud se úspěšně zaregistrují, aby příkaz uninstall přijal před uplynutím 120denní lhůty odinstalace.  

Další informace o web Windows Updatech zásadách najdete v tématu [aktualizace CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp) v dokumentaci ke správě klientů Windows.  

#### <a name="to-uninstall-the-latest-windows-10-update"></a>Odinstalace nejnovější aktualizace Windows 10  
1. Při prohlížení stránky přehled pro pozastavený aktualizační kanál vyberte možnost **odinstalovat**.  
2. Vyberte z dostupných možností pro odinstalaci aktualizace **funkcí** nebo **kvality** a pak vyberte **OK**.  
3. Po aktivaci odinstalace pro jeden typ aktualizace můžete vybrat možnost odinstalovat znovu pro odinstalování zbývajícího typu aktualizace.  

## <a name="migrate-update-settings-to-the-azure-portal"></a>Migrace nastavení aktualizace na Azure Portal  
Portál Azure Classic má také omezený počet dalších nastavení aktualizací Windows 10 v profilu konfigurace zařízení. Pokud máte některá z těchto nastavení nakonfigurovaná při migraci na Azure Portal, důrazně doporučujeme, abyste provedli následující akce:  

1. Na portále Azure Portal vytvořte aktualizační kanály Windows 10 s nastaveními, která potřebujete. Nastavení **Povolit funkce v předběžné verzi** není na webu Azure Portal podporované, protože už pro nejnovější buildy Windows 10 neplatí. Při vytvoření aktualizačních kanálů můžete nakonfigurovat ostatní tři nastavení i další nastavení aktualizace Windows 10.  

   > [!NOTE]  
   > Nastavení aktualizací Windows 10 vytvořená na klasickém portálu se na Azure Portalu po migraci nezobrazí. Tato nastavení se ale použijí. Pokud jste některá z nich migrovali a migrované zásady z Azure Portalu upravíte, tato nastavení se ze zásad odeberou.  

2. Odstraňte nastavení aktualizací na klasickém portálu. Po migraci na Azure Portal a přidání stejných nastavení do aktualizačního kanálu musíte nastavení na portálu Classic odstranit, aby se zabránilo možným konfliktům zásad. Pokud je například stejné nastavení nakonfigurované s odlišnými hodnotami, dojde ke konfliktu. Neexistuje snadný způsob, jak zjistit, protože nastavení nakonfigurované na klasickém portálu se nezobrazuje v Azure Portal.  

## <a name="next-steps"></a>Další kroky
[Nastavení služby Windows Update podporovaná službou Intune](windows-update-settings.md)  

[Sestavy dodržování předpisů v Intune pro aktualizace](windows-update-compliance-reports.md)

[Řešení potíží s aktualizačními kroužkami Windows 10](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Windows-10-Update-Ring-Policies/ba-p/714046)

