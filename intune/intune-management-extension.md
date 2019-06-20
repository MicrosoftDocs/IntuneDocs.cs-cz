---
title: Přidání Powershellových skriptů do zařízení s Windows 10 v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Vytvářet a spouštět skripty prostředí PowerShell, přiřazení zásad skriptu ke skupinám Azure Active Directory, skripty monitorování pomocí sestav a najdete v článku kroky k odstranění skripty, které přidáte na zařízeních s Windows 10 v Microsoft Intune. Viz také některé běžné problémy a jejich řešení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/19/2019
ms.topic: conceptual
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 967398516cdc2f727aa517fed3c8cf65810a38a1
ms.sourcegitcommit: 14f4e97de5699394684939e6f681062b5d4c1671
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2019
ms.locfileid: "67251230"
---
# <a name="use-powershell-scripts-on-windows-10-devices-in-intune"></a>Použití skriptů prostředí PowerShell na zařízení s Windows 10 v Intune

Rozšíření pro správu Microsoft Intune umožňuje nahrát Powershellové skripty do Intune ke spuštění na zařízení s Windows 10. Rozšíření pro správu podporuje správu mobilních zařízení Windows 10 (MDM) a usnadňuje přechod na moderní správu.

Tato funkce platí pro:

- Windows 10 a novější

## <a name="move-to-modern-management"></a>Přechod na moderní správu

Prostředí IT pro koncové uživatele prochází digitální transformací. Klasický, tradiční informační technologie se zaměřují na platformy pro jednotlivá zařízení, zařízení vlastněná firmami, uživatele, kteří pracují z office a různých ručně reaktivních IT procesů. Moderní pracoviště používá řada platforem, které jsou uživatelů a ve vlastnictví firmy, umožňuje uživatelům pracovat odkudkoli a nabízí automatické a proaktivní IT procesy.

Služby správy mobilních zařízení, jako je například Microsoft Intune můžete spravovat mobilních a desktopových zařízení s Windows 10. Integrované klient správy Windows 10 komunikuje s Intune a spuštění podnikové úlohy správy. Zde jsou některé úkoly, které mohou vyžadovat, například rozšířenou konfiguraci zařízení a řešení potíží. Pro správu aplikací Win32, můžete použít [správy aplikací Win32](apps-win32-app-management.md) funkce na zařízeních s Windows 10.

Rozšíření správy Intune doplňuje integrované funkce Windows 10 MDM. Můžete vytvořit skripty Powershellu pro spuštění na zařízení s Windows 10. Například můžete vytvořit skript Powershellu, konfigurace pokročilé zařízení, nahraje skript do Intune, skript přiřadí skupinu Azure Active Directory (AD) a spustí skript. Potom můžete monitorovat stav spuštění skriptu od začátku do konce.

## <a name="prerequisites"></a>Požadavky

Rozšíření správy Intune má následující požadavky. Jakmile jsou splněny tyto, rozšíření správy Intune se nainstaluje automaticky při skript prostředí PowerShell nebo aplikace Win32 je přiřazená uživateli nebo zařízení.

- Zařízení se systémem Windows 10 verze 1607 nebo novější. Pokud je zařízení zaregistrované pomocí [hromadně automatický zápis](windows-bulk-enroll.md), zařízení musí používat Windows 10 verze 1703 nebo novější. Rozšíření správy Intune se nepodporuje ve Windows 10 v režimu S, protože režim S neumožňuje spouštění aplikací mimo úložiště. 
  
- Zařízení připojená k Azure Active Directory (AD), včetně:  
  
  - Hybridní Azure připojené k AD: Zařízení připojené k Azure Active Directory (AD) a také připojené k místní služby Active Directory (AD). Zobrazit [naplánování vaší implementace připojení k hybridní službě Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-plan) pokyny.

