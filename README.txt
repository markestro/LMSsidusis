Skrypt automatyzujący eksport raportów zasięgów z LMS do SIDUSIS.

Instalacja:
1. Pobierz plik lms-sidusis.php do katalogu bin/
np. wget https://raw.githubusercontent.com/interduo/LMSsidusis/main/lms-sidusis.php -O /var/www/html/lms/bin/lms-sidusis.php

2. W LMS ustaw zmienne:
'sidusis.api_token' - token wygenerowany na stronie internet.gov.pl po zalogowaniu w Profilu,
'sidusis.selected_division' - raportowany oddział,
'sidusis_operator_offer_url' - adres URL z ofertą usług,

3. Uruchom pierwszy import i sprawdź poprawność danych w internet.gov.pl
bin/lms-sidusis.php --export-ranges --debug

4. Dodaj do systemowego harmonogramu zadań (crontab) komendę
bin/lms-sidusis.php --export-ranges -q

Pozdrawiam i miłej kawusi
Jarosław 'YArii' Kłopotek 
@interduo
