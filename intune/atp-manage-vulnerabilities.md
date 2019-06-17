---
title: Použijte Intune k nápravě ohrožení zabezpečení zjištěných aplikací Microsoft Defender ATP – Azure | Dokumentace Microsoftu
description: Zjistit, jak spravovat úlohy zabezpečení a hrozeb & ohrožení zabezpečení správy, část z Microsoft Defender Advanced Threat Protection (ATP) z konzoly Intune.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 05/17/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: aa6dfef745157ae96736f8405fd5cafc33d4335f
ms.sourcegitcommit: 4b83697de8add3b90675c576202ef2ecb49d80b2
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/13/2019
ms.locfileid: "67045287"
---
# <a name="use-intune-to-remediate-vulnerabilities-identified-by-microsoft-defender-atp"></a>Použijte k nápravě chyby zabezpečení identifikované pomocí ochrany ATP v programu Defender Microsoft Intune  

Při integraci Intune s Microsoft Defender Advanced Threat Protection (ATP), můžete využít výhod ATPs hrozby a ohrožení zabezpečení správy (TVM) a použijte k nápravě slabé stránky koncový bod identifikován TVM Intune. Tato integrace přináší přístup na základě rizik pro zjišťování a stanovení priority ohrožení zabezpečení, která může zlepšit dobu odezvy nápravy napříč vaším prostředím.  

[Správa ohrožení zabezpečení a hrozeb](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/next-gen-threat-and-vuln-mgt) je součástí [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection).  

## <a name="how-integration-works"></a>Jak funguje integrace  

Po připojení Intune k Microsoft Defender Advanced Threat Protection ochrany ATP v programu obdrží podrobnosti hrozby a ohrožení zabezpečení ze spravovaných zařízení.  

Ochrana ATP v programu jako správce zabezpečení v konzole Windows Defender Security Center zkontrolujte data o ohrožení zabezpečení koncového bodu. Správce pak použít jedním kliknutím k vytvoření úloh zabezpečení, které příznak zranitelných zařízení pro nápravu. Zabezpečení úloh jsou okamžitě předány do konzoly Intune kde správci Intune mohou zobrazit. Úloha zabezpečení jsou uvedeny typy ohrožení zabezpečení, priority, stavu a kroků provést k nápravě ohrožení zabezpečení. Správce Intune rozhodne následně přijímal nebo odmítal úkolu.  

Úkol je přijat, správce Intune pak funguje k nápravě ohrožení zabezpečení, ale Intune, používání doprovodné materiály zabezpečení úloh v rámci.  

Běžné akce na odstranění problému, zahrnují:  
- **Blok** spuštění aplikace  
- **Nasazení** aktualizací operačního systému pro zmírnění chyby zabezpečení.  
- **Upravit** hodnotu registru.  
- **Zakázat** nebo **povolit** konfiguraci, kterou chcete mít vliv na ohrožení zabezpečení.  
- **Vyžadují pozornost** upozorní správce, aby hrozby, když neexistuje žádné vhodné doporučení k poskytování.  

Příklad pracovního postupu:  
- V rámci ochrany ATP v programu Defender Microsoft zjišťuje ohrožení zabezpečení pro aplikaci s názvem Contoso Media Player v4 a správce, vytvoří se úkol zabezpečení k aktualizaci této aplikace. Contoso Media player je nespravované aplikace, která byla nasazena s Intune.  

  Tato úloha zabezpečení se zobrazí v konzole Intune se stavem čeká na vyřízení:  
  ![Zobrazení seznamu úloh zabezpečení v konzole Intune](./media/atp-manage-vulnerabilities/temp-security-tasks.png)
 
- Správce Intune vybere zabezpečení úloh k zobrazení podrobností o úloze.  Správce potom vybere **přijmout**, která aktualizuje stav v Intune a ochrana ATP v programu bude *přijato*.  
  ![Následně přijímal nebo odmítal zabezpečení úloh](./media/atp-manage-vulnerabilities/temp-accept-task.png) 
 
