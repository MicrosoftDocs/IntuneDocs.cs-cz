---
title: "Správa powershellových skriptů v Intune u zařízení s Windows 10"
titlesuffix: Azure portal
description: "Přečtěte si, jak nahrát powershellové skripty do Intune, aby je bylo možné používat v zařízeních s Windows 10."
keywords: 
author: dougeby
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 768b6f08-3eff-4551-b139-095b3cfd1f89
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1bdd9002c70ea8d9e8b16b73d4d8416eeec3341b
ms.sourcegitcommit: 833b1921ced35be140f0107d0b4205ecacd2753b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/04/2018
---
# <a name="manage-powershell-scripts-in-intune-for-windows-10-devices"></a>Správa powershellových skriptů v Intune u zařízení s Windows 10
Rozšíření správy Intune umožňuje nahrát powershellové skripty do Intune, aby je bylo možné spouštět v zařízeních s Windows 10. Rozšíření správy doplňuje funkce správy mobilních zařízení (MDM) s Windows 10 a usnadňuje přechod na moderní správu.

## <a name="moving-to-modern-management"></a>Přechod na moderní správu
Prostředí IT pro koncové uživatele prochází digitální transformací. Klasické tradiční informační technologie se zaměřují na platformy pro jednotlivá zařízení, na zařízení vlastněná firmami, uživatele, kteří pracují z kanceláře, a celou řadu manuálních reaktivních IT procesů. Moderní pracoviště ale umožňuje používat platformy pro více zařízení vlastněná uživateli i firmami, uživatelům pracovat odkudkoli a zajistit automatické a proaktivní IT procesy. 

Služby správy mobilních zařízení, jako je třeba Microsoft Intune, mohou spravovat zařízení s Windows 10 pomocí protokolu MDM. Integrovaný klient správy Windows 10 je schopen komunikovat s Intune a provádět úlohy podnikové správy. Pomůže vám při přechodu na moderní správu v zařízeních s Windows 10. V současné době ale ve správě mobilních zařízení pro Windows 10 nejsou dostupné určité funkce, které byste mohli potřebovat. Jedná se třeba o rozšířenou konfiguraci zařízení, řešení potíží nebo správu starších aplikací Win 32. Pro tyto funkce můžete v zařízení s Windows 10 používat softwarového klienta Intune. Nebudete ale moct používat nové funkce, které správa mobilních zařízení pro Windows 10 poskytuje. [Srovnání rozdílů mezi softwarovým klientem Intune a správou mobilních zařízení pro Windows 10](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison)

Rozšíření správy Intune doplňuje integrované funkce správy mobilních zařízení pro Windows 10. Můžete si vytvořit powershellové skripty, které vám budou poskytovat požadované funkce, a spouštět je v zařízeních s Windows 10. Můžete si třeba vytvořit powershellový skript, který nainstaluje starší aplikaci Win32 do zařízení s Windows 10, nahrát ho do Intune, přiřadit ho ke skupině Azure AD (Active Directory) a spustit ho v zařízení s Windows 10. Potom můžete monitorovat stav spuštění skriptu na zařízení s Windows 10 od začátku až do konce.

## <a name="prerequisites"></a>Požadavky
Rozšíření správy Intune vyžaduje splnění následujících požadavků:
- Zařízení musí být připojená k Azure AD.
- Zařízení musí používat Windows 10 verze 1607 nebo novější.

## <a name="create-a-powershell-script-policy"></a>Vytvoření zásad powershellových skriptů 
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
4. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Powershellové skripty**.
5. V okně **Powershellové skripty** zvolte **Přidat skript**.
6. V okně **Přidat powershellový skript** zadejte **Název** a **Popis** powershellového skriptu.
7. V části **Umístění skriptu** vyhledejte powershellový skript. Skript musí být menší než 10 kB (ASCII) nebo 5 kB (Unicode).
8. Zvolte **Konfigurovat** a potom zvolte, zda chcete skript spouštět pomocí přihlašovacích údajů uživatele v zařízení (**Ano**) nebo v kontextu systému (**Ne**). Skript se standardně spouští v kontextu systému. Možnost **Ano** vyberte, pokud nechcete, aby se skript spouštěl v kontextu systému. 
  ![Okno Přidat powershellový skript](./media/mgmt-extension-add-script.png)
9. Zvolte, zda musí být skript podepsán důvěryhodným vydavatelem (**Ano**). Standardně nejsou stanovené žádné požadavky na to, aby byl skript podepsán. 
10. Klikněte na **OK** a potom kliknutím na **Vytvořit** skript uložte.

## <a name="assign-a-powershell-script-policy"></a>Přiřazení zásad powershellových skriptů
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
4. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Powershellové skripty**.
5. V okně **Powershellové skripty** vyberte skript, který chcete přiřadit, a potom zvolte **Spravovat** > **Přiřazení**.
  ![Okno Přidat powershellový skript](./media/mgmt-extension-assignments.png)
 
6. Výběrem možnosti **Vybrat skupiny** zobrazte seznam dostupných skupin Azure AD. 
7. Vyberte jednu nebo více skupin, které obsahují uživatele, jejichž zařízení bude přijímat tento skript, a pak klikněte na **Vybrat**, aby se zásady přiřadily vybraným skupinám.

Rozšíření správy Intune se s Intune synchronizuje jednou za hodinu. Po přiřazení zásad ke skupinám Azure AD se powershellový skript spustí a zobrazí se výsledky spuštění. 
 
## <a name="monitor-run-status-for-powershell-scripts"></a>Monitorování stavu spuštění powershellových skriptů
Na portálu Azure Portal můžete monitorovat stav spuštění powershellových skriptů u uživatelů a zařízení.
1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Konfigurace zařízení**.
4. V okně **Konfigurace zařízení** zvolte **Spravovat** > **Powershellové skripty**.
5. V okně **Powershellové skripty** vyberte skript, který chcete monitorovat, zvolte **Monitorovat** a potom zvolte jednu z následujících sestav:
   - **Stav zařízení**
   - **Stav uživatele**
