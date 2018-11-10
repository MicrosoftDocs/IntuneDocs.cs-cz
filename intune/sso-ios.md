---
title: Přidání jednotného přihlašování zařízení s iOSem v Microsoft Intune – Azure | Microsoft Docs
description: V Microsoft Intune můžete vytvářet, konfigurovat, povolit a aktivovat jednotné přihlašování (SSO) zařízení s iOSem, aby uživatelé při přístupu k prostředkům organizace nemuseli zadávat heslo. Pokud chcete používat jednotné přihlašování, vytvořte profil konfigurace zařízení a zadejte hlavní název uživatele (UPN), ID zařízení, vaše aplikace a certifikát, který se použije k ověření uživatele a zařízení.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/24/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d1add113222c2aa7eaea10679c329e877b1a136f
ms.sourcegitcommit: 437eaf364c3b8a38d294397310c770ea4d8a8015
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/24/2018
ms.locfileid: "49992005"
---
# <a name="use-single-sign-on-ios-device-in-microsoft-intune"></a>Použití jednotného přihlašování na zařízení s iOSem v Microsoft Intune

Většina obchodních aplikací vyžaduje z důvodu zabezpečení určitou úroveň ověřování uživatelů. Často takové ověřování vyžaduje od uživatele opakované zadání stejných přihlašovacích údajů, což je nepříjemné. Proto je potřeba uživatelské prostředí zdokonalit, aby vývojáři mohli vytvářet aplikace, které používají jednotné přihlašování. Jednotné přihlašování snižuje počet případů, kdy uživatel musí zadat přihlašovací údaje.

V tomto článku si ukážeme, jak zapnout jednotné přihlašování na zařízeních s iOSem. Použijeme k tomu konfigurační profil zařízení v Microsoft Intune.

## <a name="before-you-begin"></a>Před zahájením

Na zařízení s iOSem musí být aplikace naprogramovaná na vyhledávání v úložišti přihlašovacích údajů v datové části jednotného přihlašování.

## <a name="create-the-sso-profile"></a>Vytvoření profilu jednotného přihlašování

1. Na [portálu Azure Portal](https://portal.azure.com) vyberte **Všechny služby**, vyfiltrujte **Intune** a vyberte **Microsoft Intune**.
2. Zvolte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. Zadejte následující nastavení:

    - **Název:** Zadejte název profilu, třeba `ios sso profile`.
    - **Popis:** Zadejte popis s klíčovými výrazy, které pomůžou profil najít v seznamu.
    - **Platforma**: Zvolte **iOS**.
    - **Typ profilu**: Zvolte **Funkce zařízení**.

4. Zvolte **Jednotné přihlašování**.

    ![Podokno Jednotné přihlašování](./media/sso-blade.png)

5. Zadejte následující nastavení: 

    - **Atribut uživatelského jména z AAD:** Pro každého uživatele v Azure AD vyhledá Intune tento atribut. Potom Intune napřed vyplní příslušné pole (třeba hlavní název uživatele) a potom vygeneruje datovou část XML, která se instaluje do zařízení. Možnosti:
    
        - **Hlavní název uživatele:** Hlavní název uživatele se parsuje následujícím způsobem:

            ![Atribut uživatelského jména](media/User-name-attribute.png)

            Sféru také můžete přepsat textem, který zadáte do textového pole **Sféra**.

            Ve společnosti Contoso například můžou mít několik podoblastí, jako jsou Evropa, Asie a Severní Amerika. Společnost může od uživatelů v Asii vyžadovat, aby používali datovou část jednotného přihlašování, ale aplikace vyžaduje hlavní název uživatele (UPN) ve formátu `username@asia.contoso.com`. Pokud v tomto případě vyberete **hlavní název uživatele (UPN)**, načte se automaticky sféra každého uživatele z Azure AD, což může být právě *contoso.com*. Proto pro uživatele v Asii můžete tuto datovou část zvlášť vytvořit a přepsat sféru hodnotou *asia.contoso.com*. Hlavní název koncového uživatele (UPN) teď bude username@asia.contoso.com místo username@contoso.com.

        - **ID zařízení Intune:** Intune automaticky vybere ID zařízení v Intune. 

            Ve výchozím nastavení aplikace používají ID zařízení. Ale pokud vaše aplikace používá ID zařízení *a* sféru, můžete ji zadat do textového pole **Sféra**.

            > [!NOTE]
            > Implicitně platí, že pokud používáte ID zařízení, sféru nevyplňujte.

    - **Sféra:** Doménová část adresy URL.
    
    - **Předpony adres URL, které použijí jednotné přihlašování**: **Přidejte** všechny adresy URL vaší organizace, které k ověření uživatelů používají jednotné přihlašování. 

        Například pokud se uživatel připojí k některému z těchto webů, použije zařízení s iOSem přihlašovací údaje pro jednotné přihlašování. Uživatel nemusí zadávat další přihlašovací údaje. Pokud ale máte zapnuté vícefaktorové ověřování, musí uživatelé provést i druhé ověření.

        > [!NOTE]
        > V těchto adresách URL se musí používat správně naformátovaný plně kvalifikovaný název domény. Apple vyžaduje adresy URL ve formátu `http://<yourURL.domain>`.

        Odpovídající vzory adres URL musí mít na začátku `http://` nebo `https://`. Provádí se prosté ověření shody řetězců, takže předpona adresy URL `http://www.contoso.com/` neodpovídá adrese `http://www.contoso.com:80/`. V iOSu 10.0 a v novějších verzích ale můžete k zadání všech vyhovujících hodnot použít jeden zástupný znak \*. Například adresa `http://*.contoso.com/` odpovídá adrese `http://store.contoso.com/` i adrese `http://www.contoso.com`.

        Vzory `http://.com` a `https://.com` odpovídají všem adresám URL typu HTTP a HTTPS, v uvedeném pořadí.
    
    - **Aplikace, které použijí jednotné přihlašování:** **Přidá** do zařízení koncových uživatelů aplikace, které můžou používat jednotné přihlašování. 

        Pole `AppIdentifierMatches` musí obsahovat řetězce, které odpovídají hodnotám ID sady prostředků aplikace. Může jít o přesné shody (například `com.contoso.myapp`) nebo můžete k zadání shodné předpony pro ID sady prostředků použít zástupný znak \*. Zástupný znak se musí zadat po tečce (.) a může se objevit jenom jednou, a to na konci řetězce (například `com.contoso.*`). Při použití zástupného znaku se udělí přístup k účtu všem aplikacím, jejichž ID sady prostředků začíná příslušnou předponou.

        **Název aplikace** použijte k zadání popisného názvu, který pomůže při identifikaci ID sady prostředků.
    
    - **Certifikát pro prodloužení platnosti přihlašovacích údajů:** Pokud k ověřování místo hesel používáte certifikáty, vyberte certifikát SCEP nebo PFX, který se nasadí uživateli jako jeho ověřovací certifikát. Většinou jde o stejný certifikát, jaký se uživateli nasazuje pro jiné profily, jako je VPN, Wi-Fi nebo e-mail.

6. Vyberte **OK** > **OK** > **Vytvořit**, uložte změny a vytvořte profil. Vytvořený profil se zobrazí v seznamu **Konfigurace zařízení – Profily**. 

## <a name="next-steps"></a>Další kroky

Další informace o konfiguraci funkce zařízení najdete v tématu [Konfigurace nastavení funkce zařízení ve službě Microsoft Intune](device-features-configure.md).

[Přiřaďte tento profil](device-profile-assign.md) zařízením s iOSem.
