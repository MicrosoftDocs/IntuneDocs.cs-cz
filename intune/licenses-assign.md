---
title: "Přiřazení licencí Intune"
description: "Přiřaďte uživatelům licence k předplatnému Intune."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 06/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 317fad8beb708a10a4dbf81a04f03c2faab41925
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2017
---
# <a name="assign-intune-licenses-to-your-user-accounts"></a>Přiřazení licencí Intune uživatelským účtům

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Ať už přidáváte uživatele ručně, nebo provádíte synchronizaci z místní služby Active Directory, musíte nejdřív všem uživatelům přiřadit licence Intune, aby mohli svá zařízení registrovat do Intune.

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a>Přiřazení licence Intune v Centru pro správu Office 365

Pomocí [portálu služeb Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) můžete ručně přidat cloudové uživatele a přiřadit licence účtům cloudových uživatelů i účtům, které se synchronizovaly z místního adresáře služby Active Directory do Azure AD.

1.  Přihlaste se na [portál služeb Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) pomocí svých přihlašovacích údajů správce tenanta a potom vyberte **Uživatelé** > **Aktivní uživatelé**.

2.  Vyberte uživatelský účet, kterému chcete přiřadit uživatelskou licenci Intune, a potom vyberte **Licence na produkty** > **Upravit**.

3.  Přepněte **Intune** nebo **Enterprise Mobility + Security** na **Zapnuto** a vyberte **Uložit**.

  ![Obrázek přiřazení licence k produktu na portálu Office 365](./media/office-assign-license.png)

4. Uživatelský účet má teď oprávnění potřebná k používání služby a registraci zařízení pro správu.

> [!NOTE]
> Uživatelé se zobrazí v konzole pro správu teprve po registraci zařízení. Můžete také vybrat skupinu uživatelů a přidat nebo odebrat licence pro všechny najednou.

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Přiřazení licencí uživatelům v Intune for Education pomocí služby SDS (School Data Sync)
Pokud patříte mezi vzdělávací organizace, můžete k přiřazení licencí na Intune for Education synchronizovaným uživatelům použít službu SDS (School Data Sync). Při nastavování profilu SDS stačí zaškrtnout políčko Intune for Education.  

![Obrázek nastavení profilu SDS](./media/i4e-sds-profile-setup-setting.png)

Při přiřazování licence na Intune for Education ověřte, že je přiřazená také licence Intune A Direct.

![Obrázek nastavení produktové licence](./media/i4e-set-licenses.png)

Další informace o službě SDS najdete v článku [Přehled služby SDS (School Data Sync)](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US).

## <a name="how-user-and-device-licenses-affect-access-to-services"></a>Vliv licencí pro uživatele a zařízení na přístup ke službám
* Každý **uživatel**, kterému přiřadíte softwarovou licenci pro uživatele, má přístup k online službám a souvisejícímu softwaru (včetně softwaru System Center) a může je používat ke správě aplikací a až 15 zařízení.
* Každé **zařízení**, kterému přiřadíte softwarovou licenci pro zařízení, má přístup k online službám a souvisejícímu softwaru (včetně softwaru System Center), které na zařízení může používat libovolný počet uživatelů.
* Pokud zařízení používá více než jeden uživatel, bude každý potřebovat softwarovou licenci pro zařízení nebo budou všichni uživatelé potřebovat softwarovou licenci pro uživatele.

## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Použití PowerShellu k selektivní správě uživatelských licencí pro EMS
Organizace, které používají Microsoft Enterprise Mobility + Security (dříve Enterprise Mobility Suite), můžou mít uživatele, kteří v balíčku EMS vyžadují jenom služby Azure Active Directory Premium nebo Intune. Pomocí [rutin PowerShellu pro Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx) můžete přiřadit jednu službu nebo podmnožinu služeb.

Pokud chcete selektivně přiřadit uživatelské licence pro služby EMS, otevřete PowerShell jako správce v počítači, kde je instalovaný [modul Azure Active Directory pro Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule). PowerShell můžete nainstalovat na místní počítač nebo na server služby AD FS.

Musíte vytvořit novou definici SKU licence, která se vztahuje jenom na požadované plány služeb. To provedete tak, že zakážete plány, které nechcete použít. Můžete třeba vytvořit definici SKU licence, která nepřiřazuje licenci pro Intune. Pokud chcete zobrazit seznam dostupných služeb, zadejte:

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

Spuštěním následujícího příkazu můžete vyloučit plán služby Intune. Stejnou metodu můžete použít k rozšíření na celou skupinu zabezpečení nebo můžete použít podrobnější filtry.

**Příklad 1**<br>
Vytvořte nového uživatele na příkazovém řádku a přiřaďte mu licenci EMS bez povolení části licence pro Intune:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Ověřte pomocí:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Příklad 2**<br>
Zakažte část licence EMS pro Intune uživateli, kterému má licenci už přiřazenou:

    Connect-MsolService

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

Ověřte pomocí:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)
