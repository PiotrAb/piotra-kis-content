## Wstęp do CSS

Jedyną dozwoloną formą opisu wyglądu stron WWW jest stosowanie kaskadowych arkuszy stylów (CSS). Zgodnie ze specyfikacją, język HTML5 nie posiada znaczników służących do stylowania dokumentów, a działanie niektórych znaczników zmieniających wygląd elementów w dokumencie ma znaczenie semantyczne.

W ogólności mamy trzy metody dodawania arkuszy stylów do dokumentów:
+ **style in-line**, które przypisane są do konkretnych elementów bezpośrednio w kodzie HTML w atrybucie `style`, np:

!["Przykład stylu in-line"](/files/OPSS1/CSS_1.png "Przykład stylu in-line")

Style in-line wykorzystywane są również do modyfikacji wyglądu z wykorzystaniem języka Java Script, gdy modyfikowane są konkretne elementy drzewa DOM.

+ **wewnątrz znacznika `<style>` w sekcji `<head>`**, gdzie styl połączony jest z zawartością pliku HTML, np:

!["Przykład stylu w sekcji <head>"](/files/OPSS1/CSS_2.png "Przykład stylu w sekcji <head>")

Rozwiązanie te jest jak najbardziej poprawne. Natomiast przydatne jest jedynie w przypadku, gdy strona jest prosta i nie zawiera zbyt wiele stylów CSS, gdyż mocno wydłuża ono plik HTML.

+ **arkusze stylów w osobnym pliku CSS** - rozwiązanie te jest najwygodniejsze i pozwala traktować style CSS jako swoiste "skórki" stron WWW, które łatwo podmieniać. Dodatkowo rozwiązanie te oddziela logiczny szkielet serwisu od jego warstwy prezentacji. Osobny plik załączany jest w sekcji `<head>` strony internetowej w następujący sposób:

!["Arkusz stylów w osobnym pliku"](/files/OPSS1/CSS_3.png "Arkusz stylów w osobnym pliku")

Atrybut `rel` określa w jaki sposób przeglądarka internetowa interpretować ma załączony plik (w typ przypadku jest to oczywiście kaskadowy arkusz stylów), a atrybut `href` określa źródło, z którego pobrany ma zostać plik CSS.

Na tym etapie polecam zbadać w jaki sposób ładowane są arkusze stylów z osobnego pliku. W tym celu należy uruchomić narzędzia developerskie przeglądarki WWW (w przypadku Chrome'a i Edge'a można zrobić to klikając przycisk F12) i przejrzeć jak wygląda "łańcuch" zapytań HTTP wysyłany przy odświeżeniu strony WWW. Każdy pojedynczy plik (niezależnie, czy to plik ze skryptem, stylem czy jakakolwiek grafika) ładowany jest osobno - przeglądarka wysyła po niego osobne zapytanie HTTP.

Wiedząc już, w jaki sposób można dodać "skórkę" do strony WWW, wypadałoby powiedzieć sobie w jaki sposób połączyć obiekty HTML z kodem CSS, tzn. w jaki sposób wskazać, które elementy na stronie WWW mają podlegać określonym przez nas stylom. W tym przypadku skorzystać można z atrybutów, które omówione zostały na sam koniec sekcji dotyczącej języka HTML. W kwestii przypomnienia, są to: 

+ nazwa znacznika
+ atrybut `id`, czyli unikalny w dokumencie identyfikator elementu
+ atrybut `class`, czyli klasa współdzielona przez wiele elementów w dokumencie

W jaki sposób połączyć elementy w HTML'u z CSS'em? Korzystając z selektorów. Najprostsze z nich zebrane zostały w tabeli poniżej.</p>

<table class="default_table">
    <tr>
        <th>HTML</th>
        <th>CSS</th>
    </tr>
    <tr>
        <td><code>&lt;nazwa_znacznika&gt;</code></td>
        <td>nazwa_znacznika</td>
    </tr>
    <tr>
        <td><code>&lt;nazwa_znacznika id="identyfikator"&gt;</code></td>
        <td>#identyfikator</td>
    </tr>
    <tr>
        <td><code>&lt;nazwa_znacznika class="klasa"&gt;</td>
        <td>.klasa</td>
    </tr>
    </table>

