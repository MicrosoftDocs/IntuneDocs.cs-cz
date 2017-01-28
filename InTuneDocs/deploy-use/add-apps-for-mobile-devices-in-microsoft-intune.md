---
title: "Přidávání aplikací pro zaregistrovaná zařízení | Dokumentace Microsoftu"
description: "Před nasazením aplikace je třeba přidat ji do Intune. Pak je k dispozici v konzole Intune, kde ji můžete nasadit a spravovat."
keywords: 
author: robstackmsft
ms.author: robstack
manager: angrobe
ms.date: 01/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5b1f1ae-f177-450a-9af9-936a02d052e3
ms.reviewer: mghadial
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 18f200ca30cfcd4c9fb00519c149f48e9b9fa8cb
ms.openlocfilehash: b566b13f8c93c8a6bddccdbc0da5eb508907dac2


---

# <a name="add-apps-for-enrolled-devices-to-intune"></a>Přidávání aplikací pro zaregistrovaná zařízení do Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Než budete moci aplikaci nasadit nebo spravovat, je třeba přidat ji do Microsoft Intune. V tomto tématu je uveden postup při přidávání aplikací pro zaregistrovaná zařízení.


> [!IMPORTANT]
> Informace uvedené v tomto tématu vám pomůžou při přidávání aplikací, které chcete nasadit, do zaregistrovaných zařízení a zaregistrovaných počítačů s Windows. Pokud chcete přidat aplikace pro počítače s Windows, které spravujete pomocí klientského softwaru Intune, projděte si téma [Přidání aplikací pro počítače s Windows v Microsoft Intune](add-apps-for-windows-pcs-in-microsoft-intune.md).

## <a name="add-the-app"></a>Přidání aplikace
Pomocí Vydavatele softwaru Microsoft Intune nakonfigurujete vlastnosti aplikace a (kde je to potřeba) ji nahrajete do cloudového úložiště. Použijte následující postup:

1.  V [konzole pro správu Microsoft Intune](https://manage.microsoft.com) vyberte **Aplikace** &gt; **Přidat aplikace**. Spustí se Vydavatel softwaru Intune.

    > [!TIP]
    > Před spuštěním vydavatele softwaru možná budete muset zadat svoje uživatelské jméno a heslo k Intune.

2.  Na stránce **Instalace softwaru** ve vydavateli vyberte u položky **Vyberte, jakým způsobem má být tento software zpřístupněn pro zařízení** jednu z těchto možností:
    - **Instalační program softwaru** – u aplikací s příponou **.msi**:
        - **Vyberte typ souboru instalačního programu softwaru**. Označuje typ softwaru, který chcete nasadit. Pokud třeba chcete instalovat aplikaci pro iOS, zvolte **Balíček aplikace pro systém iOS (soubor &#42;.ipa)**.
        - **Zadejte umístění instalačních souborů softwaru**. Zadejte umístění instalačních souborů, nebo zvolte **Procházet** a vyberte umístění ze seznamu.
        - **Zahrňte další soubory a podsložky ze stejné složky**. Tato možnost je jen pro typ souboru **Instalační služby systému Windows**.<br>Software, který používá Instalační službu systému Windows, někdy potřebuje podpůrné soubory. Ty se většinou nacházejí ve stejné složce jako instalační soubory. Tuto možnost vyberte, když chcete tyto soubory i nasadit.<br>U tohoto typu instalace se využívá část prostoru cloudového úložiště.

  -   **Externí odkaz** – u aplikací, které chcete vytvořit zadáním odkazu na obchod s aplikacemi:

        - **Zadejte adresu URL**. Zadejte některou z těchto adres URL:
            - Adresa URL obchodu s aplikacemi obsahujícího aplikaci, kterou chcete nasadit. Pokud třeba chcete nasadit aplikaci Vzdálená plocha od Microsoftu pro Android, zadejte **https://play.google.com/store/apps/details?id=com.microsoft.rdc.android**.<br>Pokud chcete vyhledat adresu URL aplikace, pomocí vyhledávacího webu najděte stránku obchodu, který aplikaci obsahuje. Pokud budete chtít najít třeba aplikaci Vzdálená plocha, můžete vyhledat výraz **Microsoft Vzdálená plocha Android**.
            - Web. Intune nasadí na zařízení ikonu zástupce odkazující na daný web.
            - Aplikace na webu. Intune nasadí na zařízení ikonu zástupce odkazující na danou aplikaci.
        - **K otevření tohoto odkazu se vyžaduje spravovaný prohlížeč (jenom Android a iOS):** Když nasadíte odkaz na web nebo do webové aplikace pro uživatele, budou ho moct otevřít jen v prohlížeči spravovaném přes Intune. Tento prohlížeč musí být nainstalovaný na jejich zařízení.<br>Další podrobnosti o spravovaném prohlížeči najdete v tématu [Správa přístupu k internetu pomocí zásad spravovaného prohlížeče v Microsoft Intune](manage-internet-access-using-managed-browser-policies.md).<br>U tohoto typu instalace se nepoužívá žádný prostor cloudového úložiště.

  -   **Spravovaná aplikace pro iOS z App Storu** – u bezplatných aplikací z obchodu iTunes, které chcete spravovat pomocí zásad pro správu mobilních aplikací (MAM):

        - **Zadejte adresu URL**. Zadejte adresu URL obchodu s aplikacemi obsahujícího aplikaci, kterou chcete nasadit. Pokud třeba chcete nasadit aplikaci Pracovní složky pro iOS od Microsoftu, zadejte adresu **https://itunes.apple.com/us/app/work-folders/id950878067?mt=8**.<br>U tohoto typu instalace se nepoužívá žádný prostor cloudového úložiště.

        Pokud třeba chcete nasadit na zařízení aplikaci Microsoft Word z obchodu iTunes, stránka bude vypadat takto:

        ![Intune Software Publisher](./media/publisher-for-mobile.png)

> [!NOTE]
> Pokud chcete přidat a nasadit aplikaci z obchodu, musí mít koncoví uživatelé u tohoto obchodu zřízený účet, aby si aplikaci mohli nainstalovat.

3.  Na stránce **Popis softwaru** nakonfigurujte následující nastavení:

    > [!TIP]
    > Některé hodnoty můžou být vyplněné automaticky v závislosti na používaném typu instalačního programu.

    - **Vydavatel:** Zadejte název vydavatele aplikace.
    - **Název**. Zadejte název aplikace, který se zobrazí na portálu společnosti.<br>Ověřte, že názvy všech používaných aplikací jsou jedinečné. Pokud stejný název aplikace existuje dvakrát, zobrazí se na portálu společnosti uživatelům jenom jedna z aplikací.
    - **Popis**. Zadejte popis aplikace. Zobrazí se uživatelům na portálu společnosti.
    - **Adresa URL informací o softwaru:** Ta je k dispozici jenom v případě, že jste vybrali **Instalační program softwaru**. Volitelně můžete zadat adresu URL webu, který obsahuje informace o této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Adresa URL zásad ochrany osobních údajů:** Ta je k dispozici jenom v případě, že jste vybrali **Instalační program softwaru**. Volitelně můžete zadat adresu URL webu, který obsahuje informace o ochraně osobních údajů v této aplikaci. Adresa URL se zobrazí uživatelům na portálu společnosti.
    - **Kategorie** (volitelné). Vyberte jednu z předdefinovaných kategorií aplikací. Uživatelé ji budou moct při procházení portálu snáz najít.
    - **Zobrazit jako doporučenou aplikaci a upozornit na ni na portálu společnosti:** Když uživatelé hledají aplikace, zobrazí se aplikace výrazně na hlavní stránce portálu společnosti.
    - **Ikona** (volitelné): Nahrajte ikonu, která bude k aplikaci přidružená. Tato ikona se u aplikace zobrazí, když uživatelé procházejí portál společnosti.

        V tomto příkladu jste nakonfigurovali popis aplikace Microsoft Word pro iOS:

        ![Příklad popisu softwaru](./media/ios-software-description.png)

4.  Na stránce **Požadavky** vyberte požadavky, které je potřeba splnit, aby bylo možné aplikaci na zařízení nainstalovat. Například u balíčku aplikace pro iOS můžete vybrat minimální požadovanou verzi iOS. Kromě toho můžete vybrat typ zařízení, který je třeba použít, třeba iPhone nebo iPad.

    > [!TIP]
    > Stránka **Požadavky** se nezobrazuje u všech typů aplikací.

5.  Další stránky průvodce se zobrazí, pokud zvolíte typ souboru **Instalační služba systému Windows**. Tento typ souboru se používá, když nasazujete software do počítačů s Windows 10 nebo novějším systémem, které jsou zaregistrované v Intune.

6.  Na stránce **Shrnutí** zkontrolujte zadané informace. Až budete připravení, zvolte **Odeslat**.

7.  Postup dokončíte výběrem možnosti **Zavřít**.

Aplikace se zobrazí v uzlu **Aplikace** v pracovním prostoru **Aplikace**.

## <a name="example---deploying-msi-applications-to-windows-10-devices"></a>Příklad: Nasazení aplikací .msi na zařízení s Windows 10
V tomto čtyřminutovém videu získáte informace o postupu při nasazování aplikací typu Instalační služba systému Windows (.msi) na zaregistrovaná zařízení s Windows 10.<br><br>

<iframe src="https://channel9.msdn.com/Series/How-to-Control-the-Uncontrolled/6--How-to-Deploy-MSI-Applications-to-Windows-10-Using-Intune-and-Mobile-Device-Management-MDM/player" width="640" height="360" allowFullScreen frameBorder="0"></iframe>

## <a name="next-steps"></a>Další kroky

Dalším krokem po vytvoření aplikace je její nasazení. Další informace najdete v tématu [Nasazení aplikací v Microsoft Intune](deploy-apps.md).



<!--HONumber=Jan17_HO2-->


