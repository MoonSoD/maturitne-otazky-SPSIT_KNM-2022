---
title: 'OSY, PAY'
created: '2022-05-17T09:27:45.458Z'
modified: '2022-05-17T17:38:05.029Z'
---

# OSY, PAY

- ### jednotlivé súborové systémy používané v operačných systémoch Microsoft
  - *CDFS* (CD-ROM File System)
    - súborový systém určený pre CD-ROM, neskôr nahradený UDF
  - *UDF* (Universal Disk Format)
    - súborový systém určený pre prenosné diskové médiá (DVD, CD)
  - *FAT* (File Allocation Table)
    - v starších verziach windowsu (95), nahradený exFAT pre flash disky
  - *exFAT* (Extended File Allocation Table)
    - používaný na flash diskoch
  - *NTFS* (New Technology File System)
    - používaný vo všetkých moderných OS Windows
  
- ### súborové systémy FAT a NTFS
  - *FAT*
    - prvý, jednoduchý súborový systém od Microsoftu
    - podporuje súbory do max 4GB a zväzky do 2TB
    - nepodporuje prístupové práva
    - nie je žurnálovací, ľahšia korupcia dát
  - *NTFS*
    - najpoužívanejší súborový systém od Microsoftu v dnešnej dobe
    - nahradil FAT
    - komprimuje súbory pri nedostatku miesta
    - dokáže nastavovať diskové kvóty
    - šifrovanie a nastavenie prístupových práv súborom
    - podporuje veľmi veľké súbory (256TB)
  
- ### relatívna a absolútna cesta (trasa) k súborom a adresárom
  - relatívna 
    - vzhľadom na aktuálny adresár, v ktorom sa nachádzame 
    - presunieme sa relatívnou cestou `cd Documents`
  - absolútna
    - vzhľadom na koreňový adresár
    - presunieme sa absolútnou cestou `cd C:\Users\user\Documents`

- ### operačné systémy podľa rôznych kritérií
  1) **podľa typu jadra OS**:
      - jednopoužívateľské - beží lokálne, môže ho používať v danom čase len 1 užívateľ
      - multiterminálové (sieťové) - beží na lokálnom serveri, môžu ho využívať viacerí klienti cez sieť
      - distribuované - beží na viacerých PC v sieti, ktoré vzájomne zdieľajú systémové prostriedky
  2) **podľa poču spravovaných úloh a procesorov v systéme**:
      - jednoúlohové - spustená iba 1 aplikácia
      - viacúlohové jednoprocesorové - multitasking, úlohy viacerých aplikácií sa striedajú vo vykonávaní
      - viacúlohové viacprocesorové - paralelný multitasking, všetký aplikácie naraz
  3) **podľa spôsobu uloženia a spracovania výkonného kódu**:
      - pamäťovo rezidentné - celý OS v ROM pamäti, jednoduché mikroPC
      - diskové - OS na pevnom disku a podľa potreby sa načítavajú do RAM pamäte
  4) **podľa určenia**:
      - univerzálne - určené na rôzne aplikácie
      - špeciálne - vykonávajú len špecializovaný druh aplikácií
  5) **podľa používateľského prostredia**:
      - GUI - grafické rozhranie systémových ponúk
      - CLI - ovládanie len príkazovým riadkom

- ### služby operačného systému
  - zabezpečenie komunikácie systému s používateľom prostredníctvom perifériií (klávesnica, myš, monitor, tlačiareň)
  - správa procesora a operačnej pamäte
  - správa systémových prostriedkov medzi aplikácie a užívateľov
  - správa procesov, multitasking
  - správa súborov na diskoch: oprávnenia, zálohovanie, zabezpečenie, odstráňovanie
  - spúšťanie užívateľských programov a správa pamäťového priestoru prideleného programu, spúšťanie programov interpretovaných v jazykoch
  - zabezpečenie systému pred stratou údajov pri výpadku napájania
  - autodiagnostika systému, kontrola integrity
  - komunikácia s inými OS (sieťové)

- ### základné verzie operačného systému Microsoft Windows a ich vydania
  - Windows v1.0
  - Windows 95
  - Windows 98, 98SE
  - Windows XP
  - Windows Vista
  - Windows 7
  - Windows 8, 8.1
  - Windows 10
  - Windows 11

- ### operačný systém Linux a základné pojmy s ním spojené 
  - open-source operačný systém, žaložený na UNIX architektúre
  - nižšia kompatibilita s väčšinou aplikácií kvôli nižšej popularite
  - linux distribúcie sa často používajú ako serverové systémy
  - vyššia bezpečnosť z hľadiska UNIXu, existuje menej škodlivých programov
  - býva viac optimalizovaný ako Windows
  - voľne upraviteľné vzhľadom na open-source
  - **Kernel**
    - jadro OS, zabezpečuje komunikáciu s HW, spravuje súbory, pripojené zariadenia, procesory a pamäť
  - **Distribúcia**
    - operačný systém založený na jadre Linuxu (Ubuntu, Debian, OpenSUSE, Arch)

