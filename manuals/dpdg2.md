Moduł kuriera DPD
===
######Gekosale 2.0

Pozwala na automatyczne generowanie paczek i pobieranie gotowych do wydruku nalepek oraz protokołów dla kuriera (w formacie PDF).

Przed rozpoczęciem korzystania z modułu należy go skonfigurować w zakładce **Integracja->DPD** **Konfiguracja**. Podczas konfiguracji można użyć przycisku **Test połączenia** w celu sprawdzenia, czy wpisane dane logowania do DPD są poprawne. 

Opcja **Domyślna waga paczki** pozwala przyspieszyć wysyłkę paczki dzięki zapewnieniu domyślnej wagi dla zamówień w których waga produktów wynosi zero (czyli prawdopodobnie nie jest podana dla zamówionych produktów).

Opcja **Automatyczne statusy** odpowiada za automatyczną zamianę statusu zamówienia po osiągnięciu przez nie kolejnych etapów wysyłki przez DPD.

Opcja **Statusy zrealizowanych zamówień** służy do ukrycia paczek, których dostarczanie zostało zakończone, co jest weryfikowane na postawie statusu zamówienia. Dzięki temu na liście paczek DPD możemy ukryć niepotrzebne wpisy.

**Dane nadawcy** to dane które pojawią się na drukowanej etykiecie.

Na koniec należy zapisać konfigurację przyciskiem **Zapisz**.

Od tego momentu można już wysyłać paczki przy pomocy DPD. W tym celu wystarczy wejść w zamówienie i wybrać przycisk **Wyślij DPD** (znajduje się on nad formularzem edycji zamówienia). Po kliknięciu pojawi się okienko z zapytaniem o wagę zamówienia, domyślnie będzie tam wpisana sumaryczna waga wszystkich produktów z zamówienia, ale można ją zmienić. W tym miejscu można również zaznaczyć opcję **ROD**, czyli **Dokumenty zwrotne** dla danego zamówienia. Przyciskiem **OK** zatwierdzamy wpisaną wagę zamówienia, a z zamówienia tworzona jest paczka która pojawi się na liście w zakładce **Integracja->DPD**. Link do tej pojawia się w komunikacie o udanym dodaniu paczki dzięki czemu można do niej łatwo przejść.

**WAŻNE!** Jeśli wprowadzimy w zamówieniu zmiany np. poprawimy błędnie wpisane dane dostawy klienta lub dodamy/usuniemy produkty z zamówienia to należy najpierw zapisać zmiany, a dopiero potem kliknąć przycisk **Wyślij DPD**

Ewentualne błędy działania modułu mogą dotyczyć nieprawidłowych danych do wysyłki, należy w takim wypadku sprawdzić, czy dane kontrahenta są poprawne (np. kod pocztowy) oraz jeśli były poprawiane to czy zostały zapisane **przed** kliknięciem przycisku **Wyślij DPD**.

Każde zamówienie jest traktowane jako osobna paczka, nie ma możliwości dodania kilku zamówień do jednej paczki. Oczywiście w ramach jednego protokołu dla kuriera może być dodanych dowolnie dużo paczek.

Moduł posiada zabezpieczenie przeciwko dodaniu dwukrotnie tego samego zamówienia do wysyłki.

Na liście paczek DPD **Integracja->DPD** znajdują się następujące przyciski:

Po prawej stronie (działają na konkretną paczkę):

- **kartka** - otwiera zamówienie którego dotyczy paczka DPD
- **kompas** - otwiera śledzenie przesyłki
- **czerwony krzyżyk** - usuwa paczkę
- **etykieta** - wyświetla PDFa z etykietą zamówienia

Na dole (działają na wszystkie zaznaczone paczki:

- **etykiety** - wyświetla PDFa z etykietą zamówienia
- **czerwony krzyżyk** - usuwa paczkę
- **notatnik** - wyświetla PFa z protokołem dla kuriera

Moduł wspiera opcje:

* **COD** - za pobraniem (jeśli wybrana jest metoda płatności "Za pobraniem")
* **ROD** - dokumenty zwrotne (ustalane oddzielnie dla każdego zamówienia)
* **CUD** - przesyłka zwrotna (wyklucza się z opcją *dokumenty zwrotne*, ustalane oddzielnie dla każdego zamówienia)
* **Duty** - odprawa celna (zależne od kraju, ustalane oddzielnie dla każdego zamówienia)
* **CarryIn** - wniesienie przez kuriera (tylko dla paczek 30-150kg, ustalane oddzielnie dla każdego zamówienia)

**WAŻNE!** Moduł korzysta z tzw. wyskakujących okienek podczas drukowania protokołu dla kuriera oraz nalepek na paczki. Z tego powodu należy się upewnić, że przeglądarka zezwala na wyświetlanie wyskakujących okienek na stronie sklepu.

---

http://mygekosale.pl
