## Struktura strony w języku HTML + podstawowe znaczniki

Język HTML to **hipertekstowy język znaczników**, a więc do zakodowania naszej strony WWW wykorzystywać będzie ściśle określone znaczniki. Znaczniki mają swoją charakterystyczną budowę:
    
    <nazwa_znacznika atrybut="wartość_atrybutu"> ... </nazwa_znacznika>

**Nazwa znacznika** to zdefiniowana w specyfikacji języka nazwa, którą zazwyczaj łatwo skojarzyć z tym, do czego rzeczywiście służy znacznik.

**Atrybuty** to pewne cechy znacznika, które opisują jego zachowanie lub właściwości. Należy tutaj pamiętać - we współczesnym HTML'u nie ma atrybutów opisujących wygląd znaczników, co najwyżej można skorzystać z atrybutu `style`, którego wartością będzie CSS opisujący wygląd.

W znakomitej większości, znaczniki mają swoje otwarcie:

    <nazwa_znacznika>

oraz zamknięcie :

    </nazwa_znacznika>

W przypadku znaczników, które nie mają swojego znacznika zamykającego, można zupełnie zapomnieć o ich zamykaniu, chociaż czasami korzysta się z następującej konstrukcji:

    <nazwa_znacznika />

która pokazuje, że znacznik jest domknięty (tzw. self-closing), ale jest to nie do końca zgodne ze specyfikacją języka, początkowo traktowane było nawet jako błąd, jednak obecnie jest akceptowanlne, lecz ma znaczenie jedynie jako pewien lukier składniowy i może przypominać trochę składnię `XML'a`. Jeśli znacznik nie ma domknięcia (tzw. void element), zgodnie ze [specyfikacją](https://html.spec.whatwg.org/multipage/syntax.html#void-elements), możemy go pozostawić bez zamknięcia.

Konkretne znaczniki będą omówione w kolejnych podrozdziałach. Na końcu tego podrozdziału znaleźć można odnośnik do kompletnej listy akceptowanych i obowiązujących aktualnie znaczników. *Specyfikacja języka HTML nie pozwala nam na tworzenie własnych znaczników*.

## Podstawowa struktura strony WWW

![Struktura strony WWW w HTML5](/files/OPSS1/HTML_1.png "Podstawowa struktura strony w HTML5")

Wyjaśnijmy po kolei każdy z elementów: 
+ *linia 1.* to deklaracja typu dokumentu, która mówi przeglądarce internetowej w jaki sposób ma być interpretowany kod
+ *linia 2.* to deklaracja języka, z którego korzysta strona WWW - dwie małe litery określają język (w tym przypadku jest to język polski), a dwie wielkie litery po myślniku to deklaracja kraju, w którym języka się używa (szczególnie istotne w przypadku języków takich jak j. angielski czy francuski, które różnią się w zależności od kraju)
+ treść pomiędzy znacznikami `<head>` to sekcja nagłówkowa strony zawierająca metadane takie jak tytuł, kodowanie znaków, załączone skrypty i inne metadane, które mogą zostać wykorzystane przez przeglądarkę internetową
+ elementy `<meta>` to metadane, które mogą być interpretowane przez przeglądarkę - w *linii 4.* mamy deklarację kodowania znaków (UTF-8 jest ogólnoświatowym standardem rozumianym przez wszystkie maszyny), a w *linii 5.* deklarację skalowania viewport'a, dzięki czemu nasza strona gotowa jest na poprawne wyświetlanie na urządzeniach wyposażonych w ekrany HiDPI (czyli takie, jakie większość z nas ma w smartfonach) - warto zajrzeć pod ten [link](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag), aby dowiedzieć się więcej na temat skalowania oraz przeczytać ten [artykuł](https://www.quirksmode.org/blog/archives/2010/04/a_pixel_is_not.html), który tłumaczy dlaczego pixel nie zawsze jest pixel'em na naszym ekranie.
+ *linia 6.* to załączony do strony arkusz stylów - wykorzystujemy w tym celu znacznik `<link>` z atrybutem `rel="stylesheet"` mówiącym przeglądarce, że w pliku określonym przez atrybut `href`, znajdować się będzie treść, którą interpretować należy jako CSS, czyli kaskadowe arkusze stylów
+ pomiędzy znacznikami `<body>` znaleźć się musi treść strony internetowej, która widoczna będzie dla użytkownika końcowego

Podstawowy szablon struktury pliku HTML5 należy bezwzględnie zapamiętać, ale tworząc kod skorzystać można z narzędzia [Emmet](https://emmet.io/), wbudowanego bezpośrednio w VS Code (więcej informacji [tutaj](https://code.visualstudio.com/docs/editor/emmet). Wystarczy wtedy w pustym pliku z rozszerzeniem .html wstawić wykrzyknik i nacisnąć klawisz Enter - powyższy kod wstawi się automatycznie.

Poprawność znaczników sprawdzić można wykorzystując narzędzie [W3C Markup Validation Service](https://validator.w3.org/). Każdy kod wytworzony w ramach zajęć powinien być przez te narzędzie sprawdzony i powinien poprawnie przechodzić proces walidacji.

Okazuje się jednak, że strona-minimum to nie kod pokazany na powyższym obrazku, ale coś o wiele krótszego.

![Struktura strony WWW w HTML5](/files/OPSS1/HTML_2.png "Strona-minimum w HTML5")

Zachęcam, aby sprawdzić, że rzeczywiście kod ten "przechodzi" przez Validator i jest w pełni zgodny ze standardem języka HTML5.

## Znaczniki języka HTML5

Znaczniki dozwolone w języku HTML5 (jak i również w standardzie HTML5.1) znaleźć można na stronie WWW [MDN Web Docs](https://developer.mozilla.org/pl/docs/Web/HTML/Element), którą swoją drogą polecam jako podstawowy materiał do nauki HTML'a. Warto również w menu z lewej strony rozwinąć podsekcję *References/HTML elements* w sekcji *Related Topics*, aby spojrzeć, których elementów nie powinni już Państwo używać (proszę zwrócić uwagę, że duża część znaczników traktowana jest jako przestarzała oraz w HTML5 nie ma żadnych znaczników służących do formatowania i stylowania treści - tę rolę przejął CSS).

W ramach notatek do zajęć przedstawione zostaną jedynie niektóre znaczniki, na które warto zwrócić szczególną uwagę.

+ znaczniki nagłówka: 
    + `<h1> ... </h1>`
    + `<h2> ... </h2>`
    + `<h3> ... </h3>`
    + `<h4> ... </h4>`
    + `<h5> ... </h5>`
    + `<h6> ... </h6>`

Proszę pamiętać, że stopień nagłówka ma znaczenie semantyczne i powinno ono odzwierciedlać jego wagę - im mniejszy indeks, tym większa waga.

+ znaczniki list numerowanych i wypunktowanych
    + Lista numerowana
![Lista numerowana](/files/OPSS1/HTML_3.png "Lista numerowana")
    
    + Lista wypunktowana 
![Lista wypunktowana](/files/OPSS1/HTML_4.png "Lista wypunktowana")

Listy można oczywiście w sobie zagnieżdżać - przykład takiego zagnieżdżania list znajduje się w kodach do zajęć. Proszę pamiętać, że pomiędzy dowolnymi znacznikami listy znajdować mogą się jedynie znaczniki `<li>`, a więc zagnieżdżona lista musi być umieszczona w elemencie listy rodzica.

+ znacznik odnośników
        
        <a href="cel">wyświetlany tekst</a>
    
 Odnośniki (linki) mogą być otwierane w osobnym oknie - wtedy należy dodać w znaczniku `<a>` atrybut `target` o wartości `_blank`, np.:
 
    <a href="https://umk.pl" target="_blank">UMK</a>

+ znacznik paragrafu

![Znacznik paragrafu](/files/OPSS1/HTML_5.png "Znacznik paragrafu")

Znaczniki paragrafu pozwalają na logiczne wydzielenie paragrafów/akapitów testu bez potrzeby sztucznego ich łamania znacznikami nowej linii.

+ znacznik nowej linii

![Znacznik nowej linii](/files/OPSS1/HTML_6.png "Znacznik nowej linii")

+ znaczniki tabeli, wiersza tabeli oraz jej komórek:

Znacznik tableli to `<table> ... </table>`. Wewnątrz tabeli wytyczyć można dwie części - część nagłówkową oraz ciało tabeli. Odpowiednio służą do tego znaczniki `<thead> ... </thead>` oraz `<tbody> ... </tbody>`. Tabele definiowane są wierszami, tzn. z poziomu kodu html uzupełniamy je wiersz po wierszu - zaczynając od wierszy nagłówka, następnie przechodząc do wierszy zawierających dane. Wiersz definiowany jest z wykorzystaniem znacznika `<tr> ... </tr>`. Wewnątrz wiersza definiowane są kolejno komórki tabeli (kolejne komórki odpowiadające kolumnom). Wykorzystywany jest w tym celu znacznik `<td> ... </td>`. Wyjątek stanowi wiersz nagłówka tabeli, w którym możemy zdefiniować komórki z wykorzystaniem znacznika `<th> ... </th>` - mają one wtedy wagę semantyczną. Dodatkowo domyślnie są wyróżnione w stosunku co do zwykłych komórek. Przykładowa tabela wygląda następująco (tablica prawdy dla logicznej funkcji XOR):

![Przykładowa tabela w HTML](/files/OPSS1/HTML_7.png "Kod tabeli w HTML")

Efekt działania powyższego kodu (oczywiście uzupełniony o odpowiednie stylowanie) jest następujący:

<table class="default_table">
    <thead>
        <tr>
            <th> p </th>
            <th> q </th>
            <th> p XOR q </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td> 0 </td>
            <td> 0 </td>
            <td> 0 </td>
        </tr>
        <tr>
            <td> 0 </td>
            <td> 1 </td>
            <td> 1 </td>
        </tr>
        <tr>
            <td> 1 </td>
            <td> 0 </td>
            <td> 0 </td>
        </tr>
        <tr>
            <td> 1 </td>
            <td> 1 </td>
            <td> 0 </td>
        </tr>
    </tbody>
</table>

+ znacznik elementu inline'owego:

<p>Tekst w paragrafie, który jest wewnątrz <span>elementu liniowego</span></p>

Pełna lista znaczników, które dozwolone są w języku HTML 5 znajduje się [w dokumentacji w serwisie MDN](https://developer.mozilla.org/pl/docs/Web/HTML/Element).

+ znacznik bloku

    `<div>`

Znacznik bloku wykorzystywany jest do budowy struktury strony WWW. Bloki można wielokrotnie w sobie zagnieżdżać. Wzajemny układ bloków definiowany jest z wykorzystaniem kaskadowych arkuszy stylów. Kontenery, zgodnie ze specyfikacją języka HTML5, mogą być zastępowane znacznikami semantycznymi, oczywiście jeśli niosą one ze sobą wartość semantyczną

## Identyfikacja elementów 

Każdemu znacznikowi przypisać można atrybut `id` oraz `class`. Pierwszy z nich to unikalny identyfikator, który w danym dokumencie powinien wystąpić jedynie raz (aby mógł jednoznacznie definiować konkretny element), a drugi do identyfikator klasy - pewnej wspólnej cechy, która może być przypisana do wielu elementów w dokumencie. W praktyce - `id` pomaga nam wybierać elementy z drzewa DOM z wykorzystaniem języka Java Script, a `class` wykorzystywany jest do stylowania (dzięki temu łatwiej stworzyć uniwersalną "skórkę" serwisu WWW) oraz do wybierania wielu elementów, które mają wspólną cechę.

## Znaczniki semantyczne

Ważnym elementem języka HTML5 są znaczniki semantyczne, których zadaniem jest logiczne budowanie struktury witryny internetowej. Warto jest rozważyć, czy kontener, który zastosowany jest w kodzie niesie ze sobą wartość składniową i rozważyć jego zamian e na znacznik semantyczny. Jeśli blok został wprowadzony tylko celem budowy szkieletu strony i ma umożliwić łatwe stylowanie elementów - może on pozostać blokiem. 

Dostępne znaczniki semantyczne to:

+ `<article>`
+ `<aside>`
+ `<details>`
+ `<figcaption>`
+ `<figure>`
+ `<footer>`
+ `<header>`
+ `<main>`
+ `<mark>`
+ `<nav>`
+ `<section>`
+ `<summary>`
+ `<time>`

Znaczników semantycznych należy używać do budowy struktury. Można je oczywiście zagnieżdżać w sobie, w ich wnętrzu mogą znaleźć się kontenery, czyli znaczniki `<div>`. Znaczniki semantyczne szczególne znaczenie w przypadku indeksowania stron WWW oraz wykorzystywania w trakcie pracy narzędzi zwiększających dostępność stron WWW (np. dla osób niedowidzących) - nazwa znacznika jest bezpośrednio związana z jego zawartością i dzięki temu łatwo ocenić, co znajduje się w danej sekcji dokumentu HTML. Dodatkowo - kod HTML napisany z wykorzystaniem znaczników semantycznych jest o wiele bardziej czytelny, a jego podział - bardziej intuicyjny.