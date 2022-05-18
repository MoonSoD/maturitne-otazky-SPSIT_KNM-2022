---
title: 'SIE, CIT, IVI'
created: '2022-05-18T07:06:16.598Z'
modified: '2022-05-18T13:35:42.101Z'
---

# SIE, CIT, IVI

- ### jednotlivé hrozby a útoky v počítačových sieťach
  - hacking - prienik do siete za účetlom hľadania chýb a nedostatkov v zabezpečení
  - cracking - prienik do siete za účelom škodiť
  - spoofing - vydávanie sa za overené zariadenie pod falošnou identitou
  - phishing - získavanie údajov (hesiel...) pomocou falošnej kópie webstránky/emailu
  - phreaking - prienik do telefónnej siete za účelom odposluchu alebo jej využívania
  - sociálne inžinierstvo - vydávanie sa za dôveryhodnú osobu za účelom získania údajov

- ### spôsoby zabezpečenia smerovačov a prepínačov
  - fyzicky - zamknúť do serverovne, racku na kľúč alebo čipovú kartu
  - elektronicky - nastavenie hesla pre privilegované režimy a pre SSH/Telnet porty
    - nastavenie hesla do privilégovaného módu, šifrované heslo a heslo do konzoly
    ```
    enable password
    enable secret
    line console 0
    password c1sc0
    login
    ```

- ### princíp prístupových zoznamov (ACL) v počítačových sieťach, ich použitie a delenie
  - spravuje prístup do siete, vymedzuje pravidlá
  - posielajú inštrukcie smerovačom a switchom o povolenej premávke
  - diktujú, čo môžu zariadenia a užívatelia v zariadení robiť
  - **typy ACL**:
    - *štandardný ACL*:
      - paket je blokovaný/prepustený na základe zdrojovej alebo cieľovej IP
      - označujú sa číslami 1-99
    - *rozšírený ACL*:
      - posytujú väčší rozsah kontroly: zdrojovú a cieľovú IP, protokol a port
      - označujú sa číslami 100-199

- ### jednotlivé WAN prenosové technológie
  - **tradičné**:
    - *circuit-switched* (pomocou telefonnej linky): 
      - Public Service Telephone Network (PSTN)
        - analógový prenos
      - Integrated Services Digital Network (ISDN)
        - umožňuje PSTN digitálny prenos
    - *packet-switched* (údaje premieňa na packety, ktoré prenáša cez verejnú sieť):
      - Frame Relay
        - na 2. vststve, kedysi prepájalo LANky a WANky
      - Asynchronous Transfer Mode (ATM)
        - dokáže prenášať audio, video a dáta cez verejné a súkromné siete
  - **moderné**:
      - *dedicated broadband*
        - prepojené priamo optickým vláknom
      - *packet-switched*
        - Metro Ethernet
        - MPLS (Multiprotocol Label Switching)
      - *internet-based broadband*
        - prepojenie cez internet

- ### princíp fungovania VPN (virtuálna privátna sieť), jej vlastnosti a delenie
  - zašifrovaný tunel, ktorý prepája 2 miesta na internete
  - často sa používa na vzdialený prístup k dátam
  - lacné, bezpečné, škávateľné
  - **delenie**
      1) VPN spravované podnikom
          - typy prístupových VPN
            - klientské - v prehliadači cez SSL
            - bezklientské - nainštalovaný VPN klient
          - GRE (Generic Routing Encapsulation)
            - nezabezpečené tunely
            - podporuje multicast
            - zabezpečuje sa cez IPsec
          - DMVPN (Dynamic Multiport VPN)
            - jednoduchšie vytváranie viacerých VPN (dynamické vytváranie)
            - používa mGRE (Multipoint GRE)
            - hub-and-spoke topológia
          - VTI (IPSec Virtual Tunnel Interface)
            - tunel sa pripája na virtuálne rozhranie
      2) VPN spravované poskytovateľom
          1) L2 MPLS VPN - ISP pridá MPLS hlavičku s návesťami, ktoré označuje jednotlivé tunely
          2) L3 MPLS VPN - MPLS hlavička sa pripája k ethernet rámcu, netreba smerovanie

