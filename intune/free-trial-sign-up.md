---
title: "Registrace bezplatné 30denní zkušební verze"
titleSuffix: Intune Azure preview
description: "Intune Azure Preview: Registrace k Intune na platformě Azure"
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 01/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 195931c0-8208-43bd-b0af-b1f8e469a32c
ms.suite: ems
ms.custom: intune-azure
ms.translationtype: Human Translation
ms.sourcegitcommit: 9ff1adae93fe6873f5551cf58b1a2e89638dee85
ms.openlocfilehash: 3be43e12abc1cf90da3584450ddd56ab63bdfac1
ms.contentlocale: cs-cz
ms.lasthandoff: 05/23/2017


---

# <a name="sign-up-for-a-microsoft-intune-free-trial-for-the-azure-portal-preview"></a>Registrace bezplatné zkušební verze Microsoft Intune na platformě Azure Portal Preview

[!INCLUDE[azure_preview](./includes/azure_preview.md)]

Tento článek vás provede registrací bezplatné zkušební verze samostatné služby Intune na platformě Azure Portal Preview. <!---and prepares your trial with some users so that you can then follow the associated evaluation guide to see how Intune manages mobile devices. ---> <!---or app data when devices are not enrolled in Intune.--->

<!--- ## Assumptions
This sign-up article and the evaluation guide assume you are using the trial for evaluation purposes only and intend to start with a clean environment when you subscribe.

To make it easy for you to get started with the trial, we are setting up a very simple environment that uses only Intune and assumes it will be your sole method of managing devices (known as the mobile device management authority). However, throughout the guide we will point you to deeper technical content if you want to explore farther.

You can do everything in the trial version that you can do in a subscription version; the only difference is you are limited to 100 user accounts in the trial.--->

<!--- ## Sign up for your trial--->
1. Přejděte na stránku [registrace Intune](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) a vyplňte formulář pro registraci zkušebního předplatného.

 <!--- If you have a work or school account and want to use that for your Intune trial, follow [these sign-in instructions](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-1) instead. However, this article assumes that you are not using such an account.---><br/> ![Obrázek registrační stránky](./media/1-clicking-try.png)

 > [!TIP]
> Pokud se většina pracovníků IT oddělení a uživatelů nachází v jiném národním prostředí než vy, můžete toto národní prostředí vybrat v části **Umístění vaší společnosti**.

2. Na konci procesu registrace dostanete zprávu s informacemi o novém účtu. <br/> ![Obrázek s informacemi o účtu](./media/2-end-of-sign-up-process.png) <br/>Pokud v tuto chvíli kliknete na **Můžete začít**, přejdete do Centra pro správu Office 365, kde můžete přidat uživatele, abyste mohli otestovat prostředí. <br/><br/>Pokud ale chcete přejít přímo na Intune Azure Portal Preview, otevřete v prohlížeči nové okno a do adresního řádku zadejte **https://portal.azure.com**. Přejdete na přihlašovací stránku Azure, kde se můžete přihlásit pomocí přidělených přihlašovacích údajů. Tuto adresu použijte vždy, když se budete chtít přihlásit ke zkušební verzi služby Intune. <br/> ![Obrázek přihlašovací stránky Azure Portal](./media/azure-portal-signin.png)

Při prvním přihlášení k Intune v Azure Preview je možné, že se tato služba na řídicím panelu Azure nezobrazí. Přidání služby Intune na řídicí panel Azure:
1. V seznamu služeb Azure nalevo od řídicího panelu zvolte **Další služby >** a do vyhledávacího pole zadejte **Intune**.
2. V seznamu zvolte **Intune** a vyberte hvězdičku, aby se tato služba přidala do seznamu služeb.<br/> ![Obrázek s výběrem Intune v seznamu služeb](./media/azure-add-intune1.png)
3. Potom výběrem **Intune** v seznamu služeb otevřete řídicí panel Intune.

Když se zaregistrujete ke zkušební verzi, přijde vám na e-mailovou adresu, kterou jste zadali při registraci, také e-mailová zpráva s informacemi o vašem účtu. Ta potvrzuje, že je vaše zkušební verze aktivní.


<!--- ## Add users
Before you leave the Office 365 Admin center for Intune, you need to add some users to your trial account.

