---
title: Konfigurace služby Windows Update pro firmy v Microsoft Intune – Azure | Microsoft Docs
description: Přečtěte si, jak upravit nastavení aktualizací softwaru na profilu a vytvořit aktualizační kanál, zkontrolujte dodržování předpisů a zjistěte, jak pozastavit aktualizace v nastavení služby Windows Update pro firmy pomocí Microsoft Intune na zařízeních s Windows 10.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/12/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: coryfe
ms.suite: ems
search.appverid: MET150
ms.collection: M365-identity-device-management
ms.openlocfilehash: 05fd362ff6f068669b85b9b78cb1dfd7d3c8011f
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57397222"
---
# <a name="manage-software-updates-in-intune"></a>Správa softwarových aktualizací v Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Intune můžete použít k definování aktualizačních kanálů, které určují, jak a kdy jako služba Windows aktualizace zařízení s Windows 10. Aktualizační kanály jsou zásady, kterou můžete přiřadit ke skupinám zařízení. Pomocí aktualizačních kanálů můžete vytvořit strategii aktualizace, která odráží vaše firemní potřeby. Další informace najdete v tématu o [správě aktualizací pomocí Windows Update pro firmy](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb).

Ve Windows 10 obsahují nové aktualizace funkcí a aktualizace pro zvýšení kvality obsah všech předchozích aktualizací. Pokud si nainstalujete nejnovější aktualizaci, máte jistotu, že jsou vaše zařízení s Windows 10 aktuální. Na rozdíl od předchozích verzí Windows je teď nutné nainstalovat celou aktualizaci (a ne jenom její část).


Služba Windows Update pro firmy vám zjednodušuje správu aktualizací. Nemusíte tak schvalovat jednotlivé aktualizace pro skupiny zařízení. Konfigurací vhodné strategie zavádění aktualizací budete mít pod kontrolou řízení rizik ve svém prostředí. Intune poskytuje možnost [nakonfigurovat nastavení aktualizací](windows-update-settings.md) na zařízeních a umožňuje pozdržet instalaci aktualizací. V Intune nejsou uložené samotné aktualizace, ale jenom přiřazení zásad aktualizací. Zařízení kvůli aktualizacím přistupují přímo k webu Windows Update. Tato kolekce nastavení, která lze konfigurovat, když se nainstalují aktualizace Windows 10 je volána *aktualizační kanál Windows 10*.

Windows 10 aktualizačních kanálů podpory [značky oboru](scope-tags.md). Značky oboru můžete pomocí aktualizačních kanálů můžete filtrovat a Správa sad konfigurace, které používáte.

## <a name="prerequisites"></a>Požadavky  

Použití funkce aktualizace pro Windows pro zařízení s Windows 10 v Intune musí být splněny následující požadavky.  

- Windows 10 počítačích musí běžet minimálně Windows 10 Pro s aktualizací Windows Anniversary update nebo novější (verze 1607 nebo novější)
- Windows Update podporuje následující edice Windows 10:
  - Windows 10
  - Windows 10 Team (pro zařízení Surface Hubu)
  - Windows Holographic for Business  

    Windows Holographic for Business podporuje podmnožinu nastavení aktualizací Windows, včetně:
    - **Chování automatické aktualizace**
    - **Aktualizace produktů Microsoftu**
    - **Kanál pro údržbu**: Podporuje **pololetní kanál** a **pololetní kanál (cílený)** možnosti  

    Další informace najdete v tématu [Správa Windows Holographic](windows-holographic-for-business.md)  
  
  Zařízení s Windows 10 Mobile nejsou podporovaná.

- Na zařízeních s Windows **zpětná vazba a Diagnostika** > **data diagnostiky a použití** musí být nastaveno na **základní**, **rozšířená**, nebo **úplné**.  

  Můžete nakonfigurovat toto nastavení ručně nebo pomocí profilu omezení zařízení Intune pro Windows 10 a novější. Pokud chcete použít profil omezení zařízení, konfigurovat nastavení **Obecné** > **odeslání diagnostických dat** na alespoň **základní**. Další informace o profilech zařízení najdete v tématu [Konfigurace nastavení omezení zařízení](device-restrictions-configure.md).  