- ### protokoly na správu siete (CDP, LLDP, NTP, SNMP, Syslog)
  - **CDP** (Cisco Discovery Protocol):
    - Cisco proprietárny
    - L2 protokol, ktorý zbiera údaje o CISCO zariadeniach na 1 link
    - odosiela CDP inzeráty k pripojeným zariadeniam, ktoré nesú údaje
  - **LLDP** (Link Layer Discovery Protocol):
    - protokol, ktorý zbiera údaje o pripojených zariadeniach
    - komunikuje so zariadeniami a získava od nich údaje... (identitu, susedov)
  - **NTP** (Network Time Protocol):
    - protokol na synchronizáciu času na smerovačoch pomocou NTP servera
    - používa hierarchické zdroje času, každá úroveň sa nazýva stratum (max 16)
      - 0 - najpresnejšie
      - 16 - desynchronizovaný čas
  - **SNMP**:
    - protokol, ktorý poskytuje formát správ a komunikáciu medzi správcami a zástupcami na správu uzlov (nodes)
      - SNMP manager (1) - get/set správy
      - SNMP agent (spravované uzly) - trap (eventy, keď sa niečo stane)
      - Management information base (MIB) 
  - **Syslog**:
    - logovacia služba na monitorovanie, zoskupinie a zisťovanie akcií na zariadení
    - má úrovne dôležitosti (0-7):
      0 - emergency
      1 - alert
      2 - critical
      3 - error
      4 - warning
      5 - notification
      6 - informational
      7 - debug

- ### optické spektrum, optické siete a optické spoje
  - **optické spektrum**:
    - skladá sa častí:
      - infračevej
      - viditeľnej
      - ultrafialovej 
    - na prenos optického signálu sa používa infračervená časť, ktorá má vo vlákne nízky relatívny útlm (0,3dB/km)
  - **optické siete**:
    - skladá sa z jednotlivých optických spojov, obsahuje aj geografické územie
      - transportná časť
      - prístupová časť
    - celý návrch siete je hierarchický a modulárny, uzly sa prepájajú horizontálne (na rovnakej úrovni) a vertikálne (medzi úrovňami)
    - *vývojový trend*:
      - transportná časť je už dobudovaná
      - prístupová časť sa buduje
    - *dokumentácia siete*:
      - majetková správa
      - územný rozsah
      - aktuálny technický stav
      - aktuálny stav zaťaženia
  - **optické spoje**:
    - prenosový systém, ktorý prepája 2 miesta v sieti, skladá sa z rôznych komponentov
    - *delenie komponentov*:
      1) vnútorné, vonkajšie
      2) aktívne, pasívne

- ### komponenty optických sietí a typy optických vlákien
  - *komponenty*:
    - optické káble
    - optické spojky
    - optické konektory 
    - prepájacie moduly (pigtail, patchcord)
    - mechanické spojky
    - zvary/pevné spoje
  - *typy optických vlákien*:
    - viacvidové 
      - na kratšie vzdialenosti (vrámci budov)
      - lacnejšie ako jednovidové
    - jednovidové
      - na dlhé vzdialenosti 

- ### odhad útlmu a prevádzkové meranie optických trás 
  - **odhad útlmu**:
    - odhadujeme, aby sme vedeli akú reálnu hodnotu môžeme namerať
    - nameraná hodnota nesmie byť väčšia ako odhad
    - odhad každej trasy robíme pre 2 vlnové dĺžky
    - *zložky*:
      - vložený útlm optického vlákna v trase
        - merný útlm [dB/km] * dĺžka trasy [km] = [db]
      - vložený útlm konektorových spojení na trase
        - limit útlmu na konektorové spojenie [dB] * počet spojení [dB]
      - vložený útlm zvaru na trase
        - limit útlmu [dB] * počet zvarov 
    - odhadovaný útlm je súčet všetkých 3
  - **meranie optických trás**:
    - meria sa 2 metódami
      - útlm priamou metódou
        - zdroj optického signálu a merač úrovne optického signálu
        - zariadenie pripojíme na priamo 1-3 patchocordami, zistíme tým pridaný útlm mimo meracej trasy
        - meriame pomocou preddefinovanej tabuľky
      - námer reflektometrom (OTDR - Optical Time Domain Reflectometer)
        - do vlákna vyšleme optický impulz, a na tej istej strane vlákna snímame časovú závislosť spätného rozptylu a odrazu
        - dĺžka impulzu od 1 mikrosekundy pri trase 10tok km
        - výsledkom je námerová krivka
    - meria sa každé vlákno zvlášť
    - meria sa pomocou 2 vlnových dĺžok
    - meria sa v prevádzke (3. fáze životnosti kábla)

