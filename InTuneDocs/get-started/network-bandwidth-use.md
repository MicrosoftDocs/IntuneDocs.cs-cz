---
title: "Využití šířky pásma Intune | Microsoft Intune"
description: "využití šířky pásma Intune"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f737d48-24bc-44cd-aadd-f0a1d59f6893
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: eeb85a28ea6f99a0123ec5df3b0d476a678b85cb
ms.openlocfilehash: 363300f04480a9ed80bd710db5c4ec7c90dd8be3


---

# <a name="intune-network-bandwidth-use"></a>Využití šířky pásma Intune

Před nastavením Microsoft Intune si přečtěte toto téma a další požadavky uvedené v tématu [Co potřebujete vědět, než začnete s Microsoft Intune](what-to-know-before-you-start-microsoft-intune.md).

Informace v dalších částech slouží k plánování síťových přenosů pro klienty Microsoft Intune.

## <a name="average-network-traffic"></a>Průměrné zatížení sítě
Tabulka uvádí přibližnou velikost a četnost u nejčastějšího obsahu přenášeného po síti u každého klienta.

> [!NOTE]
> Aby mohly počítače a mobilní zařízení přijímat potřebné aktualizace a obsah ze služby Intune, musí se pravidelně připojovat k Internetu. Čas potřebný k přijetí aktualizací nebo obsahu se bude lišit. Obecně ale platí, že by počítače a mobilní zařízení měly být trvale připojené k Internetu každý den alespoň jednu hodinu.

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
Použitím proxy serveru, který může ukládat do mezipaměti obsah, můžete snížit počet duplicitních souborů ke stažení a snížit využití šířky pásma sítě klienty, kteří požadují obsah z Internetu.

Proxy server s možností ukládání do mezipaměti přijme požadavky na obsah z klientských počítačů ve vaší síti, načte tento obsah z Internetu a potom uloží odpovědi HTTP a binární soubory ke stažení do mezipaměti. Tento server využívá informace uložené v mezipaměti k odpovědi na následné žádosti z klientských počítačů Intune.

Tady jsou obvyklá nastavení proxy serveru, který do mezipaměti ukládá obsah pro klienty Intune.

|Nastavení|Doporučená hodnota|Podrobnosti|
|-----------|---------------------|-----------|
|Velikost mezipaměti|5 GB až 30 GB|Hodnota se liší podle počtu klientských počítačích v síti a používaných konfigurací. Aby se soubory neodstranily příliš brzy, upravte velikost mezipaměti pro vaše prostředí.|
|Velikost jednotlivých souborů mezipaměti|950 MB|Toto nastavení nemusí být dostupné na všech proxy serverech s ukládáním do mezipaměti.|
|Typy objektů do mezipaměti|HTTP<br /><br />HTTPS<br /><br />BITS|Balíčky Intune jsou soubory CAB stažené Službou inteligentního přenosu na pozadí (BITS) přes HTTP.|
Informace o používání proxy serveru k ukládání obsahu do mezipaměti najdete v dokumentaci k vašemu řešení proxy serveru.

### <a name="use-background-intelligent-transfer-service-on-computers"></a>Používání Služby inteligentního přenosu na pozadí na počítačích
Intune podporuje používání Služby inteligentního přenosu na pozadí (BITS) na počítačích s Windows ke snížení šířky pásma sítě po dobu, kterou nakonfigurujete. Na stránce **Šířka pásma sítě** zásady agenta Intune můžete pro službu BITS nakonfigurovat zásady.

