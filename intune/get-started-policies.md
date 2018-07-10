---
title: Začínáme se zásadami v Microsoft Intune – Azure | Microsoft Docs
description: Vytvořte zásady k ochraně podnikových dat a správě zařízení, která koncoví uživatelé používají pro přístup k firemním prostředkům. Pak přiřaďte zásady skupinám.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 06/04/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d7fa1b596a1800971919cfc0ab3e94d2d16ec328
ms.sourcegitcommit: afda8a0fc0f615e976b18ddddf81d56d7ae3566e
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36271520"
---
# <a name="get-started-with-creating-policies"></a>Začínáme s vytvářením zásad

Zásady Intune slouží k registraci zařízení. Umožňují kontrolovat, zda zařízení dodržují zásady společnosti. Zásady dodržování předpisů pomáhají spravovat zvláštní typy zařízení, jako jsou firemní terminály, osobní zařízení (vlastní zařízení uživatelů), tablety a zařízení bez uživatele.

![Řídicí panel pro dodržování předpisů s málo daty](/intune/media/generic-compliance-dashboard.png)

Zásady dodržování předpisů můžete použít ke správě mobilních zařízení, včetně:

* Regulace počtu zařízení zaregistrovaných uživatelem v Intune
* Správy nastavení zařízení, jako je šifrování na úrovni zařízení, délka hesla a použití fotoaparátu
* Dodávání aplikací, e-mailových profilů, profilů VPN apod.
* Vyhodnocení kritérií na úrovni zařízení, které se týkají zásad dodržování předpisů o zabezpečení

Zásady dodržování předpisů se vytvářejí pro každou platformu, např. pro iOS, Android, Windows a další. V tomto cvičení použijeme iOS. Pro zařízení s iOSem jsou k dispozici následující zásady:

* Konfigurace PIN kódu nebo hesla
* Šifrování zařízení
* Zařízení s jailbreakem
* e-mailový profil
* Minimální verze operačního systému
* Maximální verze operačního systému

## <a name="create-a-policy"></a>Vytvoření zásady

1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
3. Vyberte **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**.
4. Zadejte **název** a **popis** zásady. 
5. Jako **platformu** vyberte **iOS**.
6. V **Nastavení** vyberte **Zabezpečení systému** a dejte přepínač **Vyžadovat heslo k odemknutí mobilních zařízení** do polohy **Vyžadovat**. 

    Můžete nastavit i další pravidla, například: 
    - **Minimální délka hesla**
    - **Požadovaný typ hesla**
    - **Počet nealfanumerických znaků v hesle**
    
    Po nastavení zásady vyberte **OK**.
  
7. Vraťte se k **Vytvořit zásadu** a vyberte **Vytvořit**. Tímto krokem vytvoříte zásadu, která se zobrazí v seznamu **Dodržování předpisů zařízením** > **Zásady**.
8. Vyberte novou zásadu a zvolte **Přiřazení**. Můžete zahrnout nebo vyloučit skupiny zabezpečení služby Azure Active Directory (AD).
Pokud chcete zobrazit stávající skupiny zabezpečení Azure AD, zvolte Vybrané skupiny. Můžete vybrat skupiny uživatelů, na které chcete zásady použít, a pak pomocí **Uložit** tyto zásady uživatelům nasadit.

Registrované zařízení vás po několika minutách vyzve k zadání aktuálního hesla, aby odpovídalo novým podnikovým zásadám. Aktualizaci můžete zkontrolovat ručně v **aplikaci Portál společnosti pro iOS**. Otevřete aplikaci Portál společnosti, vyberte název zařízení a pak vyberte **Synchronizovat**.

> [!NOTE]
> Nové zásady, použité pro dynamickou skupinu zařízení, se u všech zařízení ve skupině mohou projevit až za osm hodin.

## <a name="next-steps"></a>Další kroky

[Začínáme s registrací zařízení](get-started-enroll.md) – projděte si celý proces registrace zařízení s iOS a zjistěte, jak registrace probíhá.

## <a name="learn-more"></a>Další informace

* [Monitorování zásad dodržování předpisů zařízením v Intune](compliance-policy-monitor.md)
* [Běžné způsoby používání zásad podmíněného přístupu s Intune](conditional-access-intune-common-ways-use.md)
