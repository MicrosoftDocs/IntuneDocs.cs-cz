---
title: Řešení potíží s klientským nastavením
description: Řešení obecných potíží s instalací klientů
keywords: ''
author: nathbarn
ms.author: nathbarn
manager: dougeby
ms.date: 02/22/2017
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: e46d292b-1d16-46db-a87f-d53eefa4d22a
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 39c0b0997bdbf229064e6b5ef25ab559b9252f83
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31028074"
---
# <a name="troubleshoot-client-setup-in-microsoft-intune"></a>Řešení potíží s instalací klientů v Microsoft Intune

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Při odstraňování běžných problémů s instalací klientů vám můžou pomoct následující informace. Pokud tyto informace váš problém nevyřeší, přečtěte si téma [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md), ve kterém najdete další způsoby, jak získat nápovědu.

## <a name="client-installation-fails"></a>Instalace klienta selhala

-   Pokud [konzola pro správu Microsoft Intune](https://manage.microsoft.com/) nezobrazuje pro příslušný počítač žádné výstrahy týkající se nasazení klientského softwaru, zkontrolujte připojení počítače k internetu a konfiguraci proxy serveru a ujistěte se, že počítač může se službou komunikovat na adrese URL [https://manage.microsoft.com](https://manage.microsoft.com/). Pak zkuste klientský software nainstalovat znova.

-   Konfigurací pravidla oznámení v pracovním prostoru **Správce** můžete zajistit, aby se v případě výstrahy týkající se chyby nasazení klientského softwaru odeslal vybraným příjemcům e-mail. Další informace najdete v tématu [Upozorňování pomocí výstrah služby Microsoft Intune](/intune-classic/deploy-use/get-notified-by-alerts).

-   Pokud se nepovede klientský software nasadit, zobrazí Intune kritickou výstrahu **Chyba nasazení klientského softwaru**. Bude se zobrazovat na stránce **Přehled systému** a na stránkách **Výstrahy** [konzoly pro správu Microsoft Intune](https://manage.microsoft.com/). Zde je postup kontroly výstrah:

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com/) zvolte **Výstrahy** &gt; **Přehled**.

2.  Na stránce **Přehled výstrah** najdete tyto informace:

    -   První tři výstrahy, které se dají řadit podle data, kategorie nebo závažnosti

    -   Celkový počet aktivních výstrah

3.  Zvolením **Všechny výstrahy** zobrazíte na stránce **Výstrahy** následující informace. Jako první se zobrazují kritické výstrahy:

    -   **Název** – název typu generované výstrahy.

    -   **Zdroj** – odkaz na zdroj výstrahy.  Pokud je prahová hodnota pro zobrazení tohoto typu výstrahy nastavená na **Vše**, zobrazí tento odkaz jedno zařízení, kterého se výstraha týká.  Když je prahová hodnota pro zobrazení tohoto typu výstrahy nastavená na nějakou hodnotu, zobrazí tento odkaz seznam všech zařízení, kterých se tato výstraha týká.

    -   **Poslední aktualizace** – ukazuje čas poslední změny výstrahy. Pokud je výstraha zavřená, zobrazuje se čas zavření výstrahy.

    -   **Závažnost** – označuje závažnost výstrahy.

## <a name="computer-enrollment-package-doesnt-download"></a>Registrační balíček počítače se nestahuje
**Problém:** Při pokusu o registraci počítače došlo k následujícímu:
-  Registrační balíček se nestahuje.
-  Dialogové okno stažení se zobrazí, ale vyprší jeho platnost.

**Řešení:** V prohlížeči, který používáte ke stažení, v době, kdy stahování probíhá, zajistěte, že jsou povolena stahování a že šifrované soubory lze uložit na místní disk.

## <a name="client-installation-hangs-with-error-code-0x80040154"></a>Instalace klienta přestane reagovat s kódem chyby 0x80040154
**Problém:**

-  Instalace klienta během registrace přestane reagovat

-  Nelze registrovat zařízení

-  Chyba 0x80040154 v souboru WindowsUpdate.log

Může to být způsobeno absencí důležitých aktualizací softwaru v počítači.

**Řešení:** Ujistěte se, že vaše zásady aktualizace softwaru umožňují instalaci kritických aktualizací, jak je popsáno v tématu [Udržování počítačů s Windows v aktuálním stavu díky softwarovým aktualizacím v Microsoft Intune](/intune-classic/deploy-use/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune).


## <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a>Chyby související se zásadami Microsoft Intune v souboru policyplatform.log
U zařízení s Windows nespravovaných pomocí MDM můžou být chyby zásad v souboru policyplatform.log výsledkem jiného než výchozího nastavení nástroje Řízení uživatelských účtů v systému Windows (UAC) v zařízení. Některá nevýchozí nastavení UAC můžou ovlivnit zpracování zásad a instalace klientů Microsoft Intune.

### <a name="to-resolve-uac-issues"></a>Řešení potíží s UAC

1.  Vyřaďte počítač, jak je popsáno v tématu [Vyřazení dat a zařízení ze správy službou Microsoft Intune](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).

2.  Počkejte 20 minut, než se odebere klientský software.

    > [!NOTE]
    > Nepokoušejte se klienta odebrat pomocí panelu Programy a funkce.

3.  V nabídce Start zadejte **UAC**. Otevře se nastavení nástroje Řízení uživatelských účtů.

4.  Nastavte posuvník oznámení na výchozí nastavení.

## <a name="what-to-do-if-the-client-will-not-uninstall-from-the-microsoft-intune-administrator-console"></a>Co dělat, když se klient z konzoly pro správu Microsoft Intune neodinstaluje

### <a name="to-remove-the-client-software-by-using-the-microsoft-intune-command-line-tool"></a>Odebrání klientského softwaru pomocí nástroje příkazového řádku Microsoft Intune

1.  Otevřete příkazový řádek v režimu správce.

2.  Přejděte do složky *%programfiles%\Microsoft\OnlineManagement\Common*.

3.  Spusťte následující příkaz ``ProvisioningUtil.exe /UninstallAgents /MicrosoftIntune``

## <a name="client-installation-error-codes"></a>Kódy chyb instalace klientů
Kódy chyb, které se zobrazují na stránce **Výstrahy** , když se instalace klientského softwaru nepovede, popisuje následující tabulka. Obsahuje taky návrhy, jak příslušný problém vyřešit.


|                                                                   Kód chyby                                                                    |                                                          Možný problém                                                          |                                                                                                                                                                                                Navržené řešení                                                                                                                                                                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                           <strong>0x80CF0437</strong>                                                           |                                  Na hodinách klientského počítače není nastavený správný čas.                                  |                                                                                                                                                    Zkontrolujte, jestli jsou na klientském počítači správně nastavené hodiny a časové pásmo.                                                                                                                                                     |
|                              <strong>0x80240438</strong>, <strong>0x80CF0438</strong>, <strong>0x80CF401B</strong>                              |                               Nedá se připojit ke službě Intune. Zkontrolujte nastavení proxy serveru klienta.                               |                   Ověřte, že Intune konfiguraci proxy serveru na klientském počítači podporuje a že má klientský počítač přístup na internet. Další informace o podporovaných konfiguracích proxy serveru najdete v tématu [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune).                    |
|                                                           <strong>0x80CF402C</strong>                                                           |                                 Nedá se připojit ke službě Intune. Zkontrolujte připojení k síti.                                  |                                                                                                                                                   Ověřte, že je počítač připojený k síti. Zkontrolujte, jestli je připojený síťový kabel, případně jestli je zapnutá bezdrátová síť.                                                                                                                                                    |
|                                                     <strong>0x80240438, 0x80CF0438</strong>                                                     |                              Není nakonfigurované nastavení proxy serveru v Internet Exploreru a v místním systému.                              | Zkontrolujte nastavení proxy serveru klienta a ověřte, že Intune konfiguraci proxy serveru na klientském počítači podporuje a že má klientský počítač přístup na internet. Další informace o podporovaných konfiguracích proxy serveru najdete v tématu [Pomoc se zabezpečením počítačů s Windows pomocí služby Endpoint Protection pro Microsoft Intune](/intune-classic/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune). |
|                                                           <strong>0x80043001</strong>                                                           |                                                 Registrační balíček je zastaralý.                                                 |                                                                     Z pracovního prostoru <strong>Správce</strong> si stáhněte aktuální balíček klientského softwaru a nainstalujte ho. Pokyny najdete v tématu [Instalace klienta na počítači s Windows pomocí Microsoft Intune](/intune-classic/deploy-use/install-the-windows-pc-client-with-microsoft-intune).                                                                      |
|                                                           <strong>0x80043004</strong>                                                           |                                            Předplatné neexistuje nebo je deaktivované.                                            |                                                                                                   Ověřte, že je váš účet a předplatné Intune pořád aktivní. Pokud si chcete prohlédnout nastavení svého účtu, přihlaste se k němu v [centru pro správu Office 365](http://go.microsoft.com/fwlink/?LinkId=698854%20).                                                                                                   |
|                                                           <strong>0x80043002</strong>                                                           |                                                  Účet je v režimu údržby.                                                   |                                                                                             Když je účet v režimu údržby, nemůžete registrovat nové klientské počítače. Pokud si chcete prohlédnout nastavení svého účtu, přihlaste se k němu v [centru pro správu Office 365](http://go.microsoft.com/fwlink/?LinkId=698854%20).                                                                                              |
|                                                           <strong>0x80043003</strong>                                                           |                                                        Účet je odstraněný.                                                         |                                                                                                                                            Ověřte, že je váš účet a předplatné Intune pořád aktivní. Pokud si chcete prohlédnout nastavení svého účtu, přihlaste se k němu.                                                                                                                                             |
|                                                           <strong>0x80043005</strong>                                                           |                                                  Klientský počítač je vyřazený.                                                   |                                                                  Pár hodin počkejte, odeberte z počítače všechny starší verze klientského softwaru s pak zkuste nainstalovat klientský software znova. Pokyny najdete výš v části <strong>Co dělat, když se klient z konzoly pro správu Microsoft Intune neodinstaluje</strong>.                                                                  |
|                                                           <strong>0x80043006</strong>                                                           |                                  Bylo dosaženo maximálního počtu licencí povolených pro účet.                                   |                                                                                                                                                    Abyste mohli ve službě zaregistrovat víc klientských počítačů, musí si vaše organizace koupit další licence.                                                                                                                                                     |
|                                                           <strong>0x80043007</strong>                                                           |                          Ve složce s instalačním programem se nenašel soubor certifikátu.                          |                                 Než začnete s instalací, extrahujte všechny soubory. Žádné extrahované soubory nepřejmenovávejte ani nepřemísťujte: všechny soubory musí být ve stejné složce, jinak se instalace nepovede. Další informace najdete v tématu [Instalace klienta na počítači s Windows pomocí Microsoft Intune](/intune-classic/deploy-use/install-the-windows-pc-client-with-microsoft-intune).                                  |
| <strong>0x8024D015</strong>, <strong>0x00240005</strong>, <strong>0x80070BC2</strong>, <strong>0x80070BC9</strong>, <strong>0x80CFD015</strong> |                       Software nejde nainstalovat, protože se čeká na restartování klientského počítače.                        |                                                                                                                                                                        Restartujte počítač a pak zkuste nainstalovat klientský software znova.                                                                                                                                                                        |
|                                                           <strong>0x80070032</strong>                                                           |                Na klientském počítači se nenašel nejmíň jeden softwarový produkt, který je podmínkou pro instalaci klientského softwaru.                 |                            Ujistěte se, že jsou na klientském počítači nainstalované všechny požadované aktualizace, a pak zkuste nainstalovat klientský software znova. Další informace o požadavcích pro instalaci klientského softwaru najdete v tématu [Požadavky na síťovou infrastrukturu pro Microsoft Intune](/intune-classic/get-started/network-infrastructure-requirements-for-microsoft-intune).                             |
|                                                           <strong>0x80043008</strong>                                                           |                                  Nešlo spustit službu Microsoft Online Management Updates.                                  |                                                                                                                                               Kontaktujte podporu podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).                                                                                                                                                |
|                                                           <strong>0x80043009</strong>                                                           |                                     Klientský počítač je ve službě už zaregistrovaný.                                      |                                                                                        Abyste mohli klientský počítač ve službě zaregistrovat znovu, musíte ho nejdřív vyřadit. Pokyny najdete v tématu [Vyřazení dat a zařízení ze správy službou Microsoft Intune](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).                                                                                         |
|                                                           <strong>0x8004300A</strong>                                                           |  (Fáze 21) Dojde k chybě při nasazení registračního balíčku na objekt zásad skupiny za účelem instalace v oboru uživatele, nikoli v oboru počítače.   |                                                               Zkontrolujte, jestli je objekt zásad skupiny prostřednictvím GPSI správně zaměřený na obor počítače. Příspěvky na toto téma najdete na tomto [fóru TechNet](https://social.technet.microsoft.com/Forums/en-US/bb9fa71c-c132-4954-abb0-70be8acbd925/failed-to-install-windows-intune?forum=microsoftintuneprod).                                                                |
|                                                           <strong>0x8004300B</strong>                                                           | Instalační balíček klientského softwaru nejde spustit, protože verze Windows, která běží na klientovi, není podporovaná. |                                                               Intune nepodporuje verzi Windows, která běží na klientském počítači. Seznam podporovaných operačních systémů najdete v tématu [Požadavky na síťovou infrastrukturu pro Microsoft Intune](/intune-classic/get-started/network-infrastructure-requirements-for-microsoft-intune).                                                               |
|                                                             <strong>0xAB2</strong>                                                              |                           Instalační služba systému Windows nemohla získat přístup k modulu VBScript runtime pro vlastní akci.                            |                                                      Tato chyba je způsobená nějakou vlastní akcí založenou na dynamických knihovnách DLL (Dynamic-Link Library). Při odstraňování problémů s knihovnou DLL budete nejspíš muset použít nástroje popsané v [článku 198038 znalostní báze podpory Microsoftu: Užitečné nástroje při problémech s balíčky a nasazením](http://go.microsoft.com/fwlink/?LinkID=234255).                                                       |
|                                                           <strong>0x8004300f</strong>                                                           |           Software se nedá nainstalovat, protože už je nainstalovaný klient nástroje System Center Configuration Manager.            |                                                                                                                                                              Odeberte klienta nástroje Configuration Manager a pak zkuste nainstalovat klientský software znova.                                                                                                                                                               |
|                                                           <strong>0x80043010</strong>                                                           |      Software se nedá nainstalovat, protože už je nainstalovaný klient OMADM (Open Mobile Alliance Device Management).      |                                                                                                                                                                     Zrušte registraci klienta OMADM a pak zkuste nainstalovat klientský software znova.                                                                                                                                                                     |

Pokud problémy instalace potrvají, kontaktujte podporu podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md). Je potřeba mít připravený protokol o registraci klientského počítače (najdete ho tady: %*programfiles*%\Microsoft\OnlineManagement\Logs\Enrollment.log a %*userprofile*%\AppData\Local\Microsoft\OnlineManagement\Logs\Enrollement.log) a protokol služby Windows Update (%*windir*%\windowsupdate.log), abyste ho mohli ukázat technikům podpory.

## <a name="what-to-do-if-endpoint-protection-is-not-uninstalled-when-you-uninstall-the-client"></a>Co dělat, když se při odinstalaci klienta neodinstaluje funkce Endpoint Protection

Může se stát, že po spuštění výše uvedených příkazů zůstane agent Host Protection (Endpoint Protection) nainstalovaný. Pokud k tomu dojde, spusťte tento příkaz z příkazového řádku se zvýšenými oprávněními:

    ```
    "C:\Program Files\Managed Defender\Setup.exe" /x /q /s
    ```


### <a name="next-steps"></a>Další kroky
Pokud vám tyto informace o řešení potíží nepomohly, obraťte se na podporu společnosti Microsoft podle pokynů v tématu [Jak získat podporu pro Microsoft Intune](how-to-get-support-for-microsoft-intune.md).
