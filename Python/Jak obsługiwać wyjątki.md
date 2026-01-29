aliases: []  
tags: [theory, cs, programming]  
sr-due: true
graph: false

#review 

---

## 🧠 Co to jest?
**Obsługa wyjątków (exceptions) w Pythonie** to mechanizm, który  
**pozwala przechwytywać i obsługiwać błędy występujące w czasie działania programu (runtime), zamiast przerywać jego wykonanie**.

## 🔧 Jak to działa?

Python dzięki blokowi `try` wie, który fragment kodu ma wykonać „w trybie testowym”.  
Jeśli kod wykona się bez błędu, program może **bezpiecznie kontynuować działanie**.  
Jeżeli natomiast podczas wykonania wystąpi wyjątek, Python **przerywa blok `try`** i przekazuje sterowanie do odpowiedniego bloku `except`, gdzie możemy ten błąd **przechwycić i obsłużyć**.
## 🧪 Przykład

```python
try 
```

---

## 🧩 Mnemotechniki

### 🅰 Akronim

**Akronim:**

**Rozwinięcie:**

- A —
    
- B —
    
- C —
    

---

### 🔄 Tłumaczenie jako analogia

**Analogia:**

---

### 🗃 Keyword Connections (powiązania)

- [[ZeroDivisionError]]
- [[ValueError]]
- [[SyntaxError]]
- [[TypeError]]
- [[TraceBack]]

---

### 🖼 Rysunek / schemat / diagram ASCII

```
[Input] → [Processing] → [Output]
```

---

## ✨ Metoda Feynmana (1–2 zdania)

---

## ⚠ Typowe błędne wyobrażenie

---

## 📌 Kontrast (X vs Y)

| Cecha | Jak obsługiwać wyjątki | Koncepcja przeciwna |
| ----- | --------- | ------------------- |
|       |           |                     |
|       |           |                     |

---

## 🗂 Fiszki (SRS) #flashcards 



---

## 🔗 Powiązane notatki

---

Jakie typy wyjątków mamy? 
Po co ich używać w kodzie? 
Jak wygląda składnia wyjątków, z czego się składają? 
Kiedy przechwycić wyjątek a kiedy pozwolić na error dla programu?
Czy except wykona się jeśli try nie złapie błędu? 
Czy try expect ratuje nas przed błędami składni?
Jak w expect możemy wyłapać tylko dany typ błędu? 
Jak nazywa się ścieżka błędu przez który została wykonana? 
Co określa TraceBack? 
Jak w expect przechwycić wszystkie typy błędów? 
Czy as po Exception jest wymagane? 
Czy możemy mieć wiele Expect w jednym try? 
Jak określić działanie w try jeśli żaden błąd nie został wykonany?
jak określić kod który wykona się niezależnie od tego czy Try przechwyci Error 
Czy wyłapywanie Exception bez konkretnego typu jest dobrą praktyką?
Kiedy powinniśmy używać ifów do sprawdzania typów a kiedy try? 
Jak wygląda styl kodu try? Czy wszystko musi się w nim znajdować?
Kiedy występuje Compile type error?
Kiedy występuje Run-Time Error?
Kiedy występuje Logical Error?
