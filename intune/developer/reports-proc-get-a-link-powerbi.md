---
title: Připojení k datovému skladu pomocí Power BI
titleSuffix: Microsoft Intune
description: Můžete si stáhnout soubor pro použití s Microsoft Power BI, který umožňuje načíst interaktivní, dynamicky generované sestavy pro vašeho tenanta Microsoft Intune.
keywords: Datový sklad Intune
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/07/2019
ms.topic: reference
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 5E5A35D3-88F8-441B-8A0B-C5D7A1E5137B
ms.reviewer: aanavath
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic
ms.collection: M365-identity-device-management
ms.openlocfilehash: 9e8fadb625073af2a70d605d3ceabb9ba97906ae
ms.sourcegitcommit: 46322ca7a92971e18dc0b230f436b9ca892b90c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/07/2019
ms.locfileid: "72008334"
---
# <a name="connect-to-the-data-warehouse-with-power-bi"></a>Připojení k datovému skladu pomocí Power BI

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Aplikaci Power BI dodržování předpisů můžete použít k načtení interaktivních a dynamicky generovaných sestav pro vašeho tenanta Intune. Kromě toho můžete načíst data tenanta v Power BI pomocí odkazu OData. Intune poskytuje vašemu tenantovi nastavení připojení, abyste mohli zobrazit následující ukázkové sestavy a grafy týkající se:  

- Signalizac
- Registraci
- Zásady ochrany aplikací
- Zásady dodržování předpisů
- Profily konfigurace zařízení
- Aktualizace softwaru
- Protokoly inventáře zařízení

K dispozici jsou také trendy zvýrazněné pro registraci, dodržování předpisů, konfigurační profil zařízení a aktualizace softwaru. Ukázkové grafy a sestavy používají uživatelsky přívětivé filtry plátna. Pokud chcete použít rozšířené filtry, podívejte se na podokno **filtru** v Power BI Desktop.

Následující kroky ukazují, jak stáhnout soubor Power BI a jak používat odkaz OData s Power BI.

[!INCLUDE [reports-credential-reqs](../includes/reports-credential-reqs.md)]

## <a name="install-power-bi"></a>Nainstalovat Power BI

