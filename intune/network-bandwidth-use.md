---
title: Detaily o požadavcích na síť a šířce pásma pro Microsoft Intune
titlesuffix: ''
description: Podívejte se na detaily o požadavcích na konfiguraci sítě a šířce pásma pro Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 01/24/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: angerobe
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 2a34c4fe8e010e60e0969d33d70b0e98993f7e23
ms.sourcegitcommit: b0b1030017e741d92c508130447a8242d9ad7a51
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/22/2019
ms.locfileid: "58343007"
---
# <a name="intune-network-configuration-requirements-and-bandwidth"></a>Šířka pásma a požadavky na konfiguraci sítě Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Tyto pokyny pomůžou správcům Intune porozumět požadavkům služby Intune na síť. Tyto informace můžete použít k pochopení požadavků na šířku pásma a nastavení IP adres a portů potřebných k nastavení proxy serverů.

## <a name="average-network-traffic"></a>Průměrné zatížení sítě
Tabulka uvádí přibližnou velikost a četnost u nejčastějšího obsahu přenášeného po síti u každého klienta.

> [!NOTE]
> Aby bylo zajištěno, že zařízení obdrží aktualizace a obsah z Intune, musí se pravidelně připojovat k internetu. Čas potřebný k přijetí aktualizací nebo obsahu se může lišit. Zařízení by ale měla být připojená k internetu každý den nepřetržitě alespoň po dobu jedné hodiny.

|Typ obsahu|Přibližná velikost|Četnost a podrobnosti|
|----------------|--------------------|-------------------------|
|Instalace klienta Intune<br /><br />**K instalaci klienta Intune se přidávají ještě tyto požadavky**|125 MB|**Jednou**<br /><br />Velikost souborů klienta ke stažení se liší podle operačního systému klientského počítače.|
|Registrační balíček klienta|15 MB|**Jednou**<br /><br />Další stahování je možné, pokud jsou pro tento typ obsahu dostupné aktualizace.|
|Agent Endpoint Protection|65 MB|**Jednou**<br /><br />Další stahování je možné, pokud jsou pro tento typ obsahu dostupné aktualizace.|
|Agent Operations Manageru|11 MB|**Jednou**<br /><br />Další stahování je možné, pokud jsou pro tento typ obsahu dostupné aktualizace.|
|Agent zásad|3 MB|**Jednou**<br /><br />Další stahování je možné, pokud jsou pro tento typ obsahu dostupné aktualizace.|
|Agent Vzdálené pomoci prostřednictvím nástroje Microsoft Easy Assist|6 MB|**Jednou**<br /><br />Další stahování je možné, pokud jsou pro tento typ obsahu dostupné aktualizace.|
|Denní operace klienta|6 MB|**Denně**<br /><br />Klient Intune na základě pravidelné komunikace se službou Intune kontroluje aktualizace a zásady a informuje službu o stavu klienta.|
|Aktualizace definicí malwaru Endpoint Protection|Je to různé.<br /><br />Obvykle 40 KB až 2 MB|**Denně**<br /><br />Až třikrát denně|
|Aktualizace modulu Endpoint Protection|5 MB|**Měsíčně**|
|Aktualizace softwaru|Je to různé.<br /><br />Velikost závisí na nasazených aktualizacích.|**Měsíčně**<br /><br />Aktualizace softwaru se obvykle vydávají k druhému úterý v měsíci.<br /><br />Nově zaregistrovaný nebo nasazený počítač může používat větší šířku pásma sítě při stahování celé sady dříve vydaných aktualizací.|
|Aktualizace Service Pack|Je to různé.<br /><br />Velikost se liší u každé nasazené aktualizace Service Pack.|**Je to různé.**<br /><br />Závisí na tom, kdy aktualizace Service Pack nasadíte.|
|Distribuce softwaru|Je to různé.<br /><br />Velikost závisí na nasazeném softwaru.|**Je to různé.**<br /><br />Závisí na tom, kdy software nasadíte.|

## <a name="ways-to-reduce-network-bandwidth-use"></a>Způsob snížení využití šířky pásma sítě
Ke snížení využití šířky pásma sítě pro klienty Intune můžete použít jeden nebo více těchto způsobů.

