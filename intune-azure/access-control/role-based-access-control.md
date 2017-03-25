---
title: Role Intune (RBAC) pro Microsoft Intune
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Informace o tom, jak RBAC umožňuje určovat, kdo může provádět akce a změny."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
translationtype: Human Translation
ms.sourcegitcommit: deea78dcea9ade031441bf12b388a862235a8e9c
ms.openlocfilehash: e60edd86289e0fca2aa03660d8ce782e373c0236
ms.lasthandoff: 03/15/2017


---

# <a name="intune-roles-rbac-for-microsoft-intune"></a>Role Intune (RBAC) pro Microsoft Intune

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Jednoduše řečeno, **role** Intune (neboli RBAC) pomáhají určovat, kdo může v Intune provádět různé akce a na koho se tyto akce vztahují. Můžete buď použít předdefinované role, které vyhovují běžným situacím v Intune, nebo si vytvořit své vlastní role.

Roli definuje toto:

- **Definice** – Název role a oprávnění, která tato role konfiguruje
- **Členové** – Uživatel nebo skupina uživatelů, kterým se tato oprávnění udělí
- **Obor** – Uživatelé nebo zařízení, které zadaná osoba (člen) může spravovat
- **Přiřazení** – Po nakonfigurování členů, definic a oboru se role přiřadí.

## <a name="built-in-roles"></a>Předdefinované role

Následující role jsou integrované do Intune a můžete si je buď přizpůsobit, nebo je přiřadit ke skupinám, aniž byste jejich konfiguraci měnili.

- **Správce Intune** – Má úplná oprávnění pro všechny operace Intune.
- **Správce aplikací** – Spravuje a nasazuje aplikace a profily.
- **Správce zásad konfigurace** – Spravuje a nasazuje nastavení a profily konfigurace.
- **Pracovník helpdesku** – Provádí vzdálené úkoly a může zobrazovat informace o uživateli a zařízení.
- **Operátor jen pro čtení** – Může zobrazovat informace na portálu Intune, ale nemůže provádět změny.


## <a name="custom-roles"></a>Vlastní role

Pokud vašim potřebám nevyhovuje žádná z předdefinovaných rolí, můžete volbou nastavení, která pokrývají mnoho funkcí Intune, vytvořit svoji vlastní roli. Níže v tomto tématu najdete seznam dostupných nastavení.

### <a name="example"></a>Příklad

Zaměstnáte nového správce IT, který bude mít na starost nasazování a správu aplikací pro uživatele na londýnské pobočce. Uživatelé jsou ve skupině služby Azure AD pojmenované **London**. Chcete zajistit, aby správce IT nemohl nasazovat aplikace uživatelům na jiných pobočkách. Provedete následující akce:

- Přiřadíte integrovanou roli **Správce aplikací** s následujícími vlastnostmi:
    - **Členové** – Vyberte skupinu, která obsahuje správce IT, který bude nasazovat aplikace.
    - **Obor** – Vyberte skupinu **London** služby Azure AD.

    >[!IMPORTANT]
    >Abyste mohli vytvářet, upravovat nebo přiřazovat role, váš účet musí mít ve službě Azure AD jedno z těchto oprávnění:
    >- **Globální správce AAD**
    >- **Správce služby Intune**

### <a name="how-to-create-a-custom-role"></a>Jak vytvořit vlastní roli

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby** > **Monitorování + správa** > **Intune**.
3. V okně **Intune** zvolte **Role Intune**.
![Úloha řízení přístupu](./media/axxess-control.png)
1. V okně **Role** úlohy **Řízení přístupu** zvolte **Přidat vlastní**.
2. V okně **Přidat vlastní roli** zadejte název a popis nové role a klikněte na **Oprávnění**.
3. V okně **Oprávnění** zvolte oprávnění, která chcete v této roli použít. S výběrem vám pomůže referenční seznam nastavení vlastních rolí, který najdete níže v tomto tématu.
4. Po dokončení klikněte na **OK**.
5. V okně **Přidat vlastní roli** klikněte na **Vytvořit**.

Nová role se zobrazí v seznamu v okně **Role**.

## <a name="how-to-assign-a-role"></a>Jak přiřadit roli

1. V okně **Role** úlohy **Řízení přístupu** zvolte předdefinovanou nebo vlastní roli, kterou chcete přiřadit.
2. V okně <*název role*> – **Vlastnosti** zvolte **Spravovat** > **Přiřazení**.
    >[!TIP]
    >V tomto okně můžete navíc upravovat nebo odstraňovat existující role.
