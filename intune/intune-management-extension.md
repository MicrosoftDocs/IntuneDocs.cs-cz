---
title: Přidání powershellových skriptů v Microsoft Intune u zařízení s Windows 10 – Azure | Microsoft Docs
description: Přidejte powershellové skripty, přiřaďte zásady skriptů skupinám Azure Active Directory, použijte sestavy k monitorování skriptů a podívejte se na postup pro odstranění skriptů, které jste přidali na zařízení s Windows 10 v Microsoft Intune. Viz také některé běžné problémy a jejich řešení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 063a5cbbe18efc5c406c9dc7f2fa40d614b2e48a
ms.sourcegitcommit: d3b1e3fffd3e0229292768c7ef634be71e4736ae
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/04/2018
ms.locfileid: "52860958"
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Správa powershellových skriptů v Intune u zařízení s Windows 10

Rozšíření správy Intune umožňuje nahrát Powershellové skripty do Intune ke spuštění na zařízení s Windows 10. Rozšíření pro správu podporuje správu mobilních zařízení Windows 10 (MDM) a usnadňuje přechod na moderní správu.

## <a name="moving-to-modern-management"></a>Přechod na moderní správu

Prostředí IT pro koncové uživatele prochází digitální transformací. Klasické tradiční informační technologie se zaměřují na platformy pro jednotlivá zařízení, na zařízení vlastněná firmami, uživatele, kteří pracují z kanceláře, a celou řadu manuálních reaktivních IT procesů. Moderní pracoviště používá řada platforem, které jsou uživatelů a ve vlastnictví firmy, umožňuje uživatelům pracovat odkudkoli a nabízí automatické a proaktivní IT procesy.

Služby správy mobilních zařízení, jako je například Microsoft Intune můžete spravovat mobilních a desktopových zařízení s Windows 10. Integrované klient správy Windows 10 komunikuje s Intune a spuštění podnikové úlohy správy. Zde jsou některé úkoly, které mohou vyžadovat, například rozšířenou konfiguraci zařízení, řešení potíží a starší verze správy aplikací Win32, který není aktuálně k dispozici ve Windows 10 správy mobilních zařízení. Za tyto funkce lze softwarového klienta Intune na zařízení s Windows 10. [Porovnání správy počítačů s Windows jako mobilní zařízení nebo počítače](pc-management-comparison.md) je skvělý prostředek.

Rozšíření správy Intune doplňuje integrované funkce Windows 10 MDM. Můžete vytvořit skripty Powershellu pro spuštění na zařízení s Windows 10. Například můžete vytvořit skript prostředí PowerShell, který nainstaluje starší aplikaci Win32, nahraje skript do Intune, skript přiřadí skupinu Azure Active Directory (AD) a spustí skript. Potom můžete monitorovat stav spuštění skriptu od začátku do konce.

## <a name="prerequisites"></a>Požadavky

Rozšíření správy Intune vyžaduje splnění následujících požadavků:

