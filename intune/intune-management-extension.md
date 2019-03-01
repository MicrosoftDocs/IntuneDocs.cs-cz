---
title: Přidání Powershellových skriptů do zařízení s Windows 10 v Microsoft Intune – Azure | Dokumentace Microsoftu
description: Vytvářet a spouštět skripty prostředí PowerShell, přiřazení zásad skriptu ke skupinám Azure Active Directory, skripty monitorování pomocí sestav a najdete v článku kroky k odstranění skripty, které přidáte na zařízeních s Windows 10 v Microsoft Intune. Viz také některé běžné problémy a jejich řešení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 99e44190f2e87d1b859450bc96bf52e1cd1430f1
ms.sourcegitcommit: c89e41e7bd546e4feceae26d82326230a16a713c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/01/2019
ms.locfileid: "57017026"
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

Rozšíření správy Intune vyžaduje splnění následujících požadavků:

- Zařízení musí být připojený nebo zaregistrovaný do Azure AD a Azure AD je nakonfigurovaný pro [Automatická registrace do Intune](windows-enroll.md#enable-windows-10-automatic-enrollment). Rozšíření správy Intune podporuje připojená k Azure AD, připojené k hybridní domény a společně spravovat zaregistrovaná zařízení s Windows.
- Zařízení musí používat Windows 10 verze 1607 nebo novější.
- Rozšíření agenta pro správu Intune se nainstaluje při skript prostředí PowerShell nebo aplikace Win32 je nasazená na uživatele nebo skupiny zabezpečení zařízení.

## <a name="create-a-script-policy"></a>Vytvoření zásad skriptů 

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Intune**.
2. Vyberte **Konfigurace zařízení** > **Powershellové skripty** > **Přidat**.
3. Zadejte tyto vlastnosti:
    - **Název**: Zadejte název skriptu prostředí PowerShell. 
    - **Popis**: Zadejte popis pro skript prostředí PowerShell. Toto nastavení není povinné, ale doporučujeme ho zadat. 
    - **Umístění skriptu**: Vyhledejte skript prostředí PowerShell. Skript musí být kratší než 200 KB (ASCII).
4. Zvolte **konfigurovat**a zadejte následující vlastnosti:
    - **Spusťte tento skript pomocí pověření přihlášeného**: Vyberte **Ano** spusťte skript pomocí přihlašovacích údajů uživatele v zařízení. Zvolte **ne** (výchozí) pro spuštění skriptu v kontextu systému. Možnost **Ano** vyberte, pokud nechcete, aby se skript spouštěl v kontextu systému.
    - **Vynutit kontrolu podpisu skriptu**: Vyberte **Ano** Pokud musí být skript podepsán důvěryhodným vydavatelem. Vyberte **ne** (výchozí), pokud není k dispozici požadavek pro skript, který chcete podepsat. 
    - **Spuštění skriptu na hostiteli Powershellu 64-bit**: Vyberte **Ano** pro spuštění skriptu v hostitelském prostředí PowerShell (PS) 64-bit na architektuře 64-bit klienta. Vyberte **ne** (výchozí) spustí skript v hostitelském prostředí PowerShell 32-bit.

      Při nastavení na **Ano** nebo **ne**, použijte následující tabulku pro nová a existující zásady chování:

      | Spuštění skriptu na hostiteli PS 64-bit | Architektura klienta | Nový skript PS | Existující zásady skriptu PS |
      | --- | --- | --- | --- | 
      | Ne | 32-bit  | 32-bit PS hostitele podporována | Spustí jenom v hostiteli PS 32-bit, který pracuje na 32bitové a 64bitové architektury. |
      | Ano | 64-bit | Skript se spustí v 64-bit PS hostitele pro 64bitové architektury. Při spuštění na 32-bit, spuštění skriptu na hostiteli PS 32-bit. | Skript se spustí v 32bitové PS hostitele. Pokud toto nastavení se změní na 64-bit, skript otevře (není spuštěna) v hostiteli PS 64-bit a sestavy výsledky. Pokud byl spuštěn na 32-bit, spuštění skriptu na hostiteli PS 32-bit. |

    ![Přidat a používat skripty prostředí PowerShell v Microsoft Intune](./media/mgmt-extension-add-script.png)
5. Vyberte **OK** > **vytvořit** skript uložte.

## <a name="assign-the-policy"></a>Přiřazení zásady

1. V části **Powershellové skripty** vyberte skript, který chcete přiřadit, a potom zvolte **Spravovat** > **Přiřazení**.

    ![Přiřazení nebo skript prostředí PowerShell můžete nasadit do skupin zařízení v Microsoft Intune](./media/mgmt-extension-assignments.png)

2. Výběrem možnosti **Vybrat skupiny** zobrazte seznam dostupných skupin Azure AD. 
3. Vyberte jednu nebo více skupin, které obsahují uživatele, jejichž zařízení přijímat tento skript. Kliknutím na **Vybrat** přiřaďte zásady k vybraným skupinám.

> [!NOTE]
> - Koncoví uživatelé nemusí přihlásit k zařízení a spouštění skriptů prostředí PowerShell.
> - Powershellové skripty do Intune můžete zacílit na skupiny zabezpečení Azure AD zařízení.
> - Powershellové skripty do Intune můžete zacílit na skupiny zabezpečení uživatelů Azure AD.

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

Při každé přihlášení není spuštěny skripty prostředí PowerShell. Spuštění až po restartování počítače, nebo pokud **rozšíření pro správu Microsoft Intune** restartování služby. Klient kontrola Intune správu rozšíření jednou za hodinu pro všechny změny ve skriptu nebo zásady v Intune.

#### <a name="issue-intune-management-extension-doesnt-download"></a>Problém: Rozšíření správy Intune se nestahuje

**Možná řešení**:

- Ujistěte se, že zařízení jsou automaticky zaregistrovat ve službě Azure AD. Pokud chcete potvrdit, na zařízení: 

  1. Přejděte na **nastavení** > **účty** > **přístup do práce nebo do školy**.
  2. Vyberte účet, připojené k doméně > **informace**.
  3. V části **Advanced diagnostickou sestavu**vyberte **vytvořit sestavu**.
  4. Otevřít `MDMDiagReport` v webový prohlížeč a přejděte k **zaregistrované zdroje konfigurace** oddílu.
  5. Hledat **MDMDeviceWithAAD** vlastnost. Pokud tato vlastnost neexistuje, zařízení není zaregistrované automaticky.

    [Povolit automatickou registraci Windows 10](windows-enroll.md#enable-windows-10-automatic-enrollment) zahrnuje kroky.

#### <a name="issue-powershell-scripts-do-not-run"></a>Problém: Nelze spustit skripty prostředí PowerShell

**Možná řešení**:

- Ověřte rozšíření správy Intune se stáhne do `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Skripty nespouštět na Surface Huby.
- Zkontrolujte protokoly `\ProgramData\Microsoft\IntuneManagementExtension\Logs` nějaké chyby.
- Pro oprávnění možné problémy, ujistěte se, vlastnosti skript prostředí PowerShell jsou nastavené `Run this script using the logged on credentials`. Zkontrolujte také, že má přihlášený uživatel příslušná oprávnění ke spuštění skriptu.
- K izolování problémů skriptování, spusťte ukázkový skript. Například vytvořit `C:\Scripts` adresáře a udělte všem úplné řízení. Spusťte tento skript:

  ```powershell
  write-output "Script worked" | out-file c:\Scripts\output.txt
  ```

  Pokud se aktivace podaří, výstup.txt by měly být vytvořeny a by měl obsahovat text "Pracoval skript".

- Pokud chcete otestovat spuštění skriptu bez Intune, spustit skripty v kontextu systému pomocí [nástroj psexec](https://docs.microsoft.com/sysinternals/downloads/psexec) místně:

  `psexec -i -s`

## <a name="next-steps"></a>Další postup

[Monitorování](device-profile-monitor.md) a [Poradce při potížích s](device-profile-troubleshoot.md) vašich profilů.
