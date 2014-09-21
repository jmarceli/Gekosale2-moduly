Moduł bloga
===
######Gekosale 2.0

Moduł pozwala na prowadzenie bloga poprzez Panel Administracyjny Gekosale. Dostępny jest w menu głównym w zakładce **CMS->Blog**.

## Tworzenie wpisów
Dla każdego wpisu możemy zdefiniować:

* autora
* widoczność autora (po odznaczeniu autor wpisu zostanie ukryty)
* datę dodania
* widoczność daty dodania (po odznaczeniu data dodania nie będzie wyświetlana)
* ewentualne wyróżnienie symbolizowane gwiazdką oraz możliwym do ustawienia tekstem (domyślnie jest to tekst "wyróżniony")
* tytuł wpisu
* adres pod którym dostępny będzie wpis
* widoczność wpisu (można tworzyć wpisy "na zapas" i potem tylko zmieniać ich widoczność z niewidoczny na widoczny)
* treść wpisu
* skrót wpisu (widoczny w widoku listy wpisów)
* zdjęcia (pokazywane w formie galerii zdjęć)
* informacje META

Jeśli wpis będzie miał podaną tylko skróconą treść i będzie tylko jedno zdjęcie to na liście wpisów nie pojawi się przycisk "Czytaj dalej". Jeśli podana zostanie tylko skrócona treść, bez żadnej treści właściwej to ta skrócona treść pojawi się zamiast treści właściwej na stronie wpisu.

## Prezentacja wpisów
Moduł udostępnia dwie dodatkowe podstrony, które domyślnie dostępne są pod adresami **blog** i **bloglist**. Te adresy można oczywiście zmienić w menu **Konfiguracja->Zaawansowane->Ustawienia adresów URL** dzięki temu możemy je dostosować do indywidualnych potrzeb np. **wpis**, **lista_wpisow**.

Do dyspozycji administratora są uprawnienia, które można przyznawać dowolnym grupom użytkowników. Ustawiane są w zakładce **Konfiguracja->Grupy użytkowników->[wybrana_grupa]->Uprawnienia**.

Dodane zostały również dwa nowe typy zawartości boksów:
### Wpis bloga
Powienien zostać stworzony przynajmniej jeden boks o tym typie i umieszczony na stronie o nazwie **Blog**. Boks tego typu jest odpowiedzialny za wyświetlenie odpowiedniego wpisu.

### Lista wpisów bloga
Ten typ boksu odpowiedzialny jest za wyświetlenie listy wpisów. Jeśli zostanie umieszczony na stronie o nazwie **Lista wpisów bloga** to wyświetli wszystkie wpisy. Na dole boksu pojawią się linki do kolejnych stron zawierających wpisy, natomiast na górze pojawi się filtracja po roku i miesiącu publikacja danego wpisu. Oczywiście w konfiguracji boksu możemy zdefiniować czy stronicowanie ma być widoczne oraz ile wpisów ma być widocznych na jednej stronie. Dodatkowo możliwe jest również ustawienie widoczności miniaturek dla poszczególnych wpisów. Miniaturki są robione ze zdjęcia w galerii ustawionego jako główne.

Boks tego typu umieszczony na innej podstronie niż **Lista wpisów bloga** wyświetli jedynie tytuły ostatnio dodanych wpisów. Można go zatem traktować również jako boks z listą najnowszych wpisów. Ilość wyświetlonych wpisów odpowiada wartości ustawionej jako ilość wpisów na stronie.
