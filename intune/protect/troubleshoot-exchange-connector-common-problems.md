---
title: Řešení běžných potíží s Intune Exchange Connectorem
titleSuffix: Microsoft Intune
description: Řešení potíží a řešení běžných potíží s místními Microsoft Intune Exchange Connector
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 10/02/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 4219d9d4f7d7e8c56acc218d16d8277ed2cf3821
ms.sourcegitcommit: f04e21ec459998922ba9c7091ab5f8efafd8a01c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71817535"
---
# <a name="resolve-common-problems-for-the-intune-exchange-connector"></a>Řešení běžných problémů s Intune Exchange Connectorem
 
Tento článek vám může pomáhat správci Intune vyřešit běžné problémy s provozem Intune Exchange Connectoru.  

Než budete pokračovat, přečtěte si téma řešení potíží s místním Exchange Connectorem služby Intune pro základní informace o konektoru před zahájením odstraňování potíží a běžné problémy pro konfiguraci konektoru. 

## <a name="exchange-activesync-device-not-discovered-from-exchange"></a>Zařízení Exchange ActiveSync nebylo zjištěno ze systému Exchange

[Sledujte aktivitu Exchange Connector](exchange-connector-install.md#on-premises-intune-exchange-connector-high-availability-support) a zjistěte, jestli se konektor Exchange Connector synchronizuje se serverem Exchange. Pokud se po připojení zařízení úspěšně dokončila Úplná synchronizace nebo rychlá synchronizace, můžete vyhledat další možné problémy, které jsou uvedené dál. Pokud se neuskuteční žádná synchronizace, Shromážděte protokoly synchronizace a připojte je k žádosti o podporu.  

- Ujistěte se, že uživatelé mají licenci Intune, jinak konektor Exchange Connector nezjistí jejich zařízení.  

- Pokud se primární adresa SMTP uživatele liší od hlavního názvu uživatele (UPN) ve službě Azure Active Directory (Azure AD), Exchange Connector nezjistí žádná zařízení pro tohoto uživatele. Pokud chcete tento problém vyřešit, opravte primární adresu SMTP.  

- Pokud ve vašem prostředí máte servery poštovních schránek Exchange 2010 i Exchange 2013, doporučujeme, abyste odkazovali na Exchange Connector na Exchange 2013 Server pro přístup klienta (CAS). V opačném případě, pokud je Exchange Connector nastavený tak, aby komunikoval s certifikačními autoritami Exchange 2010, Exchange Connector nezjistí žádná zařízení uživatelů Exchange 2013.  

- V případě vyhrazeného prostředí Exchange Online je nutné, aby byl konektor Exchange Connector na servery Exchange 2013 CAS (nikoli CAS Exchange 2010) ve vyhrazeném prostředí během počáteční instalace, protože konektor bude při spuštění komunikovat pouze s těmito certifikačními autoritami. Rutiny PowerShellu.  


## <a name="problems-with-the-notification-email-message"></a>Problémy s e-mailovou zprávou s oznámením  

Aby bylo možné podporovat zařízení s Androidem, která nejsou Knox pro přístup k místním poštovním schránkám, musí se registrace v Intune spouštět z e-mailové zprávy "Začínáme nyní" odeslané konektorem Intune Exchange. Při spuštění registrace ze zprávy se zajistí, že zařízení bude přijímat jedinečné ActiveSyncID napříč všemi platformami (Exchange, Azure AD, Intune).  

K dispozici je několik důvodů, proč uživatel nemusí dostávat e-mailovou zprávu s oznámením:  

- Účet oznámení není nastavený správně.
- Pro účet oznámení se automatická konfigurace nezdařila.
- Požadavek EWS k odeslání e-mailové zprávy se nezdařil.

K řešení potíží s e-mailovými oznámeními použijte následující postup.

### <a name="review-the-notification-account-thats-used-to-retrieve-autodiscover-settings"></a>Zkontrolujte účet oznámení, který se používá k načtení nastavení konfigurace.
1. Ujistěte se, že služba automatické konfigurace a webové služby systému Exchange jsou nakonfigurovány ve službách Exchange Client Access. Další informace najdete v tématu [služby pro klientský přístup](https://docs.microsoft.com/Exchange/architecture/client-access/client-access).

   Další informace najdete v tématu [Služba automatické konfigurace v systému Exchange Server](https://docs.microsoft.com/Exchange/architecture/client-access/autodiscover?view=exchserver-2019).


2. Ověřte, že váš účet oznámení splňuje následující požadavky:

   - Účet má aktivní poštovní schránku, která je hostovaná na místním serveru Exchange.  

   - Hlavní název uživatele (UPN) účtu se shoduje s adresou SMTP.

3. Aby automatická práce fungovala, musí mít server DNS záznam DNS pro **Autodiscover.SMTPdomain.com** (například Autodiscover.contoso.com), který odkazuje na server Exchange Client Access. Chcete-li ověřit, zda záznam existuje, proveďte následující kroky a zadáním plně kvalifikovaného názvu domény místo *Autodiscover.SMTPdomain.com*:

   1. Na příkazovém řádku zadejte příkaz **nslookup**a potom stiskněte klávesu ENTER.  

   2. Zadejte **Autodiscover.SMTPdomain.com**a potom stiskněte klávesu ENTER.

      Výstup by měl vypadat podobně jako na následujícím obrázku:  
      ![Výsledky nástroje Nslookup](./media/troubleshoot-exchange-connector-common-problems/nslookup-results.png
)

   Službu Automatická konfigurace můžete také otestovat z Internetu na https://testconnectivity.microsoft.com/ nebo z místní domény pomocí nástroje Microsoft Connectivity Analyzer. Další informace najdete v tématu [Nástroj Microsoft Connectivity Analyzer](https://docs.microsoft.com/en-us/previous-versions/office/exchange-remote-connectivity/jj851141(v=exchg.80)). Stáhněte si [Nástroj Microsoft Connectivity Analyzer](http://go.microsoft.com/fwlink/?LinkID=313782).


### <a name="review-autodisocvery"></a>Zkontrolovat Autodisocvery  

Pokud se automatická konfigurace nezdařila, zkuste provést následující kroky:
1. [Nakonfigurujte platný záznam DNS konfigurace](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/mt473798(v=exchg.150)). 

2. V konfiguračním souboru Intune Exchange Connectoru zakódovat adresu URL služby EWS, a to následujícím způsobem:

   1. Určete adresu URL EWS. Výchozí adresa URL služby EWS pro Exchange je **https://<mailServerFQDN>/EWS/Exchange. asmx**, i když se to může lišit. Obraťte se na správce Exchange a ověřte správnou adresu URL vašeho prostředí.

   2. Upravte soubor **OnPremisesExchangeConnectorServiceConfiguration. XML** . Ve výchozím nastavení se soubor nachází v **%ProgramData%\Microsoft\Windows Intune Exchange Connectoru** na počítači, na kterém je spuštěný konektor Exchange. Otevřete soubor pomocí textového editoru a pak změňte následující řádek tak, aby odrážel adresu URL služby EWS pro vaše prostředí: `<ExchangeWebServiceURL> https://<YourExchangeHOST>/EWS/Exchange.asmx</ExchangeWebServiceURL>`
    

3. Uložte soubor a restartujte počítač nebo restartujte službu Microsoft Intune Exchange Connector.

>[!NOTE]
> V této konfiguraci Intune Exchange Connector přestane používat funkci automatického připojení a místo toho se připojí přímo k adrese URL EWS.

## <a name="next-steps"></a>Další kroky  

Následující článek vám může pomáhat vyřešit konkrétní chyby:
- [Řešení běžných chyb pro Intune Exchange Connector](troubleshoot-exchange-connector-common-errors.md)

Vyhledejte pomoc od podpory nebo komunity Intune.
- V tématu [získání podpory](../fundamentals/get-support.md) pro používání konzoly Intune můžete pomoct s řešením problému nebo otevřít případ podpory s Microsoftem. 
- Vystavte svůj problém ve [fórech Microsoft Intune](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).  
