# Password Manager – Proiect Facultate

## Descriere generală

Acest proiect reprezintă o aplicație web pentru **gestionarea securizată a parolelor**, realizată ca proiect universitar. Aplicația permite utilizatorilor să își creeze un cont, să se autentifice și să stocheze, genereze și gestioneze parole într-un mod sigur.

Arhitectura este de tip **client–server**, cu un frontend static (HTML, CSS, JavaScript) și un backend dezvoltat în **Node.js (Express)**, folosind o bază de date **MySQL**.

---

## Funcționalități principale

* 🔐 Înregistrare și autentificare utilizatori
* 🔑 Hash-uirea parolelor utilizatorilor folosind **bcrypt**
* 🪪 Autentificare bazată pe **JSON Web Tokens (JWT)**
* 📁 Stocarea securizată a parolelor
* ⚙️ Generare automată de parole puternice
* ✏️ Adăugare, editare și ștergere parole
* 🧠 Criptarea datelor sensibile la nivel de client
* 🚪 Protejarea rutelor prin middleware de autentificare
* 📤 Import , Export parole în fișier JSON

---

## Tehnologii utilizate

### Backend

* **Node.js**
* **Express.js**
* **MySQL**
* **bcrypt** – pentru hash-uirea parolelor
* **jsonwebtoken (JWT)** – autentificare

### Frontend

* **HTML5**
* **CSS3**
* **JavaScript (Vanilla JS)**
* **Fetch API** pentru cereri HTTP

---

## Structura proiectului

```
repo/
│── backend/
│   ├── db/
│   │   ├── schema.sql
│   │   └── db.js
│   ├── middleware/
│   │   └── auth.js
│   ├── routes/
│   │   ├── users.js
│   │   └── passwords.js
│   ├── services/
│   │   ├── userService.js
│   │   └── passwordService.js
│   └── server.js
│
│── frontend/
│   ├── index.html
│   ├── pages/
│   │   ├── register.html
│   │   ├── dashboard.html
│   │   └── settings.html
│   └── scripts/
│       ├── auth.js
│       ├── login.js
│       ├── passwords.js
│       ├── encryption.js
│       └── passwordGenerator.js
│
│── .env.example
│── package.json
```

---

## Configurare și instalare

### 1. Instalare dependințe

```bash
npm install
```

### 2. Configurare variabile de mediu

Copiază fișierul `.env.example` și redenumește-l în `.env`, apoi completează valorile:

```env
PORT=3000
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=parola
DB_NAME=password_manager
```
Notă: De obicei, singurele valori pe care trebuie să le modifici sunt DB_USER și DB_PASSWORD, în funcție de cum îți creezi baza de date. Restul (PORT, DB_HOST, DB_NAME) pot rămâne la valorile implicite dacă nu ai cerințe speciale.

### 3. Configurare bază de date

Asigură-te că ai un mediu MySQL funcțional (de exemplu MySQL Workbench, phpMyAdmin sau alt mediu preferat). Nu trebuie să creezi manual baza de date — scriptul SQL se ocupă de asta.

Rulează scriptul SQL din:

```
backend/db/schema.sql
```
Acesta va:

crea baza de date password_manager dacă nu există,
șterge tabelele existente (utile în development),
crea tabelele users și passwords cu toate coloanele, relațiile și indexurile necesare,
și va seta automat coloanele de timp (created_at, updated_at, last_login, last_used) pentru utilizatori și parole.

Notă: Asigură-te că valorile din fișierul .env (DB_USER și DB_PASSWORD) corespund contului tău MySQL.

### 4. Pornire aplicație

Din directorul backend ruleaza comanda:

```bash
npm run dev
```

Aplicația va rula la adresa:

```
http://localhost:3000
```

---

## Securitate

* Parolele utilizatorilor nu sunt stocate în clar
* Se folosesc algoritmi de hash siguri (**bcrypt**)
* Autentificare prin token JWT
* Middleware pentru protejarea rutelor sensibile
* Criptare la nivel de client pentru datele sensibile

---

## Scop educațional

Acest proiect a fost realizat în scop **educațional**, pentru a demonstra:

* utilizarea unei arhitecturi client–server
* lucrul cu autentificare și securitate
* integrarea unei baze de date relaționale
* bune practici de organizare a codului

---


