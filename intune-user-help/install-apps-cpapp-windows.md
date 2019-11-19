---
title: Windows 用 Intune ポータル サイト アプリからアプリをインストールする
description: Windows 用ポータル サイト アプリからアプリをインストールして共有する
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.subservice: end-user
ms.technology: ''
ms.assetid: ''
searchScope:
- User help
ROBOTS: ''
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 80fd2d54a99bc3f4ab47f48f94eb14aa1a7f630c
ms.sourcegitcommit: 5c52879f3653e22bfeba4eef65e2c86025534dab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/16/2019
ms.locfileid: "74126196"
---
# <a name="install-and-share-apps-on-your-device"></a>デバイスにアプリをインストールして共有する

Windows 用 Intune ポータル サイト アプリからデバイスにアプリをインストールします。

## <a name="install-apps"></a>アプリのインストール

1. Intune ポータル サイト アプリを開き、職場または学校アカウントでサインインします。  

    ![Windows 10 用 Intune ポータル サイト アプリのホーム ページ。](./media/RS1_AppDetailsPage_Installed_03.png)
2. Intune ポータル サイト アプリの次のいずれかのセクションでアプリを検索してインストールします。  

    * **[ホーム]** : 組織のおすすめアプリの一覧から選びます。  
    * **[すべて表示]** : **[ホーム] ページ** >  **[アプリ]** セクションで、 **[すべて表示]** をクリックして、使用可能なすべてのアプリを表示します。  
    * **[すべてのアプリ]** : インストール済みおよびおすすめのアプリを含む使用可能なすべてのアプリを表示するには、ナビゲーション ウィンドウでこのページを選択します。 Zobrazení, řazení a filtrování aplikací 検索結果は関連性で自動的に並べ替えられます。  
    * **Kategorie aplikací**: Výběrem této stránky v navigačním podokně vyberte aplikace na základě typu nebo funkce. Aplikace jsou seřazené pod kategoriemi, jako jsou **Doporučené**, **vzdělávání**a **produktivita**.  
    * **[アプリを検索]** : アプリのナビゲーション ウィンドウには、固定の検索バーがあります。 使用可能なアプリを検索するには、アプリ名または発行者で検索します。  

3. アプリを選択します。   
4. [アプリの詳細] ページで、 **[インストール]** をクリックします。 インストールが完了すると、 **[インストール済み]** 状態が表示されます。  

    ![Windows 10 用ポータル サイト アプリ、アプリの選択、[アプリの詳細] ページ。](./media/RS1_AppDetailsPage_Installed_02.png)  
    
    ![アプリのインストール後の [インストール済み] 状態が表示された Windows 10 用 Intune ポータル サイト アプリの [アプリの詳細] ページ。 [インストール] ボタンが [再インストール] に変更されています。](./media/RS1_AppDetailsPage_Installed_01.png)    

> [!IMPORTANT]
> Pokud se požadovaná aplikace nedokáže nainstalovat a vaše organizace ji zpřístupní pro ruční instalaci, vyberte **Opakovat**. Zobrazení aktualizovaného stavu může trvat až deset minut. Pokud při této době vyberete znovu možnost **Opakovat** a zobrazí se chyba, je to v pořádku. Nadále čekat na aktualizovaný stav deset minut.   

会社の規模によっては、Intune ポータル サイトからダウンロードできる Office のバージョンが複数表示される場合があります。 Windows デバイス用 Office スイートに関する具体的な情報については、「[Windows 10 デバイスに Office 365 をインストールする](./install-office-windows.md)」をご覧ください。

## <a name="share-apps"></a>Sdílení aplikací  
職場や学校の連絡先にアプリを共有したりお勧めしたりします。 次の手順は、Intune ポータル サイトから直接リンクを共有する方法を示しています。

