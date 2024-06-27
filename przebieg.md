# Typowy przebieg pracy z repozytorium Git
Typowy proces pracy z kodem korzystając z kodu zapisanego w zdalnym repozytorium. Warto pamiętać, aby ten proces przeprowadzać przynajmniej raz dziennie. Jeśli praca toczy się w zespole to nawet częściej (po wprowadzeniu każdej ważnej poprawki/aktualizacji).

1. **git checkout main** - przejście do głównego brancha
2. **git pull** - pobranie najnowszej wersji ze zdalnego repozytorium
3. **git checkout -b branch_roboczy** - utworzenie roboczego brancha i przejście na niego
4. Wprowadzenie zmian w kodzie
5. **git add .** - dodanie do stage'a zapisanych zmian w kodzie
6. **git commit** - stworzenie commita z aktualnego stage'a
7. **git checkout main** - przejście na branch main
8. **git pull** - pobranie najnowszej wersji ze zdalnego repozytorium
9. **git checkout branch_roboczy** - przejście na branch roboczy
10. **git merge main** - połączenie brancha main z branchem roboczym (na wypadek wystąpienia konfilktów)
11. Ewentualne wyeliminowanie konfliktów
12. **git checkout main** - przejście na branch main
13. **git merge branch_roboczy** - połączenie brancha roboczego z branchem main (jeśli w kroku 10. nie pojawiły się konflikty)
14. **git pull** - upewnienie się, że w "między czasie" w zdalnym repozytorium nie pojawiła się nowsza wersja
15. **git push** - wypchnięcie kody wraz z poprawkami do zdalnego repozytorium
16. **git branch -d branch_roboczy** - usunięcie zbędnego brancha roboczego