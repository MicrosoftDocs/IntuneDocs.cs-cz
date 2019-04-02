---
title: Nastavení registrace v Intune pro zařízení s Androidem Enterprise dedicated
titleSuffix: Microsoft Intune
description: Zjistěte, jak zaregistrovat zařízení s Androidem Enterprise dedicated v Intune.
keywords: ''
author: ErikjeMS
ms.author: erikje
manager: dougeby
ms.date: 1/15/2019
ms.topic: conceptual
ms.prod: ''
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: ''
ms.reviewer: chrisbal
ms.suite: ems
search.appverid: MET150
ms.custom: seodec18
ms.collection: M365-identity-device-management
ms.openlocfilehash: 5e980049797ffc3c727d89c197037c019b94326a
ms.sourcegitcommit: 484a898d54f5386fdbce300225aaa3495cecd6b0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/01/2019
ms.locfileid: "58798039"
---
# <a name="set-up-intune-enrollment-of-android-enterprise-dedicated-devices"></a>Nastavení Intune registrace podnikových zařízení s Androidem dedicated

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Android Enterprise podporuje zařízení vlastněných společností, jedno použití veřejného terminálu – vizuální styl s nastavenou řešení vyhrazená zařízení. Taková zařízení se používají k jednomu účelu, například jako zobrazovací zařízení na veřejných místech, k tisku vstupenek nebo k evidenci zásob. Správci omezí použití zařízení na omezenou sadu aplikací a webových odkazů. Uživatelé zároveň nemůžou na tomto zařízení přidávat jiné aplikace ani provádět jiné akce.

