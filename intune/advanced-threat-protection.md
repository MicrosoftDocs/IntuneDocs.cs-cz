---
title: Použití Ochrany ATP v programu Windows Defender v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se, jak komplexně povolit Rozšířenou ochranu před internetovými útoky v programu Windows Defender (ATP), včetně zapnutí ATP v Intune a Centru zabezpečení v programu Windows Defender (portál ATP), dále jak připojit zařízení pomocí konfiguračního profilu ATP, jak vytvořit zásady dodržování předpisů pro zařízení v Intune a zásady podmíněného přístupu Azure AD a jak monitorovat dodržování předpisů zařízeními.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 02/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: abbd226f2b812e1062d56a1d66b3e10bc9d68036
ms.sourcegitcommit: 78ae22b1a7cb221648fc7346db751269d9c898b1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66374083"
---
# <a name="enforce-compliance-for-windows-defender-atp-with-conditional-access-in-intune"></a>Vynucování dodržování předpisů pro Windows Defender ATP s podmíněným přístupem v Intune

Rozšířená ochrana před internetovými útoky v programu Windows Defender (ATP) a Microsoft Intune společně předcházejí porušením zabezpečení a pomáhají omezit dopad těchto porušení na organizaci.

Tato funkce platí pro: Zařízení s Windows 10

Příklad: Někdo pošle uživateli ve vaší organizaci wordový soubor s vloženým škodlivým kódem. Uživatel přílohu otevře a povolí obsah. Spustí se útok se zvýšenými oprávněními. Útočník ho provádí ze vzdáleného počítače na napadeném zařízení, ke kterému získal oprávnění správce. Z tohoto zařízení získá vzdálený přístup i k dalším zařízením uživatele.

Toto porušení zabezpečení může mít dopad na celou organizaci.

Takovýmto událostem porušení zabezpečení dokáže Ochrana ATP v programu Windows Defender zabránit. Centrum zabezpečení v programu Windows Defender (konzola ATP) označí zařízení jako vysoce rizikové a vygeneruje podrobnou sestavu o podezřelé aktivitě. V našem příkladu Ochrana ATP v programu Windows Defender zjistí, že se na zařízení spouští neobvyklý kód, proběhlo zvýšení úrovně oprávnění k procesu, byl vložen škodlivý kód a vytvořilo se podezřelé vzdálené prostředí. Ochrana ATP v programu Windows Defender vám nabídne možnosti, jak hrozbu zmírnit.

Pomocí Intune můžete vytvořit zásady dodržování předpisů, které stanoví přijatelnou úroveň rizika. Pokud zařízení tuto úroveň překročí, je označeno jako zařízení nedodržující předpisy. V kombinaci s podmíněným přístupem Azure Active Directory (AD) je uživateli zablokován přístup k podnikovým prostředkům.

V tomto článku se dozvíte, jak:

- Povolit Intune v ATP a ATP v Intune. Tyto úlohy vytvoří propojení mezi službami Intune a Ochrana ATP v programu Windows Defender. Toto propojení umožní Ochraně ATP v programu Windows Defender zapisovat rizika počítačů pro vaše zařízení v Intune.
- Vytvořit zásady dodržování předpisů v Intune.
- Povolit podmíněný přístup v Azure Active Directory (AD) na zařízeních podle jejich úrovně ohrožení.

## <a name="prerequisites"></a>Požadavky

Abyste mohli používat ATP s Intune, je potřeba mít nakonfigurované a připravené k použití následující komponenty:

- Tenant s licencí pro Enterprise Mobility + Security E3 a Windows E5 (nebo Microsoft 365 Enterprise E5)
- Prostředí Microsoft Intune se zařízeními s Windows 10 [spravovanými v Intune](windows-enroll.md), která jsou zároveň připojená k Azure AD
- [Ochrana ATP v programu Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) a přístup k Centru zabezpečení v programu Windows Defender (portál ATP)

## <a name="enable-windows-defender-atp-in-intune"></a>Povolení Ochrany ATP v programu Windows Defender v Intune

