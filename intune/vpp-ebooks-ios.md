---
title: "Správa e-knih pro iOS zakoupených v rámci multilicenčního programu"
titleSuffix: Intune on Azure
description: "Zjistěte, jak synchronizovat s Intune knihy zakoupené v rámci multilicenčního programu z obchodu pro iOS a jak následně spravovat a sledovat jejich používání."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 06/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5617074-2384-4812-b913-dc94f64c0818
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e23c40eb4c13fd0d2593742c72086fc943fe2b54
ms.sourcegitcommit: 34cfebfc1d8b81032f4d41869d74dda559e677e2
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/01/2017
---
# <a name="how-to-manage-ios-ebooks-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a>Správa e-knih pro iOS zakoupených v rámci multilicenčního programu pomocí Microsoft Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Program Apple Volume Purchase Program (VPP) umožňuje nakoupit více licencí ke knize, kterou chcete distribuovat uživatelům ve vaší společnosti. Distribuovat je možné knihy z komerčních obchodů nebo obchodů s produkty určenými pro vzdělávání.

Microsoft Intune pomáhá synchronizovat, spravovat a přiřazovat knihy, které jste zakoupili prostřednictvím tohoto programu. Můžete naimportovat informace o licencích z obchodu a sledovat, kolik licencí jste použili.

Postupy při správě knih jsou podobné jako u [správy aplikací VPP](vpp-apps-ios.md).

## <a name="manage-volume-purchased-books-for-ios-devices"></a>Správa knih zakoupených v rámci multilicenčního programu pro zařízení s iOSem
Více licencí ke knihám pro iOS můžete zakoupit prostřednictvím programu [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) nebo [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store). Součástí tohoto procesu je vytvoření účtu Apple VPP na webu Apple a odeslání tokenu Apple VPP do Intune.  Potom je možné synchronizovat informace o nákupu v rámci multilicenčního programu s Intune a sledovat využití knih, které jste tímto způsobem koupili.

## <a name="before-you-start"></a>Než začnete
Než začnete, musíte od společnosti Apple získat token VPP a nahrát ho do svého účtu Intune. A dále:

* K účtu Intune můžete přiřadit až 256 tokenů VPP.
* Pokud jste už dřív použili token VPP s jiným produktem, musíte pro Intune vygenerovat nový token.
* Tokeny mají platnost jeden rok.
* Ve výchozím nastavení se Intune synchronizuje se službou Apple VPP dvakrát denně. Ruční synchronizaci můžete spustit kdykoli.
* Po naimportování tokenu VPP do Intune neimportujte stejný token do žádného jiného řešení správy zařízení. Pokud byste to udělali, mohli byste ztratit přiřazení licence a uživatelských záznamů.
* Než začnete používat knihy pro iOS s Intune, odeberte všechny existující uživatelské účty VPP vytvořené pomocí jiných řešení správy mobilních zařízení (MDM). V rámci bezpečnostních opatření Intune nesynchronizuje tyto uživatelské účty do Intune. Intune synchronizuje jenom ta data ze služby Apple VPP, která jsou vytvořená pomocí Intune.
* V současné době můžete knihy přiřadit jenom v rámci **povinné** instalace. Když přiřazujete knihu s typem instalace **Požadovaná**, využije každý uživatel, který knihu nainstaluje, jednu licenci.
* Když přiřadíte knihu k zařízení, musí být v daném zařízení nainstalovaná integrovaná aplikace iBooks. Pokud není, musí koncový uživatel aplikaci přeinstalovat, aby si mohl knihu přečíst. V současné době není možné prostřednictvím Intune obnovit odebrané integrované aplikace.
* Přiřadit je možné jenom knihy z webu Apple Volume Purchase Program. Není možné nahrát a potom přiřadit knihy, které jste vytvořili interně.
* V současné době není možné přiřazovat ke kategoriím koncových uživatelů knihy stejně jako aplikace.
* Po přiřazení knihy už není možné licenci vrátit zpět.
* Když se uživatel s oprávněným zařízením pokusí poprvé o instalaci knihy VPP, musí se před tím, než si bude moct knihu nainstalovat, připojit k programu Apple Volume Purchase. Licence také můžete přiřadit ke skupinám zabezpečení se spravovanými identifikátory Apple ID. V takovém případě nebudou uživatelé po instalaci knihy vyzváni k zadání Apple ID.

## <a name="to-get-and-upload-an-apple-vpp-token"></a>Získání a odeslání tokenu Apple VPP

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
1.  V úloze **Mobilní aplikace** zvolte **Nastavení** > **Tokeny VPP pro iOS**.
2.  V okně se seznamem tokenů VPP klikněte na **Přidat**.
3.  V okně **Nový token VPP** zadejte následující informace:
    - **Soubor tokenu VPP** – je potřeba se zaregistrovat v rámci programu Volume Purchase Program for Business nebo Volume Purchase Program for Education. Potom si stáhněte token Apple VPP pro svůj účet a vyberte ho tady.
    - **Apple ID** – zadejte Apple ID účtu přidruženého k multilicenčnímu programu.
    - **Typ účtu VPP** – zvolte jednu z možností: **Obchodní** nebo **Vzdělávání**.
4. Po dokončení klikněte na **Nahrát**.

Token se zobrazí v okně se seznamem tokenů.


Data ukládaná společností Apple můžete kdykoli synchronizovat s Intune výběrem položky **Synchronizovat nyní**.

## <a name="to-assign-a-volume-purchased-app"></a>Přiřazení aplikace zakoupené v rámci multilicenčního programu

1. V úloze **E-knihy** zvolte **Správa** > **Všechny e-knihy**.
2. V okně se seznamem knih zvolte knihu, kterou chcete přiřadit, a pak zvolte tlačítko se třemi tečkami (**...**). > **Přiřaďte skupiny**.
3. V okně <*název knihy*> – **Přiřazené skupiny** zvolte **Spravovat** > **Přiřazené skupiny**.
4. Zvolte **Přiřadit skupiny** a potom v okně **Vybrat skupiny** zvolte skupiny uživatelů Azure AD, ke kterým chcete aplikaci přiřadit. V současné době není dostupná podpora skupin zařízení.
Zvolte akci přiřazení **Povinné**. 
5. Až to budete mít, zvolte **Uložit**.

## <a name="next-steps"></a>Další kroky

Informace, které vám pomůžou při sledování přiřazování knih, najdete v článku [Jak sledovat přiřazení aplikací](apps-monitor.md).





