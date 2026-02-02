---
sr-due: 2026-02-03
sr-interval: 4
sr-ease: 270
---

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
try:
    x = int(input("Podaj liczbę: "))
    result = 10 / x
    print("Wynik:", result)

except ZeroDivisionError:
    print("❌ Nie można dzielić przez zero")

except ValueError:
    print("❌ To nie jest liczba")

print("Program działa dalej 🚀")
```

---

## 🧩 Mnemotechniki

### 🅰 Akronim

**Akronim:** T.E.E.F.

**Rozwinięcie:**

**T** – **Try**  
→ wykonaj kod

**E** – **Except**  
→ jeśli coś wybuchnie 💥, przechwyć błąd

**E** – **Else**  
→ wykonaj, **gdy NIE było błędu**

**F** – **Finally**  
→ wykonaj **zawsze** (sprzątanie, zamykanie zasobów)

---

### 🔄 Tłumaczenie jako analogia

**Analogia:** 
**Try** to wejście w solówkę – normalnie grasz i sprawdzasz, czy plan zadziała.  
Jeśli wygrasz i nic się nie wysypie, przechodzisz do **else** – wszystko się udało, dostajesz nagrodę (np. buziaka od dziewczyny).  
Jeśli jednak coś pójdzie nie tak i przegrasz solówkę, wchodzi **except** – sytuacja zostaje przechwycona i opanowana.  
**Finally** wydarza się zawsze, niezależnie od wyniku – przychodzi nauczycielka i rozlicza całą akcję za bójkę.

---

### 🗃 Keyword Connections (powiązania)

- [[ZeroDivisionError]]
- [[ValueError]]
- [[SyntaxError]]
- [[TypeError]]
- [[TraceBack]]

---

### 🖼 Rysunek / schemat / diagram ASCII

![[Pasted image 20260129203523.png]]

---

## ✨ Metoda Feynmana (1–2 zdania)

Łapanie wyjątków w Pythonie polega na tym, że gdy coś pójdzie nie tak podczas działania programu, **kod nie wywraca się**, tylko przechodzimy do wcześniej przygotowanego planu awaryjnego. Dzięki temu program może **działać dalej w kontrolowany sposób**, nawet jeśli wydarzy się błąd.

---

## ⚠ Typowe błędne wyobrażenie

1️⃣ `except Exception` ≠ łapie wszystko ❌  
2️⃣ `try/except` ≠ „żeby program się nie wywalił” ❌  
3️⃣ Wyjątki ≠ normalny mechanizm sterowania logiką ❌

Wyjątki w Pythonie służą do obsługi nieoczekiwanych, ale przewidywalnych błędów, a nie do sterowania normalnym przepływem programu.

---

## 📌 Kontrast (X vs Y)

| Cecha      | Try                                                      | If else                        |
| ---------- | -------------------------------------------------------- | ------------------------------ |
| Prędkość   | działa wolniej                                           | działa szybciej                |
| Kiedy użyć | gdy coś **może się realnie wysypać** (IO, parsing, sieć) | gdy coś jest **przewidywalne** |

---

## 🗂 Fiszki (SRS) #flashcards #Wyjątki

Czy `try` sprawdza cały kod, a dopiero potem łapie błąd?
?
Nie. Kod w `try` wykonuje się normalnie i **zatrzymuje się dokładnie w miejscu wyjątku**.
<!--SR:!2026-02-13,11,270-->

---

Czy kod po błędzie w `try` nadal się wykona?
?
Nie. **Wyjątek przerywa blok `try`** i Python przechodzi do `except`.
<!--SR:!2026-02-03,4,270-->

---

Czy `except Exception` łapie każdy możliwy błąd?
?
Nie. **Nie łapie m.in. `SystemExit`, `KeyboardInterrupt`, `GeneratorExit`**.
<!--SR:!2026-02-10,8,250-->

---

Czy `try/except` służy głównie do tego, żeby program się nie wywalił?
?
Nie. Służy do **kontrolowanej obsługi oczekiwanych błędów**, a nie do ratowania wszystkiego.
<!--SR:!2026-02-12,10,270-->

---

Kiedy wykona się blok `else`?
?
Tylko wtedy, gdy **w `try` nie wystąpił żaden wyjątek**.
<!--SR:!2026-02-03,4,270-->

---

Czy `finally` wykona się zawsze?
?
Tak. **Zawsze**, niezależnie od tego, czy był wyjątek czy nie.
<!--SR:!2026-02-14,12,270-->

---

Czy wyjątki powinny sterować normalnym flow programu?
?
Nie. **Flow sterujemy `if`**, wyjątki są na sytuacje wyjątkowe.
<!--SR:!2026-02-05,3,230-->

---

Czy wyjątki są „wolne”?
?
Tak, są droższe niż `if`, ale **poprawność kodu jest ważniejsza niż mikro-wydajność**.
<!--SR:!2026-02-12,10,270-->

---

Kiedy użyć `raise` zamiast `print` lub `return`?
?
Gdy chcę **świadomie przerwać działanie i zakomunikować błąd wyżej**.
<!--SR:!2026-02-03,1,190-->

---

Czy dobrze napisany `except` ukrywa błąd?
?
Nie. **Dobrze napisany `except` ujawnia błąd w kontrolowany sposób**.
<!--SR:!2026-02-04,2,210-->



---

AttributeError
?
obiekt istnieje, ale nie jest taki, jak myślałem
<!--SR:!2026-02-06,4,278-->

---

TypeError
?
operacja nie ma sensu dla tego typu
<!--SR:!2026-02-03,1,238-->

---

ValueError
?
typ jest poprawny, ale wartość jest zła
<!--SR:!2026-02-03,1,238-->

---

LookupError
?
szukałem elementu, ale go nie znalazłem
<!--SR:!2026-02-05,3,258-->

---

KeyError
?
nie ma takiego klucza w dict
<!--SR:!2026-02-05,3,258-->

---

IndexError
?
nie ma takiego indeksu w sekwencji
<!--SR:!2026-02-06,4,278-->

---

AssertionError
?
założenie programisty okazało się fałszywe
<!--SR:!2026-02-06,4,278-->

---

OSError
?
kod jest OK, ale świat zewnętrzny nie działa
<!--SR:!2026-02-03,1,238-->

---

Exception
?
coś poszło nie tak w logice programu
<!--SR:!2026-02-05,3,258-->

---

Kolejność except w try
?
Python sprawdza except od góry do dołu i wykona pierwszy pasujący
<!--SR:!2026-02-06,4,278-->

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
