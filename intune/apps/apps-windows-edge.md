---
title: Přidejte Microsoft Edge pro Windows 10 a Microsoft Intune
titleSuffix: ''
description: Přečtěte si o přidání Microsoft Edge pro Windows k Microsoft Intune.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/24/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: kellieei
ms.suite: ems
search.appverid: MET150
ms.custom: ''
ms.collection: M365-identity-device-management
ms.openlocfilehash: af24b5fe33bc1e794529ef5a5ab6975eed4fb9cc
ms.sourcegitcommit: 556b7ea2049014c9027f0e44affd3f301fab55fc
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/06/2019
ms.locfileid: "73709910"
---
# <a name="add-microsoft-edge-for-windows-10-to-microsoft-intune"></a>Přidejte Microsoft Edge pro Windows 10 a Microsoft Intune

Než budete moct nasadit, nakonfigurovat, monitorovat nebo chránit aplikace, musíte je přidat do Intune. Jedním z dostupných [typů aplikací](~/apps/apps-add.md#app-types-in-microsoft-intune) je Microsoft Edge *verze 77 a novější*. Když vyberete tento typ aplikace v Intune, můžete přiřadit a nainstalovat Microsoft Edge *verze 77 a novější* na zařízení, která spravujete, na kterých běží Windows 10.

> [!IMPORTANT]
> Tento typ aplikace je ve **verzi Public Preview** a nabízí vývojové a beta kanály pro Windows 10. Nasazení je pouze anglické (EN), ale koncoví uživatelé mohou změnit jazyk zobrazení v prohlížeči v části **nastavení**  > **jazyky**. Microsoft Edge je aplikace Win32 nainstalovaná v kontextu systému a jako architektury (aplikace x86 v operačním systému x86 a x64 v operačním systému x64). Intune zjistí všechny existující instalace Microsoft Edge. Pokud je nainstalován v uživatelském kontextu, bude instalace systému přepsána. Pokud je nainstalovaný v kontextu systému, nahlásí se úspěch instalace. Automatické aktualizace Microsoft Edge jsou navíc ve výchozím nastavení **zapnuté** a Microsoft Edge nejde odinstalovat.

> [!NOTE]
> Pro macOS je k dispozici také Microsoft Edge *verze 77 a novější* .
> 
> Nemůžete použít integrované nasazení aplikace Microsoft Edge pro počítače připojení k síti na pracovišti. Integrované nasazení aplikací vyžaduje rozšíření pro správu Intune, které existuje jenom pro zařízení připojená k AAD. Verzi Microsoft Edge *77 a novější* můžete nasadit pomocí souboru *. msi* nahraného do **klientských aplikací**, viz téma [Přidání obchodní aplikace pro Windows do Microsoft Intune](~/apps/lob-apps-windows.md).

## <a name="prerequisites"></a>Požadované součásti
- Vyžaduje se Windows 10 RS2 a vyšší.
- Všechny předem nainstalované verze Microsoft Edge *verze 77 a novější* pro **vývojáře** a **beta** kanály v uživatelském kontextu budou přepsány s hranou nainstalovanými v kontextu systému.

## <a name="configure-the-app-in-intune"></a>Konfigurace aplikace v Intune
Microsoft Edge verze 77 a novější můžete do Intune přidat pomocí následujících kroků:

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. V podokně **Intune** vyberte **Klientské aplikace** > **Aplikace** > **Přidat**.
3. V seznamu **Typ aplikace** pod **Microsoft Edge verze 77 a novější**vyberte **Windows 10**.

## <a name="configure-app-information"></a>Konfigurace informací o aplikaci
V tomto kroku zadáte informace o tomto nasazení aplikace. Tyto informace vám pomůžou identifikovat aplikaci v Intune a pomáhají uživatelům najít aplikaci na portálu společnosti.

1. Kliknutím na **informace o aplikaci** zobrazíte okno **informace o aplikaci** .
2. V okně **informace o aplikaci** zadejte informace o tomto nasazení aplikace. Tyto informace vám pomůžou identifikovat aplikaci v Intune a pomáhají uživatelům najít aplikaci na portálu společnosti.
    - **Název**: zadejte název aplikace, který se zobrazí na portálu společnosti. Ujistěte se, že jsou všechny názvy jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis**: Zadejte popis aplikace. Můžete například zobrazit seznam cílových uživatelů v popisu.
    - **Vydavatel**: Jako vydavatel se zobrazí Microsoft.
    - **Kategorie**: Můžete vybrat jednu nebo několik předdefinovaných kategorií nebo kategorii, kterou jste vytvořili. Toto nastavení usnadňuje uživatelům vyhledání aplikace při procházení portálu společnosti.
    - **Zobrazit jako doporučenou aplikaci v portál společnosti**: tuto možnost vyberte, pokud chcete, aby se aplikace zobrazovala na hlavní stránce portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací**: Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů**: Volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář**: Jako vývojář se zobrazí Microsoft.
    - **Vlastník**: Jako vlastník se zobrazí Microsoft.
    - **Poznámky**: Volitelně zadejte jakékoli poznámky, které chcete k aplikaci přidružit.
3. Vyberte **OK**.

## <a name="configure-app-settings"></a>Konfigurace nastavení aplikace
V tomto kroku nakonfigurujte možnosti instalace aplikace.

1. V okně **Přidat aplikaci** vyberte **nastavení aplikace**.
2. V okně **nastavení aplikace** vyberte **beta verze** ze seznamu **kanálů** , abyste určili **, ze které** hraničního kanálu budete aplikaci nasazovat.
    - **Beta verze** Kanál je nejstabilním prostředím Microsoft Edge Preview a nejlepší volbou pro úplný pilotní nasazení v rámci vaší organizace. V případě hlavních aktualizací každých šest týdnů zahrnuje každá verze tyto učení a vylepšení z vývojového kanálu.
    - **Vývoj** Kanál je připravený na podnikovou zpětnou vazbu ve Windows, Windows serveru a macOS. Aktualizuje se každý týden a obsahuje nejnovější vylepšení a opravy.

    > [!NOTE]
    > Logo prohlížeče Microsoft Edge se zobrazí spolu s aplikací, když uživatelé procházejí portál společnosti.

3.  Vyberte **OK**.

## <a name="select-scope-tags-optional"></a>Vybrat značky oboru (volitelné)
Pomocí značek Scope můžete určit, kdo může v Intune zobrazit informace o klientské aplikaci. Úplné podrobnosti o značkách oboru najdete v tématu použití značek řízení přístupu na základě role a rozsahu pro distribuci IT.
1.  Vyberte **obor (značky)**  > **Přidat**.
2.  Pro vyhledání značek oboru použijte pole **Vybrat** .
3.  Zaškrtněte políčko vedle značek oboru, které chcete této aplikaci přiřadit.
4.  Klikněte na **vybrat**  > **OK**.

## <a name="add-the-app"></a>Přidání aplikace
Po dokončení konfigurace aplikace vyberte v okně **aplikace App App** možnost **Přidat** . 

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřazovat vybraným skupinám. 

> [!NOTE]
> Pokud zrušíte přiřazení Microsoft Edge, v tuto chvíli zůstane v zařízení.

## <a name="troubleshooting"></a>Odstraňování potíží
**Microsoft Edge verze 77 a novější pro Windows 10:**<br>
Intune používá rozšíření pro správu Intune ke stažení a nasazení instalačního programu Microsoft Edge na přiřazená zařízení s Windows 10 a pak sdělí nastavení nasazení pro instalační program Microsoft Edge, který stáhne a nainstaluje prohlížeč Microsoft Edge. přímo ze sítě CDN. Odkažte na [požadavky pro rozšíření pro správu Intune](~/apps/intune-management-extension.md#prerequisites)a osvědčené postupy, které jsou uvedené v části přístup ke službě Azure Update a CDN, aby bylo zajištěno, že konfigurace sítě umožní přístup k těmto umístěním pro zařízení s Windows 10. Chcete-li kromě toho dovolit přístup k instalačním souborům ze sítě CDN pro instalaci prohlížeče, je nutné povolený přístup k koncovým bodům web Windows Update. Další informace najdete v tématu [Správa koncových bodů připojení pro Windows 10, verze 1809 – web Windows Update](https://docs.microsoft.com/windows/privacy/manage-windows-1809-endpoints#windows-update) a [koncových bodů sítě pro Microsoft Intune](~/fundamentals/intune-endpoints.md).

## <a name="next-steps"></a>Další kroky
- [Přiřazení aplikací skupinám](~/apps/apps-deploy.md)
