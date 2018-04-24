---
title: Vytvoření zásady dodržování předpisů pro zařízení s macOS v Microsoft Intune
titleSuffix: ''
description: Vytvořte v Microsoft Intune zásadu dodržování předpisů zařízením pro zařízení s macOS umožňující vám zadat požadavky, které zařízení musí splnit, aby vyhovovalo předpisům.
keywords: ''
author: msmimart
ms.author: mimart
manager: dougeby
ms.date: 02/22/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d6252680e64067e6d12530e0226632a1c5db7d28
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="create-a-device-compliance-policy-for-macos-devices-with-intune"></a>Vytvoření zásad dodržování předpisů pro zařízení s macOS v Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Zásada dodržování předpisů Intune pro zařízení s macOS určuje pravidla a nastavení, které musí zařízení s macOS splňovat, aby bylo považováno za dodržující předpisy. Tyto zásady můžete použít s podmíněným přístupem k povolení nebo zablokování přístupu k prostředkům společnosti. Můžete také získat sestavy zařízení a provádět kroky v případě, že zařízení předpisy nedodržuje. Zásady dodržování předpisů zařízení pro každou platformu vytvoříte na portálu Intune Azure.

## <a name="before-you-begin"></a>Před zahájením

Než začnete vytvářet a přiřazovat zásady dodržování předpisů pro zařízení, přečtěte si informace o koncepci zásad dodržování předpisů zařízeními v Intune.

- Další informace o zásadách dodržování předpisů pro zařízení najdete v tématu [Začínáme s dodržováním předpisů zařízeními v Intune](device-compliance.md).

> [!IMPORTANT]
> Zásady dodržování předpisů pro zařízení je nutné vytvořit pro každou platformu zvlášť. Nastavení zásad dodržování předpisů zařízeními v Intune závisí na možnostech platformy, pro které je určené nastavení prostřednictvím protokolu MDM.

Následující tabulka popisuje, jak jsou spravovaná nevyhovující nastavení při použití zásad dodržování předpisů se zásadami podmíněného přístupu:


| Nastavení zásad | macOS 10.11 a novější |
| --- | --- |
| **Konfigurace kódu PIN nebo hesla** | Opravené |   
| **Šifrování zařízení** | Opravené (nastavením PIN kódu) |
| **E-mailový profil** | V karanténě |
|**Minimální verze operačního systému** | V karanténě |
| **Maximální verze operačního systému** | V karanténě |  


**Opravené** = operační systém zařízení vynucuje dodržování předpisů. (Uživatel musí třeba zadat kód PIN.)

**V karanténě** = operační systém zařízení nevynucuje dodržování předpisů. (Například zařízení s Androidem nenutí uživatele šifrovat zařízení.) Pokud zařízení nesplňuje předpisy, provedou se následující akce:

- Zařízení se zablokuje, pokud se zásady podmíněného přístupu vztahují na uživatele.
- Portál společnosti oznamuje uživateli všechny problémy s dodržováním předpisů.

## <a name="macos-compliance-policy-settings"></a>Nastavení zásad dodržování předpisů v MacOS

Při vytváření nových zásad dodržování předpisů zařízeními s Intune můžete vybírat z různých kategorií s různými nastaveními:

- Stav zařízení

- Vlastnosti zařízení

- Zabezpečení systému

### <a name="device-health"></a>Stav zařízení

- **Vyžadovat ochranu integrity systému** – Pokud chcete kontrolovat, jestli mají zařízení s macOS povolenou ochranu integrity systému, nastavte na **Vyžadovat**.

### <a name="device-properties"></a>Vlastnosti zařízení

- **Minimální verze OS** – Pokud zařízení nesplňuje požadavek na minimální verzi operačního systému, označí se jako nekompatibilní. Zobrazí se odkaz s informacemi, jak upgradovat. Uživatel může zvolit upgrade svého zařízení. Pak může přistupovat k prostředkům společnosti.

- **Maximální verze OS** – Pokud zařízení používá verzi operačního systému, která je novější než verze uvedená v pravidle, bude přístup k prostředkům společnosti zablokovaný a uživateli se zobrazí výzva, že má kontaktovat správce IT. Dokud nedojde ke změně v pravidle, která tuto verzi operačního systému povolí, nepůjde přes toto zařízení přistupovat k prostředkům společnosti.

### <a name="system-security-settings"></a>Systémové nastavení zabezpečení

#### <a name="password"></a>Heslo

