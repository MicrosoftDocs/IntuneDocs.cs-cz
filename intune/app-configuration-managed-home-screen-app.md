---
title: Konfigurace Microsoft spravovaná aplikace z domovské obrazovky
titleSuffix: Microsoft Intune
description: Zjistěte, jak nakonfigurovat aplikaci Microsoft Managed domovskou obrazovku.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 05/16/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 865c7f03-f525-4dfa-b3a8-d088a9106502
ms.reviewer: chmaguir
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: a9a61b89f07bfacf1dc41be1412f79509e1e147d
ms.sourcegitcommit: 916fed64f3d173498a2905c7ed8d2d6416e34061
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2019
ms.locfileid: "66049941"
---
# <a name="configure-the-microsoft-managed-home-screen-app-for-android-enterprise"></a>Konfigurace Microsoft spravovaná aplikace z domovské obrazovky pro Android Enterprise

Spravované domácí obrazovky je aplikace pro Android Enterprise vyhrazená zařízení vlastněných společností zaregistrovaná přes Intune a spuštění v režimu veřejného terminálu s více aplikacemi. Pro tato zařízení spravované domácí obrazovky funguje jako spouštěč pro jiné schválených aplikací pro spuštění dojde k jeho zvýraznění. Na spravované domovskou obrazovku poskytuje správcům IT schopnost přizpůsobit jejich zařízení a omezit možnosti, ke kterým přístup koncového uživatele. 

## <a name="when-to-configure-the-microsoft-managed-home-screen-app"></a>Když nakonfigurujte aplikaci Microsoft Managed domovskou obrazovku

Obvykle pokud jsou k dispozici prostřednictvím konfigurace zařízení nastavení, konfigurace nastavení existuje. To může ušetřit čas, minimalizovat chyby a poskytne vám lepší podporu Intune. Nicméně některé z nastavení spravovaných domovskou obrazovku jsou aktuálně dostupné jenom prostřednictvím **zásady Konfigurace aplikací** okna v konzole Intune. Pomocí tohoto dokumentu se naučíte konfigurovat řadu nastavení pomocí návrháře konfigurace nebo skript JSON. 

