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
### Adresy
Allegro przesyła nazwę ulicy, numer domu i numer mieszkania w formie jednego ciągu znaków. Moduł przetwarza adres starając się ustalić wartości dla pól: **numer domu** oraz **numer mieszkania**, ponieważ tego typu operacja nie jest możliwa w każdym przypadku to jako wartość pola **nazwa ulicy** wpisywany jest automatycznie cały ciąg znaków otrzymanych od Allegro. Wspierane formaty adresów dla których automatyczne rozpoznawanie działa wyglądają następująco:

- Ulica 11b m.123
- Ulicąęa 11/123
- Uliźćę©łca 11-123
- Ulica 11
- Ulica 11c 123
- Ulica 11m123
- Ulica 11m123 (budynek C)
- Nazwa ulicy 11 m.123
- 123 Ulica 11
- 123-nazwa ulicy 11b m.123
#### Kraj
Kraj rozpoznawany jest po nazwie kraju otrzymywanej z Allegro, przyjęte jest założenie że Allegro przesyła polską nazwę kraju, a w sklepie istnieje język polski i ma on ID = 1.

## CRON
Skrypt Cron'a znajduje się w pliku `cron_allegro.php` należy wywołać go z argumentem oznaczającym identyfikator wybranego sklepu oraz nazwę wybranej operacji np. `php cron_allegro.php 3 deals`.
Operacje które powinny być co jakiś czas wykonywane za pomocą skryptu PHP:

- synchronizacja zamówień `php cron_allegro.php 3 deals`
- synchronizacja aukcji `php cron_allegro.php 3 auctions`
- synchronizacja drzewa kategorii `php cron_allegro.php 3 categories`

## Pobieranie kategorii allegro
Obecnie możliwe tylko poprzez automatyczne zadania CRON'a

## Statusy pobranych zamówień
Pomimo ustawienia mapowania statusów nie są one niestety aktualizowane na bieżąco. Wynika to z faktu, że API Allegro nie informuje o zmianie statusu zamówienia.

## Mapowanie metod płatności oraz dostawy
W celu poprawnej integracji i pobierania zamówień należy ustawić mapowanie na odpowiednie metody w sklepie. Najwygodniej jest w tym celu stworzyć oddzielne metody, które nie będą wyświetlane \(zostaną ukryte poprzez wyłączenie w zakładce *Sklepy*\). W ten sposób będzie jasne które zamówienia pochodzą z Allegro.

## Faktury
Prośba klienta o wystawienie faktury jest oznaczana poprzez dodanie odpowiedniego tekstu w Komentarzu do zamówienia \(jedna z zakładek dostępnych podczas przeglądania zamówienia\)

## Zdjęcia
Moduł wykorzystuje dla miniaturek na Allegro styl odpowiadający największym zdjęciom ustawionym w sklepie *Konfiguraca->Globalna konfiguracja->Ustawienia galerii*
Jeśli dany produkt nie ma ustawionego oddzielnego zdjęcia wykorzystywanego do aukcji Allegro, to zostanie użyte zdjęcie oznaczone jako główne.

## Lista aukcji
Aukcje są synchronizowane z listą tylko poprzez zadania Crone'a albo kliknięcie przycisku synchronizacji znajdującego się nad listą. Jeśli ilość dni do końca aukcji jest mniejsz niż 3 to cyfra staje się czerwona, tak samo jeśli chodzi o ilość pozostałych na aukcji produktów.

## Zamówienia (edycja)
Podczas edycji zamówienia dostępne są wszystkie opcje które są dostępne normalnie, jedyna różnica jest taka że produkty w zamówieniu mają cenę za którą zostały kupione na allegro, oraz metoda wysyłki ma cenę wziętą z zamówienia Allegro

## Stany magazynowe
Automatycznie w momencie zmniejszenia stanu magazynowego z poziomu panelu administracyjnego moduł przeszukuje wszystkie aukcje dotyczące danego produktu i zmniejsza ilość dostępnych produktów jeżeli była większa od aktualnego stanu magazynowego. Jeżli nowoustawiony stan magazynowy to 0 to wszystkie aukcje zawierające ten produkt zostaną zakończone.

**UWAGA!** Jeżeli produkt jest wystawiony na kilku aukcjach to każda z nich zostanie potraktowana indywidualnie (ilość produktów nie zostanie zsumowana).

Opcja **Stan magazynowy** pozwala na zmniejszanie sklepowego stanu magazynowego w wybranym momencie. Istnieją 3 możliwe ustawienia:
1. Zmniejszanie po utworzeniu aukcji
2. Zmniejszanie po odnotowaniu sprzedaży na aukcji (zalecana częsta synchronizacja transkacji allegro)
3. Wcale (wystawianie przedmiotów na allegro nie ma wpływu na stany magazynowe)

Za pomocą opcji **Zmniejszanie ilości na aukcji** można ustawić zmniejszanie ilości produktów wystawionych na aukcji w przypadku sprzedaży danego produktu w sklepie internetowym.
Każdy zakup produktu w sklepie będzie powodował sprawdzenie, czy nie jest on aktualnie wystawiony.
Jeśli produkt jest wystawiony na aukcji to jego ilość zostanie pomniejszona o ilość kupioną przez klienta sklepu internetowego. Modyfikowana będzie tylko jedna najszybciej kończąca się aukcja (jeśli produkt jest wystawiony na wielu).

Opcja **Wystaw na auckcji wszystkie produkty** pozwala na domyślne wypełnianie pola ilości podczas tworzenia aukcji wartością aktualnego stanu magazynowego.
W przypadku niezaznaczenia tej opcji wystawiana jest domyślnie tylko jedna sztuka danego produktu.
Oczywiście wypełnienie pola **Ilość na aukcji** na karcie produktu ma pierwszeństwo przed tym ustawieniem.

Opcja **Zwiększaj ilość na aukcji wraz z dodawaniem produktóœ w sklepie** spowoduje że w przypadku zwiększenia stanu magazynowego danego produktu jego ilość na aukcji również się zwiększy.


## Paczka w Ruchu
Moduł wspiera integrację z modułem Paczka w Ruchu. Zamówienia złożone na Allegro z wybraną dostawą przez Paczkę w Ruchu zostaną przeniesione do sklepu wraz z wyborem kiosku.

---

http://mygekosale.pl