Další informace o službě BITS a počítačích s Windows najdete v části [Služba inteligentního přenosu na pozadí](http://technet.microsoft.com/library/bb968799.aspx) v knihovně TechNet.

### <a name="use-branchcache-on-computers"></a>Používání BranchCache na počítačích
Klienti Intune můžou díky BranchCache omezit přenos v síti WAN. Tyto operační systémy, které jsou podporované jako klienti, taky podporují BranchCache:

- Windows 7
- Windows 8.0
- Windows 8.1
- Windows 10

Abyste mohli BranchCache používat, musíte na klientském počítači povolit BranchCache a pak ho nakonfigurovat pro **režim distribuované mezipaměti**.

Ve výchozím nastavení jsou BranchCache a režim distribuované mezipaměti při instalaci klienta Intune na počítači povolené. Pokud už ale klient má zásady skupiny zakazující BranchCache, Intune nemůže tyto zásady přepsat a služba BranchCache zůstane na tomto počítači zakázaná.

Pokud používáte BranchCache, měli byste komunikovat s ostatními správci ve vaší organizaci, kteří spravují zásady skupiny a zásady brány firewall pro Intune, a zajistit, aby nenasazovali zásady zakazující BranchCache nebo výjimky brány firewall. Další informace o BranchCache najdete v tématu [BranchCache – přehled](http://technet.microsoft.com/library/hh831696.aspx).

## <a name="network-communication-requirements"></a>Požadavky na síťovou komunikaci

Musíte povolit síťovou komunikaci mezi zařízeními, která spravujete a používáte ke správě předplatného Intune, a weby požadovanými pro cloudové služby.

Intune nepoužívá místní infrastrukturu, jako jsou servery se softwarem Intune, ale existují možnosti používání místní infrastruktury včetně nástrojů pro synchronizaci Exchange a Active Directory.

Abyste mohli spravovat počítače, které jsou za bránami firewall nebo proxy servery, je potřeba nastavit brány firewall a proxy servery a povolit komunikaci pro Intune.

### <a name="requirements-for-proxy-servers"></a>Požadavky na proxy servery
Pokud chcete spravovat počítače, které jsou za proxy serverem, mějte na paměti následující okolnosti:

-   Proxy server musí podporovat **HTTP** i **HTTPS** vzhledem k tomu, že klienti Intune používají oba protokoly.
-   Intune podporuje neověřené proxy servery.

Nastavení proxy serveru můžete upravit na jednotlivých klientských počítačích, nebo můžete nastavení změnit pomocí zásad skupiny u všech klientských počítačů, které jsou umístěné za zadaným proxy serverem.

### <a name="requirements-for-firewalls-ports-and-domains"></a>Požadavky na brány firewall, porty a domény
Spravovaná zařízení musí být nakonfigurovaná tak, aby **všichni uživatelé** měli přístup ke službám přes brány firewall.

Následující tabulka obsahuje seznam portů a služeb, ke kterým přistupuje klient Intune.

|**Doména**|**Porty**|**IP adresa**|
|------|----|---|
|manage.microsoft.com<br>a.manage.microsoft.com<br>admin.manage.microsoft.com<br>enterpriseenrollment.manage.microsoft.com<br>enterpriseenrollment-s.manage.microsoft.com<br>i.manage.microsoft.com<br>m.manage.microsoft.com<br>p.manage.microsoft.com<br>portal.manage.microsoft.com<br>r.manage.microsoft.com|80 a 443|134.170.168.254<br>134.170.51.126
|account.manage.microsoft.com|80 a 443|157.56.13.59
|fef.msua01.manage.microsoft.com|80 a 443|138.91.243.97
|fef.msua02.manage.microsoft.com|80 a 443|23.96.112.46
|fef.msua04.manage.microsoft.com|80 a 443|23.96.112.28
|fef.msua05.manage.microsoft.com|80 a 443|138.91.244.151
|fef.msub01.manage.microsoft.com|80 a 443|137.135.128.214
|fef.msub02.manage.microsoft.com|80 a 443|137.135.130.29
|fef.msub03.manage.microsoft.com|80 a 443|23.97.165.17
|fef.msub05.manage.microsoft.com|80 a 443|23.97.166.52
|fef.msuc01.manage.microsoft.com|80 a 443|207.46.225.1
|fef.msuc02.manage.microsoft.com|80 a 443|23.98.66.118
|fef.msuc03.manage.microsoft.com|80 a 443|23.101.0.100
|fef.msuc05.manage.microsoft.com|80 a 443|207.46.154.33
|fef.msua06.manage.microsoft.com|80 a 443|104.42.188.1
|fei.msua01.manage.microsoft.com|80 a 443|138.91.240.131
|fei.msua02.manage.microsoft.com|80 a 443|23.96.112.143
|fei.msua04.manage.microsoft.com|80 a 443|23.96.112.147
|fei.msua05.manage.microsoft.com|80 a 443|138.91.240.163
|fei.msub01.manage.microsoft.com|80 a 443|137.135.130.85
|fei.msub02.manage.microsoft.com|80 a 443|137.135.132.149
|fei.msub03.manage.microsoft.com|80 a 443|23.97.160.232
|fei.msub05.manage.microsoft.com|80 a 443|23.97.162.250
|fei.msuc01.manage.microsoft.com|80 a 443|207.46.224.73
|fei.msuc02.manage.microsoft.com|80 a 443|23.98.66.194
|fei.msuc03.manage.microsoft.com|80 a 443|23.101.2.105
|fei.msuc05.manage.microsoft.com|80 a 443|207.46.147.126
|fei.msua06.manage.microsoft.com|80 a 443|138.91.149.190
|m.fei.msua01.manage.microsoft.com|80 a 443|138.91.240.131
|m.fei.msua02.manage.microsoft.com|80 a 443|23.96.112.143
|m.fei.msua04.manage.microsoft.com|80 a 443|23.96.112.147
|m.fei.msua05.manage.microsoft.com|80 a 443|138.91.240.163
|m.fei.msub01.manage.microsoft.com|80 a 443|137.135.130.85
|m.fei.msub02.manage.microsoft.com|80 a 443|137.135.132.149
|m.fei.msub03.manage.microsoft.com|80 a 443|23.97.160.232
|m.fei.msub05.manage.microsoft.com|80 a 443|23.97.162.250
|m.fei.msuc01.manage.microsoft.com|80 a 443|207.46.224.73
|m.fei.msuc02.manage.microsoft.com|80 a 443|23.98.66.194
|m.fei.msuc03.manage.microsoft.com|80 a 443|23.101.2.105
|m.fei.msuc05.manage.microsoft.com|80 a 443|207.46.147.126
|m.fei.msua06.manage.microsoft.com|80 a 443|138.91.149.190
|m.msua01.manage.microsoft.com|80 a 443|157.55.50.182
|m.msua02.manage.microsoft.com|80 a 443|134.170.49.121
|m.msua04.manage.microsoft.com|80 a 443|134.170.49.126
|m.msua05.manage.microsoft.com|80 a 443|157.55.240.190
|m.msua06.manage.microsoft.com|80 a 443|134.170.49.114
|m.msub01.manage.microsoft.com|80 a 443|94.245.121.50
|m.msub02.manage.microsoft.com|80 a 443|94.245.121.58
|m.msub03.manage.microsoft.com|80 a 443|94.245.121.56
|m.msub05.manage.microsoft.com|80 a 443|157.56.113.123
|m.msuc01.manage.microsoft.com|80 a 443|104.44.84.187
|m.msuc02.manage.microsoft.com|80 a 443|104.44.84.188
|m.msuc03.manage.microsoft.com|80 a 443|104.44.84.189
|m.msuc05.manage.microsoft.com|80 a 443|111.221.76.60
|msua01.manage.microsoft.com|80 a 443|157.55.50.182
|msua02.manage.microsoft.com|80 a 443|134.170.49.121
|msua04.manage.microsoft.com|80 a 443|134.170.49.126
|msua05.manage.microsoft.com|80 a 443|157.55.240.190
|msub01.manage.microsoft.com|80 a 443|94.245.121.50
|msub02.manage.microsoft.com|80 a 443|94.245.121.58
|msub03.manage.microsoft.com|80 a 443|94.245.121.56
|msub05.manage.microsoft.com|80 a 443|157.56.113.123
|msuc01.manage.microsoft.com|80 a 443|104.44.84.187
|msuc02.manage.microsoft.com|80 a 443|104.44.84.188
|msuc03.manage.microsoft.com|80 a 443|104.44.84.189
|msuc05.manage.microsoft.com|80 a 443|111.221.76.60
|msua06.manage.microsoft.com|80 a 443|134.170.49.114
|ncufun.account.manage.microsoft.com|80 a 443|157.55.252.224
|neufun.account.manage.microsoft.com|80 a 443|65.52.229.134
|portal.fei.msua01.manage.microsoft.com|80 a 443|138.91.240.131
|portal.fei.msua02.manage.microsoft.com|80 a 443|23.96.112.143
|portal.fei.msua04.manage.microsoft.com|80 a 443|23.96.112.147
|portal.fei.msua05.manage.microsoft.com|80 a 443|138.91.240.163
|portal.fei.msub01.manage.microsoft.com|80 a 443|137.135.130.85
|portal.fei.msub02.manage.microsoft.com|80 a 443|137.135.132.149
|portal.fei.msub03.manage.microsoft.com|80 a 443|23.97.160.232
|portal.fei.msub05.manage.microsoft.com|80 a 443|23.97.162.250
|portal.fei.msuc01.manage.microsoft.com|80 a 443|207.46.224.73
|portal.fei.msuc02.manage.microsoft.com|80 a 443|23.98.66.194
|portal.fei.msuc03.manage.microsoft.com|80 a 443|23.101.2.105
|portal.fei.msuc05.manage.microsoft.com|80 a 443|207.46.147.126
|portal.fei.msua06.manage.microsoft.com|80 a 443|138.91.149.190
|portal.msua01.manage.microsoft.com|80 a 443|157.55.50.182
|portal.msua02.manage.microsoft.com|80 a 443|134.170.49.121
|portal.msua04.manage.microsoft.com|80 a 443|134.170.49.126
|portal.msua05.manage.microsoft.com|80 a 443|157.55.240.190
|portal.msub01.manage.microsoft.com|80 a 443|94.245.121.50
|portal.msub02.manage.microsoft.com|80 a 443|94.245.121.58
|portal.msub03.manage.microsoft.com|80 a 443|94.245.121.56
|portal.msub05.manage.microsoft.com|80 a 443|157.56.113.123
|portal.msuc01.manage.microsoft.com|80 a 443|104.44.84.187
|portal.msuc02.manage.microsoft.com|80 a 443|104.44.84.188
|portal.msuc03.manage.microsoft.com|80 a 443|104.44.84.189
|portal.msuc05.manage.microsoft.com|80 a 443|111.221.76.60
|portal.msua06.manage.microsoft.com|80 a 443|134.170.49.114
|ssu2.manage.microsoft.com|80 a 443|157.55.99.181
|status.manage.microsoft.com|80 a 443|157.55.99.170
|swda01.manage.microsoft.com<br>swda02.manage.microsoft.com<br>swdb01.manage.microsoft.com<br>swdb02.manage.microsoft.com<br>swdc01.manage.microsoft.com<br>swdc02.manage.microsoft.com|80 a 443|93.184.215.200
|*.microsoftonline-p.com|80 a 443||
|has.spserv.microsoft.com<br>Požadované pro službu ověření stavu zařízení|443||
|*.microsoftonline-p.net|80 a 443||
|*.portal.office.com|80 a 443||
|*.spynet2.microsoft.com|443||
|c.microsoft.com|80 a 443||
|c1.microsoft.com|80 a 443||
|blob.core.windows.net|80 a 443||
|ajax.aspnetcdn.com|80 a 443||
|*.googleapis.com<br>Tato doména je vyžadovaná pro podporu JQuery, když používáte web portálu společnosti.|80 a 443||
|wustat.microsoft.com|80 a 443||
|Služba Microsoft Update|\*.update.microsoft.com<br>download.microsoft.com<br>update.microsoft.com<br>\*.download.windowsupdate.com<br>download.windowsupdate.com<br>\*.windowsupdate.com<br>windowsupdate.microsoft.com<br>ntservicepack.microsoft.com|80 a 443|
|Požadavky na vyhledávání DNS|manage.microsoft.com.nsatc.net|80|
|Komunikace zařízení Samsung KNOX Standard přes bránu firewall|Pokud chcete zařízením Samsung KNOX Standard povolit, aby kontaktovala servery KNOX Standard přes bránu firewall, postupujte podle pokynů v části Nejčastější dotazy pro Samsung KNOX Standard.||
|Komunikace s podmíněným přístupem|443|204.79.197.200|
|Dokumentace, nápověda a podpora:</br></br>*.livemeeting.com<br>\*.microsoftonline.com<br>\*.social.technet.microsoft.com<br>blogs.technet.com<br>go.microsoft.com<br>onlinehelp.microsoft.com<br>www.microsoft.com|80|||

>[!div class="step-by-step"]

>[&larr; **Předpoklady**](supported-mobile-devices-and-computers.md)     [**Práce v síti** &rarr;](start-with-a-paid-subscription-to-microsoft-intune-step-1.md)  



<!--HONumber=Dec16_HO2-->