### <a name="use-a-proxy-server-to-cache-content-requests"></a>Používání proxy serveru pro ukládání požadavků obsahu do mezipaměti
Proxy server může ukládat do mezipaměti obsah a snížit tak počet duplicitních položek ke stažení a redukovat u obsahu z internetu využití šířky pásma sítě.

Proxy server ukládající do mezipaměti, který dostává z klientů žádosti o obsah, může takový obsah načíst a může uložit do mezipaměti odpovědi z webu i stahované položky. Server používá data uložená v mezipaměti pro odpovědi na následné žádosti z klientských počítačů.

Tady jsou obvyklá nastavení proxy serveru, který do mezipaměti ukládá obsah pro klienty Intune.


|          Nastavení           |           Doporučená hodnota           |                                                                                                  Podrobnosti                                                                                                  |
|----------------------------|---------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|         Velikost mezipaměti         |             5 GB až 30 GB             | Hodnota se liší podle počtu klientských počítačích v síti a používaných konfigurací. Aby se soubory neodstranily příliš brzy, upravte velikost mezipaměti pro vaše prostředí. |
| Velikost jednotlivých souborů mezipaměti |                950 MB                 |                                                                     Toto nastavení nemusí být dostupné na všech proxy serverech s ukládáním do mezipaměti.                                                                     |
|   Typy objektů do mezipaměti    | HTTP<br /><br />HTTPS<br /><br />BITS |                                               Balíčky Intune jsou soubory CAB stažené Službou inteligentního přenosu na pozadí (BITS) přes HTTP.                                               |

Informace o používání proxy serveru k ukládání obsahu do mezipaměti najdete v dokumentaci k vašemu řešení proxy serveru.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>Používání Služby inteligentního přenosu na pozadí na počítačích
Intune podporuje používání Služby inteligentního přenosu na pozadí (BITS) na počítačích s Windows ke snížení šířky pásma sítě po dobu, kterou nakonfigurujete. Na stránce **Šířka pásma sítě** zásady agenta Intune můžete pro službu BITS nakonfigurovat zásady.

