---
title: Používání ATP v programu Microsoft Defender v Microsoft Intune – Azure | Microsoft Docs
description: Podívejte se, jak povolit Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP) v uceleném scénáři, včetně zapínání ATP Microsoft Defenderu v Intune a v Microsoft Defenderu Security Center, připojení zařízení pomocí ATP Microsoft Defenderu. konfigurační profil, vytvořte zásady dodržování předpisů zařízením v Intune, vytvořte zásady podmíněného přístupu Azure AD a sledujte dodržování předpisů zařízením.
keywords: ''
author: brenduns
ms.author: brenduns
manager: dougeby
ms.date: 07/22/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.reviewer: joglocke
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: af27a9b07434346a5425d0539759cb90ebf1ee6f
ms.sourcegitcommit: 614c4c36cfe544569db998e17e29feeaefbb7a2e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/24/2019
ms.locfileid: "68427095"
---
# <a name="enforce-compliance-for-microsoft-defender-atp-with-conditional-access-in-intune"></a>Vymáhání dodržování předpisů pro Microsoft Defender ATP pomocí podmíněného přístupu v Intune  

Rozšířená ochrana před internetovými útoky v programu Microsoft Defender (Microsoft Defender ATP) a Microsoft Intune vzájemně spolupracuje, aby se zabránilo narušení zabezpečení, a pomohla omezit dopad porušení zabezpečení v rámci organizace.

Tato funkce platí pro: Zařízení s Windows 10

Příklad: Někdo pošle uživateli ve vaší organizaci wordový soubor s vloženým škodlivým kódem. Uživatel přílohu otevře a povolí obsah. Spustí se útok se zvýšenými oprávněními. Útočník ho provádí ze vzdáleného počítače na napadeném zařízení, ke kterému získal oprávnění správce. Z tohoto zařízení získá vzdálený přístup i k dalším zařízením uživatele.

Toto porušení zabezpečení může mít dopad na celou organizaci.

ATP v programu Microsoft Defender může vyřešit události zabezpečení, jako je tento scénář. V programu Microsoft Defender Security Center hlásí zařízení jako "vysoké riziko" a obsahuje podrobnou zprávu o podezřelé aktivitě. V našem příkladu ATP Microsoft Defender detekuje, že zařízení provedlo neobvyklý kód, narazilo na eskalaci s oprávněním procesu, vložil škodlivý kód a vystavilo podezřelé vzdálené prostředí. Ochrana ATP v programu Microsoft Defender vám pak nabídne možnosti, jak tuto hrozbu zmírnit.

Pomocí Intune můžete vytvořit zásady dodržování předpisů, které stanoví přijatelnou úroveň rizika. Pokud zařízení tuto úroveň překročí, je označeno jako zařízení nedodržující předpisy. V kombinaci s podmíněným přístupem Azure Active Directory (AD) je uživateli zablokován přístup k podnikovým prostředkům.

V tomto článku se dozvíte, jak:

- Povolení Intune v programu Microsoft Defender Security Center a povolení ochrany ATP v programu Microsoft Defender v Intune. Tyto úlohy vytvoří propojení mezi službami Intune a Microsoft Defender ATP. Toto připojení umožňuje, aby ochrana ATP v programu Microsoft Defender mohla zapisovat rizika počítače pro vaše zařízení Intune.
- Vytvořit zásady dodržování předpisů v Intune.
- Povolte podmíněný přístup v Azure Active Directory (AD) na zařízeních na základě jejich úrovně hrozeb.

## <a name="prerequisites"></a>Požadavky

Pokud chcete používat Microsoft Defender ATP s Intune, ujistěte se, že máte nakonfigurované a připravené k použití:

- Tenant s licencí pro Enterprise Mobility + Security E3 a Windows E5 (nebo Microsoft 365 Enterprise E5)
- Prostředí Microsoft Intune se zařízeními s Windows 10 [spravovanými v Intune](windows-enroll.md), která jsou zároveň připojená k Azure AD
- Ochrana [ATP v programu Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) a přístup k Security Center programu Microsoft Defender (portál ATP)

