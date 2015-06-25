Moduł IFIRMA
===
###### Gekosale 2.0
Integracja z serwisem IFIRMA.

Integracja dotyczy **tylko wystawiania faktur VAT lub rachunków sprzedaży krajowej (dla nieVATowców)**. Pozwala na ustawienie sposobu wystawiania faktury **Netto/Brutto** i ewentualne uwzględnienie ryczałtu. Opcje pozwalające ustawić odpowiednie wartości ryczałtu dostępne są w konfiguracji integracji \(zakładka *Integracja->IFIRMA*\) oraz w formularzu edycji produktu w zakładce Cena \(można tam ustawić indywidualną wartość ryczałtu jeśli ma być inna od domyślnej\).

Wymagane jest również ustawienie miasta w którym wystawiany jest rachunek. Pojawi się ono na rachunku zaraz za datą wystawienia.

Dodatkowo niezbędne jest ustawienie stawki ryczałtu dla wysyłki ponieważ zgodnie ze specyfikacją IFIRMA musi mieć ona wartość niezerową.

Dodane zostało wsparcie dla "negatywnych" reguł koszyka np. +10% do zamówienia ze względu na płatność on-line, czy inne reguły zwiększające kwotę zamówienia. Dodawane są one jako oddzielna pozycja na fakturze o nazwie zgodnej z nazwą reguły koszyka.

W celu ponownego wygenerowania rachunku/faktury należy **odznaczyć** w konfiguracji modułu opcję **Zapobiegaj ponownemu fakturowaniu**, w innym przypadku zamiast ponownej generacji zostanie jedynie pobrana istniejąca faktura.

Rachunek można pobrać w formacie PDF klikając odpowiedni przycisk na liście zamówień lub w widoku edycji danego zamówienia. Za pomocą opcji **Pobieraj PDFy w momencie wystawienia** można wyłączyć automatyczne pobieranie dokumentów, wtedy przyciski jedynie generują faktury w programie IFIRMA, ale ich nie pobierają.

Po wystawieniu faktury zamówienie może automatycznie zmienić status. Służy do tego opcja **Status po wystawieniu faktury**.

Wystawiona faktura może być automatycznie przesyłana mailem do klienta. Służy do tego opcja **Przesyłaj fakturę mailem**. Szablon email dla przesyłanej faktury składa się z dwóch tekstów, które można dowolnie przetłumaczyć w zakładce z tłumaczeniami: *TXT_INVOICE_NOTIFICATION_TITLE* - tytuł maila, *TXT_INVOICE_NOTIFICATION_BODY* - treść wiadomości.

Moduł umożliwia również wystawianie faktur bez konieczności ich pobierania. Faktury wystawiane są wtedy jedynie w systemie IFIRMA, a w sklepie pojawiają się do pobrania w ten sam sposób co domyślne faktury sklepowe. Jeżeli chcemy wykorzystać tą opcję to przydatny będzie przełącznik **Pokaż przycisk pobierania faktury** po którego odznaczeniu ukryty zostanie przycisk do pobierania faktur w formacie PDF w panelu.

Opcja **Pobieraj PDF** pozwala na proste pobieranie faktur w formacie PDF w trakcie ich wystawiania. W ten sposób ograniczana jest konieczność wielokrotnego klikania. Po zaznaczeniu tego pola faktura będzie automatycznie pobierana w momencie wystawienia.

Pola znajdujące się w grupie **Dane wykorzystywane przy generowaniu faktur w Gekosale** nie są w żaden sposób synchronizowane z serwisem IFIRMA. Ich zawartość ma jedynie wpływ na informacje wyświetlane po stronie sklepu.

##UWAGA!!!
Dokumenty Ifirma pobierane są za pomocą tzw. wyskakujących okienek, w celu poprawnego działania modułu **musisz** zezwolić w ustawieniach swojej przeglądarki na **wyświetlanie wyskakujących okienek** przez sklep.

### Wersje
- v2.0 Współpraca z Gekosale 2.0
- v2.01 Dodanie obsługi wielu zamówień na raz oraz możliwości wysyłania faktur mailem

---

http://mygekosale.pl
