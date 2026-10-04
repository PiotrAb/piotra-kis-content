## Zadania do samodzielnego wykonania

### Zadanie 1
Wykorzystując kod z zajęć, dodaj do aplikacji **ToDo list** następujące funkcjonalności:
    
- możliwość edycji dodanego już taska (może być zrealizowane poprzez routing do odpowiedniego widoku lub poprzez pojawianie się komponentu działajacego jako okno modalne; dane mają się modyfikować w `localStorage` oraz na wyświetlanej liście zadań)
- dodaj do aplikacji dodatkowy widok **Ustawienia**, który będzie pozwalał na zmianę nazwy klucza, pod którym przechowywane są taski w `localStorage`; nazwa klucza ma być oczywiście przechowywana w `localStorage`

Ostatnia, najbardziej aktualna wersja aplikacji z zajęć znajduje się [TUTAJ](https://github.com/IS-UMK/NOFRAP24z-zajecia/tree/master/06.11/to-do-app).

### Zadanie 2
Wykorzystując mechanizmy dostępne w bibliotece Vue zaimplementuj komponent licznika analogiczny do tego z zajęć, który będzie pozwalał zmianę lokalnego licznika (inkrementacja i dekrementacja) oraz globalnego licznika. Nie wykorzystuj w tym celu bibliotek realizujących funkcjonalność store'a (np. Vuex, Pinia)

### Zadanie 3
Wykorzystując kod z zajęć realizujący prostą aplikację ToDo w React, zaimplementuj mechanizm aktualizacji stanu głównego komponentu tak, aby wykorzystywał hook `useReducer` i pozwalał na wykonywanie operacji na tablicy zadań do wykonania. Podstawowe operacje to dodawanie, usuwanie i modyfikacja statusu zdania. 

### Zadanie 4
Wykorzystując dowolny, poznany na zajęciach framework zaimplementuj prosty mechanizm logowania do strony WWW wykorzystujący mechanizm tokenów. Możesz skorzystać z dowolnego gotowego backendu lub z mock'ockowego API (np. [DummyJSON](https://dummyjson.com/docs/auth)) lub po prostu zaimplementować sprawdzanie poprawności pary login-hasło na sztywno w funkcji wykonującej autentykację.

Zaimplementuj prosty navbar, który posiadać będzie pola do wpisania loginu i hasła oraz przycisk 'Zaloguj'. Po zalogowaniu użytkownik ma możliwość wylogowania się, a więc komponent zamienia się na przycisk wylogowania. Zaimplementuj również mechanizm przechowywania tokenu autoryzacyjnego, wykorzystując `localStorage` oraz globalny stan aplikacji - token ma być przechowywany po zamknięciu okna przeglądarki i ma istnieć mechanizm pozwalający na jego odzyskanie po ponownym załadowaniu strony.

W zadaniu możesz wykorzystać dowolną bibliotekę UI.

### Zadanie 5

Wykorzystując dowolną bibliotekę do **zarządzania globalnym stanem aplikacji** zaimplementuj mechanizm przekazywania tokenu w postaci GUIDa pomiędzy komponentami aplikacji. Aplikacja ma pozwalać na wygenerowanie tokenu na głównej stronie, a dostęp do dwóch podstron dozwolony jest wyłącznie w przypadku posiadania tokenu oraz upłynięcia mniej niż 2 minut od czasu jego wygenerowania.   