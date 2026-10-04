# Materiały video do kursu

Materiały video do kursu przygotowane zostały w roku akademickim 2020/21 w czasie, gdy zajęcia odbywały się w trybie zdalnym. Materiały video nie będą na razie aktualizowane. Proszę pamiętać, że kurs żyje i wciąż się rozwija, a co za tym idzie niektóre filmy mogą się szybko dezaktualizować.

Materiały proszę traktować jako uzupełnienie wiadomości lub powtórkę przed zajęciami. Mogą być one również przydatne w nadrobieniu zaległości powstałych w wyniku nieobecności na zajęciach.

Proszę też nie sugerować się zadaniami do samodzielnego wykonania, które przedstawione są w materiałach video - zostały one od tego czasu zmienione i uściślone.

Miłego oglądania!

## Update 2022L:

+ zmodyfikowano warunki zaliczenia przedmiotu (informacje dostępne w sekcji Ogólne informacje)
+ zajęcia w pełni stacjonarne
+ drobne korekty w rozkładzie godzinowym i poruszanych tematach
+ na zajęciach pracujemy w IntelliJ Idea Ultimate i korzystamy z Oracle OpenJDK 17.0.2

## Zajęcia 0 - Wstęp do języka Java

*[Materiały na YouTube](https://www.youtube.com/watch?v=g94lR_cJ5Fw)*

## Zajęcia 1 - Składnia języka Java

*[Materiały na YouTube](https://www.youtube.com/watch?v=Quni7rLAb4M)*

## Zajęcia 3 - Programowanie obiektowe w języku Java

*[Materiały na YouTube](https://www.youtube.com/watch?v=ppOwde76px8)*

## Zajęcia 4 - Dziedziczenie w języku Java

*[Materiały na YouTube](https://www.youtube.com/watch?v=cWMM4CpdJdo)*

## Zajęcia 5 - Współbieżność w języku Java
*[Materiały na YouTube](https://youtu.be/1apj_7xsyhU)*

## Zajęcia 6 - Graficzne interfejsy użytkownika - AWT
*[Materiały na Youtube](https://youtu.be/mE1LHXc3wao)*

## Zajęcia 7 - Graficzne interfejsy użytkownika - Swing
*[Materiały na YouTube](https://youtu.be/vIxGpjNHjIY)*

## Zajęcia 8 - Graficzne interfejsy użytkownika - JavaFX
*[Materiały na YouTube](https://youtu.be/LQKANTKzt7w)*

Info:
+ wykorzystując IntelliJ Idea w wersji Ultimate można stworzyć projekt w JavaFX bez konieczności ręcznego podpinania bibliotek - wykorzystać należy wtedy Maven'a lub Gradle'a - jest to rozwiązanie "przyjemniejsze" i znacznie szybsze

Dodanie JavaFX do istniejącego projektu "z ręki":
+ ściągnąć należy bibliotekę JavaFX w odpowiedniej dla systemu operacyjnego wersji (najprościej *[stąd](https://gluonhq.com/products/javafx/)*)
+ warto doinstalować do Scene Builder'a, aby móc graficznie projektować interfejsy graficzne zamiast ręcznie tworzyć pliki fxml (najprościej *[stąd](https://gluonhq.com/products/scene-builder/)*)
+ w projekcie przechodzimy do zakładki File -> Project structure, wybieramy tam opcję Libraries i podajemy lokalizację do katalogu lib ze ściągniętej biblioteki JavaFX
+ następnie przechodzimy do zakładki Run w menu głównym i wybieramy Edit Configurations. W Build & Run wybieramy Modify options i dodajemy opcję "Add VM options" i podajemy następujące parametry

    --module-path ścieżka_do_katalogu_lib --add-modules javafx.controls, javafx.fxml

+ następnie wybieramy Apply i OK.

*UWAGA!*

 Rozwiązanie te bazuje na względnych ścieżkach i referencjach do konkretnych wersji bibliotek - warto zastosować zmienne systemowe, aby proces był uniwersalny

## Zajęcia 9 - Programowanie zorientowane sieciowo
*[Materiały na YouTube](https://youtu.be/dyZoKCyjazI)*

## Zajęcia 10 - Budowa interfejsu graficznego aplikacji sieciowych
*Brak materiału wideo*

Zajęcia dotyczące budowy interfejsu graficznego w różnych technologiach dla tej samej aplikacji - interfejs graficzny dla czatu z poprzednich zajęć

## Zajęcia 11 - Wstęp do biblioteki Spark 
*Brak materiału video*

Zajęcia na podstawie dokumentacji dostępnej na stronie *[WWW](https://sparkjava.com/documentation)*

## Zajęcia 12 - Budowa API po stronie serwera z wykorzystaniem biblioteki Spark 
*Brak materiału video*

Zajęcia na podstawie dokumentacji dostępnej na stronie *[WWW](https://sparkjava.com/documentation)*

Przykładowe API w Spark'u: https://www.baeldung.com/spark-framework-rest-api

## Zajęcia 13 - Framework Spring i wzorzec MVC
*[Materiały na YouTube](https://youtu.be/7JCYSrFrBjI)*


## Zajęcia 14 - Aplikacja CRUD z wykorzystaniem frameworka Spring.
*brak materiału video*

Testowanie aplikacji z wykorzystaniem narzędzi wbudowanych w IntelliJ Idea oraz wykorzystanie bazy H2 i JPA jako przykładu narzędzia ORM: [https://www.jetbrains.com/help/idea/spring-support-tutorial.html](https://www.jetbrains.com/help/idea/spring-support-tutorial.html)


## Materiały dodatkowe 
Budowa aplikacji dla systemu Android z wykorzystaniem języka Java (materiał dodatkowy, nagrany zostanie po sesji letniej) - *trwają prace nad materiałem*
