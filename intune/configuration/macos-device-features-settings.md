---
title: Microsoft Intune の macOS デバイスの機能設定 - Azure | Microsoft Docs
description: Microsoft Intune で AirPrint 用の macOS デバイスを構成し、電源ボタンを表示または非表示にするようログイン ウィンドウをカスタマイズするための設定について説明します。 ネットワーク内の AirPrint サーバーの IP アドレス、パス、およびポート設定を取得する手順について説明します。 デバイス構成プロファイルでこれらの設定を使用して、macOS デバイスを構成します。
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 10/22/2019
ms.topic: reference
ms.service: microsoft-intune
ms.subservice: configuration
ms.localizationpriority: medium
ms.technology: ''
ms.reviewer: ''
ms.suite: ems
search.appverid: ''
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 54995b54d7810c02c5a8b24e5ddff3fa1f08cb05
ms.sourcegitcommit: 737ad6c675deedfc6009f792023ff95981b06582
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/15/2019
ms.locfileid: "74117868"
---
# <a name="macos-device-feature-settings-in-intune"></a>Intune での macOS デバイスの機能設定

[!INCLUDE [azure_portal](../includes/azure_portal.md)]

Intune には、macOS デバイスで機能をカスタマイズするための組み込みの設定がいくつかあります。 Správci můžou například přidat tiskárny pro průchozí tisk, zvolit způsob, jakým se uživatelé přihlásí, konfigurovat řízení spotřeby, používat ověřování pomocí jednotného přihlašování a další.

これらの機能を使用して、macOS デバイスをご利用のモバイル デバイス管理 (MDM) ソリューションの一部として制御します。

この記事では、このような設定を一覧で示し、各設定の機能について説明します。 また、ターミナル アプリ (エミュレーター) を使って AirPrint プリンターの IP アドレス、パス、ポートを取得する手順についても説明します。 Další informace o funkcích zařízení najdete v pro [Přidání nastavení funkcí zařízení se systémem iOS nebo MacOS](device-features-configure.md).

## <a name="before-you-begin"></a>始める前に

[macOS デバイス構成プロファイルを作成します](device-features-configure.md)。

> [!NOTE]
> Tato nastavení platí pro různé typy registrace s některými nastaveními, která platí pro všechny možnosti registrace. Další informace o různých typech registrace najdete v tématu [registrace MacOS](../enrollment/macos-enroll.md).

## <a name="airprint"></a>AirPrint

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Nastavení platí pro: registrace zařízení a automatický zápis zařízení 

