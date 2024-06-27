# Kilka prostych fixów
Kilka prostych napraw problemów w przypadku pracy z Gitem

## Proste konflikty w liniach kodu
W przypadku prostych konfliktów polegających na różcnicy w tej samej linii kodu, przy próbie łączenia branchy pojawi się błąd połączenia. W jego wyniku plik, który miał zostać zmieniony zostanie "wzbogacony" o dodatkowe linie zawierające porównanie linii z obu plików np.:
><<<<<<< HEAD\
Linia kodu ze zmianami wprowadzonymi na nowej gałęzi\
\=======\
Linia kodu ze zmianami wprowadzonymi na starej gałęzi\
\>>>>>>> main

W takim przypadku należy pozostawić jedynie właściwą linię kodu (należy usunąć zarówno błędną linię jak i wszystkie znaczniki związane z konfliktem). Nastepnie należy ponownie dodać plik do stage'a i go scommitować.

## Poprawa błędnego commita
W prypadku popełnienie błędu w przypadku commita (np. literówka) można go poprawić pod warunkiem, że błąd zauważony zostanie od razu (przed dodaniem jakichk olwiek innych commitów do repozytorium). Aby naprawić taki błąd, nalezy nanieść poprawki a następnie użyć parametru --amend do komendy git commit:
>git commit **--ammend** -m "Poprawiony błąd"

Spowoduje to podmianę ostatniego commita na ten dodany z parametrem --ammend\
Podobnie w przypadku błędu jedynie w tytule commita, wystarczy podobnie jak poprzednio użyć komendy git commit z parametrem --ammend, np:
>git commit **--ammend** -m "Poprawiony tytułu commita"

## "Przeniesienie" commita do innego brancha
Jeśli przez przypadek dokonaliśmy zmian w gałęzi main, a chcemy, żeby te zmiany znajdowały się np. w gałęzi roboczej, jednocześnie aby gałąź main zawierała kod zgodny z ostatnim pullem z repozytorium zdalnego, możemy tego dokonać np. tak:
>git branch roboczy_branch\
>git reset --hard origin/main

Pierwsza z tych komend skopiuję branch main do nowego brancha o nazwie roboczy_branch, druga natomiast zresetuje branch main do wersji ostatnio pobieranej z repozytorium zdalnego. Dzięki temu branch main będzie zawierał oryginalny kod, natomiast branch roboczy będzie zawierał commity dodane do lokalnego repozytorium po ostatnim pobraniu ze zdalnego repo.

## Cofnięcie commita wysłanego juz do zdalnego repo
W przypadku gdy stwierdzimy, ze niepotrzebnie wysłaliśmy jakiegoś commita do zdalnego repozytorium, możemy go wycofać przy użyciu komendy git revert, np.:
>git revert a04349

gdzie a04349 to oznaczenie identyfikujące jednoznacznie konkretnego commita (wystarczająco długi ciąg z SHA1 commita - można go sprawdzić przy użyciu komendy git log).

Należy pamiętać, że ta komenda, tak naprawdę tworzy nowego commita oznaczonego jako przywrócenie (rollback) konkretnego commita. W związku z tym należy pamiętać, że błędny commit pozostanie w historii zdalnego repo i - jeśli jest to poprawka starego commita - może powodować konflikty w działającym już kodzie.

## Cofnięcie niechcianych zmian pliku (przed dodaniem go do stage'a)
Jeśli niechcący dokonaliśmy zmian w pliku i zapisaliśmy je, ale jeszcze nie dodaliśmy ich do stage to możemy przywrócić wersję pliku sprzed zmiany korzystając z komendy git checkout lub git restore:
>git checkout nazwa.pliku

lub
>git restore nazwa.pliku

Spowoduje to cofnięcie zmian zapisanych w pliku nazwa.pliku do ostatniej zacommitowanej wersji.

## Usunięcie pliku z repozytorium
Jeśli przypadkowo dodaliśmy plik do lokalnego repozytorium, który tam nie powinien się znaleźć (nie powinien być śledzony przez repozytorium), to można go usunąć z repozytorium przy użyciu komendy git rm z parametrem --cached np.:
>git rm --cached nazwa.pliku

Plik zostanie usunięty z repozytorium, zmianę należy zacommitować.

Należy jednocześnie pamiętać, aby dodać jego nazwę do pliku .gitignore, aby w późniejszym czasie nie pojawiał się jako nie zastegowany plik.