- Zařízení zaregistrovaná v Intune, včetně:

  - Zařízení zaregistrovaná v zásadách skupiny (GPO). Zobrazit [registraci zařízení s Windows 10 automaticky prostřednictvím zásad skupiny](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy) pokyny.
  
  - Zařízení ručně zaregistrovaná v Intune, což je při:
  
    - [Automatická registrace do Intune](quickstart-setup-auto-enrollment.md) je povolené ve službě Azure AD. Koncový uživatel přihlásí k zařízení pomocí místní uživatelský účet, ručně připojí zařízení k Azure AD a potom se přihlásí k zařízení pomocí svého účtu Azure AD.
    
    NEBO  
    
    - Uživatel přihlásí k zařízení pomocí svého účtu Azure AD a pak zaregistruje v Intune.

  - Spoluspravovaná zařízení, které používají Configuration Managerem a Intune. Zobrazit [co je společná správa](https://docs.microsoft.com/sccm/comanage/overview) pokyny.

> [!TIP]
> Ujistěte se, jsou zařízení [připojený](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network) do služby Azure AD. Zařízení, která jsou jenom [zaregistrovaný](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) ve službě Azure AD nebude dostávat skripty.

## <a name="create-a-script-policy"></a>Vytvoření zásad skriptů 

1. Přihlaste se k [Intune](https://go.microsoft.com/fwlink/?linkid=2090973).
2. Vyberte **Konfigurace zařízení** > **Powershellové skripty** > **Přidat**.
3. Zadejte tyto vlastnosti:
    - **Název**: Zadejte název skriptu prostředí PowerShell. 
    - **Popis**: Zadejte popis pro skript prostředí PowerShell. Toto nastavení není povinné, ale doporučujeme ho zadat. 
    - **Umístění skriptu**: Vyhledejte skript prostředí PowerShell. Skript musí být kratší než 200 KB (ASCII).
4. Zvolte **konfigurovat**a zadejte následující vlastnosti:
    - **Spusťte tento skript pomocí pověření přihlášeného**: Vyberte **Ano** spusťte skript pomocí přihlašovacích údajů uživatele v zařízení. Zvolte **ne** (výchozí) pro spuštění skriptu v kontextu systému. Mnoho správců zvolte **Ano**. Pokud skript se vyžaduje pro spuštění v kontextu systému, zvolte **ne**.
    - **Vynutit kontrolu podpisu skriptu**: Vyberte **Ano** Pokud musí být skript podepsán důvěryhodným vydavatelem. Vyberte **ne** (výchozí), pokud není k dispozici požadavek pro skript, který chcete podepsat. 
    - **Spuštění skriptu na hostiteli Powershellu 64-bit**: Vyberte **Ano** pro spuštění skriptu v hostitelském prostředí PowerShell (PS) 64-bit na architektuře 64-bit klienta. Vyberte **ne** (výchozí) spustí skript v hostitelském prostředí PowerShell 32-bit.

      Při nastavení na **Ano** nebo **ne**, použijte následující tabulku pro nová a existující zásady chování:

      | Spuštění skriptu na hostiteli PS 64-bit | Architektura klienta | Nový skript PS | Existující zásady skriptu PS |
      | --- | --- | --- | --- | 
      | Ne | 32bitová  | 32-bit PS hostitele podporována | Spustí jenom v hostiteli PS 32-bit, který pracuje na 32bitové a 64bitové architektury. |
      | Ano | 64bitová | Skript se spustí v 64-bit PS hostitele pro 64bitové architektury. Při spuštění na 32-bit, spuštění skriptu na hostiteli PS 32-bit. | Skript se spustí v 32bitové PS hostitele. Pokud toto nastavení se změní na 64-bit, skript otevře (není spuštěna) v hostiteli PS 64-bit a sestavy výsledky. Pokud byl spuštěn na 32-bit, spuštění skriptu na hostiteli PS 32-bit. |

    ![Přidat a používat skripty prostředí PowerShell v Microsoft Intune](./media/mgmt-extension-add-script.png)
5. Vyberte **OK** > **vytvořit** skript uložte.

> [!NOTE]
> Když koncový uživatel má oprávnění správce ve výchozím nastavení skriptů jsou nastaveny na uživatelský kontext, skript prostředí PowerShell spouští v části oprávnění správce.

## <a name="assign-the-policy"></a>Přiřazení zásady

1. V části **Powershellové skripty** vyberte skript, který chcete přiřadit, a potom zvolte **Spravovat** > **Přiřazení**.

    ![Přiřazení nebo skript prostředí PowerShell můžete nasadit do skupin zařízení v Microsoft Intune](./media/mgmt-extension-assignments.png)

2. Výběrem možnosti **Vybrat skupiny** zobrazte seznam dostupných skupin Azure AD. 
3. Vyberte jednu nebo více skupin, které obsahují uživatele, jejichž zařízení přijímat tento skript. Kliknutím na **Vybrat** přiřaďte zásady k vybraným skupinám.

> [!NOTE]
> - Koncoví uživatelé nemusí přihlásit k zařízení a spouštění skriptů prostředí PowerShell.
> - Powershellové skripty do Intune můžete zacílit na skupiny zabezpečení Azure AD zařízení nebo skupiny zabezpečení uživatelů Azure AD.

Klient rozšíření správy Intune zkontroluje jednou za hodinu a po každém restartování pro nové skripty nebo změny v Intune. Po přiřazení zásad ke skupinám Azure AD se powershellový skript spustí a zobrazí se výsledky spuštění. Jakmile se skript spustí, neprovede znovu Pokud dojde ke změně ve skriptu nebo zásady.

## <a name="monitor-run-status"></a>Monitorování stavu spuštění

Na portálu Azure Portal můžete monitorovat stav spuštění powershellových skriptů u uživatelů a zařízení.

V části **Powershellové skripty** vyberte skript, který chcete monitorovat, zvolte **Monitorovat** a pak zvolte jednu z následujících sestav:

- **Stav zařízení**
- **Stav uživatele**

## <a name="troubleshoot-scripts"></a>Řešení potíží s skriptů

Protokoly agenta v klientském počítači jsou obvykle v `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Můžete použít [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) zobrazení tyto soubory protokolů. 

![Protokoly agenta snímku obrazovky nebo ukázkový nástroj cmtrace v Microsoft Intune](./media/apps-win32-app-10.png)  

## <a name="delete-a-script"></a>Odstranit skript

V části **Powershellové skripty** klikněte pravým tlačítkem na skript a vyberte **Odstranit**.

## <a name="common-issues-and-resolutions"></a>Běžné problémy a jejich řešení

#### <a name="issue-intune-management-extension-doesnt-download"></a>Problém: Rozšíření správy Intune se nestahuje

**Možná řešení**:

- Zařízení není připojená k Azure AD. Ujistěte se, zařízení splňují [požadavky](#prerequisites) (v tomto článku). 
- Neexistují žádné Powershellových skriptů nebo aplikací Win32 přiřadit ke skupinám, které uživatel nebo zařízení patří.
- Zařízení nemůže vrácení se změnami pomocí služby Intune, protože žádný přístup k Internetu bez přístupu k Windows Push Notification Services (WNS) a tak dále.
- Zařízení je v režimu S. Rozšíření správy Intune nepodporuje na zařízeních se systémem v režimu S. 

Chcete-li zjistit, zda je zařízení zaregistrované automaticky, můžete:

  1. Přejděte na **nastavení** > **účty** > **přístup do práce nebo do školy**.
  2. Vyberte účet, připojené k doméně > **informace**.
  3. V části **Advanced diagnostickou sestavu**vyberte **vytvořit sestavu**.
  4. Otevřít `MDMDiagReport` ve webovém prohlížeči.
  5. Hledat **MDMDeviceWithAAD** vlastnost. Pokud existuje vlastnost, je zařízení zaregistrované automaticky. Pokud tato vlastnost neexistuje, zařízení není zaregistrované automaticky.

[Povolit automatickou registraci Windows 10](windows-enroll.md#enable-windows-10-automatic-enrollment) obsahuje postup, jak nakonfigurovat automatické registrace v Intune.

#### <a name="issue-powershell-scripts-do-not-run"></a>Problém: Nelze spustit skripty prostředí PowerShell

**Možná řešení**:

- Při každé přihlášení není spuštěny skripty prostředí PowerShell. Spuštění:

  - Když je skript přiřazen k zařízení
  - Pokud změníte skript, nahrajte ho a přiřadit ho ke uživatele nebo zařízení
  
    > [!TIP]
    > **Rozšíření pro správu Microsoft Intune** je služba, která se spustí na zařízení, stejně jako jakoukoli jinou službu v aplikaci služeb (services.msc). Po restartování zařízení se tato služba může také restartovat a vyhledat všechny přiřazené skripty prostředí PowerShell ve službě Intune. Pokud **rozšíření pro správu Microsoft Intune** služby je nastaven na ručně a restartujte službu nemusí po restartování zařízení.

- Ujistěte se, jsou zařízení [připojená k Azure AD](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network). Zařízení, která jsou pouze připojená k síti na pracovišti nebo organizace ([zaregistrovaný](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network) ve službě Azure AD) neobdrží skripty.
- Klient rozšíření správy Intune kontroluje jednou za hodinu pro všechny změny ve skriptu nebo zásady v Intune.
- Ověřte rozšíření správy Intune se stáhne do `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Na Surface Huby nebo Windows 10 nejsou v režimu S spouštěny skripty.
- Zkontrolujte protokoly nějaké chyby. Zobrazit [Poradce při potížích s skripty](#troubleshoot-scripts) (v tomto článku).
- Pro oprávnění možné problémy, ujistěte se, vlastnosti skript prostředí PowerShell jsou nastavené `Run this script using the logged on credentials`. Zkontrolujte také, že má přihlášený uživatel příslušná oprávnění ke spuštění skriptu.

- K izolování problémů skriptování, postupujte takto:

  - Zkontrolujte konfiguraci spuštění skriptu PowerShell na vašich zařízeních. Zobrazit [zásady spouštění prostředí PowerShell](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy?view=powershell-6) pokyny.
  - Spustíte ukázkový skript, pomocí rozšíření správy Intune. Například vytvořit `C:\Scripts` adresáře a udělte všem úplné řízení. Spusťte tento skript:

    ```powershell
    write-output "Script worked" | out-file c:\Scripts\output.txt
    ```

    Pokud se aktivace podaří, výstup.txt by měly být vytvořeny a by měl obsahovat text "Pracoval skript".

  - Pokud chcete otestovat spuštění skriptu bez Intune, spouštění skriptů v systému pomocí účtu [nástroj psexec](https://docs.microsoft.com/sysinternals/downloads/psexec) místně:

    `psexec -i -s`

## <a name="next-steps"></a>Další postup

[Monitorování](device-profile-monitor.md) a [Poradce při potížích s](device-profile-troubleshoot.md) vašich profilů.
