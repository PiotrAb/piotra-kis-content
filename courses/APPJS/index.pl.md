# Wiadomości ogólne

Laboratoria z Multiplatoformowych aplikacji w języku JavaScrip odbywają się w czwartki w godz. 18:00 - 19:30 w pracowni PK2.

# Repozytorium do zajęć

Każdy ze Studentów zapisany na zajęcia w systemie USOS otrzymał link do serwisu GitHub Classroom, w którym podłączył swoje repozytorium w serwisie GitHub. Studenci mają swoje prywatne repozytoria, w których przechowywać mogą kody z zajęć, rozwiązania zadań i projekt zaliczeniowy.

Dodatkowo, każda z osób, które dopisały się w GitHub Classroom, ma dostęp do repozytorium z materiałami do zajęć:

[![Static Badge](https://img.shields.io/badge/GitHub_AppJS_25L-black?logo=GitHub&style=flat&labelColor=black&color=white)](https://github.com/IS-UMK/APPJS_25L_zajecia_PiotrA)

Brak dostępu do repozytorium proszę zgłaszać mailowo, weryfikując najpierw, czy użytkownik ma swoje prywatne repo do kursu. W treści wiadomości proszę załączyć nazwę użytkownika w serwisie GitHub.

# Zasady zaliczenia przedmiotu

Na zaliczenie przedmiotu należy wykonać projekt/zadania, które przedstawione są poniżej. Studenci, którzy chcą otrzymać ocenę wyższą niż 3.5 zobowiązani są do przedstawienia kompletnego, działającego projektu, który implementuje przedstawione poniżej funkcjonalności. Osoby, które chcą uzyskać ocenę 3.0 lub 3.5 - mogą wykonać zadania w postaci osobnych aplikacji, nie połączonych ze sobą.

Zadania mogą być wykonane z wykorzystaniem biblioteki Electron.js lub w postaci aplikacji PWA. Aplikacja Electron.js ma działać w systemie operacyjnym Windows/Linux lub macOS, a aplikacja PWA ma poprawnie działać w przeglądarce internetowej Chrome (lub dowolnej innej opartej na silniku Chromium). W ramach zadania wykorzystać można dowolne biblioteki i frameworki zgodne z wykorzystaną technologią. Zachęcam również do korzystania z bibliotek do budowy UI, które znacznie przyspieszą pracę nad projektem.

- wykorzystanie dowolnego API, które dostępnie jest publicznie (otwartego lub dostępnego po zalogowaniu się celem uzyskania odpowiedniego klucza) - z aplikacji ma być wysyłane zapytanie do API, ma być odpowiednio interpretowane, a jego wynik ma być wyświetlany użytkownikowi

- przechowywanie stanu aplikacji pomiędzy ponownymi uruchomieniami - może być zrealizowane w postaci odpowiedniej implementacji cache'a

- implementacja nawigacji pomiędzy minimum trzema różnymi widokami aplikacji (przełączanie stron lub okien aplikacji)

- w aplikacji ma znajdować się przynajmniej jeden skrypt w języku JavaScript, który wykonywany będzie po stronie urządzenia klienckiego i ma on operować na danych wprowadzonych przez użytkownika (np. ma wykorzystywać lokalizację urządzenia, obsługiwać kontrolkę, której wartość ustala użytkownik itp.)

- implementacja logowania do aplikacji - można wykorzystać w tym celu API (np. [DummyJSON - Auth](https://dummyjson.com/docs/auth)) - logowanie ma dawać dostęp do jakiegoś zasobu, który nie jest widoczny przed logowaniem; stan logowania powinien być przechowywany pomiędzy uruchomieniami aplikacji

UWAGA! Zaimplementowana aplikacja ma działać poprawnie w trybie off-line. Pierwsze uruchomienie może korzystać z sieci, ale drugie i każde kolejne ma w przypadku braku dostępu do Internetu korzystać z danych zapisanych przez aplikację.

Przykładowe tematy, o które oprzeć można powyższe założenia:

- aplikacja pogodowa korzystajaca z dowolnego API (np. [OpenMeteo](https://open-meteo.com/))
- aplikacja przechowująca listę zakupów
- prosta aplikacja sklepu internetowego korzystająca z API (np. [DummyJSON - Products](https://dummyjson.com/docs/products))
- aplikacja wyświetlająca cytat na każdy dzień oraz dająca możliwość wylosowania dowolnego cytatu (np. [DummyJSON - Quotes](https://dummyjson.com/docs/quotes))
- planer studencki (dodawanie wpisów o zajęciach, kolokwiach, egzaminach etc.) synchronizowany z dowolnym kalendarzem lub przechowujący dane w postaci plików (np. JSON)
- prosta gra, np. kółko i krzyżyk, wisielec etc. (wykorzystanie API ograniczyć można tutaj do logowania)

Masz pomysł na swój własny temat projektu/zadania? Możesz go zrealizować, ale postaraj się, aby zawierał on implementację przedstawionych wymagań.

# Terminarz oddawania zadań

- termin oddawania zadań: **31 sierpnia 2025r., godz. 23:59:59**
