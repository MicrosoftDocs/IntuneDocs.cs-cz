---
title: Detaily o požadavcích na síť a šířce pásma pro Microsoft Intune
titleSuffix: ''
description: Podívejte se na detaily o požadavcích na konfiguraci sítě a šířce pásma pro Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 04/03/2019
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
ms.openlocfilehash: 40f9ada715570de7b5b2f95292b7ed0d238242d2
ms.sourcegitcommit: 04d29d47b61486b3586a0e0e5e8e48762351f2a3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/11/2019
ms.locfileid: "59509707"
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
> [!NOTE]
> Pokud používáte proxy server pro ukládání do mezipaměti obsah žádosti, komunikace mezi klientem a proxy serveru a z proxy serveru do služby Intune jenom zašifrovaná. Připojení z klienta do Intune nebudou šifrovaná začátku do konce.

Informace o používání proxy serveru k ukládání obsahu do mezipaměti najdete v dokumentaci k vašemu řešení proxy serveru.

### <a name="use-background-intelligent-transfer-service-bits-on-computers"></a>Používání služby inteligentního přenosu na pozadí (BITS) na počítačích
Během doby, které nakonfigurujete můžete použít službu BITS na počítači Windows ke snížení šířky pásma sítě. Můžete nakonfigurovat zásady služby BITS na **šířky pásma sítě** stránka zásady agenta Intune.

> [!NOTE]
> Jenom OS rozhraní pro správu pro typ aplikace MobileMSI správu správy mobilních zařízení na Windows, používá BITS ke stažení. AppX/MsiX používat jejich vlastní zásobníku stahování – služba BITS a aplikace Win32 přes agenta Intune používat optimalizace doručení spíše než službu BITS.

