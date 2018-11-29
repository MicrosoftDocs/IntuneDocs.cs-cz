---
title: Přidání powershellových skriptů v Microsoft Intune u zařízení s Windows 10 – Azure | Microsoft Docs
description: Přidejte powershellové skripty, přiřaďte zásady skriptů skupinám Azure Active Directory, použijte sestavy k monitorování skriptů a podívejte se na postup pro odstranění skriptů, které jste přidali na zařízení s Windows 10 v Microsoft Intune.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 11/28/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 2c4fb7000d808d860494d2af572c821b42fa6d5c
ms.sourcegitcommit: 77a1047f5d93c1924e5c9ea243454532881be031
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/28/2018
ms.locfileid: "52579179"
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Správa powershellových skriptů v Intune u zařízení s Windows 10
Rozšíření správy Intune umožňuje nahrát powershellové skripty do Intune, aby je bylo možné spouštět v zařízeních s Windows 10. Rozšíření správy doplňuje funkce správy mobilních zařízení (MDM) s Windows 10 a usnadňuje přechod na moderní správu.

## <a name="moving-to-modern-management"></a>Přechod na moderní správu
Prostředí IT pro koncové uživatele prochází digitální transformací. Klasické tradiční informační technologie se zaměřují na platformy pro jednotlivá zařízení, na zařízení vlastněná firmami, uživatele, kteří pracují z kanceláře, a celou řadu manuálních reaktivních IT procesů. Moderní pracoviště ale umožňuje používat platformy pro více zařízení vlastněná uživateli i firmami, uživatelům pracovat odkudkoli a zajistit automatické a proaktivní IT procesy. 

Služby správy mobilních zařízení, jako je třeba Microsoft Intune, mohou spravovat zařízení s Windows 10 pomocí protokolu MDM. Integrovaný klient správy Windows 10 je schopen komunikovat s Intune a provádět úlohy podnikové správy. Pomůže vám při přechodu na moderní správu v zařízeních s Windows 10. Existují však některé funkce, které můžete potřebovat, jako je například rozšířenou konfiguraci zařízení, která není k dispozici ve Windows 10 integrované funkce MDM.

Rozšíření správy Intune doplňuje integrované funkce správy mobilních zařízení pro Windows 10. Můžete si vytvořit powershellové skripty, které vám budou poskytovat požadované funkce, a spouštět je v zařízeních s Windows 10. Můžete vytvořit Powershellový skript, který konfiguruje vaše vlastní nastavení, nahrát ho do Intune, přiřadit ho ke skupině Azure Active Directory (AD) a spuštění skriptu na zařízení s Windows 10. Skript je možné monitorovat zobrazíte stav spuštění skriptu na zařízení s Windows 10 od začátku do konce.

## <a name="prerequisites"></a>Požadavky
Rozšíření správy Intune vyžaduje splnění následujících požadavků:
- Zařízení musí být připojená k Azure AD. Rozšíření správy Intune podporuje připojení k Azure Active Directory, připojení k hybridní doméně a společnou správu registrovaných zařízení s Windows.
- Zařízení musí používat Windows 10 verze 1607 nebo novější.
- Automatická registrace MDM musí být [povolena ve službě Azure AD](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment) a zařízení musí být automaticky zaregistrována v Intune.

## <a name="create-a-powershell-script-policy"></a>Vytvoření zásad powershellových skriptů 
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Konfigurace zařízení** > **Powershellové skripty** > **Přidat**.
4. Zadejte **Název** a **Popis** powershellového skriptu. V části **Umístění skriptu** vyhledejte powershellový skript. Velikost skriptu musí být menší než 200 kB (ASCII) nebo 100 kB (Unicode).
5. Zvolte **Konfigurace**. Potom zvolte, jestli chcete skript spouštět pomocí přihlašovacích údajů uživatele v zařízení (**Ano**) nebo v kontextu systému (**Ne**). Skript se standardně spouští v kontextu systému. Možnost **Ano** vyberte, pokud nechcete, aby se skript spouštěl v kontextu systému. 
  ![Podokno Přidat powershellový skript](./media/mgmt-extension-add-script.png)
6. Zvolte, jestli musí být skript podepsán důvěryhodným vydavatelem (**Ano**). Standardně nejsou stanovené žádné požadavky na to, aby byl skript podepsán. 
7. Výběrem **OK** a **Vytvořit** skript uložíte.

## <a name="assign-a-powershell-script-policy"></a>Přiřazení zásad powershellových skriptů
1. V části **Powershellové skripty** vyberte skript, který chcete přiřadit, a potom zvolte **Spravovat** > **Přiřazení**.
  ![Podokno Přidat powershellový skript](./media/mgmt-extension-assignments.png)
 
2. Výběrem možnosti **Vybrat skupiny** zobrazte seznam dostupných skupin Azure AD. 
3. Vyberte jednu nebo více skupin, které obsahují uživatele, jejichž zařízení skript obdrží. Kliknutím na **Vybrat** přiřaďte zásady k vybraným skupinám.

> [!NOTE]
> - Koncoví uživatelé nemusí být kvůli spouštění powershellových skriptů přihlášení k zařízení. 
> - Cílem powershellových skriptů v Intune mohou být skupiny zabezpečení zařízení služby AAD.

Rozšíření správy Intune se s Intune synchronizuje jednou za hodinu. Po přiřazení zásad ke skupinám Azure AD se powershellový skript spustí a zobrazí se výsledky spuštění. 
 
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
