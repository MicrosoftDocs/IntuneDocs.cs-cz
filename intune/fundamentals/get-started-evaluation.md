---
title: Co může Microsoft Intune dělat pro moji firmu
titleSuffix: ''
description: Běžné obchodní problémy, které Microsoft Intune pomáhají vyřešit.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 02/26/2019
ms.topic: overview
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure; get-started
ms.collection: M365-identity-device-management
ms.openlocfilehash: 845eb22522895e04f6ec4f46eda7a817e27a830c
ms.sourcegitcommit: 88b6e6d70f5fa15708e640f6e20b97a442ef07c5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/02/2019
ms.locfileid: "71731838"
---
# <a name="what-can-intune-do-for-my-company"></a>Jaké přínosy má Intune pro moji firmu?
Microsoft Intune je cloudová služba pro správu mobility velkých organizací (EMM), která pomáhá tomu, aby vaši pracovníci byli produktivní, a současně chrání vaše firemní data.

Intune vám umožňuje:

- Spravovat mobilní zařízení, která vaši pracovníci používají pro přístup k datům společnosti
- Spravovat mobilní aplikace, které vaši pracovníci používají
- Chránit informace vaší společnosti díky řízení způsobu, jak k nim vaši pracovníci přistupují a jak je sdílejí
- Zajistit, aby zařízení a aplikace splňovaly požadavky společnosti na zabezpečení

## <a name="common-business-problems-that-intune-helps-solve"></a>Běžné obchodní problémy, které Intune pomáhá vyřešit

* [Ochrana místních e-mailů a dat, aby se k nim mohlo přistupovat pomocí mobilních zařízení](common-scenarios.md#protecting-your-on-premises-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Ochrana e-mailů a dat Office 365, aby se k nim mohlo bezpečně přistupovat pomocí mobilních zařízení](common-scenarios.md#protecting-your-office-365-email-and-data-so-it-can-be-safely-accessed-by-mobile-devices)
* [Poskytnutí firemních telefonů pracovníkům](common-scenarios.md#issue-corporate-owned-phones-to-your-employees)
* [Nabídnutí programu Přineste si vlastní zařízení (BYOD) nebo programu osobních zařízení všem zaměstnancům](common-scenarios.md#offer-a-bring-your-own-device-program-to-all-employees)
* [Umožnění zabezpečeného přístupu zaměstnanců k Office 365 z nespravované veřejného terminálu](common-scenarios.md#enable-your-employees-to-securely-access-office-365-from-an-unmanaged-public-kiosk)
* [Poskytnutí sdílených tabletů s omezeným použitím pracovníkům, kteří provádějí konkrétní úlohy](common-scenarios.md#issue-limited-use-shared-tablets-to-your-employees)

## <a name="quickstarts"></a>Rychlý start

Chápeme, že zahájení správy mobilních zařízení může být obtížné. Existuje mnoho různých rozhodnutí, která budete muset udělat jménem své společnosti. Následující rychlé starty vám pomůžou začít s Intune a provádět některé běžné úkoly za minimální dobu.

Můžete postupovat podle zamýšleného pořadí **rychlých startů** pomocí obsahu na levé straně této stránky.

- [Bezplatné vyzkoušení Intune](free-trial-sign-up.md) – vytvořte si bezplatné předplatné, abyste mohli vyzkoušet Intune v testovacím prostředí.    
- [Vytvoření uživatele](quickstart-create-user.md) – přidáním uživatele do Intune mu povolíte přístup k firemním prostředkům na mobilních zařízeních.
- [Vytvořte skupinu](quickstart-create-group.md) – uspořádejte uživatele do skupin, abyste usnadnili správu zásad a aplikací, ke kterým mají přístup.
- [Nastavení automatického zápisu](../enrollment/quickstart-setup-auto-enrollment.md) – nastavte Intune, aby se zařízení automaticky zaregistrovala, když se na zařízení s Windows 10 přihlásí konkrétní uživatelé.
- [Registrace zařízení](../enrollment/quickstart-enroll-windows-device.md) – převzetí role uživatele Intune a registrace zařízení do Intune Pak se vraťte do Intune a potvrďte, že zařízení bylo úspěšně zaregistrováno.
- [Vytvoření zásady dodržování předpisů pro zařízení](../protect/quickstart-set-password-length-android.md) – vytvořte zásadu dodržování předpisů pro zařízení a pak k ní přiřaďte některou skupinu.
- [Odesílání oznámení na zařízení nesplňující požadavky](../protect/quickstart-send-notification.md) – pošle e-mailová oznámení členům svých pracovníků, kteří zařízení nedodržují předpisy, vytvořením a přiřazením zásad dodržování předpisů.
- [Přidání a přiřazení aplikace](../apps/quickstart-add-assign-app.md) – přidejte a přiřaďte svým zaměstnancům klientskou aplikaci.
- [Vytvoření a přiřazení zásady ochrany aplikací](../apps/quickstart-create-assign-app-policy.md) – vytvořte a přiřaďte zásadu ochrany aplikací ke klientské aplikaci na zařízení koncového uživatele.
- [Vytvoření a přiřazení vlastní role](create-custom-role.md) – vytvořte a přiřaďte vlastní roli se specifickými oprávněními pro oddělení operací zabezpečení. 
- [Vytvoření e-mailového profilu zařízení pro iOS](../configuration/quickstart-email-profile.md): Vytvoříte e-mailový profil pro zařízení s iOSem.

## <a name="prerequisites"></a>Požadované součásti

Než začnete, musíte mít aktivovaného správce Intune a účet tenanta. Vytvořte si bezplatné předplatné, abyste mohli [bezplatně vyzkoušet Intune](free-trial-sign-up.md) v testovacím prostředí. Aktuální předplatitelé můžou tyto aktivity také dokončit ve svém aktivním tenantovi. V těchto článcích Začínáme se předpokládá, že pracujete na testovacích zařízeních.

Abyste mohli všechny tyto úlohy Začínáme dokončit, musíte být globálními správci své organizace.

## <a name="intune-architecture"></a>Architektura Intune

Intune je součást řešení Enterprise Mobility + Security (EMS), která slouží ke správě mobilních zařízení a aplikací. Úzce se integruje s jinými součástmi řešení EMS, jako je Azure Active Directory (Azure AD) pro účely řízení přístupu a identit, a Azure Information Protection pro účely ochrany dat. Když ho použijete v sadě Office 365, můžete pracovníkům umožnit, aby byli produktivní na všech svých zařízeních a přitom měli chráněny informace vaší organizace.

![Diagram architektury vysoké úrovně pro Microsoft Intune](./media/get-started-evaluation/intunearchitecture.svg)

## <a name="next-steps"></a>Další kroky

[Začínáme s používáním Azure](tutorial-walkthrough-intune-portal.md) – pochopte principy Azure Portalu a zjistěte, jak můžete udělat změny na stránce, kterou vidíte.

## <a name="learn-more"></a>Další informace

- [Co je Intune?](what-is-intune.md)
- [Co je Azure Portal?](what-is-intune.md)
- [Životní cyklus zařízení a aplikací](device-lifecycle.md)
