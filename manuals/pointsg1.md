System punktów dla Gekosale 1.4.3
===

Za każde X złotych klient dostaje jeden punkt. Za Y punktów można wybrać darmową przesyłkę, a za Z punktów rabat A złotych. Wartości X, Y, Z, A mogą być indywidualnie dopasowne w zależności od potrzeb.
Użytkownik ma możliwość sprawdzenia ilości zebranych punktów na swoim koncie po zalogowaniu się i przejściu do podglądu swojego konta.
Jeśli użytkownik nie ma wystarczającej liczby punktów to w koszyku pojawia się informacja o ilości brakujących punktów potrzebnych do wybrania darmowej przesyłki lub rabatu.

Punkty są przydzielane dopiero po opłaceniu przez użytkownika złożonego zamówienia. Weryfikacja opłacenia odbywa się na bazie statusu zamówienia. W ustawieniach modułu można wybrać jakie statusy zamówienia będą powodowały przyznanie punktów. Punkty za zamówienie są przyznawane tylko raz, jeśli zostały już przyznane to nie zostaną przyznane ponownie.

Należy w panelu administracyjnym sprawdzić ustawienie sufixa ujemnego dla walut, ponieważ domyślnie brakuje tam spacji przed symbolem waluty. Zmienić to można w zakładce **Konfiguracja->Waluty** po wybraniu interesującej nas waluty.

Moduł wykonany jest dla namespace **myns** należy takie właśnie namespace ustawić w **Konfiguracja->Multistore->Sklepy->[nazwa sklepu]** i nie zmieniać.

W celu uwzględnienia programu lojalnościowego w szablonach email można wejść w **CRM->Szablony transakcyjne->Szablony transakcyjne** i wybrać **Odśwież szablonami standardowymi** (**UWAGA!** po tej operacji wszelkie zmiany wykonane dotychczas w szablonach e-mail zostaną utracone)