- **Vyžadovat heslo k odemknutí mobilních zařízení** – Pokud nastavíte **Vyžadovat**, budou muset uživatelé zadat heslo, aby mohli získat přístup ke svému zařízení.

- **Jednoduchá hesla** – Pokud nastavíte **Blokovat**, nebude moct uživatel vytvořit jednoduché heslo, jako je třeba **1234** nebo **1111**.

- **Minimální délka hesla** – Určuje minimální počet číslic nebo znaků, které musí obsahovat heslo uživatele.

- **Typ hesla** – Určuje, jestli musí uživatel vytvořit **alfanumerické** nebo **číselné** heslo.

- **Počet nealfanumerických znaků v hesle** – Pokud nastavíte u možnosti **Požadovaný typ hesla** hodnotu **Alfanumerické**, určuje toto nastavení nejmenší počet znakových sad, které musí heslo mít. 

    > [!NOTE]
    > Po nastavení vyššího čísla bude uživatel muset vytvořit složitější heslo.

    > [!IMPORTANT]
    > Pro zařízení s macOS toto nastavení určuje počet speciálních znaků (třeba **!** , **#**, **&amp;**), které musí heslo obsahovat.

- **Maximální počet minut nečinnosti, po kterém bude nutné zadat heslo** – Určete dobu nečinnosti, která musí uplynout, aby se po uživateli znovu požadovalo zadání hesla.

- **Konec platnosti hesla (dny)** – Vyberte počet dní (1 až 250), za který skončí platnost hesla a uživatel bude muset vytvořit nové.

- **Počet předchozích hesel, která se nesmí použít znovu** – Zadejte počet dříve použitých hesel, která se nesmí znovu použít.

    > [!IMPORTANT]
    > Když se požadavek na heslo na zařízení s macOS změní, projeví se to až při příští změně hesla uživatelem. Pokud třeba nastavíte omezení délky hesla na osm číslic a zařízení s macOS má aktuálně šestičíselné heslo, bude zařízení dál splňovat předpisy až do doby, kdy uživatel heslo na zařízení změní.

## <a name="to-create-a-device-compliance-policy"></a>Vytvoření zásad dodržování předpisů pro zařízení

1. Přejděte na portál [Azure Portal](https://portal.azure.com) a přihlaste se pomocí svých přihlašovacích údajů k Intune.

2. Když se úspěšně přihlásíte, zobrazí se vám **řídicí panel Azure**.

3. V nabídce vlevo zvolte **Všechny služby** a do filtru textového pole pak zadejte **Intune**.

4. Zvolte **Intune** a zobrazí se **řídicí panel Intune**.

5. Zvolte **Dodržování předpisů zařízením** a v části **Správa** zvolte **Zásady**.

6. Klikněte na **Vytvořit zásadu**.

7. Zadejte název a popis a zvolte platformu, u které chcete použít tyto zásady.

8. Otevře se podokno **Zásady dodržování předpisů na Macu**. Zvolte kategorie nastavení zásad zařízení **Zabezpečení systému**, **Stav zařízení** a **Vlastnosti zařízení** a zadejte svá nastavení.

10. Po dokončení nastavení vyberte u každé kategorie nastavení zásad dodržování předpisů zařízením **OK**.

11. Zvolte **OK** a potom **Vytvořit**.

## <a name="assign-user-groups"></a>Přiřazení skupin uživatelů

Pokud chcete přiřadit zásady dodržování předpisů uživatelům, vyberte zásady, které jste nakonfigurovali. Existující zásady najdete v podokně **Dodržování předpisů zařízením – Zásady**.

1. Vyberte zásady dodržování předpisů zařízením, které chcete přiřadit uživatelům, a zvolte **Přiřazení**. Otevře se podokno, kde můžete vybrat **skupiny zabezpečení Azure Active Directory** a přiřadit je k zásadám.

2. Zvolte **Vybrat skupiny** a otevřete tak podokno, kde se zobrazí skupiny zabezpečení v Azure AD.

3. Zvolte **Uložit**. Tím se zásady dodržování předpisů zařízením přiřadí do skupin zabezpečení Azure AD.

4. Až přiřazování zásad dodržování předpisů zařízením do skupin dokončíte, můžete podokno **Přiřazení** zavřít.

    > [!TIP]
    > Ve výchozím nastavení kontrolují zařízení dodržování předpisů každých 8 hodin, ale uživatelé můžou tento proces v aplikaci Portál společnosti Intune vynutit.

## <a name="next-steps"></a>Další kroky

[Jak monitorovat dodržování zásad v zařízeních](compliance-policy-monitor.md)
