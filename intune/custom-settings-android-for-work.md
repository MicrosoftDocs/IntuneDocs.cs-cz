---
title: "Nastavení vlastního profilu Intune pro Android for Work"
titlesuffix: Azure portal
description: "Zjistěte, jak vytvořit nastavení vlastního profilu Intune pro zařízení s Androidem for Work."
keywords: 
author: lleonard-msft
ms.author: alleonar
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fbda95924e34a71f214de4f37be61457c1eb5ef7
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/15/2017
---
# <a name="create-intune-custom-profile-settings-for-android-for-work-devices"></a>Vytvoření nastavení vlastního profilu Intune pro Android for Work

Pomocí zásad vlastní konfigurace pro Android for Work v Intune přiřaďte nastavení OMA-URI, která se dají používat k ovládání funkcí na zařízeních s Androidem for Work. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Tato vlastnost umožňuje přiřadit nastavení Androidu, která nejdou konfigurovat pomocí zásad Intune. Intune v současnosti podporuje omezený počet vlastních zásad Androidu. Pokud chcete zjistit, které zásady můžete nakonfigurovat, podívejte se na ukázky v tomto tématu.

## <a name="create-a-custom-profile"></a>Vytvoření vlastního profilu

1. Začněte podle pokynů v tématu [Konfigurace vlastního nastavení zařízení](custom-settings-configure.md).
2. V okně **Vlastní nastavení OMA-URI** pomocí **Přidat** přidejte nové nastavení.
3. V okně **Přidat řádek** nakonfigurujte tyto údaje:
    - **Název** – zadejte jedinečný název vlastního nastavení pro Android for Work, abyste ho mohli na Azure Portalu snadno identifikovat.
    - **Popis** – zadejte popis, který bude shrnovat účel vlastní zásady pro Android, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.
    - **OMA-URI** – zadejte OMA-URI, pro které chcete zadat nastavení.
    - **Datový typ** – vyberte datový typ, ve kterém toto nastavení OMA-URI určíte. Vyberte z možností **Řetězec**, **Řetězec (soubor XML)**, **Datum a čas**, **Celé číslo**, **Plovoucí desetinná čárka**, **Logická hodnota** nebo **Base64 (soubor)**.
    - **Hodnota** – zadejte hodnotu pro přidružení k dřív zadanému OMA-URI. Metoda zadání této hodnoty se bude lišit podle zvoleného datového typu. Pokud jste třeba zvolili **Datum a čas**, vyberete hodnotu z ovládacího prvku pro výběr data.
4. Po dokončení se pomocí OK vraťte na **Vlastní nastavení OMA-URI** a pak přidejte další nastavení nebo pomocí **Vytvořit** vytvořte vlastní profil.


## <a name="example"></a>Příklad

V tomto příkladu vytvoříte vlastní profil, který se dá použít k nastavení, jestli jsou na zařízeních s Androidem for Work povolené akce Kopírovat a Vložit mezi pracovními a osobními aplikacemi.

1. Pomocí postupu v tomto tématu vytvořte vlastní profil pro zařízení s Androidem for Work s těmito hodnotami:
    - **Název** –zadejte „Blokovat kopírování a vkládání“ nebo jiný vlastní text.
    - **Popis** – zadejte „Blokuje kopírování/vkládání mezi pracovními a osobními aplikacemi“ nebo jiný vlastní text.
    - **OMA-URI** – zadejte **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.
    - **Datový typ** – vyberte **Logická hodnota** k vyjádření, že hodnota pro OMA-URI je **Pravda** nebo **Nepravda**.
    - **Hodnota** – vyberte **Pravda**.
2. Vaše nastavení by nakonec mělo vypadat podobně jako na obrázku.
![Blokování kopírování a vkládání pro Android for Work.](./media/custom-policy-afw-copy-paste.png)
3. Když teď tento vlastní profil přiřadíte zařízením s Androidem for Work, která spravujete, bude mezi aplikacemi v osobním a pracovním profilu zakázáno kopírování a vkládání.