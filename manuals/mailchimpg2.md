Moduł integracji z serwisem Mailchimp
===
###### Gekosale 2.0

Moduł integrujący sklep z serwisem Mailchimp. Pozwala w prosty sposób automatycznie synchronizować listę osób zapisanych do newslettera w sklepie z wybraną listą mailingową programu Mailchimp.

Konfiguracja modułu po zainstalowaniu jest dostępna w zakładce **Integracja->Integracja Mailchimp**

# Konfiguracja
W ramach konfiguracji należy podać klucz dostępu do serwisu tzw. klucz API (można go znaleźć na swoim koncie w menu otwieranym po kliknięciu swojej nazwy użytkownika mailchimp w zakładce *Account->Extras->API keys*), oraz listę mailingową z którą będzie synchronizowana lista osób zapisanych do sklepowego newslettera.

Po podaniu tych informacji należy zapisać nowowprowadzone ustawienia, a następnie kliknąć *Synchronizuj newsletter* w celu przeprowadzenia początkowej synchronizacji. Po tej operacji lista zapisanych adresów e-mail bęzie automatycznie synchronizowana za każdym razem gdy ktoś się zapisze lub wypisze ze sklepowego newslettera.

Powiązanie sklepu z mailchimpem pozwalające na synchronizację Mailchimp->Gekosale (realizowane za pomocą mechanizmu Webhook) tworzy się automatycznie po wprowadzeniu klucza API i zapisaniu ustawień.

## Stary opis
Klienci z niepotwierdzonym adresem email newslettera dodawani są do Mailchimp'a jak 'Unsubscribed'
Śledzone są zmiany adresu email klienta, jeśli zmieni adres email na swoim koncie, a adres ten wcześniej był przypisany do newsletter'a to zostanie on też zmieniony w newsletterze (zarówno w Gekosale jak i Mailchimp).
Wypisanie się z newslettera powoduje usunięcie adresu z Mailchimp'a.

Oczywiście zmiany subskrypci w Gekosale są automatycznie przesyłane do Mailchimp'a i odwrotnie.

**UWAGA!**
Domyślnie w Gekosale 2.0 nie działa zapisywanie się do newslettera bez rejestracji. Jeśli korzystasz ze starej wersji Gekosale zapytaj o update lub poprawkę tego problemu (kod poprawki cdbef91).

---
http://mygekosale.pl