- ### hierarchickú štruktúru Unixovského súborového systému a význam jednotlivých adresárov
  - /root - koreňový adresár
  - /bin - binárne súbory užívateľský a systémových príkazov
  - /sbin - binárne súbory užívateľský a systémových príkazov
  - /dev - logické mená zariadení
  - /etc - konfiguračné súbory
  - /home - domovské adresáre
  - /kernel - moduly jadra
  - /platform - moduly jadra
  - /lib - knižnice
  - /mnt - dočasné súborové systémy
  - /usr - užívateľské aplikácie
  - /var - meniace sa súbory (logy)
  - /proc - procesy
  - /tmp - dočasné súbory

- ### operačné systémy Microsoft Windows a Linux - porovnanie
  | Windows | Linux
  | ------- | -----
  | closed-source | open-source
  | premium | free
  | vyššia kompatiblita s aplikáciami/ovládačmi | nižšia kompatibilita 
  | NTFS súborový systém | moderné linuxy EXT3, EXT4
  | nižšia bezpečnosť | vyššia bezpečnosť
  | viac dostupných návodov | menej dostupných návodov
  | náročný pre slabšie systémy | nenáročný pre slabé systémy
  | nemožnosť úprav | možné akékoľvek úpravy

- ### základné časti počítača
  - procesor
  - základná doska
  - zdroj
  - pamäť
  - disk
  - grafická karta

- ### vlastnosti jednotlivých časti počítača
  - procesor - vykonáva zadané inštrukcie, ktoré obsahujú PC programy
  - základná doska - umožňuje komunikáciu medzi jednotlivými komponentami PC
  - zdroj - dodáva napájanie komponentom PC
  - pamäť - uchováva údaje, ktoré musia byť ihneď dostupné k ostatnému hardvéru
  - disk - uchováva údaje, ktoré nie sú nevyhnutné na beh systému, potrebné údaje sa z disku načítavajú do pamäte
  - grafická karta - generuje grafický výstup pre zobrazovacie zariadenia

- ### jednotlivé časti počítača z ekonomického pohľadu
  - procesor - 50€ - 1000€+ (frekvencia, počet jadier, vlákien)
  - základná doska - 50€ - 300€ (kompatibilita s komponentami, architektúra, odolnosť)
  - zdroj - 40€ - 150€ (300W - 1200W+ podľa náročnosti ostatných komponentov)
  - pamäť - 20€ - 800€ (4GB - 128GB+, veľkosť, frekvencia, architektúra DDR, napätie)
  - disk - 20€ - 500€ (128GB - 8TB+, veľkosť, SSD/HDD, rýchlosť čítania, rýchlosť zapisovania)
  - grafická karta 70€ - 1000€+ (2 - 16GB+, GDDR pamäť, frekvencia, druhy/počet portov)

- ### počítačové prídavné zariadenia
  - *vstupné zariadenia*:
    - klávesnica
    - myš
    - skener
    - dotyková obrazovka
    - grafický tablet
  - *výstupné*:
    - tlačiareň
    - monitor
    - slúchadlá
    - reproduktory

- ### princípy jednotlivých konštrukčných typov monitorov
  | x | CRT | Plasma | LCD | LED | OLED
  | - | --- | ------ | --- | --- | ----
  | podsvietenie | elektronové lúče po riadkoch | sklenené bunky s plynom ovládané elektrikým poľom | tekuté kryštály ovládané elektrickým poľom, kryštály ovládané napätím | vyžarujúce diódy | organické, vlastným svetlom |
  | váha | veľmi vysoká | vyššia | nízka | nízka | nízka
  | vyrábané | nie | nie | áno | áno | áno | áno
  | spotreba | veľmi vysoká | nižšia | nízka | nízka | nízka

  - LCD panely
    - IPS (in Plane Switching) - najlepší, najpoužívanejší - matný, vysoká kvalita, nízka odozva, široký uhol zobrazenia, presnosť zobrazenia
    - TN (Twisted Nematic) - veľmi nízka odozva, lacnejšie, nízky kontrast, nepresné farby, úzky uhol zobrazenia
    - VA (Vertical Alignment) - vysoký jas, vysoký kontrast, širší uhol pozorovania, vyššia odozva

