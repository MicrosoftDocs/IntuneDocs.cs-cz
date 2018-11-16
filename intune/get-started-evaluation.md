---
title: Začínáme s Microsoft Intune
titleSuffix: ''
description: Projděte si sérii krátkých praktických rychlých startů a zjistěte, jak Intune funguje.
keywords: ''
author: dougeby
ms.author: dougeby
manager: dougeby
ms.date: 11/12/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 6bfab644-c1e2-4154-a254-e95b9a1d75f2
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure; get-started
ms.openlocfilehash: 261d15a2731ef6b388eba0f0c6d5cd025e8c3509
ms.sourcegitcommit: d8edd1c3d24123762dd6d14776836df4ff2a31dd
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/13/2018
ms.locfileid: "51576717"
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

Chápeme, že začátky související se správou mobilních zařízení můžou být obtížné, protože za svou firmu musíte udělat spoustu různých rozhodnutí. Následující rychlé starty vám pomůžou začít pracovat s Intune a provádět některé běžné úlohy v co nejkratším čase.

Pomocí obsahu na levé straně této stránky můžete postupovat v zamýšleném pořadí **rychlých startů**.

- [Bezplatné vyzkoušení Intune](free-trial-sign-up.md) – vytvořte si bezplatné předplatné, abyste mohli vyzkoušet Intune v testovacím prostředí.    
- [Vytvoření uživatele](quickstart-create-user.md) – přidáním uživatele do Intune mu povolíte přístup k firemním prostředkům na mobilních zařízeních.
- [Vytvoření skupiny](quickstart-create-group.md) – když uživatele uspořádáte do skupin, usnadníte si správu zásad a aplikací, ke kterým mají přístup.
- [Nastavení automatické registrace](quickstart-setup-auto-enrollment.md) – nastavte automatickou registraci zařízení v Microsoft Intune, když se konkrétní uživatelé přihlásí k zařízením s Windows 10.
- [Registrace zařízení](quickstart-enroll-windows-device.md) – převezměte roli uživatele Intune a zaregistrujte své zařízení v Microsoft Intune. Pak se vraťte do Intune a toto zaregistrované zařízení potvrďte.
- [Vytvoření zásady dodržování předpisů pro zařízení](quickstart-set-password-length-android.md) – vytvořte zásadu dodržování předpisů pro zařízení a pak k ní přiřaďte některou skupinu.
- [Odeslání oznámení zařízením nedodržujícím předpisy](quickstart-send-notification.md) – vytvořením a přiřazením zásady dodržování předpisů odešlete e-mailové oznámení zaměstnancům, jejichž zařízení nedodržují předpisy.
- [Přidání a přiřazení aplikace](quickstart-add-assign-app.md) – přidejte a přiřaďte svým zaměstnancům klientskou aplikaci.
- [Vytvoření a přiřazení zásady ochrany aplikací](quickstart-create-assign-app-policy.md) – vytvořte a přiřaďte zásadu ochrany aplikací ke klientské aplikaci na zařízení koncového uživatele.
- [Vytvoření a přiřazení vlastní role](quickstart-create-custom-role.md) – vytvořte a přiřaďte vlastní roli se specifickými oprávněními pro oddělení operací zabezpečení. 
- [Vytvoření e-mailového profilu zařízení pro iOS](quickstart-email-profile.md): Vytvoříte e-mailový profil pro zařízení s iOSem.

## <a name="prerequisites"></a>Požadavky

Než začnete, musíte mít aktivovaný účet správce Intune a účet tenanta. Vytvořte si bezplatné předplatné, abyste mohli [bezplatně vyzkoušet Intune](free-trial-sign-up.md) v testovacím prostředí. Stávající odběratelé také mohou k těmto činnostem použít živého tenanta. Tyto články ze sekce Začínáme předpokládají, že pracujete na testovacích zařízeních.

Abyste mohli všechny tyto úlohy Začínáme dokončit, musíte být globálními správci své organizace.

## <a name="intune-architecture"></a>Architektura Intune

Intune je součást řešení Enterprise Mobility + Security (EMS), která slouží ke správě mobilních zařízení a aplikací. Úzce se integruje s jinými součástmi řešení EMS, jako je Azure Active Directory (Azure AD) pro účely řízení přístupu a identit, a Azure Information Protection pro účely ochrany dat. Při použití v kombinaci s Office 365 vašim pracovníkům umožňuje, aby byli produktivní na všech zařízeních, a současně chrání informace vaší organizace.

![Diagram architektury vysoké úrovně pro Microsoft Intune](/intune/media/intunearchitecture.svg)

## <a name="next-steps"></a>Další kroky

[Začínáme s používáním Azure](get-started-azure.md) – pochopte principy Azure Portalu a zjistěte, jak můžete udělat změny na stránce, kterou vidíte.

## <a name="learn-more"></a>Další informace

* [Co je Intune?](introduction-intune.md)
* [Co je Azure Portal?](what-is-intune.md)
* [Životní cyklus zařízení a aplikací](introduction-device-app-lifecycles.md)