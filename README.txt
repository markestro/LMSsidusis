Skrypt automatyzujący wrzucanie raportów zasięgów z LMS do SIDUSIS

Instalacja:
1. Pobierz plik lms-sidusis.php do katalogu bin/
np. wget https://raw.githubusercontent.com/interduo/LMSsidusis/main/lms-sidusis.php -O /var/www/html/lms/bin/lms-sidusis.php

2. W LMS ustaw zmienne:
'sidusis.api_token' - token REST API wygenerowany na stronie internet.gov.pl - po zalogowaniu w edycji Profilu użytkownika,
'sidusis.selected_division' - raportowany oddział,
'sidusis_operator_offer_url' - adres URL z ofertą usług,
(gdyby ktoś wrzucał raporty z wielu oddziałów można użyć zmiennej --config i ustawiać te zmienne w różnych plikach np. /etc/lms/lms.ini i /etc/lms/lms-oddzial2.ini w sekcji [sidusis])

3. Uruchom pierwszy import i sprawdź poprawność danych w internet.gov.pl
bin/lms-sidusis.php --export-ranges --debug

4. Dodaj do systemowego harmonogramu zadań (crontab) komendę wrzucającą raport z typem przyrostowym
0 15	* * 1	root	/var/www/html/lms/bin/lms-sidusis.php -q --export-ranges

Pozdrawiam i miłej kawusi
Jarosław 'YArii' Kłopotek 
@interduo
