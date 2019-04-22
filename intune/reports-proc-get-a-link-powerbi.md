---
title: Připojení k datovému skladu pomocí Power BI
titleSuffix: Microsoft Intune
description: Můžete si stáhnout soubor pro použití s Microsoft Power BI, který vám umožní načíst interaktivní, dynamicky generované sestavy vašeho tenanta Microsoft Intune.
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 04/02/2019
ms.topic: reference
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
ms.openlocfilehash: 259d700d04547a801b0ebc37242dacf536ad61d3
ms.sourcegitcommit: 1cae690ca2ac6cc97bbcdf656f54b31878297ae8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "59899699"
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Připojení k datovému skladu pomocí Power BI

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Můžete aplikaci dodržování předpisů službou Power BI načíst interaktivní, dynamicky generované sestavy vašeho tenanta Intune. Kromě toho můžete načíst data tenanta v Power BI pomocí odkazu OData. Intune poskytuje nastavení připojení k vašemu tenantovi tak, aby se zobrazí následující ukázkové sestavy a související s grafy:  

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

Nainstalujte nejnovější verzi [Power BI Desktopu](https://aka.ms/intune/datawarehouseapi/installpowerbi). Další informace najdete v tématu [Power BI Desktopu](https://powerbi.microsoft.com/desktop)

## <a name="load-the-data-and-reports-using-the-power-bi-intune-compliance-data-warehouse-app"></a>Načtení dat a sestavy pomocí aplikace Power BI Intune dodržování předpisů datového skladu

Power BI [datový sklad Intune dodržování předpisů aplikace](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) obsahuje informace pro vašeho tenanta a sadu předem vytvořených sestav založených na datovém modelu datového skladu.

1.  Přejděte [datový sklad Intune dodržování předpisů aplikace](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) k zahájení procesu instalace.
2.  Po zobrazení výzvy k instalaci aplikace Power BI z důvěryhodných zdrojů, klikněte na tlačítko **nainstalovat**.
3.  Klikněte na **aplikace skladu dat dodržování předpisů Intune** dlaždici.
4.  Klikněte na tlačítko **propojení dat** tlačítko. 
    **Připojit k aplikaci skladu dat dodržování předpisů Intune** se zobrazí dialogové okno.
5.  Klikněte na tlačítko **přihlášení** tlačítko.
6.  Přihlaste se pomocí uživatelského účtu, který má přístup k datovému skladu Intune pro tenanta, který má hlásí, že chcete zobrazit. 
7.  Klikněte na tlačítko **sestavy** kartu a potom klikněte na tlačítko **dodržování předpisů V1.0** sestavy.
8.  Abyste usnadnili snadnou přejít zpět na tyto sestavy později, klikněte na hvězdičku vedle **V1.0 dodržování předpisů** sestavy. Sestava se přidá do oblíbených položek Power BI.

Alternativně můžete nainstalovat aplikace z portálu Intune:

1.  Přihlaste se k webu Azure Portal a zvolte **Monitorování + správa** > **Intune**. Můžete také hledat prostředky Intune.
2.  Otevřít **nastavení datového skladu Intune** okno.
3.  Vyberte **získat aplikace Power BI** pro přístup k a sdílet předem vytvořených sestav Power BI pro vašeho tenanta v prohlížeči.
4.  Postupujte podle kroků 2 až 8 výše.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Načtení dat v Power BI pomocí odkazu OData

S klientem ověřeným v Azure AD se adresa URL pro OData připojí ke koncovému bodu RESTful v rozhraní API datového skladu, který zveřejní datový model do klienta sestav. Pokud chcete použít aplikaci Power BI Desktop pro připojení a vytvoření vlastních sestav, postupujte podle těchto pokynů. Nejste omezeni aplikací Power BI Desktop. Můžete použít oblíbený analytický nástroj s adresou URL pro OData, za předpokladu, že klient podporuje ověřování OAUTH2.0 a standard OData v4.0.

1.  Přihlaste se k webu Azure Portal a zvolte **Monitorování + správa** > **Intune**. Můžete také vyhledat prostředky pro **Intune**.  
2.  Otevřít **nastavení datového skladu Intune** okno.
3. V okně vytváření sestav načtěte adresu URL vlastního informačního kanálu, například `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=v1.0`.
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

Můžete získat odpovědi na otázky týkající se vašeho prostředí, například týkající se počtu zařízení zaregistrovaných podle dne za poslední týden. Můžete získat přehled vašeho klienta a tenanta základního souboru Intune pomocí sestav Power BI datového skladu Intune načtených z okna v Azure. Intune ale poskytuje množství dalších způsobů, jak data rozšířit a znovu použít. Power BI a rozhraní API datového skladu Intune poskytují další funkce, například:

<!-- -  You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
 -  Data tenanta budou uspořádána tak, aby vám pomohla získat lepší přehled. Další informace o způsobu uspořádání dat najdete v tématu [Datový model datového skladu](reports-ref-data-model.md).
 -  K datům můžete získat přístup také z rozhraní RESTful a začlenit je do své vlastní aplikace. Další informace najdete v článku [Získání dat z rozhraní API datového skladu pomocí klienta REST](reports-proc-data-rest.md).
