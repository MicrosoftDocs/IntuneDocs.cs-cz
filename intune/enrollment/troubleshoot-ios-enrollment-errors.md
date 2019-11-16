---
title: Microsoft Intune での iOS デバイスの登録に関する問題のトラブルシューティング
titleSuffix: Microsoft Intune
description: Návrhy pro řešení některých nejběžnějších problémů při registraci zařízení se systémem iOS v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 07/25/2019
ms.topic: troubleshooting
ms.service: microsoft-intune
ms.subservice: enrollment
ms.localizationpriority: medium
ms.technology: ''
ms.assetid: ''
ms.reviewer: mghadial
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 03ceaf5493f544dbb815146eb67c3fae8856d29e
ms.sourcegitcommit: 5c52879f3653e22bfeba4eef65e2c86025534dab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/16/2019
ms.locfileid: "74126146"
---
# <a name="troubleshoot-ios-device-enrollment-problems-in-microsoft-intune"></a>Microsoft Intune での iOS デバイスの登録に関する問題のトラブルシューティング

Tento článek pomáhá správcům Intune pochopit a řešit problémy při registraci zařízení se systémem iOS v Intune.

## <a name="prerequisites"></a>必要条件

Než začnete řešit potíže, je důležité shromáždit některé základní informace. Tyto informace vám pomůžou lépe porozumět problému a zkrátit dobu, po kterou je možné najít řešení.

Shromážděte následující informace o problému:

- 正確なエラー メッセージは何ですか?
- エラー メッセージはどこに表示されますか?
- 問題が発生し始めたのはいつですか? Byl zápis někdy zpracován?
- Jakou platformu (Android, iOS, Windows) má problém?
- Kolik uživatelů je ovlivněno? Ovlivnili všichni uživatelé nebo jen některé?
- Kolik zařízení je ovlivněno? Jsou všechna zařízení ovlivněná nebo jenom některá?
- Co je Autorita MDM? Pokud je System Center Configuration Manager, jakou verzi Configuration Manager používáte?
- Jak se provádí registrace? Přináší vaše vlastní zařízení (BYOD) nebo Apple Program registrace zařízení (DEP) pomocí profilů zápisu?

## <a name="error-messages"></a>エラー メッセージ

### <a name="profile-installation-failed-a-network-error-has-occurred"></a>プロファイルのインストールに失敗しました。 ネットワーク エラーが発生しました。

**Příčina:** Došlo k nespecifikovanému problému se systémem iOS na zařízení.

#### <a name="resolution"></a>解決方法

