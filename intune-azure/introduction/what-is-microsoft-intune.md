---
title: "Úvod do Intune na portálu Azure Portal Preview"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Získejte základní informace o Intune na portálu Azure Portal Preview a o tom, jak vám pomůže se správou zařízení."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 04/24/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: 8b2bd3ecba0b597bc742ea08872ffe8fc58155cf
ms.openlocfilehash: 92e07a49205ffaf287fc3aa2da6a6376b75fda4f
ms.lasthandoff: 04/24/2017


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Úvod do Microsoft Intune na portálu Azure Portal Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune se přesouvá na portál Azure Portal, což znamená, že pracovní postupy a funkce, na které jste zvyklí, se změní.
Tento nový portál nabízí ukázku nových a aktualizovaných funkcí portálu Azure Portal, na kterém můžete spravovat mobilní zařízení, počítače a aplikace svojí organizace.
Všechny funkce Intune se nakonec přesunou na Azure, mnoho úloh Intune ale můžete na portálu Azure Portal dělat už dnes. Protože toto nové prostředí je ve verzi Preview, nemusí některé funkce na tomto portálu ještě existovat. Podrobnosti najdete v části [Co je nového](#what's-new).

> [!IMPORTANT]
> **Ještě nový portál nevidíte?**<br>
> Verzi Preview jsme už začali zavádět do vybraných tenantů. Existující tenanti se do nového prostředí začnou migrovat začátkem kalendářního roku 2017. Před migrací vašeho tenanta obdržíte oznámení v Centru zpráv Office.


Dokumentaci nového produktu najdete v této knihovně, která bude v průběhu verze Preview nepřetržitě aktualizována. Pokud máte nějaké návrhy, poskytněte nám prosím zpětnou vazbu v komentářích k tomuto tématu. Rádi bychom znali vaše názory.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

K tomu nejdůležitějšímu v novém prostředí patří:

- Integrovaná konzola pro všechny součásti EMS (Enterprise Mobility + Security)
- Konzola HTML postavená na webových standardech
- Podpora rozhraní Microsoft Graph API pro automatizaci mnoha akcí
- Skupiny Azure Active Directory (AD) pro zajištění kompatibility mezi všemi aplikacemi Azure
- Podpora většiny moderních prohlížečů

Pokud hledáte dokumentaci konzoly Intune Classic, podívejte se do [knihovny dokumentace Intune](https://docs.microsoft.com/en-us/intune/).

## <a name="before-you-start"></a>Než začnete

K použití Intune na portálu Azure Portal potřebujete účet správce a tenanta Intune. [Zaregistrujte si účet](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20), pokud ho ještě nemáte.

## <a name="supported-web-browsers-for-the-azure-portal"></a>Prohlížeče, které portál Azure Portal podporuje

Azure Portal funguje na většině moderních počítačů PC, Mac a tabletech. Mobilní telefony nejsou podporované.
V současnosti se podporují následující prohlížeče:

- Microsoft Edge (nejnovější verze)
- Microsoft Internet Explorer 11
- Safari (nejnovější verze, jen Mac)
- Chrome (nejnovější verze)
- Firefox (nejnovější verze)

Nejnovější informace o podporovaných prohlížečích najdete na portálu [Azure Portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).

## <a name="whats-in-this-library"></a>Co je v této knihovně?

Do této dokumentace je promítnuto rozložení portálu Intune, abyste mohli snadněji najít informace, které potřebujete.

![Úlohy portálu Azure Portal](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a>Úvod a začínáme
Tato část obsahuje informace o [novinkách](/intune-azure/introduction/whats-new), [známých problémech](/intune-azure/introduction/known-issues-in-the-intune-preview), [možnostech získání podpory](/intune-azure/introduction/how-to-get-support-for-microsoft-intune) a o tom, jak [začít pracovat s bezplatnou zkušební verzí](/intune-azure/introduction/sign-up-free-trial-microsoft-intune) Intune.
### <a name="plan-and-design"></a>Plánování a navrhování
Informace, které vám usnadní [plánování a navrhování](/intune-azure/plan-and-design/get-started) prostředí Intune
### <a name="device-enrollment"></a>Registrace zařízení
[Zjistěte, jak zajistíte správu zařízení přes Intune](/intune-azure/enroll-devices/what-is).
### <a name="device-compliance"></a>Dodržování předpisů zařízení
[Definujte úroveň dodržování předpisů pro svá zařízení a dostávejte zprávy o všech zařízeních, která je nedodržují](/intune-azure/set-device-compliance/what-is-device-compliance).
### <a name="device-configuration"></a>Konfigurace zařízení
[Informace o profilech, s jejichž pomocí můžete na spravovaných zařízeních nakonfigurovat nastavení a funkce](/intune-azure/configure-devices/what-are-device-profiles)
### <a name="devices"></a>Zařízení
[Inventář a sestavy vám poskytnou přehled o spravovaných zařízeních](/intune-azure/manage-devices/what-is).
### <a name="mobile-apps"></a>Mobilní aplikace
[Informace o publikování, správě, konfiguraci a ochraně aplikací](/intune-azure/manage-apps/what-is-app-management)
### <a name="conditional-access"></a>Podmíněný přístup
[Omezte přístup ke službám Exchange na základě určených podmínek](/intune-azure/conditional-access/what-is-conditional-access).
### <a name="on-premises-access"></a>Místní přístup
[Konfigurace přístupu k Exchangi ActiveSync a místnímu Exchangi](/intune/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a>Uživatelé
[Další informace o uživatelích zařízení, která spravujete, a řazení prostředků do skupin](/intune-azure/manage-users/what-is)
### <a name="groups"></a>Skupiny
[Informace o tom, jak můžete používat skupiny Azure Active Directory s Intune](/intune-azure/manage-users/get-started-with-groups)
### <a name="intune-roles"></a>Role Intune
[Určete, kdo může v Intune provádět různé akce a na koho se tyto akce vztahují](/intune-azure/access-control/role-based-access-control). Můžete buď použít předdefinované role, které vyhovují běžným situacím v Intune, nebo si vytvořit své vlastní role.
### <a name="software-updates"></a>Aktualizace softwaru
[Informace o tom, jak nakonfigurovat aktualizace softwaru pro zařízení s Windows 10](/intune-azure/configure-devices/how-to-configure-windows-update-for-business)



## <a name="whats-new"></a>Co je nového

[Zjistěte, co nového tato verze Preview přináší](/intune-azure/introduction/whats-new).