Najbardziej uniwersalnym i w sumie preferowanym sposobem stylowania dokumentu jest stylowanie oparte na klasach. Pozwala ono stworzyć uniwersalne klasy, które przypisane zostaną do wielu elementów na stronie WWW (tak jak wspominiano wcześniej, ta sama klasa może pojawić się w dokumencie wielokrotnie). Działa tutaj oczywiście kaskadowość arkuszy stylów, tak więc style klas mogą być przez siebie nadpisywane.

Nie są to oczywiście wszystkie dostępne w CSS selektory. Na chwilę obecną spojrzymy na jeszcze jeden selektor `>`, będący selektorem dziecka konkretnego elementu. Pozostałe selektory omówione zostaną w ramach osobnych zajęć. Działanie selektora dziecka jest następujące:

`rodzic > dziecko`

Selektor ten wybiera dziecko, które znajduje się zaraz pod rodzicem (nie wybiera on dzieci dzieci, czyli wnucząt elementu). Można go wykorzystać, aby wskazać konkretne zależności pomiędzy elementami. Na przykład `p > img` wskazuje na obraz, który znajduje się w paragrafie. Taki selektor będzie "dotykał" obu elementów `<img>` w poniższym kodzie:

!["Selektor dziecka w CSS"](/files/OPSS1/CSS_4.png "Selektor dziecka w CSS")

Selektor ten nie będzie już dotykał elementu `<img>` w tym kodzie:

!["Selektor dziecka w CSS"](/files/OPSS1/CSS_4.png "Selektor dziecka w CSS")

Aby wskazać obraz, czyli zawartość znacznika `<img>` w powyższym przykładzie należy albo odwołać się do "wnuczka" elementu `<p>`, albo 

## Kaskadowość arkuszy stylów

Arkusze stylów zachowują się kaskadowo, co znaczy, że reguły CSS mogą wykluczać się wzajemnie i "przekrywać" się pomiędzy zdefiniowanymi różnymi stylami, a ostateczny wygląd elementu ustalany jest na podstawie hierarchii. 

Ogólna zasada jest bardzo prosta - im bliżej formatowanego elementu, tym wyższe pierwszeństwo.

Przeglądarka internetowa interpretuje style w następującej kolejności:

1. domyślne arkusze stylów dla przeglądarki WWW
1. domyślne arkusze stylów przeglądarki skonfigurowane przez użytkownika przeglądarki
1. zewnętrzne arkusze stylów z plików CSS i wewnętrzne ze znacznika `<style>` w sekcji `<head>` strony WWW
1. definicje stylów in-line w atrybucie `style` znacznika elementu

Style wewnętrzne podlegają interpretacji wcześniej niż style zewnętrzne, a więc łatwo przekryć zewnętrznym stylem definicję ze znacznika `<style>` w sekcji `<head>` - warto więc przyjąć zasadę. aby nie mieszać stylów wewnętrznych i zewnętrznych, pozostając przy jednych z nich (oczywiście ze względów czytelności kodu lepiej pozostać przy stylach zewnętrznych).

Jeśli dla danego elementu zdefiniowane są style zarówno dla znacznika, klasy, identyfikatora, to kolejność interpretacji wygląda w następujący sposób:

1. znaczniki i pseudo-elementy
1. selektory klas, atrybutów i pseudo-klas
1. identyfikatory

<!-- DOPISAĆ -->

Dodatkowo warto pamiętać o istnieniu selektora `*`, tzw. selektora uniwersalnego, który dotyczy wszystkich elementów na stronie WWW. Priorytet tego selektora jest oczywiście najmniejszy, ponieważ jest to najbardziej ogólny selektor.

