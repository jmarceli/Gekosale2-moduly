Moduł płatności eCard
===
######Gekosale 2.0

### Informacje ogólne
Moduł integruje płatności eCard (http://www.ecard.pl) z Gekosale 2.0.

Zapewnia podstawową funkcjonalność przekierowując klienta po wyborze płatności eService na stronę płatności, a następnie w zależności od rezultatu wykonywanej płatności zmienia status zamówienia na jeden z trzech wcześniej ustalonych. Pozwala na ustalenie statusu zamówienia dla wszystkich dostępnych w eCard statusów płatności.
Dodatkowo umożliwia określenie limitu czasowego na wykonanie przez klienta płatności.

Moduł udostępnia możliwość wykonywania ponownych płatności, jeśli płatność się nie powiedzie lub nie zostanie zakończona.

Przykładowy link do ponownej płatności: http://twojsklep.pl/payagain/123

Gdzie 123 to numer zamówienia.

### WAŻNE
Statusy sklepowe przypisywane do statusów eCard nie powinny się powtarzać.

Statusy eCard uznawane za pomyślną płatność:
Przelew online zaakceptowany
Przelew online potwierdzony
Karta/PayPal transakcja autoryzowana (blokada środków)
Karta/PayPal transakcja potwierdzona do rozliczenia
Karta/PayPal transakcja potwierdzona do rozliczenia

Statusy uznawane za pomyślne przeprowadzenie płatności nie powinny być mapowane na statusy sklepowe dla płatności nie zakończonych. W innym przypadku może nie pojawić się na liście zamówień klienta link do ponowienia płatności.

Status płatności zakończonej nigdy nie zmieni się na status niedokończony, jest to ochrona na wypadek ponownej płatności która zostanie przeprowadzona pomyślnie, a po pewnym czasie przyjdzie status dotyczący pierwszej próby opłacenia zamówienia informujący o niepowodzeniu.

---

http://mygekosale.pl
