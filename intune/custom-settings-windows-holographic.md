---
title: "Vlastní nastavení Microsoft Intune pro zařízení s Windows Holographic for Business"
titlesuffix: 
description: "Podívejte se na nastavení, která je možné použít ve vlastním profilu Windows Holographic for Business."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 3/6/2018
ms.article: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b95d891d1dfaecbce182fde4a2221255a7e1eb06
ms.sourcegitcommit: 4db0498342364f8a7c28995b15ce32759e920b99
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/08/2018
---
# <a name="microsoft-intune-custom-device-settings-for-devices-running-windows-holographic-for-business"></a>Vlastní nastavení zařízení Microsoft Intune pro zařízení s Windows Holographic for Business

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 **Vlastní** profil Microsoft Intune pro Windows Holographic for Business použijte, pokud chcete nasadit nastavení OMA-URI (Open Mobile Alliance Uniform Resource Identifier), s jehož pomocí se dají ovládat funkce na zařízeních. Windows Holographic for Business zpřístupňuje řadu nastavení poskytovatelů konfiguračních služeb (CSP). Základní informace o CSP najdete v [úvodu o poskytovatelích konfiguračních služeb (CSP) pro IT specialisty](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers). Konkrétní poskytovatele CSP, které podporuje Windows Holographic, najdete v části [Poskytovatelé CSP podporovaní ve Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens).

Pokud hledáte konkrétní nastavení, mějte na paměti, že [profil omezení zařízení s Windows Holographic for Business](device-restrictions-windows-holographic.md) obsahuje řadu integrovaných nastavení, která nevyžadují, abyste zadali vlastní hodnoty.

1. Začněte podle pokynů v tématu [Jak nakonfigurovat vlastní nastavení zařízení v Microsoft Intune](custom-settings-configure.md).
2. Pokud chcete přidat jedno nebo více nastavení OMA-URI, v části **Vytvořit profil** zvolte **Nastavení**.
3. V části **Vlastní nastavení OMA-URI** klikněte na **Přidat**, abyste mohli přidat novou hodnotu. Můžete také kliknout na **Exportovat** a vytvořit seznam všech hodnot, které jste nakonfigurovali v souboru hodnot oddělených čárkami (CSV).
4. Ke každému nastavení OMA-URI, které chcete přidat, zadejte následující informace:
    - **Název nastavení** – Zadejte jedinečný název nastavení OMA-URI, který vám pomůže ho rozpoznat v seznamu nastavení.
    - **Popis nastavení** – Volitelně zadejte popis nastavení.
    - **Datový typ** – Vybírejte z těchto typů:
        - **Řetězec**
        - **Řetězec (XML)**
        - **Datum a čas**
        - **Celé číslo**
        - **Číslo s plovoucí desetinnou čárkou**
        - **Logická hodnota**
    - **OMA-URI (rozlišuje velká a malá písmena)** – Uveďte, který OMA-URI chcete nastavit.
    - **Hodnota** – Zadejte hodnotu, která má být k uvedenému OMA-URI přidružena.
1. Až to budete mít, vraťte se do části **Vytvořit profil** a klikněte na **Vytvořit**.
Profil se vytvoří a zobrazí se v seznamu profilů.

## <a name="recommended-custom-settings"></a>Doporučená vlastní nastavení

Následující nastavení jsou užitečná pro zařízení s Windows Holographic for Business.


|Název nastavení|OMA-URI|Datový typ  |
|---------|---------|---------|
|[AllowFastReconnect](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-authentication#authentication-allowfastreconnect)|./Vendor/MSFT/Policy/Config/Authentication/AllowFastReconnect|Celé číslo<br>0 – Nepovoluje se.<br>1 – Povoluje se (výchozí).|
|[AllowVPN](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-settings#settings-allowvpn)|./Vendor/MSFT/Policy/Config/Settings/AllowVPN|Celé číslo<br>0 – Nepovoluje se.<br>1 – Povoluje se (výchozí).|
|[AllowUpdateService](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-allowupdateservice)|./Vendor/MSFT/Policy/Config/Update/AllowUpdateService|Celé číslo<br>0 – Služba aktualizací se nepovoluje. <br>1 – Služba aktualizací se povoluje (výchozí).|
|[UpdateServiceURL](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-updateserviceurl)|./Vendor/MSFT/Policy/Config/Update/UpdateServiceUrl|Řetězec<br>URL – Zařízení vyhledá aktualizace na serveru WSUS na zadané adrese URL.<br>Nenakonfigurováno – Zařízení vyhledá aktualizace ve službě Microsoft Update.|
|[RequireUpdatesApproval](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-requireupdateapproval)|./Vendor/MSFT/Policy/Config/Update/RequireUpdateApproval|Celé číslo<br>0 – Není nakonfigurováno. Zařízení nainstaluje všechny použitelné aktualizace.<br>1 – Zařízení nainstaluje jenom aktualizace, které jsou použitelné a jsou také v seznamu schválených aktualizací. Pokud chce oddělení IT řídit nasazení aktualizací na zařízení, třeba když je před nasazením nutné testování, nastavte tuto zásadu na 1.|
|[ApprovedUpdates](https://docs.microsoft.com/windows/client-management/mdm/update-csp)|./Vendor/MSFT/Update/ApprovedUpdates<br><br>**Důležité**<br>Musíte si přečíst smlouvy EULA k aktualizacím a přijmout je jménem vašich koncových uživatelů. Pokud tak neučiníte, dojde k porušení právních nebo smluvních závazků.|Uzel pro schválení aktualizací a přijetí smlouvy EULA jménem koncového uživatele|
[ApplicationLaunchRestrictions](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|./Vendor/MSFT/AppLocker/ApplicationLaunchRestrictions/*Grouping*/*ApplicationType*/Policy<br><br>**Důležité**<br>V článku o AppLocker CSP se používají příklady XML, které obsahují pomocné řídicí znaky. Pokud chcete nakonfigurovat nastavení s vlastními profily Intune, je nutné použít prostý XML.|Řetězec<br>Další informace najdete v článku o [AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp). 

## <a name="how-to-find-the-policies-you-can-configure"></a>Jak najít zásady, které můžete nakonfigurovat

Úplný seznam všech poskytovatelů konfiguračních služeb (CSP), které Windows Holographic podporuje, najdete v části [Poskytovatelé CSP podporovaní ve Windows Holographic](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#hololens). Ne všechna nastavení jsou kompatibilní se všemi verzemi Windows Holographic. V tabulce v článku týkajícím se Windows zjistíte, které verze se pro jednotlivé CSP podporují.

Intune navíc nepodporuje všechna nastavení uvedená v tomto článku. Pokud chcete zjistit, jestli Intune podporuje vámi požadované nastavení, otevřete si článek týkající se daného nastavení. Jednotlivé stránky nastavení zobrazují podporované operace. Aby dané nastavení fungovalo s Intune, musí podporovat operace **Přidat** nebo **Nahradit**.