1. Intune ポータル サイトで任意のアプリを右クリックするか、長押しして、その[コンテキスト メニュー](https://docs.microsoft.com//windows/uwp/design/controls-and-patterns/menus)を開きます。  

    ![アプリとデバイスの一覧が表示されている、Windows 10 用 Intune ポータル サイト アプリのフロント ページ。 クリック可能な [共有] コンテキスト メニューが、サンプル アプリのアイコンの上部に表示されます。 ](./media/1808_ShareContext_CP_Windows.png)  

2. **[共有]** を選択します。
3. 個別の連絡先から選択するか、OneNote などの別のプログラムを選択して、グループに送信します。 使用するアプリが表示されない場合は、 **[Get apps in Store]\(ストアでアプリを入手\)** を選択して、その他の使用可能なアプリを参照します。  

    ![Windows 10 用 Intune ポータル サイト アプリの [共有] ポップアップ ページのサンプル スクリーンショット。 ページには、[Learn about <example app name> in the Company Portal app]\(Intune ポータル サイト アプリの <サンプル アプリ名> の詳細\) と表示されています。 これには、リンクを送信するために選択できる、1 人の連絡先と 2 つのアプリと、[Get apps in Store]\(ストアでアプリを入手\) リンクが表示されています。 ](./media/1808_ShareApps_CP_Windows.png) 

共有すると、受信者はアプリの詳細を表示するためのリンクとメッセージを受け取ります。 このリンクにより、ポータル サイトの **[アプリの詳細]** ページが開きます。 

## <a name="optional-and-required-apps"></a>Volitelné a požadované aplikace
Aplikace vám přiřadí vaše organizace. Vaše organizace bude vyžadovat, abyste měli některé aplikace a aplikace budou volitelné. Pokud chcete zjistit, které aplikace jsou vyžadované a volitelné, nahlédněte do části **nainstalované aplikace** a podívejte se do sloupce **požadovaného vaší organizací**.  

* Volitelné aplikace: tyto aplikace jsou vybrané vaší organizací a jsou vhodné a užitečné pro práci nebo školu. Jsou k dispozici pro vás, ale je to na vás, ať už je chcete nainstalovat. Toto jsou jediný druh aplikací, které najdete v Portál společnosti k instalaci. 

* Požadované aplikace: tyto aplikace jsou nutné pro práci a školu a nasazují se přímo do vašeho zařízení. Tyto aplikace se automaticky nainstalují bez zásahu. 

アプリは、デバイスの種類に基づいて使用が許可されます。 たとえば、Windows 用ポータル サイト アプリを使用している場合、Windows アプリにはアクセスできますが、iOS アプリにはアクセスできません。

## <a name="request-an-app-for-work-or-school"></a>職場または学校用のアプリを要求する  
必要なアプリがあるが、ポータル サイト内に存在しない場合は、そのアプリを要求します。 ポータル サイト アプリの [ヘルプとサポート] ページで、**ヘルプデスク**の連絡先詳細を確認してください。 同じ連絡先情報は、[ポータル サイト Web サイト](https://go.microsoft.com/fwlink/?linkid=2010980)でも確認できます。    

  ![Windows 10 用ポータル サイト アプリの [ヘルプとサポート] ページで、ヘルプデスクの詳細を強調表示。 ](./media/1812_UCP_Help_Support_helpdesk.png)  

## <a name="view-installed-apps"></a>Zobrazit nainstalované aplikace  
Zobrazí seznam všech aplikací nainstalovaných v zařízení. Na stránce **nainstalované aplikace** jsou uvedeny následující podrobnosti o každé aplikaci:

* [名前]: アプリの名前。 Volitelné aplikace zahrnují odkaz na stránku **podrobností aplikace** .
* Typ přiřazení: jak se aplikace přiřadí a zpřístupní vám. 
* Vydavatel: název vývojáře nebo společnosti, která aplikaci distribuuje. Vydavatelem je obvykle dodavatel softwaru nebo organizace.  
* Datum publikování: datum, kdy byla aplikace zpřístupněna ke stažení. Datum publikování by mohlo Ukázat počáteční verzi aplikace nebo nejnovější aktualizaci aplikace.
* Stav: aktuální stav instalace aplikace na vašem zařízení. Aplikace se můžou zobrazovat jako instalace, instalace a instalace se nezdařilo. Aby bylo možné zobrazit aktuální stav, můžou požadované aplikace trvat až 10 minut. Důležité informace o instalaci požadované aplikace najdete v poznámce v části [instalace aplikací](#install-apps) . 

Pokud se chcete dostat na tuto stránku, přejděte do navigační nabídky a vyberte **nainstalované aplikace**.  


Pomocí **Seřadit podle** můžete změnit uspořádání typu přiřazení aplikace, vydavatele, abecedně podle názvu nebo chronologicky podle data publikování. Pomocí **Filter by** můžete omezit aplikace, se kterými se zobrazuje stav instalace.  Pokud nejsou k dispozici žádné aplikace, zobrazí se zpráva, že nebyly nainstalovány žádné aplikace společnosti.  

さらに手助けが必要ですか。 社内サポートに問い合わせてください。 連絡先情報については、[ポータル サイト Web サイト](https://go.microsoft.com/fwlink/?linkid=2010980)をご確認ください。  
