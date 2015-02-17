Moduł SMS API
===
###### Gekosale 2.0

Moduł integrujący sklep z serwisem SMS API (http://smsapi.pl). Pozwala na wysyłanie newslettera SMS do wybranych klientów oraz na wysyłanie SMSów po zmianie statusu zamówienia.

Moduł po zainstalowaniu dostępny jest w zakładce **Integracja->SMSAPI**

# Konfiguracja
W celu uruchomienia modułu należy wypełnić pola:
* Login - login do systemu SMSAPI
* Hasło - hasło do systemu SMSAPI

Hasło do SMSAPI należy ustawić w panelu serwisu SMSAPI w zakładce **Ustawienia API->Hasło do API** (https://ssl.smsapi.pl/client_api/password). W module podajemy hasło normalnie **nie** w formie zaszyfrowanej przez MD5 (moduł sam wykonuje takie szyfrowanie przed wysłaniem zapytania do serwisu SMSAPI).

W zakładce ustawienia można ustawić teksty wiadomości jakie będą wysyłane gdy zamówienie osiąga kolejne statusy. Pozostawienie pustego pola oznacza, że żadna wiadomość nie zostanie wysłana.
Przy tworzeniu wiadomości mamy do dyspozycji następujące znaczniki:
* %imie% - zostanie zastąpione imieniem użytkownika do którego wysyłany jest SMS (jest to imię podane podczas składania zamówienia w formularzu danych płatnika)
* %nazwisko% - zostanie zastąpione nazwiskiem użytkownika do którego wysyłany jest SMS (jest to nazwisko podane podczas składania zamówienia w formularzu danych płatnika)
* %kod_sledzenia% - zostanie zastąpiony kodem śledzenia Sendit (**opcja dostępna tylko w przypadku jednoczesnego korzystania z modułu Sendit dostarczonego przez http://mygekosale.pl**, należy również zaznaczyć pole **Integracja Sendit**, aby ten znacznik był dostępny)

Moduł umożliwia wysyłkę dowolnej ilości SMSów na raz.

Moduł wyposażony jest w opcje:
* Nadawca SMS'a - pozwala określić pole nadawcy zgodnie z możliwościami dostępnymi w serwisie SMSAPI (**ECO**, **2way**, **PRO**)
* Tryb testowy - pozwalającą na symulację wysyłki bez faktycznego wysłania wiadomości
* Pomiń zagraniczne numery - pozwala na automatyczne pominięcie wysyłki na zagraniczne numery
* Usuń znaki specjalne - automatyczna zamiana np. polskich liter na ich odpowiedniki ą -> a itd. dzięki czemu wiadomości mają mniejszy rozmiar, a co za tym idzie są tańsze

---
http://mygekosale.pl
