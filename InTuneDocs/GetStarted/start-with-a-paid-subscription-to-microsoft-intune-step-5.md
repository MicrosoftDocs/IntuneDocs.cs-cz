---
title: "Vytvoření skupiny pro uspořádání uživatelů a zařízení | Microsoft Intune"
description: 
keywords: 
author: Staciebarker
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ms.reviewer: jeffgilb
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed26d65b98a0ae1bbc4fbac682fb53fddd50b4e5
ms.openlocfilehash: 00ac59ffe219109dd48c47e59de9ecf588f07344


---


# Vytvoření skupiny pro uspořádání uživatelů a zařízení
Skupiny v Intune poskytují flexibilitu pro správu zařízení a uživatelů. Můžete nastavit skupiny podle potřeb vaší organizace (třeba podle zeměpisné polohy, oddělení nebo vlastností hardwaru) a použít je k provádění široké škály úloh správy od nasazení zásad pro víc uživatelů až po nasazení aplikací na skupinu zařízení.

Skupiny zařízení i uživatelů se vytvářejí v pracovním prostoru SKUPINY konzoly pro správu Intune.

![Pracovní prostor skupin konzoly pro správu](./media/groups.png)


> [!TIP]
> Další informace o používání skupin najdete v tématu [Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](/intune/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).


## Vytvoření skupiny zařízení
Skupiny zařízení použijte k nasazení aplikací a aktualizací a konfiguraci dalších funkcí. Můžete třeba nastavit skupinu Moje zařízení podle těchto kroků:

1.  V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte **Skupiny** > **Přehled** > **Vytvořit skupinu**.

2.  Jako hodnotu **Název skupiny** zadejte „Moje zařízení“, ze seznamu nadřazených skupin vyberte **Všechna zařízení** a potom zvolte **Další**.

3.  Na stránce **Definovat kritéria členství** vyberte **Všechna zařízení** , což znamená, že skupina zahrnuje mobilní zařízení i počítače.

4.  Na stránce **Definovat přímé členství** vyberte **Další**. Pokud jste dřív vytvořili skupinu, která neobsahuje všechna zařízení, a chtěli jste do nové skupiny přidat určitá zařízení, můžete to udělat tady.

5.  Na stránce **Souhrn** si prohlédněte akce, které se provedou, a pak zvolte **Dokončit**.

Nově vytvořenou skupinu najdete v seznamu **Skupiny** v pracovním prostoru **Skupiny** v části **Všechna zařízení**. Tady můžete skupinu i upravit nebo odstranit.

## Vytvoření skupiny uživatelů
Skupiny uživatelů můžete použít k nasazení softwaru a zásad zařízení. Můžete třeba nastavit skupinu Uživatelé Intune podle těchto kroků:

1.  V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte **Skupiny** > **Přehled** > **Vytvořit skupinu**.

2.  Jako hodnotu **Název skupiny** zadejte „Uživatelé Intune“, ze seznamu nadřazených skupin vyberte **Všichni uživatelé** a potom zvolte **Další**.

3.  Na stránce **Definovat kritéria členství** nastavte možnost **Začít členství ve skupině s** na **Všichni uživatelé v nadřazené skupině**.

4.  Vedle **Vyloučit členy z těchto skupin zabezpečení** vyberte **Procházet** a potom vyberte **Správce společnosti**. Toto vyloučení vám umožní spravovat skupinu Uživatelé Intune bez vlivu na účet správce společnosti (taky označovaný jako správce klienta).

5.  Na stránce **Definovat přímé členství** vyberte **Další**. Tady nemusíte nic dělat, protože chcete, aby skupina Uživatelé Intune obsahovala všechny uživatele kromě správce společnosti.

6.  Na stránce **Souhrn** si prohlédněte akce, které se provedou, a pak zvolte **Dokončit**.

Nově vytvořenou skupinu najdete v seznamu **Skupiny** v pracovním prostoru **Skupiny** v části **Všichni uživatelé**. Tady můžete skupinu i upravit nebo odstranit.



### Další kroky
Gratulujeme! Právě jste dokončili krok 5 *úvodní příručky Intune*.

>[!div class="step-by-step"]

>[&larr; **Správa licencí Intune**](.\start-with-a-paid-subscription-to-microsoft-intune-step-4.md)       [**Vytváření zásad a aplikací** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  



<!--HONumber=Jun16_HO4-->