- Zařízení musí být připojená k Azure AD a [automaticky zaregistrovat](windows-enroll.md#enable-windows-10-automatic-enrollment). Rozšíření správy Intune podporuje připojená k Azure AD, připojené k hybridní domény a comanaged zaregistrovaná zařízení s Windows. Zařízení zaregistrovaná v objektu zásad skupiny nejsou podporovány.
- Zařízení musí používat Windows 10 verze 1607 nebo novější.
- Rozšíření agenta pro správu Intune se nainstaluje při skript prostředí PowerShell nebo aplikace Win32 je nasazená na uživatele nebo skupiny zabezpečení zařízení.

## <a name="create-a-powershell-script-policy"></a>Vytvoření zásad powershellových skriptů 

1. V [webu Azure portal](https://portal.azure.com)vyberte **všechny služby** > vyfiltrujte **Intune** > vyberte **Microsoft Intune**.
2. Vyberte **Konfigurace zařízení** > **Powershellové skripty** > **Přidat**.
3. Zadejte **Název** a **Popis** powershellového skriptu. V části **Umístění skriptu** vyhledejte powershellový skript. Skript musí být kratší než 200 KB (ASCII) nebo velikost 100 KB (Unicode).
4. Zvolte **Konfigurace**. Potom zvolte, jestli chcete skript spouštět pomocí přihlašovacích údajů uživatele v zařízení (**Ano**) nebo v kontextu systému (**Ne**). Skript se standardně spouští v kontextu systému. Možnost **Ano** vyberte, pokud nechcete, aby se skript spouštěl v kontextu systému. 
  ![Podokno Přidat powershellový skript](./media/mgmt-extension-add-script.png)
5. Zvolte, jestli musí být skript podepsán důvěryhodným vydavatelem (**Ano**). Standardně nejsou stanovené žádné požadavky na to, aby byl skript podepsán. 
6. Výběrem **OK** a **Vytvořit** skript uložíte.

## <a name="assign-a-powershell-script-policy"></a>Přiřazení zásad powershellových skriptů

1. V části **Powershellové skripty** vyberte skript, který chcete přiřadit, a potom zvolte **Spravovat** > **Přiřazení**.

    ![Podokno Přidat Powershellový skript](./media/mgmt-extension-assignments.png)

2. Výběrem možnosti **Vybrat skupiny** zobrazte seznam dostupných skupin Azure AD. 
3. Vyberte jednu nebo více skupin, které obsahují uživatele, jejichž zařízení přijímat tento skript. Kliknutím na **Vybrat** přiřaďte zásady k vybraným skupinám.

> [!NOTE]
> - Skripty PowerShell se nedají použít u skupin počítačů.
> - Koncoví uživatelé nemusí přihlásit k zařízení a spouštění skriptů prostředí PowerShell.
> - Powershellové skripty do Intune můžete zacílit na skupiny zabezpečení Azure AD zařízení.

Klient rozšíření správy Intune kontroluje každou hodinu pomocí Intune. Po přiřazení zásad ke skupinám Azure AD se powershellový skript spustí a zobrazí se výsledky spuštění.

## <a name="monitor-run-status-for-powershell-scripts"></a>Monitorování stavu spuštění powershellových skriptů

Na portálu Azure Portal můžete monitorovat stav spuštění powershellových skriptů u uživatelů a zařízení.

V části **Powershellové skripty** vyberte skript, který chcete monitorovat, zvolte **Monitorovat** a pak zvolte jednu z následujících sestav:

- **Stav zařízení**
- **Stav uživatele**

## <a name="troubleshoot-powershell-scripts"></a>Řešení potíží s skripty prostředí PowerShell

Protokoly agenta v klientském počítači jsou obvykle v `\ProgramData\Microsoft\IntuneManagementExtension\Logs`. Můžete použít [CMTrace.exe](https://docs.microsoft.com/sccm/core/support/tools) zobrazení tyto soubory protokolů. 

![Snímek obrazovky s protokoly agenta](./media/apps-win32-app-10.png)  

## <a name="delete-a-powershell-script"></a>Odstranění powershellového skriptu

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

#### <a name="issue-the-powershell-scripts-do-not-run"></a>Problém: Skripty Powershellu se nespustí.

**Možná řešení**:

- Ověřte rozšíření správy Intune se stáhne do `%ProgramFiles(x86)%\Microsoft Intune Management Extension`.
- Skripty nespouštět na Surface Huby.
- Zkontrolujte protokoly `\ProgramData\Microsoft\IntuneManagementExtension\Logs` nějaké chyby.
- Pro oprávnění možné problémy, ujistěte se, vlastnosti skript prostředí PowerShell jsou nastavené `Run this script using the logged on credentials`. Zkontrolujte také, že má přihlášený uživatel příslušná oprávnění ke spuštění skriptu.
- K izolování problémů skriptování, spusťte ukázkový skript. Například vytvořit `C:\Scripts` adresáře a udělte všem úplné řízení. Spusťte následující skript:

  ```powershell
  write-output "Script worked" | out-file c:\Scripts\output.txt
  ```

  Pokud se aktivace podaří, výstup.txt by měly být vytvořeny a by měl obsahovat text "Pracoval skript".

- Pokud chcete otestovat spuštění skriptu bez Intune, spustit skripty v kontextu systému pomocí [nástroj psexec](https://docs.microsoft.com/sysinternals/downloads/psexec) místně:

  `psexec -i -s`

## <a name="next-steps"></a>Další postup

[Monitorování](device-profile-monitor.md) a [Poradce při potížích s](device-profile-troubleshoot.md) vašich profilů.