1. Aby nedošlo ke ztrátě dat v následujících krocích (obnovení iOS odstraní všechna data v zařízení), ujistěte se, že zálohujete data.
2. Zařízení umístěte do režimu obnovení a pak ho obnovte. Ujistěte se, že jste ji nastavili jako nové zařízení. Další informace o tom, jak obnovit zařízení s iOS, najdete v tématu [https://support.apple.com/HT201263](https://support.apple.com/HT201263).
3. デバイスを再度登録します。

### <a name="profile-installation-failed-connection-to-the-server-could-not-be-established"></a>プロファイルのインストールに失敗しました。 サーバーへの接続を確立できませんでした。

**Příčina:** Váš tenant Intune je nakonfigurovaný tak, aby povoloval jenom zařízení vlastněná společností. 

#### <a name="resolution"></a>解決方法
1. Azure ポータルにサインインします。
2. **[その他のサービス]** を選択して、Intune を検索した後、 **[Intune]** を選択します。
3. **[デバイスの登録]**  >  **[登録の制限]** を選択します。
4. **[デバイスの種類の制限]** で、>**プロパティ** >  設定する制限を選択し、 **[プラットフォームの選択]** > [ **iOS**で**許可**する] の順に選択し、[ **OK]** をクリックします。
5. Vyberte **Konfigurovat platformy**, vyberte možnost **povoleno** pro zařízení s iOS v osobním vlastnictví a pak klikněte na **OK**.
6. デバイスを再度登録します。

### <a name="this-service-is-not-supported-no-enrollment-policy"></a>Tato služba se nepodporuje. 登録ポリシーがありません。

**Příčina**: certifikát Apple MDM push Certificate není v Intune nakonfigurovaný, nebo je certifikát neplatný. 

#### <a name="resolution"></a>解決方法

- Pokud není nabízený certifikát MDM nakonfigurovaný, postupujte podle kroků v části [získání certifikátu Apple MDM push Certificate](apple-mdm-push-certificate-get.md#steps-to-get-your-certificate).
- Pokud je certifikát MDM push Certificate neplatný, postupujte podle kroků v části [obnovení certifikátu Apple MDM push Certificate](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).

### <a name="company-portal-temporarily-unavailable-the-company-portal-app-encountered-a-problem-if-the-problem-persists-contact-your-system-administrator"></a>ポータル サイトは一時的に使用できません。 V aplikaci Portál společnosti došlo k problému. 問題が解決しない場合は、システム管理者に問い合わせてください。

**Příčina:** Aplikace Portál společnosti není aktuální nebo je poškozená.

#### <a name="resolution"></a>解決方法
1. デバイスからポータル サイト アプリを削除します。
2. **App Store**から **Microsoft Intune ポータル サイト** アプリをダウンロードしてインストールします。
3. デバイスを再度登録します。
 > [!NOTE]
    > K této chybě může dojít také v případě, že se uživatel pokouší zaregistrovat více zařízení, než je registrace zařízení nakonfigurovaná tak, aby povolovala. Pokud tyto kroky problém nevyřeší, postupujte podle kroků v části řešení pro limit **zařízení** .

### <a name="device-cap-reached"></a>デバイス キャップに達しました

**Příčina:** Uživatel se pokusí zaregistrovat více zařízení, než je limit pro registraci zařízení.

#### <a name="resolution"></a>解決方法
1. [Intune 管理ポータル](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) >  台の**デバイス** > **すべてのデバイス** を開き、ユーザーが登録したデバイスの数を確認します。
    > [!NOTE]
    > Měli byste také mít vliv na přihlášení ovlivněného uživatele na [uživatelský portál Intune](https://portal.manage.microsoft.com/) a ověřit zařízení, která jsou zaregistrovaná. Můžou existovat zařízení, která se zobrazují na [uživatelském portálu Intune](https://portal.manage.microsoft.com/) , ale ne na [portálu pro správu Intune](https://portal.azure.com/?Microsoft_Intune=1&Microsoft_Intune_DeviceSettings=true&Microsoft_Intune_Enrollment=true&Microsoft_Intune_Apps=true&Microsoft_Intune_Devices=true#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview). Tato zařízení se také počítají do limitu registrace zařízení.
2. Přejít na **správce** > **správa mobilních zařízení** > **pravidla registrace** > Ověřte limit registrace zařízení. 既定では、制限は 15 に設定されています。 
3. Pokud počet zaregistrovaných zařízení dosáhl limitu, odeberte nepotřebná zařízení nebo zvyšte limit pro registraci zařízení. Vzhledem k tomu, že všechna zaregistrovaná zařízení využívají licenci Intune, doporučujeme, abyste nejdřív odebrali nepotřebná zařízení.
4. デバイスを再度登録します。

### <a name="workplace-join-failed"></a>Workplace Join se nezdařilo

**Příčina:** Aplikace Portál společnosti není aktuální nebo je poškozená.  

#### <a name="resolution"></a>解決方法
1. デバイスからポータル サイト アプリを削除します。
2. **App Store**から **Microsoft Intune ポータル サイト** アプリをダウンロードしてインストールします。
3. デバイスを再度登録します。

### <a name="user-license-type-invalid"></a>Neplatný typ uživatelské licence

**Příčina:** Uživatel, který se pokouší zaregistrovat zařízení, nemá platnou licenci Intune.

#### <a name="resolution"></a>解決方法
1. [Microsoft 365 管理センター](https://portal.office.com/adminportal/home#/homepage)にアクセスし、 **[ユーザー]**  >  **[アクティブなユーザー]** の順に選択します。
2. Vyberte ovlivněný uživatelský účet > **licence k produktům** >  –**Upravit**.
3. Ověřte, jestli se tomuto uživateli přiřadí platná licence Intune.
4. デバイスを再度登録します。

### <a name="user-name-not-recognized-this-user-account-is-not-authorized-to-use-microsoft-intune-contact-your-system-administrator-if-you-think-you-have-received-this-message-in-error"></a>ユーザー名を認識できません。 Tento uživatelský účet nemá autorizaci používat Microsoft Intune. Pokud si myslíte, že jste tuto zprávu dostali omylem, obraťte se na správce systému.

**Příčina:** Uživatel, který se pokouší zaregistrovat zařízení, nemá platnou licenci Intune.

1. [Microsoft 365 管理センター](https://portal.office.com/adminportal/home#/homepage)にアクセスし、 **[ユーザー]**  >  **[アクティブなユーザー]** の順に選択します。
2. Vyberte ovlivněný uživatelský účet a pak zvolte **licence na produkty** > **Upravit**.
3. Ověřte, jestli se tomuto uživateli přiřadí platná licence Intune.
4. デバイスを再度登録します。

### <a name="profile-installation-failed-the-new-mdm-payload-does-not-match-the-old-payload"></a>プロファイルのインストールに失敗しました。 Nová datová část MDM se neshoduje se starou datovou částí.

**Příčina:** V zařízení je již nainstalován profil pro správu.

#### <a name="resolution"></a>解決方法

1. IOS デバイスの **設定** を開き、 **全般** >  **デバイス管理**> ます。
2. Klepněte na existující profil pro správu a klepněte na **Odebrat správu**.
3. デバイスを再度登録します。

### <a name="noenrollmentpolicy"></a>NoEnrollmentPolicy

**Příčina:** Certifikát služby Apple Push Notification Service (APNs) chybí, je neplatný nebo vypršela jeho platnost.

#### <a name="resolution"></a>解決方法
Ověřte, že se do Intune přidal platný certifikát APNs. 詳細については、[iOS および Mac のデバイス管理の設定](https://docs.microsoft.com/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)に関するページをご覧ください。 

### <a name="accountnotonboarded"></a>AccountNotOnboarded

**Příčina:** Došlo k potížím s certifikátem APNs (Apple Push Notification Service), který je nakonfigurovaný v Intune.

#### <a name="resolution"></a>解決方法
Obnovte certifikát APNs a pak zařízení znovu zaregistrujte.

> [!IMPORTANT]
> Ujistěte se, že jste obnovili certifikát APNs. Neměňte certifikát APNs. Pokud certifikát nahradíte, budete muset znovu zaregistrovat všechna zařízení s iOS v Intune. 

- Informace o obnovení certifikátu APNs v samostatné službě Intune najdete v tématu [obnovení certifikátu Apple MDM push Certificate](apple-mdm-push-certificate-get.md#renew-apple-mdm-push-certificate).
- Informace o obnovení certifikátu APNs v programu Intune Hybrid pomocí Configuration Manager najdete v tématu [nastavení hybridní správy zařízení s iOS pomocí System Center Configuration Manager a Microsoft Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/enroll-hybrid-ios-mac).
- Informace o obnovení certifikátu APNs v Office 365 najdete v tématu [Vytvoření certifikátu APNS pro zařízení s iOS](https://support.office.com/article/Create-an-APNs-Certificate-for-iOS-devices-522b43f4-a2ff-46f6-962a-dd4f47e546a7).

### <a name="xpc_type_error-connection-invalid"></a>Neplatné připojení XPC_TYPE_ERROR

Když zapnete zařízení spravované pomocí programu DEP, které má přiřazený profil registrace, registrace se nepovede a zobrazí se tato chybová zpráva:

```
asciidoc
mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" } }
iPhone mobileassetd[83] <Notice>: Client connection invalid (Connection invalid); terminating connection
iPhone com.apple.accessibility.AccessibilityUIServer(MobileAsset)[288] <Notice>: [MobileAssetError:29] Unable to copy asset information from https://mesu.apple.com/assets/ for asset type com.apple.MobileAsset.VoiceServices.CombinedVocalizerVoices
iPhone mobileassetd[83] <Notice>: 0x1a49aebc0 Client connection: XPC_TYPE_ERROR Connection invalid <error: 0x1a49aebc0> { count = 1, transaction: 0, voucher = 0x0, contents = "XPCErrorDescription" => <string: 0x1a49aee18> { length = 18, contents = "Connection invalid" }
```

**Příčina:** Mezi zařízením a službou Apple DEP dojde k problému s připojením.

#### <a name="resolution"></a>解決方法
Opravte problém s připojením nebo použijte k registraci zařízení jiné síťové připojení. Pokud se problém opakuje, může se také stát, že budete muset kontaktovat společnost Apple.


## <a name="other-issues"></a>その他の問題

### <a name="dep-enrollment-doesnt-start"></a>Registrace DEP se nespustí.
Když zapnete zařízení spravované pomocí programu DEP, které má přiřazený profil registrace, proces registrace Intune se iniciuje.

**Příčina:** Profil registrace se vytvoří před nahráním tokenu DEP do Intune.

#### <a name="resolution"></a>解決方法

1. Upravte registrační profil. V profilu můžete provádět změny. Účelem je aktualizovat čas změny profilu.
2. Synchronizace zařízení spravovaných programem DEP: Otevřete portál Intune > **správce** > **správa mobilních zařízení** > **iOS** > **program registrace zařízení** > **Sync Now**. 同期要求が Apple に送信されます。

### <a name="dep-enrollment-stuck-at-user-login"></a>Registrace DEP zablokování při přihlášení uživatele
Když zapnete zařízení spravované pomocí programu DEP, kterému je přiřazený profil registrace, počáteční nastavení po zadání přihlašovacích údajů.

**Příčina:** Multi-Factor Authentication (MFA) je povolené. V tuto chvíli MFA nefunguje během registrace na zařízeních DEP.

#### <a name="resolution"></a>解決方法
Zakažte MFA a pak zařízení znovu zaregistrujte.

## <a name="next-steps"></a>次のステップ

- [Intune のデバイス登録に関するトラブルシューティング](../troubleshoot-device-enrollment-in-intune.md)
- [Intune フォーラムで質問する](https://social.technet.microsoft.com/Forums/%7Blang-locale%7D/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)
- [Podívejte se na blog týmu podpory Microsoft Intune.](https://techcommunity.microsoft.com/t5/Intune-Customer-Success/bg-p/IntuneCustomerSuccess)
- [Podívejte se na blog Microsoft Enterprise mobility and Security.](https://techcommunity.microsoft.com/t5/Azure-Active-Directory-Identity/Announcing-the-public-preview-of-Azure-AD-group-based-license/ba-p/245210)
