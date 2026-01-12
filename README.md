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
* 📤 Export parole în fișier JSON

---

## Tehnologii utilizate

### Backend

* **Node.js**
* **Express.js**
* **MySQL**
* **bcrypt** – pentru hash-uirea parolelor
* **jsonwebtoken (JWT)** – autentificare
* **dotenv** – variabile de mediu
* **cors** – comunicare frontend–backend

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
JWT_SECRET=secretul_tau
```

### 3. Configurare bază de date

Rulează scriptul SQL din:

```
backend/db/schema.sql
```

### 4. Pornire aplicație

```bash
npm start
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

## Autor

Proiect realizat ca temă / proiect universitar.

---

## Observații

Aplicația **nu este destinată utilizării în producție**, ci exclusiv scopului didactic.
