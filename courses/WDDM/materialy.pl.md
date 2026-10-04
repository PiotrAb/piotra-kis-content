# Materiały do kursu Wstęp do Data mining

## Prezentacja do zajęć

Udostępniam Państwu od razu wszystkie slajdy do wykładu, ale proszę zwrócić uwagę, że prezentacja jest aktualizowana regularnie przed zajęciami. Dostęp do prezentacji mają Państwo po zalogowaniu się do serwisu Office 365 kontem należącym do organizacji UMK.

*[Wstęp do data mining - semestr letni 2024](https://umkt-my.sharepoint.com/:p:/g/personal/piotra_o365_umk_pl/Ef0z8zNVzSZPujyqNkKti4oB08Eu0DDMdilplJFqiUQ7SA?e=113NWk)*

## Repozytoria GitHub

*[Repozytorium z materiałami do zajęć](https://github.com/IS-UMK/WDDM24L_zajecia_PiotrA)*

Każdy ze Studentów zapisanych na kurs w systemie USOS dodany został do zespołu w serwisie GitHub i otrzymał w związku z tym dostęp do repozytorium - jeśli pojawią się problemy z dostępem proszę o kontakt.

Repozytorium z materiałami jest dla Państwa dostępne jako zapis kodów omawianych w trakcie zajęć - bazuje ono na materiałach przygotowanych specjalnie na potrzeby tych zajęć, ale w takcie semestru ulegać może drobnym zmianom - warto do niego regularnie zaglądać i w przypadku jego sklonowania na lokalną maszynę regularnie je pull'ować.

W repozytorium znajdują się również zadania - każde zadanie to osobny zeszyt Jupyter Notebook.

## Dodatkowe materiały warte uwagi

+ Zajęcia 5. - **Regresja**
    - Jak działa regresja liniowa? Interaktywna strona tłumacząca regresję liniową: [MLU-EXPLAIN](https://mlu-explain.github.io/linear-regression/)
    - Regresja liniowa z wykorzystaniem scikit-learn: [Real Python](https://realpython.com/linear-regression-in-python/)
    - 7 algorytmów regresji wykorzystywanych w uczeniu maszynowym: [Pierian Training](https://pieriantraining.com/7-machine-learning-regression-algorithms-python/)

## W jaki sposób pobrać nową zawartość repozytorium szkieletowego do swojego fork'a?

Wewnątrz katalogu ze swoim fork'iem:

    git remote add upstream [link do repo]
    git fetch upstream
    git checkout master
    git merge upstream/master
    git push 

Pierwszą komendę należy wydać tylko za pierwszym razem.