- ### princípy jednotlivých konštrukčných typov tlačiarní
  - *Ihličkové*:
    - tlačiaca hlava s ihličkami, ktoré tvoria maticu
    - ihličky sa vysúvajú elektromagnetmi podľa písmena, ktoré tlačia
    - pretlačia text cez pásku
  - *Atramentové*:
    - tlačiaca hlava s tryskami, cez ktoré strieka atrament
    - písmena sa tlačia striekaním kvapiek atramentu
    - farebná tlač sa dosiahne zmiešaním 3 základných farieb (CMY)
  - *Laserové*:
    - toner sa naniesie na miesta, ktoré sa nabijú elektrostatickým poľom podľa predlohy strany, ten sa zahreje na vysokú teplotu, napáli a zotrie
  - *Tepelné*
    - na papier nanesený atramentom sa prenáša na určité miesta teplo, ten sa zohreje a atrament sa zviditeľní

-  ### vlastnosti a druhy pamätí používaných vo výpočtovej technike
  - pamäť je zariadenie, ktoré umožňuje zapamätať si informáciu na ľubovoľnú dobu a poskytunúť ju 
  - **vlastnosti**:
    - *kapacita*: množstvo údajov, ktoré môžeme do pamäte uložiť
    - *prístupová doba*: čas, za ktorý pamäť údaje sprostredkuje
    - *prenosová rýchlosť*: počet prenesených údajov za určitý čas
    - *MTFB*: poruchovosť, stredná doba medzi poruchami
    - *spotreba*
    - *cena*
  - **delenie pamäti**:
    - *podľa energetickej závislosti*:
      - volatilné - údaje sa po odpojení napájania stratia
      - nevolatilné - údaje sa po odpojení napájania nestratia
    - *podľa prístupu a možnosti programovania*:
      - ROM - iba na čítanie, naprogramovaná od výroby
      - PROM - 1x programovateľná
      - EPROM - 100x programovateľná, vymaže sa UV svetlom
      - EEPROM - 1000x programovateľná, vymaže sa elektricky
      - FLASH - vylepšená EEPROM, podobá sa RAM, cca. 100 000x programovateľná
      - RWM - volatilná pamäť na čítanie aj zapisovanie
      - RAM - pamäť s ľubovoľným prístupom
    - *podľa druhu prístupu*:
      - maticové - paralelný prístup k údajom podľa riadku a stĺpca
      - SAM - sériový prístup
    - *podľa princípu činnosti*:
      - statické - údaje sa pamätajú po celý čas napájania
      - dynamické - údaje musíme pravidelne obnoviť
    - *podľa technológie výroby*:
      - bipolárne - bipolárne tranzistory, vyššia spotreba, technológia TTL
      - unipolárne - unipolárne tranzistory, nižšia spotreba, technológia CMOS
      - feroelektrické - feroelektrické kryštály, drahé

- ### činnosť, časti a charakteristiky pevného disku
  - zariadenie na trvalé uchovanie dát na základe magnetizmu
  - geometria disku - počet hláv, sektorov a cylindrov
  - stopa - jedna kružnica na strane platne
  - sektor - jedna časť rozdelenej stopy
  - **časti HDD**:
    - platne - záznamové médium
    - pohon - motor, ktorý poháňa platne
    - hlavička - čítanie, zápis
  - **vlastnosti disku**:
    - kapacita
    - výkon - rýchlosť zápisu/čítania, doba vyhľadávania, doba prístupu
    - MTFB
    - cena

- ### optický záznam dát a porovnajte jednotlivé optické disky (CD, DVD, BD)
  - údaje sa zapisujú vo forme výstupov (log. 1) alebo priehlbín (log. 0) na špeciálny materiál disku
  - čítanie pomocou laserového lúča
    - CD: 700MB, 
    - DVD: 4-8GB 
    - BD: 25-50GB

- ### jednotlivé typy výpočtového modelu
  - vzťah všetkých zložiek, ktoré sú v PC sieťach (užívatelia, hardvér, softvér, dáta)
  - **typy**:
    - *dávkové spracovanie*
      - najstarší výpočtový model
      - k PC mala kedysi prístup len špeciálizovaná obsluha, záujemcovia o výpočet dávali požiadavky na dierne štítky a po čase si mohli príst po výsledok 
      - v dnešne dobe sa používa pri RJE (Remote Job Entry) kde sa dávka pripraví na PC a pošle sa na spracovanie SuperPC
    - *host/terminál*
      - vzdialené ovládanie hostiteľského PC pomocou terminálu (textového/grafického) 
      - umožňuje používanie periférií
      - väčšinou viac terminálov pripojených k jednému hostiteľovi
    - *samostatné počítače* (sieťovo neprepojené)
      - úplne decentralizované
    - *rovný s rovným* (peer-to-peer)
      - všetky uzly v sieti sú si hierarchicky rovnocenné
      - každý počítač môže poskytovať svoje prostriedky a služby iným uzlom
    - *klient/server*
      - server - poskytovateľ služieb
      - klient - konzument služieb
      - služby: diskový server (vyhradený disk), súborový server (vyhradená kapacita), tlačový server, aplikačný server (webový, mailový), databázový server
    - *distribuovaný systém*
      - rozdelenie náročného výpočtového problému medzi viac uzlov
    - *cloud computing*
      - na serveri v dátovom centre je softvér, a len ten zákazník používa
      - softvér spravuje poskytovateľ
    - *internet vecí* (IoT)
      - "veci" sledujú svoje okolie a komunikujú s inými "vecami", so serverom alebo s ľuďmi
      - napr.: snímač odtlačku prsta nenájde zhodu a neotvorí vám bránu

