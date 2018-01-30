---
title: "Nastavení omezení registrace v Intune"
titlesuffix: Azure portal
description: "Omezení registrace podle platformy a nastavení limitu počtu zařízení pro registraci zařízení v Intune \""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3e3f35648784de860eb7e3f2e203488bc77a96d
ms.sourcegitcommit: a41ad9988a8c14e6b15123a9ea9bc29ac437a4ce
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="set-enrollment-restrictions"></a>Nastavení omezení registrace

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Jako správce Intune můžete vytvořit a spravovat omezení registrace definující počet a typy zařízení, u kterých můžete zaregistrovat správu přes Intune. Můžete vytvořit více omezení a použít je u různých skupin uživatelů. Pro různá omezení můžete nastavit [pořadí priority](#change-enrollment-restriction-priority).

>[!NOTE]
>Omezení registrací nepatří k funkcím zabezpečení. Ohrožená zařízení mohou poskytovat zavádějící informace. Tato omezení jsou jen určitou bariérou pro uživatele bez zlých úmyslů.

>[!NOTE]
>Níže popsané omezení registrace přiřazené skupinám a funkce priority se v současnosti zavádí napříč zákaznickou základnou Intune. Než se zavedení dokončí, možná nebudete mít k funkcím skupin a priority přístup. 

Mezi konkrétní omezení registrace, která můžete vytvořit, patří:

- Maximální počet zaregistrovaných zařízení
- Platformy zařízení, které se mohou zaregistrovat:
  - Android
  - Android for Work
  - iOS
  - macOS
  - Windows
- Verze operačního systému platformy iOS, Android, Android for Work a Windows (můžou být použity jenom verze Windows 10; pokud je povolený systém Windows 8.1, ponechte toto prázdné)
  - Minimální verze
  - Maximální verze
- Omezení soukromých zařízení (pouze iOS, Android, Android for Work a macOS)

## <a name="default-restrictions"></a>Výchozí omezení

Pro omezení registrace typu i limitu počtu zařízení se automaticky poskytnou výchozí omezení. Možnosti výchozích omezení můžete změnit. Výchozí omezení se použijí pro všechny registrace zařízení s uživateli i bez uživatelů. Tato výchozí omezení můžete přepsat tak, že vytvoříte nová omezení s vyšší prioritou.

## <a name="create-a-restriction"></a>Vytvoření omezení

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby**, vyhledejte **Intune** a zvolte **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. Zvolte **Vytvořit omezení**.
5. Pojmenujte omezení a zadejte jeho popis.
6. Zvolte **Typ omezení** a pak klikněte na **Vytvořit**.
7. Pokud u omezení počtu zařízení chcete nastavit maximální počet zařízení, která uživatel může zaregistrovat, klikněte na **Limit počtu zařízení**.
8. Pokud u omezení typu zařízení chcete povolit nebo blokovat různé platformy a verze, klikněte na **Platformy** a **Konfigurace platforem**.
9. Klikněte na **Přiřazení** > **+ Vybrat skupiny**.
10. V části **Vybrat skupiny** vyberte alespoň jednu skupinu a klikněte na **Vybrat**. Omezení platí jenom u skupin, ke kterým je přiřazeno. Pokud omezení nepřiřadíte alespoň k jedné skupině, nebude mít žádný efekt.
11. Klikněte na **Uložit**.
12. Priorita nově vytvořeného omezení bude o jeden stupeň vyšší než výchozí omezení. [Prioritu můžete změnit](#change-enrollment-restriction-priority).

## <a name="set-device-type-restrictions"></a>Nastavení omezení typů zařízení

Nastavení omezení typu zařízení můžete změnit podle následujícího postupu:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby**, vyhledejte **Intune** a zvolte **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. V části **Omezení typů zařízení** zvolte omezení, které chcete nastavit.
5. V části názvu omezení (u výchozího omezení se jedná o **Všichni uživatelé**) vyberte **Platformy**. U každé uvedené platformy zvolte **Povolit** nebo **Blokovat**.
6. Klikněte na **Uložit**.
7. V části názvu omezení (u výchozího omezení se jedná o **Všichni uživatelé**) zvolte **Konfigurace platforem** a u uvedených platforem vyberte minimální a maximální **verzi**. Podporované verze zahrnují:
  - Android a Android for Work podporují major.minor.rev.build.
  - Systém iOS podporuje major.minor.rev.
  - Systém Windows podporuje jenom major.minor.rev.build pro Windows 10.
  Verze operačního systému se nevztahují na zařízení Apple registrovaná v Programu registrace zařízení, pomocí Apple School Manageru ani v aplikaci Apple Configurator. 
8. U každé uvedené platformy zadejte, zda chcete **Povolit** nebo **Blokovat**  zařízení **v osobním vlastnictví**.

    ![Snímek obrazovky pracovního prostoru Omezení zařízení s výchozími konfiguracemi platformy zařízení zobrazující konfiguraci nastavení pro osobní vlastnictví](media/device-restrictions-platform-configurations.png)
9. Klikněte na **Uložit**.

>[!NOTE]
>- Když zablokujete registraci zařízení s Androidem v osobním vlastnictví, stále půjde zaregistrovat zařízení v osobním vlastnictví, která používají verzi Android for Work.
>- Ve výchozím nastavení budou nastavení zařízení s Androidem for Work stejná jako nastavení zařízení s Androidem. Po změně nastavení Androidu for Work tomu už tak nebude.
>- Pokud zablokujete registraci Androidu for Work u osobních zařízení, budou se jako Android for Work moct zaregistrovat jenom firemní zařízení s Androidem.

## <a name="set-device-limit-restrictions"></a>Nastavení omezení limitů počtu zařízení

Nastavení omezení počtu zařízení můžete změnit podle následujícího postupu:

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby**, vyhledejte **Intune** a zvolte **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. V části **Omezení počtu zařízení** zvolte omezení, které chcete nastavit.
5. Zvolte **Limit počtu zařízení** a potom v rozevíracím seznam vyberte maximální počet zařízení, která uživatel může zaregistrovat.
    ![Snímek obrazovky okna Omezení limitů počtů zařízení s omezením limitu počtu zařízení](./media/device-restrictions-limit.png)
6. Klikněte na **Uložit**.

## <a name="change-enrollment-restriction-priority"></a>Změna priority omezení registrace

Priorita se používá, když uživatel existuje v několika skupinách, ke kterým jsou přiřazena omezení. Uživatelé podléhají jenom omezení s nejvyšší prioritou přiřazenému ke skupině, ve které se nacházejí. Jan je například ve skupině A, která má přiřazena omezení s prioritou 5, a ve skupině B, na kterou se vztahují omezení s prioritou 2. U Jana se uplatní jenom omezení s prioritou 2. 

Když vytvoříte omezení, přidá se do seznamu bezprostředně nad výchozí omezení.

Registrace zařízení obsahuje výchozí omezení jak pro omezení typu zařízení, tak pro omezení limitu počtu zařízení. Tato dvě omezení platí pro všechny uživatele, pokud je nepřepíšete omezeními s vyšší prioritou. 

Prioritu kteréhokoli nevýchozího omezení můžete změnit. 

**Změna priority omezení**

1. Přihlaste se k portálu Azure Portal.
2. Zvolte **Další služby**, vyhledejte **Intune** a zvolte **Intune**.
3. Zvolte **Registrace zařízení** > **Omezení registrace**.
4. Najeďte kurzorem myši na omezení v seznamu priorit.
5. Pomocí tří svislých teček přetáhněte prioritu na požadované místo v seznamu.





