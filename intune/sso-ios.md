---
title: Nakonfigurování Microsoft Intune na jednotné přihlašování pro zařízení s iOSem
titlesuffix: ''
description: Přečtěte si, jak nakonfigurovat Microsoft Intune na jednotné přihlašování pro zařízení s iOSem.
keywords: ''
author: vhorne
ms.author: victorh
manager: dougeby
ms.date: 3/2/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8f19320df9a9728cdd77e608fc0ad219272a731f
ms.sourcegitcommit: e6319ff186d969da34bd19c9730ba003d6cce353
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/20/2018
---
# <a name="configure-microsoft-intune-for-ios-device-single-sign-on"></a>Nakonfigurování Microsoft Intune na jednotné přihlašování pro zařízení s iOSem

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Většina obchodních aplikací vyžaduje z důvodu zabezpečení určitou úroveň ověřování uživatelů. V mnoha případech to vyžaduje, aby uživatel zadával stejné přihlašovací údaje vícekrát, což může být pro uživatele nepříjemné. Kvůli vylepšení prostředí pro uživatele můžou vývojáři vytvářet aplikace používající jednotné přihlašování, které omezují počet případů, kdy uživatel musí zadat přihlašovací údaje.

Pokud chcete využívat jednotné přihlašování na zařízení s iOSem, musíte zajistit následující podmínky:

- Aplikace s kódem vyhledávajícím úložiště přihlašovacích údajů uživatelů v datové části jednotného přihlašování na zařízení s iOSem
- Nakonfigurování Intune na jednotné přihlašování pro zařízení s iOSem

## <a name="to-configure-intune-for-ios-device-single-sign-on"></a>Postup pro nakonfigurování Intune na jednotné přihlašování pro zařízení s iOSem


