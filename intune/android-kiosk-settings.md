---
title: Nastavení beznabídkového režimu Androidu v Microsoft Intune – Azure | Microsoft Docs
description: Zařízení s Androidem v beznabídkovém režimu můžete nakonfigurovat jako zařízení v beznabídkovém režimu s jednou nebo více aplikacemi.
keywords: ''
author: MandiOhlinger
ms.author: mandia
manager: dougeby
ms.date: 9/13/2018
ms.topic: article
ms.prod: ''
ms.service: microsoft-intune
ms.technology: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.openlocfilehash: 5cd16a351beefd851d51175717abd4400382c216
ms.sourcegitcommit: 51b763e131917fccd255c346286fa515fcee33f0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/20/2018
ms.locfileid: "52185232"
---
# <a name="kiosk-settings-for-android-devices-in-intune"></a>Nastavení beznabídkového režimu zařízení s Androidem v Intune

Nastavením konfigurace zařízení můžete zařízení nastavit do beznabídkového režimu s jednou nebo více aplikacemi. Když je zařízení v beznabídkovém režimu, je jeho použití omezené na aplikace nebo webové odkazy definované profilem omezení. 

## <a name="restrict-an-android-kiosk-device-to-a-single-app"></a>Omezení zařízení s Androidem v beznabídkovém režimu na jednu aplikaci

Pokud je profil omezení zařízení v beznabídkovém režimu nastavený na **Beznabídkový režim** = **Veřejný terminál s jednou aplikací**, mají uživatelé přístup jen k jedné aplikaci. Když se zařízení nakonfigurované v tomto režimu zapne, spustí se tato konkrétní aplikace. Uživatelé nemůžou otevírat nové aplikace ani měnit spuštěnou aplikaci.

