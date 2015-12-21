Moduł API dla Gekosale
===
###### Gekosale 2.0

#Informacje ogólne:
To API zbudowane jest jako usługa RESTowa udostępniająca zasoby sklepu poprzez obsługę zapytań GET protokołu HTTP. Jako odpowiedź na otrzymane zapytanie serwis zwraca wynik w postaci struktury XML. API zwraca wyniki zgodne z domyślnym językiem i walutą z którymi przeglądany jest sklep (domyślnie POLSKI i waluta PLN). Zwracane są tylko elementy widoczne w sklepie.

API służy jedynie do pobierania informacji (tylko metoda GET), 

# Klucz:
Obecnie obsługiwany jest jeden klucz dla wszystkich użytkowników korzystających z API. Można go ustawić w panelu sterowania w zakładce 'Moduł API'. Klucz jest wymagany.

Klucz powinien być umieszczony w każdym przesyłanym zapytaniu jako jeden z jego parametrów:

http://api.mygekosale.pl/api/products?key=ustawiony_klucz_api

# Wielojęzyczność:
Jeżeli sklep obsługuje więcej niż jeden język opisy w odpowiednim języku możesz pobrać dodając do zapytania parametr `lang` z odpowiednim **kodem** języka.
Przykład:

<http://api.mygekosale.pl/api/categories?key=ustawiony_klucz_api&lang=en_EN>

Powyższe zapytanie zwróci angielskie opisy jeżeli `en_EN` jest poprawnym kodem języka dla języka angielskiego. W celu uzyskania kodów języka należy skontaktować się z obsługą sklepu.

**UWAGA!**
Obsługa sklepu może znaleźć kody poszczególnych języków w zakładce **Konfiguracja -> Język**. Kody języków są wypisane w kolumnie **Nazwa**.

# Parametry zapytań:
API udostępnia dwa rodzaje zapytań.

1. Zapytanie o produkty:

  <http://api.mygekosale.pl/api/products?key=ustawiony_klucz_api>

2. Zapytanie o kategorie:

  <http://api.mygekosale.pl/api/categories?key=ustawiony_klucz_api>

Każde zapytanie może odnosić się do listy elementów (tak jak powyższe) lub do konkretnego elementu na przykład:

<http://api.mygekosale.pl/api/categories/751?key=ustawiony_klucz_api>

Każde zapytanie o listę może przyjmować szereg atrybutów:

* list - jeśli zadeklarowany wyświetlona zostanie lista zawierająca tylko nazwy elementów oraz ich ID w innym wypadku wyświetlana jest szczegółowa lista wyników zawierająca wszystkie udostępniane przez API informacje
  <http://api.mygekosale.pl/api/products?key=ustawiony_klucz_api&list>

* per_page=# - ilość wyników na jednej stronie (domyślnie 10), wartość 0 oznacza wszystkie wyniki na jednej stronie
  <http://api.mygekosale.pl/api/products?key=ustawiony_klucz_api&per_page=15>
  <http://api.mygekosale.pl/api/products?key=ustawiony_klucz_api&per_page=0>

* page=# - numer aktualnie przeglądanej strony (domyślnie 1)

  <http://api.mygekosale.pl/api/products?key=ustawiony_klucz_api&page=2>

  <http://api.mygekosale.pl/api/products?key=ustawiony_klucz_api&page=4>

* categoryid=# - dotyczy tylko zapytań o listę produktów, umożliwia wyświetlenie produktów należących tylko do wybranej kategorii na podstawie podanego id, (domyślna wartość 0 - oznacza brak filtrowania)

  <http://api.mygekosale.pl/api/products?key=ustawiony_klucz_api&categoryid=751>

Przy zapytaniach o konkretny element użycie jednego z wyżej opisanych atrybutów nie powinno mieć miejsca i może zwrócić niewłaściwy rezultat.

Parametry przy zapytaniach o listę można kumulować i zamieniać miejscami:

<http://api.mygekosale.pl/api/products?key=ustawiony_klucz_api&page=2&per_page=15&list>

---
# Dostępne zapytania

## Kategorie:
### Widok listy (parametr &list w zapytaniu):
<http://api.mygekosale.pl/api/categories?key=ustawiony_klucz_api&list>

    <categories total="7" page_total="7" last_page="1" page_number="1">
    <category id="752"><name>Artykuły chemiczne</name></category>
    ...
    </categories>

### Elementy
element | opis
-------------  | -------------
categories | zewnętrzny element zbierający listę wszystkich kategorii
category | element oznaczający kategorię
name | nazwa konkretnej kategorii