- ### von Neumanovú a Harvardskú architektúru počítačov
  - von Neumannová
    - skladá sa:
      - OP (Operačná Pamäť)
      - ALU (Aritmeticko Logická Jednotka)
      - Radič
      - IO zariadenia (Vstupné a výstupné zariadenia)
![Image](https://raw.githubusercontent.com/MoonSoD/maturitne-otazky-SPSIT_KNM-2022/main/attachments/neumannova_architektura.jpg)
  - Harvardská
    - fyzicky oddeľuje pamäť programu a dát
    - dvojitá pamäť umožňuje paralelný prístup, čo zrýchľuje spracovanie a vyššiu bezpečnosť
![Image](https://raw.githubusercontent.com/MoonSoD/maturitne-otazky-SPSIT_KNM-2022/main/attachments/harvardska_architektura.jpg)

- ### čipová sústava základnej dosky osobných počítačov
  - motherboard chipset
  - ovláda komunikáciu medzi CPU, RAM, úložiskom a prefifériami
  - ich parametre definujú maximálnu rýchlosť a počet USB portov
  - špecifické procesory fungujú na špecifických chipsetoch (Intel CPU nedáme na AMD chipset)
  - Intel Z690 pre 12th Gen Alder Lake, AMD X570 pre Ryzen 3000

- ### rôzne druhy procesorov a ich vlastnosti
  - **podľa použitia**:
    - CPU - v PC
    - MCU - klávesnice, diaľkové ovládače, vývojové dosky
    - DSP - spracovanie signálov
  - **podľa počtu jadier**:
    - jednojadrové
    - viacjadrové
  - **podľa inštrukčnej sady**:
    - CISC (komplexná sada inštrukcií) - vysoký počet inštrukcií, dlhšie výpočty
    - RISC (redukovaná sada inštrukcií) - nízky počet inštrukcií, nižšia spotreba pamäte
    - ZISC - priemyselné procesory
  - **podľa šírky operanda**:
    - 4 a 8 bitové - jednoduché (kalkulačky)
    - 8 a 16 bitové - stredne zložité (PDA, MP3)
    - 32 a 64 bitové - náročné (PC)

- ### architektúru CISC a RISC a princíp prúdového spracovania informácií
  - **CISC**:
    - komplexná inštrukčná sada, procesor vykonáva paralelne viac inštrukcií
    - vyššie nároky na HW, menej kódu, viac dátových typov
  - **RISC**:
    - redukovaná inštrukčná sada, menej inštrukcií
    - nižie nároky na HW, viac registrov, viac kódu
  - **Prúdové spracovanie**:
    - prekrývanie inštrukcií, zreťazené spracovanie
    - inštrukcia sa vykonáva v sekcii, keď sa dokončí, tak sa do sekcie presunie ďalšia inštrukcia na spracovanie

- ### princípy paralelných systémov (napríklad SISD, MISD, SIMD, MIMD)
  - SI - 1 tok programu
  - MI - viac tokov programu
  - SD - 1 tok dát
  - MD - viac tokov dát
  - **ich kombinácie (4)**:
    - *SISD*: 1 tok programu spracováva 1 tok dát, bez paralelného spracovania
    - *MISD*: viac programov spracuje 1 tok dát, prúdové spracovanie
    - *SIMD*: 1 program spracuje viac tokov dát, napr. práca s grafikou
    - *MIMD*: viac programova spracuje viac tokov dát, paralelné spracovanie

- ### jednotlivé typy správy pamäte
  - pridelenie celej OP - 1 úlohový systém
  - pridelenie OP po blokoch - pri spustení aplikácie sa jej pridelí blok OP
  - presúvanie blokov - efektívne využitie, presun trvá nejaký čas
  - stránkovanie - pamäť rozdelená na rovnaké časti (stránky), správca ich prideľuje aplikáciam podľa potreby
  - stránkovanie OP na žiadosť (virtuálna OP) - časť dát aplikácií sa ukladá na HDD, viac pamäte, HDD je pomalší

- ### jednotlivé typy správy procesora
  - monitorovanie stavu procesora, vyťaženia
  - prideľovanie a odoberanie strojového času
  - plánovanie a optimalizácia

- ### jednotlivé typy správy vstupno-výstupných zariadení
  - x