1. Přihlaste se k [portálu Azure Portal](https://portal.azure.com).
2. Zvolte **Všechny služby** > **Intune**. Intune se nachází v části **Monitorování a správa**.
3. V podokně **Intune** zvolte **Konfigurace zařízení**.
4. V podokně **Konfigurace zařízení** v části **Spravovat** zvolte **Profily**.
5. V podokně profilů zvolte **Vytvořit profil**.
6. Zadejte název a popis a nakonfigurujte následující nastavení:
   - **Platforma**: Zvolte **iOS**.
   - **Typ profilu**: Zvolte **Funkce zařízení**.
7. V podokně **Funkce zařízení** zvolte **Jednotné přihlašování**.

   ![Podokno Jednotné přihlašování](./media/sso-blade.png)

8. Vyplňování polí v podokně **Jednotné přihlašování** vám usnadní následující souhrnná tabulka. Podrobnosti najdete v oddílech za tabulkou.

   |Pole  |Poznámky|
   |---------|---------|
   |**Atribut uživatelského jména z AAD**|Atribut, který Intune načte pro každého uživatele z AAD a kterým vyplní příslušné pole (například hlavní název uživatele (UPN)) před vygenerováním datové části XML, která se instaluje na zařízení|
   |**Sféra**|Doménová část adresy URL|
   |**Předpony adres URL, které použijí jednotné přihlašování**|Všechny adresy URL ve vaší organizaci, které pro ověření uživatelů používají jednotné přihlašování|
   |**Aplikace, které použijí jednotné přihlašování**|Aplikace na zařízení koncového uživatele, které používají datovou část jednotného přihlašování|
   |**Certifikát pro prodloužení platnosti přihlašovacích údajů**|Pokud používáte pro ověřování certifikáty, vyberte certifikát SCEP nebo PFX, který se má danému uživateli nasadit jako ověřovací certifikát.|

Následující oddíly poskytují další podrobnosti týkající se jednotlivých polí pro jednotné přihlašování.

### <a name="username-attribute-from-aad-and-realm"></a>Atribut uživatelského jména z AAD a Sféra

- Pokud je pro toto pole vybraný **hlavní název uživatele (UPN)**, analyzuje se takto:

   ![Atribut uživatelského jména](media/User-name-attribute.png)

   Máte také možnost přepsat sféru textem, který zadáte do textového pole **Sféra**.

   Ve společnosti Contoso například můžou mít několik podoblastí, jako jsou Evropa, Asie a Severní Amerika. Můžou požadovat, aby jejich uživatelé v Asii používali datovou část jednotného přihlašování, a daná aplikace vyžaduje hlavní název uživatele (UPN) ve formátu *username@asia.contoso.com*. Pokud v tomto případě vyberete **hlavní název uživatele (UPN)**, načte se ve výchozím nastavení sféra pro každého uživatele z AAD, což může být právě *contoso.com*. Proto pro uživatele v Asii můžete tuto datovou část zvlášť vytvořit a přepsat sféru hodnotou *asia.contoso.com*. Hlavní název uživatele (UPN) pro koncového uživatele teď bude *username@asia.contoso.com*, nikoli *username@contoso.com*.

- Pokud vyberete **ID zařízení**, Intune automaticky vybere ID zařízení v Intune.

   Ve výchozím nastavení aplikace používají ID zařízení. Pokud ale vaše aplikace kromě ID zařízení používá sféru, můžete danou sféru zadat do textového pole **Sféra**.

   > [!NOTE]
   > Pokud ve výchozím nastavení používáte ID zařízení, ponechejte pole pro sféru prázdné.

### <a name="url-prefixes-that-will-use-single-sign-on"></a>Předpony adres URL, které použijí jednotné přihlašování

Zadejte všechny adresy URL ve vaší organizaci, které vyžadují ověření uživatelů.

Když se uživatel připojí k některému z těchto webů, zařízení s iOSem použije přihlašovací údaje pro jednotné přihlašování a uživatel nemusí zadávat žádné další přihlašovací údaje. Pokud ale máte zapnuté vícefaktorové ověřování, musí uživatelé provést i druhé ověření.

> [!NOTE]
> V těchto adresách URL se musí používat správně naformátovaný plně kvalifikovaný název domény. Apple vyžaduje, aby tyto adresy byly ve formátu `http://<yourURL.domain>`.

Odpovídající vzory adres URL musí mít na začátku `http://` nebo `https://`. Provádí se prosté ověření shody řetězců, takže předpona adresy URL `http://www.contoso.com/` neodpovídá adrese `http://www.contoso.com:80/`. V iOSu 9.0 a v novějších verzích se ale k určení všech odpovídajících hodnot může použít jeden zástupný znak \*. Například adresa `http://*.contoso.com/` odpovídá adrese `http://store.contoso.com/` i adrese `http://www.contoso.com`.
Vzory `http://.com` a `https://.com` odpovídají všem adresám URL typu HTTP a HTTPS, v uvedeném pořadí.

### <a name="apps-that-will-use-single-sign-on"></a>Aplikace, které použijí jednotné přihlašování

Určete aplikace na zařízení koncového uživatele, které můžou používat datovou část jednotného přihlašování.

Pole `AppIdentifierMatches` musí obsahovat řetězce, které odpovídají hodnotám ID sady prostředků aplikace. Tyto řetězce můžou být přesné shody (například `com.contoso.myapp`) nebo můžou určovat shodu předpony u ID sady prostředků pomocí zástupného znaku \*. Zástupný znak se musí zadat po tečce (.) a může se objevit jenom jednou, a to na konci řetězce (například `com.contoso.*`). Při použití zástupného znaku se udělí přístup k účtu všem aplikacím, jejichž ID sady prostředků začíná příslušnou předponou.

Pole **Název aplikace** se používá k přidání popisného názvu, který vám pomůže dané ID sady prostředků identifikovat.

### <a name="credential-renewal-certificate"></a>Certifikát pro prodloužení platnosti přihlašovacích údajů

Pokud používáte k ověření koncových uživatelů certifikáty (a ne hesla), použijte toto pole k výběru certifikátu SCEP nebo PFX, který se má danému uživateli nasadit jako ověřovací certifikát. Obvykle je to stejný certifikát, který se danému uživateli nasazuje pro jiné profily, jako jsou například VPN, Wi-Fi nebo e-mail.

## <a name="next-steps"></a>Další kroky

Další informace o konfiguraci funkce zařízení najdete v tématu [Konfigurace nastavení funkce zařízení ve službě Microsoft Intune](device-features-configure.md).
