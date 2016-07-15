---
title: "Využití šířky pásma Intune | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 779127bfd39145010f0d9b6609286aaf4dedfdc8
ms.openlocfilehash: e104dc52a8a9bdda4b2edb2939d8c7c36e8ecc12


---

# Využití šířky pásma Intune

Před nastavením [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] si přečtěte toto téma a další požadavky uvedené v tématu [Co potřebujete vědět, než začnete s Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

Informace v dalších částech slouží k plánování síťových přenosů pro klienty [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)].

## Průměrné zatížení sítě
Tato tabulka uvádí přibližnou velikost a četnost společného obsahu, který se přenáší po síti u jednotlivých klientů.

> [!NOTE]
> Aby mohly počítače a mobilní zařízení přijímat potřebné aktualizace a obsah ze služby [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], musí se pravidelně připojovat k Internetu. Čas potřebný k přijetí aktualizací nebo obsahu se bude lišit. Obecně ale platí, že by počítače a mobilní zařízení měly být trvale připojené k Internetu každý den alespoň jednu hodinu.

|Typ obsahu|Přibližná velikost|Četnost a podrobnosti|
|----------------|--------------------|-------------------------|
|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] se přidávají ještě tyto požadavky<br /><br />**K instalaci klienta [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] se přidávají ještě tyto požadavky**|125 MB|**Jednou**<br /><br />Velikost souborů klienta ke stažení se liší podle operačního systému klientského počítače.|
|Registrační balíček klienta|15 MB|**Jednou**<br /><br />Další stahování je možné, pokud jsou pro tento typ obsahu dostupné aktualizace.|
|Agent Endpoint Protection|65 MB|**Jednou**<br /><br />Další stahování je možné, pokud jsou pro tento typ obsahu dostupné aktualizace.|
|Agent Operations Manageru|11 MB|**Jednou**<br /><br />Další stahování je možné, pokud jsou pro tento typ obsahu dostupné aktualizace.|
|Agent zásad|3 MB|**Jednou**<br /><br />Další stahování je možné, pokud jsou pro tento typ obsahu dostupné aktualizace.|
|Agent Vzdálené pomoci prostřednictvím nástroje Microsoft Easy Assist|6 MB|**Jednou**<br /><br />Další stahování je možné, pokud jsou pro tento typ obsahu dostupné aktualizace.|
|Denní operace klienta|6 MB|**Denně**<br /><br />Klient [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] na základě pravidelné komunikace se službou [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] kontroluje aktualizace a zásady a informuje službu o stavu klienta.|
|Aktualizace definicí malwaru Endpoint Protection|Je to různé.<br /><br />Obvykle 40 KB až 2 MB|**Denně**<br /><br />Až třikrát denně|
|Aktualizace modulu Endpoint Protection|5 MB|**Měsíčně**|
|Aktualizace softwaru|Je to různé.<br /><br />Velikost závisí na nasazených aktualizacích.|**Měsíčně**<br /><br />Aktualizace softwaru se obvykle vydávají k druhému úterý v měsíci.<br /><br />Nově zaregistrovaný nebo nasazený počítač může používat větší šířku pásma sítě při stahování celé sady dříve vydaných aktualizací.|
|Aktualizace Service Pack|Je to různé.<br /><br />Velikost se liší u každé nasazené aktualizace Service Pack.|**Je to různé.**<br /><br />Závisí na tom, kdy aktualizace Service Pack nasadíte.|
|Distribuce softwaru|Je to různé.<br /><br />Velikost závisí na nasazeném softwaru.|**Je to různé.**<br /><br />Závisí na tom, kdy software nasadíte.|

## Způsob snížení využití šířky pásma sítě
Ke snížení využití šířky pásma sítě pro klienty [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] můžete použít jeden nebo víc těchto způsobů.

### Používání proxy serveru pro ukládání požadavků obsahu do mezipaměti
Použitím proxy serveru, který může ukládat do mezipaměti obsah, můžete snížit počet duplicitních souborů ke stažení a snížit využití šířky pásma sítě klienty, kteří požadují obsah z Internetu.

Proxy server s možností ukládání do mezipaměti přijme požadavky na obsah z klientských počítačů ve vaší síti, načte tento obsah z Internetu a potom uloží odpovědi HTTP a binární soubory ke stažení do mezipaměti. Tento server využívá informace uložené v mezipaměti k odpovědi na následné žádosti z klientských počítačů [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

Tady jsou obvyklá nastavení proxy serveru, který ukládá do mezipaměti obsah pro klienty [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)].

|Nastavení|Doporučená hodnota|Podrobnosti|
|-----------|---------------------|-----------|
|Velikost mezipaměti|5 GB až 30 GB|Hodnota se liší podle počtu klientských počítačích v síti a používaných konfigurací. Aby se soubory neodstranily příliš brzy, upravte velikost mezipaměti pro vaše prostředí.|
|Velikost jednotlivých souborů mezipaměti|950 MB|Toto nastavení nemusí být dostupné na všech proxy serverech s ukládáním do mezipaměti.|
|Typy objektů do mezipaměti|HTTP<br /><br />HTTPS<br /><br />BITS|[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] jsou soubory CAB stažené Službou inteligentního přenosu na pozadí (BITS) přes HTTP.|
Informace o používání proxy serveru k ukládání obsahu do mezipaměti najdete v dokumentaci k vašemu řešení proxy serveru.

### Používání Služby inteligentního přenosu na pozadí na počítačích
[!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)] podporuje používání Služby inteligentního přenosu na pozadí (BITS) na počítačích s Windows ke snížení šířky pásma sítě po dobu, kterou nakonfigurujete. Na stránce **Šířka pásma sítě** zásady agenta [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] můžete pro službu BITS nakonfigurovat zásady.

Další informace o službě BITS a počítačích s Windows najdete v části [Služba inteligentního přenosu na pozadí](http://technet.microsoft.com/library/bb968799.aspx) v knihovně TechNet.

### Používání BranchCache na počítačích
[!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] můžou díky BranchCache omezit přenos v síti WAN. Tyto operační systémy, které jsou podporované jako klienti, taky podporují BranchCache:

-   [!INCLUDE[nextref_client_7](../includes/nextref_client_7_md.md)]

-   [!INCLUDE[win8_client_2](../includes/win8_client_2_md.md)]

-   [!INCLUDE[winblue_client_2](../includes/winblue_client_2_md.md)]

Abyste mohli BranchCache používat, musíte na klientském počítači povolit BranchCache a pak ho nakonfigurovat pro **režim distribuované mezipaměti**.

Ve výchozím nastavení jsou BranchCache a režim distribuované mezipaměti na počítači povolené při instalaci klienta [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)]. Pokud už ale klient má zásady skupiny zakazující BranchCache, [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] nemůže tyto zásady přepsat a služba BranchCache zůstane na tomto počítači zakázaná.

Pokud používáte BranchCache, měli byste komunikovat s ostatními správci ve vaší organizaci, kteří spravují zásady skupiny a zásady brány firewall pro [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)], a zajistit, aby nenasazovali zásady zakazující BranchCache nebo výjimky brány firewall. Další informace o BranchCache najdete v tématu [BranchCache – přehled](http://technet.microsoft.com/library/hh831696.aspx).

### Související témata
[Co potřebujete vědět, než začnete s Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md)


<!--HONumber=Jun16_HO4-->


