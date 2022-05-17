---
title: 'OSY, PAY'
created: '2022-05-17T09:27:45.458Z'
modified: '2022-05-17T11:03:08.504Z'
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
    - 


