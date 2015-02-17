Moduł Allegro
===
######Gekosale 2.0
Moduł pozwala na wystawianie aukcji allegro bezpośrednio z Panelu Administracyjnego sklepu na podstawie istniejących w sklepie produktów.

## Szablony
Szablony są automatycznie pobierane z folderu /themes/\[nazwa-szablonu-sklepu\]/templates/allegro/
Nazwa szablonu to nazwa pliku .tpl który go zawiera

## Zamówienia
Zamówienia złożone przez Allegro powinny być pobierane do sklepu za pomocą zadań okresowych tzw. Cron. Jeśli w zamówieniu pojawi się choćby jeden produkt dodany z poza tego modułu \(np. ręcznie\) to całe zamówienie jest ignorowane i nie pojawi się w sklepie na liście zamówień. Dzieje się tak ze względu na fakt, że każde zamówienie w Gekosale musi mieć przypisane produkty ze sklepu.
Synchronizacja poprzez Crone'a nie obejmuje zamówień będących aukcjami (czyli z licytacją zamiast "Kup teraz"), oraz zmian dokonywanych ręcznie poprzez panel Allegro po wystawieniu aukcji, nie są również synchronizowane odwołania ofert kupna.

## CRON
Skrypt Cron'a znajduje się w pliku `cron_allegro.php` należy wywołać go z argumentem oznaczającym identyfikator wybranego sklepu oraz nazwę wybranej operacji np. `php cron_allegro.php 3 deals`.
Operacje które powinny być co jakiś czas wykonywane za pomocą skryptu PHP:

- synchronizacja zamówień `php cron_allegro.php 3 deals`
- synchronizacja aukcji `php cron_allegro.php 3 auctions`
- synchronizacja drzewa kategorii `php cron_allegro.php 3 categories`

## Statusy pobranych zamówień
Pomimo ustawienia mapowania statusów nie są one niestety aktualizowane na bieżąco. Wynika to z faktu, że API Allegro nie informuje o zmianie statusu zamówienia.
## Mapowanie metod płatności oraz dostawy
W celu poprawnej integracji i pobierania zamówień należy ustawić mapowanie na odpowiednie metody w sklepie. Najwygodniej jest w tym celu stworzyć oddzielne metody, które nie będą wyświetlane \(zostaną ukryte poprzez wyłączenie w zakładce *Sklepy*\). W ten sposób będzie jasne które zamówienia pochodzą z Allegro.
## Faktury
Prośba klienta o wystawienie faktury jest oznaczana poprzez dodanie odpowiedniego tekstu w Komentarzu do zamówienia \(jedna z zakładek dostępnych podczas przeglądania zamówienia\)
## Zdjęcia
Moduł wykorzystuje dla miniaturek na Allegro styl odpowiadający największym zdjęciom ustawionym w sklepie *Konfiguraca->Globalna konfiguracja->Ustawienia galerii*
## Lista aukcji
Aukcje są synchronizowane z listą tylko poprzez zadania Crone'a albo kliknięcie przycisku synchronizacji znajdującego się nad listą. Jeśli ilość dni do końca aukcji jest mniejsz niż 3 to cyfra staje się czerwona, tak samo jeśli chodzi o ilość pozostałych na aukcji produktów.
## Zamówienia (edycja)
Podczas edycji zamówienia dostępne są wszystkie opcje które są dostępne normalnie, jedyna różnica jest taka że produkty w zamówieniu mają cenę za którą zostały kupione na allegro, oraz metoda wysyłki ma cenę wziętą z zamówienia Allegro

---

http://mygekosale.pl
