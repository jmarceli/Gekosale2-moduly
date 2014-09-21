Moduł płatności PayPal
========
######Gekosale 2.0

### Informacje ogólne
Integruje płatności eService (http://www.eservice.com.pl/) z Gekosale 2.0.

Zapewnia podstawową funkcjonalność przekierowując klienta po wyborze płatności eService na stronę płatności, a następnie w zależności od rezultatu wykonywanej płatności zmienia status zamówienia na jeden z trzech wcześniej ustalonych. Pozwala na ustalenie statusu zamówienia w przypadku płatności wykonanej, anulowanej lub oczekującej.

Moduł udostępnia możliwość ponownego opłacenia zamówienia, jeśli jego status odpowiada statusowi ustawionemu jako "rozpoczęta" lub "błędna".

### Opis statusów
Informacje co oznaczają poszczególne statusy możliwe do ustawienia w konfiguracji:
* **Płatność rozpoczęta** - klient został przekierowany na stronę serwisu płatności, ale nie wykonał jeszcze płatności
* **Płatność oczekująca** - płatności zaakceptowana przez eService, oczekująca na realizację przez wybrany bank
* **Płatność potwierdzona** - płatność została zakończona
* **Płatność anulowana** - płatność zakończona niepowodzeniem

###Uwaga!
Obecnie obsługiwane są waluty: **PLN**, **USD** i **EUR**. Tylko takie nazwy są dozwolone (jeśli w sklepie zamiast **PLN** jest np. **zł** to należy ten fakt zgłosić w celu dostosowania modułu) w Gekosale inaczej moduł nie będzie działać poprawnie. Ewentualne roszerzenie tej listy jest możliwe i łatwe w realizacji.

---

hhttp://mygekosale.pl