Nainstalujte nejnovější verzi [Power BI Desktop](https://aka.ms/intune/datawarehouseapi/installpowerbi). Další informace najdete v tématu [Power BI Desktop](https://powerbi.microsoft.com/desktop)

## <a name="load-the-data-and-reports-using-the-power-bi-intune-compliance-data-warehouse-app"></a>Načtěte data a sestavy pomocí Power BI aplikace datového skladu dodržování předpisů Intune.

Aplikace Power BI [Intune pro dodržování předpisů (datový sklad)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) obsahuje informace pro vašeho tenanta a sadu předem připravených sestav založených na datovém modelu datového skladu.

1. Přejděte na stránku **AppSource** aplikace pro [dodržování předpisů v Intune (datový sklad)](https://aka.ms/intune/datawarehouseapi/getpowerbiapp) , abyste zahájili proces instalace.
2. Klikněte na tlačítko **získat nyní** a potom klikněte na tlačítko **pokračovat**.
3. Po zobrazení výzvy k instalaci aplikace Power BI klikněte na **nainstalovat**.
4. Po dokončení instalace klikněte na dlaždici aplikace **Intune pro dodržování předpisů (datový sklad)** .
5. Klikněte na tlačítko **připojit** . Zobrazí se dialogové okno **připojit k Intune dodržování předpisů (datový sklad)** .
6. Klikněte na tlačítko **Přihlásit** se.
7. Přihlaste se pomocí uživatelského účtu, který má přístup k datovému skladu Intune pro tenanta se sestavami, které chcete zobrazit.
8. Pokud chcete zobrazit zahrnutý řídicí panel, klikněte na kartu **řídicí panely** a potom klikněte na řídicí panel **Přehled dodržování předpisů** .
9. Chcete-li zobrazit všechny dostupné sestavy, klikněte na kartu **sestavy** a potom klikněte na sestavu **dodržování předpisů v 1.0** . Procházejte stránkami sestavy kliknutím na karty v dolní části.
10. Chcete-li se později snadno vrátit k těmto sestavám, klikněte na hvězdičku vedle sestavy **dodržování předpisů v 1.0** . Tím se sestava přidá do oblíbených Power BI.

Alternativně můžete aplikaci nainstalovat z portálu Intune:

1. Přihlaste se k Azure Portal a vyberte **Monitorování a správa** > **Intune**. Můžete také vyhledat prostředky pro Intune.
2. Otevřete okno **nastavit datový sklad Intune** .
3. Vyberte **získat Power BI aplikaci** pro přístup k předem vytvořeným Power BIm sestavám pro vašeho tenanta v prohlížeči a jejich sdílení.
4. Postupujte podle kroků 2-10 výše.

## <a name="load-the-data-in-power-bi-using-the-odata-link"></a>Načtení dat v Power BI pomocí odkazu OData

S klientem ověřeným pro Azure AD se adresa URL OData připojí ke koncovému bodu RESTful v rozhraní API datového skladu, které zpřístupňuje datový model klientovi sestav. Podle těchto pokynů můžete pomocí Power BI Desktop připojit a vytvořit vlastní sestavy. Nejste omezeni na Power BI Desktop, ale můžete použít svůj oblíbený analytický nástroj s adresou URL OData, pokud klient podporuje ověřování OAUTH 2.0 a Standard OData v 4.0.

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. V části **Další úkoly** na pravé straně okna Přehled klikněte na **nastavit datový sklad Intune** . Zobrazí se okno **datový sklad Intune** .
3. V okně vytváření sestav načtěte adresu URL vlastního kanálu, například:<br>
    `https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=v1.0`
4. Otevřete **Power BI Desktop**.
5. Vyberte **soubor** > **načíst data**. Vyberte **kanál OData**.
6. Vyberte **základní**.
7. Do pole Adresa URL zadejte nebo vložte **adresu URL OData** .
8. Vyberte **OK**.
9. Pokud jste neověřili službu Azure AD pro vašeho tenanta z klienta služby Power BI Desktop, zadejte své přihlašovací údaje. Abyste získali přístup k datům, musíte se pomocí protokolu OAuth 2,0 ověřit pomocí služby Azure Active Directory (Azure AD).  
    1. Vyberte **účet organizace**.  
    2. Zadejte své uživatelské jméno a heslo.  
    3. Vyberte **Přihlásit se.**  
    4. Vyberte **připojit**.  
10. Vyberte **načíst**.

## <a name="next-steps"></a>Další kroky

Můžete najít odpovědi na otázky týkající se vašeho prostředí, jako je počet zařízení zapsaných během posledního týdne za den. Můžete získat přehled o naplnění tenanta a klientů Intune pomocí datových skladů Intune Power BI sestav načtených z okna v Azure. Intune ale poskytuje řadu dalších způsobů, jak data roztáhnout nebo znovu použít. Power BI a rozhraní API datového skladu Intune poskytují další funkce, například:

<!-- - You can use Power BI Desktop to create additional report types with your data. For example, you could create a custom chart representing the ratio of device manufactures in your enterprise. For more information about creating custom reports with Power BI and the Intune Data Warehouse, see `BLOG POST ON POWER BI`. -->
- Vaše data tenanta jsou uspořádaná tak, aby vám pomohla získat přehled o vašich datech. Další informace o tom, jak jsou data uspořádaná, najdete v tématu [datový model datového skladu](reports-ref-data-model.md).
- Můžete také přistupovat k datům z rozhraní RESTful a začlenit data do vlastní aplikace. Další informace najdete v tématu [získání dat z rozhraní API datového skladu pomocí klienta REST](../reports-proc-data-rest.md).
