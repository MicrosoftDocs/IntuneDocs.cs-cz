---
title: Sestava šifrování a klíče Bitlockeru v Microsoft Intune
titleSuffix: Microsoft Intune
description: Zobrazit sestavu na stav šifrování zařízení a přístupové klíče pro obnovení Bitlockeru z v rámci portálu Microsoft Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 03/20/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: shpate
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 1c9028d3b8e69c8f20e264f99bd4bf8fda6c9050
ms.sourcegitcommit: 02803863eba37ecf3d8823a7f1cd7c4f8e3bb42c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/09/2019
ms.locfileid: "59423520"
---
# <a name="monitor-bitlocker-and-device-encryption"></a>Monitorování šifrování nástroje BitLocker a zařízení  
Intune nabízí centralizované umístění k identifikaci stav šifrování zařízení s Windows 10 a pomáhá s přístupem důležité informace pro nástroj BitLocker z vašich zařízení, jak se nachází ve službě Azure Active Directory (Azure AD).  

- [Sestavy šifrování (ve verzi Public Preview)](#encryption-report) obsahuje podrobné informace o stavu šifrování a připravenost zařízení. Podrobnosti sestavy můžete identifikovat problémy, které brání v úspěšné šifrování zařízení, která chcete chránit.  
- [Zobrazit podrobnosti o BitLocker (ve verzi Public Preview)](#bitlocker-recovery-keys) , jako je ID klíče a obnovení klíče pro vaše zařízení z portálu Intune.  

## <a name="encryption-report"></a>Sestava šifrování
Sestava šifrování (ve verzi Public Preview) slouží k zobrazení podrobností o stav šifrování zařízení s Windows 10.  

Pokud chcete najít sestavu, přihlaste se k [Intune](https://aka.ms/intuneportal) a přejděte na **konfigurace zařízení**a potom v části *monitorování*vyberte **šifrování sestavu (Preview)**.  

### <a name="prerequisites"></a>Požadavky:
Zobrazit v sestavě šifrování zařízení musí používat Windows verze 1607 nebo novější.  

### <a name="report-details"></a>Podrobnosti sestavy
Sestavě se zobrazuje **název zařízení** pro zařízení s Windows 10 a základní podrobnosti o každém, včetně:  
- **Verze operačního systému** – verze Windows.  
- **Verze čipu TPM** – verze čipu Trusted Platform Module (TPM) na zařízení.  
- **Šifrování připravenosti** – což je hodnocení připravenosti zařízení pro podporu šifrování nástrojem BitLocker. Zařízení může mít stav šifrování *šifrované* i když je šifrování připravenost *není připraven*, protože postrádá čip TPM.  
- **Stav šifrování** – ať už zašifrovaný jednotky operačního systému.  


### <a name="device-encryption-status"></a>Stav šifrování zařízení
Pokud vyberete zařízení, Intune se zobrazí **stav šifrování zařízení** podokně.

V tomto podokně poskytuje následující podrobnosti:  
- **Název zařízení** – název zařízení prohlížíte.  
- **Šifrování připravenosti** – vyhodnocení připravenosti zařízení pro podporu šifrování nástrojem BitLocker. Zařízení může mít stav šifrování *šifrované* i když je šifrování připravenost *není připraven*, protože postrádá čip TPM.  
- **Stav šifrování** – ať už zašifrovaný jednotky operačního systému.  
- **Profily** – seznam *konfigurace zařízení* profily, které platí pro toto zařízení a zahrnuje následující typy profilů a nastavení:  
    - Typ profilu = *Endpoint protection*  
    - Nastavení > šifrování Windows > šifrovat zařízení = *vyžaduje*  

  Tento seznam může být použita při hledání jednotlivé zásady pro kontrolu, přehled stavu profilu označovat potíže s.  

- **Souhrn stavu profilu** – souhrn profily, které se vztahují k tomuto zařízení. Souhrn představuje nejméně uspokojivým podmínku ve všech příslušných profilů. Například pokud se jeden profil způsobí chybu, souhrn stavu profilu se zobrazí *chyba*.  
- **Podrobnosti o stavu** – rozšířené informace o stavu šifrování zařízení. 
  > [!NOTE]  
  > Intune se zobrazují jenom *podrobnosti o stavu* pro zařízení se systémem *aktualizace Windows 10. dubna 2019* nebo novější.
  
  Toto pole zobrazí informace o každé příslušné chyby, kterou lze zjistit. Tyto informace můžete použít k pochopení, proč zařízení nemusí být připravena šifrování.  

  Následují příklady, které Intune můžete sestavu Podrobnosti o stavu:  

   - Zásada Bitlockeru vyžaduje souhlas uživatele ke spuštění nástroje BitLocker Drive Encryption průvodce. spustí šifrování svazku operačního systému, ale neměli souhlas uživatele.  
   - Metoda šifrování svazku operačního systému zadané informace neodpovídají zásad nástroje BitLocker.  
   - Zásady Bitlockeru vyžadují, aby ochrana čipem TPM ochrany svazku operačního systému, ale nepoužívá čip TPM.  
   - Zásady Bitlockeru vyžadují ochranu pouze TPM pro svazek operačního systému, ale ochranou TPM se nepoužívá.  
   - Zásady nástroje BitLocker vyžaduje ochrany TPM + kód PIN pro svazek operačního systému, ale nepoužívá ochranného zařízení TPM + kód PIN.  
   - Zásada Bitlockeru vyžaduje TPM a spouštěcí klíč ochrany svazku operačního systému, ale čip TPM + spuštění ochrany pomocí klíče se nepoužívá.  
   - Zásada Bitlockeru vyžaduje TPM + kód PIN + ochrany klíčů po spuštění pro svazek operačního systému, ale TPM + kód PIN + spuštění ochrany pomocí klíče se nepoužívá.  
   - Svazek s operačním systémem není chráněný.  
   - Zálohování klíče pro obnovení se nezdařilo.  
   - Pevný disk není chráněný.  
   - Metoda šifrování pevnou jednotku neodpovídá zásad nástroje BitLocker.  
   - K šifrování disků, vyžaduje zásad nástroje BitLocker buď uživatele k přihlášení jako správce nebo pokud je zařízení připojená k Azure AD, musí být zásada AllowStandardUserEncryption nastavena na hodnotu 1.  
   - Prostředí Windows Recovery Environment (WinRE) není nakonfigurovaná.  
   - Čip TPM není k dispozici pro nástroj BitLocker, protože není k dispozici, jeho má byla k dispozici v registru nebo je operační systém na vyměnitelné jednotce.  
   - Čip TPM není připraven pro BitLocker.  
   - Síť není k dispozici, které jsou požadovány pro zálohu pro obnovení klíče.  

## <a name="bitlocker-recovery-keys"></a>Obnovení klíče Bitlockeru
Jako verze Public Preview Intune poskytuje přístup okno Azure AD pro nástroj BitLocker, můžete zobrazit ID klíče Bitlockeru a obnovovací klíče pro zařízení s Windows 10 z portálu Intune.  Být přístupné, zařízení musí mít jeho klíče mezi do služby Azure AD. 
1. Přihlaste se k [Intune](https://aka.ms/intuneportal), přejděte na stránku **zařízení** a potom v části *spravovat*vyberte **všechna zařízení**.
2. Vyberte zařízení, ze seznamu a pak v části *monitorování*vyberte **obnovovací klíče – ve verzi Preview**.  
  
Když klíče jsou k dispozici ve službě Azure AD, je k dispozici následující informace:
- ID klíče Bitlockeru
- Obnovovací klíč nástroje BitLocker
- Typ jednotky  

Pokud klíče nejsou ve službě Azure AD, Intune zobrazí *nalezen klíč Bitlockeru ne pro toto zařízení*.  

Informace o nástroj BitLocker je získat pomocí [poskytovatel konfiguračních služeb pro BitLocker](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp) (CSP). Nástroj BitLocker CSP se podporuje na Windows 10 verze 1703 a vyšší a pro Windows 10 Pro verze 1809 a novější. 

## <a name="next-steps"></a>Další postup
Vytvoření [dodržování předpisů zařízením](compliance-policy-create-windows.md) zásady pro zařízení s Windows 10 ke konfiguraci Bitlockeru a šifrování.
