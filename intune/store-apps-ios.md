---
title: Přidání aplikací pro App Store (iOS) do Microsoft Intune
titlesuffix: ''
description: Zjistěte, jak do Microsoft Intune přidat aplikace z obchodu pro iOS.
keywords: Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 03/06/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4eaa4b279ab98c6fe41482628937e0f2b0dc70a5
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Přidání aplikací pro App Store (iOS) do Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Informace v tomto článku vám pomůžou přidat do Intune aplikace z obchodu pro iOS. Aplikace z obchodu pro iOS jsou aplikace, které Intune instaluje na zařízení uživatelů. Uživatel je jeden ze zaměstnanců společnosti. Aplikace z obchodu pro iOS se automaticky aktualizují.

>[!NOTE]
>Uživatelé zařízení s iOSem můžou odebrat některé integrované aplikace pro iOS, jako jsou například aplikace Akcie a Mapy, ale není možné tyto aplikace s použitím Intune znovu nasadit. Pokud koncoví uživatelé tyto aplikace odstraní, musejí přejít do obchodu s aplikacemi a znovu si je ručně nainstalovat.

## <a name="before-you-start"></a>Než začnete

Pomocí této metody můžete aplikace přiřazovat jen v případě, že jsou v obchodě s aplikacemi bezplatné. Pokud chcete pomocí Intune přiřazovat placené aplikace, zvažte použití [programu hromadného nákupu iOS](vpp-apps-ios.md).

>[!NOTE]
>Při práci s Microsoft Intune jsou doporučenými prohlížeči Chrome a Microsoft Edge.

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V okně **Intune** zvolte **Mobilní aplikace**.
4. V úloze **Mobilní aplikace** zvolte v oddílu **Spravovat** možnost **Aplikace**.
5. Na pravé straně podokna **Aplikace** zvolte **Přidat**.
6. V seznamu **Typ aplikace** vyberte z typů **Aplikace pro Store** možnost **iOS**.
7. Zvolte **Hledat v App Storu**.
8. V okně **Hledat v App Storu** vyberte národní prostředí App Storu.
9. Do vyhledávacího pole zadejte název (nebo část názvu). Intune prohledá Store a vrátí seznam relevantních výsledků.
10. V seznamu zvolte požadovanou aplikaci a pak klikněte na **Vybrat**.
11. V okně **Přidat aplikaci** zvolte **Informace o aplikaci** a nakonfigurujte aplikaci.
12. V okně **Informace o aplikaci** přidejte následující informace o aplikaci. V závislosti na zvolené aplikaci mohou být některé hodnoty v tomto okně vyplněny automaticky:
    - **Název** – zadejte název aplikace, který se zobrazí na portálu společnosti. Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis** – zadejte popis aplikace, který se zobrazí uživatelům na portálu společnosti.
    - **Vydavatel** – zadejte název vydavatele aplikace.
    - **Adresa URL obchodu s aplikacemi** – zadejte adresu URL obchodu s aplikacemi pro aplikaci, kterou chcete vytvořit.
    - **Minimální operační systém** – v seznamu zvolte minimální verzi operačního systému, na kterou jde aplikaci nainstalovat. Na zařízení se starším operačním systémem se aplikace nenainstaluje.
    - **Použitelný typ zařízení** – ze seznamu vyberte zařízení, která aplikace používá.
    - **Kategorie** (volitelné). Vyberte jednu nebo několik předdefinovaných nebo vytvořených kategorií aplikací. Díky kategoriím uživatelé aplikaci při procházení portálu společnosti snadněji najdou.
    - **Zobrazit na Portálu společnosti jako vybranou aplikaci** – aplikace se zobrazí na význačném místě hlavní stránky portálu společnosti, když uživatelé vyhledávají aplikace.
    - **Adresa URL informací** – volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL informací o ochraně osobních údajů** – volitelně zadejte adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Vývojář** – volitelně zadejte jméno vývojáře aplikace. Toto pole vidí jenom správce a koncoví uživatelé je neuvidí.
    - **Vlastník** – volitelně zadejte vlastníka aplikace, například **Personální oddělení**.  Toto pole vidí jenom správce a koncoví uživatelé je neuvidí.
    - **Poznámky** – zadejte jakékoli poznámky, které chcete k aplikaci připojit. Toto pole vidí jenom správce a koncoví uživatelé je neuvidí.
    - **Logo** – nahrajte ikonu, která se k aplikaci přidruží. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.
13. Až budete hotovi, klikněte v okně **Informace o aplikaci** na **OK**.
14. V okně **Přidat aplikaci** klikněte na **Přidat**.

Vytvořená aplikace se zobrazí v seznamu aplikací, kde ji můžete přiřadit ke zvoleným skupinám.

## <a name="next-steps"></a>Další kroky

- [Postup přiřazení aplikací do skupin](apps-deploy.md)
