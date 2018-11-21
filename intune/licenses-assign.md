---
title: Přiřazení licencí Microsoft Intune
description: Přiřazení licencí uživatelům, aby mohli zaregistrovat zařízení v Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 10/31/2017
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
search.appverid: MET150
ms.custom: intune-classic; get-started
ms.openlocfilehash: 4f19a7fa667c7f350e12ca469cb65f4250b1b95a
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52184688"
---
# <a name="assign-licenses-to-users-so-they-can-enroll-devices-in-intune"></a>Přiřazení licencí uživatelům, aby mohli zaregistrovat zařízení v Intune

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Ať už přidáváte uživatele ručně, nebo provádíte synchronizaci z místní služby Active Directory, musíte nejdřív všem uživatelům přiřadit licence Intune, aby mohli svá zařízení registrovat do Intune. Seznam licencí najdete v tématu [Licence zahrnující Intune](licenses.md).

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a>Přiřazení licence Intune v Centru pro správu Office 365

Pomocí [portálu služeb Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) můžete ručně přidat cloudové uživatele a přiřadit licence účtům cloudových uživatelů i účtům, které se synchronizovaly z místního adresáře služby Active Directory do Azure AD.

1. Přihlaste se na [portál služeb Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) pomocí svých přihlašovacích údajů správce tenanta a potom vyberte **Uživatelé** > **Aktivní uživatelé**.

2. Vyberte uživatelský účet, kterému chcete přiřadit uživatelskou licenci Intune, a potom vyberte **Licence na produkty** > **Upravit**.

3. Přepněte **Intune** nebo **Enterprise Mobility + Security** na **Zapnuto** a vyberte **Uložit**.

   ![Snímek obrazovky s portálem Office 365 – část Licence na produkty](./media/office-assign-license.png)

4. Uživatelský účet má teď oprávnění potřebná k používání služby a registraci zařízení pro správu.

> [!NOTE]
> Uživatelé se zobrazí v konzole pro správu teprve po registraci zařízení. Můžete také vybrat skupinu uživatelů a přidat nebo odebrat licence pro všechny najednou.

## <a name="assign-an-intune-license-by-using-azure-active-directory"></a>Přiřazení licence Intune pomocí Azure Active Directory

Licence Intune můžete uživatelům přiřadit také pomocí Azure Active Directory. Další informace najdete v článku věnovaném [licencování uživatelů v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal). 

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Přiřazení licencí uživatelům v Intune for Education pomocí služby SDS (School Data Sync)
Pokud patříte mezi vzdělávací organizace, můžete k přiřazení licencí na Intune for Education synchronizovaným uživatelům použít službu SDS (School Data Sync). Při nastavování profilu SDS stačí zaškrtnout políčko Intune for Education.  

![Snímek obrazovky s nastavením profilu SDS](./media/i4e-sds-profile-setup-setting.png)

Při přiřazování licence na Intune for Education ověřte, že je přiřazená také licence Intune A Direct.

![Snímek obrazovky s nastavením produktové licence](./media/i4e-set-licenses.png)

Další informace o službě SDS najdete v článku [Přehled služby SDS (School Data Sync)](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

## <a name="how-user-and-device-licenses-affect-access-to-services"></a>Vliv licencí pro uživatele a zařízení na přístup ke službám
* Každý **uživatel**, kterému přiřadíte softwarovou licenci pro uživatele, má přístup k online službám a souvisejícímu softwaru (včetně softwaru System Center) a může je používat ke správě aplikací a až 15 zařízení.
* Licence pro libovolná zařízení si můžete koupit odděleně od uživatelských licencí. Licence zařízení nemusí být přiřazené zařízením. Každé zařízení, které přistupuje k online službám a souvisejícímu softwaru (včetně softwaru System Center) a používá je, musí mít licenci zařízení.
* Pokud zařízení používá více než jeden uživatel, bude každý potřebovat softwarovou licenci pro zařízení nebo budou všichni uživatelé potřebovat softwarovou licenci pro uživatele.

## <a name="understanding-the-type-of-licenses-you-have-purchased"></a>Porozumění typu licencí, které jste zakoupili

Informace o předplatném určuje způsob, jakým jste zakoupili Intune:

- Pokud jste Intune zakoupili na základě smlouvy Enterprise, najdete informace o předplatném na portálu multilicencí v části **Předplatná**.
- Pokud jste Intune zakoupili přes poskytovatele Cloud Solution Provider, obraťte se na prodejce.
- Pokud jste Intune zakoupili přes CC# nebo na fakturu, budou vaše licence uživatelské.




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
