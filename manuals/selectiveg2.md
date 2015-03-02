Moduł Integracja selektywna
===
###### Gekosale 2.0

Moduł pozwalający na udostępnianie jedynie części oferty sklepu serwisowi porównywującemu ceny np. Ceneo (http://ceneo.pl)

Moduł po zainstalowaniu dostępny jest w zakładce **Integracja->Integracja selektywna**

# Konfiguracja
W celu poprawnej pracy modułu należy najpierw poprawnie skonfigurować domyślne moduły integrujące sklep z wybranymi porównywarkami (zakładka **Integracja->Lista porównywarek**). Dotyczy to przede wszystkim Ceneo, ponieważ do poprawnego działania wymaga ono ustawienia odpowiedniego mapowania kategorii dla każdej z kategorii sklepowych. Mapowanie wykonuje się w zakładce **Katalog->Kategorie** dla każdej kategorii osobno.

**UWAGA!** Jeśli lista kategorii Ceneo jest pusta to należy wejść w Integracja->Lista porównywarek kliknąć Ceneo.pl i poczekać (system ściągnie wtedy listę kategorii).

**UWAGA 2!** Jeśli produkt nie ma ustawionego zdjęcia głównego to nie zostanie uwzględniony w XML'u Ceneo (jest to problem systemu Gekosale niezależny od tego modułu)


W zakładce ustawienia na podstronie modułu można ustawić domyślną nazwę producenta dla produktów, jest to niezbędne ponieważ niektóre porównywarki nie akceptują braku nazwy producenta dla produktu.

Moduł zakłada, że podstawową walutą sklepu w której podane są ceny produktów jest złotówka.

Moduł gwarantuje wyświetlanie najniższej dostępnej ceny jeśli produkt posiada kilka wariantów w różnych cenach.

# Opcje
Moduł umożliwia ustawienie minimalnego stanu magazynowego poniżej którego produkt przestanie być widoczny dla porównywarek cenowych.
Dostępna jest również możliwość włączania lub wyłączania wszystkich produktów w wybranej kategorii za pomocą jednego przycisku.

Obecnie moduł **nie jest przystosowany** do stosowania w konfiguracji MULTISTORE.

# Wsparcie
Na chwilę obecną moduł wspiera następujące porównywarki cenowe:
- ceneo.pl
- nokaut.pl
- skapiec.pl
- okazje.info

---
http://mygekosale.pl