### Atrybuty elementów

#### categories
atrybut | opis
-------------  | -------------
@total | całkowita ilość kategorii
@page_total | ilość kategorii na tej stronie
@last_page | numer ostatniej strony
@page_number | numer aktualnie przeglądanej strony

#### category
atrybut | opis
-------------  | -------------
@id | identyfikator kategorii

### Widok listy ze szczegółami (brak parametru &list w zapytaniu):
<http://api.mygekosale.pl/api/categories?key=ustawiony_klucz_api>

    <categories total="7" page_total="7" last_page="1" page_number="1">
    <category id="752" parentid="0">
    <name>Artykuły chemiczne</name>
    <seo>artykuly-chemiczne</seo>
    <products>3</products>
    </category>
    ...
    </categories>

### Elementy
element | opis
-------------  | -------------
categories | zewnętrzny element zbierający listę wszystkich kategorii
category | element oznaczający kategorię
name | nazwa kategorii
seo | ciąg znaków będący elementem adresu URL kategorii
products | ilość produktów znajdujących się w kategorii

### Atrybuty elementów

#### categories
atrybut | opis
-------------  | -------------
@total | całkowita ilość kategorii
@page_total | ilość kategorii na tej stronie
@last_page | numer ostatniej strony
@page_number | numer aktualnie przeglądanej strony

#### category
atrybut | opis
-------------  | -------------
@id | identyfikator kategorii
@parentid | identyfikator kategorii nadrzędnej (0 - jeśli brak kategorii nadrzędnej)

### Widok wybranej kategorii (w przykładzie kategoria o ID = 751):
<http://api.mygekosale.pl/api/categories/751?key=ustawiony_klucz_api>

    <categories total="1" page_total="1" last_page="1" page_number="1">
    <category id="752" parentid="0">
    <name>Artykuły chemiczne</name>
    <seo>artykuly-chemiczne</seo>
    <products>3</products>
    </category>
    </categories>

### Elementy
element | opis
-------------  | -------------
categories | zewnętrzny element
category | element oznaczający kategorię
name | nazwa kategorii
seo | ciąg znaków będący elementem adresu URL kategorii
products | ilość produktów znajdujących się w kategorii

### Atrybuty elementów

#### categories
atrybut | opis
-------------  | -------------
@total | całkowita ilość kategorii
@page_total | ilość kategorii na tej stronie
@last_page | numer ostatniej strony
@page_number | numer aktualnie przeglądanej strony

#### category
atrybut | opis
-------------  | -------------
@id | identyfikator kategorii
@parentid | identyfikator kategorii nadrzędnej (0 - jeśli brak kategorii nadrzędnej)

---

## Produkty:
### Widok listy (parametr &list w zapytaniu):
<http://api.mygekosale.pl/api/products?key=ustawiony_klucz_api&list>

    <products total="34" page_total="10" last_page="4" page_number="1">
    <product id="689"><name>.NET CLR. Księga eksperta</name>
    </product>
    ...
    </products>

### Elementy
element | opis
-------------  | -------------
products | zewnętrzny element zbierający listę wszystkich produktów
product | element oznaczający produkt
name | nazwa produktu
stock | aktualny stan magazynowy

### Atrybuty elementów
#### products
atrybut | opis
-------------  | -------------
@total | całkowita ilość produktów
@page_total | ilość produktów na tej stronie
@last_page | numer ostatniej strony
@page_number | numer aktualnie przeglądanej strony

#### product
atrybut | opis
-------------  | -------------
@id | identyfikator produktu

### Widok listy ze szczegółami (brak parametru &list w zapytaniu):
<http://api.mygekosale.pl/api/products?key=ustawiony_klucz_api>

    <products total="34" page_total="10" last_page="4" page_number="1">
    <product id="702">
    <shortdescription><p>
      Wulkanizowana guma daje maksimum przyczepności i dużą odporność na ścieranie. To są buty prawdziwie przeznaczone do zadań specjalnych!</p></shortdescription>
    <longdescription>Jakiś tekst</longdescription>
    <additionalinfo>Dodatkowe informacje</additionalinfo>
    <name>Emerica Westgate</name>
    <vat>23.00</vat>
    <pricenetto>162.6016</pricenetto>
    <finalprice>200.00</finalprice>
    <currencysymbol>PLN</currencysymbol>
    <stock>210</stock>
    <photos>
    <photo id="1088" mainphoto="1">http://api.localhost/design/_gallery/_orginal/1088.jpg</photo>
    ...
    </photos>
    </product>
    ...
    </products>