3. V dalším okně zvolte **Přiřadit**.
4. V okně **Přiřazení rolí** zadejte **Název** a volitelný **Popis** přiřazení a zvolte následující:
    - **Členové** – Vyberte skupinu, která obsahuje uživatele, kterému chcete udělit oprávnění.
    - **Obor** – Vyberte skupinu, která obsahuje uživatele, které člen výše bude moct spravovat.
5. Po dokončení klikněte na **OK**.

Nové přiřazení se zobrazí v seznamu přiřazení.

## <a name="custom-role-settings-reference"></a>Referenční informace o nastavení vlastních rolí

Když vytvoříte vlastní roli, můžete nakonfigurovat jednu nebo více z těchto nastavení:

### <a name="device-configurations"></a>Konfigurace zařízení

|||
|-|-|
|**Přiřadit**|Přiřazení profilů zařízení ke skupinám|
|**Vytvořit**|Vytvoření profilů zařízení|
|**Odstranit**|Odstranění profilů zařízení|
|**Číst**|Čtení profilů zařízení a jejich vlastností|
|**Aktualizovat**|Aktualizace existujících profilů zařízení|

### <a name="managed-apps"></a>Spravované aplikace

|||
|-|-|
|**Přiřadit**|Přiřazení spravovaných aplikací ke skupinám|
|**Vytvořit**|Přidání nových spravovaných aplikací do Intune|
|**Odstranit**|Odstranění spravovaných aplikací|
|**Číst**|Čtení spravovaných aplikací a jejich vlastností|
|**Aktualizovat**|Aktualizace existujících spravovaných aplikací|
|**Vymazání**|Vymazání spravovaných aplikací ze zařízení|

### <a name="managed-devices"></a>Spravovaná zařízení

|||
|-|-|
|**Odstranit**|Odstranění spravovaných zařízení z Intune|
|**Číst**|Zobrazení informací o spravovaných zařízeních na portálu Intune|
|**Aktualizovat**|Aktualizace informací o spravovaných zařízeních|

### <a name="mobile-apps"></a>Mobilní aplikace

|||
|-|-|
|**Přiřadit**|Přiřazení mobilních aplikací ke skupinám|
|**Vytvořit**|Přidání nových mobilních aplikací do Intune|
|**Odstranit**|Odstranění mobilních aplikací|
|**Číst**|Čtení mobilních aplikací a jejich vlastností|
|**Aktualizovat**|Aktualizace existujících mobilních aplikací|

### <a name="organization"></a>Organizace

|||
|-|-|
|**Číst**|Čtení nastavení tenanta|
|**Aktualizovat**|Aktualizace nastavení tenanta|

### <a name="remote-tasks"></a>Vzdálené úlohy

|||
|-|-|
|**Vynechat zámek aktivace**|Odebrání zámku aktivace ze zařízení s iOSem bez Apple ID a hesla uživatele |
|**Zakázat režim ztráty**|Zákaz režimu ztráty. Režim ztráty umožňuje zadat zprávu a telefonní číslo, které se zobrazí na zamykací obrazovce zařízení.|
|**Povolit režim ztráty**|Povolení režimu ztráty. Režim ztráty umožňuje zadat zprávu a telefonní číslo, které se zobrazí na zamykací obrazovce zařízení.|
|**Vyhledat zařízení**|-|
|**Okamžitě restartovat**|Restartuje zařízení.|
|**Vzdálené uzamčení**|Zamkne zařízení. Vlastník zařízení musí k jeho odemčení použít heslo.|
|**Resetovat heslo**|Vygeneruje pro zařízení nové heslo, které se zobrazí v okně Přehled <device name>.|
|**Vyřadit**|Odebere jenom firemní data spravovaná přes Intune. Osobní data ze zařízení neodebere.|
|**Vymazání**|Vrátí zařízení na výchozí nastavení.|



### <a name="telecom-expenses"></a>Výdaje na telekomunikaci

|||
|-|-|
|**Číst**|Čtení nastavení služby TEM (Telecom Expense Management)|
|**Aktualizovat**|Aktualizace nastavení služby TEM (Telecom Expense Management)|

### <a name="terms-and-conditions"></a>podmínky a ujednání

|||
|-|-|
|**Přiřadit**|Přiřazení podmínek a ujednání ke skupinám|
|**Vytvořit**|Vytvoření nastavení podmínek a ujednání|
|**Odstranit**|Odstranění nastavení podmínek a ujednání|
|**Číst**|Čtení nastavení podmínek a ujednání na portálu Intune|
|**Aktualizovat**|Aktualizace existujících podmínek a ujednání|
