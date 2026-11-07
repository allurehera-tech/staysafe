# Stay Safe (Android)

Aplicație Android nativă, scrisă în Kotlin. Interfața are selector de limbă cu steaguri: română, engleză, spaniolă, italiană, franceză, germană, chineză, arabă, portugheză și hindi. Utilizatorul poate salva până la trei numere de telefon și poate activa un buton SOS plutitor care rămâne disponibil peste celelalte aplicații. O apăsare continuă de 5,5 secunde pe butonul plutitor pornește alarma și trimite fiecărui număr salvat SMS-ul „Help” cu link Google Maps. Opțional, după activarea manuală a serviciului Accessibility, ținerea Volum jos timp de 5 secunde declanșează alarma și SMS-ul, inclusiv când ecranul este stins. Apăsările scurte de Volum jos continuă să regleze volumul. Înaintea permisiunilor se afișează explicații cu acceptare/anulare. Paginile de confidențialitate, GDPR și informații legale sunt accesibile din aplicație. Alarma rulează într-un serviciu foreground armat cât timp SOS este activ și poate fi oprită din aplicație sau din notificare.

## Deschidere

Deschide proiectul în Android Studio și lasă Gradle să sincronizeze pluginurile. Rulează configurația `app` pe un telefon cu Android 8.0+ și SIM cu serviciu SMS. Emulatorul poate să nu poată trimite SMS-uri reale.

## Limitare Android

Android nu livrează atingeri când ecranul este stins. În loc să intercepteze toate atingerile și să afecteze folosirea normală a celorlalte aplicații, Stay Safe afișează un buton SOS plutitor după acordarea permisiunii „Afișare peste alte aplicații”. Apăsarea lungă funcționează cât timp ecranul este aprins.

Trimiterea SMS în fundal necesită permisiunea `SEND_SMS`; poziția în fundal necesită acces la locație, inclusiv „Permite tot timpul” pe Android 10+. Dacă nu există o locație recentă, aplicația așteaptă până la 7 secunde pentru una nouă și apoi trimite cea mai recentă poziție disponibilă sau precizează că locația nu este disponibilă. SMS-urile pot fi taxate de operator. Nu se trimit mesaje de test. Înainte de publicare, verificați că informațiile operatorului sunt corecte și găzduiți politica de confidențialitate la un URL public stabil. Politica Google Play permite permisiunile SMS doar aplicațiilor înregistrate ca aplicație SMS implicită sau asistent; prin urmare, trimiterea automată în această formă poate împiedica publicarea în Play. Utilizarea Accessibility API cere de asemenea declarații și evaluare. Instalarea directă pe dispozitiv are cerințe diferite.

Pagina publică de confidențialitate este în `docs/index.html`. Pentru GitHub Pages, publicați numai acest fișier într-un repository public, apoi selectați `Settings > Pages > Deploy from a branch` și folderul `/docs`. Pagina este bilingvă (română și engleză) și include datele operatorului furnizate.
