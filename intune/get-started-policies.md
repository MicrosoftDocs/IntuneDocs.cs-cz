---
title: Začínáme se zásadami v Microsoft Intune
titlesuffix: ''
description: Vytvořte zásady k ochraně podnikových dat a správě zařízení, která koncoví uživatelé používají pro přístup k firemním prostředkům.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/26/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 661ef25085892e299e45156f27b3d9db959577d4
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="get-started-with-creating-policies"></a>Začínáme s vytvářením zásad

Jedním z hlavních cílů, když začínáte používat Intune, je registrace zařízení, abyste měli jistotu, že dodržují zásady společnosti. Zásady dodržování předpisů pomáhají spravovat nejen zvláštní typy zařízení, jako jsou firemní veřejné terminály, ale i osobní zařízení (vlastní zařízení uživatelů), tablety a zařízení bez uživatele.

![Řídicí panel pro dodržování předpisů s málo daty](/intune/media/generic-compliance-dashboard.png)

Spravujte mobilní zařízení v těchto oblastech pomocí zásad dodržování předpisů:

* Regulace počtu zařízení, které každý uživatel může zaregistrovat
* Správa nastavení zařízení (například šifrování na úrovni zařízení, délka hesla nebo používání fotoaparátu)
* Dodávání aplikací, e-mailových profilů, profilů VPN apod.
* Vyhodnocení kritérií na úrovni zařízení, které se týkají zásad dodržování předpisů o zabezpečení

Zásady dodržování předpisů vytváříte pro každou platformu zvlášť. V tomto cvičení se budeme držet iOS. Pro zařízení s iOSem jsou k dispozici následující zásady:

* Konfigurace PIN kódu nebo hesla
* Šifrování zařízení
* Zařízení s jailbreakem
* e-mailový profil
* Minimální verze operačního systému
* Maximální verze operačního systému

__Jak vytvořím zásadu?__

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. Vyberte **Dodržování předpisů zařízením**.
4. V podokně **Dodržování předpisů zařízením** vyberte **Zásady**.
5. Vyberte **Vytvořit zásadu** a vyplňte podrobnosti jako **Název** a **Popis**. 
6. Jako **Platformu** vyberte **iOS**.
6. V nabídce **Nastavení** vyberte **Zabezpečení systému** a dejte přepínač **Vyžadovat heslo k odemknutí mobilních zařízení** do polohy **Vyžadovat**. Můžete také nastavit další pravidla, jako je **Minimální délka hesla**, **Požadovaný typ hesla** a **Počet nealfanumerických znaků v hesle**. Jakmile zásadu nastavíte, vyberte **OK**.
7. Vraťte se do podokna **Vytvořit zásadu** a vyberte **Vytvořit**.
8. Jakmile zásadu vytvoříte, vyberte **Přiřazení** a přiřaďte ji testovací skupině. Vyberte testovací skupinu, ve které je váš testovací uživatel, a kliknutím na **Uložit** jí zásadu přiřaďte.
9. Počkejte pár minut. Na zaregistrovaném zařízení by se měla zobrazit výzva k zadání aktualizovaného hesla, aby zařízení dále vyhovovalo firemním zásadám. Nastavení také můžete zkontrolovat ručně v **aplikaci Portál společnosti pro iOS**, když klepnete na název zařízení a pak na tlačítko **Synchronizovat**.

## <a name="next-steps"></a>Další kroky

[Začínáme s registrací zařízení](get-started-enroll.md) – projděte si celý proces registrace zařízení s iOS a zjistěte, jak registrace probíhá.

## <a name="learn-more"></a>Další informace

* [Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md)
* [Běžné způsoby používání zásad podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md)