## <a name="enable-microsoft-defender-atp-in-intune"></a>Povolení ochrany ATP v Microsoft Defenderu v Intune

Když integrujete novou aplikaci do ochrany před mobilními hrozbami Intune a povolíte připojení, Intune vytvoří v Azure Active Directory zásady klasického podmíněného přístupu. Každá aplikace MTD, kterou integrujete, jako je [Defender ATP](advanced-threat-protection.md) nebo některé z našich dalších [MTDch partnerů](mobile-threat-defense.md#mobile-threat-defense-partners), vytvoří nové zásady podmíněného přístupu v klasickém rozhraní.  Tyto zásady je možné ignorovat, ale neměly by být upravované, odstraňující ani zakázané.

Klasické zásady podmíněného přístupu pro aplikace MTD: 

- Používá Intune MTD k tomu, aby vyžadovala, aby byla zařízení zaregistrovaná ve službě Azure AD, aby měla ID zařízení. IDENTIFIKÁTOR je povinný, aby zařízení a mohl úspěšně ohlásit svůj stav do Intune.  
- Liší se od zásad podmíněného přístupu, které byste mohli vytvořit, abyste mohli lépe spravovat MTD.
- Ve výchozím nastavení nekomunikujete s dalšími zásadami podmíněného přístupu, které používáte pro vyhodnocení.  

Pokud chcete zobrazit klasické zásady podmíněného přístupu, přejděte v [Azure](https://portal.azure.com/#home)na **Azure Active Directory** > **klasické zásady** **podmíněného přístupu** > .

### <a name="to-enable-defender-atp"></a>Povolení ATP programu Defender
1. Přihlaste [](https://go.microsoft.com/fwlink/?linkid=2090973)se k Intune.
2. Vyberte **zařízení dodržování předpisů** > v**programu Microsoft Defender ATP**a pak pod *nastavením konektoru*vyberte **otevřít Security Center programu Microsoft Defender**.

    ![Výběrem otevřete Security Center programu Microsoft Defender.](./media/advanced-threat-protection/atp-device-compliance-open-microsoft-defender.png)

4. V **programu Microsoft Defender Security Center**:
    1. Zvolte **Nastavení** > **Pokročilé funkce**.
    2. Přepínač pro **připojení Microsoft Intune** přepněte do polohy **Zapnuto**:

        ![Povolení připojení k Intune](./media/advanced-threat-protection/atp-security-center-intune-toggle.png)

    3. Vyberte **Uložit předvolby**.

4. Vraťte se do Intune, **dodržování předpisů** > zařízením v**programu Microsoft Defender ATP**. Nastavte **připojit zařízení s Windows verze 10.0.15063 a novější pro Microsoft Defender ATP** na **on**.
5. Vyberte **Uložit**.

Tento postup stačí obvykle provést jednou. Takže pokud je v prostředku Intune už povolené prostředí Microsoft Defender ATP, nemusíte to dělat znovu.

## <a name="onboard-devices-using-a-configuration-profile"></a>Připojení zařízení pomocí konfiguračního profilu

Když se koncový uživatel zaregistruje v Intune, můžete pomocí konfiguračního profilu odesílat do zařízení různá nastavení. To platí i pro ATP v programu Microsoft Defender.

Microsoft Defender ATP zahrnuje konfigurační balíček, který komunikuje se [službami ATP v programu Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) , aby kontroloval soubory, zjišťoval hrozby a nahlásila rizika pro ATP v programu Microsoft Defender.

Po zprovoznění Intune získá automaticky generovaný konfigurační balíček z ochrany ATP v programu Microsoft Defender. Intune po odeslání konfiguračního profilu do zařízení doručí konfigurační balíček do zařízení, což umožňuje službě Microsoft Defender ATP monitorovat hrozby těchto zařízení.

Jakmile jednou připojíte zařízení pomocí konfiguračního balíčku, už to příště dělat nemusíte. Zařízení můžete připojit také pomocí [skupiny zásad nebo System Center Configuration Manageru (SCCM)](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).

### <a name="create-the-configuration-profile"></a>Vytvoření konfiguračního profilu

1. Přihlaste [](https://go.microsoft.com/fwlink/?linkid=2090973)se k Intune.
2. Vyberte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte **Název** a **Popis**.
4. V části **Platforma** vyberte **Windows 10 a novější**.
5. Jako **typ profilu**vyberte **ATP Microsoft Defender (Windows 10 Desktop)** .
6. Nakonfigurujte nastavení:

    - **Typ balíčku konfigurace klienta ATP v programu Microsoft Defender**: Vyberte  připojit a přidejte konfigurační balíček do profilu. Výběrem možnosti **Zrušit zprovoznění** konfigurační balíček odeberete.
  
    > [!NOTE]  
    > Pokud jste správně navázali připojení k ochraně ATP v programu Microsoft Defender, Intune se automaticky připojí ke konfiguračnímu profilu a nastavení **typu balíčku konfigurace klienta služby Microsoft Defender ATP** nebude k dispozici.
  
    - **Sdílení vzorků pro všechny soubory**: **Možnost Povolit** umožňuje shromažďovat vzorky a sdílet je s Microsoft Defender atp. Pokud se například zobrazí podezřelý soubor, můžete ho odeslat do ochrany ATP v programu Microsoft Defender pro hloubkovou analýzu. Nenakonfigurováno nesdílí žádné ukázky do ochrany ATP v programu Microsoft Defender.
    - **Urychlení generování sestav telemetrie**: U zařízení, která mají vysoké riziko, toto nastavení **Povolte** , aby se do služby ATP v programu Microsoft Defender nahlásí telemetrie častěji.

    Připojení [počítačů s Windows 10 pomocí System Center Configuration Manager](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints-sccm) obsahuje další podrobnosti o těchto nastaveních ATP v programu Microsoft Defender.

7. Zvolte **OK** a pak **Vytvořit**. Tím uložíte změny a vytvoříte profil.

## <a name="create-the-compliance-policy"></a>Vytvoření zásady dodržování předpisů
Zásady dodržování předpisů určují přijatelnou úroveň rizika v zařízení.

1. Přihlaste [](https://go.microsoft.com/fwlink/?linkid=2090973)se k Intune.
2. Vyberte **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**.
3. Zadejte **Název** a **Popis**.
4. V části **Platforma** vyberte **Windows 10 a novější**.
5. V nastavení **ATP v programu Microsoft Defender** nastavte možnost **vyžadovat, aby zařízení bylo na základě skóre rizika počítače** na upřednostňovanou úroveň. Klasifikace úrovně hrozeb určují služby [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/alerts-queue).

   - **Vymazat**: Tato úroveň je nejbezpečnější. Zařízení nemůže mít žádné existující hrozby a bude mít přístup k prostředkům společnosti. Pokud se najde jakákoli hrozba, zařízení se vyhodnotí jako nevyhovující. (Hodnota *zabezpečení*pro uživatele ATP v programu Microsoft Defender.)
   - **Nízká úroveň**: Zařízení je kompatibilní, pokud existují jenom hrozby nízké úrovně. Zařízení se středními nebo vysokou úrovní hrozeb nejsou kompatibilní.
   - **Střední**: Zařízení je kompatibilní, pokud jsou hrozby zjištěné v zařízení nízké nebo střední. Pokud se v zařízení zjistí hrozby vysoké úrovně, vyhodnotí se jako nevyhovující.
   - **Vysoká**: Tato úroveň je nejméně bezpečná a umožňuje všechny úrovně hrozeb. To znamená, že zařízení s vysokou, střední nebo nízkou úrovní hrozeb se považují za vyhovující.

6. Zvolte **OK** a pak **Vytvořit**. Tím uložíte změny a vytvoříte zásadu.

## <a name="assign-the-policy"></a>Přiřazení zásady

1. Přihlaste [](https://go.microsoft.com/fwlink/?linkid=2090973)se k Intune.
2. Vyberte**zásady** **dodržování předpisů** > pro zařízení > vyberte zásady dodržování předpisů v programu Microsoft Defender atp.
3. Zvolte **Přiřazení**.
4. Vyberte, kterým skupinám Azure AD chcete zásadu přiřadit.
5. Když zvolíte **Uložit**, zásada se nasadí dané skupině. U uživatelských zařízení, na která zásady cílí, se vyhodnotí dodržování předpisů.

## <a name="create-a-conditional-access-policy"></a>Vytvoření zásady podmíněného přístupu
Zásada podmíněného přístupu zablokuje přístup k prostředkům, *Pokud* zařízení nedodržuje předpisy. Pokud tedy zařízení překročí úroveň hrozby, můžete zablokovat přístup k podnikovým prostředkům jako SharePoint nebo Exchange Online.  

> [!TIP]  
> Podmíněný přístup je technologie Azure Active Directory (Azure AD). Uzel podmíněného přístupu, ke kterému se přistupuje z *Intune*, je stejný uzel, ke kterému se přistupuje z *Azure AD*.  

1. Přihlaste [](https://go.microsoft.com/fwlink/?linkid=2090973) se k Intune a vyberte**nové zásady** **podmíněného přístupu** > .
2. Zadejte **Název** zásady a zvolte **Uživatelé a skupiny**. Pomocí možností Zahrnout a Vyloučit vyberte požadované skupiny pro nasazení zásady a zvolte **Hotovo**.
3. Zvolte **Cloudové aplikace** a vyberte aplikace, které chcete chránit. Zvolte například **Vybrat aplikace** a pak vyberte **Office 365 SharePoint Online** a **Office 365 Exchange Online**.

    Zvolením možnosti **Hotovo** uložte změny.

4. Když zvolíte **Podmínky** > **Klientské aplikace**, zásady se použijí pro aplikace a prohlížeče. Zvolte například **Ano** a pak povolte **Prohlížeč** a **Mobilní aplikace a desktopoví klienti**.

    Zvolením možnosti **Hotovo** uložte změny.

5. Vyberte **udělit** pro uplatnění podmíněného přístupu na základě dodržování předpisů zařízením. Zvolte například **Udělit přístup** > **Vyžadovat, aby zařízení bylo označené jako vyhovující**.

    Zvolením možnosti **Vybrat** uložte změny.

6. Zvolte **Povolit zásadu** a potom **Vytvořit**. Tím uložíte provedené změny.

[Co je podmíněný přístup?](conditional-access.md) je dobrým prostředkem.

## <a name="monitor-device-compliance"></a>Monitorování dodržování předpisů zařízením
Dále Sledujte stav zařízení, která mají zásady dodržování předpisů ATP v programu Microsoft Defender.

1. Přihlaste [](https://go.microsoft.com/fwlink/?linkid=2090973)se k Intune.
2. Vyberte **Dodržování předpisů zařízením** > **Dodržování zásad**.
3. Vyhledejte v seznamu Zásady ochrany ATP v programu Microsoft Defender a podívejte se, která zařízení jsou kompatibilní nebo nekompatibilní.

## <a name="more-good-stuff"></a>Další užitečné materiály
[Podmíněný přístup Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/conditional-access)  
[Řídicí panel rizik pro ATP v programu Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)  

[Začínáme se zásadami dodržování předpisů zařízeními](device-compliance-get-started.md)  
[Podmíněný přístup ve službě Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)