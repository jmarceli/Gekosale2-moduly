# Moduł utilities
Jest to czysto deweloperski moduł zawierający jedynie dodatkowe funkcje dla Gekosale pozwalające w prostszy sposób tworzyć właściwe moduły

# Instrukcja
Ogólny zamysł jest taki, że dodajemy branch utils_branch jako remote w wybranym repozytorium
```
git remote add utilsg2 /home/janek/www/geko/utilsg2/.git -t utils_branch
git fetch utilsg2
```

## Pull'owanie
Potem tworzymy w tym repozytorium oddzielny branch który będzie śledził zmiany
```
git co -b utilsg2_[nazwa_repo] utilsg2/utils_branch
```
Następnie merge'ujemy wszystko do branch master, czy tam gdzie akurat potrzebne są Utils
```
git co master
git merge utilsg2_[nazwa_repo]
```
Przy czym nazwa branch'a w docelowym repo jest ważna, żeby w razie pushowania zmian do głównego repo **utilsg2** było wiadomo skąd się wzięły

## Push'owanie zmian
Ze względu na ustawioną w .gitconfig metodę push'owania **simple** przy pushowaniu trzeba zadeklarować do jakiego branch'a w remote repo mając zostać przesłane zmiany
```
git push utilsg2 HEAD:utils_branch
```
