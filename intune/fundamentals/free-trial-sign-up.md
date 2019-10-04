---
title: Rychlý Start – Vyzkoušejte si Microsoft Intune zdarma
titleSuffix: ''
description: V tomto rychlém startu vytvoříte bezplatné zkušební předplatné, budete rozumět podporovaným konfiguracím a požadavkům na síť a volitelně můžete nakonfigurovat název domény.
keywords: ''
author: Erikre
ms.author: erikre
manager: dougeby
ms.date: 10/02/2019
ms.topic: quickstart
ms.service: microsoft-intune
ms.localizationpriority: high
ms.technology: ''
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.reviewer: ''
ms.suite: ems
search.appverid: MET150
ms.custom: intune-azure
ms.collection: M365-identity-device-management
ms.openlocfilehash: 1f1e19822aaf90761e6429b2e91194eacccf467a
ms.sourcegitcommit: 223d64a72ec85fe222f5bb10639da729368e6d57
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/04/2019
ms.locfileid: "71940509"
---
# <a name="quickstart-try-microsoft-intune-for-free"></a>Rychlý Start: Vyzkoušejte si Microsoft Intune zdarma

Microsoft Intune pomáhá chránit podniková data vaší pracovní síly prostřednictvím správy zařízení a aplikací. V tomto rychlém startu vytvoříte bezplatné předplatné, abyste si mohli vyzkoušet Intune v testovacím prostředí.

Intune poskytuje správu mobilních zařízení (MDM) a správu mobilních aplikací (MAM) ze zabezpečené cloudové služby, která je spravovaná pomocí portál Microsoft Azure. Pomocí Intune zajistíte správnou konfiguraci podnikových prostředků zaměstnanců (data, zařízení a aplikací), které jsou k dispozici, jsou dostupné a aktualizované a vyhovují zásadám dodržování předpisů a požadavkům vaší společnosti.

## <a name="prerequisites"></a>Požadavky
Než nastavíte Microsoft Intune, přečtěte si následující požadavky:

- [Podporované operační systémy a prohlížeče](supported-devices-browsers.md)
- [Požadavky na konfiguraci sítě a šířku pásma](network-bandwidth-use.md)

## <a name="sign-up-for-a-microsoft-intune-free-trial"></a>Registrace Microsoft Intune bezplatné zkušební verze

Vyzkoušení Intune je zdarma po dobu 30 dnů. Pokud už máte svůj pracovní nebo školní účet, **přihlaste** se pomocí tohoto účtu a přidejte Intune k vašemu předplatnému. Jinak se můžete **zaregistrovat** k novému účtu, abyste mohli používat Intune pro vaši organizaci.

> [!IMPORTANT]
> Po registraci nového účtu nemůžete kombinovat stávající pracovní nebo školní účet.

