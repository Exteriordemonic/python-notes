aliases: []  
tags: [theory, cs, programming]  
sr-due: true
graph: false

#review 

---

## 🧠 Co to jest?

**Praca z plikami w Pythonie** to mechanizm umożliwiający **otwieranie, odczyt, zapis i modyfikację danych w plikach** przy użyciu funkcji `open(path, mode)`, gdzie **tryb otwarcia określa rodzaj operacji (czytanie, pisanie, dopisywanie, tworzenie) oraz typ pliku (tekstowy lub binarny)**, a opcjonalny `+` pozwala na jednoczesny odczyt i zapis.

`+` pozwala na **jednoczesny odczyt i zapis**, bez zmiany podstawowego zachowania trybu (np. nadpisywania, dopisywania czy warunku istnienia pliku).

## 🔧 Jak to działa?

Python otwiera plik jako strumień danych, a tryb określa, jak program może z tym strumieniem pracować.

## 🧪 Przykład

```python
# zapis do pliku
file = open("example.txt", "w")
file.write("Hello, Python!")
file.close()

# odczyt z pliku
file = open("example.txt", "r")
content = file.read()
file.close()

print(content)
```

---

## 🧩 Mnemotechniki

### 🅰 Akronim

**Akronim:** WRAX

**Rozwinięcie:**

W - Write
R - Read
A - Append
X - Write ale tylko jak nie istnieje 

---

### 🔄 Tłumaczenie jako analogia

**Analogia:**
Narzędzie do pracy z plikami w różnym trybie 

---

### 🗃 Keyword Connections (powiązania)

- [[open]]
    
- [[close]]
    
- [[write]]
    
-  [[seek]]
	  
- [[tell]]

---

### 🖼 Rysunek / schemat / diagram ASCII

![[Pasted image 20260202164313.png]]

---

## ✨ Metoda Feynmana (1–2 zdania)

To narzędzie do pracy z plikami, decyduje co otwieramy oraz w jakim trybie. 

---

## ⚠ Typowe błędne wyobrażenie

f.write() pisze zawsze w tym samym miejscu tak na prawdę piszę w miejscu kursora 
f.read() tak samo od kursora do końca

---

## 📌 Kontrast (X vs Y)

|Cecha|default|+|
|---|---|---|
|w|Pozwala na zapis|Pozwala na zapis oraz odczyt|
|r|Pozwala na odczyt|Pozwala na odczyt oraz zapis|
|a|Pozwala na dopisywanie|Pozwala na dopisywanie oraz odczyt|
|x|Tworzy nowy plik i zapisuje|Tworzy nowy plik, zapisuje oraz odczytuje|

---

## 🗂 Fiszki (SRS) #flashcards #pliki

### 

open()  
?  
tworzy połączenie między programem a plikiem, a tryb określa uprawnienia

---

Tryb domyślny  
?  
r — tylko odczyt

---

w  
?  
zapisuje dane i czyści plik przed zapisem

---

w+  
?  
zapis oraz odczyt, ale plik jest czyszczony na starcie

---

r  
?  
odczyt danych z istniejącego pliku

---

r+  
?  
odczyt i zapis bez czyszczenia pliku

---

a  
?  
dopisywanie danych na końcu pliku

---

a+  
?  
dopisywanie oraz odczyt, kursor startuje na końcu

---

x  
?  
tworzy nowy plik i nie pozwala nadpisać istniejącego

---

x+  
?  
tworzy nowy plik oraz pozwala na zapis i odczyt

---

?  
rozszerza tryb bazowy o brakujące uprawnienia

---

t  
?  
tryb tekstowy, domyślny — pracujemy na str

---

b  
?  
tryb binarny — pracujemy na bytes

---

write()  
?  
zapisuje dane w aktualnej pozycji kursora

---

read()  
?  
czyta dane od aktualnej pozycji kursora do końca pliku

---

seek()  
?  
przesuwa kursor w pliku

---

tell()  
?  
zwraca aktualną pozycję kursora

---



## 🔗 Powiązane notatki
[Files](https://www.programiz.com/python-programming/file-operation)

[File Handling](https://pynative.com/python/file-handling/)

[Files General Concepts Opening CLosing a File](https://www.bestprog.net/uk/2020/04/22/python-files-general-concepts-opening-closing-a-file-functions-open-close-ua/)

[File Handling Modes](https://tutorial.eyehunts.com/python/python-file-modes-open-write-append-r-r-w-w-x-etc/)

[File Handling Examples](https://www.softwaretestinghelp.com/python/python-file-reading-writing/)

[Context manager](https://book.pythontips.com/en/latest/context_managers.html)

---

Jak otworzyć plik w pythonie?
Jak zamknąć plik?
Jak czytać rzeczy z pliku?
Jakie tryby mamy dostępne do pracy z plikiem?
Jaki jest domyślny tryb przy otwieraniu plików?
Jakiego trybu użyjesz do odczytu? r / default
jakiego trybu użyjesz do zapisu? w / wipe & write
jakiego trybu użyjesz do dopisywania? a / add at the end
jakiego trybu użyjesz, kiedy potrzebujesz stworzyć nowy plik, ale nie chcesz nigdy go nadpisywać?x
jak w Pythonie rozszerzyć uprawnienia do czytania plików? 