1. Přihlaste se k webu [Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Dodržování předpisů zařízením** > **Windows Defender ATP** > **Otevřít Centrum zabezpečení v programu Windows Defender**.

    ![Výběrem otevřete Centrum zabezpečení v programu Windows Defender.](./media/atp-device-compliance-open-windows-defender.png)

4. V **Centru zabezpečení v programu Windows Defender**:
    1. Zvolte **Nastavení** > **Pokročilé funkce**.
    2. Přepínač pro **připojení Microsoft Intune** přepněte do polohy **Zapnuto**:

        ![Povolení připojení k Intune](./media/atp-security-center-intune-toggle.png)

    3. Vyberte **Uložit předvolby**.

5. Přejděte zpět do Intune > **Dodržování předpisů zařízením** > **Windows Defender ATP**. Nastavte **Připojit zařízení s Windows verze 10.0.15063 a vyšší ke konektoru Windows Defender ATP** na **Zapnuto**.
6. Vyberte **Uložit**.

Tento postup stačí obvykle provést jednou. Takže pokud už ATP v prostředcích Intune povolené máte, není potřeba tento krok opakovat.

## <a name="onboard-devices-using-a-configuration-profile"></a>Připojení zařízení pomocí konfiguračního profilu

Když se koncový uživatel zaregistruje v Intune, můžete pomocí konfiguračního profilu odesílat do zařízení různá nastavení. To platí i pro Ochranu ATP v programu Windows Defender.

Windows Defender obsahuje balíček konfigurace připojení, který s [Ochranou ATP v programu Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) komunikuje: kontroluje soubory, detekuje hrozby a hlásí Ochraně ATP případná rizika.

Když se připojíte, obdrží Intune z Ochrany ATP v programu Windows Defender automaticky vytvořený konfigurační balíček. Jakmile se profil odešle nebo nasadí do zařízení, odešle se do něj i tento balíček. To umožňuje Ochraně ATP v programu Windows Defender monitorovat na zařízení potenciální hrozby.

Jakmile jednou připojíte zařízení pomocí konfiguračního balíčku, už to příště dělat nemusíte. Zařízení můžete připojit také pomocí [skupiny zásad nebo System Center Configuration Manageru (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-windows-defender-advanced-threat-protection).

### <a name="create-the-configuration-profile"></a>Vytvoření konfiguračního profilu

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **Název** a **Popis**.
4. V části **Platforma** vyberte **Windows 10 a novější**.
5. Jako **Typ profilu** zvolte **Rozšířená ochrana před internetovými útoky v programu Windows Defender (Windows 10 Desktop)** .
6. Nakonfigurujte nastavení:

  - **Typ balíček konfigurace klienta ochrany ATP v programu Windows Defender**: Vyberte **připojení** chcete do profilu přidat konfigurační balíček. Výběrem možnosti **Zrušit zprovoznění** konfigurační balíček odeberete.
  
    > [!NOTE] 
    > Pokud jste správně navázat spojení se ochrana ATP v programu Windows Defender, Intune se automaticky **připojení** konfigurační profil a **typ balíček konfigurace klienta ochrany ATP v programu Windows Defender** nastavení nebude k dispozici.
  
  - **Sdílení ukázky pro všechny soubory**: **Povolit** umožňuje ukázky, které se shromažďují a sdílet je s ochrany ATP v programu Windows Defender. Pokud například uvidíte podezřelý soubor, můžete ho odeslat službě Ochrana ATP v programu Windows Defender k hloubkové analýze. Pokud nechcete sdílet ukázky s Ochranou ATP v programu Windows Defender, vyberte možnost **Nenakonfigurováno**.
  - **Zvýšit četnost hlášení telemetrie**: U zařízení s vysokým rizikem **povolit** toto nastavení, aby hlásila telemetrii službě ochrana ATP v programu Windows Defender častěji.

    Další podrobnosti o těchto nastaveních Ochrany ATP v programu Windows Defender získáte v článku [Připojení počítačů s Windows 10 pomocí System Center Configuration Manageru](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/configure-endpoints-sccm-windows-defender-advanced-threat-protection).

7. Zvolte **OK** a pak **Vytvořit**. Tím uložíte změny a vytvoříte profil.

## <a name="create-the-compliance-policy"></a>Vytvoření zásady dodržování předpisů
Zásady dodržování předpisů určují přijatelnou úroveň rizika v zařízení.

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**.
3. Zadejte **Název** a **Popis**.
4. V části **Platforma** vyberte **Windows 10 a novější**.
5. V **ochrany ATP v programu Windows Defender** nastavte **vyžadovat, aby zařízení bylo na nebo za skóre rizika počítače** na požadovanou úroveň. Úrovně klasifikace hrozeb jsou [určené ochrany ATP v programu Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/alerts-queue-windows-defender-advanced-threat-protection).

   - **Vymazat**: Tato úroveň je nejbezpečnější úroveň. Zařízení nemůže přistupovat k prostředkům společnosti, pokud je vystavené nějakým hrozbám. Pokud se najde jakákoli hrozba, zařízení se vyhodnotí jako nevyhovující. (Uživatelé ochrany ATP v programu Windows Defender hodnota *Secure*.)
   - **Nízká**: Zařízení splňuje předpisy, pokud jenom hrozby nízké úrovně. Zařízení s hrozbami střední nebo vysoké úrovně jsou nevyhovující.
   - **Střední**: Zařízení splňuje předpisy, pokud jsou hrozby pohybují na střední nebo nízké. Pokud se v zařízení zjistí hrozby vysoké úrovně, vyhodnotí se jako nevyhovující.
   - **Vysoká**: Tato úroveň je nejméně bezpečná a umožňuje všechny úrovně hrozeb. Jako vyhovující se tedy vyhodnotí zařízení s hrozbami nízké, střední i vysoké úrovně.

6. Zvolte **OK** a pak **Vytvořit**. Tím uložíte změny a vytvoříte zásadu.

## <a name="assign-the-policy"></a>Přiřazení zásady

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Dodržování předpisů zařízením** > **Zásady**> vyberte zásady dodržování předpisů vaší Ochrany ATP v programu Windows Defender.
3. Zvolte **Přiřazení**.
4. Vyberte, kterým skupinám Azure AD chcete zásadu přiřadit.
5. Když zvolíte **Uložit**, zásada se nasadí dané skupině. U uživatelských zařízení, na která zásady cílí, se vyhodnotí dodržování předpisů.

## <a name="create-a-conditional-access-policy"></a>Vytvoření zásad podmíněného přístupu
Zásady podmíněného přístupu zablokují přístup zařízení k prostředkům, *pokud* se zařízení vyhodnotí jako nevyhovující. Pokud tedy zařízení překročí úroveň hrozby, můžete zablokovat přístup k podnikovým prostředkům jako SharePoint nebo Exchange Online.  

> [!TIP]  
> Podmíněný přístup je technologie Azure Active Directory (Azure AD). Uzel podmíněného přístupu, ke kterému se přistupuje z *Intune*, je stejný uzel, ke kterému se přistupuje z *Azure AD*.  

1. V [webu Azure portal](https://portal.azure.com), otevřete **Intune** > **podmíněného přístupu** > **nové zásady**.
2. Zadejte **Název** zásady a zvolte **Uživatelé a skupiny**. Pomocí možností Zahrnout a Vyloučit vyberte požadované skupiny pro nasazení zásady a zvolte **Hotovo**.
3. Zvolte **Cloudové aplikace** a vyberte aplikace, které chcete chránit. Zvolte například **Vybrat aplikace** a pak vyberte **Office 365 SharePoint Online** a **Office 365 Exchange Online**.

    Zvolením možnosti **Hotovo** uložte změny.

4. Když zvolíte **Podmínky** > **Klientské aplikace**, zásady se použijí pro aplikace a prohlížeče. Zvolte například **Ano** a pak povolte **Prohlížeč** a **Mobilní aplikace a desktopoví klienti**.

    Zvolením možnosti **Hotovo** uložte změny.

5. Zvolením možnosti **Udělení** použijete podmíněný přístup na základě dodržování předpisů zařízením. Zvolte například **Udělit přístup** > **Vyžadovat, aby zařízení bylo označené jako vyhovující**.

    Zvolením možnosti **Vybrat** uložte změny.

6. Zvolte **Povolit zásadu** a potom **Vytvořit**. Tím uložíte provedené změny.

Doporučujeme přečíst si článek [Co je podmíněný přístup](conditional-access.md).

## <a name="monitor-device-compliance"></a>Monitorování dodržování předpisů zařízením
V dalším kroku monitorujte stav zařízení, která mají nasazené zásady dodržování předpisů Ochrany ATP v programu Windows Defender.

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Dodržování předpisů zařízením** > **Dodržování zásad**.
3. Najděte v seznamu požadovanou zásadu Ochrany ATP v programu Windows Defender a podívejte se, která zařízení jsou vyhovující a která ne.

## <a name="more-good-stuff"></a>Další užitečné materiály
[Podmíněný přístup Ochrany ATP v programu Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/conditional-access-windows-defender-advanced-threat-protection)  
[Řídicí panel rizika Ochrany ATP v programu Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-atp/dashboard-windows-defender-advanced-threat-protection)  
[Začínáme se zásadami dodržování předpisů zařízeními](device-compliance-get-started.md)  
[Podmíněný přístup v Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)
