---
title: 'PRO, DAA'
created: '2022-05-11T17:08:40.382Z'
modified: '2022-05-11T17:44:54.915Z'
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
  | Assembler | statické | procedurálna | `; koment` | žiadne bodkočiarky

  - *statické dátové typy* - musíme ich predurčiť v kóde
  - *dynamické dátové typy* - jazyk si ich dokáže sám dosadiť počas runtime
  - *OOP* - Objektovo Orientované Programovanie - každá časť programu delená do tried, ktoré majú svoje konštruktory, atribúty, deštruktory, metódy (použitie jednej triedy na viac vecí abstrakciou, nemusíme sa opakovať)
  - *procedurálna štruktúra* - písanie presných inštrukcií pre kód, žiadne delenie ako pri OOP, môžeme opakovať viackrát to isté
  - *scope* - sekcia kódu 
  ```java
  // demonštrácia v jave
  void funkcia() { 
    //toto je scope
    int cislo = 5;

    for (int i = 0; i <= 5; i++) {
      //toto je ďalší scope
      System.out.println("Ahoj svet!");
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

- ### 
