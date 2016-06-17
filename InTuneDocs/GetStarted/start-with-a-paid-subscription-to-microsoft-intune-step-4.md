---
# required metadata

title: Správa licencí Intune | Microsoft Intune
description:
keywords:
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Správa licencí Intune
Než se bude moct uživatel přihlásit ke službě Intune a používat ji nebo registrovat své zařízení ke správě, musí mít licenci k vašemu předplatnému této služby. Uživatelé, kteří mají licenci, jsou členy skupiny uživatelů [!INCLUDE[wit_firstref](../includes/wit_firstref_md.md)]. Tato skupina zahrnuje všechny uživatele, kteří mají licenci k používání předplatného. **Každá uživatelská licence podporuje registraci až pěti zařízení.**.

## Přiřazování licencí služby Intune
Když jsou uživatelské účty synchronizovány z místní služby Active Directory nebo ručně přidány do předplatného cloudových služeb prostřednictvím portálu účtů, není jim automaticky přiřazena licence Intune. Místo toho musí správce tenanta Intune později uživatelský účet upravit a licenci uživateli přiřadit ručně z portálu účtů.

Pokud vaše předplatné sdílí Azure AD s jinými cloudovými službami přidruženými vašemu předplatnému, máte také přístup k uživatelům přidaným do těchto služeb. Tito uživatelé nebudou mít licenci k [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)], dokud jim tyto licence jednotlivě nepřiřadíte.

> [!TIP]
> Pokud je možnost přiřadit licenci k [!INCLUDE[wit_nextref](../includes/wit_nextref_md.md)] nebo ji odvolat neaktivní, může vaše předplatné zahrnovat možnosti multilicencí, třeba možnosti dostupné v případě používání sady [Enterprise Mobility Suite](https://www.microsoft.com/en-us/server-cloud/enterprise-mobility/overview.aspx). Informace o tom, jak přiřadit nebo odvolat licenci najdete v dokumentaci k vašim možnostem licencování.

## Přiřazení uživatelské licence pro Intune

Službu **[!INCLUDE[wit_icp_2](../includes/wit_icp_2_md.md)]** můžete použít k ručnímu přidání cloudových uživatelů a přiřazení licencí účtům cloudových uživatelů i účtům, které se synchronizovaly z místní služby Active Directory do Azure AD.

1.  Přihlaste se na portál účtů Intune pomocí svých přihlašovacích údajů správce tenanta.

2.  Vyberte uživatelský účet, kterému chcete přiřadit uživatelskou licenci pro Intune, a zaškrtněte políčko **Microsoft Intune** ve vlastnostech uživatelského účtu.

3.  Uživatelský účet bude nyní přidán do skupiny uživatelů Microsoft Intune, která uděluje uživatelům oprávnění k používání služby a registraci svých zařízení do správy.

### Použití PowerShellu k selektivní správě uživatelských licencí pro EMS
Organizace, které používají sadu Enterprise Mobility Suite (EMS) Microsoftu, mohou mít uživatele, kteří v balíčku EMS vyžadují jenom služby Azure Active Directory Premium nebo Intune. Pomocí [rutin PowerShellu pro Azure Active Directory](https://msdn.microsoft.com/library/jj151815.aspx) můžete přiřadit jednu službu nebo jejich podmnožinu.. 

Chcete-li selektivně přiřadit uživatelské licence pro služby EMS, otevřete PowerShell jako správce v počítači, kde je instalovaný [modul Azure Active Directory pro Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule). PowerShell můžete nainstalovat v místním počítači nebo na serveru služby AD FS.

Musíte vytvořit novou definici SKU licence, která se vztahuje pouze na požadované plány služeb. Chcete-li to provést, zakažte plány, které nechcete použít. Můžete například vytvořit definici SKU licence, která nepřiřazuje licenci pro Intune. Chcete-li zobrazit seznam dostupných služeb, zadejte:
 
    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus 

Spuštěním následujícího příkazu můžete vyloučit plán služby Intune. Stejnou metodu můžete použít k rozšíření na celou skupinu zabezpečení nebo můžete použít podrobnější filtry. 

**Příklad 1**
Vytvořte nového uživatele na příkazovém řádku a přiřaďte mu licenci EMS bez povolení části licence pro Intune:

    Connect-MsolService 
        
    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS 
    

Ověřte pomocí:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Příklad 2**
Zakažte část licence EMS pro Intune uživateli, kterému má licenci už přiřazenou:

    Connect-MsolService 
    
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS
    
    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS
 
Ověřte pomocí:
 
    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### Další kroky
Gratulujeme! Právě jste dokončili krok 4 *úvodní příručky Intune*.
>[!div class="step-by-step"]

>[&larr; **Synchronizace uživatelů do Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-2.md)     [**Organizace uživatelů a zařízení** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)  


<!--HONumber=May16_HO1-->