Intune vám pomůže nasadit aplikace a nastavení pro zařízení s Androidem Enterprise dedicated. Konkrétní podrobnosti o Androidu Enterprise, najdete v části [požadavky na Androidu enterprise](https://support.google.com/work/android/answer/6174145?hl=en&ref_topic=6151012).

Zařízení, která se spravují tímto způsobem, jsou v Intune zaregistrovaná bez uživatelského účtu a nejsou přidružená k žádnému koncovému uživateli. Nejsou určená pro osobní používání aplikací, které závisejí na datech spojených s účtem konkrétního uživatele, jako je Outlook nebo Gmail.

## <a name="device-requirements"></a>Požadavky na zařízení

Zařízení musí splňovat tyto požadavky pro správu jako vyhrazená zařízení s Androidem Enterprise:

- Verze operačního systému Android 5.1 a vyšší
- Zařízení musí používat distribuci Androidu s připojením ke službě GMS (Google Mobile Services). Zařízení musí mít dostupnou službu GMS a musí být schopna se k této službě připojit.

## <a name="set-up-android-enterprise-dedicated-device-management"></a>Nastavení správy pro zařízení s Androidem Enterprise vyhrazené

Nastavení správy pro zařízení s Androidem Enterprise vyhrazené, postupujte podle těchto kroků:

1. Při přípravě na správu mobilních zařízení musíte [nastavit autoritu pro správu mobilních zařízení (MDM) na **Microsoft Intune**](mdm-authority-set.md) podle pokynů. Tato možnost se nastavuje jenom jednou při prvním nastavování Intune pro správu mobilních zařízení.
2. [Připojte si účet tenanta Intune ke svému účtu spravovaný obchod Google Play](connect-intune-android-enterprise.md).
3. [Vytvořte registrační profil](#create-an-enrollment-profile).
4. [Vytvořte skupinu zařízení](#create-a-device-group).
5. [Registrace zařízení vyhrazená](#enroll-the-dedicated-devices).

### <a name="create-an-enrollment-profile"></a>Vytvoření profilu registrace

Tak, aby vyhrazená zařízení můžete zaregistrovat, musíte vytvořit registrační profil. Po vytvoření poskytne tento profil registrační token (náhodný řetězec) a kód QR. V závislosti na operační systém Android a verze zařízení, můžete použít buď tokenu nebo kódu QR [registrace zařízení s vyhrazenou](#enroll-the-dedicated-devices).

1. Přejděte na [portál Intune](https://portal.azure.com) a zvolte **registrace zařízení** > **registrace zařízení s Androidem** > **vlastněné podniková dedicated zařízení**.
2. Zvolte **Vytvořit** a vyplňte požadovaná pole.
    - **Název**: Zadejte název, který budete používat při přiřazování profilu dynamická skupina zařízení.
    - **Datum vypršení platnosti tokenu**: Datum vypršení platnosti tokenu. Google vynucuje maximálně 90 dnů.
3. Uložte profil pomocí tlačítka **Vytvořit**.

### <a name="create-a-device-group"></a>Vytvoření skupiny zařízení

Aplikace a zásady můžete cílit buď na přiřazené, nebo dynamické skupiny zařízení. Následujícím postupem nakonfigurujete dynamické skupiny zařízení služby AAD tak, aby se automaticky naplnily zařízeními, která se zaregistrují s konkrétním registračním profilem:

1. Přejděte na [portál Intune](https://portal.azure.com) a zvolte **Skupiny** > **Všechny skupiny** > **Nová skupina**.
2. V okně **Skupina** vyplňte požadovaná pole následujícím způsobem:
    - **Typ skupiny**: Zabezpečení
    - **Název skupiny**: Zadejte intuitivní název (třeba objekt pro vytváření 1 zařízení)
    - **Typ členství**: Dynamické zařízení
3. Zvolte **Přidat dynamický dotaz**.
4. V okně **Pravidla dynamického členství** vyplňte pole následujícím způsobem:
    - **Přidat dynamické pravidlo členství**: Jednoduché pravidlo
    - **Přidat zařízení, kde**: Název registračního profilu
    - V prostředním poli zvolte **Shoda**.
    - Do posledního pole zadejte název dříve vytvořeného registračního profilu.
    Další informace o pravidlech dynamického členství najdete v tématu [Pravidla dynamického členství pro skupiny v AAD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership). 
5. Zvolte **Přidat dotaz** > **Vytvořit**.

### <a name="replace-or-remove-tokens"></a>Nahrazení nebo odebrání tokenů

Tokeny a kódy QR můžete nahradit nebo odebrat.

- **Nahradit token**: Když jedna vypršení platnosti přiblíží pomocí nahradit Token, můžete vygenerovat nový token/QR kód.
- **Odvolat token**: Okamžitě můžete ukončit platnost tokenu/QR kód. Od tohoto okamžiku nebude token nebo kód QR použitelný. Tuto možnost můžete použít, pokud:
    - Omylem nasdílíte token nebo kód QR s neautorizovanou stranou
    - Dokončíte všechny registrace a token nebo kód QR už nepotřebujete

Nahrazení nebo odvolání tokenu/kódu QR nebude mít žádný vliv na zařízení, která už jsou zaregistrovaná.

1. Přejděte [portálu Intune](https://portal.azure.com) a zvolte **registrace zařízení** > **registrace zařízení s Androidem** > **podnikových vlastní vyhrazený zařízení**.
2. Zvolte profil, se kterým chcete pracovat.
3. Zvolte **Token**.
4. Pokud chcete token nahradit, zvolte **Nahradit token**.
5. Pokud chcete token odvolat, zvolte **Odvolat token**.

## <a name="enroll-the-dedicated-devices"></a>Registrace vyhrazená zařízení.

Teď můžete [zaregistrovat svoje zařízení vyhrazené](android-dedicated-devices-fully-managed-enroll.md).

## <a name="managing-apps-on-android-enterprise-dedicated-devices"></a>Správa aplikací na zařízeních s Androidem Enterprise vyhrazené

Jenom aplikace, které mají typ přiřazení [nastavit na požadované](apps-deploy.md#assign-an-app) se dá nainstalovat na zařízení s Androidem Enterprise dedicated. Aplikace jsou nainstalované spravovaný obchod Google Play storu stejným způsobem jako s Androidem Enterprise pracovní profil zařízení.

Když vývojář aplikace publikuje aktualizaci do obchodu Google Play, aktualizují se aplikace na spravovaných zařízeních automaticky.

K odebrání aplikace ze zařízení s Androidem Enterprise dedicated, můžete provést jeden z následujících akcí:
-   Odstranění nasazení povinné aplikace
-   Vytvoření nasazení odinstalace pro tuto aplikaci

## <a name="next-steps"></a>Další postup
- [Nasadit aplikace pro Android](apps-deploy.md)
- [Přidání zásad konfigurace pro Android](device-profiles.md)
