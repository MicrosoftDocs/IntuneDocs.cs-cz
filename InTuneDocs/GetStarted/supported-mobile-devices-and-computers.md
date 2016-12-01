---
title: "Podporovaná mobilní zařízení a prohlížeče | Microsoft Intune"
description: "Mobilní zařízení a počítače, které Intune podporuje"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aeeccfa4-0f14-447e-a3df-c8435c8a4bb2
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 149f3a3310907d131affeaad4bd372aa60be9206
ms.openlocfilehash: 80541567c535cfeb7fca3eda3c9143f4b11d7abb


---

# <a name="supported-mobile-devices-and-computers"></a>Podporovaná mobilní zařízení a počítače

Zaregistrovat a spravovat je možné následující typy zařízení:

[!INCLUDE[mdm-supported-devices](../includes/mdm-supported-devices.md)]

Registrace zařízení poskytuje [tyto možnosti](/Intune/get-started/choose-how-to-manage-devices).

Další možností je spravovat počítače s Windows pomocí klientského počítačového softwaru Intune. Klientský software Intune pro počítače podporuje Windows 7 a novější, s výjimkou Windows 10 Home. Správa počítačů pomocí klientského softwaru přináší [tyto možnosti](https://docs.microsoft.com/intune/deploy-use/set-up-windows-device-management-with-microsoft-intune).

Zákazníci s Enterprise Management Suite můžou k registraci zařízení s Windows 10 používat také Azure Active Directory (Azure AD).

## <a name="microsoft-intune-supported-web-browsers"></a>Webové prohlížeče podporované Microsoft Intune

Různé úlohy správy vyžadují, abyste použili některý z následujících webů pro správu.

- [Portál Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)
- [Konzola pro správu Microsoft Intune](https://admin.manage.microsoft.com/)

> [!Note]
> Pro konzolu správce se nepodporuje Microsoft Edge ani mobilní prohlížeče, protože nepodporují [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). Konzola Intune se z prostředí Silverlight průběžně přesouvá. Všechny funkce správy mobilních zařízení a aplikací služby Intune budou nakonec [dostupné na novém portálu Microsoft Azure Portal](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

|Funkce Intune |Podporované prohlížeče|
|---------|---------|
|Konzola správce Intune     |  Internet Explorer 10 nebo novější<br /><br />Google Chrome (verze starší než verze 42)<br /><br />Mozilla Firefox s povoleným Silverlightem<br /><br />**Poznámka:** Microsoft Edge a mobilní prohlížeče nejsou podporované pro konzolu správce.                      
|Portál správy Office 365     |Všechny prohlížeče, včetně mobilních a spravovaných prohlížečů  |
|Web portálu společnosti     |**Na mobilních zařízeních:** používejte výchozí webový prohlížeč pro příslušnou podporovanou platformu.   <br /><br />**Na počítačích s Windows:** Internet Explorer 10 nebo novější nebo Microsoft Edge<br /><br />**Pro Mac OS X 10.9 nebo novější:** Apple Safari    |

> [!Note]
> Pro konzolu správce se nepodporuje Microsoft Edge ani mobilní prohlížeče, protože nepodporují [Microsoft Silverlight](https://msdn.microsoft.com/en-us/library/cc838158(v=vs.95).aspx). Konzola Intune se z prostředí Silverlight průběžně přesouvá. Všechny funkce správy mobilních zařízení a aplikací služby Intune budou nakonec [dostupné na novém portálu Microsoft Azure Portal](https://blogs.technet.microsoft.com/enterprisemobility/2015/11/17/enhancing-managed-mobile-productivity/).

### <a name="office-365-portalhttpgomicrosoftcomfwlinkplinkid698854"></a>[Portál Office 365](http://go.microsoft.com/fwlink/p/?LinkId=698854)

**Jako správce tenanta můžete používat tento portál ke správě svého předplatného**, včetně těchto úloh (pokud je umožňuje vaše role správce):

- Správa uživatelských účtů pro předplatné a konfigurace synchronizace adresářů z místní služby Active Directory.
- Správa skupin uživatelů, které se nazývají skupiny zabezpečení.
- Přiřazení licencí, které chcete použít pro uživatele Intune.
- Konfigurace názvu domény, který používáte se svým předplatným. Název domény definuje účet, ke kterému se uživatelé přihlašují.
- Správa údajů o fakturaci a nákupech ohledně vašeho předplatného, včetně počtu licencí, které máte, nebo velikosti úložiště cloudu, které můžete použít.
- Hledání odkazů pro zobrazení stavu služby Intune.
- Jakožto správce tenanta se můžete přihlásit k portálu Office 365 a spravovat předplatné i v případě, že váš účet nemá přiřazenou licenci k používání Intune.
- Všichni uživatelé, kteří mají licenci pro Intune, ale nejsou správci, můžou na tomto portálu obnovit své heslo účtu a upravovat svůj profil.
- Abyste měli přístup k portálu Office 365, musí mít váš účet stav přihlášení **Povoleno**. Tento stav je něco jiného než vlastnictví licence k předplatnému. Ve výchozím nastavení jsou všechny uživatelské účty nastavené na **Povoleno**.


### <a name="microsoft-intune-administrator-consolehttpsmanagemicrosoftcom"></a>[Konzola pro správu Microsoft Intune](https://manage.microsoft.com/)

**Jako správce služby můžete tento portál využívat ke správě každodenních operací** včetně:

- Nastavení zásad pro počítače a mobilní zařízení.
- Nahrání a nasazení softwaru, třeba aktualizací softwaru a aplikací.
- Správa služby Endpoint Protection na počítačích.
- Zobrazení stavu zařízení a spouštění sestav.
- Přihlaste se k tomuto portálu. Abyste se mohli přihlásit k tomuto portálu, musíte mít buď oprávnění správce služeb, nebo být správcem tenanta s rolí globálního správce.


K tomuto portálu se můžou přihlásit jen uživatelé, kteří mají oprávnění správce služeb nebo jsou správcem tenanta s rolí globálního správce. Abyste získali přístup ke konzole pro správu, musí mít váš účet licenci k používání Intune a stav registrace **Povoleno**.



<!--HONumber=Nov16_HO4-->


