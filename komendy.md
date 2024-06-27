# Najważniejsze komendy Gita
Kilka najważniejszych komend Gita

## Praca z lokalnym repozytorium
* **git init** - komenda do inicjowania repozytorium
* **git status** - komenda do sprawdzania aktualnego statusu (m.in. czy wprowadzone zostały zmiany)
* **git clone https://github.com/...** - komenda do klonowania zdalnego repozytorium do lokalnej maszyny
* **git log** - pozwala sprawdzić historię commitów zapisaną w repozytorium

## Praca z commitami
* **git restore nazwa.pliku** - cofnięcie niechcianych zmian wprowadzonych w pliku o nazwie nazwa.pliku, po jego zapisaniu a przed wprowadzeniem go do stage'a
* **git add nazwa.pliku** - dodanie do stage'a pliku o nazwie nazwa.pliku
* **git add .** - dodanie wszystkich zapisanych zmian do stage'a
* **git commit** - zapisanie zmian w repozytorium przy użyciu commita (otwiera edytor tekstu); jeśli w używane są issue'sy to warto użyć linkowania używając znaku # i nr issue
* **git commit -m "Tytuł Commita"** - zapisanie zmian w repozytorium przy użyciu commita o tytule: Tytuł Commita (z pominięciem edytora tekstu)
* **git commit --ammend -m "Poprawiony błąd"** - poprawienie ostatniego commita (zarówno jego zawartości jak i tylko samej nazwy)

## Cofanie zmian
* **git rm --cached nazwa.pliku** - usunięcie pliku o nazwie nazwa.pliku z repozytorium (należy dodatkowo umieścić jego nazwę w pliku .gitignore)
* **git revert SHA1** - cofnięcie zmian wprowadzonych w konkretnym commicie przy użyciu SHA1 tego commita (nie jest to jego usunięcie!)

## Praca na branchach
* **git branch** - sprawdzenie jakie branche są dostępne
* **git branch nowy_branch** - stworzenie nowego brancha o nazwie nowy_branch (bez przenoszenia się na niego)
* **git checkout nowy_branch** - przeniesienie się na branch o nazwie nowy_branch
* **git checkout -b nowy_branch** - utworzenie nowego brancha o nazwie nowy_branch i przeniesienie się na niego
* **git branch -d stary_branch** - usunięcie starego niepotrzebnego brancha
* **git merge main** - łączenie main brancha z aktualnym branchem (o ile nie ma konfliktów)

## Praca ze zdalnym repozytorium
* **git pull** - pobranie zmian ze zdalnego repozytorium
* **git push** - przesłanie zapisanych commitów do zdalnego repozytorium
* **git reset --hard origin/main** - zresetowanie brancha do ostatnio pobieranej wersji ze zdalnego repozytorium