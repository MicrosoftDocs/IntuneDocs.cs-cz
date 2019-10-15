---
title: Zásady brány firewall pro počítače s Windows
titleSuffix: Microsoft Intune
description: Intune vám může pomoci zabezpečit počítače, které spravujete, mnoha různými způsoby, včetně pomoci při konfiguraci nastavení brány Windows Firewall.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 01/01/2018
ms.topic: archived
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: 9549c072-ac3d-4d14-a931-a2eda8846217
ms.reviewer: owenyen
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic-keep
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8e5a67ade5f1b3c9efc2674887a042bd828136fa
ms.sourcegitcommit: a2654f3642b43b29ab0e1cbb2dfa2b56aae18d0e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/14/2019
ms.locfileid: "72310751"
---
# <a name="help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune"></a>Ochrana počítačů s Windows pomocí zásad brány Windows Firewall v Microsoft Intune

[!INCLUDE [classic-portal](../../intune-classic/includes/classic-portal.md)]

> [!NOTE]
> Informace v tomto tématu se vztahují jenom na počítače s Windows, které spravujete jako počítače pomocí softwarového klienta Intune. Pokud chcete spravovat nastavení brány firewall pro počítače s Windows zaregistrované jako mobilní zařízení, přečtěte si téma [Přidání nastavení ochrany koncových bodů v Intune](../protect/endpoint-protection-configure.md).

Microsoft Intune vám může přispět k zabezpečení počítačů s Windows, které spravujete pomocí klienta Intune, mnoha různými způsoby. Jedním ze způsobů, jak to dělá, je poskytování zásad, které vám umožní nakonfigurovat nastavení brány Windows Firewall na počítačích.

Pokud jste ještě na svých počítačích nenainstalovali klienta Intune pro počítače s Windows, přečtěte si téma [instalace klienta na počítači s Windows pomocí Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).

Informace v následujících částech vám pomůžou s konfigurací, nasazením a monitorováním zásad brány Windows Firewall na počítačích s Windows.

## <a name="use-intune-policies-to-manage-windows-firewall"></a>Použití zásad Intune ke správě brány Windows Firewall
Zásady brány Windows Firewall umožňují vytvářet a nasazovat nastavení, která řídí bránu Windows Firewall na spravovaných počítačích. Nemůžete spravovat vlastní výjimky pro bránu Windows Firewall a tato nastavení neovlivní brány firewall třetích stran.

> [!NOTE]
> Pokud jsou zásady Microsoft Intune a Zásady skupiny nakonfigurované pro správu stejných nastavení na počítači, přepíše nastavení Zásady skupiny zásady Microsoft Intune. Informace o tom, jak se vyhnout konfliktům mezi zásadami a Zásady skupiny Intune, najdete v tématu [řešení konfliktů zásad objektů zásad skupiny a Microsoft Intune](resolve-gpo-and-microsoft-intune-policy-conflicts.md).
>
> Pokud chcete nasadit nastavení brány Windows Firewall do počítačů se systémem Windows Vista, musíte na tyto počítače nejdřív nainstalovat [opravu hotfix KB971800](https://support2.microsoft.com/kb/971800) .

> [!IMPORTANT]
> Pokud chcete spravovat bránu Windows Firewall pomocí Intune, ujistěte se, že na počítačích, které spravujete, jsou povolené tyto dvě služby:
>
> - Brána Windows Firewall
> - Agent zásad protokolu IPsec

## <a name="configure-a-windows-firewall-policy"></a>Konfigurace zásad brány Windows Firewall

1. V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/)vyberte **zásady** &gt; **Přidat zásadu**.

2. Nakonfigurujte a nasaďte zásady **nastavení brány Windows Firewall** . Můžete použít doporučená nastavení nebo přizpůsobit nastavení. Pokud potřebujete další informace o tom, jak vytvořit a nasadit zásady, Projděte si článek [běžné úlohy správy počítačů s Windows pomocí počítačového klienta Microsoft Intune](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md).

    V následující části jsou uvedené hodnoty, které můžete v zásadách konfigurovat, a také výchozí hodnoty, které se použijí, pokud zásady neupravíte.

Po nasazení zásad brány Windows Firewall můžete zobrazit její stav na stránce **všechny zásady** pracovního prostoru **zásady** .

## <a name="specify-policy-settings-for-windows-firewall"></a>Zadat nastavení zásad pro bránu Windows Firewall

### <a name="turn-on-windows-firewall"></a>Zapnout bránu Windows Firewall

Tato nastavení zásad povolují bránu Windows Firewall na spravovaných počítačích, které jsou:
- Připojeno k doméně (například na pracovišti)
- Připojeno k privátní (důvěryhodné) síti (například k domácí síti)
- Připojeno k nedůvěryhodné veřejné síti (například v kavárně)

Výchozí hodnota pro každé z těchto nastavení je **Ano**, což je nejbezpečnější hodnota.