> [!NOTE]
> Je aktuálně možné a doporučuje pro nastavení Povolit uvedené aplikace a připnuté webových odkazů pomocí **klientské aplikace** a **konfigurace zařízení**. Úplný seznam nastavení, které jsou k dispozici v **konfigurace zařízení** , který dopad spravované domovskou obrazovku, naleznete v tématu [vyhrazené nastavení zařízení](device-restrictions-android-for-work.md#dedicated-device-settings).  

Nejprve přejděte do konzoly Intune na webu Azure portal a přejděte na **klientské aplikace** > **zásady Konfigurace aplikací**. Přidat zásady konfigurace pro **spravovaných zařízeních** systémem **Android** a zvolte **spravované domovskou obrazovku** jako přidružené aplikace. Klikněte na **nastavení konfigurace** chcete nakonfigurovat jiná nastavení k dispozici spravované domovskou obrazovku. 

## <a name="choosing-a-configuration-settings-format"></a>Výběr formát nastavení konfigurace

Existují dvě metody, které můžete použít k definování nastavení konfigurace pro spravované domovskou obrazovku:

- **Návrháře konfigurace** umožňuje konfigurovat nastavení se snadným ovládáním uživatelského rozhraní, ve kterém můžete zapnout nebo vypnout funkce a nastavte hodnoty. V této metodě se několik zakázané konfigurační klíče s hodnotovým typem `BundleArray`. Tyto konfigurační klíče se dá nakonfigurovat jenom zadáním dat JSON. 
- **JSON data** můžete zadat všechny možné konfigurace klíče pomocí skriptu JSON. 

Pokud chcete přidat vlastnosti pomocí návrháře konfigurace, můžete tyto vlastnosti automaticky převést na JSON výběr **data JSON zadejte** z **formát nastavení konfigurace** rozevíracího seznamu.

![Snímek obrazovky konfigurace možností formátu](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_01.png)

## <a name="using-configuration-designer"></a>Pomocí návrháře konfigurace

Návrháře konfigurace můžete vybrat nastavení předem vyplněná a jejich přidružené hodnoty. 

![Snímek obrazovky přidání nastavení](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_02.png)

V následující tabulce jsou uvedeny spravované domovskou obrazovku k dispozici konfigurační klíče, typy hodnot, výchozí hodnoty a popisy. Popis obsahuje očekávané zařízení chování na základě vybraných hodnot. Konfigurační klíče, které jsou zakázány v Návrháři konfigurace nejsou uvedené v tabulce.

| Konfigurační klíč | Typ hodnoty | Výchozí hodnota | Popis |
|---------------------------------------------------------------------------------------------------------------------------|-------------|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Nastavte velikost mřížky | řetězec | Automaticky | Umožňuje nastavit velikost mřížky pro aplikace se umístí na spravované domovské obrazovce. Můžete nastavit počet aplikace řádky a sloupce, které chcete definovat velikost mřížky v následujícím formátu `columns;rows`. Pokud definujete velikost mřížky, maximální počet aplikací, které budou zobrazeny po sobě na domovské obrazovce by být počet řádků, které nastavíte, a maximální počet aplikací, které se zobrazí ve sloupci na domovské obrazovce by počet sloupců, které jste nastavili. |
| Povolit hlavičky obrazovky | BOOL | TRUE | Umožňuje horním navigačním panelu pro různá zobrazení, které nabízí spravované domovské obrazovky jako jsou karty informačního kanálu nebo informačního kanálu. Pokud toto nastavení povolíte, uživatelům zařízení se zobrazí hlavičku. |
| Povolit zařízení stavového řádku | BOOL | TRUE | Umožňuje stavovém řádku v domovské obrazovky (hlavní panel, který zobrazuje aktuální počet připojení jako Wi-Fi a atd.). Pokud povolíte tuto konfiguraci klíče, koncový uživatel bude moci zobrazit ikony zobrazené na stavové řádky, které představují připojení a aktivní aplikace. |
| Povolit oznámení "BADGE" oznámení | BOOL | FALSE | Povolí oznámení Odznáček ikony aplikace, který zobrazuje počet nových oznámení v aplikaci. Pokud povolíte toto nastavení, koncovým uživatelům se zobrazí oznámení, oznámení v aplikacích používajících nepřečtená oznámení. Pokud tuto konfiguraci klíče zakázáno, koncový uživatel neuvidí žádné oznámení do aplikací, které může být označené jako nepřečtená oznámení. |
| Domovská stránka zámek obrazovky | BOOL | TRUE | Odebere schopnost koncový uživatel pohyb ikony aplikace na domovské obrazovce. Pokud povolíte tuto konfiguraci klíče, uzamknou ikony aplikace na domovské obrazovce a koncový uživatel nebude moci přetažení do různých mřížky polohy na domovskou obrazovku. Pokud `false`, koncoví uživatelé budou moci pohyb ikony aplikace a webový odkaz na na spravované domovskou obrazovku.  |
| Nastavit tapetu zařízení | řetězec | Výchozí | Umožňuje nastavit tapetu podle vašeho výběru tak, že zadáte adresu URL obrázku, který chcete nastavit jako tapetu. |
| Nastavte velikost ikony aplikace | integer | 2 | Umožňuje nastavit velikost ikony pro aplikace na domovské obrazovce. Můžete použít následující hodnoty v této konfiguraci pro různé velikosti - 0 (nejmenší), 1 (malé), 2 (Regular), 3 (velké) a 4 (největší). |
| Nastavit ikonu složky aplikace | integer | 0 | Umožňuje definovat vzhled složky aplikace na domovské obrazovce. Vzhled můžete vybrat z následujících hodnot: Dark Square(0);   Dark Circle(1); Light Square(2); Light Circle(3). |
| Povolit gesta | BOOL | FALSE | Povolte koncový uživatel možnost přiřadit různé gesta jako je například potáhnutí prstem nahoru a potažením dolů akce. Pokud tento klíč konfigurace zakážete, koncoví uživatelé pouze bude mít potáhnutí prstem doprava, pokud je druhé stránce a zpět na domovskou stránku. |
| Povolit svislé posouvání | BOOL | FALSE | Umožňuje svislé posouvání na spravované domovské obrazovce. Pokud povolíte tuto konfiguraci klíče, koncový uživatel pouze bude moci přejít na různých stránkách svisle spíše než potáhnutím vodorovně. |
| Motiv nastavení domovské obrazovky | řetězec | Theme.Light.Blue | Můžete vybírat předdefinovanou sadu motivů, které mají různé barvy motivu pro domovskou obrazovku. Můžete použít následující motivy tak, že zadáte hodnotu řetězce v následujícím formátu.   Theme.Light.Green. Kde světla se dá nahradit výrazem tmavý motiv tmavý a zelená lze nahradit modrou, žlutá, růžová, Red, Orange a nachová. |
| Povolit ukotvení | BOOL | FALSE | Povolí ukotvení části aplikace v dolní části domovské obrazovky s trvalou zobrazené aplikace a vstupní bod pro všechny nainstalované aplikace. Pokud povolíte toto konfigurační klíč, bude koncový uživatel moct získat přístup k aplikacím v docku a také přístup k oddílu všechny aplikace přejděte na seznam všech nainstalovaných aplikací na zařízeních, zda byly uvedeny povolit. |
| Nastavit orientaci obrazovky | integer | 1 | Umožňuje nastavit orientaci ovládacího prvku na domovskou obrazovku režimu na výšku, šířku nebo povolit automatické otočit. Orientace můžete nastavit tak, že zadáte hodnoty 1 (pro režimu na výšku), 2 (pro režimu jehličkové tiskárny), 3 (pro Autorotate). |
| Povolení kanálu domovské obrazovky | BOOL | FALSE | Umožňuje kanál domovské obrazovce, která můžou vidět potažením doleva na domovskou obrazovku. Tento kanál se zobrazí jiný typ obsahu, jako jsou novinky, kalendář, často uživatelským aplikacím a Cortana hlasového Pomocníka s nastavením karty atd. Pokud je povolit, bude koncový uživatel moci přejít na informační kanál potáhnutím prstem doleva na domovské obrazovce. |
| Povolit režim – přehled | BOOL | FALSE | Umožňuje koncovým uživatelům přidávat nebo odebírat různé stránky na domovské obrazovce, který je přístupný potáhnutím pravé na výchozí obrazovce. Pokud povolíte tím, koncový uživatel budete moct přidat stránkovaného napravo od výchozí stránku na domovskou obrazovku, bude také možné změnit výchozí stránku a také budou mít přístup k nastavení na domovské obrazovce spravované. |
| Povolit telemetrii zařízení | BOOL | FALSE | Umožňuje veškerá telemetrická data zachytávaná pro spravované domovskou obrazovku. Pokud povolíte toto, Microsoft bude možné ji zachytit zařízení telemetrických dat, jako je počet průchodů konkrétní aplikace se spustí na tomto zařízení. |
| Nastavení seznamu povolených aplikací | bundleArray | FALSE | Umožňuje definovat sadu aplikací, které jsou viditelné na domovské obrazovce z mezi aplikacemi na zařízení nainstalovaná. Aplikace můžete definovat tak, že zadáte název balíčku aplikace z aplikace, které chcete zviditelnit, například com.android.settings s žádným nastavení přístupné na domovské obrazovce. Aplikace už musí být nainstalován tento jste seznamu povolených v této části na zařízení-li být viditelný na domovské obrazovce. |
| Sada připnuté webové odkazy | bundleArray | FALSE | Můžete připnout weby jako ikony rychlé spuštění na domovské obrazovce. Pomocí této konfigurace můžete definovat adresu URL a přidat na domovskou obrazovku pro koncového uživatele spustit v prohlížeči s jediným klepnutím. |
| Povolit panel hledání | BOOL | FALSE | Umožňuje panelu hledání na domovské obrazovce. Pokud povolíte tím, uživatelům zařízení se zobrazí na panelu hledání na domovské obrazovce, ve kterém bude možné je zadat cokoli, co chtějí hledat na webu. |
| Zakázat aplikaci nastavení | BOOL | FALSE | Na stránce nastavení zakáže spravované domácí obrazovky. Pokud zakážete toto, koncový uživatel zařízení nebude možné získat nastavení na spravovaných domovskou obrazovku. |
| Povolit spořiče obrazovky | BOOL | FALSE | Pokud chcete povolit režim spořič obrazovky, nebo ne. Pokud nastavena na hodnotu true, můžete nakonfigurovat **screen_saver_image**, **screen_saver_show_time**, **inactive_time_to_show_screen_saver**, a **media_detect_ screen_saver**. |
| Spořič obrazovky | řetězec |   | Nastavte adresu URL obrázku spořič obrazovky. Pokud je nastavena žádná adresa URL, zařízení se zobrazí na výchozí obrazovce, když se aktivuje šetřič.  |
| Zobrazit čas spořič obrazovky | integer | 0 | Poskytuje možnost nastavit dobu v sekundách zařízení zobrazí spořič obrazovky během režimu spořič obrazovky. Pokud nastavena na hodnotu 0, spořič obrazovky se zobrazí v režimu spořiče obrazovky po neomezenou dobu, dokud se zařízení stane aktivním.  |
| Neaktivní doba umožňující spořič obrazovky | integer | 30 | Počet sekund, po které zařízení neaktivní před aktivací spořič obrazovky. Pokud je nastaveno na 0, zařízení nikdy přejde do režimu spořič obrazovky. |
| Média detekovat před zobrazením spořič obrazovky | BOOL | TRUE | Zvolte, jestli obrazovku zařízení by měl obsahovat spořič obrazovky Pokud je na zařízení přehrávání audio/video. Je-li nastavena hodnota true, zařízení nebude možné přehrát zvuk/video, bez ohledu na hodnotu v **inactive_time_to_show_scree_saver**. Pokud nastavena na hodnotu false, zobrazí obrazovku zařízení spořič obrazovky podle hodnotu nastavenou v **inactive_time_to_show_screen_saver**.   |
| Povolit virtuální tlačítko Domů | BOOL | FALSE | Zapnout toto nastavení `True` koncový uživatel přístup k domovské tlačítko na spravované domovské obrazovky, který vrátí uživatelem na domovskou obrazovku spravované z aktuální úlohy jsou v.  |
| Typ virtuální tlačítko Domů | řetězec | swipe_up | Použití **swipe_up** pro přístup k domovské tlačítko s potáhnutí prstem nahoru gest. Použití **float** pro přístup k rychlé, trvalé tlačítko Domů, které koncový uživatel může přesouvat na obrazovce. |
| Baterie a signálem řádku indikátoru | BOOL | Pravda  | Povolením tohoto nastavení `True` zobrazí panel indikátor sílu baterie a signálu. |
| Heslo režimu uzamčení úloh ukončení | řetězec |   | Zadejte 4-6místným číselným kódem pomocí dočasně vyřadit z režimu uzamčení úloh odstraňování potíží. |
| Zobrazit nastavení Wi-Fi | BOOL | FALSE | Povolením tohoto nastavení `True` umožňuje koncový uživatel můžete zapnout nebo vypnout Wi-Fi nebo se připojit k různým sítím Wi-Fi.  |
| Zobrazit nastavení Bluetooth | BOOL | FALSE | Povolením tohoto nastavení `True` umožňuje koncovému uživateli zapnout nebo vypnout Bluetooth a připojovat k jiné podporující Bluetooth zařízení.   |

## <a name="enter-json-data"></a>Zadat JSON Data

Zadat data JSON nakonfigurovat všechna nastavení k dispozici pro spravované domovskou obrazovku, stejně jako zakázané v nastavení **Configuration Designer**.

![Snímek obrazovky Přidání data JSON](./media/app-configuration-managed-home-screen-app/app-configuration-managed-home-screen-app_03.png)

Kromě konfigurovatelné nastavení uvedená v seznamu **Configuration Designer** tabulky (viz výše), následující tabulka obsahuje konfigurační klíče, které můžete nakonfigurovat jenom přes JSON data.

|    Konfigurační klíč    |    Typ hodnoty    |    Výchozí hodnota    |    Popis    |
|-------------------------------------------------|--------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Nastavení Povolit uvedených v seznamu aplikací    |    bundleArray    | <img alt="JSON - Example 1" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson01.png" width="300"> |    Umožňuje definovat sadu aplikací, které jsou viditelné na domovské obrazovce z mezi aplikacemi na zařízení nainstalovaná. Aplikace můžete definovat tak, že zadáte název balíčku aplikace z aplikace, které chcete zviditelnit, například com.android.settings s žádným nastavení přístupné na domovské obrazovce. Aplikace už musí být nainstalován tento jste seznamu povolených v této části na zařízení-li být viditelný na domovské obrazovce.    |
|    Sada připnuté webové odkazy    |    bundleArray    | <img alt="JSON - Example 2" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson02.png" width="300"> |    Můžete připnout weby jako ikony rychlé spuštění na domovské obrazovce. Pomocí této konfigurace můžete definovat adresu URL a přidat na domovskou obrazovku pro koncového uživatele spustit v prohlížeči s jediným klepnutím.    |
|    Vytvoření spravované složky pro seskupení aplikací    |    bundleArray    | <img alt="JSON - Example 3" src="./media/app-configuration-managed-home-screen-app/defaultvaluejson03.png" width="300"> |    Umožňuje vytvořit a název složky a skupiny aplikací v mezích těchto složek. Koncoví uživatelé nebudou mít přesunutí složky, složky přejmenovat nebo přesunout aplikace v rámci složky.   Složky se zobrazí v pořadí vytvořeny a aplikace v rámci složky se zobrazí podle abecedy.         Poznámka: všechny aplikace, které chcete seskupit do složek musí přiřadit jako požadovaný k zařízení a musí být přidán do na spravované domovskou obrazovku.     |

Následuje příklad skript JSON se všemi klíči dostupné konfigurace zahrnuté:

```json
{
    "kind": "androidenterprise#managedConfiguration",
    "productId": "com.microsoft.launcher.enterprise",
    "managedProperty": [
        {
            "key": "grid_size",
            "valueString": "Auto"
        },
        {
            "key": "keep_page_header",
            "valueBool": true
        },
        {
            "key": "keep_status_bar",
            "valueBool": true
        },
        {
            "key": "show_notification_badge",
            "valueBool": false
        },
        {
            "key": "lock_home_screen",
            "valueBool": true
        },
        {
            "key": "wallpaper",
            "valueString": "default"
        },
        {
            "key": "icon_size",
            "valueInteger": 2
        },
        {
            "key": "app_folder_icon",
            "valueInteger": 0
        },
        {
            "key": "gesture_on",
            "valueBool": false
        },
        {
            "key": "vertical_scrolling",
            "valueBool": false
        },
        {
            "key": "theme",
            "valueString": "Theme.Light.Blue"
        },
        {
            "key": "dock_enable",
            "valueBool": false
        },
        {
            "key": "screen_orientation",
            "valueInteger": 1
        },
        {
            "key": "feed_enable",
            "valueBool": false
        },
        {
            "key": "allow_overview_mode",
            "valueBool": false
        },
        {
            "key": "enable_telemetry",
            "valueBool": false
        },
        {
            "key": "applications",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "package",
                            "valueString": “app package name here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "weblinks",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "link",
                            "valueString": “link here”
                        },
                        {
                            "key": "label",
                            "valueString": “weblink label here”
                        }
                    ]
                }
            ]
        },
        {
            "key": "search_bar",
            "valueBool": false
        },
        {
            "key": "hide_settings",
            "valueBool": false
        },
        {
            "key": "show_virtual_home",
            "valueBool": false
        },
        {
            "key": "virtual_home_type",
            "valueString": "swipe_up"
        },
        {
            "key": "show_virtual_status_bar",
            "valueBool": true
        },
        {
            "key": "exit_lock_task_mode_code",
            "valueString": ""
        },
        {
            "key": "show_wifi_setting",
            "valueBool": false
        },
        {
            "key": "show_bluetooth_setting",
            "valueBool": false
        },
        {
            "key": "managed_folders",
            "valueBundleArray": [
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Folder name here"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.emmx"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.bing"
                                        }
                                    ]
                                },
                                {
                                    "managedProperty": [
                                        {
                                            "key": "link",
                                            "valueString": "https://microsoft.com/"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                },
                {
                    "managedProperty": [
                        {
                            "key": "folder_name",
                            "valueString": "Example folder name 2"
                        },
                        {
                            "key": "applications",
                            "valueBundleArray": [
                                {
                                    "managedProperty": [
                                        {
                                            "key": "package",
                                            "valueString": "com.microsoft.office.word"
                                        }
                                    ]
                                }
                            ]
                        }
                    ]
                }
            ]
        }
    ]
}

```
## <a name="next-steps"></a>Další postup

- Další informace o zařízení s Androidem Enterprise dedicated, naleznete v tématu [nastavení Intune registrace podnikových zařízení s Androidem vyhrazené](android-kiosk-enroll.md).