### Elementy
element | opis
-------------  | -------------
products | zewnętrzny element zbierający listę wszystkich produktów
product | element oznaczający produkt
shortdescription | krótki opis produktu (w znacznikach CDATA, może zawierać znaczniki HTML)
longdescription | pełny opis produktu (w znacznikach CDATA, może zawierać znaczniki HTML)
additionalinfo | dodatkowe informacje o produkcie (w znacznikach CDATA, może zawierać znaczniki HTML)
name | nazwa produktu
vat | stawka VAT na produkt
pricenetto | cena netto produktu
finalprice | cena brutto (po uwzględnieniu ewentualnych promocji)
currencysymbol | symbol waluty w której podana jest cena
stock | stan magazynowy produktu
photos | lista zdjęć produktu
photo | zdjęcie produktu


### Atrybuty elementów
#### products
atrybut | opis
-------------  | -------------
@total | całkowita ilość produktów
@page_total | ilość produktów na tej stronie
@last_page | numer ostatniej strony
@page_number | numer aktualnie przeglądanej strony

#### product
atrybut | opis
-------------  | -------------
@id | identyfikator produktu

#### photo
atrybut | opis
-------------  | -------------
@id | identyfikator zdjęcia
@mainphoto | czy zdjęcie jest zdjęciem głównym produktu (1 | tak, 0 | nie)


### Widok wybranego produktu (w przykładzie produkt o ID = 702):
<http://api.mygekosale.pl/api/products/702?key=ustawiony_klucz_api>

    <products total="1" page_total="1" last_page="1" page_number="1">
    <product id="702">
    <shortdescription><p>
      Wulkanizowana guma daje maksimum przyczepności i dużą odporność na ścieranie. To są buty prawdziwie przeznaczone do zadań specjalnych!</p></shortdescription>
    <longdescription></longdescription>
    <additionalinfo></additionalinfo>
    <name>Emerica Westgate</name>
    <vat>23.00</vat>
    <pricenetto>162.6016</pricenetto>
    <finalprice>200.00</finalprice>
    <currencysymbol>PLN</currencysymbol>
    <stock>210</stock>
    <photos>
    <photo id="1088" mainphoto="1">http://api.localhost/design/_gallery/_orginal/1088.jpg</photo>
    <photo id="1089" mainphoto="0">http://api.localhost/design/_gallery/_orginal/1089.jpg</photo>
    <photo id="1090" mainphoto="0">http://api.localhost/design/_gallery/_orginal/1090.jpg</photo>
    <photo id="1091" mainphoto="0">http://api.localhost/design/_gallery/_orginal/1091.jpg</photo>
    <photo id="1092" mainphoto="0">http://api.localhost/design/_gallery/_orginal/1092.jpg</photo>
    <photo id="1093" mainphoto="0">http://api.localhost/design/_gallery/_orginal/1093.jpg</photo>
    <photo id="1094" mainphoto="0">http://api.localhost/design/_gallery/_orginal/1094.jpg</photo>
    </photos>
    </product>
    </products>

### Elementy
element | opis
-------------  | -------------
products | zewnętrzny element
product | element oznaczający produkt
shortdescription | krótki opis produktu (w znacznikach CDATA, może zawierać znaczniki HTML)
longdescription | pełny opis produktu (w znacznikach CDATA, może zawierać znaczniki HTML)
additionalinfo | dodatkowe informacje o produkcie (w znacznikach CDATA, może zawierać znaczniki HTML)
name | nazwa produktu
vat | stawka VAT na produkt
pricenetto | cena netto produktu
finalprice | cena brutto (po uwzględnieniu ewentualnych promocji)
currencysymbol | symbol waluty w której podana jest cena
stock | stan magazynowy produktu
photos | lista zdjęć produktu
photo | zdjęcie produktu

### Atrybuty elementów

#### products
atrybuty | opis
-------------  | -------------
@total | całkowita ilość produktów
@page_total | ilość produktów na tej stronie
@last_page | numer ostatniej strony
@page_number | numer aktualnie przeglądanej strony

#### product
atrybuty | opis
-------------  | -------------
@id | identyfikator produktu

#### photo
atrybuty | opis
-------------  | -------------
@id | identyfikator zdjęcia
@mainphoto | czy zdjęcie jest zdjęciem głównym produktu (1 | tak, 0 | nie)

---

http://mygekosale.pl