- ### princíp činnosti DNS a hierarchickú štruktúru DNS
  - (Domain Name System) - menný systém na internete
  - prekladá mená na IP adresy
  - menný server spracováva informácie, ktoré sa pôvodne nachádzali na jednotlivých hostiteľoch
  - **DNS hierarchia**:
    1) root level (menný server)
    2) top level domény (com, eu, sk, cz, net, org)
    3) second level domény (názov domény... __spsknm__.sk)
    4) sub doména (**spsknm**.edupage.org)
    5) hostiteľ
  
- ### princíp činnosti protokol prekladu adries NAT
  - Network Address Translation
  - umožňuje pripojenie viacerých zariadení na internet pod 1 verejnou IP adresou
  - pri vstupe na internet sa lokálna IP adresa preloží na globálnu (verejnú) IP adresu, pri vrátení packetu sa verejná IP premení na lokálnu

- ### princíp činnosti protokolu DHCP
  - Dynamic Host Configuration Protocol
  - protokol na dynamické prideľovanie IP adries v sieti, zariadenie si vyžiada IP adresu a DHCP server mu pridelí dostupnú adresu
  - dostupné adresy uchováva v databáze/tabuľke

- ### prenosová technológia Ethernet
  - súbor technológií na pripojenie do počítačových sietí
  - používajú sa káble:
    - krútený pár (pomalšie)
    - optické vlákna (rýchle)
  - realizuje sa fyzickou a linkovou vrstvou OSI modelu 

- ### ethernetový prepínač, jeho časti, funkcie a vlastnosti, faktory výberu ethernetového prepínača
  - sieťové hardvérové zariadenie, ktoré prepája zariadenie pripojené káblom (PC, Wi-Fi access pointy, PoE svietenie, servery) aby mohli spolu komunikovať
  - oproti hubu, ktorý je na fyzickej vrstve, ethernetový prepínač spravuje tok dát, smeruje ho medzi portami podľa hlavičky packetu a MAC adresy
    - dokáže limitovať prenos alebo priradiť viac prenosovej rýchlosti na určitý port bez degradácie výknu
    - pri viacerých aktívnych zariadeniach je ethernetové prepínanie efektívnejšie
    - znižuje výpadky
  - **faktory výberu**:
    - počet portov
    - očakávaný bandwidth
    - efektívnosť napájania
    - veľkosť
    - frekvencia aktualizácií

- ### proces prepínania rámcov v ethernetovom prepínači
  - prepínač v pamäti vytvorí tabuľku MAC adries všetkých zariadení na portoch
  - po zapnutí je MAC tabuľka prázdna, prepínaš rozpošle dátové rámce všetkým zariadeniam, no príjme ho len zariadenie pre ktoré je rámec určený
  - odpoveďou na rámec sa zariadenie zapíše do MAC tabuľky
  - podľa mac tabuľky porovnáva zariadenia na portoch, podľa toho vie kam preposlať dáta

- ### konfiguračné príkazy ethernetového prepínača
  ```
  show version
  show running-config
  show interfaces

  enable secret cisc0
  line console 0
  password cisc0
  login
  hostname MENO_PREPINACA

  interface fa0/1
  ip address 192.168.1.2 255.255.255.0
  exit
  ip default-gateway 192.168.1.1
  ```

- ### princíp činnosti protokolov pre agregáciu liniek v prepínaných ethernetových sieťach
  - agregácia portov, ktorá zoskupí viac pripojených zariadení a môžu vystupovať cez 1 IP adresu ako 1 zariadenie

- ### dôvody používania redundancie v prepínaných ethernetových sieťach a problémy, ktoré to spôsobuje
  - v prípade výpadku sa použije iná, redundantná linka, tým sa zamedzí úplnému výpadku
  - redudancia môže vytvárať fyzické slučky v topológii siete, packety sa odrážajú späť k prepínaču, ktorý ich poslal
  - na prevenciu slučiek sa používa Spanning Tree Protocol (STP)

- ### princíp činnosti protokolu STP v ethernetových prepínačoch a jednotlivé verzie STP
  - v prípade redundancie liniek v prepínanych sieťach 2 alebo viacerými prepínačmi sa môžu tvoriť fyzické slučky
  - STP zabraňuje tvorbe slučiek pomocou Spanning Tree Algoritmu
  - prepínače si vymieňajú BDPU rámce s cenami trás a prioritami, podľa týchto informácií STP zablokuje redundantné linky, ktoré by spôsobili slučku
  - **verzie**:
    - 
   