1. Přejít na stránku [Microsoft Intune zkušební verzi](https://go.microsoft.com/fwlink/?linkid=2019088) a vyplňte formulář.

    ![Snímek obrazovky webové stránky pro registraci zkušebního účtu Microsoft Intune](./media/free-trial-sign-up/account-sign-up-site-full-browser.png)

    Pokud je většina vašich IT operací a uživatelů v jiném národním prostředí než vy, můžete vybrat toto národní prostředí v části **země nebo oblast**. Azure používá vaše regionální informace k poskytování správných služeb. Toto nastavení nelze později změnit.

2. Vytvořte účet pomocí názvu společnosti následovaného **příponou. onmicrosoft.com**. 

    ![Snímek obrazovky zkušebního účtu Intune – nový proces přihlašovacích údajů](./media/free-trial-sign-up/account-sign-up-site-user-id.png)

    Pokud má vaše organizace vlastní doménu, kterou chcete použít bez **. onmicrosoft.com**, můžete ji změnit v centru pro správu Microsoft 365 popsané dále v tomto článku.

3. Podívejte se na informace o novém účtu na konci procesu registrace.

    ![Obrázek informací o účtu](./media/free-trial-sign-up/intune-end-of-sign-up-process.png) 

## <a name="sign-in-to-the-azure-portal"></a>Přihlaste se k Azure Portal

1. Otevřete nové okno prohlížeče a do adresního řádku zadejte **https://portal.azure.com** . 
2. Přihlaste se pomocí přihlašovacích údajů, které jste použili v předchozích krocích.

    ![Obrázek přihlašovací stránky Azure Portal](./media/free-trial-sign-up/azure-portal-signin.png)

3. Chcete-li zobrazit Microsoft Intune v Azure Portal, vyberte **všechny služby** z bočního panelu na levé straně stránky.
4. V poli filtru vyhledejte **Microsoft Intune** a vyberte ji.
5. Výběrem **hvězdičky** přidáte Intune do dolní části seznamu oblíbených služeb a otevřete řídicí panel Intune.

Při registraci zkušební verze obdržíte také e-mailovou zprávu, která obsahuje informace o účtu a e-mailovou adresu, kterou jste zadali během procesu registrace. Tento e-mail potvrzuje, že je vaše zkušební verze aktivní.

> [!TIP]
> Při práci s Azure Portal můžete mít lepší výsledky práce s prohlížečem v normálním režimu, nikoli v privátním režimu.

## <a name="set-the-mdm-authority-to-intune"></a>Nastavení autority MDM na Intune

Až se přihlásíte k Azure Portal a vyberete Intune, může se zobrazit oranžová banner s oznámením, že jste ještě nestavili autoritu MDM. Nastavení autority správy mobilních zařízení (MDM) určuje způsob správy zařízení. Aby mohli uživatelé registrovat zařízení pro správu, musí být nastavená Autorita MDM.

Pokud chcete nastavit autoritu MDM na Intune, postupujte podle těchto kroků.

1. Otevřete nové okno prohlížeče a do adresního řádku zadejte **https://portal.azure.com** . 
2. Vyberte **všechny služby** > **Microsoft Intune**.
3. Vyberte banner s oznámením, že jste nepovolili správu zařízení, nebo pokud se banner nezobrazuje hned, vyberte **registrace zařízení**. Pokud jste ještě nepovolili správu zařízení, zobrazí se okno **zvolit autoritu MDM** .

    > [!NOTE]
    > Pokud jste nastavili autoritu MDM, v okně **registrace zařízení** se zobrazí hodnota Autorita MDM. Oranžový banner se zobrazí pouze v případě, že jste ještě nenastavili autoritu MDM. 

    ![Obrázek okna zvolit autoritu MDM](./media/free-trial-sign-up/choose-mdm-authority.png) 

4. Pokud vaše Autorita MDM není nastavená, nastavte v části **zvolit autoritu MDM**autoritu MDM na **autoritu MDM pro Intune**.

Další informace o autoritě MDM najdete v tématu [Nastavení autority pro správu mobilních zařízení](mdm-authority-set.md).

## <a name="configure-your-custom-domain-name-optional"></a>Konfigurace vlastního názvu domény (volitelné)

Jak je uvedeno výše, pokud má vaše organizace vlastní doménu, kterou chcete použít bez **. onmicrosoft.com**, můžete ji změnit v centru pro správu Microsoft 365. Pomocí následujících kroků můžete přidat, ověřit a nakonfigurovat vlastní název domény.  

> [!IMPORTANT]
> Nelze přejmenovat ani odebrat *úvodní* část názvu domény **onmicrosoft.com** . Můžete ale přidat, ověřit nebo odebrat *vlastní* názvy domén používané v Intune, abyste zachovali, že vaše obchodní identita bude jasná. Další informace najdete v tématu [Konfigurace vlastního názvu domény](custom-domain-name-configure.md).

1. Přejít na [Centrum pro správu Microsoft 365](https://admin.microsoft.com) a přihlaste se pomocí účtu správce.

2. V navigačním podokně vyberte **nastavení** > **domény** > **Přidat doménu**.

3. Zadejte vlastní název domény. Pak vyberte **Další**.

   ![Snímek obrazovky centra pro správu Microsoft 365 – přidat doménu](./media/free-trial-sign-up/domain-custom-add.png)

4. Ověřte, že jste vlastníkem domény, kterou jste zadali v předchozím kroku. 
    
    Když vyberete **Odeslat kód e-mailem** , pošle se na registrovaný kontakt vaší domény e-mail. Po přijetí e-mailu zkopírujte kód a zadejte ho do pole s popiskem **sem zadejte svůj ověřovací kód**. Pokud se ověřovací kód shoduje, doména se přidá do vašeho tenanta. Zobrazený e-mail nemusí vypadat dobře. Některé registrátory skrývají reálnou e-mailovou adresu. I tato e-mailová adresa může být odlišná, a to, co se zadalo při registraci domény.

   ![Snímek obrazovky centra pro správu Microsoft 365 – ověření domény](./media/free-trial-sign-up/domain-custom-verify.png)

   > [!NOTE]
   > Podrobnosti o ověření záznamu TXT najdete v tématu [Vytvoření záznamů DNS u libovolného poskytovatele hostingu DNS pro Office 365](https://support.office.com/article/Create-DNS-records-at-any-DNS-hosting-provider-for-Office-365-7B7B075D-79F9-4E37-8A9E-FB60C1D95166).

## <a name="admin-experiences"></a>Prostředí pro správu

Můžete použít dva Portály:
- Řídicí panel Intune v Azure ([Portal.Azure.com](https://portal.azure.com)) je místo, kde můžete prozkoumat [Možnosti Intune](what-is-intune.md). Normálně budete pracovat na řídicím panelu Intune.
- Centrum pro správu Microsoft 365 ([admin.Microsoft.com](https://admin.microsoft.com)) je místo, kde můžete přidávat a spravovat uživatele, pokud pro tuto možnost nepoužíváte Azure Active Directory. Můžete také spravovat další aspekty svého účtu, včetně fakturace a podpory.

## <a name="next-steps"></a>Další kroky

V tomto rychlém startu jste vytvořili bezplatné předplatné, abyste si mohli vyzkoušet Intune v testovacím prostředí. Další informace o nastavení Intune najdete v tématu [Nastavení Intune](setup-steps.md).

Pokud chcete postupovat podle této série rychlých startů Intune, přejděte k dalšímu rychlému startu.

> [!div class="nextstepaction"]
> [Rychlý Start: vytvoření uživatele a přiřazení licence k němu](quickstart-create-user.md)
