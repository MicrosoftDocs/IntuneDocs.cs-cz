---
title: "Úvod do Intune na portálu Azure Portal Preview | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Získejte základní informace o Intune na portálu Azure Portal Preview a o tom, jak vám pomůže se správou zařízení."
keywords: 
author: robstackmsft
ms.author: robstack
nmanager: angrobe
ms.date: 01/08/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.reviewer: 
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 1024d2a33d843c628ffbb68f7b01a5d511191e7e
ms.openlocfilehash: f7f6dd79531d8d69eda3ed80bbb1cddf2692ab81


---


# <a name="introduction-to-microsoft-intune-in-the-azure-portal-preview"></a>Úvod do Microsoft Intune na portálu Azure Portal Preview


[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Microsoft Intune se přesouvá na portál Azure Portal, což znamená, že pracovní postupy a funkce, na které jste zvyklí, se změní.
Tento nový portál nabízí ukázku nových a aktualizovaných funkcí portálu Azure Portal, na kterém můžete spravovat mobilní zařízení, počítače a aplikace své organizace.
Všechny funkce Intune se nakonec přesunou na Azure, určité úlohy Intune ale můžete na portálu Azure Portal dělat už dnes. Protože toto nové prostředí je ve verzi Preview, nemusí některé funkce na tomto portálu ještě existovat. Podrobnosti najdete v části [Co je nového ve verzi Preview](#what's-new-in-the-preview).

> [!IMPORTANT]
> **Ještě nový portál nevidíte?**<br>
> Verzi Preview jsme už začali zavádět do vybraných tenantů. Existující tenanti se do nového prostředí začnou migrovat začátkem kalendářního roku 2017. Před migrací vašeho tenanta obdržíte oznámení v Centru zpráv Office. Pokud máte jakékoli dotazy k časovému plánu migrace vašeho tenanta, kontaktujte náš tým pro migraci na adrese [intunegrps@microsoft.com](mailto:intunegrps@microsoft.com).


Dokumentaci nového produktu najdete v této knihovně, která bude v průběhu verze Preview nepřetržitě aktualizována. Pokud máte nějaké návrhy, poskytněte nám prosím zpětnou vazbu v komentářích k tomuto tématu. Rádi bychom znali vaše názory.

<!--- You can view the new Intune technical preview console in Azure at [portal.azure.com]. --->

K tomu nejdůležitějšímu v novém prostředí patří:

- Integrovaná konzola pro všechny součásti EMS (Enterprise Mobility + Security)
- Konzola HTML postavená na webových standardech
- Podpora rozhraní Microsoft Graph API pro automatizaci mnoha akcí
- Skupiny Azure AD pro zajištění kompatibility mezi všemi aplikacemi Azure
- Podpora většiny moderních prohlížečů

Pokud hledáte dokumentaci konzoly Intune Classic, podívejte se do [knihovny dokumentace Intune](https://docs.microsoft.com/en-us/intune/).

## <a name="before-you-start"></a>Než začnete

K použití Intune na portálu Azure Portal potřebujete účet správce a tenanta Intune. Účet si můžete zaregistrovat [zde](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20).

## <a name="supported-web-browsers-for-the-azure-portal"></a>Prohlížeče, které portál Azure Portal podporuje

Azure Portal funguje na většině moderních počítačů PC, Mac a tabletech. Mobilní telefony nejsou podporované.
V současnosti se podporují následující prohlížeče:

- Microsoft Edge (nejnovější verze)
- Microsoft Internet Explorer 11
- Safari (nejnovější verze, jen Mac)
- Chrome (nejnovější verze)
- Firefox (nejnovější verze)

Nejnovější informace o podporovaných prohlížečích najdete [zde](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).

## <a name="whats-in-this-library"></a>Co je v této knihovně?

Do této dokumentace je promítnuto rozložení portálu Intune, abyste mohli snadněji najít informace, které potřebujete.

![Úlohy portálu Azure Portal](./media/azure-portal-workloads.png)

<!--- ### Plan and design
Information to help you plan and design your Intune environment.
[Read more](/intune-azure/plan-and-design/get-started) --->
### <a name="enroll-devices"></a>Registrace zařízení
Zjistěte, jak zajistíte správu zařízení přes Intune.
[Další informace](/intune-azure/enroll-devices/what-is)
### <a name="devices--groups"></a>Zařízení a skupiny
Inventář a sestavy vám poskytnou přehled o spravovaných zařízeních.
[Další informace](/intune-azure/manage-devices/what-is)
### <a name="manage-users"></a>Správa uživatelů
Zjistěte informace o uživatelích zařízení, která spravujete.
[Další informace](/intune-azure/manage-users/what-is)
### <a name="manage-apps"></a>Správa aplikací
Obsahuje informace o publikování, správě, konfiguraci a ochraně aplikací.
[Další informace](/intune-azure/manage-apps/what-is-app-management)
### <a name="configure-devices"></a>Konfigurace zařízení
Obsahuje informace o profilech, s jejichž pomocí můžete na spravovaných zařízeních nakonfigurovat nastavení a funkce.
[Další informace](/intune-azure/configure-devices/what-are-device-profiles)
### <a name="set-device-compliance"></a>Nastavení dodržování předpisů zařízením
Definujte úroveň dodržování předpisů pro svá zařízení a dostávejte zprávy o všech zařízeních, která je nedodržují. [Další informace](/intune-azure/set-device-compliance/what-is-device-compliance)
### <a name="conditional-access"></a>Podmíněný přístup
Omezte přístup ke službám Exchange na základě určených podmínek.
[Další informace](/intune-azure/conditional-access/what-is-conditional-access)
### <a name="access-control"></a>Řízení přístupu
Zde můžete určit, kdo může v Intune provádět různé akce a na koho se tyto akce vztahují. Můžete buď použít předdefinované role, které vyhovují běžným situacím v Intune, nebo si vytvořit své vlastní role.
[Další informace](/intune-azure/access-control/role-based-access-control)


## <a name="whats-new"></a>Co je nového

[Zjistěte, co nového tato verze Preview přináší](/intune-azure/introduction/whats-new).


<!--HONumber=Feb17_HO1-->


