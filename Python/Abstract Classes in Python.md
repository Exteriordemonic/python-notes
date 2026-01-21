aliases: []  
tags: [theory, cs, programming]  
sr-due: true
graph: false

#review 

---

## 🧠 Co to jest?

W Pythonie **klasa abstrakcyjna** to specjalny rodzaj klasy, który:

- **nie może być instancjonowany** (czyli nie można tworzyć jej obiektu bezpośrednio),
    
- służy jako **szablon/kontrakt** dla klas potomnych,
    
- zapewnia wspólny interfejs — wymusza implementację określonych metod przez klasy dziedziczące.

Krótko: to niekompletna klasa, którą wykorzystujesz do wymuszenia zachowań w podklasach.
## 🔧 Jak to działa?
Python udostępnia moduł `abc`, który pozwala definiować klasy abstrakcyjne:

`from abc import ABC, abstractmethod  class Animal(ABC):     @abstractmethod     def sound(self):         pass`

- `ABC` — klasa bazowa (metaklasa) dla klas abstrakcyjnych.
    
- `@abstractmethod` — dekorator oznaczający metodę abstrakcyjną.
    
- Taka klasa **nie może być instancjonowana**, dopóki wszystkie abstrakcyjne metody nie zostaną zaimplementowane w klasie potomnej.

## 🧠 **Dlaczego warto używać klas abstrakcyjnych?**

Oto główne zalety:

✔️ Wymuszają spójny interfejs dla klas potomnych  
✔️ Ułatwiają projektowanie “kontraktów” (np. różne typy zwierząt muszą implementować sound())  
✔️ Poprawiają czytelność i strukturę kodu  
✔️ Pozwalają na częściowe zaimplementowanie wspólnej logiki (metody konkretne)

## 🧪 Przykład

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def sound(self):
        pass

class Dog(Animal):
    def sound(self):
        return "Bark"

dog = Dog()
print(dog.sound())  # Bark

```

---

## 🧩 Mnemotechniki

### 🅰 Akronim

**Akronim:** ABC

**Rozwinięcie:**

- AB— Abstract 
    
- C — Class
    

---

### 🔄 Tłumaczenie jako analogia

**Analogia:** **Abstract Class** można porównać do **wzoru lub instrukcji**, która nie robi nic sama z siebie, tylko **narzuca strukturę i wymagania** — tak jak instrukcja pisania maila mówi, że musi być adresat, temat, treść i stopka, ale **nie podaje konkretnych słów**, bo to zależy od osoby, która ten mail faktycznie napisze.

---

### 🗃 Keyword Connections (powiązania)

- [[OOP]]
    
- [[Class]]
    
---

### 🖼 Rysunek / schemat / diagram ASCII

![[Pasted image 20260121083550.png]]
---

## ✨ Metoda Feynmana (1–2 zdania)

Absctart class to taka wzór instrukcji, nie mówi Ci jak ma coś działać tylko jakie funkcję powinna posiadać 

---

## ⚠ Typowe błędne wyobrażenie

---

## 📌 Kontrast (X vs Y)

| Cecha | Metoda abstrakcyjna                                             | Metoda konkretna                                                                           |
| ----- | --------------------------------------------------------------- | ------------------------------------------------------------------------------------------ |
|       | zadeklarowana bez ciała (`pass`) i oznaczona `@abstractmethod`. | posiada implementację i jest dziedziczona przez podklasy bez konieczności jej redefinicji. |
|       |                                                                 |                                                                                            |

---

## 🗂 Fiszki (SRS) #flashcards 

Na czym polega rola modułu **abc** w Pythonie?  
?  
Moduł **abc** dostarcza mechanizm do definiowania klas abstrakcyjnych, umożliwiając egzekwowanie kontraktu poprzez klasę `ABC` oraz dekorator `@abstractmethod`.

---

Czym mentalnie jest **klasa abstrakcyjna (ABC)**?  
?  
Klasa abstrakcyjna definiuje **kontrakt** dla klas potomnych — określa, jakie metody muszą istnieć, ale nie narzuca ich konkretnej implementacji.

---

Co sprawia, że klasa jest uznawana przez Pythona za **abstrakcyjną**?  
?  
Klasa jest abstrakcyjna tylko wtedy, gdy posiada **niezaimplementowane metody oznaczone `@abstractmethod`**; samo dziedziczenie po `ABC` nie wystarcza.

---

Dlaczego nie można tworzyć instancji klasy abstrakcyjnej?  
?  
Ponieważ Python egzekwuje kontrakt — **instancję można utworzyć dopiero wtedy, gdy wszystkie metody abstrakcyjne zostaną zaimplementowane**.

---

Na czym polega kluczowa różnica mentalna między **ABC a duck typingiem**?  
?  
Duck typing sprawdza jedynie **zachowanie w danym miejscu** („czy obiekt ma tę metodę”),  
natomiast ABC definiuje **formalny kontrakt i rolę obiektu**, wymagając spełnienia całego zestawu metod.

---

## 🔗 Powiązane notatki