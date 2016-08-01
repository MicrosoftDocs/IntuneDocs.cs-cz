---
title: "Zásady brány firewall pro počítače s Windows | Microsoft Intune"
description: "Intune vám může pomoci zabezpečit počítače, které spravujete, mnoha různými způsoby, včetně nastavení brány Windows Firewall."
keywords: 
author: robstackmsft
manager: arob98
ms.date: 07/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9549c072-ac3d-4d14-a931-a2eda8846217
ms.reviewer: owenyen
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a409d36c1c5fcfd3d81ce0cbdf1f69af4747157a
ms.openlocfilehash: 826bdcd4db11b0eca94a250d6cb95f76e22569bf


---

# Pomoc při ochraně počítačů s Windows pomocí zásad brány Windows Firewall v Microsoft Intune
Microsoft Intune vám může pomoci zabezpečit počítače PC s Windows, které spravujete, mnoha různými způsoby, včetně použití zásad, které vám umožní nakonfigurovat nastavení brány Windows Firewall v počítačích PC.

Pokud jste si ještě do počítačů nenainstalovali klienta Intune pro počítače s Windows, přečtěte si téma [Instalace klienta na počítači s Windows pomocí Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Informace v následujících částech vám pomohou s konfigurací, nasazováním a monitorováním zásad brány Windows Firewall na počítačích PC.

## Použití zásad Intune ke správě brány Windows Firewall
Zásady brány Windows Firewall umožňují vytvářet a nasazovat nastavení, která řídí bránu Windows Firewall na spravovaných počítačích PC. Není možné spravovat vlastní výjimky pro bránu Windows Firewall a tato nastavení neovlivní brány firewall třetích stran.

> [!NOTE]
> Pokud jsou zásady Microsoft Intune a zásady skupiny nakonfigurované pro správu stejných nastavení na počítači PC, pak má nastavení zásad skupiny přednost před zásadami Microsoft Intune. Informace o tom, jak zamezit konfliktům mezi zásadami Intune a zásadami skupiny, najdete v článku [Řešení konfliktů GPO a zásad Microsoft Intune](resolve-gpo-and-microsoft-intune-policy-conflicts.md).
>
> Pokud chcete nasadit nastavení brány Windows Firewall do počítačů se systémem Windows Vista, musíte na tyto počítače nejdřív nainstalovat [opravu Hotfix KB971800](http://support2.microsoft.com/kb/971800) .

> [!IMPORTANT]
> Pokud chcete spravovat bránu Windows Firewall pomocí Intune, musí být na počítačích, které budete spravovat, povolené následující dvě služby:
>
> -   Brána Windows Firewall
> -   Agent zásad protokolu IPsec

## Konfigurace zásad brány Windows Firewall

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) zvolte **Zásady** &gt; **Přidat zásadu**.

2.  Konfigurujte a nasaďte zásady **nastavení brány Windows Firewall** . Můžete použít doporučená nastavení nebo nastavení upravit. Pokud potřebujete více informací o postupu při vytváření a nasazování zásad, projděte si článek [Běžné úlohy správy počítačů s Windows pomocí počítačového klienta Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

    V následující části jsou uvedeny hodnoty, které můžete v zásadách konfigurovat, a také výchozí hodnoty, které se použijí, pokud zásady neupravíte.

Po nasazení zásad brány Windows Firewall můžete zobrazit stav těchto zásad na stránce **Všechny zásady** pracovního prostoru **Zásady**.

## Nastavení zásad brány Windows Firewall

### Zapnout bránu Windows Firewall

Tato nastavení zásad povolují bránu Windows Firewall na spravovaných počítačích, které jsou připojené k doméně (například na pracovišti), privátní (důvěryhodné) síti (například k domácí síti) nebo k nedůvěryhodné, veřejné síti (například v kavárně). Výchozí hodnota pro každé z těchto nastavení je **Ano**, což je nejbezpečnější hodnota. 



### Blokování všech příchozích připojení, včetně připojení uvedených na seznamu povolených programů

Tato nastavení zásad konfigurují bránu Windows Firewall na blokování příchozích síťových přenosů, když jsou spravované počítače připojené k doméně (například na pracovišti), k privátní (důvěryhodné) síti (například k domácí síti) nebo k nedůvěryhodné, veřejné síti (například v kavárně). Výchozí hodnota pro každé z těchto nastavení je **Ano**, což je nejbezpečnější hodnota. 

> [!IMPORTANT]
> Obsahuje-li dané prostředí spravované počítače, v nichž je spuštěn systém Windows Vista bez nainstalovaných aktualizací Service Pack, je nutné nainstalovat aktualizaci uváděnou ve znalostní bázi Microsoft Knowledge Base v [článku 971800](http://go.microsoft.com/fwlink/?LinkId=188405) nebo jinak vypnout nastavení zásady **Blokovat všechna příchozí připojení** v zásadách nasazených v těchto počítačích.

### Oznámit uživatelům blokování nového programu bránou Windows Firewall

Tato nastavení zásad konfigurují to, jestli bude brána Windows Firewall oznamovat uživatelům počítačů, že jsou blokovány příchozí síťový přenosy, když jsou spravované počítače připojené k doméně (například na pracovišti), privátní (důvěryhodné) síti (například k domácí síti) nebo k nedůvěryhodné, veřejné síti (například v kavárně). Výchozí hodnota pro každé z těchto nastavení je **Ano**.


### Předdefinované výjimky

Po nakonfigurování výše uvedených základních hodnot můžete nakonfigurovat výjimky, které budou povolovat určité přenosy v síti přes bránu firewall bez ohledu na výše nakonfigurované hodnoty. Ve výchozím nastavení nejsou nakonfigurována žádná z těchto nastavení.

|Název nastavení|Podrobnosti|
|------------------|--------------------|
|**Služba BranchCache – načítání obsahu**<br>(Windows 7 nebo novější)|Umožňuje klientům služby BranchCache prostřednictvím protokolu HTTP načítat obsah vzájemně jeden z druhého (v distribuovaném režimu) a z hostované mezipaměti (v režimu hostované mezipaměti). Toto nastavení využívá protokol HTTP.|
|**Služba BranchCache – klient hostované mezipaměti**<br>(Windows 7 nebo novější)|Umožňuje klientům služby BranchCache používat hostovanou mezipaměť. Toto nastavení využívá protokol HTTPS.|
|**Služba BranchCache – server hostované mezipaměti**|Umožňuje klientům služby BranchCache používat hostovanou mezipaměť ke komunikaci s ostatními klienty. Toto nastavení využívá protokol HTTPS.|
|**Služba BranchCache – zjišťování rovnocenných zařízení**<br>(Windows 7 nebo novější)|Umožňuje klientům služby BranchCache používat protokol WS Discovery k vyhledání dostupnosti obsahu v místní podsíti.|
|**Ukládání do sdílené mezipaměti BITS**|Umožňuje klientům používat službu inteligentního přenosu na pozadí (BITS) k vyhledání a sdílení souborů uložených v mezipaměti BITS na klientských počítačích ve stejné podsíti. Toto nastavení využívá rozhraní WSDAPI a RPC.|
|**Připojení k síťovému projektoru**|Umožňuje uživatelům připojit se k projektorům prostřednictvím drátových nebo bezdrátových sítí a promítat prezentace. Toto nastavení využívá rozhraní WSDAPI.|
|**Základní síťové služby**|Umožňuje klientům používat protokoly IPv4 a IPv6 pro připojení k síťovým prostředkům.|
|**Koordinátor distribuovaných transakcí**|Umožňuje spravovaným počítačům koordinovat transakce, které aktualizují prostředky s ochranou transakcí, jako jsou databáze, fronty zpráv nebo souborové systémy.|
|**Sdílení souborů a tiskáren**|Umožňuje uživatelům sdílet místní soubory a tiskárny s dalšími uživateli v síti. Toto nastavení využívá rozhraní NetBIOS, LLMNR, SMB a RPC.|
|**Domácí skupina**<br>(Windows 7 nebo novější)|Umožňuje spravovaným počítačům účast v síti domácí skupiny.|
|**Služba iSCSI**|Umožňuje spravovaným počítačům připojení k serverům a zařízením iSCSI.|
|**Služba správy klíčů**|Umožňuje spočítání počítačů kvůli shodě s licencí v podnikovém prostředí.|
|**Zařízení Media Center Extender**|Umožňuje zařízením Media Center Extender komunikovat s počítači se systémem Windows Media Center. Toto nastavení využívá protokol SSDP a službu qWave.|
|**Služba Netlogon**|Konfiguruje zabezpečený kanál mezi klienty v doméně a řadičem domény za účelem ověřování totožnosti uživatelů a služeb. Toto nastavení využívá protokol RPC.|
|**Zjišťování sítě**|Umožňuje počítačům zjišťovat jiná zařízení a být zjištěny jinými zařízeními v síti. Toto nastavení používá službu publikování a hostitele rozpoznávání funkcí a taky síťové protokoly SSDP, NetBIOS, LLMNR a UPnP.|
|**Výstrahy a protokolování výkonu**|Umožňuje vzdálenou správu služby Výstrahy a protokolování výkonu. Toto nastavení využívá protokol RPC.|
|**Vzdálená správa**|Umožňuje vzdálenou správu počítače.|
|**Vzdálená pomoc**|Umožňuje uživatelům spravovaných počítačů žádat o vzdálenou pomoc od jiných uživatelů v síti. Toto nastavení používá síťové protokoly SSDP, PNRP, Teredo a UPnP.|
|**Vzdálená plocha**|Umožňuje počítači přistupovat k jiným počítačům pomocí vzdálené plochy.|
|**Vzdálená správa protokolu událostí**|Umožňuje vzdálené zobrazení a správu protokolů událostí klienta. Toto nastavení využívá pojmenované kanály a rozhraní RPC.|
|**Vzdálená správa naplánovaných úloh**|Umožňuje vzdálenou správu služby plánování úloh. Toto nastavení využívá protokol RPC.|
|**Vzdálená správa služeb**|Umožňuje vzdálenou správu místních služeb na klientech. Toto nastavení využívá pojmenované kanály a rozhraní RPC.|
|**Vzdálená správa svazků**|Umožňuje vzdálenou softwarovou a hardwarovou správu svazku disku. Toto nastavení využívá protokol RPC.|
|**Směrování a vzdálený přístup**|Umožňuje příchozí připojení VPN a připojení se vzdáleným přístupem k počítačům.|
|**Protokol SSTP**|Umožňuje příchozí připojení VPN ke spravovaným počítačům pomocí protokolu SSTP (Secure Socket Tunneling Protocol). Toto nastavení využívá protokol HTTPS.|
|**Zachytávání pro službu SNMP**|Umožňuje spravovaným počítačů příjem přenosů služby depeší protokolu SNMP.|
|**Architektura UPnP**|Konfiguruje službu Architektura UPnP na počítačích, aby mohly zjišťovat a používat certifikovaná zařízení UPnP.|
|**Služba registrace názvu počítače pro Centrum spolupráce**|Umožňuje počítačům najít další počítače a komunikovat s nimi pomocí protokolu PNRP (Peer Name Resolution Protocol). Toto nastavení využívá protokol SSDP a PNRP.|
|**Windows Media Player**|Umožňuje uživatelům přijímat multimédia streamovaná přes UDP.|
|**Služba Windows Media Player Network Sharing**|Umožňuje uživatelům sdílet multimédia přes síť. Toto nastavení používá síťové protokoly SSDP, qWave a UPnP.|
|**Služba Windows Media Player Network Sharing (Internet)**<br>(Windows 7 nebo novější)|Umožňuje uživatelům sdílet domácí multimédia prostřednictvím internetu.|
|**Centrum spolupráce**|Umožňuje uživatelům spolupracovat přes síť a sdílet tak dokumenty, programy nebo plochy. Toto nastavení používá službu DFSR a P2P.|
|**Základ spolupráce rovnocenných počítačů**|Konfiguruje různé programy a technologie peer-to-peer, aby se mohly připojit. Toto nastavení využívá protokol SSDP a PNRP.|
|**Vzdálená správa systému Windows (režim kompatibility)**|Umožňuje vzdálenou správu spravovaných počítačů pomocí služby vzdálené správy systému Windows (WS-Management), což je protokol založený na webových službách pro vzdálenou správu operačních systémů a zařízení.|
|**Vzdálená správa systému Windows**<br>(Windows 8 nebo novější)|Umožňuje vzdálenou správu spravovaných počítačů pomocí služby vzdálené správy systému Windows (WS-Management), což je protokol založený na webových službách pro vzdálenou správu operačních systémů a zařízení.|
|**Windows Virtual PC**<br>(Windows 7 nebo novější)|Umožňuje virtuálním počítačům komunikovat s dalšími počítači.|
|**Bezdrátová přenosná zařízení**|Umožňuje přenos multimediálních souborů z fotoaparátu nebo multimediálního zařízení připojeného k síti do spravovaných počítačů pomocí protokolu MTP (Media Transfer Protocol). Toto nastavení používá síťové protokoly SSDP a UPnP.|

### Související témata
[Zásady ochrany počítačů se systémem Windows](policies-to-protect-windows-pcs-in-microsoft-intune.md)



<!--HONumber=Jul16_HO3-->


