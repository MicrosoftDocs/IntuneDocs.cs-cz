---
title: "Správa licencí Intune | Dokumentace Microsoftu"
description: "Přiřaďte uživatelům licence k předplatnému Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
translationtype: Human Translation
ms.sourcegitcommit: ad13897fe7bbe4fe13167bb4ce7f558b436a7a90
ms.openlocfilehash: b6ab60eff3c65244290b7141e81a7b052dd790ed
ms.lasthandoff: 02/15/2017


---

# <a name="manage-intune-licenses"></a>Správa licencí Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

V tomto tématu najdou správci informace o tom, jak můžou uživatelům přiřadit licence, aby mohli začlenit zařízení do systému správy.

Aby se mohl uživatel přihlásit ke službě Intune a používat ji nebo zaregistrovat své zařízení v systému správy, musíte mu nejdříve přiřadit licenci k vašemu předplatnému Intune na [portálu služeb Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854).

Organizace, které používají Microsoft Enterprise Mobility + Security (EMS), můžou mít uživatele, kteří v balíčku EMS vyžadují jenom služby Azure Active Directory Premium nebo Intune. Pomocí [rutin PowerShellu pro Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx) můžete přiřadit jednu službu nebo sadu služeb. Další informace najdete v tématu [Správa licencí Intune pomocí PowerShellu](start-with-a-paid-subscription-to-microsoft-intune-step-4-posh.md).

## <a name="how-intune-licenses-are-assigned"></a>Přiřazování licencí služby Intune
Když jsou uživatelské účty synchronizované z místní služby Active Directory nebo ručně přidané do předplatného cloudových služeb prostřednictvím [portálu služeb Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854), není jim automaticky přiřazená licence Intune. Místo toho musí správce klienta Intune později uživatelský účet upravit a licenci uživateli přiřadit ručně z portálu Office služeb 365.

Pokud vaše předplatné sdílí Azure AD s jinými cloudovými službami přidruženými k vašemu předplatnému, máte také přístup k uživatelům přidaným do těchto služeb. Tito uživatelé nebudou mít licenci k [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], dokud jim tyto licence jednotlivě nepřiřadíte.

> [!TIP]
> Pokud je zakázaná možnost přiřadit nebo odvolat licenci pro [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], vaše předplatné může zahrnovat možnosti multilicence podobné možnostem, které jsou dostupné při používání sady [Enterprise Mobility Suite + Security](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx). Informace o tom, jak přiřadit nebo odvolat licenci najdete v dokumentaci k vašim možnostem licencování.

## <a name="assign-an-intune-user-license"></a>Přiřazení uživatelské licence pro Intune

[Portál služeb Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) můžete použít k ručnímu přidání cloudových uživatelů a přiřazení licencí účtům cloudových uživatelů i účtům, které se synchronizovaly z místní služby Active Directory do Azure AD.

1.  Přihlaste se na [portál služeb Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854) pomocí svých přihlašovacích údajů správce klienta a potom vyberte **Lidé** > **Všichni uživatelé**.

2.  Vyberte uživatelský účet, kterému chcete přiřadit uživatelskou licenci pro Intune, a potom vyberte **Microsoft Intune** (samostatně) nebo **Enterprise Mobility Suite**.

3.  Uživatelský účet má teď potřebná oprávnění k používání služby a registraci zařízení pro správu.

> [!NOTE]
> Jakmile uživatelé zaregistrují zařízení, zobrazí se v konzole.

### <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Použití PowerShellu k selektivní správě uživatelských licencí pro EMS
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

>[!div class="step-by-step"]

>[&larr; **Synchronizace uživatelů do Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organizace uživatelů a zařízení** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  

