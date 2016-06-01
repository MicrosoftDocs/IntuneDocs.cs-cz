---
# required metadata

title: Použití vzdáleného vymazání pro lepší ochranu dat | Microsoft Intune
description:
keywords:
author: NathBarn
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: 8519e411-3d48-44eb-9b41-3e4fd6a93112

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Lepší ochrana dat s využitím plného nebo selektivního vymazání pomocí Microsoft Intune
Stejně jako u zařízení se v určitém okamžiku stane, že potřebujete nebo chcete [vyřadit aplikace](retire-apps-using-microsoft-intune.md), které jste nasadili do počítačů a zařízení, protože už nejsou potřeba. Může být taky potřeba odebrat ze zařízení firemní data. K tomuto účelu Intune poskytuje možnosti selektivního a úplného vymazání. Protože mobilní zařízení můžou ukládat citlivá firemní data a poskytovat přístup ke spoustě firemních prostředků, můžete z rozhraní Intune odeslat příkaz pro vzdálené vymazání zařízení a ztracené nebo odcizené zařízení vymazat. Příkaz pro vzdálené vymazání zařízení můžou taky zadat uživatelé z Intune na soukromých zařízeních, která jsou v Intune zaregistrovaná.

  > [!NOTE]
  > Toto téma se věnuje jenom vymazání zařízení spravovaných přes Intune. K [vymazání firemních dat z aplikace](wipe-managed-company-app-data-with-microsoft-intune.md) můžete taky použít [portál Azure Preview](https://portal.azure.com).

## Úplné vymazání


**Úplné vymazání** na zařízení obnoví výchozí nastavení od výrobce a odebere všechna firemní a uživatelská data a nastavení. Zařízení se odebere ze služby Intune. Plné vymazání je užitečné k tomu, aby se zařízení resetovalo, než se předá novému uživateli, a v případech, kdy došlo ke ztrátě nebo odcizení zařízení.  Volbu úplného vymazání používejte velmi opatrně.

## Data v zařízení nejde obnovit.

Selektivní vymazání **Selektivní vymazání** odebere ze zařízení firemní data, včetně případných dat správy mobilních aplikací (MAM), nastavení a e-mailových profilů. Při selektivním vymazání se osobní údaje uživatele na zařízení ponechají. Zařízení se odebere ze služby Intune.

**Následující tabulka pro jednotlivé platformy popisuje, jaká data se odeberou, a vliv na data, která v zařízení po selektivním vymazání zůstanou.**

|iOS|Datový typ|
|-------------|-------|
|iOS|Firemní aplikace a související data nainstalovaná službou Intune Odinstalují se aplikace.<br /><br />Odeberou se data firemních aplikací. Odeberou se data aplikací z aplikací Microsoftu, které používají správu mobilních aplikací.|
|Aplikace se neodebere.|Nastavení|
|Konfigurace, které byly nastavené zásadami Intune, už nebudou vynucené a uživatelé můžou nastavení změnit.|Nastavení profilu sítě Wi-Fi a VPN|
|Odebrané|Nastavení profilu certifikátu|
|Certifikáty se odeberou a zruší.|Agent pro správu|
|Profil pro správu se odebere.|E-mailu|
|E-mailové profily, které jsou zřízené prostřednictvím Intune, se odeberou a e-maily v mezipaměti zařízení se odstraní.|Zrušení služby Azure Active Directory (AAD)|
|Záznam AAD se odebere | Kontakty  Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou. <br /> <br />Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat.

**V současné době se podporuje jen aplikace Outlook.**

|Android|Datový typ|Android|
|-------------|-----------|------------------------|
|Android Samsung KNOX|Webové odkazy|Odebrány.|
|Odebrané|Nespravované aplikace Google Play|Aplikace a data zůstanou nainstalované.|
|Aplikace a data zůstanou nainstalované.|Nespravované obchodní aplikace|Aplikace a data zůstanou nainstalované. Aplikace se odinstalují a následkem toho se odeberou data, která jsou pro tuto aplikaci místní.|
|Neodeberou se žádná data mimo aplikaci (karta SD atd.).|Spravované aplikace Google Play Odeberou se data aplikací. Aplikace se neodebere.|Data chráněná šifrováním MAM mimo aplikaci (karta SD atd.) zůstávají šifrovaná, ale neodeberou se. Odeberou se data aplikací. Aplikace se neodebere.|
|Data chráněná šifrováním MAM mimo aplikaci (karta SD atd.) zůstávají šifrovaná, ale neodeberou se.|Spravované obchodní aplikace Odeberou se data aplikací. Aplikace se neodebere.|Data chráněná šifrováním MAM mimo aplikaci (karta SD atd.) zůstávají šifrovaná, ale neodeberou se. Odeberou se data aplikací. Aplikace se neodebere.|
|Data chráněná šifrováním MAM mimo aplikaci (karta SD atd.) zůstávají šifrovaná, ale neodeberou se.|Nastavení|Konfigurace, které byly nastavené zásadami Intune, už nebudou vynucené a uživatelé můžou nastavení změnit.|
|Konfigurace, které byly nastavené zásadami Intune, už nebudou vynucené a uživatelé můžou nastavení změnit.|Nastavení profilu sítě Wi-Fi a VPN|Odebrané|
|Odebrané|Nastavení profilu certifikátu|Certifikáty se zruší, ale neodeberou.|
|Certifikáty se odeberou a zruší.|Agent pro správu|Zruší se oprávnění správce zařízení.|
|Zruší se oprávnění správce zařízení.|E-mailu|E-maily přijaté aplikací Microsoft Outlook pro Android se odeberou.|
|E-mailové profily, které jsou zřízené prostřednictvím Intune, se odeberou a e-maily v mezipaměti zařízení se odstraní.|Zrušení služby Azure Active Directory (AAD)|Záznam AAD se odebere|
|Záznam AAD se odebere | Kontakty  Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou. <br /> <br />Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat.|V současné době se podporuje jen aplikace Outlook.  Kontakty synchronizované přímo z aplikace do nativního adresáře se odeberou. <br /> <br />Kontakty synchronizované z nativního adresáře do dalšího externího zdroje není možné vymazat.

**V současné době se podporuje jen aplikace Outlook.**

|Windows|Datový typ|Windows 8.1 (MDM) a Windows RT 8.1|Windows RT|Windows Phone 8 a Windows Phone 8.1|
|-------------|----------------------------------------------------------------|--------------|-----------------------------------------|--------|
|Windows 10|Firemní aplikace a související data nainstalovaná službou Intune|U souborů chráněných systémem souborů EFS dojde ke zrušení klíče a uživatel nebude moct soubory otevírat.|Neodebere firemní aplikace. Odinstalují se aplikace původně nainstalované prostřednictvím firemního portálu.|Odeberou se data firemních aplikací.|
|Aplikace jsou odinstalovány a jsou odebrány klíče zkušebního načtení.|Nastavení|Konfigurace, které byly nastavené zásadami Intune, už nebudou vynucené a uživatelé můžou nastavení změnit.|Konfigurace, které byly nastavené zásadami Intune, už nebudou vynucené a uživatelé můžou nastavení změnit.|Konfigurace, které byly nastavené zásadami Intune, už nebudou vynucené a uživatelé můžou nastavení změnit.|
|Konfigurace, které byly nastavené zásadami Intune, už nebudou vynucené a uživatelé můžou nastavení změnit.|Nastavení profilu sítě Wi-Fi a VPN|Odebrané|Odebrané|Není podporované|
|Odebrané|Nastavení profilu certifikátu|Certifikáty se odeberou a zruší.|Certifikáty se odeberou a zruší.|Není podporované|
|Certifikáty se odeberou a zruší.|E-mailu|Odebere e-mail s povoleným systémem souborů EFS, což zahrnuje e-maily a přílohy aplikace Pošta pro Windows.|Není podporované|E-mailové profily, které jsou zřízené prostřednictvím Intune, se odeberou a e-maily v mezipaměti zařízení se odstraní. Odebere e-mail s povoleným systémem souborů EFS, což zahrnuje e-maily a přílohy aplikace Pošta pro Windows.|
|Odebere e-mailové účty, které byly zřízené Intune.|Zrušení služby Azure Active Directory (AAD)|Ne|Ne|Záznam AAD se odebere Nelze použít.|

### Windows 10 nepodporuje selektivní vymazání pro zařízení připojená k Azure Active Directory.

1.  Vzdálené vymazání zařízení z konzoly správce Intune Vyberte zařízení, která se mají vymazat.

    -   **Můžete je vyhledat podle uživatele nebo podle zařízení.**

        1.  Podle uživatele:

        2.  V [konzole správce Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všichni uživatelé**. Zvolte jméno uživatele, pro kterého chcete vymazat mobilní zařízení.

        3.  Vyberte **Zobrazit vlastnosti**. Na stránce **Vlastnosti** tohoto uživatele zvolte **Zařízení** a pak klikněte na název mobilního zařízení, které chcete vymazat.

    -   **Když chcete vybrat víc zařízení, klikejte na ně se stisknutou klávesou Ctrl.**

        1.  Podle zařízení:

      ![V [konzole správce Intune](https://manage.microsoft.com/) zvolte **Skupiny** &gt; **Všechna mobilní zařízení**.](../media/dev-sa-wipe.png)

        2.  Zahájení operace vymazání nebo vyřazení Zvolte **Zařízení** a pak vyberte název mobilního zařízení, které chcete vymazat.

2.  Když chcete vybrat víc zařízení, klikejte na ně se stisknutou klávesou Ctrl.

3.  Zvolte **Vyřadit z provozu či vymazat**.

    -   Zobrazí se zpráva s požadavkem, abyste potvrdili, jestli chcete zařízení vyřadit z provozu.

    -   Pokud chcete provést **Selektivní vymazání**, které odebere jenom firemní aplikace a data, zvolte **Ano**. Pokud chcete provést **Úplné vymazání**, který vymaže všechny aplikace a data a vrátí zařízení do výchozího nastavení z výroby, vyberte **Před vyřazením z provozu zařízení vymazat**. Tato akce se vztahuje na všechny platformy kromě Windows 8.1.

Data odebraná pomocí úplného vymazání nejde obnovit.

## Vymazání všech typů zařízení trvá méně než 15 minut.
Vymazání obsahu s povoleným šifrováním systému souborů EFS (Encryption File System) Selektivní vymazání obsahu zašifrovaného systémem souborů EFS podporuje Windows 8.1 a Windows RT 8.1.

-   Pro selektivní vymazání obsahu s povoleným systémem souborů EFS platí následující: Selektivně se vymažou jenom aplikace a data, která jsou chráněná systémem souborů EFS ve stejné internetové doméně jako účet Intune.

-   Další informace najdete v tématu [Selektivní vymazání ve Windows pro správu dat na zařízeních](http://technet.microsoft.com/library/dn486874.aspx).

-   Pokud u domény přidružené k systému souborů EFS dojde ke změnám, může trvat až 48 hodin, než se aplikace a data využívající tuto novou doménu selektivně vymažou.

Vymažou se všechny domény, které je zaregistrované ve službě Intune.

-   Mezi data a aplikace, u kterých se aktuálně podporuje selektivní vymazání systému souborů EFS, patří:

-   Aplikace Pošta pro Windows

-   Pracovní složky Soubory a složky zašifrované systémem souborů EFS.

-   Další informace najdete v tématu [Osvědčené postupy pro systém souborů EFS](http://support.microsoft.com/kb/223316).  Pokud vaše organizace udržuje svou identitu ve službě Active Directory, musí používat nástroj synchronizace adresářů (DirSync) k synchronizaci informací do AAD, aby selektivní vymazání pro systém souborů EFS fungovalo správně.

## Další informace o nástroji DirSync najdete v tématu [Scénář synchronizace adresářů](http://technet.microsoft.com/library/dn441212.aspx) v dokumentaci služby Azure Active Directory.
Sledování akcí vyřazení z provozu, vymazání a odstranění

1.  Pokud chcete získat sestavu zařízení, která se vyřadila z provozu, vymazala nebo odstranila a taky to, kdo tuto operaci provedl:

2.  V[konzole správce Intune](https://manage.microsoft.com/) zvolte **Sestavy** &gt; **Sestavy historie zařízení**.


### Zadejte počáteční a koncové datum pro sestavu a pak zvolte **Zobrazit sestavu**.
[Související témata](retire-devices-from-microsoft-intune-management.md)

[Vyřazení zařízení](http://technet.microsoft.com/library/dn486874.aspx)


<!--HONumber=May16_HO2-->