Další informace o službě BITS a počítačích s Windows najdete v části [Služba inteligentního přenosu na pozadí](http://technet.microsoft.com/library/bb968799.aspx) v knihovně TechNet.

### <a name="use-branchcache-on-computers"></a>Používání BranchCache na počítačích
Klienti Intune můžou díky BranchCache omezit přenos v síti WAN. BranchCache podporují následující operační systémy:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Abyste mohli BranchCache používat, musíte na klientském počítači povolit BranchCache a pak ho nakonfigurovat pro **režim distribuované mezipaměti**.

Při instalaci klienta Intune na počítačích, jsou ve výchozím nastavení povolená služba BranchCache a režim distribuované mezipaměti. Pokud se zásady skupiny BranchCache zakázaly, Intune nebude tyto zásady přepsat a Služba BranchCache zůstane zakázaná.

Pokud používáte BranchCache, měli byste při správě zásad skupiny a zásad brány firewall pro Intune spolupracovat s ostatními správci ve vaší organizaci. Zajistěte, aby že se nenasazují zásady zakazující BranchCache nebo výjimky brány Firewall. Další informace o BranchCache najdete v tématu [BranchCache – přehled](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Požadavky na síťovou komunikaci

Povolte síťovou komunikaci mezi zařízeními, která spravujete a koncové body požadovanými pro cloudové služby.

Jako čistě cloudovou službu Intune nevyžaduje místní infrastrukturu, jako jsou servery nebo brány.

Ke správě zařízení za bránami firewall nebo proxy servery, je nutné povolit komunikaci pro Intune.

- Proxy server musí podporovat **HTTP (80)** i **HTTPS (443)**, protože klienti Intune používají oba protokoly.
- Pro některé úlohy (jako je stahování aktualizace softwaru), vyžaduje Intune přístup k neověřenému proxy serveru na adresu manage.microsoft.com

Můžete upravit nastavení proxy serveru na jednotlivých klientských počítačích. Nastavení zásad skupiny můžete také změnit nastavení pro všechny klientské počítače umístěné za zadaným proxy serverem.


<!--
> [!NOTE] If Windows 8.1 devices haven't cached proxy server credentials, enrollment might fail because the request doesn't prompt for credentials. Enrollment fails without warning as the request wait for a connection. If users might experience this issue, instruct them to open their browser settings and save proxy server settings to enable a connection.   -->

Spravovaná zařízení musí být nakonfigurovaná tak, aby **všichni uživatelé** měli přístup ke službám přes brány firewall.

Následující tabulky obsahují seznam portů a služeb, ke kterým přistupuje klient Intune:

|**Domény**|**IP adresa**|
|---------------------|-----------|
|login.microsoftonline.com | Další informace: [Office 365 –adresy URL a rozsahy IP adres](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) |
|portal.manage.microsoft.com<br> m.manage.microsoft.com |52.175.12.209<br>20.188.107.228<br>52.138.193.149<br>51.144.161.187<br>52.160.70.20<br>52.168.54.64 |
| sts.manage.microsoft.com | 13.93.223.241 <br>52.170.32.182 <br>52.164.224.159 <br>52.174.178.4 <br>13.75.122.143 <br>52.163.120.84|
|Manage.microsoft.com <br>i.manage.microsoft.com <br>r.manage.microsoft.com <br>a.manage.microsoft.com <br>p.manage.microsoft.com <br>EnterpriseEnrollment.manage.microsoft.com <br>EnterpriseEnrollment-s.manage.microsoft.com | 40.83.123.72<br>13.76.177.110<br>52.169.9.87<br>52.174.26.23<br>104.40.82.191<br>13.82.96.212|
|fei.msua01.manage.microsoft.com<br>portal.fei.msua01.manage.microsoft.com <br>m.fei.msua01.manage.microsoft.com<br>fei.msua02.manage.microsoft.com<br>portal.fei.msua02.manage.microsoft.com<br>m.fei.msua02.manage.microsoft.com<br>fei.msua04.manage.microsoft.com<br>portal.fei.msua04.manage.microsoft.com <br>m.fei.msua04.manage.microsoft.com<br>fei.msua05.manage.microsoft.com <br>portal.fei.msua05.manage.microsoft.com <br>m.fei.msua05.manage.microsoft.com<br>fei.amsua0502.manage.microsoft.com <br>portal.fei.amsua0502.manage.microsoft.com <br>m.fei.amsua0502.manage.microsoft.com<br>fei.msua06.manage.microsoft.com <br>portal.fei.msua06.manage.microsoft.com <br>m.fei.msua06.manage.microsoft.com<br>fei.amsua0602.manage.microsoft.com <br>portal.fei.amsua0602.manage.microsoft.com <br>m.fei.amsua0602.manage.microsoft.com<br>fei.amsua0202.manage.microsoft.com <br>portal.fei.amsua0202.manage.microsoft.com <br>m.fei.amsua0202.manage.microsoft.com<br>fei.amsua0402.manage.microsoft.com <br>portal.fei.amsua0402.manage.microsoft.com <br>m.fei.amsua0402.manage.microsoft.com|52.160.70.20<br>52.168.54.64 |
|fei.msub01.manage.microsoft.com <br>portal.fei.msub01.manage.microsoft.com <br>m.fei.msub01.manage.microsoft.com<br>fei.amsub0102.manage.microsoft.com <br>portal.fei.amsub0102.manage.microsoft.com <br>m.fei.amsub0102.manage.microsoft.com<br>fei.msub02.manage.microsoft.com <br>portal.fei.msub02.manage.microsoft.com <br>m.fei.msub02.manage.microsoft.com<br>fei.msub03.manage.microsoft.com <br>portal.fei.msub03.manage.microsoft.com <br>m.fei.msub03.manage.microsoft.com<br>fei.msub05.manage.microsoft.com <br>portal.fei.msub05.manage.microsoft.com <br>m.fei.msub05.manage.microsoft.com<br>fei.amsub0202.manage.microsoft.com <br>portal.fei.amsub0202.manage.microsoft.com <br>m.fei.amsub0202.manage.microsoft.com<br>fei.amsub0302.manage.microsoft.com <br>portal.fei.amsub0302.manage.microsoft.com <br>m.fei.amsub0302.manage.microsoft.com|52.138.193.149<br>51.144.161.187|
|fei.msuc01.manage.microsoft.com <br>portal.fei.msuc01.manage.microsoft.com <br>m.fei.msuc01.manage.microsoft.com<br>fei.msuc02.manage.microsoft.com <br>portal.fei.msuc02.manage.microsoft.com <br>m.fei.msuc02.manage.microsoft.com<br>fei.msuc03.manage.microsoft.com <br>portal.fei.msuc03.manage.microsoft.com <br>m.fei.msuc03.manage.microsoft.com<br>fei.msuc05.manage.microsoft.com <br>portal.fei.msuc05.manage.microsoft.com <br>m.fei.msuc05.manage.microsoft.com|52.175.12.209<br>20.188.107.228|
|fef.msua01.manage.microsoft.com|138.91.243.97|
|fef.msua02.manage.microsoft.com|52.177.194.236|
|fef.msua04.manage.microsoft.com|23.96.112.28|
|fef.msua05.manage.microsoft.com|138.91.244.151|
|fef.msua06.manage.microsoft.com|13.78.185.97|
|fef.msua07.manage.microsoft.com|52.175.208.218|
|fef.msub01.manage.microsoft.com|137.135.128.214|
|fef.msub02.manage.microsoft.com|137.135.130.29|
|fef.msub03.manage.microsoft.com|52.169.82.238|
|fef.msub05.manage.microsoft.com|23.97.166.52|
|fef.msuc01.manage.microsoft.com|52.230.19.86|
|fef.msuc02.manage.microsoft.com|23.98.66.118|
|fef.msuc03.manage.microsoft.com|23.101.0.100|
|fef.msuc05.manage.microsoft.com|52.230.16.180|
|fef.amsua0202.manage.microsoft.com|52.165.165.17|
|fef.amsua0402.manage.microsoft.com|40.69.157.122|
|fef.amsua0502.manage.microsoft.com|13.85.68.142|
|fef.amsua0602.manage.microsoft.com|52.161.28.64|
|fef.amsub0102.manage.microsoft.com|40.118.98.207|
|fef.amsub0202.manage.microsoft.com|40.69.208.122|
|fef.amsub0302.manage.microsoft.com|13.74.145.65|
|enterpriseregistration.windows.net|52.175.211.189|
|Admin.manage.microsoft.com|52.224.221.227<br>52.161.162.117<br>52.178.44.195<br>52.138.206.56<br>52.230.21.208<br>13.75.125.10|
|wip.mam.manage.microsoft.com|52.187.76.84<br>13.76.5.121<br>52.165.160.237<br>40.86.82.163<br>52.233.168.142<br>168.63.101.57|
|mam.manage.microsoft.com|104.40.69.125<br>13.90.192.78<br>40.85.174.177<br>40.85.77.31<br>137.116.229.43<br>52.163.215.232<br>52.174.102.180|






### <a name="apple-device-network-information"></a>Informace o síti pro zařízení Apple


|Používá pro|Hostname (IP address/subnet)|Protocol (Protokol)|Port|
|-----|--------|------|-------|
|Nabízená oznámení ze služby Intune prostřednictvím Apple Push Notification Service (APNS). Najdete v dokumentaci Apple [zde](https://support.apple.com/en-us/HT203609)|                                    gateway.push.apple.com (17.0.0.0/8)                                  |    TCP     |     2195     |
|Odeslání zpětné vazby na službu Intune prostřednictvím Apple Push Notification Service (APNS)|                                  feedback.push.apple.com(17.0.0.0/8)                                  |    TCP     |     2196     |
|Načítání a zobrazování obsahu ze serverů společnosti Apple|itunes.apple.com<br>\*.itunes.apple.com<br>\*.mzstatic.com<br>\*.phobos.apple.com<br> \*.phobos.itunes-apple.com.akadns.net |    HTTP    |      80      |
|Komunikaci se servery pro služby APN|#-courier.push.apple.com (17.0.0.0/8)<br>"#" je náhodné číslo od 0 do 50.|    TCP     |  5223 a 443  |
|Různé funkce, včetně přístupu k World Wide Web iTunes storu, obchodu s aplikacemi s macOS, Icloudu, zasílání zpráv, atd. |phobos.apple.com<br>ocsp.apple.com<br>ax.itunes.apple.com<br>ax.itunes.apple.com.edgesuite.net| HTTP/HTTPS |  80 nebo 443   |

Další informace najdete v tématu společnosti Apple [porty TCP a UDP používané softwarové produkty společnosti Apple](https://support.apple.com/en-us/HT202944), [o macOS, iOS a iTunes připojení k serveru hostitele a iTunes pozadí procesy](https://support.apple.com/en-us/HT201999), a [Pokud vaše klienty se systémy iOS a macOS nedaří získat nabízených oznámení Apple](https://support.apple.com/en-us/HT203609).
