---
sr-due: 2026-02-03
sr-interval: 3
sr-ease: 253
---


aliases: []  
tags: [theory, cs, programming]  
sr-due: true
graph: false

#review 

---

## 🧠 Co to jest?

**Asercja (`assert`)** to **instrukcja języka Python**, która służy do **sprawdzania założeń (invariantów) w kodzie**.  
Jeśli warunek jest fałszywy, Python **automatycznie zgłasza `AssertionError`**.

Asercje **nie służą do obsługi błędów biznesowych**, tylko do upewnienia się, że program działa zgodnie z oczekiwaniami programisty (debug / sanity-check).

## 🔧 Jak to działa?

- gdy warunek jest `True` → nic się nie dzieje
    
- gdy warunek jest `False` → `AssertionError` z podanym komunikatem
- 
## 🧪 Przykład

```python
assert x > 0, "x musi być dodatnie"
```



---

## 🧩 Mnemotechniki

### 🅰 Akronim

### **ASS**

**A** – _Assumption_  
**S** – _Sanity check_  
**S** – _Stripped in -O_

---

### 🔄 Tłumaczenie jako analogia

**Analogia:** 
**Assertion w Pythonie** to jak **zakład z kolegą**: mówisz „jestem pewien, że w tym miejscu programu warunek jest spełniony”. Jeśli masz rację, kod wykonuje się dalej i nikt do tego nie wraca; jeśli się mylisz, Python zgłasza `AssertionError` — zakład przegrany — co oznacza, że zawiodły Twoje założenia jako programisty, a nie logika biznesowa czy dane od użytkownika.

---

### 🗃 Keyword Connections (powiązania)

[[raise]]
[[assert]]


---

### 🖼 Rysunek / schemat / diagram ASCII

![[Pasted image 20260130075119.png]]
---

## ✨ Metoda Feynmana (1–2 zdania)
**Assertion w Pythonie** to mechanizm, którym programista sprawdza własne założenie o stanie programu.  
Jeśli założenie jest prawdziwe — kod działa dalej, a jeśli jest fałszywe — Python zgłasza `AssertionError`, sygnalizując błąd w myśleniu programisty, nie w danych wejściowych.

---

## ⚠ Typowe błędne wyobrażenie

---

## 📌 Kontrast (X vs Y)

| Cecha                                                    | Assert | Raise |
| -------------------------------------------------------- | ------ | ----- |
| Zawsze wykonuje się w każdym trybie uruchomienia Pythona | ❌      | ✅     |
| Służy do walidacji danych wejściowych od użytkownika     | ❌      | ✅     |
| Sygnalizuje błąd w założeniach programisty               | ✅      | ❌     |
| Może rzucać różne typy wyjątków                          | ❌      | ✅     |
| Jest elementem logiki biznesowej programu                | ❌      | ✅     |

---

## 🗂 Fiszki (SRS) #flashcards #Wyjątki 

**Czy `assert` zawsze wykona się w Pythonie?**
?
Nie — w trybie `-O` (optymalizacja) asercje są ignorowane.
<!--SR:!2026-02-04,4,270-->

---

**Czy `assert` służy do obsługi błędów użytkownika?**
?
Nie — `assert` sprawdza założenia programisty, nie dane wejściowe.
<!--SR:!2026-02-03,3,250-->

---

**Co oznacza `AssertionError` mentalnie?**
?
Programista założył coś nieprawdziwego o stanie programu.
<!--SR:!2026-02-05,3,250-->

---

**Kiedy powinienem użyć `raise`, a nie `assert`?**
?
Gdy warunek musi być sprawdzany zawsze, także na produkcji.
<!--SR:!2026-02-04,2,230-->

---

**Uzupełnij zdanie:**
`assert` sprawdza ___, a `raise` obsługuje ___ programu.
?
Założenia programisty, logikę/błędy programu.
<!--SR:!2026-02-03,3,250-->

---

## 🔗 Powiązane notatki

[[Jak obsługiwać wyjątki]]

---
Czym jest asercja? 
Etymologia słowa asercja?
Z jakiego słówka skorzystamy aby wywołać wyjątek? 
Co robi raise w pythonie? 
Jak raise współpracuje z Try Except?
Czym jest assert w pythonie? < z etymologi jest jest to coś na zasadzie zapewnienia prawdy 
Jak możemy dodać własny komunikat do assertion? 
Jaki typ błędu zwraca assertion i dlaczego musimy na niego uważać? 

