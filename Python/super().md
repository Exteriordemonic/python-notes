---
sr-due: 2026-01-07
sr-interval: 2
sr-ease: 247
---

aliases: []  
tags: [theory, cs, programming]  
sr-due: true
graph: false

#review 

---

## 🧠 Co to jest?
**`super()`** w Pythonie to wbudowana funkcja, która zwraca **proxy do klasy nadrzędnej (lub kolejnej w MRO)** i pozwala wywoływać jej metody **bez jawnego odwoływania się do nazwy klasy**.
Zwraca Obiekt reprezętującey klasę nadrzędną

## 🔧 Jak to działa?
### 1️⃣ Co tak naprawdę zwraca `super()`

`super()` **nie wywołuje metody**.  
`super()` **zwraca obiekt proxy**, który:

- wie **z jakiej klasy** jest wywoływany
    
- wie **dla jakiej instancji**
    
- zna **MRO (Method Resolution Order)**
    

Ten proxy mówi:

> „Znajdź następną klasę w kolejności MRO i spróbuj tam znaleźć metodę”.

### 2️⃣ MRO – klucz do wszystkiego

Python **nie idzie „do rodzica”**, tylko:  
➡️ **idzie do następnej klasy w MRO**

## 🧪 Przykład

```python
class A:
    def foo(self):
        print("A")

class B(A):
    def foo(self):
        print("B")

class C(B):
    def foo(self):
        super().foo()

```

C → B → A → object

Python robi:

1. `C.foo()`
    
2. `super()` w `C` → **następna w MRO = `B`**
    
3. Wywołuje `B.foo()`
    

📌 **Nie `A`**, tylko **B**


---

## 🧩 Mnemotechniki

### 🅰 Akronim

#### **Akronim: SUPER**

**S — Szuka następnej klasy wg MRO**  
👉 _nie rodzica, tylko kolejną w kolejności_

**U — Up the MRO**  
👉 _idzie „w górę” hierarchii zgodnie z MRO_

**P — Proxy do klasy nadrzędnej**  
👉 _`super()` nie wywołuje metody — zwraca obiekt pośredni_

**E — Execute next method**  
👉 _wykonuje metodę znalezioną w następnej klasie_

**R — Respects MRO order**  
👉 _zachowuje poprawną kolejność i działa z wielodziedziczeniem_

---

### 🔄 Tłumaczenie jako analogia

#### Analogią filmowa – wersja dopracowana

> Tak jak w filmach możemy odwoływać się do **wydarzeń kanonicznych z poprzednich części serii**, tak w Pythonie, tworząc klasę podrzędną, używamy `super()`, aby **przez obiekt proxy** poszukać odpowiedniej metody **w kolejnej klasie zgodnie z MRO**.
> 
> `super()` nie wybiera „rodzica”, tylko **następną część historii w oficjalnej kolejności (MRO)**.
---

### 🗃 Keyword Connections (powiązania)

- [[MRO]]
    
- [[proxy]]
    
- [[Dziedziczenie (inheritance)]]
     
- [[isinstance]]
    
- [[issubclass]]


---

### 🖼 Rysunek / schemat / diagram ASCII

![[Pasted image 20251216064345.png]]


---

## ✨ Metoda Feynmana (1–2 zdania)

`super()` mówi Pythonowi: „idź do następnej klasy w kolejce”.

---

## ⚠ Typowe błędne wyobrażenie
`super()` nie wywołuje metody — zwraca proxy, które zgodnie z MRO wskazuje, gdzie szukać jej dalej.

Nie powinniśmy ręcznie wywoływać class w objektach -> Ręczne wywołania łamią MRO i są niebezpieczne przy refaktoryzacji.

---

## 📌 Kontrast (X vs Y)

| Cecha | super() | Koncepcja przeciwna |
| ----- | --------- | ------------------- |
|       |           |                     |
|       |           |                     |

---

## 🗂 Fiszki (SRS) #flashcards 

## 🔹 `super()`

**Czym jest `super()` w Pythonie?**  
?  
Obiektem proxy wskazującym kolejną klasę w MRO.

**Po czym się rozpoznaje działanie `super()`?**
?
Po tym, że wywołuje metody zgodnie z MRO, a nie bezpośredniego rodzica.
<!--SR:!2025-12-19,1,230-->

**Kiedy używa się `super()`?**  
?  
Gdy chcemy bezpiecznie wywoływać metody w hierarchii dziedziczenia, także przy wielodziedziczeniu.

---

## 🔹 `isinstance`

**Czym jest `isinstance()`?**
?
Funkcją sprawdzającą, czy obiekt jest instancją danej klasy lub jej podklasy.
<!--SR:!2025-12-21,3,250-->

**Po czym się rozpoznaje `isinstance()`?**  
?  
Po tym, że działa na obiekcie i uwzględnia dziedziczenie.

**Kiedy używa się `isinstance()`?**  
?  
Gdy sprawdzamy typ obiektu w czasie działania programu.

---

## 🔹 `issubclass`

**Czym jest `issubclass()`?**
?
Funkcją sprawdzającą, czy jedna klasa dziedziczy po drugiej.
<!--SR:!2026-01-28,1,210-->

**Po czym się rozpoznaje `issubclass()`?**
?
Po tym, że działa na klasach, a nie na instancjach.
<!--SR:!2025-12-19,1,230-->

**Kiedy używa się `issubclass()`?**  
?  
Gdy sprawdzamy relacje dziedziczenia między klasami.

---

# ➕ NOWE FISZKI (ściśle powiązane z `super()`)

## 🔹 MRO

**Czym jest MRO?**
?
MRO (Method Resolution Order) to kolejność, w jakiej Python przeszukuje klasy w hierarchii dziedziczenia w poszukiwaniu metod i atrybutów.
<!--SR:!2025-12-19,1,230-->

**Po czym się rozpoznaje MRO?**  
?  
Po liście zwracanej przez `Class.__mro__`.

**Kiedy używa się wiedzy o MRO?**  
?  
Przy dziedziczeniu wielokrotnym i pracy z `super()`.

---

## 🔹 proxy

**Czym jest obiekt proxy?**  
?  
Obiektem pośrednim przekazującym wywołania dalej.

**Po czym się rozpoznaje proxy w `super()`?**  
?  
Po tym, że nie zawiera metod, tylko wskazuje gdzie ich szukać.

**Kiedy używa się proxy?**  
?  
Gdy chcemy kontrolować dostęp do innego obiektu lub mechanizmu.

---

## 🔹 shadowing (przesłanianie)

**Czym jest shadowing metod?**  
?  
Sytuacją, w której metoda w podklasie przesłania metodę z nadklasy.

**Po czym się rozpoznaje shadowing?**
?
Po tym, że metoda z klasy nadrzędnej nie jest wywoływana bez `super()`.
<!--SR:!2025-12-19,1,230-->

**Kiedy występuje shadowing?**
?
Gdy klasa definiuje metodę o tej samej nazwie co jej nadklasa.
<!--SR:!2025-12-22,4,270-->

---

## 🔹 cooperative inheritance

**Czym jest cooperative inheritance?**  
?  
Wzorzec dziedziczenia, w którym wszystkie klasy używają `super()`.

**Po czym się je rozpoznaje?**  
?  
Po tym, że każda klasa woła `super()` zamiast konkretnej klasy.

**Kiedy się je stosuje?**  
?  
Przy wielodziedziczeniu, aby zachować pełny łańcuch wywołań.

---

## 🔗 Powiązane notatki