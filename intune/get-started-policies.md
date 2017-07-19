---
title: "Začínáme se zásadami"
titleSuffix: Intune on Azure
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/27/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 232ec25c34df5e71f70737ca5f0f8a2ef12a05f0
ms.sourcegitcommit: fd2e8f6f8761fdd65b49f6e4223c2d4a013dd6d9
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/03/2017
---
# <a name="getting-started-with-policies"></a>Začínáme se zásadami

Jedním z hlavních cílů, proč začít používat Intune, je registrace zařízení, abyste měli jistotu, že odpovídají zásadám společnosti. Zásady dodržování předpisů pomáhají spravovat nejen zvláštní typy zařízení, jako jsou firemní veřejné terminály, ale i osobní zařízení (vlastní zařízení uživatelů), tablety a zařízení bez uživatele.

![Řídicí panel pro dodržování předpisů s málo daty](/intune/media/generic-compliance-dashboard.png)

Zásady dodržování předpisů nabízejí následující možnosti správy mobilních zařízení:

* Regulace počtu zařízení, které každý uživatel může zaregistrovat
* Správa nastavení zařízení (například šifrování na úrovni zařízení, délka hesla nebo používání kamery)
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
2. V části **Hledat prostředky** vyhledejte **Intune**.
3. Vyberte **Dodržování předpisů zařízením**.
4. V okně **Dodržování předpisů zařízením** vyberte **Zásady**.
5. Vyberte **Vytvořit zásadu** a vyplňte podrobnosti jako **Název** a **Popis**. Jako **Platformu** vyberte **iOS**.
6. V nabídce **Nastavení** vyberte **Zabezpečení systému** a dejte přepínač **Vyžadovat heslo k odemknutí mobilních zařízení** do polohy **Vyžadovat**. Můžete také nastavit další pravidla, jako je **Minimální délka hesla**, **Požadovaný typ hesla** a **Počet nealfanumerických znaků v hesle**. Jakmile zásadu nastavíte, vyberte **OK**.
7. Vraťte se do okna **Vytvořit zásadu** a vyberte **Vytvořit**.
8. Jakmile zásadu vytvoříte, vyberte **Přiřazení** a přiřaďte ji testovací skupině. Vyberte testovací skupinu, ve které je váš testovací uživatel, a kliknutím na **Uložit** jí zásadu přiřaďte.
9. Počkejte pár minut. Na zaregistrovaném zařízení by se měla zobrazit výzva k zadání aktualizovaného hesla, aby zařízení dále vyhovovalo firemním zásadám. Nastavení také můžete zkontrolovat ručně v **aplikaci Portál společnosti pro iOS**, když klepnete na název zařízení a pak na tlačítko **Synchronizovat**.
