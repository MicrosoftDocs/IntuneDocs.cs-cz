---
title: Konfigurace služby Windows Update pro firmy v Microsoft Intune – Azure | Microsoft Docs
description: Pomocí aktualizačních kanálů a zásad aktualizací funkcí spravujte aktualizace softwaru Windows 10. Můžete zkontrolovat dodržování předpisů a pozastavit instalaci aktualizace s web Windows Update pro obchodní nastavení pomocí Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 11/20/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.subservice: protect
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: mghadial
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 01866bba0ef47ac807b24a66f773e212c76ff7df
ms.sourcegitcommit: 1cf063c98e1caae00a6e6fab821cc3254562bca9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2019
ms.locfileid: "74291091"
---
# <a name="manage-windows-10-software-updates-in-intune"></a>Správa aktualizací softwaru Windows 10 v Intune

Intune slouží ke správě instalace aktualizací softwaru Windows 10 z web Windows Update pro firmy.

Služba Windows Update pro firmy vám zjednodušuje správu aktualizací. Nemusíte tak schvalovat jednotlivé aktualizace pro skupiny zařízení. Konfigurací vhodné strategie zavádění aktualizací budete mít pod kontrolou řízení rizik ve svém prostředí. Intune poskytuje možnost konfigurovat na zařízeních [nastavení aktualizací](windows-update-settings.md) a poskytuje možnost odložit instalaci aktualizací. Můžete taky zabránit tomu, aby zařízení instalovala funkce z nových verzí Windows, aby se zachovala jejich stabilita, zatímco tato zařízení můžou dál instalovat aktualizace pro kvalitu a zabezpečení.

Intune ukládá jenom přiřazení zásad aktualizace, ne samotné aktualizace. Zařízení kvůli aktualizacím přistupují přímo k webu Windows Update.

Intune poskytuje pro správu aktualizací následující typy zásad:

- **Aktualizační kanál Windows 10**: Tato zásada je kolekcí nastavení, která konfigurují, kdy se aktualizace Windows 10 instalují.

- **Aktualizace funkcí Windows 10 (Public Preview)** : Tato zásada přináší zařízení do zadané verze Windows a zablokuje sadu funkcí na těchto zařízeních, dokud se nerozhodnete je aktualizovat na novější verzi Windows.  I když verze funkce zůstává statická, zařízení můžou dál instalovat aktualizace kvality a zabezpečení, které jsou k dispozici pro jejich verzi funkcí.

Pro skupiny zařízení přiřadíte zásady pro aktualizační kanály Windows 10 a aktualizace funkcí Windows 10. Oba typy zásad můžete použít ve stejném prostředí Intune ke správě aktualizací softwaru pro zařízení s Windows 10 a k vytvoření strategie aktualizace, která odráží vaše obchodní požadavky.

