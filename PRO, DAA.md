---
title: 'PRO, DAA'
created: '2022-05-11T17:08:40.382Z'
modified: '2022-05-11T19:29:06.209Z'
---

# PRO, DAA

- ### programovacie jazyky Python, Java/C#, C, PHP, Blocky, Assembler - porovnanie 
  | jazyk | dátové typy | štruktúra | komentáre | syntax |
  | ----- | ----------- | --------- | --------- | ------ |
  | Python | dynamické | OOP  | `# koment`;`""koment""` | nepovinné bodkočiarky, oddelenie scopov (sekcií) tabulátormi, žiadne množinové zátvorky {}
  | Java/C# | statické | OOP | `// koment `;`/* koment */` | bodkočiarky, oddelenie scopov {}
  | C | statické | procedurálna  | `/* koment */` | bodkočiarky, oddelenie scopov {}
  | PHP | dynamické | OOP | `// koment`;`/* koment */` | bodkočiarky, oddelenie scopov {}
  | Blocky | dynamické | procedurálna/OOP | nemá | programovanie presúvaním blokov, nie písaním kódu
  | Assembler | ? | procedurálna | `; koment` | žiadne bodkočiarky

  - *statické dátové typy* - musíme ich predurčiť v kóde
  - *dynamické dátové typy* - jazyk si ich dokáže sám dosadiť počas runtime
  - *OOP* - Objektovo Orientované Programovanie - každá časť programu delená do tried, ktoré majú svoje konštruktory, atribúty, deštruktory, metódy (použitie jednej triedy na viac vecí abstrakciou, nemusíme sa opakovať)
  - *procedurálna štruktúra* - písanie presných inštrukcií pre kód, žiadne delenie ako pri OOP, môžeme opakovať viackrát to isté
  - *scope* - sekcia kódu 
  ```java
  // demonštrácia v jave
  class Trieda {
    public Trieda() { //konštruktor
      //toto je scope
    }

    void funkcia() { 
      //toto je scope
      int cislo = 5;

      for (int i = 0; i <= 5; i++) {
        //toto je ďalší scope
        System.out.println("Ahoj svet!");
      }
    }
  }


    ```
    ```python
    # demonštrácia v pythone
    def funkcia():
      #toto je scope
      cislo = 5

      for i in range(6):
        #toto je ďalší scope
        print("Ahoj svet!")
    ```

- ### dátové typy a druhy komentárov v jazyku C/C++
  | typ | popis | deklarácia |
  | --- | ----- | ---------- |
  | Boolean | pravdivostná hodnota 1/0 true/false | bool |
  | Character | 1 znak - písmeno/číslo... | char |
  | Integer | celé číslo | int |
  | Floating point | desatinné číslo, 6-7 miest | float |
  | Double floating point | desatinné číslo, 15-16 miest | doube |
  | Valueless | bez návratovej hodnoty | void |
  | Wide character | znak, ktorý zaberá viac ako 1 byte | wchar_t

- ### využitie konštánt, makier a knižníc v jazyku C/C++
  - *konštanta*
    - premenná, ktorá sa nedá počas behu programu prepísať (na čítanie/read-only)
    - používame za predpokladu, že nechceme zásah do premennej /prípadne aj z tretej strany/
    ```C
    const int cislo = 1;
    ```
  - *makro*
    - časť kódu/funkcia, za ktorú sa počas kompilácie dosadí definovaná hodnota daného makra
    - môže mať aj argumenty
    ```C
    #define SCITAT (a, b) (a) + (b) 
    ```
  - *knižnica*
    - balík predpísaného kódu, ktorý ušetrí programátorovi čas a stabilitu programu
    - bývajú písané tretími stranami na zjednodušenie určitých cieľov v kóde
    ```C
    #include <iostream>
    ```

- ### činnosť operátorov +=, ++, &&, ||, =, ==, !=, %, &, |, >>, ^
  | operátor | popis | príklad |
  | -------- | ----- | ------- |
  | += | pridanie hodnoty na pravej strane na ľavú stranu spolu s navrátením už pridanej hodnoty | <pre lang="C">int i = 5; <br>i += 2; // hodnota bude 7</pre> |
  | ++ | zvýšenie hodnoty o 1 | <pre lang="C">int i = 5; <br>i++ //hodnota i bude 6</pre> |
  | && | logický AND - a -> návratová hodnota bude pravdivá len pokiaľ podmienky na oboch stranách budú pravidivé | <pre lang="C">int i = 5; <br>int j = 8; <br>bool plati = i == 5 \&\& j == 8; //vrati hodnotu true</pre> |
  | \|\| | logický OR - alebo -> návratová hodnota bude pravdivá ak aspoň podmienka z 1 strany bude pravdivá | <pre lang="C">int i = 5; <br>int j = 8; <br>bool plati = i == 5 \|\| j == 6; //vrati hodnotu true</pre> |
  | = | priradenie hodnoty pravej strany na ľavú stranu | <pre lang="C">int i = 5;</pre> |
  | == | binárne porovnanie ľavej a pravej strany, pokiaľ sa rovnajú vráti true | <pre lang="C">int i = 5; <br>bool plati = i == 5; //vrati hodnotu true |
  | != | negované binárne porovnanie ľavej a pravej strany, pokiaľ sa rovnajú vráti false | <pre lang="C">int i = 5; <br>bool plati = i != 5; //vrati hodnotu false |
  | % | modulo -> vráti hodnotu zvyšku delenia ľavej strany pravou stranou | <pre lang="C">int i = 3 % 4; //vráti 3 |
  | & | bitový AND - vráti hodnotu bitového súčinu ľavej a pravej strany | <pre lang="C">int i = 5; <br>int j = 9; <br>int bitovy_sucin = i & j; //vrati hodnotu 1 |
  | \| | bitový OR -  vráti hodnotu bitového súčtu ľavej a pravej strany | <pre lang="C">int i = 5; <br>int j = 9; <br>int bitovy_sucet = i \| j; //vrati hodnotu 13 |


