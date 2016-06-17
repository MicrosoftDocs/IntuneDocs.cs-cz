---
# required metadata

title: Řešení konfliktů GPO a zásad Intune | Microsoft Intune
description:
keywords:
author: robstackmsft
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: e76af5b7-e933-442c-a9d3-3b42c5f5868b

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Řešení konfliktů objektů zásad skupiny (GPO) a zásad Microsoft Intune
Intune používá zásady, které vám pomůžou spravovat nastavení na počítačích, které spravujete. Pomocí zásad můžete třeba na počítačích řídit nastavení pro bránu Windows Firewall. Hodně nastavení služby Intune se podobá nastavením, která nejspíš konfigurujete pomocí zásad skupiny Windows. Někdy se ale může stát, že se tyto dvě metody dostanou vzájemně do konfliktu.

V případě konfliktu mají před zásadami Intune přednost zásady skupiny na úrovni domény mimo případů, kdy se počítač nemůže přihlásit do domény. V takovém případě se použijí na klientském počítači zásady Intune.

## Co je potřeba udělat, když používáte zásady skupiny
Zkontrolujte, že žádné zásady, které používáte, nejsou spravované zásadami skupiny. Abyste líp zabránili konfliktům, můžete využít některé z těchto metod:

-   Před instalací klienta Intune přesuňte počítače do organizační jednotky služby Active Directory, u které se nepoužívá nastavení zásad skupiny. V organizačních jednotkách obsahujících počítače zaregistrované v Intune, u kterých nechcete používat nastavení zásad skupiny, můžete taky zablokovat dědičnost zásad skupiny.

-   Pomocí filtru rozhraní WMI nebo filtru zabezpečení omezte objekty GPO jenom na počítače, které nespravuje Intune. Příklady a další informace o tom, jak to udělat, najdete v části [Jak filtrovat stávající objekty zásad skupiny, aby nedocházelo ke konfliktům se zásadami Microsoft Intune](resolve-gpo-and-microsoft-intune-policy-conflicts.md#BKMK_Filter).

-   Zakažte nebo odeberte objekty zásad skupiny, které jsou v konfliktu se zásadami Intune.

Další informace o službě Active Directory a zásadách skupiny Windows najdete v dokumentaci k Windows Serveru.

## Jak filtrovat stávající objekty GPO, aby nedocházelo ke konfliktům se zásadami Intune
Pokud jste našli objekty GPO s nastavením, které je v konfliktu s nastavením zásad Intune, můžete použít některou z následujících metod filtrování a omezit tak tyto objekty zásad skupiny jenom na počítače, které nespravuje Intune.

### Použití filtrů rozhraní WMI
Filtry rozhraní WMI selektivně používají objekty zásad skupiny jenom u počítačů, které splňují podmínky dotazu. Pokud chcete použít filtr rozhraní WMI, nasaďte před registrací počítačů ve službě Intune na všechny počítače v podnikové síti instanci třídy služby WMI.

#### Použití filtrů rozhraní WMI u objektu zásad skupiny

1.  Vytvořte soubor objektu správy, a to tak, že zkopírujete následující text, vložíte ho do textového souboru a ten uložíte pod názvem **WIT.mof** na vhodné místo. Tento soubor obsahuje instanci třídy služby WMI a tu můžete nasadit na počítače, které chcete zaregistrovat ve službě Intune.

    ```
    //Beginning of MOF file.
    #pragma classflags("forceupdate")
    #pragma namespace ("\\\\.\\Root")
    instance of __Namespace
    {
       Name = "WindowsIntune";
    };

    #pragma namespace ("\\\\.\\Root\\WindowsIntune")
    [
       Description("This class defines Microsoft Intune common properties")
    ]
    class WindowsIntune_ManagedNode
    {
       [ read, Description("This defines whether Microsoft Intune Policy is enabled"): DisableOverride ToSubClass ]
       boolean WindowsIntunePolicyEnabled;
       [ read, key, Description("This property defines the version." "Example: 1.0"): ToSubClass ]
       string Version;
    };

    instance of WindowsIntune_ManagedNode
    {
       Version = "1.0";
       WindowsIntunePolicyEnabled = 1;
    };
    ```

2.  Použijte spouštěcí skript nebo zásady skupiny a tento soubor nasaďte. Dole je příkaz pro nasazení v případě spouštěcího skriptu. Instanci třídy služby WMI je potřeba nasadit před registrací klientských počítačů ve službě Intune.

    **C:/Windows/System32/Wbem/MOFCOMP &lt;cesta k souboru MOF&gt;\wit.mof**

3.  Spusťte některý z následujících příkazů pro vytvoření filtrů rozhraní WMI, a to podle toho, jestli je objekt zásad skupiny, který chcete filtrovat, použitý u počítačů spravovaných pomocí Intune nebo u počítačů, které pomocí Intune spravované nejsou.

    -   U objektů zásad skupiny použitých u počítačů, které nejsou spravované pomocí Intune, použijte tento příkaz:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=0
        ```

    -   U objektů zásad skupiny použitých u počítačů, které jsou spravované pomocí Intune, použijte tento příkaz:

        ```
        Namespace:root\WindowsIntune
        Query:  SELECT WindowsIntunePolicyEnabled FROM WindowsIntune_ManagedNode WHERE WindowsIntunePolicyEnabled=1
        ```

4.  Upravte objekt zásad skupiny v konzole pro správu zásad skupiny tak, aby používal filtr rozhraní WMI, který jste vytvořili v předchozím kroku.

    -   U objektů zásad skupiny, které by se měly používat jenom u počítačů, které chcete spravovat pomocí Intune, použijte filtr **WindowsIntunePolicyEnabled=1**..

    -   U objektů zásad skupiny, které by se měly používat jenom u počítačů, které nechcete spravovat pomocí Intune, použijte filtr **WindowsIntunePolicyEnabled=0**..

Další informace o tom, jak používat filtry rozhraní WMI v zásadách skupiny, najdete v blogovém příspěvku [Filtrování zabezpečení, filtrování WMI a cílení na úrovni položek v předvolbách zásad skupiny](http://go.microsoft.com/fwlink/?LinkId=177883)..

### Použití filtrů skupin zabezpečení
Zásady skupiny umožňují používat objekty zásad skupiny jenom u skupin zabezpečení, které jsou pro vybraný objekt zásad skupiny zadané v oblasti **Filtrování zabezpečení** konzoly pro správu zásad skupiny. Objekty zásad skupiny se ve výchozím nastavení používají u skupiny **Authenticated Users**..

-   V modulu snap-in **Uživatelé a počítače služby Active Directory** vytvořte novou skupinu zabezpečení obsahující účty počítačů a uživatelské účty, které nechcete spravovat pomocí Intune. Vaše skupina by třeba mohla mít název **Nespravovat v Microsoft Intune**..

-   V konzole pro správu zásad skupiny klikněte na kartě **Delegování** pro vybraný objekt zásad skupiny pravým tlačítkem na novou skupinu zabezpečení a udělte uživatelům i počítačům v této skupině zabezpečení příslušná oprávnění **Číst** a **Používat zásady skupiny**. (Oprávnění**Používat zásady skupiny** jsou dostupná v dialogovém okně **Upřesnit** .)

-   Pak u vybraného objektu zásad skupiny použijte nový filtr skupin zabezpečení a odeberte výchozí filtr **Authenticated Users** .

S novou skupinou zabezpečení se musí ve změnách služby Intune nakládat jako s registrací.

### Související témata
[Správa počítačů s Windows pomocí Intune](manage-windows-pcs-with-microsoft-intune.md)


<!--HONumber=May16_HO1-->