In the Office 365 Admin center, you can add users individually or in bulk by uploading a .csv file. We will do both to set up your trial. However, in your production environment, you will probably want to take advantage of your Azure Active Directory user accounts, which you can learn more about in our [Getting Started guide](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-3) and in the [Next steps](#Next-steps) section of this article.

### Add an individual user
1. Choose either of the options to add a use to open a form that allows you to create a user. Only the items starred with an asterisk (\*) are required.
![Image of add user button options](./media/sign-up/add-user.png)


2.  When you add the user, the final step will be to send the user an email with their temporary Intune password. For the purposes of this evaluation, use your own work email address so you will receive the log-on information and see the email your users will get. You can then use these user identities to enroll test devices.<br/>

 ![Image of add user final step](./media/sign-up/new-user-2.png)

3. If you want to assign a user an admin role after you create it, you can edit the role in the Office 365 Admin center by selecting the user name from your list of users, and then choosing **Edit** in the Role line to see the list of user roles you can select from and assign to that user.

 ![Image of user  role options](./media/sign-up/change-user-role.png)

### Import multiple users
1. You will find the wizard for importing multiple users in the **More** list.

 ![Image of option to add multiple users](./media/sign-up/add-multiple-users.png)

2. To help you set up your .csv file correctly, you can download a template file to populate with your user data. Download the .csv file that contains headers and sample user information to see exactly the kind of data is needed for each field.

 ![Image of first step in bulk enrollment wizard](./media/sign-up/bulk-enroll-step-1.png)


3. After you’ve created and saved your .csv file, choose **Browse** to select the file. Verify, and choose **Next**. Your users will be uploaded and added to your list of active users.

> [!NOTE]
> Your users won't show up in Intune until they've enrolled a device to be managed.

Now it’s time to head over to Intune to start managing your users, their devices, and their apps.--->

## <a name="keeping-the-admin-experiences-straight"></a>Přehled prostředí pro správu
<!---### Classic Intune
There are two portals you will use for classic Intune:
- The Office 365 Admin center ([portal.office.com](https://portal.office.com))
- The Intune administration console ([manage.microsoft.com](https://manage.microsoft.com))

Normally, you’ll do your work in the Intune administration console, shown below. This is the site where you set up and manage your groups, policies, devices, and apps.

![Image of Intune administration console](./media/sign-up/intune-admin-console.png)

However, you will use the Office 365 Admin center, shown below, to add and manage your users and other aspects of your account, including billing and support.

![Image of Office 365 Admin center](./media/sign-up/office-admin-center.png)

You can navigate from the Office 365 Admin center to the Intune admin console. The admin centers are under the last item in the left navigation pane. Choose **Intune** to open the Intune admin console in a new tab.

![Image of link to Intune administration console](./media/sign-up/link-to-intune.png)

To get from Intune back to the Office 365 Admin center, choose the **Add Users** task on the Groups Overview page.

![Image of link back to Office 365  Admin center](./media/sign-up/task-add-users.png)--->

<!---### Intune Azure preview--->
Pro Intune Azure Preview budete používat tři portály:
- Řídicí panel Intune na portálu Azure ([portal.azure.com](https://portal.azure.com)), kde můžete prozkoumat [možnosti Intune na webu Azure Portal](what-is-intune.md).
- Centrum pro správu Office 365 ([portal.office.com](https://portal.office.com)), kde můžete přidat a spravovat uživatele, pokud za tímto účelem nepoužíváte Azure Active Directory. Můžete také spravovat další oblasti svého účtu, včetně fakturace a podpory.
- Konzola pro správu Intune Classic ([manage.microsoft.com](https://manage.microsoft.com)), kde můžete prozkoumat funkce, které ještě nejsou přidané do Azure.

Obvykle budete používat řídicí panel Intune, který je na obrázku níže. To je web, na kterém se nastavují a spravují skupiny, zásady, zařízení a aplikace.

Z řídicího panelu můžete přejít do konzoly pro správu Intune Classic výběrem dlaždice **Otevřít portál Classic služby Intune**.

Pokud se chcete vrátit k Intune Azure Preview, zadejte na adresní řádek v prohlížeči https://portal.azure.com a pak v seznamu služeb znovu zvolte **Intune**.

 ![Obrázek řídicího panelu Intune](./media/intune-azure-dashboard.png)


Přidávat a spravovat uživatele a pracovat s dalšími aspekty vašeho účtu včetně fakturace a podpory ale budete pomocí Centra pro správu Office 365, které vidíte dole.

![Obrázek Centra pro správu Office 365](./media/office-admin-center.png)

K přechodu z Centra pro správu Office 365 na řídicí panel Intune zadejte na adresní řádek v prohlížeči https://portal.azure.com. V seznamu služeb zvolte **Intune**.

K návratu z Intune zpět do Centra pro správu Office 365 zadejte na adresní řádek v prohlížeči https://portal.office.com. Pokud jste už přihlášení do Intune, přejdete přímo do Centra pro správu Office 365.

## <a name="next-steps"></a>Další kroky

### <a name="intune-azure-preview"></a>Intune Azure preview
Přečtěte si další informace o [Intune v Azure Portal Preview](what-is-intune.md).
### <a name="classic-intune"></a>Classic Intune
Scénář hodnocení: [Hodnocení správy mobilních zařízení v Microsoft Intune](https://docs.microsoft.com/intune-classic/understand-explore/mobile-device-management-trial-guide-microsoft-intune)

### <a name="integration-with-other-products"></a>Integrace s dalšími produkty
Přečtěte si další informace o používání uživatelských účtů služby Azure Active Directory v Intune:
- [Požadavky na identity](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)
- [Požadavky na synchronizaci adresáře](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)
- [Požadavky na vícefaktorové ověřování](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

Přečtěte si další informace o používání [Intune s nástrojem System Center Configuration Manager.](https://docs.microsoft.com/sccm/mdm/understand/hybrid-mobile-device-management)