- **[IP アドレス]** : プリンターの IPv4 アドレスまたは IPv6 アドレスを入力します。 ホスト名を使用してプリンターを識別している場合は、ターミナル アプリでプリンターに ping を実行することで IP アドレスを取得できます。 詳細については、「[IP アドレスとパスを取得する](#get-the-ip-address-and-path)」(この記事) を参照してください。
- **[パス]** : プリンターのパスを入力します。 通常、このパスはネットワーク上のプリンターの `ipp/print` です。 詳細については、「[IP アドレスとパスを取得する](#get-the-ip-address-and-path)」(この記事) を参照してください。
- **[ポート]** (iOS 11.0 以降): AirPrint の接続先のリスニング ポートを入力します。 このプロパティを空白のままにすると、AirPrint には既定のポートが使用されます。
- **[TLS]** (iOS 11.0 以降): トランスポート層セキュリティ (TLS) で AirPrint の接続を保護するには、 **[有効]** を選択します。

- AirPrint サーバーを**追加**します。 多数の AirPrint サーバーを追加できます。

AirPrint プリンターの一覧を含むコンマ区切りファイル (.csv) を **[インポート]** することもできます。 また、Intune に AirPrint プリンターを追加した後、この一覧を **[エクスポート]** することもできます。

### <a name="get-the-ip-address-and-path"></a>IP アドレスとパスを取得する

AirPrinter サーバーを追加するには、プリンターの IP アドレス、リソース パス、およびポートが必要です。 この情報を取得する手順は次のとおりです。

1. AirPrint プリンターと同じローカル ネットワーク (サブネット) に接続している Mac 上で、( **/アプリケーション/ユーティリティ**から) **ターミナル**を開きます。
2. ターミナル アプリで「`ippfind`」と入力し、Enter キーを押します。

    プリンター情報をメモします。 たとえば、`ipp://myprinter.local.:631/ipp/port1` のような内容が返されます。 最初の部分はプリンターの名前です。 最後の部分 (`ipp/port1`) はリソース パスです。

3. ターミナルで「`ping myprinter.local`」と入力し、Enter キーを押します。

   IP アドレスをメモします。 たとえば、`PING myprinter.local (10.50.25.21)` のような内容が返されます。

4. この IP アドレスとリソース パスの値を使用します。 この例では、IP アドレスは `10.50.25.21`、リソース パスは `/ipp/port1` です。

## <a name="login-items"></a>ログイン項目

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: všechny typy registrace

- **Soubory, složky a vlastní aplikace**: **přidejte** cestu k souboru, složce, vlastní aplikaci nebo systémové aplikaci, kterou chcete otevřít, když se uživatel přihlásí k zařízení. Systémové aplikace nebo aplikace sestavené nebo přizpůsobené pro vaši organizaci jsou obvykle ve složce `Applications` s cestou podobnou `/Applications/AppName.app`. 

  Můžete přidat mnoho souborů, složek a aplikací. たとえば、次のように入力します。  
  
  - `/Applications/Calculator.app`
  - `/Applications`
  - `/Applications/Microsoft Office/root/Office16/winword.exe`
  - `/Users/UserName/music/itunes.app`
  
  Při přidávání libovolné aplikace, složky nebo souboru Nezapomeňte zadat správnou cestu. Ne všechny položky jsou ve složce `Applications`. Pokud uživatel přesune položku z jednoho umístění do druhé, cesta se změní. Tato přesunutá položka nebude otevřena, když se uživatel přihlásí.

## <a name="login-window"></a>ログイン ウィンドウ

### <a name="settings-apply-to-device-enrollment-and-automated-device-enrollment"></a>Nastavení platí pro: registrace zařízení a automatický zápis zařízení 

#### <a name="window-layout"></a>ウィンドウのレイアウト

- **メニュー バーに追加の情報を表示する**: メニュー バー上の時刻領域を選択すると、 **[許可]** にホスト名と macOS のバージョンが表示されます。 **[未構成]** (既定) の場合、この情報はメニュー バーには表示されません。
- **[バナー]** : デバイスのサインイン画面に表示されるメッセージを入力します。 たとえば、組織の情報、ようこそメッセージ、遺失物情報などを入力します。
- **[ログインの形式を選択する]** : ユーザーがデバイスにサインインする方法を選択します。 次のようなオプションがあります。
  - **[ユーザー名とパスワードの入力を求める]** (既定): ユーザーはユーザー名とパスワードを入力する必要があります。
  - **[すべてのユーザーを一覧表示して、パスワードの入力を求める]** : ユーザーはユーザーの一覧から自分のユーザー名を選び、パスワードを入力する必要があります。 以下も構成します:

    - **[ローカル ユーザー]** : **[非表示]** の場合、ユーザー一覧にローカル ユーザー アカウントは表示されません。標準および管理者アカウントも対象となることがあります。 ネットワークおよびシステム ユーザー アカウントのみ表示されます。 **[未構成]** (既定) の場合、ユーザー一覧にローカル ユーザー アカウントが表示されます。
    - **[モバイル アカウント]** : **[非表示]** の場合、ユーザー一覧にモバイル アカウントは表示されません。 **[未構成]** (既定) の場合、ユーザー一覧にモバイル アカウントが表示されます。 一部のモバイル アカウントは、ネットワーク ユーザーとして表示される場合があります。
    - **[ネットワーク ユーザー]** : **[表示]** を選択すると、ユーザー一覧にネットワーク ユーザーがリストされます。 **[未構成]** (既定) の場合、ユーザー一覧にネットワーク ユーザー アカウントが表示されません。
    - **[管理者ユーザー]** : **[非表示]** の場合、ユーザー一覧に管理者ユーザー アカウントは表示されません。 **[未構成]** (既定) の場合、ユーザー一覧に管理者ユーザー アカウントが表示されます。
    - **[他のユーザー]** : **[表示]** を選択すると、ユーザー一覧に **[その他]** ユーザーがリストされます。 **[未構成]** (既定) の場合、ユーザー一覧にその他のユーザー アカウントが表示されません。

#### <a name="login-screen-power-settings"></a>ログイン画面の電源設定

- **[システム終了ボタン]** : **[非表示]** の場合、サインイン画面にシステム終了ボタンが表示されません。 **[未構成]** (既定) の場合、システム終了ボタンが表示されます。
- **[[再起動] ボタン]** : **[非表示]** の場合、サインイン画面に再起動ボタンが表示されません。 **[未構成]** (既定) の場合、再起動ボタンが表示されます。
- **[スリープ ボタン]** : **[非表示]** の場合、サインイン画面にスリープ ボタンが表示されません。 **[未構成]** (既定) の場合、スリープ ボタンが表示されます。

#### <a name="other"></a>その他

- **[[コンソール] からユーザーのログインを無効にする]** : **[無効]** の場合、サインインに使用される macOS コマンドラインが非表示になります。 一般的なユーザーの場合、この設定は **[無効]** にします。 **[未構成]** (既定) の場合、上級ユーザーは macOS コマンドラインを使用してサインインすることができます。 ユーザーがコンソール モードに入るには、[ユーザー名] フィールドに `>console` を入力し、コンソール ウィンドウで認証を行う必要があります。

#### <a name="apple-menu"></a>Apple メニュー

ユーザーがデバイスにサインインした後どの操作ができるかは、次の設定によって影響を受けます。

- **[[システム終了] を無効にする]** : **[無効]** の場合、ユーザーはサインイン後 **[システム終了]** オプションを選択することができません。 **[未構成]** (既定) の場合、ユーザーはデバイスで **[システム終了]** メニュー項目を選択することができます。
- **[[再起動] を無効にする]** : **[無効]** の場合、ユーザーはサインイン後 **[再起動]** オプションを選択することができません。 **[未構成]** (既定) の場合、ユーザーはデバイスで **[再起動]** メニュー項目を選択することができます。
- **[[電源オフ] を無効にする]** : **[無効]** の場合、ユーザーはサインイン後 **[電源オフ]** オプションを選択することができません。 **[未構成]** (既定) の場合、ユーザーはデバイスで **[電源オフ]** メニュー項目を選択することができます。
- **[[ログアウト] を無効にする]** (macOS 10.13 以降): **[無効]** の場合、ユーザーはサインイン後 **[ログアウト]** オプションを選択することができません。 **[未構成]** (既定) の場合、ユーザーはデバイスで **[ログアウト]** メニュー項目を選択することができます。
- **[[ロック画面] を無効にする]** (macOS 10.13 以降): **[無効]** の場合、ユーザーはサインイン後 **[ロック画面]** オプションを選択することができません。 **[未構成]** (既定) の場合、ユーザーはデバイスで **[ロック画面]** メニュー項目を選択することができます。

## <a name="single-sign-on-app-extension"></a>シングル サインオン アプリの拡張機能

この機能は、以下に適用されます。

- macOS 10.15 以降

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: všechny typy registrace 

- **Typ rozšíření aplikace jednotného přihlašování**: Vyberte typ rozšíření aplikace jednotného přihlašování. 次のようなオプションがあります。

  - **Nenakonfigurováno**: rozšíření aplikací se nepoužívají. Pokud chcete zakázat rozšíření aplikace jednotného přihlašování, přepněte typ rozšíření aplikace jednotného přihlašování z **protokolu Kerberos** nebo **přihlašovací údaje** na **Nenakonfigurováno**.
  - **Přihlašovací údaje**: k použití jednotného přihlašování použijte obecné rozšíření aplikace s přizpůsobitelnou přihlašovacími údaji. Ujistěte se, že znáte ID rozšíření a ID týmu pro rozšíření aplikace jednotného přihlašování ve vaší organizaci.  
  - **Kerberos**: použijte integrované rozšíření protokolu Kerberos společnosti Apple, které je součástí macOS Catalina 10,15 a novějších. Tato možnost je verze rozšíření **přihlašovacích údajů** specifická pro Kerberos.

  > [!TIP]
  > Pomocí typu **přihlašovacích údajů** přidáte vlastní hodnoty konfigurace, které chcete předat prostřednictvím rozšíření. Místo toho zvažte použití předdefinovaného nastavení konfigurace poskytované společností Apple v typu **Kerberos** .

- **ID rozšíření** (jenom přihlašovací údaje): zadejte identifikátor sady prostředků, který identifikuje vaše rozšíření aplikace jednotného přihlašování, například `com.apple.ssoexample`.
- **ID týmu** (pouze přihlašovací údaje): zadejte identifikátor týmu rozšíření aplikace jednotného přihlašování. Identifikátor týmu je alfanumerický řetězec (čísla a písmena), který vygenerovala společnost Apple, například `ABCDE12345`. 

  [Najděte své ID týmu](https://help.apple.com/developer-account/#/dev55c3c710c) (otevře se webová stránka společnosti Apple), kde najdete další informace.

- **Sféra**: zadejte název sféry ověřování. Název sféry by měl být velkými písmeny, například `CONTOSO.COM`. Název vaší sféry je typicky stejný jako název vaší domény DNS, ale jenom na velká písmena.
- **Domény**: zadejte doménu nebo názvy hostitelů pro weby, které se dají ověřit pomocí jednotného přihlašování. Pokud je váš web například `mysite.contoso.com`, `mysite` je název hostitele a `contoso.com` je název domény. Když se uživatelé připojí k některé z těchto webů, aplikace App Extension zpracuje výzvu ověřování. Toto ověřování umožňuje uživatelům k přihlášení použít ID obličeje, dotykové ID nebo Apple PINCODE/přístupový kód.

  - Všechny domény v profilech služby Intune, které mají rozšíření pro aplikace jednotného přihlašování, musí být jedinečné. Doménu nemůžete opakovat v žádném profilu rozšíření aplikace pro přihlášení, i když používáte různé typy rozšíření aplikace jednotného přihlašování.
  - U těchto domén se nerozlišují velká a malá písmena.

- **Další konfigurace** (jenom přihlašovací údaje): zadejte další data specifická pro rozšíření, která chcete předat rozšíření aplikace jednotného přihlašování:
  - **Konfigurační klíč**: zadejte název položky, kterou chcete přidat, například `user name`.
  - **Typ hodnoty**: zadejte typ dat. 次のようなオプションがあります。

    - 文字列型
    - Boolean: v **hodnotě konfigurace**zadejte `True` nebo `False`.
    - Integer: v **hodnotě konfigurace**zadejte číslo.
    
  - **Hodnota konfigurace**: zadejte data.
  
  - **Přidat**: vyberte, pokud chcete přidat konfigurační klíče.

- **Použití řetězce klíčů** (jenom Kerberos): vyberte **blok** , aby se zabránilo ukládání a ukládání hesel do řetězce klíčů. **Nenakonfigurováno** (výchozí) umožňuje ukládat a ukládat hesla do řetězce klíčů.  
- **ID obličeje, dotykové ID nebo heslo** (jenom Kerberos): **vyžaduje** , aby uživatelé zadali své ID a dotykové ID, nebo Apple heslo pro přihlášení k doménám, které jste přidali. **Nenakonfigurováno** (výchozí) nevyžaduje, aby uživatelé používali biometrika nebo heslo pro přihlášení.
- **Výchozí sféra** (pouze Kerberos): Chcete-li nastavit hodnotu **sféry** , kterou jste zadali jako výchozí sféru, vyberte možnost **Povolit** . **Nenakonfigurováno** (výchozí) nenastavuje výchozí sféru.

  > [!TIP]
  > - Toto nastavení **Povolte** , pokud konfigurujete více rozšíření aplikace pro jednotné přihlašování pomocí protokolu Kerberos ve vaší organizaci.
  > - Toto nastavení **Povolte** , pokud používáte více sfér. Nastaví hodnotu **sféry** , kterou jste zadali jako výchozí sféru.
  > - Pokud máte pouze jednu sféru, ponechte ji **nenakonfigurovanou** (výchozí).

- **Automatická konfigurace** (jenom Kerberos): Pokud je nastavená na **blokovat**, nebude rozšíření protokolu Kerberos automaticky používat LDAP a DNS k určení jeho názvu lokality Active Directory. **Nenakonfigurováno** (výchozí) umožňuje rozšíření automaticky najít název lokality služby Active Directory.
- **Změny hesla** (jenom Kerberos): **blok** znemožní uživatelům měnit hesla, která používají pro přihlášení k doménám, které jste zadali. **Nenakonfigurováno** (výchozí) povolí změny hesla.  
- **Synchronizace hesel** (jenom Kerberos): Pokud chcete synchronizovat místní hesla uživatelů do Azure AD, vyberte **Povolit** . **Nenakonfigurováno** (výchozí) zakáže synchronizaci hesla do služby Azure AD. Toto nastavení použijte jako alternativu nebo zálohu k jednotnému přihlašování. Toto nastavení nefunguje, pokud jsou uživatelé přihlášení pomocí mobilního účtu Apple.
- **Složitost hesla služby Active Directory systému Windows Server** (pouze Kerberos): vyberte možnost **vyžadovat** , pokud chcete vynutit uživatelská hesla pro splnění požadavků na složitost hesla služby Active Directory. Další informace najdete v tématu [heslo musí splňovat požadavky na složitost](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/password-must-meet-complexity-requirements) . **Nenakonfigurováno** (výchozí) nevyžaduje, aby uživatelé splnili požadavky na heslo služby Active Directory.
- **Minimální délka hesla** (jenom Kerberos): zadejte minimální počet znaků, které můžou vytvořit heslo uživatele. **Nenakonfigurováno** (výchozí) neuplatňuje pro uživatele minimální délku hesla.
- **Omezení opakovaného použití hesla** (jenom Kerberos): zadejte počet nových hesel, od 1-24, které se musí použít, až bude možné znovu použít předchozí heslo v doméně. **Nenakonfigurováno** (výchozí) neuplatňuje limit opakovaného použití hesla.
- **Minimální stáří hesla** (jenom Kerberos): zadejte počet dní, po které se musí heslo v doméně používat, než ho uživatel může změnit. **Nenakonfigurováno** (výchozí) neuplatňuje minimální stáří hesla, než bude možné je změnit.
- **Oznámení vypršení platnosti hesla** (jenom Kerberos): zadejte počet dní, než heslo vyprší, uživatelé obdrží oznámení o vypršení platnosti hesla. **Nenakonfigurováno** (výchozí) používá `15` dní.
- **[パスワードの有効期限]** (Kerberos のみ): デバイス パスワードの変更が必要になるまでの日数を入力します。 **Nenakonfigurováno** (výchozí) znamená, že uživatelská hesla nikdy nevyprší.
- **Hlavní název** (jenom Kerberos): zadejte uživatelské jméno objektu zabezpečení protokolu Kerberos. Nemusíte zahrnovat název sféry. Například v `user@contoso.com``user` je hlavní název a `contoso.com` je název sféry.
- **Kód lokality služby Active Directory** (pouze Kerberos): zadejte název lokality služby Active Directory, kterou má rozšíření protokolu Kerberos použít. Tuto hodnotu pravděpodobně nebudete muset měnit, protože rozšíření protokolu Kerberos může automaticky najít kód lokality služby Active Directory.
- **Název mezipaměti** (jenom Kerberos): zadejte název obecné služby zabezpečení (GSS) mezipaměti protokolu Kerberos. Tuto hodnotu pravděpodobně nemusíte nastavovat.  
- **Zpráva požadavky na heslo** (jenom Kerberos): zadejte textovou verzi požadavků na heslo vaší organizace, které se zobrazují uživatelům. Zpráva se zobrazí, pokud nepožadujete požadavky na složitost hesla služby Active Directory nebo nezadáte minimální délku hesla.  
- **ID sady prostředků aplikace** (jenom Kerberos): **přidejte** identifikátory sady prostředků aplikace, které by měly na svých zařízeních používat jednotné přihlašování. Těmto aplikacím je udělen přístup k lístku pro udělení lístku protokolu Kerberos, ověřovacímu lístku a ověřování uživatelů pro služby, kterým mají oprávnění k přístupu.
- **Mapování sféry domény** (jenom Kerberos): **přidejte** přípony DNS domény, které by se měly namapovat do vaší sféry. Toto nastavení použijte, pokud názvy DNS hostitelů neodpovídají názvu sféry. Pravděpodobně nemusíte vytvářet vlastní mapování domén na sféru.
- **Certifikát PKINIT** (jenom Kerberos): **Vyberte** certifikát kryptografie s veřejným klíčem pro počáteční ověřování (PKINIT), který se dá použít k obnovení přihlašovacích údajů Kerberos bez zásahu uživatele. Certifikát by měl být certifikát PKCS nebo SCEP, který jste dříve přidali do Intune.

## <a name="associated-domains"></a>関連付けられたドメイン

Intune では、次のことができます。

- Přidejte mnoho přidružení aplikace k doméně.
- Přidružte mnoho domén ke stejné aplikaci.

この機能は、以下に適用されます。

- macOS 10.15 以降

### <a name="settings-apply-to-all-enrollment-types"></a>Nastavení platí pro: všechny typy registrace

- **ID aplikace**: zadejte identifikátor aplikace, který se má přidružit k webu. Identifikátor aplikace zahrnuje ID týmu a ID sady: `TeamID.BundleID`.

  ID týmu je alfanumerické znaky (písmena a čísla) vygenerované společností Apple pro vývojáře aplikací, například `ABCDE12345`. [Vyhledejte ID týmu](https://help.apple.com/developer-account/#/dev55c3c710c)  (otevře web společnosti Apple) obsahuje další informace.

  ID sady prostředků jednoznačně identifikuje aplikaci a obvykle je ve formátu zpětného zápisu názvů domén. Například ID sady Finder je `com.apple.finder`. Pokud chcete najít ID sady, použijte AppleScript v terminálu:

  `osascript -e 'id of app "ExampleApp"'`

- **Doména**: zadejte doménu webu, kterou chcete přidružit k aplikaci. Doména zahrnuje typ služby a plně kvalifikovaný název hostitele, například `webcredentials:www.contoso.com`.

  Všechny subdomény přidružené domény můžete vyhledat zadáním `*.` (zástupný znak hvězdička a tečka) před začátkem domény. Období je povinné. Přesné domény mají vyšší prioritu než u domén se zástupnými znaky. Modely z nadřazených domén se tedy shodují, *Pokud* se shoda nenajde v plně kvalifikované subdoméně.

  Typ služby může být:

  - **authsrv**: シングル サインオン アプリの拡張機能
  - **applink**: Universal Link
  - **webcredentials**: Automatické vyplňování hesel

- **Přidat**: vyberte, pokud chcete přidat své aplikace a přidružené domény.

> [!TIP]
> Pokud chcete řešit potíže, otevřete na zařízení macOS možnosti **Předvolby systému** > **profily**. Ověřte, že profil, který jste vytvořili, je v seznamu profily zařízení. Pokud je v seznamu uveden, ujistěte se, že je **Konfigurace přidružených domén** v profilu a obsahuje správné ID aplikace a domény.

## <a name="next-steps"></a>次のステップ

[プロファイルを割り当てて](device-profile-assign.md)、[その状態を監視](device-profile-monitor.md)します。

Můžete taky nakonfigurovat funkce zařízení v [iOS](ios-device-features-settings.md).