Další informace o službě BITS a počítačích s Windows najdete v části [Služba inteligentního přenosu na pozadí](http://technet.microsoft.com/library/bb968799.aspx) v knihovně TechNet.

### <a name="use-branchcache-on-computers"></a>Používání BranchCache na počítačích
Klienti Intune můžou díky BranchCache omezit přenos v síti WAN. BranchCache podporují následující operační systémy:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Abyste mohli BranchCache používat, musíte na klientském počítači povolit BranchCache a pak ho nakonfigurovat pro **režim distribuované mezipaměti**.

Ve výchozím nastavení jsou BranchCache a režim distribuované mezipaměti při instalaci klienta Intune na počítače povolené. Pokud ale zásady skupiny BranchCache zakázaly, nemůže Intune přepsat tyto zásady a služba BranchCache zůstane zakázaná.

Pokud používáte BranchCache, měli byste při správě zásad skupiny a zásad brány firewall pro Intune spolupracovat s ostatními správci ve vaší organizaci. Nesmí být nasazeny zásady zakazující BranchCache nebo výjimky brány firewall. Další informace o BranchCache najdete v tématu [BranchCache – přehled](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Požadavky na síťovou komunikaci

Povolte síťovou komunikaci mezi zařízeními, která spravujete, a weby požadovanými pro cloudové služby.

Intune nepoužívá místní infrastrukturu, jako jsou servery se softwarem Intune, ale existují možnosti používání místní infrastruktury včetně nástrojů pro synchronizaci Exchange a Active Directory.

Pokud chcete spravovat počítače za branami firewall a proxy servery, je nutné povolit komunikaci pro Intune.

-   Proxy server musí podporovat **HTTP (80)** i **HTTPS (443)**, protože klienti Intune používají oba protokoly.
-   U některých úloh, jako je stahování softwaru a aktualizací, vyžaduje Intune neověřený přístup k proxy serveru manage.microsoft.com.

Nastavení proxy serveru můžete upravit na jednotlivých klientských počítačích, nebo můžete nastavení změnit pomocí zásad skupiny u všech klientských počítačů, které jsou umístěné za zadaným proxy serverem.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Spravovaná zařízení musí být nakonfigurovaná tak, aby **všichni uživatelé** měli přístup ke službám přes brány firewall.

Následující tabulky obsahují seznam portů a služeb, ke kterým přistupuje klient Intune:

|**Domény**|**IP adresa**|
|---------------------|-----------|
|login.microsoftonline.com | Další informace: [Office 365 –adresy URL a rozsahy IP adres](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |52.175.12.209<br>20.188.107.228<br>52.138.193.149<br>51.144.161.187<br>52.160.70.20<br>52.168.54.64 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 40.83.123.72<br>13.76.177.110<br>52.169.9.87<br>52.174.26.23<br>104.40.82.191<br>13.82.96.212<br>52.234.146.75|
|portal.fei.msua01.manage.microsoft.com<br>m.fei.msua01.manage.microsoft.com |13.64.196.170|
|fei.msua01.manage.microsoft.com<br> portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com |40.71.34.120 |
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com |13.64.198.190|
|fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br> m.fei.msua02.manage.microsoft.com |  13.64.198.190|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |13.64.188.173|
|fei.msua04.manage.microsoft.com<br> portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com |40.71.32.174|
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |13.64.197.181 |
|fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com |40.71.38.205|
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |13.64.191.182 |
|fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com |40.71.37.51 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |40.118.250.246 |
|fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com |13.90.142.194 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.64.250.226 |
|fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com |13.90.151.142 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.169.155.165 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com |52.174.188.97 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.178.190.24 |
|fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com |52.174.16.215 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |40.69.69.27 |
|fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com |52.166.196.199 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |40.69.71.164 |
|fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com |52.174.182.102 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |40.69.78.145 |
|fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com |52.174.192.105 |
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |13.94.46.250|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com |52.163.119.15 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |13.75.124.145 |
|fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com |52.163.119.5|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.175.35.226|
|fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com |52.163.119.6|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.175.38.24|
|fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com |52.163.119.3|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|23.97.165.17|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|
|enterpriseregistration.windows.net|52.175.211.189|

### <a name="apple-device-network-information"></a>Informace o síti pro zařízení Apple

|         Název hostitele         |                                        Adresa URL (IP adresa/podsíť)                                        |  Protocol (Protokol)  |     Port     |                          Zařízení                           |
|--------------------------|-------------------------------------------------------------------------------------------------------|------------|--------------|-----------------------------------------------------------|
|      Konzola správce       |                                  gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |                    Apple iOS a macOS                    |
|      Konzola správce       |                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |                    Apple iOS a macOS                    |
|      Konzola správce       | Apple iTunesitunes.apple.com, \*.mzstatic.com, \*.phobos.apple.com, \*.phobos.apple.com.edgesuite.net |    HTTP    |      80      |                    Apple iOS a macOS                    |
|        Server PI         |                gateway.push.apple.com(17.0.0.0/8) feedback.push.apple.com(17.0.0.0/8)                 |    TCP     |  2195, 2196  |         Platí pro cloudové zasílání zpráv v systémech Apple iOS a macOS.          |
|     Služby zařízení      |                                        gateway.push.apple.com                                         |    TCP     |     2195     |                           Apple                           |
|     Služby zařízení      |                                        feedback.push.apple.com                                        |    TCP     |     2196     |                           Apple                           |
|     Služby zařízení      |   Apple iTunesitunes.apple.com \*.mzstatic.com\*.phobos.apple.com \*.phobos.apple.com.edgesuite.net   |    HTTP    |      80      |                           Apple                           |
| Zařízení (internet/Wi-Fi) |                                 #-courier.push.apple.com(17.0.0.0/8)                                  |    TCP     | 5223 a 443 | Pouze Apple. &#39;#&#39; je náhodné číslo od 0 do 200. |
| Zařízení (internet/Wi-Fi) |                           phobos.apple.comocsp.apple.comax.itunes.apple.com                           | HTTP/HTTPS |  80 nebo 443   |                        Pouze Apple.                         |

