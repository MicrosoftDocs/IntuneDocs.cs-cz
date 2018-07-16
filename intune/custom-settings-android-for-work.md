---
title: Nastavení vlastního profilu Intune pro pracovní profily Androidu
titlesuffix: Microsoft Intune
description: Zjistěte, jak vytvořit nastavení vlastního profilu Microsoft Intune pro zařízení s pracovním profilem Androidu.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 04/12/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4724d6e5-05e5-496c-9af3-b74f083141f8
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 109c50acf194598017aa507a0979ad3b9298de9e
ms.sourcegitcommit: 98b444468df3fb2a6e8977ce5eb9d238610d4398
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/07/2018
ms.locfileid: "37905287"
---
# <a name="create-intune-custom-profile-settings-for-android-work-profile-devices"></a>Vytvoření nastavení vlastního profilu Intune pro zařízení s pracovním profilem Androidu

Pomocí vlastních zásad konfigurace pracovního profilu Androidu v Intune přiřaďte nastavení OMA-URI, která lze používat k ovládání funkcí na zařízeních s pracovním profilem Androidu. Jsou to standardní nastavení, která k ovládání funkcí zařízení používá spousta výrobců mobilních zařízení.

Tato vlastnost umožňuje přiřadit nastavení Androidu, která nejdou konfigurovat pomocí zásad Intune. Intune v současnosti podporuje omezený počet vlastních zásad Androidu. Pokud chcete zjistit, které zásady můžete nakonfigurovat, podívejte se na příklady v tomto článku.

## <a name="create-a-custom-profile"></a>Vytvoření vlastního profilu

1. Začněte podle pokynů v tématu [Konfigurace vlastního nastavení zařízení](custom-settings-configure.md). V poli **Platforma** zvolte **Android Enterprise** a jako **Typ profilu** zvolte **Vlastní**.
2. V okně **Vlastní nastavení OMA-URI** pomocí **Přidat** přidejte nové nastavení.
3. V okně **Přidat řádek** nakonfigurujte tyto údaje:
    - **Název** – zadejte jedinečný název vlastního nastavení pracovního profilu Androidu, abyste ho mohli na Azure Portalu snadno identifikovat.
    - **Popis** – zadejte popis, který bude shrnovat účel vlastní zásady pro Android, a uveďte jakékoli další důležité informace, které vám pomůžou zásadu najít.
    - **OMA-URI** – zadejte OMA-URI, pro které chcete zadat nastavení.
    - **Datový typ** – vyberte datový typ, ve kterém toto nastavení OMA-URI určíte. Vyberte z možností **Řetězec**, **Řetězec (soubor XML)**, **Datum a čas**, **Celé číslo**, **Plovoucí desetinná čárka**, **Logická hodnota** nebo **Base64 (soubor)**.
    - **Hodnota** – zadejte hodnotu pro přidružení k dřív zadanému OMA-URI. Metoda zadání této hodnoty se bude lišit podle zvoleného datového typu. Pokud jste třeba zvolili **Datum a čas**, vyberete hodnotu z ovládacího prvku pro výběr data.
4. Po dokončení se pomocí OK vraťte na **Vlastní nastavení OMA-URI** a pak přidejte další nastavení nebo pomocí **Vytvořit** vytvořte vlastní profil.


## <a name="example"></a>Příklad

V tomto příkladu vytvoříte vlastní profil, pomocí kterého můžete omezit, jestli jsou na zařízeních s pracovním profilem Androidu povolené akce Kopírovat a Vložit mezi pracovními a osobními aplikacemi.

1. Pomocí postupu v tomto článku vytvořte vlastní profil pro zařízení s pracovním profilem Androidu s těmito hodnotami:
    - **Název** –zadejte „Blokovat kopírování a vkládání“ nebo jiný vlastní text.
    - **Popis** – zadejte „Blokuje kopírování/vkládání mezi pracovními a osobními aplikacemi“ nebo jiný vlastní text.
    - **OMA-URI** – zadejte **./Vendor/MSFT/WorkProfile/DisallowCrossProfileCopyPaste**.
    - **Datový typ** – vyberte **Logická hodnota** k vyjádření, že hodnota pro OMA-URI je **Pravda** nebo **Nepravda**.
    - **Hodnota** – vyberte **Pravda**.
2. Vaše nastavení by nakonec mělo vypadat podobně jako na obrázku.
![Blokování kopírování a vkládání v pracovním profilu Androidu](./media/custom-policy-afw-copy-paste.png)
3. Když teď tento vlastní profil přiřadíte zařízením s pracovním profilem Androidu, která spravujete, bude mezi aplikacemi v osobním a pracovním profilu zakázáno kopírování a vkládání.