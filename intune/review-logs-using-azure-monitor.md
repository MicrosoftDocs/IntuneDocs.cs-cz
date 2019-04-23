---
title: Protokoly auditu směrování ve službě Azure monitor pomocí Microsoft Intune – Azure | Dokumentace Microsoftu
description: Nastavení diagnostiky použijte k odesílání protokolů auditu a provozní protokoly v Microsoft Intune do účtu úložiště Azure, služby event hubs nebo log analytics. Zvolte, jak dlouho chcete uchovávat data, vidíme, že některé odhadované náklady na jinou velikost tenantů.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 03/18/2019
ms.topic: troubleshooting
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: fb33a1207e165323de2e82467c7a0dd5239d9713
ms.sourcegitcommit: 143dade9125e7b5173ca2a3a902bcd6f4b14067f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "61507332"
---
# <a name="send-log-data-to-storage-event-hubs-or-log-analytics-in-intune-preview"></a>Odeslat data protokolů do služby storage, služby event hubs, nebo se přihlaste analytics Intune (preview)

Microsoft Intune obsahuje integrované protokoly, které poskytují informace o vašem prostředí. **Protokoly auditu** zobrazit podrobnosti pro jednotlivé události nebo úlohy, ke kterým dochází v Intune. **Operační protokoly (preview)** to úspěšně zobrazit podrobností o uživateli a zařízeními (nebo neúspěšných) k registraci, a také podrobnosti o zařízení nedodržující předpisy.

Tyto protokoly můžete odeslat také se službami Azure Monitor, včetně účtů úložiště, služba event hubs a log analytics. Konkrétně můžete:

* Archivujte protokoly Intune do účtu služby Azure storage pro uchovávání dat nebo archivaci nastavte dobu.
* Stream Intune protokolů do služby Azure event hub Analytics pomocí oblíbených nástrojů informace o zabezpečení a správu událostí (SIEM), jako je například Splunk a QRadar.
* Protokoly Intune integrate svoje vlastní řešení vlastního protokolu pomocí streamování do centra událostí.
* Odeslání protokolů Intune umožňují přehledné vizualizace, monitorování a upozorňování na připojených dat Log Analytics.

Tyto funkce jsou součástí **nastavení diagnostiky** v Intune.

V tomto článku se dozvíte, jak používat **nastavení diagnostiky** k odesílání dat protokolu do různých služeb, poskytuje příklady a odhady nákladů a odpovědi na některé běžné dotazy.

## <a name="prerequisites"></a>Požadavky

Pokud chcete používat tuto funkci, potřebujete:

