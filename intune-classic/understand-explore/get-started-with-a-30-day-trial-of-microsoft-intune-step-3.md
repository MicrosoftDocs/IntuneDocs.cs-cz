---
title: "Vytvoření skupin pro uspořádání uživatelů a zařízení v bezplatné zkušební verzi| Dokumentace Microsoftu"
description: "Vytvoření skupin zařízení a skupin uživatelů při registraci bezplatné 30denní zkušební verze Microsoft Intune"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 11/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7162cad3-5c14-43f3-a760-833ffd7786b1
ms.suite: ems
ms.custom: intune-classic
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: f6a5926876bdd7224d0e9bfef55aa86f51c87aff
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="create-groups-to-organize-evaluation-subscription-users-and-devices"></a>Vytvoření skupiny pro uspořádání uživatelů a zařízení pro testovací předplatné

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Skupiny v Intune poskytují flexibilitu pro správu zařízení a uživatelů. Můžete nastavit skupiny podle potřeb vaší organizace (třeba podle zeměpisné polohy, oddělení nebo vlastností hardwaru) a použít je k provádění řady úloh správy se škálováním od nastavení zásad pro sadu uživatelů po nasazení aplikací na sadu zařízení.

## <a name="create-a-device-group"></a>Vytvoření skupiny zařízení
Použijte skupiny zařízení k nasazení softwaru a aktualizací a ke konfiguraci zásad nastavení agenta služby Microsoft Intune a brány Windows Firewall. Můžete třeba nastavit skupinu Moje zařízení zkušební verze podle těchto kroků:

1.  V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Přehled** &gt; **Vytvořit skupinu**.

2.  Jako hodnotu **Název skupiny** zadejte text „Moje zařízení zkušební verze“, ze seznamu nadřazených skupin vyberte **Všechna zařízení** a potom zvolte **Další**.

3.  Na stránce **Definovat kritéria členství** vyberte **Všechna zařízení** , což znamená, že skupina zahrnuje mobilní zařízení i počítače.

4.  Na stránce **Definovat přímé členství** vyberte **Další**. Pokud jste dřív vytvořili skupinu, která neobsahuje všechna zařízení, a chtěli byste do nové skupiny přidat určitá zařízení, můžete to udělat tady.

5.  Na stránce **Souhrn** si prohlédněte akce, které se provedou, a pak zvolte **Dokončit**.

Nově vytvořenou skupinu najdete v seznamu **Skupiny** v pracovním prostoru **Skupiny** v části **Všechna zařízení**. Tady můžete skupinu i upravit nebo odstranit.

## <a name="create-a-user-group"></a>Vytvoření skupiny uživatelů
Skupiny uživatelů můžete použít k nasazení softwaru a zásad zařízení. Můžete třeba nastavit skupinu Moji uživatelé zkušební verze podle těchto kroků:

1.  V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Přehled** &gt; **Vytvořit skupinu**.

2.  Jako hodnotu **Název skupiny** zadejte text „Moji uživatelé zkušební verze“, ze seznamu nadřazených skupin vyberte **Všichni uživatelé** a potom zvolte **Další**.

3.  Na stránce **Definovat kritéria členství** nastavte možnost **Začít členství ve skupině s** na **Všichni uživatelé v nadřazené skupině**.

4.  Vedle **Vyloučit členy z těchto skupin zabezpečení** vyberte **Procházet** a potom vyberte **Správce společnosti**. Toto vyloučení vám umožní spravovat skupinu Moji uživatelé zkušební verze bez vlivu na účet správce společnosti (taky označovaný jako správce klienta).

5.  Na stránce **Definovat přímé členství** vyberte **Další**. Tady nemusíte nic dělat, protože chcete, aby skupina Moji uživatelé zkušební verze obsahovala všechny uživatele kromě správce společnosti.

6.  Na stránce **Souhrn** si prohlédněte akce, které se provedou, a pak zvolte **Dokončit**.

Nově vytvořenou skupinu najdete v seznamu **Skupiny** v pracovním prostoru **Skupiny** v části **Všichni uživatelé**. Tady můžete skupinu i upravit nebo odstranit.

Další informace o používání skupin najdete v tématu [Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](/intune-classic/Deploy-Use/use-groups-to-manage-users-and-devices-with-microsoft-intune).

## <a name="next-steps"></a>Další kroky
[Vytvoření zásad](get-started-with-a-30-day-trial-of-microsoft-intune-step-4.md)  