Další informace najdete v tématu o [správě aktualizací pomocí Windows Update pro firmy](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

## <a name="prerequisites"></a>Předpoklady

Aby se pro zařízení s Windows 10 v Intune používaly aktualizace Windows, musí se splnit následující požadavky.

- V počítačích s Windows 10 musí běžet tyto verze Windows 10:
  - **Aktualizační kanály Windows 10**: verze 1607 nebo novější
  - **Aktualizace funkcí Windows 10**: verze 1703 nebo novější

- Web Windows Update podporuje následující edice Windows 10:
  - Windows 10
  - Windows 10 Team – pro zařízení Surface Hub (nepodporuje *aktualizace funkcí Windows 10*)
  - Windows Holographic for Business

    Windows Holografick pro firmy podporuje podmnožinu nastavení pro aktualizace Windows, včetně:
    - **Chování automatické aktualizace**
    - **Aktualizace produktů Microsoftu**
    - **Kanál pro údržbu**: podporuje možnosti **s polovičním** a **půlročním kanálem (cílené)** . Další informace najdete v tématu [Správa Windows holografické](../fundamentals/windows-holographic-for-business.md).

  > [!NOTE]
  > **Nepodporované verze a edice**:
  > - Windows 10 Mobile  
  > - Windows 10 Enterprise LTSC. Web Windows Update for Business (WUfB) v současné době nepodporuje *dlouhodobé vydáváníy kanálů služby* . Naplánujte použití alternativních metod oprav, jako je WSUS nebo Configuration Manager.

- Na zařízeních s Windows musí být **Zpětná vazba & diagnostika** > **diagnostická data a data o použití** nastavena na hodnotu **základní**, **Rozšířená**nebo **plná**.  

  Nastavení *dat diagnostiky a použití* můžete nakonfigurovat pro zařízení s Windows 10 ručně nebo použít profil omezení zařízení Intune pro Windows 10 a novější. Pokud použijete profil omezení zařízení, nastavte [Nastavení omezení pro zařízení](../configuration/device-restrictions-windows-10.md#reporting-and-telemetry) **sdílet data o využití** aspoň na **Basic**. Toto nastavení najdete pod kategorií **vytváření sestav a telemetrie** při konfiguraci zásad omezení pro zařízení s Windows 10 nebo novějším.

  Další informace o profilech zařízení najdete v tématu [Konfigurace nastavení omezení zařízení](../configuration/device-restrictions-configure.md).

- Pokud používáte portál Azure Classic, [migrujte nastavení do Azure Portal](#migrate-update-settings-to-the-azure-portal).


## <a name="windows-10-update-rings"></a>Aktualizační kanály Windows 10

Vytvořte aktualizační kanály, které určují, jak a kdy Windows jako služba aktualizuje vaše zařízení s Windows 10 pomocí aktualizací funkcí a kvality. Ve Windows 10 obsahují nové aktualizace funkcí a aktualizace pro zvýšení kvality obsah všech předchozích aktualizací. Pokud si nainstalujete nejnovější aktualizaci, máte jistotu, že jsou vaše zařízení s Windows 10 aktuální. Na rozdíl od předchozích verzí Windows je teď nutné nainstalovat celou aktualizaci (a ne jenom její část).

Aktualizační kanály Windows 10 podporují [značky oboru](../fundamentals/scope-tags.md). Pomocí značek Scope s aktualizačními kroužky můžete filtrovat a spravovat sady konfigurací, které používáte.

### <a name="create-and-assign-update-rings"></a>Vytvoření a přiřazení aktualizačních kanálů

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager]( https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte **zařízení** > **Windows** > **aktualizačních okruhů Windows 10** > **vytvořit**.

3. V části *základy*zadejte název, popis (volitelné) a pak vyberte **Další**.
  ![vytvoření aktualizačního kroužku]( ./media/windows-update-for-business-configure/basics-tab.png)
  
4. V části **aktualizovat nastavení vyzvánění**nakonfigurujte nastavení pro své obchodní potřeby. Informace o dostupných nastaveních najdete v tématu Nastavení služby Windows Update. Po konfiguraci nastavení *aktualizace a uživatelského prostředí* vyberte **Další**.

5. V části **značky oboru**vyberte **+ Vybrat rozsah značky** a otevřete tak podokno *Vybrat značky* , pokud je chcete použít pro aktualizační kanál. Zvolte jednu nebo více značek a kliknutím na tlačítko **Vybrat** je přidejte do aktualizačního kanálu a vraťte se na stránku *značka oboru*s.

   Až budete připraveni, vyberte **Další** a pokračujte v *přiřazení*.

6. V části **přiřazení**zvolte **+ Vybrat skupiny, které chcete zahrnout** , a potom přiřaďte aktualizační kanál k jedné nebo více skupinám. Pomocí **+ Vyberte skupiny, které se vyloučí** , abyste mohli přiřazení vyladit. Pokračujte výběrem **Další** .

7. V části**zkontrolovat + vytvořit**zkontrolujte nastavení a pak vyberte **vytvořit** , jakmile budete připraveni Uložit aktualizační kanál Windows 10. Nový aktualizační kanál se zobrazí v seznamu aktualizačních kanálů.

### <a name="manage-your-windows-10-update-rings"></a>Správa aktualizačních kanálů Windows 10

Na portálu přejděte na **zařízení** > **Windows** > **aktualizačních kanálů Windows 10** a vyberte zásadu, kterou chcete spravovat.  Zásada se otevře na stránce s **přehledem** .

Na této stránce můžete zobrazit stav přiřazení vyzvánění a v horní části podokna přehled vybrat následující akce ke správě aktualizačního kanálu:

- [Odstranit](#delete)
- [Chvíli](#pause)
- [Opakované](#resume)
- [Zvětšení](#extend)
- [Uninstall](#uninstall)

![Dostupné akce](./media/windows-update-for-business-configure/overview-actions.png)

#### <a name="delete"></a>Odstranit

Výběrem možnosti **Odstranit** zabráníte vynucování nastavení vybraného aktualizačního kanálu Windows 10. Odstraněním prstence se odebere jeho konfigurace z Intune, aby se už Intune nepoužíval a tato nastavení se neuplatní.

Při odstranění prstence z Intune se nezmění nastavení na zařízeních, kterým se přiřadil aktualizační kanál.  Místo toho zařízení udržuje aktuální nastavení. Zařízení neudržují historický záznam o tom, jaká nastavení byla dříve držená. Zařízení také mohou přijímat nastavení z dalších aktualizačních kanálů, které zůstávají aktivní.

##### <a name="to-delete-a-ring"></a>Odstranění prstence

1. Při prohlížení stránky přehled pro aktualizační kanál vyberte možnost **Odstranit**.
2. Vyberte **OK**.

#### <a name="pause"></a>Pozastavení

Vyberte **pozastavit** , pokud chcete, aby zařízení nepřijímala aktualizace funkcí nebo aktualizace kvality až 35 dní od času, kdy jste okruh zastavili. Po uplynutí maximálního počtu dní funkce pozastavení automaticky vyprší a zařízení zkontroluje dostupné aktualizace ve Windows Update. Po této kontrole můžete aktualizace znovu pozastavit.
Pokud obnovíte pozastavený aktualizační kanál a pak tento prstenec znovu zastavíte, doba pozastavení se resetuje na 35 dní.

##### <a name="to-pause-a-ring"></a>Pozastavení vyzvánění

1. Při prohlížení stránky přehled pro aktualizační kanál vyberte **pozastavit**.
2. Vyberte buď **funkci** , nebo **kvalitu** , aby se tento typ aktualizace zastavil, a pak vyberte **OK**.
3. Po pozastavení jednoho typu aktualizace můžete vybrat možnost pozastavit znovu a pozastavit jiný typ aktualizace.

Když je typ aktualizace pozastaven, zobrazuje podokno přehled pro tento prstenec, kolik dní zbývá před tím, než se tento typ aktualizace obnoví.

> [!IMPORTANT]
> Po vystavení příkazu pozastavit zařízení dostanou tento příkaz při příští kontrole služby. Je možné, že před přihlášením ke službě nainstalují plánovanou aktualizaci. Kromě toho platí, že pokud je cílové zařízení při vydání příkazu k pozastavení vypnuté, může po zapnutí stáhnout a nainstalovat plánované aktualizace před tím, než se přihlásí k Intune.

#### <a name="resume"></a>Obnovit

Když je aktualizační kanál pozastaven, můžete vybrat možnost **pokračovat** a obnovit aktualizace funkcí a kvality pro daný okruh na aktivní operaci. Po pokračování aktualizačního kanálu můžete tento prstenec pozastavit znovu.

##### <a name="to-resume-a-ring"></a>Obnovení prstence

1. Při prohlížení stránky přehled pro pozastavený aktualizační kanál vyberte **pokračovat**.
2. Vyberte z dostupných možností, aby se obnovily buď aktualizace **funkcí** , nebo **kvality** , a pak vyberte **OK**.
3. Po obnovení jednoho typu aktualizace můžete znovu vybrat pokračovat a obnovit jiný typ aktualizace.

#### <a name="extend"></a>Rozšíření  

Když je aktualizační kanál pozastaven, můžete vybrat možnost **Rozšířené** a resetovat dobu pozastavení pro aktualizace funkcí a kvality pro daný aktualizační kanál na 35 dní.

##### <a name="to-extend-the-pause-period-for-a-ring"></a>Prodloužení doby pozastavení pro okruh

1. Při prohlížení stránky přehled pro pozastavený aktualizační kanál vyberte možnost **Zvětšit**.
2. Vyberte z dostupných možností, aby se obnovily buď aktualizace **funkcí** , nebo **kvality** , a pak vyberte **OK**.
3. Po rozšíření pozastavení pro jeden typ aktualizace můžete vybrat rozšířit znovu a rozšířit jiný typ aktualizace.

#### <a name="uninstall"></a>Odinstalovat  

Správce Intune může pomocí **odinstalace** odinstalovat (vrátit zpátky) nejnovější aktualizaci *funkcí* nebo nejnovější aktualizaci *kvality* pro aktivní nebo pozastavený aktualizační kanál. Po odinstalování jednoho typu můžete odinstalovat jiný typ. Intune nepodporuje nebo nespravuje možnost uživatelů odinstalovat aktualizace.  

> [!IMPORTANT]
> Když použijete možnost *odinstalovat* , Intune požadavek na odinstalaci předá zařízení okamžitě.
>
> - Zařízení s Windows začnou odebírat aktualizace, jakmile obdrží změnu v zásadách Intune. Odebrání aktualizace není omezené na plány údržby, a to i v případě, že jsou nakonfigurované jako součást aktualizačního kruhu.
> - Pokud odebrání aktualizace vyžaduje restart zařízení, zařízení se restartuje bez nabídky uživatelů zařízení, aby bylo možné tyto možnosti zpozdit.

K úspěšnému odinstalaci:

- V zařízení musí běžet aktualizace Windows 10 z dubna 2018 (verze 1803) nebo novější.

Zařízení musí mít nainstalovanou nejnovější aktualizaci. Vzhledem k tomu, že aktualizace jsou kumulativní, budou mít zařízení, která instalují nejnovější aktualizaci, nejnovější funkce a aktualizace kvality. Příkladem použití této možnosti je vrácení poslední aktualizace, pokud byste zjistili, že došlo k zásadnímu problému na počítačích s Windows 10.

Při použití nástroje Uninstall Vezměte v úvahu následující skutečnosti:

- Odinstalace aktualizace funkcí nebo kvality je dostupná jenom pro kanál pro údržbu, ve kterém se dané zařízení nachází.

- Použití funkce odinstalovat pro aktualizace funkcí nebo kvality aktivuje zásadu pro obnovení předchozí aktualizace na počítačích s Windows 10.

- Po úspěšném vrácení aktualizace kvality na zařízení s Windows 10 se uživatelům zařízení nadále zobrazuje aktualizace uvedená v **nastavení Windows** > **aktualizace** > **historii aktualizací**.

- V případě aktualizací funkcí je čas, který můžete odinstalovat, omezen na 2-60 dní. Toto období se konfiguruje pomocí nastavení aktualizace aktualizačních kroužků **nastavit interval odinstalace aktualizace funkcí (2 – 60 dní)** . Aktualizaci funkcí, která je nainstalovaná na zařízení, se nedá vrátit zpátky po instalaci aktualizace delší než nakonfigurované období odinstalace.

  Představte si například aktualizační kanál s dobou odinstalace aktualizace funkcí o 20 dní. Po 25 dnech se rozhodnete vrátit nejnovější aktualizaci funkcí a použít možnost odinstalace.  Zařízení, na která se nainstalovala aktualizace funkcí víc než 20 dní, ji nemůžou odinstalovat, protože v rámci údržby odebrala potřebné bity. Zařízení, u kterých se tato funkce nainstalovala jenom do 19 dnů, ale můžou aktualizaci odinstalovat, jenom když se úspěšně zaregistrují, aby se před tím, než je doba odinstalace odinstalovala.

Další informace o web Windows Updatech zásadách najdete v tématu [aktualizace CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp) v dokumentaci ke správě klientů Windows.

##### <a name="to-uninstall-the-latest-windows-10-update"></a>Odinstalace nejnovější aktualizace Windows 10

1. Při prohlížení stránky přehled pro pozastavený aktualizační kanál vyberte možnost **odinstalovat**.
2. Vyberte z dostupných možností pro odinstalaci aktualizace **funkcí** nebo **kvality** a pak vyberte **OK**.
3. Po aktivaci odinstalace pro jeden typ aktualizace můžete vybrat možnost odinstalovat znovu pro odinstalování zbývajícího typu aktualizace.

## <a name="windows-10-feature-updates"></a>Aktualizace funkcí Windows 10

*Tato funkce je ve verzi Public Preview.*

S *aktualizacemi funkcí Windows 10*vyberete verzi funkcí Windows, na které mají zařízení zůstat, jako je Windows 10 verze 1803 nebo verze 1809. Můžete nastavit úroveň funkcí 1803 nebo novější.

Když zařízení obdrží zásadu aktualizace funkcí Windows 10:

- Zařízení se aktualizuje na verzi Windows zadanou v zásadě. Zařízení, které už používá novější verzi Windows, zůstane v aktuální verzi. Po zmrazení verze zůstane sada funkcí zařízení stabilní po dobu trvání zásad.

- I když je nainstalovaná verze systému Windows nastavená, zařízení můžou dál přijímat a instalovat kvality a aktualizace zabezpečení pro svou verzi Windows po dobu trvání podpory této verze, což vám pomůže zajistit aktuálnost a zabezpečení zařízení.

- Na rozdíl od použití příkazu *pozastavit* s aktualizačním kanálem, který vyprší po 35 dnech, zůstane zásada aktualizace funkcí Windows 10 platná. Zařízení neinstalují novou verzi Windows, dokud nezměníte nebo neodeberete zásady aktualizací funkcí Windows 10. Pokud zásadu upravíte a určíte novější verzi, zařízení pak mohou nainstalovat funkce z této verze systému Windows.

### <a name="limitations-for-windows-10-feature-updates"></a>Omezení pro aktualizace funkcí Windows 10

- Když nasadíte zásady *aktualizace funkcí Windows 10* do zařízení, které zároveň obdrží zásady *aktualizačního vyzvánění Windows 10* , Projděte si aktualizační kanál pro následující konfigurace:
  - **Doba odložení aktualizace funkcí (ve dnech)** musí být nastavená na **0**.
  - Musí *běžet*aktualizace funkcí pro aktualizační kanál. Nesmí být pozastavené.

- Zásady *aktualizací funkcí Windows 10* se u autopilotu nepodporují. Intune tyto zásady neimplementuje:
  - Zařízení, která jsou zřízena autopilotem.
  - Zařízení, která byla dříve zřízena s autopilotem.

  Toto omezení se zkoumá, aby bylo možné zjistit, jestli ho v budoucnu podporuje.


### <a name="create-and-assign-windows-10-feature-updates"></a>Vytvoření a přiřazení aktualizací funkcí Windows 10

1. Přihlaste se k [centru pro správu služby Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

2. Vyberte **zařízení** > **Windows** > **aktualizace funkcí Windows 10** > **vytvořit**.

3. V části **základy**zadejte název, popis (volitelný) a **aktualizaci funkcí k nasazení**, vyberte verzi Windows se sadou funkcí, kterou chcete použít, a pak vyberte **Další**.

4. V části **přiřazení**zvolte **+ Vybrat skupiny, které chcete zahrnout** , a potom přiřaďte aktualizační kanál k jedné nebo více skupinám. Pokračujte výběrem **Další** .

5. V části **zkontrolovat + vytvořit**zkontrolujte nastavení a vyberte **vytvořit** , až budete připraveni Uložit zásady aktualizací funkcí Windows 10.  

### <a name="manage-windows-10-feature-updates"></a>Správa aktualizací funkcí Windows 10

V centru pro správu přejdete na **zařízení** > **Windows** > Windows **10 aktualizace funkcí** a vyberte zásadu, kterou chcete spravovat. Zásada se otevře v podokně s **přehledem** .

V tomto podokně můžete:

- Vyberte **Odstranit** , pokud chcete zásadu odstranit z Intune a odebrat ji ze zařízení.
- Vyberte **vlastnosti** a upravte nasazení.  V podokně *vlastnosti* vyberte **Upravit** a otevřete *nastavení nasazení nebo přiřazení*, kde pak můžete nasazení upravit.
- Chcete-li zobrazit informace o zásadě, vyberte možnost **stav aktualizace koncového uživatele** .

## <a name="migrate-update-settings-to-the-azure-portal"></a>Migrace nastavení aktualizace na Azure Portal

Portál Azure Classic má také omezený počet dalších nastavení aktualizací Windows 10 v profilu konfigurace zařízení. Pokud jsou některá z těchto nastavení nakonfigurovaná při migraci na Azure Portal, důrazně doporučujeme, abyste provedli následující akce:

1. Na portále Azure Portal vytvořte aktualizační kanály Windows 10 s nastaveními, která potřebujete. Nastavení **Povolit funkce v předběžné verzi** není na webu Azure Portal podporované, protože už pro nejnovější buildy Windows 10 neplatí. Při vytváření aktualizačních kanálů můžete nakonfigurovat další tři nastavení a další nastavení aktualizací Windows 10.

   > [!NOTE]
   > Nastavení aktualizací Windows 10 vytvořená na klasickém portálu se na Azure Portalu po migraci nezobrazí. Tato nastavení se ale použijí. Pokud jste některá z nich migrovali a migrované zásady z Azure Portalu upravíte, tato nastavení se ze zásad odeberou.

2. Odstraňte nastavení aktualizací na klasickém portálu. Po migraci na Azure Portal a přidání stejných nastavení do aktualizačního kanálu musíte nastavení na portálu Classic odstranit, aby se zabránilo možným konfliktům zásad. Pokud je například stejné nastavení nakonfigurované s různými hodnotami, dojde ke konfliktu. Neexistuje snadný způsob, jak zjistit, protože nastavení nakonfigurované na klasickém portálu se nezobrazuje v Azure Portal.

## <a name="next-steps"></a>Další kroky

[Nastavení služby Windows Update podporovaná službou Intune](../windows-update-settings.md)

[Sestavy dodržování předpisů v Intune pro aktualizace](../windows-update-compliance-reports.md)

[Řešení potíží s aktualizačními kroužkami Windows 10](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/Support-Tip-Troubleshooting-Windows-10-Update-Ring-Policies/ba-p/714046)