* Předplatné Azure: Pokud nemáte předplatné Azure, můžete si [zaregistrujte si bezplatnou zkušební verzi](https://azure.microsoft.com/free/).
* Prostředí Microsoft Intune (tenant) v Azure
* Uživatel kdo má **globálního správce** nebo **Správce služby Intune** tenanta Intune.

V závislosti na tom, kde chcete směrovat data protokolu auditování budete potřebovat následující služby:

* [Účtu služby Azure storage](https://docs.microsoft.com/azure/storage/common/storage-account-overview) s *klíče Listkey* oprávnění. Doporučujeme vám, že používáte obecný účet úložiště a ne účet blob storage. Informace o cenách služby storage, najdete v článku [cenové kalkulačky pro Azure Storage](https://azure.microsoft.com/pricing/calculator/?service=storage). 
* [Oboru názvů Azure event hubs](https://docs.microsoft.com/azure/event-hubs/event-hubs-create#create-an-event-hubs-namespace) k integraci s řešeními třetích stran.
* [Pracovní prostor Azure log analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) odesílat protokoly do Log Analytics.

## <a name="send-logs-to-azure-monitor"></a>Odeslání protokolů s Azure monitor

1. V [webu Azure portal](https://portal.azure.com/)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. V části **monitorování**vyberte **nastavení diagnostiky**. Při prvním otevření, zapněte ho:

    ![Zapnout nastavení diagnostiky v Intune odeslat protokoly Azure monitoru](media/diagnostics-settings-turn-on.png)

3. Zadejte tyto vlastnosti:

    - **Název**: Zadejte název pro nastavení diagnostiky. Toto nastavení zahrnuje všechny vlastnosti, které zadáte. Zadejte například `Route audit logs to storage account`.
    - **Archivovat do účtu úložiště**: Data protokolu se uloží do účtu služby Azure storage. Tuto možnost použijte, pokud chcete uložit nebo archivovat data.

        1. Tuto možnost vyberte > **konfigurovat**. 
        2. V seznamu vyberte existující účet úložiště > **OK**.

    - **Stream do centra událostí**: Streamování protokolů do služby Azure event hub. Pokud chcete na datech log analytics SIEM pomocí nástrojů, jako je Splunk a QRadar, zvolte tuto možnost.

        1. Tuto možnost vyberte > **konfigurovat**. 
        2. Zvolte existující obor názvů centra událostí a zásad ze seznamu > **OK**.

    - **Odeslání do Log Analytics**: Odešle data do služby Azure log analytics. Pokud chcete použít vizualizace, monitorování a upozorňování pro svoje protokoly, vyberte tuto možnost.

        1. Tuto možnost vyberte > **konfigurovat**. 
        2. Vytvořte nový pracovní prostor a zadejte podrobnosti o pracovním prostoru. Nebo zvolte existující pracovní prostor v seznamu > **OK**.

            [Pracovní prostor Azure log analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace) obsahuje další podrobnosti o těchto nastaveních.

    - **PROTOKOL** > **mají**: Vyberte tuto možnost k odeslání [protokoly auditu Intune](monitor-audit-logs.md) do účtu úložiště, Centrum událostí nebo log analytics. Protokoly auditu zobrazit historii každé úlohy, který generuje změny v Intune, včetně toho, kdo jste a kdy.

      Pokud budete chtít používat účet úložiště, pak také zadejte jak dlouho chcete uchovávat data (uchovávání). Chcete-li zachovat data navždy, nastavte **uchování (dny)** k `0` (nula).

    - **PROTOKOL** > **OperationalLogs**: Operační protokoly (preview) zobrazit úspěch nebo neúspěch uživatelů a zařízení zaregistrovaná v Intune, jakož i podrobnosti o zařízení nedodržující předpisy. Výběrem této možnosti Odeslat protokoly registrace do vašeho účtu úložiště, se v Centru událostí nebo protokolování analytics.

      Pokud budete chtít používat účet úložiště, pak také zadejte jak dlouho chcete uchovávat data (uchovávání). Chcete-li zachovat data navždy, nastavte **uchování (dny)** k `0` (nula).

      > [!NOTE]
      > Operační protokoly jsou ve verzi preview. Pokud chcete poskytnout zpětnou vazbu, včetně informací o zahrnutých v provozních protokolech, přejděte na [UserVoice](https://microsoftintune.uservoice.com/forums/291681-ideas/suggestions/36613948-diagnostics-settings-feedback) (otevře se nový web).

    Až budete hotovi, vaše nastavení vypadat podobně jako následující nastavení: 

    ![Ukázkový obrázek, který odešle protokoly auditu Intune do účtu služby Azure storage](media/diagnostics-settings-example.png)

4. **Uložte** provedené změny. Vaše nastavení se zobrazí v seznamu. Jakmile se vytvoří, můžete změnit nastavení tak, že vyberete **upravit nastavení** > **Uložit**.

## <a name="use-audit-logs-throughout-intune"></a>Pomocí protokolů auditu v Intune

Můžete také exportovat protokoly auditu v ostatních částech Intune, včetně registrace, dodržování předpisů, konfigurace, zařízení, klientské aplikace a další.

Například pro export auditu protokoly při použití dodržování předpisů pro zařízení:

1. V [webu Azure portal](https://portal.azure.com/)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **dodržování předpisů zařízením** > **monitorování** > **protokoly auditu**:

    ![Zvolte protokoly auditu pro směrování Intune dat do úložiště Azure Monitor, události rozbočovače nebo analytics](media/audit-logs-under-monitor-in-compliance.png)

3. Vyberte **exportovat nastavení dat**. Pokud není povolená, můžete zapnout **nastavení diagnostiky**. Kam má odesílat protokoly, můžete také zvolit, jak je popsáno v [odeslat protokoly Azure monitoru](#send-logs-to-azure-monitor) (v tomto článku).

## <a name="cost-considerations"></a>Důležité informace o nákladech

Pokud již máte licence na Microsoft Intune, potřebujete předplatné Azure k nastavení účtu a událostí centra úložiště. Je obvykle bezplatné předplatné Azure. Ale platíte za použití prostředků Azure, včetně účet úložiště pro archivaci a centra událostí pro streamování. Množství dat a náklady se liší v závislosti na velikosti tenanta.

### <a name="storage-size-for-activity-logs"></a>Velikost úložiště pro protokoly aktivit

Každé události protokolu auditu používá přibližně 2 KB datového úložiště. Pro tenanta se 100 000 uživatelů můžete mít asi 1,5 milionu událostí za den. Možná bude nutné přibližně 3 GB úložiště dat za den. Protože zápisy v listech pětiminutovém nejčastěji dochází, můžete očekávat, že přibližně 9 000 operace zápisu za měsíc.

Následující tabulky popisují odhad nákladů v závislosti na velikosti tenanta. Zahrnuje také účet úložiště pro obecné účely verze 2 v oblasti západní USA pro uchovávání dat nejméně jeden rok. Pokud chcete získat odhad pro datový svazek, který budete pro svoje protokoly, použijte [cenové kalkulačky pro Azure storage](https://azure.microsoft.com/pricing/details/storage/blobs/).

**Protokol auditu s 100 000 uživatelů**

| | |
|---|---|
|Událostí za den| 1,5 milionu|
|Odhadovanému objemu dat za měsíc| 90 GB|
|Odhadované náklady za měsíc (USD)| $1.93|
|Odhadované náklady za rok (USD)| $23.12|

**Protokol auditu s 1 000 uživatelů**

| | |
|---|---|
|Událostí za den| 15,000|
|Odhadovanému objemu dat za měsíc| 900 MB|
|Odhadované náklady za měsíc (USD)| $0.02|
|Odhadované náklady za rok (USD)| $0.24|

### <a name="event-hub-messages-for-activity-logs"></a>Zprávy centra událostí pro protokoly aktivit

Události jsou obvykle dávce v pěti minutách a odesílají jako jedna zpráva se všechny události v tomto časovém rámci. Zprávy v Centru událostí má maximální velikost 256 KB. Pokud celková velikost všech zpráv v rámci časový rámec překročit tento svazek, jsou odeslány více zpráv.

Například asi 18 událostí za sekundu nejčastěji dochází u velkých tenanta z více než 100 000 uživatelů. To odpovídá 5 400 události každých pět minut (300 sekund x 18 události). Protokoly auditu se přibližně 2 KB na událost. To odpovídá 10,8 MB na data. Tedy 43 zprávy se posílají do centra událostí v tomto intervalu pět minut.

Následující tabulka obsahuje odhadované náklady za měsíc pro Centrum událostí úrovně basic v oblasti západní USA, v závislosti na objemu dat událostí. Pokud chcete získat odhad objem dat, který budete pro svoje protokoly, použijte [Event Hubs pomocí cenové kalkulačky](https://azure.microsoft.com/pricing/details/event-hubs/).

**Protokol auditu s 100 000 uživatelů**

| | |
|---|---|
|Událostí za sekundu| 18|
|Událostí za pět minut| 5,400|
|Svazek na interval| 10.8 MB|
|Zpráv za interval| 43|
|Zpráv za měsíc| 371,520|
|Odhadované náklady za měsíc (USD)| $10.83|

**Protokol auditu s 1 000 uživatelů**

| | |
|---|---|
|Událostí za sekundu|0.1 |
|Událostí za pět minut| 52|
|Svazek na interval|104 KB |
|Zpráv za interval|1 |
|Zpráv za měsíc|8,640 |
|Odhadované náklady za měsíc (USD)|$10.80 |

### <a name="log-analytics-cost-considerations"></a>Log Analytics úspory nákladů

Náklady související se správou pracovní prostor Log Analytics najdete v tématu [spravovat náklady pomocí řízení objemu dat a uchovávání dat v Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-manage-cost-storage).

## <a name="frequently-asked-questions"></a>Nejčastější dotazy

Získejte odpovědi na nejčastější dotazy a přečtěte si informace o známých problémech s protokoly Intune ve službě Azure Monitor.

#### <a name="which-logs-are-included"></a>Protokoly, které jsou zahrnuty?

Protokoly auditu a protokolů provozní (preview) jsou k dispozici pro použití této funkce směrování.

#### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-event-hub"></a>Po akci, když odpovídající protokoly objeví události centra?

Protokoly obvykle se zobrazí v Centru událostí během několika minut po provedení akce. [Co je Azure Event Hubs? ](https://docs.microsoft.com/azure/event-hubs/) poskytuje další informace.

#### <a name="after-an-action-when-do-the-corresponding-logs-show-up-in-the-storage-account"></a>Po akci, když odpovídající protokoly objeví v účtu úložiště?

Pro účty Azure storage latence je kdekoli z 5 na 15 minut po spuštění akce.

#### <a name="what-happens-if-an-administrator-changes-the-retention-period-of-a-diagnostic-setting"></a>Co se stane, pokud správce změní doba uchování nastavení diagnostiky?

Nové zásady uchovávání informací platí pro protokoly se shromažďují po provedení změny. Shromážděné protokoly předtím, než se změna zásad nejsou ovlivněny.

#### <a name="how-much-does-it-cost-to-store-my-data"></a>Kolik stojí uložit Moje data?

Náklady na úložiště závisí na velikosti protokolů a dobu uchování, kterou zvolíte. Seznam odhadované náklady pro tenanty, které závisí na svazek s protokolem vygenerována, najdete v článku [velikost úložiště pro protokoly aktivit](#storage-size-for-activity-logs) (v tomto článku).

#### <a name="how-much-does-it-cost-to-stream-my-data-to-an-event-hub"></a>Kolik stojí Streamovat data do centra událostí?

Náklady na streamování závisí na počtu zpráv, který jste dostali za minutu. Podrobnosti o jak výpočet a náklady na základě počtu zpráv odhady nákladů, naleznete v tématu [zprávy centra událostí protokoly aktivity](#event-hub-messages-for-activity-logs) (v tomto článku).

#### <a name="how-do-i-integrate-intune-audit-logs-with-my-siem-system"></a>Jak můžu integrovat protokoly auditu Intune se systémem SIEM?

Pomocí Azure monitoru službou Event Hubs do datového proudu protokolů do vašeho systému SIEM. Nejprve je potřeba [streamování protokolů do služby event hub](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub). Potom [nastavení nástroje SIEM](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub#access-data-from-your-event-hub) s centrem událostí nakonfigurované. 

#### <a name="what-siem-tools-are-currently-supported"></a>Jaké nástroje SIEM se aktuálně podporují?

V současné době podporuje monitorování Azure [Splunk](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-integrate-activity-logs-with-splunk), QRadar, a [Sumo logiky](https://help.sumologic.com/Send-Data/Applications-and-Other-Data-Sources/Azure_Active_Directory) (otevře se nový web). Další informace o tom, jak fungují konektory najdete v tématu [pomocí externího nástroje pro monitorování data do centra událostí pro používání Azure Stream](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs).

#### <a name="can-i-access-the-data-from-an-event-hub-without-using-an-external-siem-tool"></a>Mám přístup k datům z centra událostí bez použití externího nástroje SIEM?

Ano. Pro přístup k protokolům z vaší vlastní aplikace, můžete použít [Event Hubs API](https://docs.microsoft.com/azure/event-hubs/event-hubs-dotnet-standard-getstarted-receive-eph).

#### <a name="what-data-is-stored"></a>Jaká data se ukládají?

V Intune nejsou uložené žádné data odesílaná prostřednictvím kanálu. Intune směruje data do kanálu Azure Monitor, na oprávnění tenanta. Další informace najdete v tématu [Přehled monitorování Azure](https://docs.microsoft.com/azure/azure-monitor/overview).

## <a name="next-steps"></a>Další postup

* [Protokoly aktivit archivovat do účtu úložiště](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-azure-monitor-route-logs-to-storage-account)
* [Směrování protokolů aktivit do centra událostí](https://docs.microsoft.com/azure/active-directory/reports-monitoring/tutorial-azure-monitor-stream-logs-to-event-hub)
* [Integrovat protokoly aktivit s využitím Log Analytics](https://docs.microsoft.com/azure/active-directory/reports-monitoring/howto-integrate-activity-logs-with-log-analytics)
