Integracja z Pocztą Polską Gekosale 2
===
######Gekosale 2.0

Integracja pozwala na proste dodawanie przesyłek do serwisu internetowego Poczty Polskiej (https://e-nadawca.poczta-polska.pl).

Obecnie wspierane są usługi:
- Pocztex Krajowy, Miejski, Bezpośredni, Ekspres
- Pocztex Kurier 48 (Przesyłka biznesowa)
- Paczka 24, 48, Extra

Moduł pozwala na zdefiniowanie maksymalnie dwóch różnych kont które następnie można przypisać do wybranej usługi. Do formularza zamówienia dodawane są dwa przyciski **Pocztex** oraz **Paczka** pozwalające szybko dodać wybrane zamówienie do serwisu Poczty Polskiej. Po dodaniu wyświetlany jest stosowny komunikat.

Możliwe jest ustawienie automatycznej zmiany statusu na wcześniej ustalony po wysłaniu przesyłki do serwisu Poczty. Dodatkowo wraz z dodaniem paczki do serwisu Poczty możliwe jest automatyczne wysyłanie maila do klienta z odpowiednim powiadomieniem. Szablon tego maila jest możliwy do edycji tak jak inne szablony Gekosale 2, czyli w plikach z szablonami.

Status po zamówieniu przesyłki jest ustawiany oddzielnie dla każdej metody wysyłki.

Dodane zostało pole **numer rachunku pobrania** oraz opcja wysłania za pobraniem dla usługi Pocztex. W tym przypadku na stałe wybrana jest opcja przelewu na wybrany numer konta który podajemy w ustawieniach w polu **numer rachunku pobrania**. Jako tytuł przelewu wpisany jest tekst: *Opłata za zamówienie nr. [numer_zamówienia]*, gdzie oczywiście [numer_zamówienia] zastępowane jest faktycznym numerem zamówienia.

Wybór metod wysyłki pozwala ustalić które zamówienia mogą być przesyłane Pocztą Polską. Jeżeli zamówienie ma inną wybraną metodę wysyłki to przyciski poczty nie pojawią się w edycji zamówienia, a ewentualna próba wysyłki tego zamówienia przez Pocztę Polską wyświetli odpowiedni komunikat z błędem.

**UWAGA!** W serwisie https://e-nadawca.poczta-polska.pl w zakładce *Ustawienia* w ramce *Inne* trzeba zaznaczyć opcję **Pokaż bufory webapi w przygotowanych** inaczej nie będą widoczne przesyłki wysłane za pomocą modułu.

Działanie modułu dla Gekosale 2 w konfiguracji multistore nie było testowane.

### Wersje
- v1.0 Integracja z Pocztex oraz Paczka
- v1.1 Dodana integracja z Pocztex Kurier 48
- v2.0 Pierwsza wersja współpracująca z Gekosale 2
- v2.1 Dodanie możliwości przesyłania wielu paczek jednocześnie do serwisu Poczty Polskiej z poziomu listy zamówień
- v2.11 Ograniczenie wysyłania zamówienia jeżeli metoda wysyłki jest inna niż wybrana w module
- v2.12 Opcja automatycznego odznaczania zamówień po wysłaniu, wsparcie dla szablonu RWD

---

http://mygekosale.pl
