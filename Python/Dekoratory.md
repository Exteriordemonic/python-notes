aliases: []  
tags: [theory, cs, programming]  
sr-due: true
graph: false

---

## 🧠 Co to jest?
Dekorator to funkcja, która przyjmuje inną funkcję jako argument, „opakowuje” ją i zwraca nową wersję z rozszerzonym zachowaniem — bez zmieniania oryginalnego kodu. Mechanizm ten jest inspirowany wzorcem projektowym _Dekorator_, który polega na dynamicznym dodawaniu funkcjonalności.

To _dodawanie zachowania przed lub po_ działaniu funkcji.

## 🔧 Jak to działa?
1. **Piszesz funkcję, która przyjmuje funkcję**
    
2. **Wewnątrz tworzysz funkcję „opakowującą”**
    
3. **Zwracasz ją**
    
4. **Używasz `@nazwa_dekoratora` nad funkcją, którą chcesz udekorować**

## 🧪 Przykład

```python
def dekorator(func):
    def wrapper():
        print("Zanim funkcja się wykona")
        result = func()
        print("Po wykonaniu funkcji")
        return result
    return wrapper

@dekorator
def hello():
    print("Hello!")

hello()

```

---

## 🧩 Mnemotechniki

### 🅰 Akronim

**Akronim:** O-O-Z-W

**Rozwinięcie:**

- **O** – **Otrzymuje funkcję**  
- **O** – **Opakowuje ją**  
- **Z** – **Zwraca nową wersję**  
- **W** – **Wzorzec projektowy (inspiracja)**

---

### 🔄 Tłumaczenie jako analogia

**Analogia:**
**Hot-dog z Żabki jako system dekoratorów**

#### **Parówka → funkcja (oryginalna logika)**

To jest “goła” funkcja.  
Może działać sama — parówka to parówka.

#### **Bułka → dekorator opakowujący**

Bułka:

- **nie zmienia parówki**,
    
- **opakowuje ją**,
    
- dodaje „zachowanie”: trzyma wszystko razem, nadaje formę, umożliwia zjedzenie.
    

W Pythonie bułka = funkcja wrapper.

#### **Sos → kolejny dekorator, który rozszerza zachowanie**

Do hot-doga możesz dodać:

- ketchup,
    
- musztardę,
    
- jalapeno,
    
- majonez truflowy, jak ktoś ma fantazję 😂
    

Każdy sos:

- **nie zmienia parówki**,
    
- tylko **dodaje nową warstwę działania** (smak → nowe zachowanie).
    

To jest dokładnie to, co robi dekorator w Pythonie.

---

### 🗃 Keyword Connections (powiązania)

- [[meta function]]
    
- [[syntactic sugar]]
    
- [[design patterns]]
    

---

### 🖼 Rysunek / schemat / diagram ASCII


![[Pasted image 20251202193057.png]]

---

## ✨ Metoda Feynmana (1–2 zdania)
Dekorator to taki „wrapper” dla Twojej funkcji — dodaje nowe zachowanie bez ingerowania w jej oryginalny kod.  
To jak w Żabce: masz parówkę (funkcję), do której dokładane są kolejne warstwy — bułka i sosy — pełniące rolę dekoratorów.

---

## ⚠ Typowe błędne wyobrażenie

---

## 📌 Kontrast (X vs Y)

| Cecha | Dekoratory | Koncepcja przeciwna |
| ----- | --------- | ------------------- |
|       |           |                     |
|       |           |                     |

---

## 🗂 Fiszki (SRS) #flashcards 



---

## 🔗 Powiązane notatki