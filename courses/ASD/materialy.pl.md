## Materiały

<i class="pi pi-file-pdf"></i> [Lista zadań obowiązujących w roku akademickim 2023/24](/files/23-lab-zadania.pdf)

<i class="pi pi-file-pdf"></i> [Prezentacja do wykładu prof. Norberta Jankowskiego](http://is.umk.pl/~norbert/asd/asd_wyk.pdf)

<i class="pi pi-file-pdf"></i> [Prezentacja z pierwszych zajęć](/files/ASD_22Z.pdf)

## Środowisko developerskie

W ramach zajęć polecam pracować na jednym z serwerów wydziałowych: **tor** lub **polon**, gdzie znajduje się zestaw narzędzi wystarczający do przygotowania rozwiązań zadań. Z zewnątrz Wydziału, można łączyć się do serwera dostępowego **ameryk**.

Polecam skorzystać z następujących narzędzi, które są multiplatformowe i nie powinny sprawiać problemów przy pracy:

+ [Visual Studio Code](https://code.visualstudio.com)
+ wtyczka do VS Code: [Remote-SSH](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-ssh)


Nic nie stoi na przeszkodzie, aby skorzystali Państwo z prywatnych komputerów i pracowali na nich. Konfiguracja przedstawiona została w dwóch poniższych dokumentach PDF (jest to wersja z poprzedniego roku akademickiego, odrobinę zmieniło się nazewnictwo repo, ale idea i rozwiązania techniczne są takie same). Z prywatnych maszyn można również łączyć się z serwerem **ameryk.fizyka.umk.pl** z wykorzystaniem protokołu SSH.

<i class="pi pi-file-pdf"></i> [Konfiguracja lokalnego środowiska developerskiego](/files/ASD-VSCode.pdf)

<i class="pi pi-file-pdf"></i> [Krótka instrukcja do GitHub'a](/files/ASD-GitHub.pdf)

<i class="pi pi-file-pdf"></i> [Konfiguracja kluczy SSH na serwerze Ameryk](/files/ASD-ameryk.pdf)


## Repozytoria GitHub

Każdy ze Studentów zapisanych do prowadzonych przeze mnie grup zajęciowych otrzymał zaproszenie do klasy w serwisie GitHub Classroom. Proszę kliknąć w link zaproszenia i dopisać się do grupy. Dzięki temu sklonowane zostanie repozytorium stanowiące szkielet rozwiązań zadań (zadeklarowane są tam nagłówki funkcji, których definicja jest rozwiązaniem zadania).

Repozytoria podlegają sprawdzaniu przez prowadzącego i są podstawą do rozliczenia zadań.

## W jaki sposób pobrać nową zawartość repozytorium szkieletowego do swojego prywatnego repo?

**UWAGA!** Tę czynność należy wykonać jedynie w przypadku, gdy w trakcie semestru pojawią się zmiany w repozytorium szkieletowym (nie przewiduję ich, ale również nie wykluczam - być może niektóre deklaracje będą wymagały uściślenia lub drobnej modyfikacji).

Wewnątrz katalogu ze swoim repozytorium:

    git remote add upstream https://github.com/IS-UMK/ASD_LAB_23Z
    git fetch upstream
    git checkout master
    git merge upstream/master
    git push 

Pierwszą komendę należy wydać tylko za pierwszym razem.