Precedencję stylów złamać można poprzez zastosowanie dyrektywy `!important` przy definicji konkretnego atrybutu, dodając ją na końcu. Dzięki temu style, które odziedziczone zostały z innych elementów zostaną bezwzględnie nadpisane. Zainteresowanych odsyłam do dalszej lektury ciekawego artytułu w serwisie [CSS Tricks](https://css-tricks.com/when-using-important-is-the-right-choice/).

Wszystkie potrzebne informacje na temat stylowania dokumentów HTML znaleźć można w dokumentacji na stronie [MDN Web Docs](https://developer.mozilla.org/pl/docs/Learn/CSS). Zachęcam w szczególności do zapoznania się dwoma modułami dotyczącymi stylowania konkretnych grup treści:

+ [tekstu](https://developer.mozilla.org/en-US/docs/Learn/CSS/Styling_text)
+ [bloków i kontenerów](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks)

# Model pudełkowy w CSS

Bardzo ważnym aspektem zrozumienia kaskadowych arkuszy stylów jest model pudełkowy (ang. box-model). Każdy element na stronie WWW traktowany jest jako pudełko, na które składają się: **treść**, **margines wewnętrzny**, **obramowanie** i **margines zewnętrzny**.</p>

!["Model pudełkowy w CSS"](/files/OPSS1/css_box-model.png "Model pudełkowy w CSS")

Aby podejrzeć jak wyglądają konkretne wartości dla elementu na stronie WWW wykorzystać można ponownie narzędzia developerskie przeglądarki internetowej. Na samym dole sekcji Styles widoczne są parametry naszego pudełka: 

!["Podgląd pudełek w narzędziach developerskich przeglądarki"](/files/OPSS1/box-model_devtools.png "Podgląd pudełek w narzędziach developerskich przeglądarki")

Poszczególne elementy modelu pudełkowego to:
+ `margin`, czyli margines zewnętrzny
+ `padding`, czyli margines wewnętrzny
+ `border`, czyli obramowanie

Każdy z tych parametrów dotyka czterech stron obiektu: `top`, `right`, `bottom`, `left` - czyli góra, prawa strona, dół i lewa strona. Można je ustawić w następujący sposób:

!["Ustawienie marginesów i obramowania w CSS"](/files/OPSS1/CSS_6.png "Ustawienie marginesów i obramowania w CSS")

gdzie wartość podana w `px` to grubość (można skorzystać też z innych jednostek) odpowiedniego marginesu lub obramowania. Będzie ona traktowana jako taka sama z każdej strony. Natomiast, jeżeli skorzystamy z zapisu

!["Ustawienie marginesów i obramowania w CSS"](/files/OPSS1/CSS_7.png "Ustawienie marginesów i obramowania w CSS")

możemy zdefiniować grubości marginesów niezależnie. Kolejność parametrów jest następująca: góra, prawo, dół, lewo - co łatwo zapamiętać, bo są one określane zgodnie z ruchem wskazówek zegara rozpoczynając od godziny 12:00.

Można oczywiście każdy z marginesów/obramowań określić osobno: 

!["Ustawienie marginesów CSS - każdy z  osobna"](/files/OPSS1/CSS_8.png "Ustawienie marginesów w CSS - każdy z osobna")

Rozwiązanie te jest szczególnie przydatne w przypadku, gdy zależy nam na modyfikacji tylko jednego obramowania lub marginesu.

W tym miejscu wypada również powiedzieć parę słów o obramowaniach. Jak pokazano w kodzie powyżej atrybut `border` posiada trzy argumenty - pierwszym z nich jest grubość obramowania, drugim styl obramowania a trzecim jego kolor. Więcej na temat obramowań znaleźć można w dokumentacji na stronie [MDN](https://developer.mozilla.org/pl/docs/Web/CSS/border").

Domyślnie, nasza przeglądarka do rozmiaru elementu dodaje padding i obramowanie, tak więc zdefiniowanie przez nas bloku o konkretnym rozmiarze powoduje, że obszar przez niego zajmowany będzie powiększony o margines zewnętrzny, wewnętrzny oraz o obramowanie. Atrybutem w CSS, który decyduje o wyliczaniu rozmiaru elementów jest atrybut `box-sizing`. Domyślnie przyjmuje on wartość `content-box`. Aby w danym bloku, margines wewnętrzny i obramowanie wliczane były do rozmiaru elementów wartość atrybutu `box-sizing` ustawić należy na `border-box`. Poniżej znajdują się dwa bloki o takiej samej definicji w HTML, lecz nałożonych dwóch różnych stylach CSS zgodnych z poniższym kodem:

!["Działanie atrybutu box-sizing"](/files/OPSS1/CSS_9.png "Działanie atrybutu box-sizing")

Wygląd elementu `#div1` jest następujący:

<div style="width: 200px; height: 100px; padding: 25px; margin: 50px; border: 2px solid black; box-sizing: content-box;"></div>

Natomiast kontener `#div2` wygląda tak: 

<div style="width: 200px; height: 100px; padding: 25px; margin: 50px; border: 2px solid black; box-sizing: border-box;"></div>

Widać znaczną różnicę w rozmiarach, prawda? Polecam zbadać oba elementy z wykorzystaniem narzędzi developerskich (w przeglądarkach opartych na Chrome/Chromium klawisz `F12` na klawiaturze). Oba kontenery mają ustawione takie same wymiary, ale różnią się jedynie sposobem obliczania rozmiarów.


## Layouty stron WWW - archaiczny `float`


W ramach zajęć skupiliśmy się na layoutach,które przyjazne użytkownikowi korzystającemu z urządzeń mobilnych. W dzisiejszym świecie pamiętać należy, że większość odwiedzin serwisów WWW odbywa się z urządzeń mobilnych - głównie smartfonów, które rozdzielczością i wielkością ekranu dorównują praktycznie tabletom sprzed kilku lat.</p>

W pierwszej kolejności zwróciliśmy uwagę na fakt, że coraz więcej ekranów korzysta ze skalowania HiDPI - raczej mało wygodne jest korzystanie z ekranów, które mają rozdzielczości FullHD i wyższe na ekranach, które mają pomiędzy 5 a 7 cali. Wszystko obecnie rozbija się o parametr PPI (ang. pixels per inch), a więc zagęszczenie pikseli na cal ekranu. Aby uniknąć problemów ze skalowaniem i aby rozmiary elementów na stronie WWW nie były definiowane rozdzielczością natywną ekranu, a przeskalowaną rozdzielczością, która została ustalona przez producenta urządzenia lub jego użytkownika wprowadziliśmy w sekcji `head` strony internetowej dodatkowy wpis: 

!["Definicja skalowania viewportu strony WWW"](/files/OPSS1/CSS_10.png "Definicja skalowania viewportu strony WWW")

Dzięki niemu skalowanie elementów na stronie WWW odbywa się zgodnie z ustalonym skalowaniem ekranu. Aby dokładnie zrozumieć ten problem polecam lekturę sekcji MDN poświęconej konfiguracji viewport'a: [Viewport meta tag](https://developer.mozilla.org/en-US/docs/Web/HTML/Viewport_meta_tag") oraz artykułu ["A pixel is not a pixel"](https://www.quirksmode.org/blog/archives/2010/04/a_pixel_is_not.html).

Najprostsze możliwe "dostosowanie" stron do potrzeb ekranów o różnych rozdzielczościach oparte jest na pływaniu elementów, czyli ustawieniu odpowiednim blokom atrybutu `float`: 
+ `float: left` - w przypadku elementów, które mają pływać do lewej strony
+ `float: right` - w przypadku elementów, które mają pływać do prawej strony

Domyślnie, elementy blokowe zajmują całą dostępną szerokość elementu rodzica, lecz w przypadku, gdy ma stonie ustawione są elementy pływające, mogą pojawić się problemy z wyświetlaniem, które mają zajmować całą szerokość rodzica i w ich przypadku należy dodatkowo dodać atrybut `clear` z wartością `both`. Dzięki niemu, element znajdzie pod lub nad elementami pływającymi, zgodnie z miejscem, które zajmuje w szkielecie strony WWW.

Więcej na ten temat znaleźć można w odpowiednich sekcjach dokumentacji w serwisie MDN: 
+ [float](https://developer.mozilla.org/en-US/docs/Web/CSS/float)
+ [clear](https://developer.mozilla.org/en-US/docs/Web/CSS/clear)

W ramach zajęć przekonaliśmy się, że użycie tych dwóch atrybutów nie jest zbyt wygodne w przypadku budowania layout'u współczesnej strony WWW i słusznie powinno zostać porzucone na rzecz rozwiązań o wiele bardziej uniwersalnych. Proszę pamiętać - layout oparty na atrybutach `float` i `clear` jest rozwiązaniem wybitnie antymobilnym.

Jako, że współczesne strony internetowe konsumowane są głównie z poziomu smartfonów i urządzeń mobilnych (wspólnie stwierdziliśmy, że "scrollowanie" na telefonie jest standardowym sposobem na spędzenie wolnej chwili i zastępuje spojrzenie w gazetę lub książkę), to layout oparty na `float`'ach powinien zostać słusznie zapomniany.

Mobilność serwisu WWW warto testować na najmniejszym możliwym ekranie. Obecnie przyjmuje się, że minimalny rozmiar ekranu w trybie portretowym to 320x568px na 4", czyli rozdzielczość jaką oferuje użytkownikowi iPhone 5/5s/SE gen1. Rzeczywista rozdzielczość tego ekranu to 640x1136px, ale wprowadzone zostało skalowanie - jeden pixel wyświetlany jest przez 4 fizyczne pixele (Apple nazywa taki ekran ekranem Retina, Microsoft - PixelSense), czyli jest to typowy przykład skalowania ekranów HiDPI. Wszystko wskazuje na to, że wraz z zakończeniem wsparcia dla tych smartfonów (głównie iPhone SE 1gen) najmniejszy rozmiar ekranu, który będzie trzeba rozważać to ekran o rozmiarze 4,7' i rozdzielczości 375x667px (natywna rozdzielczość 750x1334px), w który wyposażone są nowsze małe smartfony.

Warto pamiętać, w jaki sposób ograniczyć można zmiany szerokości/wysokości elementów na stronach WWW poprzez zastosowanie atrybutów `min-width`, `max-width`, `min-height` i `max-height`. Jest to szczególnie ważne w przypadku, gdy zależy nam na ograniczeniu zmiany rozmiaru niektórych elementów stron WWW, które niekoniecznie powinny być maksymalnie zmniejszone lub powiększone (głównie chodzi tutaj o treść strony WWW).

Zwrócić uwagę należy również na poprawne skalowanie się stron internetowych na ekranach o innych proporcjach niż powszechnie stosowane panoramy 16:9 i 16:10. W przypadku proporcji ekranu 21:9 (powszechnie zwanej ultrapanoramiczną) warto zastosować ograniczenie szerokości, aby strona nie wyglądała na sztucznie rozciągniętą w poziomie (odbiór treści z takiej witryny był dość mało wygodny).

## Layout `flex`

Znacznie bardziej przyjaznym urządzeniom mobilnym podejściem do budowy szablonu strony WWW jest zastosowanie layoutu `flex`, który domyślnie przystosowany jest do zastosowań na urządzeniach przenośnych.

Jego funkcjonalność warto implementować w oparciu o dokumentację techniczną, która dostępna jest na stronach [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/flex).

Dodatkowo - warto zajrzeć do serwisu [CSS-TRICKS](https://css-tricks.com/snippets/css/a-guide-to-flexbox/), gdzie znaleźć można kompletne wyjaśnienia dotyczące layoutu `flex`.

Zasada korzystania z tego layoutu jest bardzo prosta - jeśli strona ma być "z pudełka" przyjazna urządzeniom mobilnym, to warto wykorzystać ten właśnie layout. Sprawdza się on wszędzie tam, gdzie `float` oraz tam, gdzie `float` sprawia problemy (np. przy środkowaniu elementów, które zmieniają swoje położenie w zależności o rozmiaru ekranu). Jeśli strona WWW korzystać ma z bloków, które mają się przemieszczać przy zmianach rozdzielczości lub gdy ich rozmiary mają być definiowane jako konkretny stosunek podziału dostępnej przestrzeni z zaznaczeniem, że istnieje minimalny lub maksymalny rozmiar elementu - odpowiednim wyborem jest właśnie `flex`.

## Layout `grid`

Drugim z layout'ów, które są obecnie wykorzystywane i również nadają się do zastosowań mobilnych jest layout `grid`. `grid` to nic innego jak siatka, układ wierszy i kolumn, która może skalować się do swojego rodzica, definiując swoje rozmiary jako proporcje rodzica lub mieć je z góry określone (w dowolnych jednostkach).

`grid` świetnie nadaje się tam, gdzie układ elementów ma tworzyć siatkę (np. galerie fotografii, zbiory kart czy kafelkowe zestawy odnośników). 

Jak wcześniej wspomniano, layout `grid` może skalować się do rozmiarów elementu rodzica, przez co może sprawiać pewien problem w przypadku urządzeń mobilnych, gdyż jego siatka dostosuje się do mniejszej przestrzeni, a więc i jego zawartość będzie mniejsza. Warto pamiętać, że w przypadku stosowania `grid`'a na urządzeniach mobilnych warto zadbać o zdefiniowanie minimalnego rozmiaru elementu i umożliwienie scroll'owania treści w przypadkach, gdy nie wszystko może zmieścić się na ekranie urządzenia.

Szczegóły dotyczące implementacji layout'u `grid` znaleźć można w dokumentacji technicznej na stronach [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/grid).

Warto też zajrzeć do serwisu [CSS-TRICKS](https://css-tricks.com/snippets/css/complete-guide-grid/), aby zapoznać się ze szczegółami `grid`'a w przystępnej formie.

## Metody pozycjonowania elementów na stronach WWW

Za pozycjonowanie elementów na stronie WWW odpowiada atrybut `position`. Jego możliwe wartości są następujące:

+ `position: static` - domyślny sposób pozycjonowania elementów, są one pozycjonowane względem rodzica i nie ulegają modyfikacjom wprowadzanym przez atrybuty `left`, `top`, `right`, `bottom` 
+ `position: sticky` - element pozycjonuje się w zależności od pozycji scroll'a przeglądarki jako `static` lub jako `fixed` - do określonej pozycji we viewport'cie jest on statyczny i blokuje się jako fixed po jej osiągnięciu
+ `position: fixed` - element pozycjonowany jest niezależnie od stanu scroll'a
+ `position: relative` - element pozycjonowany jest zgonie ze swoją normalną pozycją (jak `static`), ale jego dzieci, które ustawione będą miały `position: absolute;` będą pozycjonowane względem tego właśnie elementu
+ `position: absolute` - element pozycjonowany jest absolutnie względem rodzica, którego pozycja jest zdefiniowana, jeśli żaden przodek elementu nie ma zdefiniowanej pozycji, to pozycjonowanie przebiega względem najstarszego elementu w drzewie, czyli względem elementu `<body>`.

Pełna dokumentacja techniczna atrybutu `position` znajduje się w serwisie [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/position).

## Pseudoklasy w CSS

W języku CSS występują pseudoklasy, które ułatwiają wybór elementów na podstawie informacji, które nie są ściśle związane z drzewem dokumentu. Z pseudoklas można korzystać dla każdego elementu w drzewie strony i można je łączyć z innymi selektorami CSS.

Na stronach [MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes) znaleźć można pełną dokumentację pseudoklas, w ramach zajęć zdążyliśmy skorzystać jedynie z kilku z nich:

+ `:hover` - pseudoklasa związana z elementem, który znajduje się pod kursorem myszy
+ `:nth-child(n)` - pseudoklasa związana z elementem będącym n-tym dzieckiem
+ `:first-child` - pseudoklasa związana z elementem będącym pierwszym dzieckiem (pierwsze wystąpienie konkretnego elementu wewnątrz innego elementu)
+  `:last-child` - pseudoklasa związana z elementem będącym ostatnim dzieckiem (ostatnie wystąpienie konkretnego elementu wewnątrz innego elementu)

## Mobilne szablony stron WWW - **RWD**

RWD (ang. Responsive Web Design) jest jednym z podejść do tworzenia mobilnych stron WWW. Podejście te święciło swoje triumfy przed dziesięcioma laty, gdy strony musiały dostosowywać się do różnych ekranów (różne rozdzielczości i wielkości), mobilne serwisy WWW raczkowały. Założenie było bardzo proste - budujemy serwis w wersji desktopowej, a następnie modyfikujemy go tak, aby dało się z niego korzystać również na urządzeniach mobilnych: tabletach i smartfonach.

!["RWD vs. AWD"](/files/OPSS1/RWD_AWD.png "RWD vs. AWD")

RWD było przeciwieństwem AWD (ang. Adaptive Web design), które zakładało generowanie optymalnych dla danego urządzenia kaskadowych arkuszy stylów, a więc wymuszało na programiście stworzenie równolegle kilku arkuszy. AWD oczywiście mogło być bardziej optymalne, mogło gwarantować szybsze ładowanie się stron WWW, gdyż assety przygotowywane były typowo pod konkretne urządzenie, a więc rozmiarowo dostosowane do tego urządzenia, jednak znacznie wydłużało to pracę nad serwisem i było trudne w utrzymaniu (za każdym razem trzeba było przygotowywać kilka wersji assetów).

Założenie było bardzo proste - w zależności od rozdzielczości ekranu i jego pozycji (ustawienie horyzontalne lub wertykalne), modyfikowane jest położenie elementów na stronie. Dodatkowo - RWD pozwalał na ukrywanie niektórych treści na stronie w przypadku, gdy ich wyświetlenie jest trudne, a treść nie jest kluczowa w odbiorze strony WWW. Tworzenie serwisu rozpoczynało się na wersji desktopowej, a kończyło na wersji mobilnej, poprzez dodawanie odpowiednich breakpointów w kodzie CSS i stosowanie `media-queries`. Sama responsywność dotyczyła tutaj dostosowania się zmiennego rozmiaru ekranu.

!["Responsive Web Design - breakpointy"](/files/OPSS1/RWD.png "Responsive Web Design - breakpointy")

Obecnie coraz częściej odchodzi się od idei RWD na rzecz podejścia bardziej mobilnego podejścia, które zakłada stworzenie dobrej wersji mobilnej i dobudowywanie do niej zmian na potrzeby większych urządzeń.

Celem zapoznania się ideą Responsive Web Design zachęcam do zajrzenia w poniższe odnośniki:

+ [HTML5 - Responsive Web Design @ Learn Microsoft](https://learn.microsoft.com/pl-pl/archive/msdn-magazine/2011/november/html5-responsive-web-design)
+ [Responsive Design @ MDN](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Responsive_Design)
+ [Media queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)

## Mobilne szablony stron WWW - **mobile-first**

Bardziej nowoczesne podejście do tematu mobilności na stronach WWW to metodologia mobile-first, która zakłada, że najważniejsza jest wersja mobilna serwisu WWW. Jest to oczywiście podejście uzasadnione, zważywszy, że większość wejść na współczesne strony pochodzi właśnie z urządzeń mobilnych. Dodatkowo - dobrze zrealizowana strona mobilna będzie poprawnie działać w środowisku desktopowym, co w drugą stronę jest już oczywistością.

!["mobile-first na stronach WWW"](/files/OPSS1/mobile-first.png "mobile-first na stronach WWW")

Zasada budowy serwisów w oparciu o mobile-first jest bardzo prosta - w pierwszej kolejności przygotowujemy wersję mobilną, a następnie rozbudowujemy aplikację do potrzeb większych ekranów. Oczywiście, tak jak stwierdzono wcześniej, aplikacja poprawnie przygotowana mobilnie może też być wersją desktopową, ale warto jest dopracować jej interfejs, który wygodnie będzie obsługiwany nie tylko dotykiem, ale również kursorem myszy lub też z poziomu klawiatury. W przypadku implementacji aplikacji w podejściu mobile-first również warto zastosować odpowiednie `media-queries`, zadbać o odpowiednią typografię a czasami skorzystać z gotowych bibliotek implementujących podejście mobile-first. Większość współczesnych bibliotek do budowy GUI podchodzi do budowy stron w ten właśnie sposób (zobacz jak wygląda to w przypadku biblioteki [Bootstrap](https://getbootstrap.com/docs/5.3/getting-started/introduction/)).

Mobile-first to również korzystnie z layoutów, które są przyjazne urządzeniom mobilnym. W pierwszej kolejności warto wykorzystać `flex`'a, można również rozważyć skorzystanie z layoutu `grid`. Unikać warto na pewno `float`'ów.

Cytując za Joshem Clarkiem z jego książki "Seven deadly mobile myths" (oryginalnie stwierdzenia tego używał Bruce Lee):

*Content is like water. You put water into a cup it becomes the cup. You put water into a bottle it becomes a bottle. You put it in a teapot, it becomes the teapot.*

W mobile-first w pierwszej kolejności liczy się treść, która nie może być "obcinana" przez warstwę jej prezentacji.

Dodatkowo - mobile-first to pierwszy krok, który pozwoli zamknąć aplikację webową w postaci PWA (ang. Portable Web App). Zainteresowanych zachęcam do lektury [rozdziału MDN](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps), [dokumentacji przeglądarki Google Chrome](https://support.google.com/chrome/answer/9658361?hl=pl&co=GENIE.Platform%3DAndroid) oraz [artykułów na stronie web.dev](https://web.dev/progressive-web-apps/).

Warto jest również zajrzeć pod poniższe linki:

+ [Mobile-first @ CSS-TRICKS](https://css-tricks.com/how-to-develop-and-test-a-mobile-first-design-in-2021/)
+ [Mobile-first @ MDN](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps/Responsive/Mobile_first)