- Pokud používáte portál Azure classic, [migrace nastavení na webu Azure portal](#migrate-update-settings-to-the-azure-portal).  

## <a name="create-and-assign-update-rings"></a>Vytvoření a přiřazení aktualizačních kanálů

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a potom vyberte **Microsoft Intune**.
3. Vyberte **Aktualizace softwaru** > **Aktualizační kanály Windows 10** > **Vytvořit**.
4. Zadejte název a popis (volitelný) a potom zvolte **Konfigurovat**.
5. V **nastavení**, nakonfigurujte nastavení pro vaše obchodní potřeby. Informace o dostupných nastaveních najdete v tématu [Windows aktualizujte nastavení](windows-update-settings.md).  
6. Po dokončení zvolte **OK**. V podokně **Vytvořit aktualizační kanál** vyberte **Vytvořit**. Nový aktualizační kanál se zobrazí v seznamu aktualizačních kanálů.
7. Pokud chcete přiřadit kanál, v seznamu aktualizačních kanálů, vyberte kanál a pak na \<název kanálu > kartě **přiřazení**.
8. Použití **zahrnout** a **vyloučit** karty k definování, které seskupí kanál je přiřazeno a pak vyberte **Uložit** tím přiřazení dokončíte.

## <a name="manage-your-windows-10-update-rings"></a>Spravovat vaše aktualizační kanály Windows 10
Na portálu, můžete vybrat aktualizační kanál Windows 10 a otevřete její **přehled** podokně. V tomto podokně můžete zobrazit stav přiřazení aktualizační kanály a provést další akce ke správě kanál. 
### <a name="to-view-an-updates-rings-overview-pane"></a>Chcete-li zobrazit podokno Přehled aktualizace aktualizační kanály: 
1. Přihlaste se k portálu Azure.
2. Přejděte do **Intune** > **aktualizace softwaru** > **aktualizační kanály Windows 10**.
3. Vyberte aktualizační kanál, který chcete zobrazit nebo spravovat.  

Kromě zobrazování stavu přiřazení, můžete vybrat z horní části podokna přehledu ke správě aktualizační kanál následující akce:  
- [Odstranění](#delete)  
- [Pozastavení](#pause)  
- [Obnovení](#resume)  
- [Rozšíření](#extend)  
- [Odinstalace](#uninstall)  

![Dostupné akce](./media/windows-update-for-business-configure/overview-actions.png)

### <a name="delete"></a>Odstranění  
Vyberte **odstranit** zastavit vynucení nastavení vybrané aktualizační kanál Windows 10. Odstranění okruhu odebere jeho konfigurace ze služby Intune, tak, aby Intune již nadále platí a vynucuje tato nastavení.  

Odstranění okruhu ze služby Intune nezmění nastavení na zařízení, která byly přiřazeny aktualizační kanál.  Místo toho zařízení zachová aktuální nastavení. Toto je vzhledem k tomu, že zařízení neudržují Historický záznam co nastavení bylo dříve použito, a vzhledem k tomu, že zařízení může získat nastavení z další aktualizační kanály, které zůstávají aktivní.  

#### <a name="to-delete-a-ring"></a>Chcete-li odstranit okruhu  
1. Při zobrazení na stránce s přehledem pro aktualizační kanál, vyberte **odstranit**.  
2. Vyberte **OK**.  

### <a name="pause"></a>Pozastavení  
Vyberte **pozastavit** zabránit přiřazených zařízeních zamčený příjem aktualizací funkcí nebo aktualizací kvality po dobu až 35 dní od okamžiku pozastavení kanál. Po uplynutí maximálního počtu dní funkce pozastavení automaticky vyprší a zařízení zkontroluje dostupné aktualizace ve Windows Update. Po této kontrole můžete aktualizace znovu pozastavit. Pokud budete pokračovat pozastaveného aktualizační kanál a potom pozastavte tento kanál znovu, obnoví období pozastavení na 35 dní.  

 #### <a name="to-pause-a-ring"></a>Chcete-li pozastavit okruhu  
1. Při zobrazení na stránce s přehledem pro aktualizační kanál, vyberte **pozastavení**.  
2. Vyberte buď **funkce** nebo **kvality** pozastavení daný typ aktualizace, a pak vyberte **OK**.  
3. Po pozastavení jeden typ aktualizace, můžete vybrat Pause pozastavit daný typ aktualizace.  

Pokud typ aktualizace je pozastavený, zobrazí podokno s přehledem pro tento kanál, kolik dní zbývá před tuto aktualizaci zadejte obnoví.

> [!IMPORTANT]  
> Po vydáte příkaz k pozastavení, zařízení ho obdrží při dalším přihlášením ke službě. Je možné, že před přihlášením ke službě nainstalují plánovanou aktualizaci. Kromě toho platí, že pokud je cílové zařízení při vydání příkazu k pozastavení vypnuté, může po zapnutí stáhnout a nainstalovat plánované aktualizace před tím, než se přihlásí k Intune.

### <a name="resume"></a>Obnovit  
Zatímco aktualizační kanál je pozastavený, můžete vybrat **Resume** obnovit aktualizace funkcí a kvality pro tento kanál aktivní operace. Po probuzení aktualizační kanál, je možné pozastavit tento kanál znovu.  

#### <a name="to-resume-a-ring"></a>Obnovit jako kruh  
1. Při zobrazení na stránce s přehledem pro pozastavené aktualizační kanál, vyberte **Resume**.  
2. Vyberte z dostupných možností obnovit buď **funkce** nebo **kvality** aktualizace a pak vyberte **OK**.  
3. Po obnovení jeden typ aktualizace, můžete vybrat pokračovat obnovit jiný typ aktualizace.  

### <a name="extend"></a>Rozšíření  
Zatímco aktualizační kanál je pozastavený, můžete vybrat **rozšířit** obnovíte doby pozastavit aktualizace funkcí a kvality pro tento aktualizační kanál po dobu 35 dní.  

#### <a name="to-extend-the-pause-period-for-a-ring"></a>Prodloužení doby pozastavit o okruhu  
1. Při zobrazení na stránce s přehledem pro pozastavené aktualizační kanál, vyberte **rozšířit**. 
2. Vyberte z dostupných možností obnovit buď **funkce** nebo **kvality** aktualizace a pak vyberte **OK**.  
3. Po prodlužuje se pozastavení pro jeden typ aktualizace, můžete vybrat rozšíření znovu pro daný typ aktualizace rozšíření.  

### <a name="uninstall"></a>Odinstalace  
Správce Intune můžete použít **odinstalovat** odinstalace (vrácení zpět) na nejnovější verzi *funkce* update nebo si prohlédnout nejnovější *kvality* aktualizace pro aktivní nebo pozastaveného aktualizační kanál. Po odinstalování serveru jeden typ, pak můžete odinstalovat jiného typu. Intune nepodporuje ani spravovat možnost odinstalovat aktualizace uživatelů.  

Odinstalace proběhla úspěšně:  
- Zařízení musí používat Windows 10. dubna 2018 update (verze 1803) nebo novější.  

Zařízení musí mít nainstalované nejnovější aktualizace. Protože jsou kumulativní aktualizace, zařízení, která nainstalovat nejnovější aktualizaci budou mít nejnovější aktualizace funkcí a kvality. Příkladem může být při použití této možnosti je vrátit zpět poslední aktualizace by měl zjistit nejnovější vydání na počítačích s Windows 10.  

Použijete-li odinstalovat, zvažte následující:  
- Odinstalace aktualizace funkcí nebo kvality je dostupná jenom pro kanál pro údržbu, ve kterém se dané zařízení nachází.  

- Pomocí funkce odinstalovat nebo aktualizace kvality se aktivuje zásadu, která obnovit předchozí aktualizace na počítačích s Windows 10.  

- Na zařízení s Windows 10 po aktualizaci kvality úspěšně vrácena zpět, koncoví uživatelé nadále zobrazovat aktualizaci uvedenou v **nastavení Windows** > **aktualizuje**  >  **Aktualizace historie**.  

- Pro funkci aktualizace konkrétně, čas můžete odinstalovat aktualizace funkcí je omezena z 2 až 60 dní, podle konfigurace v rámci nastavení aktualizace update okruhy **nastavit odinstalace aktualizací funkcí období (2 – 60 dní)**. Aktualizace funkcí, který je nainstalovaný na zařízení aktualizací funkcí po instalaci pro delší než nakonfigurované období odinstalace nelze vrátit zpět.  

  Představte si třeba aktualizační kanál s funkcí aktualizace odinstalovat 20 dnů. Za 25 dnů rozhodnete vrátit nejnovější aktualizace funkcí a použijte možnost odinstalovat.  Zařízení s nainstalovanou aktualizací funkcí před více než 20 dny ji nelze odinstalovat, protože se odebraly nezbytné bity jako součást jejich údržbu. Zařízení, která instaluje aktualizace funkcí do 19 dny však můžete aktualizaci odinstalovat, pokud se úspěšně vrácení se změnami do zobrazí příkaz odinstalovat před překročení doby 20 dnů odinstalovat.  

Další informace o vytváření zásad Windows Update najdete v tématu [Update CSP](https://docs.microsoft.com/windows/client-management/mdm/update-csp) v dokumentaci ke klientu správy Windows.  

#### <a name="to-uninstall-the-latest-windows-10-update"></a>Odinstalace nejnovější aktualizace Windows 10  
1. Při zobrazení na stránce s přehledem pro pozastavené aktualizační kanál, vyberte **odinstalovat**.  
2. Vyberte z dostupných možností odinstalace buď **funkce** nebo **kvality** aktualizace a pak vyberte **OK**.  
3. Po aktivaci odinstalace pro jeden typ aktualizace, můžete vybrat odinstalovat odinstalovat zbývající typ aktualizace.  

## <a name="migrate-update-settings-to-the-azure-portal"></a>Migrace nastavení aktualizací na webu Azure portal  
Portál Azure Classic má také omezený počet dalších nastavení aktualizací Windows 10 v profilu konfigurace zařízení. Pokud máte některá z těchto nastavení nakonfigurovaná při migraci na Azure Portal, důrazně doporučujeme, abyste udělali toto:  

1. Na portále Azure Portal vytvořte aktualizační kanály Windows 10 s nastaveními, která potřebujete. Nastavení **Povolit funkce v předběžné verzi** není na webu Azure Portal podporované, protože už pro nejnovější buildy Windows 10 neplatí. Při vytvoření aktualizačních kanálů můžete nakonfigurovat ostatní tři nastavení i další nastavení aktualizace Windows 10.  

   > [!NOTE]  
   > Nastavení aktualizací Windows 10 vytvořená na klasickém portálu se na Azure Portalu po migraci nezobrazí. Tato nastavení se ale použijí. Pokud jste některá z nich migrovali a migrované zásady z Azure Portalu upravíte, tato nastavení se ze zásad odeberou.  

2. Odstraňte nastavení aktualizací na klasickém portálu. Po migraci na Azure Portal a přidání stejných nastavení do aktualizačního kanálu musíte nastavení na portálu Classic odstranit, aby se zabránilo možným konfliktům zásad. Pokud je například stejné nastavení nakonfigurované s odlišnými hodnotami, dojde ke konfliktu. Není k dispozici snadný způsob, jak poznat, protože nastavení nakonfigurované na klasickém portálu se nezobrazí na portálu Azure portal.  

## <a name="next-steps"></a>Další postup
[Windows aktualizujte nastavení podporovaných službou Intune](windows-update-settings.md)  

[Sestavy dodržování předpisů Intune pro aktualizace](windows-update-compliance-reports.md)

