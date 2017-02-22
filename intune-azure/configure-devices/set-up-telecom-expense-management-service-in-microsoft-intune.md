---
title: "Nastavení služby TEM (Telecom Expense Management) | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Nakonfigurujte službu TEM Saaswedo pro integraci s Intune."
keywords: Saaswedo
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 01/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 915d61344a3c1d388305dd51b1e2463bd2e32770
ms.openlocfilehash: 8d94fec099e1dc8918077062fb73b94a5973ea96

---

# <a name="set-up-a-telecom-expense-management-service-in-intune-azure-preview"></a>Nastavení služby TEM (Telecom Expense Management) v Intune Azure Preview
[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Intune obsahuje integrované řešení pro správu výdajů na telekomunikaci Datalert od externího vývojáře softwaru Saaswedo. Datalert je software pro správu výdajů na telekomunikaci v reálném čase, který umožňuje spravovat využití telekomunikačních dat a předejít tak finančně nákladnému a neočekávanému nadlimitnímu využití dat a roamingu u zařízení spravovaných pomocí Intune. Integrace Intune s Datalertem umožňuje centrálně nastavit, monitorovat a vynutit limity využití roamingu a domácích dat pomocí automatických výstrah, které se zobrazí, když limity překročí definované prahové hodnoty. Službu můžete nakonfigurovat tak, aby se použily různé akce u jednotlivců nebo skupin koncových uživatelů, včetně zákazu roamingu v případě, že uživatelé překročí stanovenou prahovou hodnotu. Sestavy využití a monitorování dat jsou dostupné v konzole pro správu Datalertu.

Než budete moct začít používat službu Datalert s Intune, musíte nakonfigurovat nastavení v konzole Datalert a v Intune. Pro službu Datalert a pro Intune musí být připojení zapnuté. Pokud je připojení povolené ve službě Datalert, ale v Intune ne, Intune komunikaci přijme, ale ignoruje ji.

>[!NOTE]
>Pokud chcete tuto funkci povolit ve zkušebním tenantovi, [obraťte se na podporu Microsoftu](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune) a požádejte ji o aktivaci a podporu Datalertu pro požadované softwarové licence.

## <a name="supported-platforms"></a>Podporované platformy

- Samsung Knox
- iOS 8.0 a novější

## <a name="prerequisites"></a>Požadavky

- Předplatné Microsoft Intune
- Předplatné služby TEM (Telecom Expense Management) Datalert

## <a name="list-of-telecom-expense-management-providers"></a>Seznam poskytovatelů služby TEM (Telecom Expense Management)

Intune aktuálně spolupracuje s následujícími poskytovateli služby TEM (Telecom Expense Management):

[Služba TEM Datalert od Saaswedo](http://www.datalert.biz/)

## <a name="configure-intune-to-work-with-the-datalert-service"></a>Konfigurace Intune pro použití se službou Datalert

 

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Jiné** > **Intune**.
3. V okně **Intune** zvolte **Konfigurovat zařízení**.
2. V okně **Konfigurace zařízení** zvolte **Nastavení** > **Služba TEM (Telecom Expense Management)**.
2. V části **Služba TEM (Telecom Expense Management)** vyberte **Stav připojení**.

3. Vyberte **Seznam poskytovatelů služeb TEM** a potom z uvedeného seznamu vyberte svého poskytovatele. Otevře se stránka specifická pro daného poskytovatele. V případě poskytovatele Saaswedo se otevře stránka Datalert. Od Saaswedo si budete muset zakoupit předplatné služby Datalert.

4. V konzole pro správu **Datalert** proveďte tento postup:

    a. Přejdete na kartu **Nastavení** a potom přejděte do části **Konfigurace MDM**.

    b. Vyberte **Odemknout**, abyste na stránce mohli zadat nastavení.

    c. U položky **Server MDM** zvolte **Microsoft Intune**.

    d. U položky **ID tenanta** zadejte ID tenanta Intune a vyberte tlačítko **Připojení**. Když vyberete možnost **Připojení**, služba Datalert zkontroluje v Intune, že dosud neexistuje žádné připojení Datalert v Intune. Po několika sekundách se otevře přihlašovací stránka Microsoft a po ní ověření Azure pro Datalert.

    e. Na ověřovací stránce Microsoft vyberte **Přijmout**. Budete přesměrováni na stránku Datalert s poděkováním, která se po pár sekundách zavře. Datalert ověří připojení a zobrazí zelenou značku zaškrtnutí vedle seznamu ověřených položek. Pokud se ověření nezdaří, zobrazí se zpráva zvýrazněná červeně. Pokud k tomu dojde, obraťte se na podporu Datalertu se žádostí o pomoc.

5. Počkejte pár minut a potom přejděte na portál Azure Portal a zkontrolujte, že se stav připojení zobrazuje jako **Aktivní**. 

    >[!NOTE]
    >Pokud chcete povolit tuto funkci ve zkušební verzi tenanta, [obraťte se prosím na podporu Microsoftu](https://docs.microsoft.com/intune/troubleshoot/how-to-get-support-for-microsoft-intune).

6. Vraťte se do konzoly pro správu Datalertu a nakonfigurujte řádky dat:

    a. Přejdete na kartu **Nastavení**.

    b. Přejděte do průvodce **instalací** a postupujte podle jeho pokynů.



Služba Datalert je nyní aktivní. Spustí monitorování využití dat a zakáže mobilní a roamingová data u zařízení, která překročí nakonfigurované limity využití.

## <a name="turning-off-the-datalert-service"></a>Vypnutí služby Datalert

Zakázání služby Datalert na portálu Azure Portal bude mít za následek toto:

- Všechny akce, které jsou u zařízení použité (z důvodu překročení limitů využití), se zruší.
- Uživatelům se už nebude blokovat přístup k datům a roaming.
- Intune bude stále přijímat signály ze služby, ale bude je ignorovat.

**Vypnutí služby**

1. V okně **Služba TEM (Telecom Expense Management)** na portálu Azure Portal vyberte **Zakázat**.

2. Vyberte **Uložit**.

## <a name="viewing-data-usage-and-roaming-reports"></a>Zobrazení sestav využití dat a roamingu

Vytváření seznam využití dat je momentálně dostupné jenom v konzole pro správu služby Datalert od Saaswedo.



<!--HONumber=Feb17_HO2-->