1. Zajistěte, aby aplikace, kterou chcete na zařízení v beznabídkovém režimu používat, byla [nasazena do zařízení](apps-deploy.md) a přiřazena skupině zařízení, kterou jste pro tato zařízení vytvořili.
2. Přejděte na [portál Intune](https://portal.azure.com) a zvolte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. V okně **Vytvořit profil** nastavte následující pole:
     - **Název**
     - **Platforma**: Android Enterprise
     - **Typ profilu**: Jen vlastník zařízení > Omezení zařízení
4. Zvolte **Nastavení** > **Veřejný terminál**.
5. Jako **Beznabídkový režim** zvolte **Veřejný terminál s jednou aplikací**.
6. Zvolte **Vyberte spravovanou aplikaci** a pak ve spravovaném obchodu Google Play vyberte aplikaci, která má být jedinou aplikací dostupnou v zařízeních s tímto profilem.
7. Zvolte **OK** > **OK** > **OK** > **Vytvořit**.
8. Zvolte právě vytvořený profil > **Přiřazení**.
9. V oblasti **Přiřadit k** zvolte **Vybrané skupiny**.
10. Zvolte **Vybrat skupiny, které se zahrnou** > zvolte skupinu zařízení, kterou jste vytvořili pro zařízení v beznabídkovém režimu > **Vybrat**.

## <a name="restrict-a-kiosk-device-to-a-set-of-apps-or-web-links"></a>Omezení zařízení v beznabídkovém režimu na sadu aplikací nebo webových odkazů

Pokud je profil omezení zařízení v beznabídkovém režimu nastavený na **Beznabídkový režim** = **Beznabídkový režim s více aplikacemi**, mají uživatelé přístup jen k omezenému počtu nakonfigurovaných aplikací. Můžete také definovat sadu webových odkazů, které uživatelé můžou navštěvovat. Při uplatnění této zásady vidí uživatelé na domovské obrazovce ikony povolených aplikací.

Následujícím postupem nastavíte u zařízení s Androidem v beznabídkovém režimu více aplikací:

1. [Import a nasazení aplikace Managed Home Screen ze spravovaného obchodu Google Play](#import-and-deploy-the-managed-home-screen-app)
2. [Přidání a přiřazení aplikací, které lze používat v beznabídkovém režimu](#add-and-assign-apps-that-can-be-used-in-kiosk-mode)
3. (Volitelné) [Přidání webových odkazů, které lze používat v beznabídkovém režimu](#add-web-links-that-can-be-used-in-kiosk-mode)

### <a name="import-and-deploy-the-managed-home-screen-app"></a>Import a nasazení aplikace Managed Home Screen

1. Přejděte na [stránku Managed Home Screen v obchodu Google Play](https://play.google.com/work/apps/details?id=com.microsoft.launcher.enterprise) a přihlaste se pod stejným účtem, který používáte pro jiné aplikace ze spravovaného obchodu Google Play.
2. Zvolte **Schválit**.
3. Přejděte na [portál Intune](https://portal.azure.com) a zvolte **Klientské aplikace** > **Spravovaný obchod Google Play** > **Synchronizovat**.
4. Zvolte **Aplikace** > **Managed Home Screen** > **Přiřazení** > **Přidat skupinu**.
5. Jako **Typ přiřazení** zvolte **Povinné**.
6. Zvolte **Zahrnuté skupiny** > **Vybrat skupiny, které se zahrnou** > zvolte skupinu zařízení, kterou jste vytvořili pro zařízení v beznabídkovém režimu > **Vybrat** > **OK** > **OK** > **Uložit**.

> [!NOTE]
> Když přidáte aplikaci Managed Home Screen do profilu beznabídkového režimu s více aplikacemi, přidá se ikona. Ale když tuto ikonu vyberete, nic se nestane. Proto tuto aplikaci nemusíte do profilu beznabídkového režimu s více aplikacemi ani přidávat.

### <a name="add-and-assign-apps-that-can-be-used-in-kiosk-mode"></a>Přidání a přiřazení aplikací, které lze používat v beznabídkovém režimu

U každé aplikace, která má být na zařízeních v beznabídkovém režimu dostupná, postupujte takto:

1. [Přidejte aplikaci do Intune](store-apps-android.md).
2. Zvolte **Klientské aplikace** > **Aplikace** > zvolte aplikaci > **Přiřazení** > **Přidat skupinu**.
3. Jako **Typ přiřazení** zvolte **Povinné**.
4. Zvolte **Zahrnuté skupiny** > **Vybrat skupiny, které se zahrnou** > zvolte skupinu zařízení, kterou jste vytvořili pro zařízení v beznabídkovém režimu > **Vybrat** > **OK** > **OK** > **Uložit**.

### <a name="add-web-links-that-can-be-used-in-kiosk-mode"></a>Přidání webových odkazů, které lze používat v beznabídkovém režimu

1. Přejděte na [portál Intune](https://portal.azure.com) a zvolte **Klientské aplikace** > **Aplikace** > **Přidat**.
2. Jako **Typ aplikace** zvolte **Webový odkaz**.
3. Zvolte **Konfigurovat** a zadejte potřebné informace. Nemusíte přidávat obrázek loga, protože se automaticky načte ze souboru favicon.ico daného webu.
4. Zvolte **OK** > **Přidat**.

Ověřte, že jste do zařízení s beznabídkovým režimem nasadili webovou aplikaci. Další informace najdete v části [Přidání webových aplikací do Microsoft Intune](web-app.md).

### <a name="create-a-multi-app-kiosk-profile"></a>Vytvoření profilu beznabídkového režimu s více aplikacemi

1. Přejděte na [portál Intune](https://portal.azure.com) a zvolte **Konfigurace zařízení** > **Profily** > **Vytvořit profil**.
3. V okně **Vytvořit profil** nastavte následující pole:
     - **Název**: Zadejte výstižný název.
     - **Platforma**: Android Enterprise
     - **Typ profilu**: Jen vlastník zařízení > Omezení zařízení
4. Zvolte **Nastavení** > **Veřejný terminál**.
5. Jako **Beznabídkový režim** zvolte **Beznabídkový režim s více aplikacemi**.
6. Zvolte **Přidat** a vyberte aplikace nebo webové odkazy, které mají být dostupné na zařízeních s tímto profilem.
7. Zvolte **OK** > **OK** > **OK** > **Vytvořit**.
8. Zvolte právě vytvořený profil > **Přiřazení**.
9. V oblasti **Přiřadit k** zvolte **Vybrané skupiny**.
10. Zvolte **Vybrat skupiny, které se zahrnou** > zvolte skupinu zařízení, kterou jste vytvořili pro zařízení v beznabídkovém režimu > **Vybrat** > **Uložit**.

## <a name="next-steps"></a>Další postup
[Přiřaďte profil](device-profile-assign.md) a [monitorujte jeho stav](device-profile-monitor.md).
