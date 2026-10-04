## Laboratorium

Laboratoria z przedmiotu Programowanie Serwisów Web odbywają się w piątki w godzinach 18:00 - 19:30 w formie zdalnej synchronicznej/asynchronicznej.

## Zaliczenie zajęć

Zaliczenie zajęć odbywa się na podstawie wykonanych zadań (projekt podzielony na kilka etapów). Kod opublikowany ma zostać przez Studenta na jego prywatnym repozytorium do zajęć. Kody podlegać będą code-review, każda z części będzie punktowana.

Z pierwszej części zajęć dotyczącej technologii związanych z JS/TS, uzyskać będzie można 50pkt., które stanowić będą 50% wkładu do oceny końcowej.

Zadanie projektowe powinno zostać wykonane do końca maja 2025r..

## Zadanie

Zadanie polega na stworzeniu części backendowej i frontendowej aplikacji pozwalającej na zarządzanie małą firmą (a) lub domową biblioteką gier/filmów/książek(b).

a) aplikacja ma umożliwiać przechowywanie danych kontrahentów, informacji o oferowanych produktach/usługach, obsługę zamówień realizowanych przez klientów oraz wystawianie rachunków, obsługę płatności;

b) aplikacja ma umożliwiać przechowywanie informacji na temat książek/gier/muzyki, obsługiwać wielu użytkowników, pozwalać na wypożyczanie zasobów, przedstawiać informacje o wypożyczeniach oraz umożliwiać tworzenie listy zasobów do uzupełnia (lista najbliższych zakupów)

Temat aplikacji możesz na zarządzanie dowolnymi zasobami (np. narzędziami, kolekcją figurek, kart do gry, komiksów itp.)

0. Przygotuj swoje repozytorium:

   - wygeneruj plik _README.md_, w którym opiszesz architekturę swojego projektu, podstawowe założenia i pomysły na ich realizację.
   - stwórz plik _Tasks.md_, w którym będziesz zapisywać informacje o aktualnie wykonywanych zadaniach (zajrzyj [TUTAJ](https://github.blog/news-insights/product-news/task-lists-in-all-markdown-documents/))

1. Przygotowanie projektu:

   - skonfiguruj potrzebne w projekcie paczki - podziel je na paczki, które potrzebne są jedynie w wersji developerskiej oraz te, które niezbędne są na produkcji
   - stwórz odpowiednią strukturę katalogową odpowiadającą wzorcowi MVC
   - przygotuj konfigurację _dotfile_'ów bibliotek, które wykorzystasz w projekcie

2. Zaimplementuj klasy modeli oraz obiektów DTO, które wykorzystywane będą przez Twoją aplikację. Stwórz odpowiednie typy TS oraz interfejsy, które wprowadzą do Twojej aplikacji silne typowanie.

3. Zaimplementuj lekkie kontrolery, które korzystać będą z funkcji pośredniczących (middleware), pozwalających na obsługę błędów, autentykację użytkownika w wykorzystaniem tokenów JWT oraz autentykację wykorzystującą mechanizm oAuth2.0 (z wykorzystaniem Firebase). Na początku możesz przygotować mockowe zestawy danych, z których korzystać będzie Twoja aplikacja.

4. Przygotuj prosty frontend generowany po stronie serwera (SSR), wykorzystujący dowolny mechanizm szablonów i pozwalający na zarządzanie Twoją aplikacją. Wykorzystaj gotowe biblioteki UI (np. Bootstrap lub TailwindCSS).

5. Przygotuj prosty frontend działający po stronie klienta (CSR) - może on wykorzystywać czysty JS/TS, dowolny framework (np. React, Vue.js). Ma on umożliwiać wykonywanie podstawowych metod kontrolerów. Możesz wykorzystać dowolne biblioteki UI.

6. Wykorzystaj dowolny ORM i zapewnij swojej aplikacji możliwość persystentnego przechowywania danych.
