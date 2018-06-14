# MetaTXT

#### Copyright (c) 2012, Kis János Tamás

## Leírás
A „MetaTxt” egy apró segédprogram, mely alapvetően az ingatlan-nyilvántartási célú földmérési és térképészeti tevékenység részletes szabályairól szóló 25/2013. (IV. 16.) VM rendelet 60.§ szakaszában meghatározott meta-adatok szöveges kiterjesztésű (meta.txt) fájlba történő mentésére szolgál.

## Rendszerkövetelmények
A program futtatásához a Microsoft .NET 4.0 keretrendszer szükséges, mely letölthető például a következő helyről: http://www.microsoft.com/hu-hu/download/details.aspx?id=22833

## Verzió-történet
1.6. A betöltött térkép megtekinthető a "Fájl/DAT megtekintés" menüpontban, illetve a "DATPlussz.exe" hibái javítva lettek.
1.5.2. Apró javítások történtek és ettől kezdve a "DATPlussz.exe" használható pl "id" keresésre az alábbi módon:
       1. Elindítjuk a "DATPlussz.exe"-t:
          - első paraméterül adva a betöltendő DAT fájl nevét (és szükség esetén elérési útját);
          - második paraméternek a "/m" (vagy "-m", "-q", "/q") karaktereket (a kis és nagybetű nem számít);
       2. A betöltés (ami akár sokáig is tarthat...) végeztével egy rövid menüben lehet választani, hogy:
          1. egy adott "id"-t keresünk meg, vagy
          2. egy adott "felulet_id"-hez tartozó vonalszakaszokat kérdezünk le.
          ( A menü elég kezdetleges, és az "id" kereső funkció eredménye sem olyan, mint kellene, de már használható... )
1.5.1. Apró javítások, mint például:
       - hibakezelés DAT megnyitás nélküli mentési kísérletkor;
       - a hitelesítő bizonylat nevének módosítási lehetősége.
1.5. Elkészült az automatikus hitelesítő bizonylat készítő funkció;
     A fájl megnyitása után az ablak automatikusan átméreteződik.
1.4. Elkészült ez a leírás, azaz az első "Súgó".
1.3. A futtaható állomány kapott egy beágyazott ikont;
     A fájl megnyitás és mentés során fellépő hibák kezelése megtörtént.
1.2. Az ablak átméretezése során az egyes elemek kitöltik a rendelkezésükre álló helyet;
     Valamennyi, a megnyitott állományokból kinyerhető és szükséges adat mentésre került.
1.1. Ez volt az első valamelyest használható változat, alapvetően semmiféle hibakezelést nem tartalmazott;
     Az adatszolgáltató és település választó lista mellett a fekvés kiválasztására is lehetőség volt;
     A méretarány és a vetület kikeresése a táblázatból még nem működött.
1.0. Az első változat kizárólag prototípusként szolgált, nem került kiadásra.

## Mielőtt használni kezded, jó, ha tudod…
A program az induló adatait, mint pl az adatszolgáltató és a térképellátottság adatai egy-egy CSV állományból veszi annak érdekében, hogy ezt a részt könnyebb legyen testre szabni. (A CSV fájlok első, fejlécet tartalmazó sora nem kerül feldolgozásra!)

Jellemzően egy-egy járásban csak egyetlen adatszolgáltató van, így az Adatszolgáltató.csv-ben elegendő csupán egy szervezetet feltüntetni. Ha egynél több szervezet van a listában, akkor a program engedi a kiválasztást, egyébként a választó-doboz nem lesz aktív.

Hasonló mondható el a térképek adatait tartalmazó Térképellátottság.csv fájlról, azaz a szükségtelten sorokat ki kell/lehet törölni. Térkép-ellátottsági tájékoztatóban lévő adatok a FÖMI/Adminisztráció/Térképellátottság helyről származnak. A fájlban lévő adatok egy része nyilvánvalóan felesleges, de az igazság szerint, lusta voltam minden felesleges adatot kitörölni... ;)

## Használat
0. A program nem igényel önálló telepítést, csupán a ZIP-ben lévő állományokat kell egy szabadon megválasztható könyvtárba másolni.
1. A program indítása a MetaTxt.exe futtatásával történik. (A DatPlussz.exe pár darab tárolt eljárás miatt kell, önálló funkciója nincs. E program az első parancssori paraméterként megadott DAT fájl-ról ad statisztikai adatokat.)
2. Indítás után ki kell választani az adatszolgáltató nevét, feltéve, hogy az elsőként látható nem megfelelő.
3. Ki kell választani a DAT fájlt (pl a "DAT fájl beolvasása" gombra kattintva). Sikeres megnyitás után a meta.txt adatai listázásra kerülnek.
4. Szükség esetén javítani lehet a Településnevet az aktívvá váló legördülő választódobozban. (Jelen pillanatban a javítás csak egyszer hajtható végre, így ha a javítást is javítani kell, akkor a DAT fájlt ismét be kell olvasni.)
5. A beolvasás után javítani lehet továbbá a leendő meta.txt szövegének bármely egyéb részét is, bár erre vélhetően nem túl gyakran lesz szükség.
6. Ha a "Hitelesítő bizonylat mentése" választódoboz be van jelölve, a megjelenő csoport-dobozban megadható a számla betűjele és száma (az évszám a rendszeridőből fog származni). A bizonylat sablonjaként a program mellett lévő "Hitelesítő bizonylat.rtf" szolgál, mely szabadon szerkeszthető. (Esetleges szerkesztésre a Winword helyett a Windows beépített Wordpad-ját ajánlom.) Szerkesztés esetén ügyelni kell, hogy a program a "[" és "]" jelek közötti szövegrészeket cseréli, így ha azokat módosítjuk, a sablon nem fog megfelelően működni.
7. Ha a MetaTxt/MetaRtf fülön látható adatok megfelelnek, akkor a "Meta.txt mentés" gombra kattintva megadható a célfájl neve.
8. A hitelesítő bizonylatként mentett fájl neve automatikusan képződik, de szükség esetén módosítható, illetve az RTF állomány szükség esetén utólag is szabadon szerkeszthető (Erre a Winword helyett itt is a Wordpad-ot javaslom.).
9. A legegyszerűbb nyomtatási lehetőség:
   a. Start menü / Beállítások / Nyomtatók és faxok, majd a megfelelő nyomtató megnyitása;
   b. A hitelesítő bizonylat elkészítése után bármely fájlkezelő programból a mentett állományt a "fogd és vidd" módszerrel a nyomtató ablakába kell dobni. (Ekkor "előugrik" az "rtf" fájlokhoz társított program és a fájl tartalmát elküldi a nyomtatóra.)

## Engedélyek
Ez a segédprogram alapvetően ingyenes.
Lehetőséged van szabadon terjeszteni a segédprogramot floppy lemezen, CD-ROM-on, Interneten, vagy bármilyen más módon, de a Copyright és az engedély szövegét minden másolaton meg kell őrizni, továbbá a kereskedelmi célú felhasználás nem engedélyezett!
A szoftvert (én, a szerző) azzal a reménnyel terjesztem, hogy hasznos lesz, de MINDENFÉLE GARANCIA VÁLLALÁSA NÉLKÜL.
A szerző nem tehető felelőssé a véletlen, követlen, vagy közvetett kárért, adatvesztésért, vagy bármely más ok miatt.

## Visszacsatolás
Ha bármilyen problémád, javaslatod, megjegyzésed van, vagy hibát találtál a programban, kérlek küldj egy "megfelelő" üzenetet a kijato at gmail.com címre!