### <a name="block-all-incoming-connections-including-those-in-the-list-of-allowed-programs"></a>Blokovat všechna příchozí připojení, včetně těch, které jsou uvedeny v seznamu povolených programů

Tato nastavení zásad konfigurují bránu Windows Firewall tak, aby blokovala příchozí síťový provoz na spravovaných počítačích, které jsou:
- Připojeno k doméně (například na pracovišti)
- Připojeno k privátní (důvěryhodné) síti (například k domácí síti)
- Připojeno k nedůvěryhodné veřejné síti (například v kavárně)

Výchozí hodnota pro každé z těchto nastavení je **Ano**, což je nejbezpečnější hodnota.

> [!IMPORTANT]
> Pokud vaše prostředí obsahuje spravované počítače, na kterých běží Windows Vista bez nainstalovaných aktualizací Service Pack, musíte nainstalovat aktualizaci, která je přidružená k [článku 971800](https://go.microsoft.com/fwlink/?LinkId=188405) ve znalostní bázi Microsoft Knowledge Base, nebo zakázat **blokování všech příchozích zpráv.** nastavení zásad připojení v zásadách nasazených do těchto počítačů.

### <a name="notify-the-user-when-windows-firewall-blocks-a-new-program"></a>Upozorní uživatele, když brána Windows Firewall blokuje nový program.

Tato nastavení zásad určují, jestli brána Windows Firewall upozorní uživatele počítače, když blokuje příchozí síťový provoz, když je spravovaný počítač:
- Připojeno k doméně (například na pracovišti)
- Připojeno k privátní (důvěryhodné) síti (například k domácí síti)
- Připojeno k nedůvěryhodné veřejné síti (například v kavárně)

Výchozí hodnota pro každé z těchto nastavení je **Ano**.


### <a name="configure-predefined-exceptions"></a>Konfigurace předdefinovaných výjimek

Můžete nakonfigurovat výjimky, které umožní konkrétní typy síťových přenosů přes bránu firewall bez ohledu na hodnoty, které jste nakonfigurovali dříve. Žádné z těchto nastavení není ve výchozím nastavení nakonfigurováno.

|Název nastavení|Podrobnosti|
|------------------|--------------------|
|**BranchCache – načítání obsahu**<br>(Windows 7 nebo novější)|Umožňuje klientům služby BranchCache pomocí protokolu HTTP načítat obsah z jiných klientů služby BranchCache v režimu distribuované mezipaměti a z hostované mezipaměti v režimu hostované mezipaměti. Toto nastavení využívá protokol HTTP.|
|**BranchCache – klient hostované mezipaměti**<br>(Windows 7 nebo novější)|Umožňuje klientům služby BranchCache používat hostovanou mezipaměť. Toto nastavení využívá protokol HTTPS.|
|**BranchCache – server hostované mezipaměti**|Umožňuje klientům služby BranchCache používat hostovanou mezipaměť ke komunikaci s ostatními klienty. Toto nastavení využívá protokol HTTPS.|
|**BranchCache – zjišťování rovnocenných zařízení**<br>(Windows 7 nebo novější)|Umožňuje klientům služby BranchCache používat protokol WS-Discovery (Web Services Dynamic Discovery) k vyhledání dostupnosti obsahu v místní podsíti.|
|**Ukládání do sdílené mezipaměti BITS**|Umožňuje klientům použít Background Intelligent Transfer Service (BITS) k vyhledání a sdílení souborů uložených v mezipaměti BITS na klientech ve stejné podsíti. Toto nastavení využívá webové služby na zařízeních (WSDAPI) a vzdálené volání procedur (RPC).|
|**Připojení k síťovému projektoru**|Umožňuje uživatelům připojit se k projektorům prostřednictvím drátových nebo bezdrátových sítí a promítat prezentace. Toto nastavení využívá rozhraní WSDAPI.|
|**Základní síťové služby**|Umožňuje klientům používat protokoly IPv4 a IPv6 pro připojení k síťovým prostředkům.|
|**DTC (Distributed Transaction Coordinator)**|Umožňuje spravovaným počítačům koordinovat transakce, které aktualizují prostředky s ochranou transakcí, jako jsou databáze, fronty zpráv nebo souborové systémy.|
|**Sdílení souborů a tiskáren**|Umožňuje uživatelům sdílet místní soubory a tiskárny s dalšími uživateli v síti. Toto nastavení využívá rozhraní NetBIOS, propojování místního vícesměrového překladu názvů (LLMNR), protokolu SMB (Server Message Block) a RPC.|
|**Síť**<br>(Windows 7 nebo novější)|Umožňuje spravovaným počítačům účast v síti domácí skupiny.|
|**Služba iSCSI**|Umožňuje spravovaným počítačům připojení k serverům a zařízením iSCSI.|
|**Služba správy klíčů**|Umožňuje počítat počítače s licenčními podmínkami v podnikovém prostředí.|
|**Zařízení Media Center Extenders**|Povoluje, aby zařízení Media Center rozšířila komunikaci s počítači se systémem Windows Media Center. Toto nastavení využívá protokol SSDP (Simple Service Discovery Protocol) a službu qWave.|
|**Služba Netlogon**|Konfiguruje kanál zabezpečení mezi klienty domény a řadičem domény pro ověřování uživatelů a služeb. Toto nastavení využívá protokol RPC.|
|**Zjišťování sítě**|Umožňuje počítačům zjišťovat jiná zařízení a být zjištěna jinými zařízeními v síti. Toto nastavení používá službu publikování a hostitele zjišťování funkcí a síťové protokoly SSDP, NetBIOS, LLMNR a UPnP.|
|**Výstrahy a protokolování výkonu**|Povolí vzdálenou správu služby Výstrahy a protokolování výkonu. Toto nastavení využívá protokol RPC.|
|**Vzdálená správa**|Umožňuje vzdálenou správu počítače.|
|**Vzdálená pomoc**|Umožňuje uživatelům spravovaných počítačů žádat o vzdálenou pomoc od jiných uživatelů v síti. Toto nastavení využívá protokol SSDP, protokol PNRP (Peer Name Resolution Protocol), Teredo a síťové protokoly UPnP.|
|**Vzdálená plocha**|Umožňuje počítači přistupovat k jiným počítačům pomocí vzdálené plochy.|
|**Vzdálená správa protokolu událostí**|Umožňuje vzdálené zobrazení a správu protokolů událostí klienta. Toto nastavení využívá pojmenované kanály a protokol RPC.|
|**Vzdálená správa naplánovaných úloh**|Umožňuje vzdálenou správu služby plánování úloh. Toto nastavení využívá protokol RPC.|
|**Vzdálená správa služeb**|Umožňuje vzdálenou správu místních služeb na klientech. Toto nastavení využívá pojmenované kanály a protokol RPC.|
|**Vzdálená správa svazků**|Umožňuje vzdálenou softwarovou a hardwarovou správu svazku disku. Toto nastavení využívá protokol RPC.|
|**Směrování a vzdálený přístup**|Umožňuje příchozí připojení VPN a vzdáleného přístupu k počítačům.|
|**Protokol SSL (Secure Socket Tunneling Protocol)**|Umožňuje příchozí připojení VPN ke spravovaným počítačům pomocí protokolu SSTP (Secure Socket Tunneling Protocol). Toto nastavení využívá protokol HTTPS.|
|**Depeše SNMP**|Umožňuje spravovaným počítačům přijímat přenos služby depeší protokolu SNMP (Simple Network Management Protocol).|
|**Architektura UPnP**|Nakonfiguruje službu architektury UPnP na počítačích, aby mohla zjišťovat a používat zařízení s certifikací UPnP.|
|**Služba registrace názvu počítače pro spolupráci ve Windows**|Umožňuje počítačům najít další počítače a komunikovat s nimi pomocí protokolu SSDP a PNRP.|
|**Media Player Windows**|Umožňuje uživatelům přijímat média streamovaná přes protokol UDP (User Datagram Protocol).|
|**Služba Media Player pro sdílení sítě Windows**|Umožňuje uživatelům sdílet média přes síť. Toto nastavení používá síťové protokoly SSDP, qWave a UPnP.|
|**Windows Media Player služba sdílení sítě (Internet)**<br>(Windows 7 nebo novější)|Umožňuje uživatelům sdílet domácí média prostřednictvím Internetu.|
|**Prostor pro schůzky Windows**|Umožňuje uživatelům spolupracovat přes síť a sdílet tak dokumenty, programy a jejich plochy. Toto nastavení využívá službu systém souborů DFS (Distributed File System) Replication (DFSR) a P2P.|
|**Základ spolupráce rovnocenných uzlů Windows**|Konfiguruje různé programy a technologie peer-to-peer, aby se mohly připojit. Toto nastavení využívá protokol SSDP a PNRP.|
|**Vzdálená správa systému Windows (kompatibilita)**|Umožňuje vzdálenou správu spravovaných počítačů s protokolem WS-Management, což je protokol založený na webových službách pro vzdálenou správu operačních systémů a zařízení.|
|**Vzdálená správa systému Windows**<br>(Windows 8 nebo novější)|Umožňuje vzdálenou správu spravovaných počítačů s protokolem WS-Management, což je protokol založený na webových službách pro vzdálenou správu operačních systémů a zařízení.|
|**Virtuální počítač s Windows**<br>(Windows 7 nebo novější)|Umožňuje virtuálním počítačům komunikovat s ostatními počítači.|
|**Bezdrátová přenosná zařízení**|Povolí přenos médií z fotoaparátu nebo mediálního zařízení s povoleným síťovým rozhraním do spravovaných počítačů pomocí protokolu MTP (Media Transfer Protocol). Toto nastavení používá síťové protokoly SSDP a UPnP.|

## <a name="see-also"></a>Další informace najdete v tématech
[Zásady ochrany počítačů s Windows](policies-to-protect-windows-pcs-in-microsoft-intune.md)
