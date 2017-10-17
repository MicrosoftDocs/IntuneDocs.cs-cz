---
title: "Vytvoření skupiny pro uspořádání uživatelů a zařízení"
description: "Vytvořte uživatele a skupiny pro předplatné Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 21fe439a229dfa81b11c001b71df073e4522a752
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/10/2017
---
# <a name="create-groups-to-organize-users-and-devices"></a>Vytvoření skupiny pro uspořádání uživatelů a zařízení

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

V tomto tématu najdou správci informace o tom, jak můžou v Intune vytvořit skupiny uživatelů.

Skupiny v Intune poskytují flexibilitu pro správu zařízení a uživatelů. Můžete nastavit skupiny podle potřeb vaší organizace (třeba podle zeměpisné polohy, oddělení nebo vlastností hardwaru) a použít je k provádění široké škály úloh správy od nasazení zásad pro víc uživatelů až po nasazení aplikací na skupinu zařízení.

## <a name="group-management-moving-to-azure-ad"></a>Přesunutí správy skupin do Azure AD

**Od listopadu 2016** budou nové účty spravovat skupiny uživatelů a zařízení na portálu Azure Active Directory (AD). V prosinci 2016 začne produktový tým Intune s migrací stávajících zákazníků na novou správu na základě skupin Azure AD. Všechny skupiny uživatelů a zařízení budou migrovány na skupiny zabezpečení služby Azure AD. Migraci zahájíme až ve chvíli, kdy co nejvíce minimalizujeme veškerý dopad, který by mohla mít na vaši každodenní práci. Očekáváme, že na vaše uživatele nebude mít dopad žádný. Před zahájením migrace vašeho účtu vám navíc pošleme upozornění.


>[!IMPORTANT]
>
>Pokud na portálu Intune otevřete pracovní prostor Skupiny a uvidíte zprávu **Uživatelské skupiny Intune se teď spravují jako skupiny v Azure Active Directory** s odkazem na portál Azure Active Directory, znamená to, že už používáte *nový* přístup ke správě skupin v Intune – na základě skupin zabezpečení Azure AD. Informace o tom, jak vytvářet skupiny, najdete v části [Správa skupin v Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).
>
>Pokud se vám odkaz na portál Azure AD nezobrazí, znamená to, že ke správě skupin pořád používáte portál Intune.

## <a name="group-management-in-the-intune-portal"></a>Správa skupin na portálu Intune

Skupiny zařízení i uživatelů se vytvářejí v pracovním prostoru SKUPINY konzoly pro správu Intune.

![Pracovní prostor skupin konzoly pro správu](./media/groups.png)


> [!TIP]
> Další informace o používání skupin najdete v tématu [Použití skupin pro správu uživatelů a zařízení s Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).


## <a name="create-a-device-group"></a>Vytvoření skupiny zařízení
Skupiny zařízení použijte k nasazení aplikací a aktualizací a konfiguraci dalších funkcí. Můžete třeba nastavit skupinu Moje zařízení podle těchto kroků:

1.  V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte **Skupiny** > **Přehled** > **Vytvořit skupinu**.

2.  Jako hodnotu **Název skupiny** zadejte „Moje zařízení“, ze seznamu nadřazených skupin vyberte **Všechna zařízení** a potom zvolte **Další**.

3.  Na stránce **Definovat kritéria členství** vyberte **Všechna zařízení** , což znamená, že skupina zahrnuje mobilní zařízení i počítače.

4.  Na stránce **Definovat přímé členství** vyberte **Další**. Pokud jste dřív vytvořili skupinu, která neobsahuje všechna zařízení, a chtěli jste do nové skupiny přidat určitá zařízení, můžete to udělat tady.

5.  Na stránce **Souhrn** si prohlédněte akce, které se provedou, a pak zvolte **Dokončit**.

Nově vytvořenou skupinu najdete v seznamu **Skupiny** v pracovním prostoru **Skupiny** v části **Všechna zařízení**. Tady můžete skupinu i upravit nebo odstranit.

## <a name="create-a-user-group"></a>Vytvoření skupiny uživatelů
Skupiny uživatelů můžete použít k nasazení softwaru a zásad zařízení. Můžete třeba nastavit skupinu Uživatelé Intune podle těchto kroků:

1.  V [konzole pro správu Intune](https://manage.microsoft.com/) zvolte **Skupiny** > **Přehled** > **Vytvořit skupinu**.

2.  Jako hodnotu **Název skupiny** zadejte „Uživatelé Intune“, ze seznamu nadřazených skupin vyberte **Všichni uživatelé** a potom zvolte **Další**.

3.  Na stránce **Definovat kritéria členství** nastavte možnost **Začít členství ve skupině s** na **Všichni uživatelé v nadřazené skupině**.

4.  Vedle **Vyloučit členy z těchto skupin zabezpečení** vyberte **Procházet** a potom vyberte **Správce společnosti**. Toto vyloučení vám umožní spravovat skupinu Uživatelé Intune bez vlivu na účet správce společnosti (taky označovaný jako správce klienta).

5.  Na stránce **Definovat přímé členství** vyberte **Další**. Tady nemusíte nic dělat, protože chcete, aby skupina Uživatelé Intune obsahovala všechny uživatele kromě správce společnosti.

6.  Na stránce **Souhrn** si prohlédněte akce, které se provedou, a pak zvolte **Dokončit**.

Nově vytvořenou skupinu najdete v seznamu **Skupiny** v pracovním prostoru **Skupiny** v části **Všichni uživatelé**. Tady můžete skupinu i upravit nebo odstranit.

>[!div class="step-by-step"]
/intune/licenses-assign [&larr; **Správa licencí Intune**](/intune/licenses-assign)       [**Vytvoření zásad a aplikací** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)  