- Správce pak opraví úloh podle pokynů.  Pokyny se liší v závislosti na typu nápravu, který je nezbytný. Pokud je k dispozici, obsahuje pokyny k nápravě odkazy, které se otevřou příslušné podokna pro konfigurace Intune. 

  Vzhledem k tomu, že na Windows media player v tomto příkladu není spravovanou aplikaci, Intune můžete poskytnout pokyny. Pokud se aplikace spravovanou, Intune může poskytují pokyny ke stažení aktualizovanou verzi a odkaz k otevření nasazení pro aplikaci tak, aby aktualizované soubory mohou být přidány do nasazení. 

- Po opravě nastaví na dokončení správce Intune se otevře zabezpečení úloh a vybere **dokončit úkol**.  Stav nápravy aktualizuje Intune a ochrana ATP v programu, kde jako správce zabezpečení potvrdit upravený stav chyby.  

## <a name="prerequisites"></a>Požadavky  

**Předplatná**:  
- Microsoft Intune  
- Microsoft Defender Advanced Threat Protection ([zaregistrujte si bezplatnou zkušební verzi](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-main-abovefoldlink).)  

**Konfigurace Intune pro ochrany ATP v programu**:  
- Konfigurace připojení služeb pomocí ochrany ATP v programu Defender Microsoft.  
- Nasazení zásad dodržování předpisů pro zařízení s typem profilu **Microsoft Defender ATP (Windows 10 Desktop)** na zařízení, která bude mít rizika hodnoceno ochrany ATP v programu.
  Informace o tom, jak nastavit Intune pro práci s ochrany ATP v programu najdete v tématu [vynucování dodržování předpisů pro Microsoft Defender ATP s podmíněným přístupem v Intune](https://docs.microsoft.com/intune/advanced-threat-protection#enable-windows-defender-atp-in-intune).  

## <a name="work-with-security-tasks"></a>Práce s úlohami zabezpečení  

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973) a přejděte na **zabezpečení zařízení** > **zabezpečení úloh**.  
2. Vyberte úlohu ze seznamu a otevřete okno prostředků, které se zobrazí další podrobnosti pro tuto úlohu zabezpečení.  
3. Při zobrazení okna prostředků zabezpečení úloh, můžete vybrat další odkazy:  
   - SPRAVOVANÉ aplikace – zobrazení aplikace, která je ohrožen. Pokud tuto chybu zabezpečení platí pro několik aplikací, zobrazí se vám filtrovaný seznam aplikací.  
   - ZAŘÍZENÍ – zobrazení seznamu *zranitelných zařízení*, ze které můžete propojit prostřednictvím další podrobnosti pro tuto chybu zabezpečení na tomto zařízení.  
   - ŽADATEL – použijte tento odkaz Odeslat e-mailu správce, který odeslal tuto úlohu zabezpečení.  
   - Poznámky k – čtení vlastních zpráv odeslaná žadateli při otevírání úlohu zabezpečení.  
4. Vyberte **přijmout** nebo **odmítnout** odeslat oznámení do ochrany ATP v programu pro plánované akce. Když přijmout nebo odmítnout úlohu, můžete odeslat poznámky, které se odesílají do ochrany ATP v programu.  

5. Po přijetí úlohu znovu otevřít zabezpečení úloh (Pokud je uzavřený) a postupujte podle podrobnosti o NÁPRAVĚ náprava ohrožení zabezpečení.  Pokynů z ochrany ATP v programu v podrobnostech o úloze zabezpečení se liší v závislosti na tuto chybu zabezpečení.  

   Pokud je to možné, Uděláte to tak, pokyny k nápravě zahrnovat odkazy, které otevírají objekty položky konfigurace v konzole Intune.  

6. Po dokončení nápravných kroků, otevřete úlohu zabezpečení a vyberte **dokončit úkol**.  Tato akce aktualizuje stav zabezpečení úloh v Intune a ochrana ATP v programu.  

Po úspěšné nápravě lze přetáhnout skóre rizika vystavení v ochrany ATP v programu, založené na nové informace z opravená zařízení. 

## <a name="next-steps"></a>Další kroky
Další informace o Intune a [ochrany ATP v programu Defender Microsoft](https://docs.microsoft.com/intune/advanced-threat-protection)  
Projděte si Intune [Mobile Threat Defense](https://docs.microsoft.com/intune/mobile-threat-defense)  
Zkontrolujte [řídicí panel Správa ohrožení zabezpečení a hrozeb](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/tvm-dashboard-insights) v ochraně ATP v programu Defender Microsoft
