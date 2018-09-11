---
title: Úvod do Intune na Azure Portalu
titlesuffix: ''
description: Microsoft Intune je k dispozici na portálu Azure Portal. Přečtěte si základní informace o Intune na portálu Azure Portal.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/28/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: get-started
ms.openlocfilehash: 3f8f0dce416c943dbc244d0e2a4366b12b305708
ms.sourcegitcommit: 18f51ae8291b57562921e40fc364a5a60a59b139
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/09/2018
ms.locfileid: "44253778"
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a>Úvod do Microsoft Intune na portálu Azure Portal


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Podobně jako jiné služby Azure je Microsoft Intune k dispozici na portálu Azure Portal. Po výběru **Intune** na portálu Azure Portal můžete spravovat mobilní zařízení, počítače a aplikace vaší organizace.

> [!NOTE]
> Pokud jste používali dřívější verzi Microsoft Intune, můžou pro vás být užitečné následující informace:
>     * Téma [Kde v Azure najdu svoje funkce](ui-changes.md) obsahuje referenční informace, kde můžete vidět konkrétní pracovní postupy a uživatelská rozhraní, která se změnila s přechodem na Azure.
>     * V tématu [Skupiny klasického Intune na portálu Azure](groups-get-started.md) je vysvětlené, jaký dopad má přechod na skupiny zabezpečení Azure Active Directory na správu skupin.

Mezi nejdůležitější prvky prostředí Microsoft Intune na portálu Azure Portal patří:

- Integrovaná konzola pro všechny součásti EMS (Enterprise Mobility + Security)
- Konzola HTML postavená na webových standardech
- Podpora rozhraní Microsoft Graph API pro automatizaci mnoha akcí
- Skupiny Azure Active Directory (AD) pro zajištění kompatibility mezi všemi aplikacemi Azure
- Podpora většiny moderních prohlížečů

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

## <a name="microsoft-intune-in-the-azure-portal"></a>Microsoft Intune na portálu Azure Portal

[Azure Portal](https://portal.azure.com) je místo, kde najdete službu Microsoft Intune. Azure obsahuje několik služeb, z nichž většinu nemusíte pravidelně používat. Stručný návod pro přizpůsobení prostředí portálu najdete v tématu [Začínáme s Intune na portálu Azure Portal](get-started-azure.md).

## <a name="the-microsoft-intune-documentation"></a>Dokumentace k Microsoft Intune

Toto téma, stejně jako celá dokumentace k Microsoft Intune, se průběžně aktualizuje. Pokud máte nějaké návrhy, poskytněte nám zpětnou vazbu v komentářích k tomuto tématu. Rádi bychom znali vaše názory.

Tato dokumentace odráží rozložení Microsoft Intune na portálu Azure Portal (zobrazeno níže), abyste mohli snadněji najít informace, které potřebujete.

![Úlohy portálu Azure Portal](./media/azure-portal-workloads.png)

### <a name="documentation-guide"></a>Průvodce dokumentací

Pomocí následující tabulky můžete rychle vyhledat hlavní oblasti Microsoft Intune a seznámit se s nimi.

| Oddíl                                                      | Popis                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [Úvod a začínáme](introduction-intune.md)       | Vysvětlení základních principů Intune, například:<br /> - běžná řešení<br /> - způsob, jak Microsoft Intune funguje<br /> - správa zařízení v Intune<br /> - správa aplikací v Intune<br /> - správa mobility velkých organizací (EMM) s registrací zařízení i bez ní                                                         |
| [Plánování a navrhování](planning-guide.md)                         | Pokyny, které vám pomůžou úspěšně naplánovat a navrhnout prostředí Microsoft Intune                                                                                                                                                                                                             |
| [Registrace zařízení](device-enrollment.md)                    | Vysvětlení, jak Microsoft Intune usnadňuje správu zařízení pracovníků díky registraci zařízení do služby Intune. Zařízení pracovníků lze registrovat několika způsoby.                                                                                                         |
| [Dodržování předpisů zařízeními](device-compliance.md)                    | Zásady dodržování předpisů zařízeními v Intune definují pravidla a nastavení, která jsou pro zařízení povinná, pokud má toto zařízení vyhovět zásadám Microsoft Intune. Příkladem takových zásad je třeba vyžadování hesla pro přístup k zařízení, šifrování zařízení nebo vyžadování minimální verze operačního systému. |
| [Konfigurace zařízení](device-profiles.md)                   | Po vytvoření profilů zařízení v Microsoft Intune můžete nakonfigurovat nastavení a funkce na všech zařízeních, která spravujete. Můžete například nakonfigurovat funkce, jako jsou oznámení, sdílení dat, e-mailová podpora, připojení wi-fi, certifikáty a Endpoint Protection.              |
| [Zařízení](device-management.md)                              | Můžete zajistit, aby spravovaná zařízení poskytovala prostředky, které vaši koncoví uživatelé potřebují k práci, a současně aby data společnosti byla chráněná před možnými riziky. Můžete zařízení spravovat pomocí kontroly inventáře zařízení pracovníků a prováděním akcí se vzdáleným zařízením.                                                      |
| [Mobilní aplikace](app-management.md)                             | Vysvětlení, jak přidat, nasadit, monitorovat, nakonfigurovat a chránit aplikace                                                                                                                                                                                                                             |
| [Podmíněný přístup](conditional-access.md)                  | Můžete definovat podmínky pro zařízení a pro aplikace, které budou chránit přístup k firemním datům.                                                                                                                                                                                                            |
| [Uživatelé](users-add.md)                                        | Přečtěte si, jak můžete přidat uživatele zařízení a aplikací, které spravujete.                                                                                                                                                                                                                                           |
| [Skupiny](groups-get-started.md)                              | Přečtěte si, jak můžete vytvořit a spravovat skupiny v Intune. Pomocí skupin můžete rychle přiřadit zařízení a nakonfigurovat zásady ochrany aplikací.                                                                                                                                             |
| [Role Intune](role-based-access-control.md)                 | Přečtěte si, jak určovat, kdo může v Intune provádět různé akce a jak se tyto akce používají. Můžete buď použít předdefinované role, které vyhovují běžným situacím v Intune, nebo si vytvořit své vlastní role.                                                                                 |
| [Aktualizace softwaru](windows-update-for-business-configure.md) | Přečtěte si informace o tom, jak nakonfigurovat aktualizace softwaru pro zařízení s Windows 10.                                                                                                                                                                                                                                  |

## <a name="whats-new"></a>Co je nového

Informace o nejnovějších funkcích Microsoft Intune najdete v části [Co je nového](whats-new.md).
