---
title: Registrace zařízení s Windows 10 v portálu společnosti Intune | Dokumentace Microsoftu
description: Návod k registraci zařízení s Windows 10 v portálu společnosti Intune
keywords: ''
author: lenewsad
ms.author: lanewsad
manager: dougeby
ms.date: 05/21/2019
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope:
- User help
ROBOTS: ''
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.collection: M365-identity-device-management
ms.openlocfilehash: 77b7f3adf4fa8675e3734f7eab8fbaa9391d952a
ms.sourcegitcommit: 7315fe72b7e55c5dcffc6d87f185f3c2cded9028
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/02/2019
ms.locfileid: "67527955"
---
# <a name="enroll-windows-10-devices-with-intune-company-portal"></a>Registrace zařízení s Windows 10 pomocí portálu společnosti Intune

Registrace zařízení s Windows 10 v rámci správy vaší organizace pomocí portálu společnosti Intune. Tento článek popisuje, jak zaregistrovat zařízení s Windows 10 verze 1607 a novější a Windows 10 verze 1511 a starší. Než začnete, ujistěte se, že jste [ověřit verzi na zařízení s](windows-enrollment-company-portal.md#find-windows-10-version-number) tak, aby provedením správným krokům.  

Windows 10 je podporována mezi různé typy zařízení, včetně desktop, telefonu a tabletu. Kroky registrace se stejný libovolným zařízením, které používáte. Vaše obrazovka může vypadat trochu liší od bitové kopie, uvidíte v tomto článku.  
</br>
> [!VIDEO https://www.youtube.com/embed/TKQxEckBHiE?rel=0]

## <a name="enroll-windows-10-version-1607-and-later-device"></a>Registrace Windows 10 verze 1607 a novější zařízení 
Tyto kroky popisují, jak zaregistrovat zařízení, která běží na Windows 10 verze 1607 a novější.  

1. Přejděte na **Start**. Pokud jste na zařízení s Windows 10 Mobile, pokračujte **všechny aplikace** seznamu.

2. Otevřít **nastavení** aplikace. Není-li aplikace snadno k dispozici v seznamu aplikací, přejděte na panel hledání a zadejte "nastavení".

3. Vyberte **Účty** > **Přístup do práce nebo do školy** > **Připojit**.  


    ![Vyberte možnost Nastavit pracovní nebo školní účet.](./media/w10-enroll-rs1-connect-to-work-or-school.png)  

4. Zadejte svou pracovní nebo školní e-mailovou adresu a pak vyberte **Další**.  


   ![Zadejte svůj pracovní nebo školní účet](./media/w10-enroll-rs1-set-up-work-or-school-account.png)  

5. Přihlaste se k Intune ze svého pracovního nebo školního účtu.  


    ![Přidat pracovní nebo školní účet](./media/w10-enroll-rs1-enter-your-credentials.png)  

    Nakonec uvidíte zprávu, že vaše společnost nebo škola registruje vaše zařízení.

6. Pokud vaše organizace vyžaduje, abyste nastavili PIN kód pro Windows Hello, budete vyzváni k zadání ověřovacího kódu. Zadejte kód a bude pokračovat až na obrazovce kroky k vytvoření PIN kódu.  

7. Na **všechno je připravené!** vyberte **Hotovo**. Právě jste svoje zařízení zaregistrovali.  

8. Chcete-li zkontrolovat připojení, přejděte zpět na **nastavení** > **účty** > **přístup do práce nebo do školy**.  Váš účet by teď měla být uvedena.  


    ![Ověření, zda bylo připojení správně nastaveno](./media/w10-enroll-rs1-validate-successful-enrollment.png)  

Stále nemáte přístup k pracovním nebo školním e-mailům, souborům nebo jiným datům? Zjistěte, jak [Poradce při potížích účet](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).  

## <a name="enroll-windows-10-version-1511-and-earlier-device"></a>Registrace Windows 10 verze 1511 a starší zařízení  
Tyto kroky popisují, jak zaregistrovat zařízení, která běží na Windows 10 verze 1511 a starší.  

1. Přejděte na **Start**. Pokud jste na zařízení s Windows 10 Mobile, pokračujte **všechny aplikace** seznamu.

2. Otevřít **nastavení** aplikace. Není-li aplikace snadno k dispozici v seznamu aplikací, přejděte na panel hledání a zadejte "nastavení".

3. Vyberte **účty** > **účtu**.  


    ![Vyberte svůj účet.](./media/W10-enroll-2-accounts-your-account.png)  

5. Vyberte **Přidat pracovní nebo školní účet**.  


    ![Vyberte možnost přidat pracovní nebo školní účet.](./media/w10-enroll-3-add-work-school-acct.png)  

6. Přihlaste se pomocí přihlašovacích údajů svého pracovního nebo školního účtu.  


    ![Když se přihlásíte](./media/W10-enroll-4-sign-in.png)  

Stále nemáte přístup k pracovním nebo školním e-mailům, souborům nebo jiným datům? Zjistěte, jak [řešit problémy související s účtem](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-your-account) během registrace.  

## <a name="it-administrator-support"></a>Podpora pro správce IT   

Pokud jste správcem IT a spustit potíží při registraci zařízení, najdete v článku [problémy registrace zařízení Poradce při potížích s Windows v Microsoft Intune](https://support.microsoft.com/help/4469913). Tento článek uvádí běžné chyby, jejich příčiny a kroky k jejich řešení. 

## <a name="next-steps"></a>Další postup  
Pokud potřebujete pomoc s aplikace portál společnosti nebo registrace, obraťte se na vaše organizace IT tým podpory. Jeho kontaktní údaje najdete na [webu portál společnosti](https://go.microsoft.com/fwlink/?linkid=2010980). Přihlaste se k webu pomocí svého pracovního nebo školního účtu.  

 

