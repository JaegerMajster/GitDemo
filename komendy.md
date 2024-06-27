# Najważniejsze komendy Gita
Kilka najważniejszych komend Gita

* **git init** - komenda do inicjowania repozytorium
* **git status** - komenda do sprawdzania aktualnego statusu (m.in. czy wprowadzone zostały zmiany)
* **git add nazwa.pliku** - dodanie do stage'a pliku o nazwie nazwa.pliku
* **git add .** - dodanie wszystkich zapisanych zmian do stage'a
* **git commit** - zapisanie zmian w repozytorium przy użyciu commita (otwiera edytor tekstu)
* **git commit -m "Tytuł Commita"** - zapisanie zmian w repozytorium przy użyciu commita o tytule: Tytuł Commita (z pominięciem edytora tekstu)
* **git log** - pozwala sprawdzić historię commitów zapisaną w repozytorium
* **git branch** - sprawdzenie jakie branche są dostępne
* **git branch nowy_branch** - stworzenie nowego brancha o nazwie nowy_branch (bez przenoszenia się na niego)
* **git checkout nowy_branch** - przeniesienie się na branch o nazwie nowy_branch
* **git checkout -b nowy_branch** - utworzenie nowego brancha o nazwie nowy_branch i przeniesienie się na niego
* **git branch -d stary_branch** - usunięcie starego niepotrzebnego brancha
* **git merge main** - łączenie main brancha z aktualnym branchem (o ile nie ma konfliktów)