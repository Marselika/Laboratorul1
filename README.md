# Lucrare de laborator nr. 1. Bazele HTTP
### Instrucțiuni pentru rularea proiectului
**Sarcina nr. 1. Analiza cererilor HTTP**
1. Accesați site-ul http://sandbox.usm.md/login.
2. Deschideți fila Network în instrumentele pentru dezvoltatori ale browserului.
3. Introduceți date incorecte pentru autentificare (de exemplu, username: student, password: studentpass).
4. Analizați cererile care au fost trimise către server.
5. Răspundeți la următoarele întrebări:
 - Ce metodă HTTP a fost utilizată pentru a trimite cererea?
 - Ce anteturi au fost trimise în cerere?
 - Ce parametri au fost trimiși în cerere?
 - Ce cod de stare a fost returnat de server?
 - Ce anteturi au fost trimise în răspuns?
6. Repetați pașii 3-5, introducând date corecte pentru autentificare (username: admin, password: password).
   
**Sarcina nr. 2. Crearea cererilor HTTP**
1. Scrieți o cerere de tip GET către server la adresa http://sandbox.com, indicând în antetul User-Agent numele și prenumele dvs.
2. Scrieți o cerere de tip POST către server la adresa http://sandbox.com/cars, indicând în corpul cererii următorii parametri:
make: Toyota
model: Corolla
year: 2020
3. Scrieți o cerere de tip PUT către server la adresa http://sandbox.com/cars/1, indicând în antetul User-Agent numele și prenumele dvs., în antetul Content-Type valoarea application/json, iar în corpul cererii următorii parametri: json { "make": "Toyota", "model": "Corolla", "year": 2021 }
4. Scrieți unul dintre posibilele răspunsuri ale serverului la cererea anterioară. http POST /cars HTTP/1.1 Host: sandbox.com Content-Type: application/json User-Agent: John Doe model=Corolla&make=Toyota&year=2020 Presupuneți situațiile în care serverul poate returna codurile de stare HTTP 200, 201, 400, 401, 403, 404, 500.
5. Scrieți o cerere de tip DELETE la alegerea dvs. și să explicați de ce, în acest caz, este potrivit să utilizați metoda DELETE.
Sarcina nr. 3. Sarcina suplimentară. HTTP_Quest

**Sarcina nr. 3. Sarcina suplimentară. HTTP_Quest**
1. Trimiteți o cerere de tip POST către server la adresa http://sandbox.usm.md/quest, indicând în antetul User-Agent numele și prenumele dvs. (De exemplu, User-Agent: John Doe). http POST /quest HTTP/1.1 Host: sandbox.usm.md User-Agent: John Doe curl: bash curl -X POST http://sandbox.usm.md/quest -H "User-Agent: John Doe"
2. Urmați instrucțiunile de pe server, îndeplinindu-le în ordine.
3. La finalul quest-ului, vi se va afișa un cuvânt secret, pe care va trebui să-l includeți în raport.
   
### Scop
Scopul acestei lucrări de laborator este studierea principiilor de bază ale protocolului HTTP.

### Descrierea lucrării individuale
Lucrarea a fost realizata in trei sarcini principale, avand ca obiectiv analiza cererilor HTTP si crearea unor cereri de diferite tipuri. In prima sarcina, am explorat cererile trimise catre server prin intermediul unui formular de autentificare, observand comportamentul serverului atat cu date incorecte, cat si corecte. A doua sarcina a constat in formularea manuala a cererilor HTTP de tip GET, POST, PUT si DELETE, explicandu-se contextul in care sunt utilizate aceste metode. In final, sarcina suplimentara a implicat trimiterea unei cereri POST catre un server specific, urmand instructiunile oferite si obtinand un cuvant secret.

