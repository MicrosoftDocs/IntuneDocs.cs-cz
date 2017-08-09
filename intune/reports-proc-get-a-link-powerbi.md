---
title: "Připojení k datovému skladu pomocí Power BI | Dokumentace Microsoftu"
description: "Můžete si stáhnout soubor pro použití s Microsoft Power BI, který vám umožní načíst interaktivní, dynamicky generované sestavy vašeho tenanta Intune."
keywords: "Datový sklad Intune"
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a9d99b71b9f84eea45ae597ed0f69010f6e95805
ms.sourcegitcommit: addf6a40caa22c22adfd2e2eff7d666cd1877e3c
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/04/2017
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Připojení k datovému skladu pomocí Power BI

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Můžete si stáhnout soubor pro použití s Microsoft Power BI, který vám umožní načíst interaktivní, dynamicky generované sestavy vašeho tenanta Intune. Soubor Power BI datového skladu (pbix) obsahuje nastavení připojení k vašemu tenantovi a následující ukázkové sestavy a grafy: 

  -  Zařízení
  -  Registrace
  -  zásady ochrany aplikací
  -  zásady dodržování předpisů
  -  Konfigurační profily zařízení
  -  Aktualizace softwaru
  -  Protokoly inventáře zařízení

Jsou tu také zvýrazněné trendy pro registraci, dodržování předpisů, konfigurační profil zařízení a aktualizace softwaru. Ukázkové grafy a sestavy používají uživatelsky přívětivé filtry plátna. Pokud chcete použít rozšířené filtry, podívejte se na podokno **Filtr** v aplikaci Power BI Desktop. 

Následující kroky vám ukážou, jak stáhnout soubor Power BI a jak používat odkaz OData s Power BI.

## <a name="install-power-bi"></a>Instalace Power BI

Nainstalujte si nejnovější verzi aplikace Power BI Desktop. Power BI Desktop si můžete stáhnout z webu: [PowerBI.microsoft.com](https://powerbi.microsoft.com/en-us/desktop) 

## <a name="load-the-data-and-reports-using-the-power-bi-file-pbix"></a>Načtení dat a sestav pomocí souboru Power BI (pbix)

Soubor Power BI (pbix) obsahuje informace o připojení pro vašeho tenanta a sadu předem vytvořených sestav založených na datovém modelu datového skladu. Soubor otevřete v aplikaci Power BI Desktop a přihlaste se k Azure AD. Sestava načte data z vašeho tenanta Intune.

1.  Přihlaste se k webu Azure Portal a zvolte **Monitorování + správa** > **Intune**. Můžete také vyhledat prostředky pro **Intune**.  
2.  Otevřete okno **Rozhraní API datového skladu Microsoft Intune (Preview)**.
3.  Klikněte na **Stáhnout soubor Power BI**. Soubor s příponou PBIX se stáhne do vámi zadaného umístění.
4.  Soubor otevřete pomocí Power BI. Načtou se *sestavy datového skladu Intune*. Může to ale chvíli trvat, protože se získávají data vašeho tenanta.
5.  Pokud chcete načíst data tenanta a zkontrolovat sestavy, klikněte na **Aktualizovat**.
6.  Pokud se služba Power BI neověřila pomocí přihlašovacích údajů pro Azure Active Directory, vyzve vás k zadání vašich přihlašovacích údajů. Při výběru přihlašovacích údajů zvolte jako metodu ověřování **Účet organizace**.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Načtení dat v Power BI pomocí odkazu OData

S klientem ověřeným v Azure AD se adresa URL pro OData připojí ke koncovému bodu RESTful v rozhraní API datového skladu, který zveřejní datový model do klienta sestav. Pokud chcete použít aplikaci Power BI Desktop pro připojení a vytvoření vlastních sestav, postupujte podle těchto pokynů. Nejste omezeni aplikací Power BI Desktop. Můžete použít oblíbený analytický nástroj s adresou URL pro OData, za předpokladu, že klient podporuje ověřování OAUTH2.0 a standard OData v4.0.

1.  Načtěte **adresu URL pro OData** v okně vytváření sestav, například `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`.
2.  Otevřete aplikaci **Power BI Desktop**.
3.  Zvolte **Domů** > **Získat data**. Vyberte **Datový kanál OData**.
4.  Zvolte **Základní**.
5.  Do pole adresy URL zadejte nebo vložte **adresu URL pro OData**.
6.  Klikněte na **OK**.
7.  Pokud jste se službě Azure AD pro vašeho tenanta neověřili z klienta aplikace Power BI Desktop, zadejte své přihlašovací údaje.  
    a.  Vyberte **Účet organizace**.  
    b.  Zadejte své uživatelské jméno a heslo.  
    c.  Klikněte na **Přihlásit se**.  
    d.  Klikněte na možnost **Připojit**.  
8.  Klikněte na **Načíst**.

## <a name="next-steps"></a>Další kroky

Můžete získat odpovědi na otázky týkající se vašeho prostředí, například týkající se počtu zařízení zaregistrovaných podle dne za poslední týden. Můžete získat přehled o naplnění vašeho klienta a tenanta Intune pomocí sestav využívajících soubor Power BI datového skladu Intune (pbix) načtených z okna v Azure. Intune ale poskytuje množství dalších způsobů, jak data rozšířit a znovu použít. Pomocí Power BI a rozhraní API datového skladu Intune můžete udělat mnohem víc, například:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Data tenanta budou uspořádána tak, aby vám pomohla získat lepší přehled. Další informace o způsobu uspořádání dat najdete v tématu [Datový model datového skladu](reports-ref-data-model.md). 
<!-- -  You can also access the data from a RESTful interface and incorporate the data into your own app. For more information, see [Get data from the Data Warehouse API with a REST client](reports-proc-data-rest.md). -->