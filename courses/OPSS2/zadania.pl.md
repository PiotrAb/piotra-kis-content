# Zadania zaliczeniowe do samodzielnego wykonania

## Zadanie 1

Do aplikacji stworzonej w trakcie zajęć, dotyczącej animacji i obsługi zdarzeń klawiatury, dodaj dwie funkcjonalności:

- po kliknięciu na przycisk **z** - uruchom animację ataku, której sprite dostępny jest [TUTAJ](/files/OPSS2/attack1.png)
- po kliknięciu na przycisku **x** - uruchom animację ataku, której sprite dostępny jest [TUTAJ](/files/OPSS2/attack2.png).

Kod źródłowy aplikacji dostępny jest w repozytorium do zajęć - są to odpowiednio katalogi 03.25 oraz 03.27 dla grupy wtorkowej i czwartkowej.

## Zadanie 2

Zaimplementuj tester klawiatury, który będzie pozwalał na sprawdzenie, które klawisze zostały już wciśnięte. Zadbaj o to, aby można było wykryć wciśnięcie kilku klawiszy jednocześnie.

Klawiaturę wygeneruj automatycznie - możesz utworzyć szablon przycisku i go sklonować lub możesz stworzyć funkcję, która wygeneruje każdy z klawiszy z osobna. Komponenty UI związane z klawiszami powinny być generowane przez skrypt.

Dodatkowo postaraj się zaimplementować możliwie jak najmniej kodu związanego ze zdarzeniami. Zwróć uwagę, że kod wywoływany przez naciśnięcie każdego z przycisków klawiatury jest identyczny.

Możesz inspirować się [TĄ](https://www.keyboardtester.com/tester.html) aplikacją.

Ogranicz się do głównych przycisków, które dostępne są w klawiaturach 75%.

## Zadanie 3

W aplikacji ToDo wykonywanej w ramach zajęć zbuduj osobne komponenty, które odpowiadać będą za obsługę elementów **input** oraz **button** na dole ekranu aplikacji (tworzenie nowego zadania) oraz listę zadań do wykonania.

## Zadanie 4

W aplikacji ToDo z zajęć dodaj funkcjonalność edycji zadania. Zaimplementuj możliwość zmiany nazwy zadania i jego opisu, dodatkowo zadbaj, aby aktualizowana była data ostatniej modyfikacji wpisu. W tym celu wykorzystaj komponent [Modal](https://getbootstrap.com/docs/5.3/components/modal/) biblioteki Bootstrap, który pokazywać się będzie po kliknięciu na ikonę edycji przy konkretnym zadaniu. Modyfikacja zachodzić ma zarówno w interfejsie graficznym, jak i w danych aplikacji (zarówno aktualnym stanie zmiennych jak i wartościach przechowywanych w Local Storage).

## Zadanie 5

Zaimplementuj moduł JS, frontendowy, backendowy lub uniwersalny (od tego zależeć będzie wybór CommonJS czy ModularJS), który pozwoli na obsługę podstawowych zapytań HTTP. Zaimplementuj funkcje pozwalające na wysyłanie zapytań pod dowolny adres URL, budujące query-stringa pozwalającego na wysyłanie zapytań pod konkretne ścieżki i z konkretnym zestawem parametrów (zapytania GET). W przypadku zapytań POST, parametry mają być wysyłane w ciele zapytania. Zadbaj, aby parametry wejściowe funkcji były możliwie jak najbardziej atomowe (np. osobno adres URL, ścieżka, parametry w postaci słowników klucz-wartość lub tablic). W zadaniu oceniana będzie zarówno poprawność implementacji jak i sensowność skonstruowanego modułu (podział parametrów itp.).

Twój kod przejdzie code-review, tak więc zawsze będzie istniała możliwość odniesienia się do uwag i wprowadzenia potrzebnych poprawek przed finalną oceną kodu.

# Projekt zaliczeniowy

Wykorzystując publicznie dostępne API pozwalające na wykonywanie podstawowych operacji na produktach ([products](https://dummyjson.com/docs/products)) oraz koszyku sklepowym ([carts](https://dummyjson.com/docs/carts)), zaimplementuj aplikację sklepu internetowego.

Funkcjonalności:

- prezentowanie wszystkich produktów
- prezentowanie produktów z podziałem na kategorie
- możliwość dokonywania zakupów (koszyk zakupowy zbierający wybrane produkty i podliczający całkowitą kwotę do zapłaty)
- UI ma być kompatybilne zarówno z urządzeniami desktopowymi jak i mobilnymi (RWD)
- możliwość zalogowania się do sklepu i przejrzenia swojego koszyka (może być przechowany w _localStorage_, logowanie ma być jedynie wykorzystaniem [API Auth](https://dummyjson.com/docs/auth) - informację o logowaniu można przechować na czas sesji lub skorzystać z mechanizmu ciasteczek)
- aplikacja ma się współcześnie prezentować - można w tym celu wykorzystać gotowe biblioteki służące do budowy UI aplikacji internetowych - pozwolą Ci one również w prosty sposób zadbać o responsywność

Z projektu możesz otrzymać **50 pkt.** Ocenie podlegać będzie każda z funkcjonalności, po **5 pkt.** za każdą z nich (łącznie 30 pkt.) oraz poprawność implementacji, za którą otrzymać można **20pkt.**

Projekt ma być skonfigurowany tak, aby wydanie poleceń:

```bash
npm install
npm run dev
```

pozwalało na uruchomienie projektu. Cały kod potrzebny do uruchomienia ma znaleźć się w Twoim repozytorium do zajęć.

**UWAGA!!!** Nie będą sprawdzane projekty, które nie uruchamiają się! Błędy w projektach można będzie naprawić, a wszelkie nieścisłości przedyskutować - sprawdzę wtedy projekt raz jeszcze i wystawię nową punktację. Wszelkie podejrzenia związane z nadmiernym wykorzystaniem narzędzi AI wspomagających pracę programisty wyjaśniane będą indywidualnie, w postaci rozmowy na temat zastosowanych w projekcie rozwiązań.
