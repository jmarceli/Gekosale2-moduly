Integracja z Pocztą Polską
===
######Gekosale 1.4

Integracja pozwala na proste dodawanie przesyłek do serwisu internetowego Poczty Polskiej (https://e-nadawca.poczta-polska.pl).

Obecnie wspierane są usługi:
- Pocztex Krajowy, Miejski, Bezpośredni, Ekspres
- Pocztex Kurier 48 (Przesyłka biznesowa)
- Paczka 24, 48, Extra

Moduł pozwala na zdefiniowanie maksymalnie dwóch różnych kont które następnie można przypisać do wybranej usługi. Do formularza zamówienia dodawane są dwa przyciski **Pocztex** oraz **Paczka** pozwalające szybko dodać wybrane zamówienie do serwisu Poczty Polskiej. Po dodaniu wyświetlany jest stosowny komunikat.

Możliwe jest ustawienie automatycznej zmiany statusu na wcześniej ustalony po wysłaniu przesyłki do serwisu Poczty. Dodatkowo wraz z dodaniem paczki do serwisu Poczty możliwe jest automatyczne wysyłanie maila do klienta z odpowiednim powiadomieniem. Szablon tego maila można edytować w standardowy sposób.

Status po zamówieniu przesyłki jest ustawiany oddzielnie dla każdej metody wysyłki.

Dodane zostało pole **numer rachunku pobrania** oraz opcja wysłania za pobraniem dla usługi Pocztex. W tym przypadku na stałe wybrana jest opcja przelewu na wybrany numer konta który podajemy w ustawieniach w polu **numer rachunku pobrania**. Jako tytuł przelewu wpisany jest tekst: *Opłata za zamówienie nr. [numer_zamówienia]*, gdzie oczywiście [numer_zamówienia] zastępowane jest faktycznym numerem zamówienia.

**UWAGA!** W serwisie https://e-nadawca.poczta-polska.pl w zakładce *Ustawienia* w ramce *Inne* trzeba zaznaczyć opcję **Pokaż bufory webapi w przygotowanych** inaczej nie będą widoczne przesyłki wysłane za pomocą modułu.

W celu wysyłania różnych maili ze sklepów w konfiguracji **multistore** niezbędne jest dodanie odpowiednich szablonów e-mail. Szablony te trzeba dodawać po przełączeniu się w Panelu Administracyjnym na konkretny sklep (przyciskiem obok wyboru języka). W polu **Akcja** należy ustawić opcję analogiczą do szablonu zdefiniowanego w sklepie globalnym.  Następnie należy nadać mu dowolną sensowną nazwę i wpisać odpowiednią **Treść Kod HTML** (najlepiej skopiować z szablonu globalnego). W Gekosale występuje błąd nie pozwalający zapisać nowego szablonu bez wpisania czegokolwiek w pole **Treść Tekst** z tego powodu przy dodawaniu szablonu trzeba tam wpisać kilka dowolnych znaków, a po zapisaniu szablonu wejść w jego edycję i je usunąć. Na koniec należy ustawić w każdym sklepie stworzony szablon jako domyślny.

### Wersje
- v1.0 Integracja z Pocztex oraz Paczka
- v1.1 Dodana integracja z Pocztex Kurier 48

---

http://mygekosale.pl
