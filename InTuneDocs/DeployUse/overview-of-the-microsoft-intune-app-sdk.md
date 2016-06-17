---
# required metadata

title: Přehled sady Microsoft Intune App SDK | Microsoft Intune
description:
keywords:
author: Msmbaldwin
manager: jeffgilb
ms.date: 04/28/2016
ms.topic: article
ms.prod:
ms.service: microsoft-intune
ms.technology:
ms.assetid: ef1751bb-3a2f-4662-a922-38c076869eb3

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: jeffgilb
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Přehled Microsoft Intune App SDK
Sada Intune App SDK je dostupná pro platformy iOS i Android a umožňuje funkce správy mobilních aplikací s Microsoft Intune. Navíc se snažíme snížit objem změn kódu, které se od vývojářů vyžadují. Zjistíte, že většinu funkcí sady SDK můžete povolit bez změny chování vaší aplikace.  Pro zlepšení činnosti koncových uživatelů a správců IT můžete využít rozhraní API k přizpůsobení chování vaší aplikace pro funkce, které vyžadují zapojení vaší aplikace. 

Po povolení aplikace můžou správci IT nasadit zásady pro aplikace spravované v Intune a využít těchto funkcí k ochraně podnikových dat.

# Funkce:
## Ovládání možnosti uživatele přesouvat podnikové dokumenty
Správci IT můžou řídit relokaci souborů podnikových dokumentů v aplikacích spravovaných v Intune. Můžou třeba nasadit zásadu, která zakazuje aplikacím pro zálohování souborů zálohovat podniková data do cloudu.  

## Konfigurace omezení schránky
Správci IT můžou konfigurovat chování schránky v aplikacích spravovaných v Intune. Můžou třeba nasadit zásadu, která koncovým uživatelům znemožní používat schránku pro vyjmutí/kopírování z aplikace spravované v Intune a vložit obsah do nespravované aplikace.

## Konfigurace omezení snímků obrazovky
Správci IT můžou zabránit uživatelům, aby pořizovali snímky obrazovky, když se zobrazuje aplikace spravovaná v Intune. Použití tohoto omezení zabrání zachycení a zveřejnění důvěrného podnikového obsahu. Tato funkce je dostupná jenom pro zařízení se systémem Android. 

## Vynucení šifrování uložených dat
Správci IT můžou vynutit zásadu, která zajišťuje, aby data ukládaná aplikací do zařízení šifrovala.

## Vzdálené vymazání podnikových dat
Správci IT můžou vzdáleně vymazat podniková data z aplikace spravované v Intune, když se zruší registrace zařízení v Intune. Tato funkce je založená na identitě a odstraní jenom soubory, které se vztahují k podnikové identitě koncového uživatele. Kvůli tomu funkce vyžaduje zapojení aplikace. Aplikace může určit identitu, u které má dojít k vymazání, na základě uživatelského nastavení. Když uvedená uživatelská nastavení v aplikaci chybí, výchozí chování je vymazat adresář aplikace a upozornit koncového uživatele, že došlo k odebrání přístupu k prostředkům společnosti. 

## Vynucení používání spravovaného prohlížeče
Správci IT můžou vynutit používání spravovaného prohlížeče při otevírání odkazů z aplikací spravovaných v Intune. Používání prohlížeče spravovaného v Microsoft Intune pomáhá zaručit, aby se odkazy v e-mailech (v e-mailovém klientovi spravovaném v Intune)  udržely v rámci domény aplikací spravovaných v Intune.

## Vynucení zásady kódu PIN
Správci IT můžou vynutit zásadu kódu PIN při spuštění aplikace spravované v Intune. Tato zásada pomáhá zkontrolovat, jestli jsou koncoví uživatelé, kteří zaregistrovali svá zařízení do Microsoft Intune, totožné s osobami, které teď aplikace spouštějí. Když koncoví uživatelé nakonfigurují kód PIN, sada Intune App SDK použije Azure Active Directory k ověření přihlašovacích údajů koncového uživatele s přihlašovacími údaji registrace zařízení. 

## Vyžádání přihlašovacích údajů před spuštěním aplikací
Správci IT můžou vyžadovat, aby uživatelé před spuštěním aplikací spravovaných v Intune zadali přihlašovací údaje. Sada Intune App SDK použije Azure Active Directory k jednotnému přihlášení, při kterém se jednou zadané přihlašovací údaje znovu použijí pro další přihlášení. Také podporujeme ověřování řešení správy identity [sdružených se službou Azure Active Directory](https://msdn.microsoft.com/en-us/library/azure/jj679342.aspx).. 

## Kontrola stavu zařízení a dodržování předpisů
Správci IT můžou před přístupem koncových uživatelů k aplikacím spravovaným v Intune kontrolovat stav zařízení a dodržování podnikových zásad. Na platformě iOS tato zásada kontroluje, jestli zařízení nemá jailbreak. Na platformě Android tato zásada kontroluje, jestli zařízení nemá root.  




<!--HONumber=May16_HO1-->


