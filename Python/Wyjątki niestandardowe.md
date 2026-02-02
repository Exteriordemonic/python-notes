---
sr-due: 2026-02-04
sr-interval: 4
sr-ease: 271
---


aliases: []  
tags: [theory, cs, programming]  
sr-due: true
graph: false

#review 

---

## 🧠 Co to jest?

**Wyjątki niestandardowe** to własne klasy wyjątków, które tworzymy samodzielnie, aby **precyzyjnie opisywać konkretne błędy w naszym programie**, zamiast używać ogólnych `Exception` lub wbudowanych wyjątków, które są zbyt ogólne.

- lepiej **komunikują intencję błędu** (czytając kod od razu wiesz _co_ poszło nie tak)
    
- pozwalają **łapać bardzo konkretne sytuacje**
    
- oddzielają **logikę domenową** od technicznych błędów Pythona

Custom exception = nazwany błąd  świata biznesowego / logiki

## 🔧 Jak to działa?

 **1. Tworzysz klasę wyjątku**

- Dziedziczy po `Exception` (albo innym wyjątku bazowym)
```python
class InvalidAgeError(Exception):
    pass

```

 **2. Rzucasz wyjątek w konkretnym miejscu**

- Gdy Twoje założenie / reguła domenowa jest złamana
```python
if age < 0:
    raise InvalidAgeError("Age cannot be negative")

```

Custom exception = sygnał alarmowy z własną etykietą

## 🧪 Przykład

```python
class InvalidAgeError(Exception):
    pass

def set_age(age):
    if age < 0:
        raise InvalidAgeError("Age cannot be negative")

```
Tu **nie chodzi o błąd Pythona**, tylko o **błąd domeny** („wiek nie może być ujemny”).


---

## 🧩 Mnemotechniki

---

### 🔄 Tłumaczenie jako analogia

**Analogia:** Custom Expection jest czymś w rodzaju dodawania własnych zasad do gry, np gracie w koszykówkę, ale dodajecie że można zrobić tylko 3 kozły, jest to wasza zasada, normalnie w koszykówce nie istnieje więc tworzycie własny error 

```python
class TooManyDribblesError(Exception):
    """You dribbled too many times"""
    

dribbles = 4

if dribbles > 3:
    raise TooManyDribblesError("You can only dribble 3 times")
```

---

### 🗃 Keyword Connections (powiązania)

- [[raise]]
    
- [[Exception]]
    

---

### 🖼 Rysunek / schemat / diagram ASCII

![[Pasted image 20260130204225.png]]
---

## ✨ Metoda Feynmana (1–2 zdania)
**Wyjątek niestandardowy** to własna zasada programu, która mówi: _jeśli ta konkretna reguła zostanie złamana, program natychmiast się zatrzyma i dokładnie powie, co poszło nie tak_.

---

## ⚠ Typowe błędne wyobrażenie

**Myślałem, że** `raise` działa podobnie do `return`, tylko zamiast wartości zwraca błąd i kończy program lub blok `try`.

**Gdzie tak naprawdę** `raise` nie zwraca nic i nie działa lokalnie — przerywa wykonanie i propaguje wyjątek w górę stosu wywołań, aż zostanie złapany albo zakończy program.

**Myślałem, że** `raise MyError` i `raise MyError()` robią dokładnie to samo.

**Gdzie tak naprawdę** `raise MyError` polega na tym, że Python sam tworzy instancję wyjątku bez argumentów, a `raise MyError()` to jawne stworzenie obiektu — różnica ma znaczenie, gdy wyjątek przyjmuje dane.

**Myślałem, że** użycie `raise` automatycznie kończy działanie programu.

**Gdzie tak naprawdę** program kończy się **dopiero wtedy**, gdy wyjątek nie zostanie nigdzie obsłużony.

---

## 📌 Kontrast (X vs Y)

| Cecha | Wyjątki niestandardowe | Koncepcja przeciwna |
| ----- | ---------------------- | ------------------- |
|       |                        |                     |
|       |                        |                     |

---

## 🗂 Fiszki (SRS) #flashcards  #Wyjątki 

**Czy `raise` działa jak `return`?**
?
Nie. `raise` nie zwraca wartości — przerywa flow i propaguje wyjątek w górę stosu wywołań.
<!--SR:!2026-02-03,3,271-->

---

**Czy `raise MyError` i `raise MyError()` to to samo?**
?
Nie. `raise MyError` tworzy instancję bez argumentów, a `raise MyError()` tworzy obiekt jawnie — różnica ma znaczenie przy danych w wyjątku.
<!--SR:!2026-02-03,3,271-->

---

**Czy Python rozpoznaje wyjątek po `__str__`?**
?
Nie. Python rozpoznaje wyjątek po dziedziczeniu po `BaseException`, a `__str__` służy tylko do komunikatu.
<!--SR:!2026-02-04,4,291-->

---

**Czy `except Exception` łapie custom exception?**
?
Tak. Każdy wyjątek dziedziczący po `Exception` zostanie złapany przez `except Exception`.
<!--SR:!2026-02-04,4,291-->

---

**Czy `raise` zawsze kończy program?**
?
Nie. Program kończy się tylko wtedy, gdy wyjątek nie zostanie nigdzie obsłużony.
<!--SR:!2026-02-04,4,291-->

---

**Czy custom exception służy tylko do ładnych komunikatów?**
?
Nie. Służy do precyzyjnego sygnalizowania złamania reguł domenowych i kontroli flow.
<!--SR:!2026-02-03,1,231-->

---

**Czy wyjątek powinien zawierać logikę walidacji?**
?
To zależy. Może, jeśli reguła jest ściśle związana z tym jednym wyjątkiem, ale często lepiej trzymać walidację poza nim.
<!--SR:!2026-02-05,3,251-->

---

**Czy wyjątki są „złe”, bo są wolniejsze od `if`?**
?
Nie. Są wolniejsze, ale poprawność, czytelność i semantyka domenowa są ważniejsze niż mikrooptymalizacja.
<!--SR:!2026-02-03,3,271-->

---

## 🔗 Powiązane notatki


---
Czym są wyjątki niestandardowe?
Z czego tworzymy wyjątki niestandardowe? 
Kiedy używać Wyjątków niestandardowych? 

[[Jak obsługiwać wyjątki]]
[[Wywoływanie i asercja wyjątków]]