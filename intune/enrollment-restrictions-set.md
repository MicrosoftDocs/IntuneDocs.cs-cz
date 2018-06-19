---
title: Nastavení omezení registrace v Microsoft Intune
titlesuffix: ''
description: Omezení registrace podle platformy a nastavení limitu počtu zařízení pro registraci zařízení v Intune
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 03/02/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9b17cb50ead094962196bb030c3a18e4119c6904
ms.sourcegitcommit: 5eba4bad151be32346aedc7cbb0333d71934f8cf
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31026325"
---
# <a name="set-enrollment-restrictions"></a>Nastavení omezení registrace

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Jako správce Intune můžete vytvořit a spravovat omezení registrace definující počet a typy zařízení, u kterých můžete zaregistrovat správu přes Intune. Můžete vytvořit více omezení a použít je u různých skupin uživatelů. Pro různá omezení můžete nastavit [pořadí priority](#change-enrollment-restriction-priority).

>[!NOTE]
>Omezení registrací nepatří k funkcím zabezpečení. Ohrožená zařízení mohou poskytovat zavádějící informace. Tato omezení jsou jen určitou bariérou pro uživatele bez zlých úmyslů.

>[!NOTE]
>Omezení registrace přiřazené skupinám a funkce priority v tomto článku se v současnosti zavádějí napříč zákaznickou základnou Intune. Než se zavedení dokončí, možná nebudete mít k funkcím skupin a priority přístup.

Mezi konkrétní omezení registrace, která můžete vytvořit, patří:

- Maximální počet zaregistrovaných zařízení
- Platformy zařízení, které se mohou zaregistrovat:
  - Android.
  - Android for Work
  - iOS
  - macOS
  - Windows
- Verze operačního systému platformy pro iOS, Android, Android for Work a systém Windows. (Je možné použít jenom verze Windows 10. Pokud jsou povolená Windows 8.1., nechejte prázdné.)
  - Minimální verze
  - Maximální verze
- Omezení soukromých zařízení (jenom iOS, Android, Android for Work a macOS)

## <a name="default-restrictions"></a>Výchozí omezení

Pro omezení registrace typu i limitu počtu zařízení se automaticky poskytnou výchozí omezení. Možnosti výchozích omezení můžete změnit. Výchozí omezení se použijí pro všechny registrace zařízení s uživateli i bez uživatelů. Tato výchozí omezení můžete přepsat tak, že vytvoříte nová omezení s vyšší prioritou.

## <a name="create-a-restriction"></a>Vytvoření omezení

1. Přihlaste se k portálu Azure Portal.
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

Nastavení omezení typu zařízení můžete změnit podle následujícího postupu:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby**, vyhledejte **Intune** a zvolte **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. V části **Omezení typů zařízení** zvolte omezení, které chcete nastavit.
5. V části názvu omezení (u výchozího omezení se jedná o **Všichni uživatelé**) vyberte **Platformy**. U každé uvedené platformy zvolte **Povolit** nebo **Blokovat**.
6. Vyberte **Uložit**.
7. V části názvu omezení (u výchozího omezení se jedná o **Všichni uživatelé**) vyberte **Konfigurace platformy**. Pak vyberte minimální a maximální **Verze** pro uvedené platformy. Podporované verze zahrnují:
    - Android a Android for Work podporují major.minor.rev.build.
    - Systém iOS podporuje major.minor.rev.
    - Systém Windows podporuje jenom major.minor.rev.build pro Windows 10.
  Verze operačního systému se nevztahují na zařízení Apple registrovaná v Programu registrace zařízení, pomocí Apple School Manageru ani v aplikaci Apple Configurator.
8. U každé uvedené platformy zadejte, zda chcete **Povolit** nebo **Blokovat**  zařízení **v osobním vlastnictví**.
    ![Pracovní prostor Omezení zařízení s výchozími konfiguracemi platformy zařízení zobrazující konfiguraci nastavení pro osobní vlastnictví](media/device-restrictions-platform-configurations.png)
9. Vyberte **Uložit**.


>[!NOTE]
>- Když zablokujete registraci zařízení s Androidem v osobním vlastnictví, stále půjde zaregistrovat zařízení v osobním vlastnictví, která používají verzi Android for Work.
>- Ve výchozím nastavení jsou nastavení zařízení s Androidem for Work stejná jako nastavení zařízení s Androidem. Po změně nastavení Androidu for Work tomu už tak nebude.
>- Pokud zablokujete registraci Androidu for Work u osobních zařízení, budou se jako Android for Work moct zaregistrovat jenom firemní zařízení s Androidem.

## <a name="set-device-limit-restrictions"></a>Nastavení omezení limitů počtu zařízení

Nastavení omezení počtu zařízení můžete změnit podle následujícího postupu:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby**, vyhledejte **Intune** a zvolte **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. V části **Omezení počtu zařízení** zvolte omezení, které chcete nastavit.
5. Zvolte **Limit počtu zařízení** a pak v rozevíracím seznam vyberte maximální počet zařízení, která uživatel může zaregistrovat.
    ![Okno Omezení limitů počtů zařízení s omezením limitu počtu zařízení](./media/device-restrictions-limit.png)
6. Vyberte **Uložit**.


Při dosažení limitu počtu zaregistrovaných zařízení se uživatelům zobrazí oznámení. Například v iOSu vypadá takto:

![Oznámení o dosažení limitu počtu zařízení s iOSem](./media/enrollment-restrictions-ios-set-limit-notification.png)

## <a name="change-enrollment-restriction-priority"></a>Změna priority omezení registrace

Priorita se používá, když uživatel existuje v několika skupinách, ke kterým jsou přiřazena omezení. Uživatelé podléhají jenom omezení s nejvyšší prioritou přiřazenému ke skupině, ve které se nacházejí. Jan je například ve skupině A, která má přiřazena omezení s prioritou 5, a také ve skupině B, na kterou se vztahují omezení s prioritou 2. U Jana se uplatní jenom omezení s prioritou 2.

Když vytvoříte omezení, přidá se do seznamu bezprostředně nad výchozí omezení.

Registrace zařízení obsahuje výchozí omezení jak pro omezení typu zařízení, tak pro omezení limitu počtu zařízení. Tato dvě omezení platí pro všechny uživatele, pokud je nepřepíšete omezeními s vyšší prioritou.

Prioritu kteréhokoli nevýchozího omezení můžete změnit.

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby**, vyhledejte **Intune** a zvolte **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. Najeďte kurzorem myši na omezení v seznamu priorit.
5. Pomocí tří svislých teček přetáhněte prioritu na požadované místo v seznamu.