### Documentația a proiectului
## Sarcina nr. 1. Analiza cererilor HTTP
Pentru a analiza cererile HTTP trimise către server, am început prin accesarea site-ului http://sandbox.usm.md/login. Odata ce pagina s-a incarcat, am deschis fila Network in instrumentele pentru dezvoltatori ale browserului, care permite monitorizarea cererilor și răspunsurilor HTTP.
Apoi, am introdus date incorecte pentru autentificare, utilizand username-ul „student” și parola „studentpass”. După trimiterea formularului, am observat cererile efectuate către server, anteturile trimise și codul de stare returnat. 
#### Date incorecte pentru autentificare:
 - Ce metodă HTTP a fost utilizată pentru a trimite cererea?
   
   Metoda HTTP POST a fost utilizata pentru a trimite cerere data.
   
  ![image](https://github.com/user-attachments/assets/76ec91b9-da20-40d4-9754-d6d3b0317391)

 - Ce anteturi au fost trimise în cerere?
   
   Accept, Accept-Encoding, Accept-Language, Connection, Content-Length, Content-Type, Host, Origin, Referer, User-Agent, X-Requested-With
   
   ![image](https://github.com/user-attachments/assets/e14447cd-3333-48f5-b981-497e0f454d04)

 - Ce parametri au fost trimiși în cerere?
   
   username = "student", password = "studentpass"
   
   ![image](https://github.com/user-attachments/assets/e498fe99-1ccd-4cbc-a3e6-2d17b578d02e)

 - Ce cod de stare a fost returnat de server?
   
   401 Unauthorized
   
    ![image](https://github.com/user-attachments/assets/1a2295a4-9d91-48a2-91c2-2da74b52a653)
 - Ce anteturi au fost trimise în răspuns?
   
   Connection, Content-Type, Date, Server, Transfer-Encoding
   
   ![image](https://github.com/user-attachments/assets/35a8ce38-eb1a-4b1b-8f52-ad3c21c12a34)


#### Date corecte pentru autentificare:
 - Ce metodă HTTP a fost utilizată pentru a trimite cererea?
   
   Metoda HTTP POST a fost utilizata pentru a trimite cererea.
   
   ![image](https://github.com/user-attachments/assets/5cb59ef7-b3ee-44d0-8a27-c0120a076701)

 - Ce anteturi au fost trimise în cerere?
   
   Accept, Accept-Encoding, Accept-Language, Connection, Content-Length, Content-Type, Host, Origin, Referer, User-Agent, X-Requested-With
   
   ![image](https://github.com/user-attachments/assets/acedf28a-b770-404d-bc79-52f0f1988fe1)

 - Ce parametri au fost trimiși în cerere?
   
   username = "admin", password = "password"
   
   ![image](https://github.com/user-attachments/assets/47098cb3-da22-47e1-a0e5-6b95b50966f4)

 - Ce cod de stare a fost returnat de server?
   
   200 OK
   
   ![image](https://github.com/user-attachments/assets/022a7d1c-d72a-49fc-833e-6c0d246c027b)

 - Ce anteturi au fost trimise în răspuns?
   
   Connection, Content-Type, Date, Server, Transfer-Encoding
   
   ![image](https://github.com/user-attachments/assets/08e6cb8e-6435-4438-8add-37f58d9a4e9b)





## Sarcina nr. 2. Crearea cererilor HTTP
1. **Cerere GET:** Se trimite o cerere GET pentru a obtine informatii de pe pagina principala, specificand în antetul User-Agent numele și prenumele utilizatorului.
   
![image](https://github.com/user-attachments/assets/45429bed-f609-405e-8d3e-812235b9dcb8)


2. **Cerere POST:** O cerere POST este formulată către /cars pentru a crea o nouă resursă (autovehicul) cu parametrii: make: Toyota, model: Corolla, year: 2020.
   
![image](https://github.com/user-attachments/assets/08271546-fd07-431d-87a6-35a56215314c)
Resursa pe care incercam sa o accesam nu există pe server. Aceasta poate fi cauzată de faptul că resursa a fost stearsa anterior, nu a fost creata deloc sau a fost mutata intr-o alta locatie fara actualizarea URL-ului. 

3. **Cerere PUT:** Se trimite o cerere PUT către /cars/1 pentru a actualiza resursa existentă, inclusiv în antetul User-Agent și Content-Type, iar în corpul cererii se specifică datele actualizate (year: 2021).

![image](https://github.com/user-attachments/assets/7e5399ba-97ce-4c63-9e6f-fb49a7d65c9f)

![image](https://github.com/user-attachments/assets/20f207cd-eb95-4a6d-aa62-7ca05574afac)

Prin această cerere PUT, actualizăm vehiculul cu ID-ul 1 pentru a indica faptul că este un model Toyota Corolla din anul 2021. Dacă vehiculul cu ID-ul 1 nu există, serverul ar putea returna codul 404 Not Found, ceea ce ar indica faptul că resursa nu a fost găsită.

4. **Unul dintre posibilele răspunsuri ale serverului la cererea anterioară:**

{ "id": 1, "make": "Toyota", "model": "Corolla", "year": 2020, "message": "Car created successfully" }

Situațiile posibile in care serverul poate returna codurile de stare HTTP 200, 201, 400, 401, 403, 404, 500:
 - 200 OK: Cererea a fost procesată cu succes.
 - 201 Created: Resursa a fost creată cu succes.
 - 400 Bad Request: Cererea nu a fost formatată corect.
 - 401 Unauthorized: Autentificare necesară.
 - 403 Forbidden: Acces interzis.
 - 404 Not Found: Resursa nu a fost găsită.
 - 500 Internal Server Error: Eroare pe server.

5. **Cerere DELETE:** Se formulează o cerere DELETE către /cars/1 pentru a șterge resursa cu ID-ul 1, ceea ce este o acțiune standard în gestionarea resurselor.

![image](https://github.com/user-attachments/assets/fc934e44-cfc6-4c8f-b40d-a63ac6a50c5a)

Codul de eroare 404 Not Found la cererea DELETE catre /cars/1 poate apărea din cauza faptului că resursa cu ID-ul 1 nu exista sau URL-ul este incorect.

Metoda DELETE este potrivita in acest caz deoarece se doreste eliminarea unei resurse specifice de pe server, in acest exemplu, a vehiculului cu ID-ul 1. Utilizarea metodei DELETE permite serverului sa stie ca utilizatorul intentioneaza sa stearga definitiv resursa respectiva din baza de date, asigurand astfel o gestionare eficienta a datelor. Aceasta actiune este comuna in gestionarea resurselor, cum ar fi autovehiculele intr-o aplicatie de gestionare a flotei, unde este esential sa se mentina o baza de date curata si actualizata.




## Sarcina nr. 3. Sarcina suplimentară. HTTP_Quest

#### Trimitem o cerere de tip POST către server la adresa http://sandbox.usm.md/quest, indicând în antetul User-Agent numele și prenumele.
1.  ![image](https://github.com/user-attachments/assets/c126ebd7-bfe5-41d9-a994-19391ad81924)

2. ![image](https://github.com/user-attachments/assets/f843eeae-350c-45d2-acfd-b864fe28256b)
3. ![image](https://github.com/user-attachments/assets/f7e21475-939f-45db-997b-c6fc35093708)
4. ![image](https://github.com/user-attachments/assets/8a739505-6a80-4678-9440-3cbf9ce2fc23)



#### Cuvântul secret: 







### Răspunsuri la întrebările de control
**1. Ce este protocolul HTTP?**
HTTP (Hypertext Transfer Protocol) este un protocol de comunicatie utilizat pentru transferul de informatii pe web. Acesta permite clientului (de obicei un browser web) sa comunice cu serverul, solicitand resurse (cum ar fi pagini web, imagini sau fisiere) si primind raspunsuri. HTTP functioneaza pe baza unui model de cerere-raspuns, unde clientul trimite o cerere catre server, iar serverul returneaza un raspuns corespunzator.

**2. Pentru ce folosim antetul User-Agent?**
Antetul User-Agent este utilizat pentru a identifica tipul si versiunea browserului, sistemul de operare si alte informatii despre clientul care efectueaza cererea. Acest antet ajuta serverul sa determine cum sa raspunda la cerere, de exemplu, prin personalizarea continutului sau prin redirectionarea utilizatorilor catre versiuni specifice ale site-ului optimizate pentru diferite dispozitive.

**3. Care este diferența dintre metodele PUT și PATCH?**

**PUT:** Metoda PUT este utilizata pentru a actualiza o resursa existenta sau pentru a crea una noua la un anumit URL. Atunci cand se foloseste PUT, clientul trimite intreaga reprezentare a resursei, iar serverul inlocuieste resursa existenta cu cea noua.

**PATCH:** Metoda PATCH este utilizata pentru a aplica modificari partiale unei resurse existente. Spre deosebire de PUT, PATCH trimite doar datele care trebuie actualizate, nu intreaga resursa. Aceasta face PATCH mai eficient in situatiile in care doar o mica parte a resursei trebuie modificata.


### Concluzii
Lucrarea a oferit o intelegere profundă a cererilor HTTP si a interactiunilor dintre client și server. Prin analiza cererilor efectuate pe site-ul de autentificare, am identificat metodele utilizate, anteturile trimise, precum și codurile de stare returnate de server. Aceste observații au evidențiat importanta unei autentificari corecte si modul în care serverele gestionează cererile gresite. Crearea cererilor HTTP a demonstrat cum funcționeaza diferitele metode (GET, POST, PUT, DELETE) și relevanta fiecărei metode în gestionarea resurselor. Aceasta lucrare nu doar că a consolidat cunoștințele teoretice, dar a și evidențiat aplicabilitatea practică a acestora în dezvoltarea web. Astfel, am dobândit abilitati esentiale pentru gestionarea eficienta a aplicațiilor web si a interactiunilor HTTP.
