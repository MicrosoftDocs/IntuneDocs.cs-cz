---
title: Připojení k datovému skladu pomocí Power BI
titlesuffix: Microsoft Intune
description: Můžete si stáhnout soubor pro použití s Microsoft Power BI, který vám umožní načíst interaktivní, dynamicky generované sestavy vašeho tenanta Microsoft Intune.
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 12/20/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2b911adab0357bea50e3e08821766d45e903e69b
ms.sourcegitcommit: 430b290474b11f9df87785b01edc178e6bae2049
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57394149"
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Připojení k datovému skladu pomocí Power BI

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Můžete si stáhnout soubor pro použití s Microsoft Power BI, který vám umožní načíst interaktivní, dynamicky generované sestavy vašeho tenanta Intune. Soubor Power BI datového skladu (pbix) obsahuje nastavení připojení k vašemu tenantovi a také následující ukázkové sestavy a grafy:  

  -  Zařízení
  -  Registrace
  -  zásady ochrany aplikací
  -  zásady dodržování předpisů
  -  Konfigurační profily zařízení
  -  Aktualizace softwaru
  -  Protokoly inventáře zařízení

Jsou tu také zvýrazněné trendy pro registraci, dodržování předpisů, konfigurační profil zařízení a aktualizace softwaru. Ukázkové grafy a sestavy používají uživatelsky přívětivé filtry plátna. Pokud chcete použít rozšířené filtry, podívejte se na podokno **Filtr** v aplikaci Power BI Desktop.

Následující kroky vám ukážou, jak stáhnout soubor Power BI a jak používat odkaz OData s Power BI.

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="install-power-bi"></a>Instalace Power BI

Nainstalujte si nejnovější verzi aplikace Power BI Desktop. Power BI Desktopu z si můžete stáhnout: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)

## <a name="load-the-data-and-reports-using-the-power-bi-file-pbix"></a>Načtení dat a sestav pomocí souboru Power BI (pbix)

Soubor Power BI (pbix) obsahuje informace o připojení pro vašeho tenanta a sadu předem vytvořených sestav založených na datovém modelu datového skladu. Soubor otevřete v aplikaci Power BI Desktop a přihlaste se k Azure AD. Sestava načte data z vašeho tenanta Intune.

> [!Important]  
> Jednotlivé soubory Power BI (pbix) se můžou lišit podle umístění tenanta. Pokud spravujete několik tenantů Intune, je nutné použít soubor, který jste z portálu Azure Portal stáhli, když jste byli přihlášení k požadovanému tenantovi.  

1.  Přihlaste se k webu Azure Portal a zvolte **Monitorování + správa** > **Intune**. Můžete také vyhledat prostředky pro **Intune**.  
2.  Otevřete okno **Rozhraní API datového skladu Microsoft Intune (Preview)**.
3.  Vyberte **Stáhnout soubor Power BI**. Soubor s příponou PBIX se stáhne do vámi zadaného umístění.
4.  Soubor otevřete pomocí Power BI. Načtou se *sestavy datového skladu Intune*. Získání dat vašeho tenanta ale může chvíli trvat.
5.  Pokud chcete načíst data tenanta a zkontrolovat sestavy, vyberte **Aktualizovat**.
6.  Pokud se služba Power BI neověřila pomocí přihlašovacích údajů pro Azure Active Directory, vyzve vás k zadání vašich přihlašovacích údajů. Při výběru přihlašovacích údajů zvolte jako metodu ověřování **Účet organizace**.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Načtení dat v Power BI pomocí odkazu OData

S klientem ověřeným v Azure AD se adresa URL pro OData připojí ke koncovému bodu RESTful v rozhraní API datového skladu, který zveřejní datový model do klienta sestav. Pokud chcete použít aplikaci Power BI Desktop pro připojení a vytvoření vlastních sestav, postupujte podle těchto pokynů. Nejste omezeni aplikací Power BI Desktop. Můžete použít oblíbený analytický nástroj s adresou URL pro OData, za předpokladu, že klient podporuje ověřování OAUTH2.0 a standard OData v4.0.

1.  Přihlaste se k webu Azure Portal a zvolte **Monitorování + správa** > **Intune**. Můžete také vyhledat prostředky pro **Intune**.  
2.  Otevřete okno **Rozhraní API datového skladu Microsoft Intune (Preview)**.
3. V okně vytváření sestav načtěte adresu URL vlastního informačního kanálu, například `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`.
4. Otevřete aplikaci **Power BI Desktop**.
5. Zvolte **Domů** > **Získat data**. Vyberte **Datový kanál OData**.
6. Zvolte **Základní**.
7. Do pole adresy URL zadejte nebo vložte **adresu URL pro OData**.
8. Vyberte **OK**.
9. Pokud jste se službě Azure AD pro vašeho tenanta neověřili z klienta aplikace Power BI Desktop, zadejte své přihlašovací údaje. Abyste získali přístup k datům, musíte se vůči službě Azure Active Directory (Azure AD) autorizovat protokolem OAuth 2.0.  
    1.  Vyberte **Účet organizace**.  
    2.  Zadejte své uživatelské jméno a heslo.  
    3.  Vyberte **Přihlásit se**.  
    4.  Vyberte **Connect** (Připojit).  
10. Vyberte **Načíst**.

## <a name="next-steps"></a>Další postup

Můžete získat odpovědi na otázky týkající se vašeho prostředí, například týkající se počtu zařízení zaregistrovaných podle dne za poslední týden. Můžete získat přehled o naplnění vašeho klienta a tenanta Intune pomocí sestav využívajících soubor Power BI datového skladu Intune (pbix) načtených z okna v Azure. Intune ale poskytuje množství dalších způsobů, jak data rozšířit a znovu použít. Pomocí Power BI a rozhraní API datového skladu Intune můžete udělat mnohem víc, například:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Data tenanta budou uspořádána tak, aby vám pomohla získat lepší přehled. Další informace o způsobu uspořádání dat najdete v tématu [Datový model datového skladu](reports-ref-data-model.md).
 -  K datům můžete získat přístup také z rozhraní RESTful a začlenit je do své vlastní aplikace. Další informace najdete v článku [Získání dat z rozhraní API datového skladu pomocí klienta REST](reports-proc-data-rest.md).
