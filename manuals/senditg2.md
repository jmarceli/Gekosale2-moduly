Moduł Sendit
===
######Gekosale 2.0
Integracja z serwisem Sendit. Obejmuje operatorów DPD, UPS oraz INPOST.

Moduł udostępnia stronę z listą wszystkich zamówień które spełniają ustalone w konfiguracji modułu kryteria dotyczące sposobu wysyłki oraz statusu. Dzięki ograniczeniu ze względu na metodę wysyłki zamówienia które nie mają zostać wysłane za pomocą Sendit nie pojawiają się naliście. Ograniczenie statusem zamówienia zapewnia ukrycie już zrealizowanych (zakończonych) zamówień tak, aby nie tworzyły niepotrzebnego bałaganu.

Po wejściu w edycję przesyłki można ustawić dane nadawcy (domyślnie brane z zamówienia) jak również inne jej parametry (waga, ilość paczek w przesyłce, kwota ubezpieczenia, kwota pobrania, paczkomat - jeśli dotyczy).
Moduł umożliwia również nadawanie przesyłek paletowych.

Kolejny krok to sprawdzenie dostępnych dla adresu odbiorcy usług. Wystarczy w tym celu kliknąć przycisk "Sprawdź dostępne usługi", po chwili pojawi się lista wszystkich dostępny usług z której można wybrać właściwe dla tej paczki (np. ubezpieczenie). Na koniec można wycenić paczkę u wszystkich obsługiwanych operatorów i na podstawie tej wyceny wybrać tego który nam odpowiada.

## Konfiguracja
Na początek należy podać login, hasło oraz klucz API. Poprawność wprowadzonych danych można sprawdzić wciskając przycisk Test połączenia.

Następnie można skonfigurować filtrowanie według metod wysyłki (opisywane wcześniej) oraz statusy dla zrealizowanych zamówień.

Dostępna jest również opcja domyślnej wagi paczki dla wysyłki Paczkomatami Inpost, która zostanie użyta w przypadku gdy obliczona waga zamówienia wynosi 0 (może się to wydarzyć jeśli produkty nie mają wpisanej wagi).

Opcja automatyczne statusy pozwala na automatyczne zmienianie statusów po osiągnięciu przez paczkę kolejnych etapów. Do ustawienia są możliwe trzy etapy:

* Przesyłka przesłana do Sendit
* Nalepka wydrukowana
* Protokół wydrukowany

Dla każdego z tych etapów możemy ustalić status, który zostanie automatycznie przypisany do zamówienia.

Oczywiście moduł umożliwia ustawienie danych nadawcy. Znajdują się tam wszystkie podstawowe informacje przesyłane do Sendit. Jeżeli zostanie wpisana nazwa firmy to będzie ona umieszczona w polu "Nazwy nadawcy" zamiast imienia i nazwiska. Imię i nazwisko będą zawsze przekazywane w polu "Osoba kontaktowa".

Ostatnia zakładka z ustwieniami zawiera dane konfiguracyjne dla usług operatora Inpost. Można tu ustawić paczkomat nadawczy, domyślny typ paczki oraz wartość ubezpieczenia. Ustawiona tutaj wartość ubezpieczenia będzie brana pod uwagę za każdym razem gdy podczas wysyłki paczki przez operatora Inpost zaznaczymy opcję "Ubezpieczenie".

Moduł ma wbudowany mechanizm zapisu listy dostępnych paczkomatów do pamięci podręcznej. Pamięć ta jest odświeżana każdorazowo przy wejściu na stronę konfiguracji modułu.

## Przydatne informacje
W celu wygenerowania jednego protokołu zbiorczego dla kilku przesyłek, nie należy klikać przycisku generuj protokół w edycji danej przesyłki tylko zamiast tego zaznaczyć na liście przesyłek wybrane pozycji i użyć przycisku zbiorczej generacji protokołu (pod listą przesyłek). Jeśli zostanie wygenerowany indywidualny protokół dla pojedynczej przesyłki to nie ma już możliwości wygenerowania dla tej przesyłki protokołu zbiorczego (z innymi przesyłkami).
Dodane zostało pole do wpisania komentarza (lub numeru dokumentu sprzedaży) oraz pole pozwalające wpisać zawartość przesyłki. Obydwa pola są opcjonalne.
Ponadto na liście przesyłek możliwe jest wyświetlenie pola numeru protokołu dla danej przesyłki oraz komentarza i opisu zawartości.

## Ograniczenia

* Paczkomaty mają ograniczoną maksymalną wagę przesyłanej paczki do 25kg.
* Wymiary paczek Inpost przypisane na stałe do typów A, B, C. Dzięki temu zamiast wpisywać wszystkie wymiary paczki wystarczy wybrać konkretny typ.
* Numer konta bankowego dla przesyłek za pobraniem należy ustawić bezpośrednio w serwisie Sendit w zakładce Moje konto (nie ma możliwości przesłania numeru konta w inny sposób)

---
http://mygekosale.pl
