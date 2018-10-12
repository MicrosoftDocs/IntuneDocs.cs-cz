---
title: 'Rychlý start: Přidání zásady dodržování předpisů pro zařízení s Windows 10'
description: V tomto rychlém startu vytvoříte zásady, které chrání podniková data a umožňují spravovat přístup zařízení koncových uživatelů k prostředkům společnosti. Pak přiřaďte zásady skupinám.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 09/21/2018
ms.topic: quickstart
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 73e1e0a27d128d567a924e6f2b343026b11f1a44
ms.sourcegitcommit: 27eed5aba5c8bfafb079171081b68f75a6cbffaf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 09/22/2018
ms.locfileid: "46581578"
---
# <a name="quickstart-add-a-device-compliance-policy-for-a-windows-10-device"></a>Rychlý start: Přidání zásady dodržování předpisů pro zařízení s Windows 10
Zásada dodržování předpisů Intune pro zařízení s Windows určuje pravidla a nastavení, které musí zařízení s Windows splňovat, aby bylo považováno za dodržující předpisy. Tyto zásady [podmíněného přístupu](https://docs.microsoft.com/intune/conditional-access) můžete použít k povolení nebo zablokování přístupu k prostředkům společnosti. Můžete také získat sestavy zařízení a provádět akce v případě nedodržování předpisů.

V tomto rychlém startu vytvoříte zásadu dodržování předpisů pro zařízení s Windows 10 a pak této zásadě přiřadíte skupinu zařízení.

Pokud nemáte předplatné Intune, [zaregistrujte si bezplatný zkušební účet](free-trial-sign-up.md).

## <a name="prerequisites"></a>Požadavky
- K dokončení tohoto rychlého startu potřebujete napřed [vytvořit uživatele](quickstart-create-user.md) a [vytvořit skupinu](quickstart-create-group.md).


## <a name="sign-in-to-intune"></a>Přihlášení k Intune
Přihlaste se k [Intune](https://aka.ms/intuneportal) jako globální správce nebo správce služby Intune.

## <a name="create-a-device-compliance-policy"></a>Vytváření zásad dodržování předpisů pro zařízení
1. Vyberte **Dodržování předpisů zařízením** > **Zásady** > **Vytvořit zásadu**.
2. Do pole **Název** zadejte **Dodržování předpisů ve Windows 10** a do pole **Popis** zadejte **Ukázková zásada dodržování předpisů pro Windows 10**.
3. V poli **Platforma** vyberte **Windows 10 a novější**.
4. V **Nastavení** vyberte **Zabezpečení systému** a dejte přepínač **Vyžadovat heslo k odemknutí mobilních zařízení** do polohy **Vyžadovat**. Po nastavení zásady vyberte **OK**.
   ![Zásada dodržování předpisů](/intune/media/quickstart-create-policy/compliance-policy.png)
5. Zavřete podokno **Zásady dodržování předpisů ve Windows 10**. 
6. V podokně **Vytvořit zásadu** vyberte **Vytvořit**. Tímto krokem vytvoříte zásadu, která se zobrazí v seznamu **Dodržování předpisů zařízením** > **Zásady**.
7. Vyberte novou zásadu a zvolte **Přiřazení**. Můžete zahrnout nebo vyloučit skupiny zabezpečení služby Azure Active Directory (AD).
8. Pokud chcete zobrazit stávající skupiny zabezpečení z Azure AD, zvolte **Vybrané skupiny**. Pokud chcete zásadu nasadit uživatelům ve skupině, vyberte **Contoso Testers** (Testeři Contosa) a zvolte **Uložit**. Pokud jste tuto skupinu v podokně [Vytvořit skupinu](quickstart-create-group.md) nevytvořili, můžete použít jinou skupinu, kterou vyberete. 

## <a name="clean-up-resources"></a>Vyčištění prostředků
Až tuto zásadu nebudete potřebovat, odstraňte ji. Uděláte to tak, že vyberete zásadu **dodržování předpisů ve Windows 10** a kliknete na **Odstranit**. 

## <a name="next-steps"></a>Další kroky
V tomto rychlém startu jste vytvořili jednoduchou zásadu dodržování předpisů pro zařízení a přiřadili jste ji. Pokud chcete zaregistrovat zařízení s Windows 10, která budou příjemcem této zásady, pokračujte rychlým startem, ve kterém nastavíte automatickou registraci. 
 
> [!div class="nextstepaction"]
> [Nastavení automatické registrace](quickstart-setup-auto-enrollment.md)