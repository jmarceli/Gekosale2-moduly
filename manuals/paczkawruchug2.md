Moduł Paczka w Ruchu
===
###### Gekosale 2.0

Moduł integrujący sklep z serwisem Paczka w Ruchu. Pozwala na wybór przez klientów punktu odbioru przesyłki oraz na wygodne generowanie etykiet na paczki i wysyłanie ich bezpośrednio z panelu administracyjnego sklepu.

Moduł po zainstalowaniu dostępny jest w zakładce **Integracja->Paczka w Ruchu**

# Konfiguracja
Konfiguracja modułu dostępna jest w zakładce "Ustawienia". Należy w niej po pierwsze podać niezbędne dane dostępowe do serwisu **Paczka w Ruchu** otrzymane od obsługi.

Dostępne jest pole odpowiedzialne za wymuszenie pobierania etykiet w formie pliku PDF, lub jeśli nie zostanie ono zaznaczone to etykiety będą otwierane bezpośrednio w oknie przeglądarki.

Kolejne pole odpowiada za ustawienie odpowiednich metod wysyłki. Zaznaczone metody będą traktowane jako realizowane przez **Paczkę w Ruchu**, a więc klient przy ich wyborze będzie mógł zdefiniować punkt (kiosk) w którym odbierze paczkę.

Ustawienie automatycznych statusów pozwoli na automatyczną zmianę statusu zamówienia po wystąpieniu określonych akcji: wysłanie przesyłki, wydrukowanie etykiety. Zaznaczenie pola odpowiedzialnego za mailowe powiadamianie klienta spowoduje dodatkowe generowanie odpowiedniego maila po automatycznej zmianie statusu.

Statusy zrealizowanych zamówień pozwalają zachować porządek na liście paczek poprzez ukrycie na niej zamówień których realizacja została zakończona bądź które zostały anulowane. Należy wybrać odpowiednie statusy dla których zamówienia mają znikać z listy paczek **Paczka w Ruchu**.

Zakładka dane nadawcy pozwala na ustawienie danych które pojawią się na etykiecie w polu nadawca. Wartości wymagane zostały oznaczone pogrubioną czcionką.

Lista paczek **Paczka w Ruchu** zawiera wszystkie zamówienia dla których została wybrana odpowiednia metoda wysyłki. Dla każdego zamówienia dostępne są następujące akcje (patrząc od lewej):
- Otworzenie szczegółów zamówienia
- Nadanie paczki **Paczka w Ruchu** (paczka otrzyma unikatowy identyfikator)
- Wydruk etykiety
- Śledzenie aktualnego statusu paczki przy pomocy serwisu **Paczka w Ruchu**
- Odświeżenie statusu paczki
- Anulowanie wysyłki paczki

Statusy paczek na liście ze względów wydajnościowych nie są automatycznie odświeżane. Można to zrobić klikając odpowiednią ikonę dla wybranej paczki na liście, lub klikając przycisk **Aktualizuj statusy**, który zaktualizuje statusy wszystkich przesyłanych paczek.

Dodane zostało ustawienie pozwalające określić metody wysyłki za pobraniem.

Paczki dla które zostaną wysłane wspólnie będą również miały jeden wspólny plik PDF z etykietami. Nawet po anulowaniu jednej z paczek wygenerowany plik PDF dalej będzie zawierał etykiety wszystkich wspólnie wysłanych paczek. Można to zmienić za pomocą opcji "Wiele etykiet w jednym pliku" która po odznaczeniu będzie generowała każdą etykietę w oddzielnym pliku PDF.

---
http://mygekosale.pl
