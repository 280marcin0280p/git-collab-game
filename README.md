# git-collab-game
Prosta gra dla przećwiczenia współpracy w zespole podczas rozwijania jednego repozytorium

## ZESPÓŁ

Zespół składa się z trzech osób:
- osoba A - Release Manager
- osoba B - Programista Modułu
- osoba C - Tester Integrator

### Właściciel repozytorium
- Jedna osoba z zespołu wykonuje forka niniejszego repozytorium. 
- Na profilu właściciela pojawia się repozytorium LOGIN_GITHUB/git-collab-game.
- Właściciel daje dostęp do repozytorium osobom ze swojego zespołu:

  ```Repository → Settings → Collaborators → Add people```

## PRZYGOTOWANIE
- Każdy członek zespołu klonuje repozytorium od właściciela do lokalnego folderu (pendrive...)

## RUNDA 1: SZTAFETA PO MAIN/MASTER

__Cel:__ zobaczyć najprostszy przypadek synchronizacji, w którym pull --ff-only wykonuje fast-forward.

### 1. Osoba A - release manager - wykonuje:

```
git checkout main
git pull --ff-only
```

po czym edytuje plik `release-room/status.md`:
```
Koordynator: LOGIN_OSOBY_A
```

by finalnie:
1. dodać plik do stage'a
2. wykonać commita zmian
3. wypchnąć zmiany do origina

### Osoba B - programista modułu:
1. Czeka na sygnał od OSOBY A, że może działać
2. wykonuje:

```
git checkout main
git pull --ff-only
git log --oneline -5
```

3. Po potwierdzeniu, że w logu widać commit OSOBY A, edytuje plik `release-room/modules/logika.md`:
```
# Moduł logiki

Odpowiedzialny: LOGIN_OSOBY_B
Stan: GOTOWY
Opis zmiany: Dodano walidację danych wejściowych.
```

by finalnie:
1. dodać plik do stage'a
2. wykonać commita zmian
3. wypchnąć zmiany do origina

### Osoba C - tester integrator:
1. Czeka na sygnał od OSOBY B, że może działać
2. Wykonuje:

```
git checkout main
git pull --ff-only
git log --oneline -5
```

3. Po potwierdzeniu, że w logu widać commity OSOBY A i OSOBY B, edytuje plik `release-room/modules/testy.md`:
```
# Testy

Odpowiedzialny: LOGIN_OSOBY_C
Stan: GOTOWY
Opis zmiany: Sprawdzono podstawowe scenariusze wydania.
```

by finalnie:
1. dodać plik do stage'a
2. wykonać commita zmian
3. wypchnąć zmiany do origina

### WSZYSCY
1. Po sygnale od OSOBY C, że zakończyła pracę, wykonują:
```
git pull --ff-only
git log --oneline -5
```
