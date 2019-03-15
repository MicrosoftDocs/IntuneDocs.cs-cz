---
title: Nastavení omezení registrace v Microsoft Intune
titlesuffix: ''
description: Omezení registrace podle platformy a nastavení limitu počtu zařízení pro registraci zařízení v Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 08/17/2018
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 8e86285d81527d16486ce592d16937b679720d51
ms.sourcegitcommit: 25e6aa3bfce58ce8d9f8c054bc338cc3dff4a78b
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/14/2019
ms.locfileid: "57390379"
---
# <a name="set-enrollment-restrictions"></a>Nastavení omezení registrace

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce Intune můžete vytvořit a spravovat omezení registrace definující počet a typy zařízení, u kterých můžete zaregistrovat správu přes Intune. Můžete vytvořit více omezení a použít je u různých skupin uživatelů. Pro různá omezení můžete nastavit [pořadí priority](#change-enrollment-restriction-priority).

>[!NOTE]
>Omezení registrací nepatří k funkcím zabezpečení. Ohrožená zařízení mohou poskytovat zavádějící informace. Tato omezení jsou jen určitou bariérou pro uživatele bez zlých úmyslů.

Mezi konkrétní omezení registrace, která můžete vytvořit, patří:

- Maximální počet zaregistrovaných zařízení
- Platformy zařízení, které se mohou zaregistrovat:
  - Android
  - Pracovní profil Androidu
  - iOS
  - macOS
  - Windows
- Verze operačního systému platformy pro iOS, Android, pracovní profil Androidu a Windows. (Je možné použít jenom verze Windows 10. Pokud jsou povolená Windows 8.1., nechejte prázdné.)
  - Minimální verze
  - Maximální verze
- Omezení soukromých zařízení (jen iOS, Android, pracovní profil Androidu, macOS a Windows)

## <a name="default-restrictions"></a>Výchozí omezení

Pro omezení registrace typu i limitu počtu zařízení se automaticky poskytnou výchozí omezení. Možnosti výchozích omezení můžete změnit. Výchozí omezení se použijí pro všechny registrace zařízení s uživateli i bez uživatelů. Tato výchozí omezení můžete přepsat tak, že vytvoříte nová omezení s vyšší prioritou.

## <a name="create-a-restriction"></a>Vytvoření omezení

1. Přihlaste se k portálu Azure.
2. Zvolte **Další služby**, vyhledejte **Intune** a zvolte **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. Zvolte **Vytvořit omezení**.
5. Pojmenujte omezení a zadejte jeho popis.
6. Zvolte **Typ omezení** a pak zvolte na **Vytvořit**.
7. Pokud u omezení počtu zařízení chcete nastavit maximální počet zařízení, která uživatel může zaregistrovat, zvolte **Limit počtu zařízení**.
8. Pokud u omezení typu zařízení chcete povolit nebo blokovat různé platformy a verze, zvolte **Platformy** a **Konfigurace platforem**.
9. Zvolte **Přiřazení** > **+ Vybrat skupiny**.
10. V části **Vybrat skupiny** vyberte alespoň jednu skupinu a pak zvolte **Vybrat**. Omezení platí jenom u skupin, ke kterým je přiřazené. Pokud omezení nepřiřadíte alespoň k jedné skupině, nebude mít žádný efekt.
11. Vyberte **Uložit**.
12. Priorita nově vytvořeného omezení bude o jeden stupeň vyšší než výchozí omezení. [Prioritu můžete změnit](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Nastavení omezení typů zařízení

Nastavení omezení typu zařízení můžete změnit podle následujícího postupu. Tato omezení nemají vliv na zařízení, která jsou už zaregistrovaná. Pomocí této funkce se nedají blokovat zařízení zaregistrovaná prostřednictvím [agenta Intune pro počítače](manage-windows-pcs-with-microsoft-intune.md).

1. Přihlaste se k portálu Azure.
2. Zvolte **Další služby**, vyhledejte **Intune** a zvolte **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. V části **Omezení typů zařízení** zvolte omezení, které chcete nastavit > **Vlastnosti** > **Vyberte platformy**. U každé uvedené platformy zvolte **Povolit** nebo **Blokovat**.
    ![Obrazovka s volbami pro povolení nebo blokování platformy](media/enrollment-restrictions-set/platform-allow-block.png)
5. Zvolte **OK**.
6. Zvolte **Konfigurovat platformy**.
    ![Obrazovka s volbou pro konfiguraci platforem](media/enrollment-restrictions-set/configure-platforms.png)
7. Vyberte minimální a maximální **verze** uvedených platforem. Podporované formáty verzí:
    - Pracovní profil Androidu podporuje major.minor.rev.build.
    - Systém iOS podporuje major.minor.rev. Verze operačního systému se nevztahují na zařízení Apple registrovaná v Programu registrace zařízení, pomocí Apple School Manageru ani v aplikaci Apple Configurator.
    - Systém Windows podporuje jenom major.minor.rev.build pro Windows 10.
> [!Note]
> Windows 10 neposkytuje číslo sestavení během registrace, tak pro instanci, pokud zadáte do 10.0.17134.100 a zařízení je 10.0.17134.174 se zablokuje při registraci.
8. U každé uvedené platformy vyberte, zda chcete **Povolit** nebo **Blokovat**  zařízení **v osobním vlastnictví**.
9. Zvolte **OK**.

### <a name="blocking-personal-android-devices"></a>Blokování osobních zařízení s Androidem
- Když zablokujete registraci osobních zařízení s Androidem, stále půjde zaregistrovat osobní zařízení s pracovním profilem Androidu.
- Nastavení zařízení s pracovním profilem Androidu jsou stejná jako nastavení zařízení s Androidem. Po změně nastavení pracovního profilu Androidu tomu už tak nebude.
- Pokud zablokujete registraci pracovního profilu Androidu u osobních zařízení, budou se jako pracovní profil Androidu moci zaregistrovat jen firemní zařízení s Androidem.

### <a name="blocking-personal-windows-devices"></a>Blokování osobních zařízení s Windows
Když zablokujete registraci osobních zařízení s Windows, Intune u každého nového požadavku na registraci zařízení s Windows zkontroluje, jestli se autorizoval jako firemní registrace. Neautorizované registrace se zablokují.

K registraci zařízení s Windows ve společnosti jsou povoleny následující metody:
 - Uživatel se registruje pomocí [účtu správce registrace zařízení]( device-enrollment-manager-enroll.md).
- Zařízení se registruje prostřednictvím programu [Windows AutoPilot](enrollment-autopilot.md).
- K registraci zařízení se použije Windows Autopilot, ale nejedná se o jedinou možnost registrace MDM z nastavení Windows.
- Číslo IMEI zařízení je uvedené v seznamu **Registrace zařízení** > **[Identifikátory podnikových zařízení](corporate-identifiers-add.md)**. (Nepodporuje se ve Windows Phone 8.1.)
- Zařízení se registruje v rámci [balíčku hromadného zřizování](windows-bulk-enroll.md).
- Zařízení se zaregistruje prostřednictvím objektu zásad skupiny, nebo [automatickou registraci z SCCM pro spolusprávu](https://docs.microsoft.com/sccm/core/clients/manage/co-management-overview#how-to-configure-co-management.md).
 
Následující registrace služba Intune sice označuje jako registrace ve společnosti, ale budou zablokovány vzhledem k tomu, že správci Intune neumožňují kontrolu na úrovni jednotlivých zařízení:
 - [Automatická registrace MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) s [připojením k Azure Active Directory během instalace Windows](https://docs.microsoft.com/azure/active-directory/device-management-azuread-joined-devices-frx)\*.
- [Automatická registrace MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) s [připojením k Azure Active Directory z nastavení Windows](https://docs.microsoft.com/azure/active-directory/user-help/user-help-register-device-on-network).*
 
Zablokují se také následující metody osobní registrace:
- [Automatická registrace MDM](windows-enroll.md#enable-windows-10-automatic-enrollment) s [přidáním pracovního účtu z nastavení Windows](https://docs.microsoft.com/azure/active-directory/user-help/user-help-join-device-on-network)\*.
- Volba [Jen registrace MDM]( https://docs.microsoft.com/windows/client-management/mdm/mdm-enrollment-of-windows-devices#connecting-personally-owned-devices-bring-your-own-device) v nastavení Windows.

\*Nezablokují se, pokud se k registraci použije Autopilot.

## <a name="set-device-limit-restrictions"></a>Nastavení omezení limitů počtu zařízení

Nastavení omezení počtu zařízení můžete změnit podle následujícího postupu:

1. Přihlaste se k portálu Azure.
2. Zvolte **Další služby**, vyhledejte **Intune** a zvolte **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. V části **Omezení počtu zařízení** zvolte omezení, které chcete nastavit.
5. Zvolte **Limit počtu zařízení** a pak v rozevíracím seznam vyberte maximální počet zařízení, která uživatel může zaregistrovat.
    ![Okno Omezení limitů počtů zařízení s omezením limitu počtu zařízení](./media/device-restrictions-limit.png)
6. Vyberte **Uložit**.


Během registrace BYOD uživatelům se zobrazí oznámení, že se při dosažení limitu počtu zaregistrovaných zařízení. Například v iOSu vypadá takto:

![Oznámení o dosažení limitu počtu zařízení s iOSem](./media/enrollment-restrictions-ios-set-limit-notification.png)

Omezení limitu počtu zařízení se nedá použít pro následující typy podnikové registrace Windows:

- Spoluspravovaná registrace
- Objekt zásad skupiny registrací
- Registrace připojené služby Azure Active Directory
- Registrace připojené hromadné Azure Active Directory
- Registrace AutoPilot

Omezení zařízení můžete nastavit pro tyto typy registrace [ve službě Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/devices/device-management-azure-portal#configure-device-settings).

## <a name="change-enrollment-restriction-priority"></a>Změna priority omezení registrace

Priorita se používá, když uživatel existuje v několika skupinách, ke kterým jsou přiřazena omezení. Uživatelé podléhají jenom omezení s nejvyšší prioritou přiřazenému ke skupině, ve které se nacházejí. Jan je například ve skupině A, která má přiřazena omezení s prioritou 5, a také ve skupině B, na kterou se vztahují omezení s prioritou 2. U Jana se uplatní jenom omezení s prioritou 2.

Když vytvoříte omezení, přidá se do seznamu bezprostředně nad výchozí omezení.

Registrace zařízení obsahuje výchozí omezení jak pro omezení typu zařízení, tak pro omezení limitu počtu zařízení. Tato dvě omezení platí pro všechny uživatele, pokud je nepřepíšete omezeními s vyšší prioritou.

Prioritu kteréhokoli nevýchozího omezení můžete změnit.

1. Přihlaste se k portálu Azure.
2. Zvolte **Další služby**, vyhledejte **Intune** a zvolte **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. Najeďte kurzorem myši na omezení v seznamu priorit.
5. Pomocí tří svislých teček přetáhněte prioritu na požadované místo v seznamu.
