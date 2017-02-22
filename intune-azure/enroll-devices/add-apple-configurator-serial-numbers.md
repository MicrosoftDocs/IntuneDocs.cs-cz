---
title: "Přidání sériových čísel Apple Configuratoru | Intune Azure Preview | Dokumentace Microsoftu"
description: "Intune Azure Preview: Přečtěte si, jak pomocí Apple Configuratoru přidat sériová čísla k zařízením se systémem iOS, která vlastní firma."
keywords: 
author: staciebarker
ms.author: stabar
manager: angrobe
ms.date: 02/03/17
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d408aa38-7d1e-40df-9067-246e53f6e26f
ms.reviewer: dagerrit
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 65a6b2e22359bdcb9b0c15a84c6b3586dafe4d6c
ms.openlocfilehash: 71d29a245f8f900a7427528167bae0b52565d42b


---

# <a name="add-apple-configurator-serial-numbers"></a>Přidání sériových čísel Apple Configuratoru 

[!INCLUDE[azure_preview](../includes/azure_preview.md)]

Tento postup použijte, pokud chcete přidat sériová čísla k Intune, když chcete [zaregistrovat zařízení se systémem iOS vlastněná firmou pomocí Apple Configuratoru s Průvodcem nastavením](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). Sériová čísla můžete přidávat postupně nebo můžete nahrát soubor se sériovými čísly ve formátu CSV. K přidaným číslům můžete přiřadit profil. Profil obsahuje specifická nastavení správy, která chcete použít u zařízení. 

Další metody registrace zařízení s iOSem jsou popsané v článku [Volba způsobu registrace zařízení s iOSem v Intune](choose-ios-enrollment-method.md).

**Přidání sériových čísel Apple Configuratoru k Intune**

1. Vytvořte seznam hodnot oddělených čárkami se dvěma sloupci (.csv) bez záhlaví. Do levého sloupce přidejte identifikátor IMEI a v pravém sloupci uveďte podrobnosti. Aktuálně je maximální počet řádků v seznamu 500. V textovém editoru vypadá seznam CSV přibližně takto:

    F7TLWCLBX196,podrobnosti o zařízení</br>
    DLXQPCWVGHMJ,podrobnosti o zařízení

2. Na portálu Azure Portal zvolte **Další služby**, do textového pole zadejte **Intune** a pak zvolte **Jiné** > **Intune**.

3.  V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Registrace Apple**.

4. V části **Spravovat nastavení registrace Apple Configuratoru** vyberte **Sériová čísla Apple Configuratoru**.

5. V okně **Sériová čísla Apple Configuratoru** vyberte **Přidat**.

6. V okně **Přidat sériová čísla** vyberte profil, který chcete použít pro sériová čísla při importu. Pokud importujete soubor s novými podrobnostmi, které mají přepsat ty stávající, vyberte Přepište podrobnosti u existujících identifikátorů a nové podrobnosti nahradí stávající.

7. Přejděte k souboru .csv se sériovými čísly a vyberte **Přidat**.

## <a name="assign-a-profile-to-specific-serial-numbers"></a>Přiřazení čísel ke specifickým sériovým číslům

Intune umožňuje přiřadit profily ze dvou různých míst na portálu Azure Portal. Můžete použít následující postup nebo můžete přiřadit profily z okna Registrační profily Apple Configuratoru, což je místo, kde vytvoříte profil (viz téma [Registrace zařízení se systémem iOS pomocí Apple Configuratoru s Průvodcem nastavením](enroll-ios-devices-with-apple-configurator-and-setup-assistant.md). Pomocí následujícího postupu můžete profil přiřadit, jenom pokud jste ho už vytvořili.

1. V okně Intune zvolte **Registrovat zařízení** a pak zvolte **Registrace Apple**.

2. V okně **Sériová čísla Apple Configuratoru** vyberte sériová čísla, ke kterým chcete přiřadit profil, a potom vyberte **Přiřadit profil**.

3. V okně **Přiřadit profil** vyberte profil, který chcete přiřadit, a potom klepněte na **Přiřadit**.

## <a name="delete-serial-numbers"></a>Odstranění sériových čísel
Dříve naimportovaná sériová čísla můžete odstranit. Sériová čísla můžete odstranit jenom v případě, že zařízení nejdřív odregistrujete. Po odebrání sériového čísla není možné používat Apple Configurator prostřednictvím Průvodce nastavením, pokud toto číslo znovu nepřidáte.

## <a name="view-the-state-of-a-device"></a>Zobrazení stavu zařízení
Sériová čísla zařízení můžou mít jeden ze dvou stavů:

- Zaregistrované – zařízení je zaregistrované a připojilo se ke službě Intune.
- Nekontaktované – zařízení se ke službě Intune nikdy nepřipojilo.
- Nevyřízené obnovení – zařízení je zaregistrované, ale byla provedena změna (například se změnilo nastavení registrace nebo použitý profil DEP). Pokud změníte profil DEP zařízení, nepoužijí se změny, dokud zařízení neodregistrujete a znovu nezaregistrujete.

**Zobrazení stavu sériového čísla**

V okně **Sériová čísla Apple Configuratoru** vyberte sériové číslo, jehož stav chcete zobrazit, a podívejte se na informace u položky **Stav**.



<!--HONumber=Feb17_HO1-->


