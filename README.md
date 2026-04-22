# API Testing Portfolio (Postman)

## 📌 Opis projektu

Projekt zawiera testy API wykonane w Postmanie dla publicznego API:
https://jsonplaceholder.typicode.com/

Celem projektu było:

* testowanie endpointów REST (GET, POST, PUT/PATCH, DELETE)
* walidacja struktury odpowiedzi
* testy pozytywne i negatywne
* wykrywanie błędów walidacji danych (bugi)

---

## 🛠 Technologie

* Postman
* JavaScript (testy w Postmanie)
* JSON

---

## 📂 Zakres testów

### 🔹 GET

* pobranie pojedynczego posta (`GET /posts/1`)
* walidacja struktury odpowiedzi
* walidacja typów danych (userId, id, title, body)
* testy czasu odpowiedzi

#### Edge cases:

* niepoprawny id (`@`) → oczekiwany 404
* brak id (`GET /posts/`) → lista postów

---

### 🔹 POST

* tworzenie posta z poprawnymi danymi (`201 Created`)
* walidacja odpowiedzi i typów danych
* weryfikacja zgodności danych (np. userId)

#### Edge cases:

* pusty request body
* userId jako string
* id jako string
* title jako integer ❌ (bug)
* body jako integer ❌ (bug)
* wszystkie pola = null ❌

---

### 🔹 PUT / PATCH

* aktualizacja posta (`PUT /posts/1`, `PATCH /posts/1`)
* weryfikacja zmiany danych (title, body)
* sprawdzenie czy id pozostaje bez zmian

---

### 🔹 DELETE

* usunięcie posta (`DELETE /posts/1`)
* walidacja statusu (200)
* sprawdzenie pustej odpowiedzi

---

## 🧪 Przykładowe testy

* status code validation (200, 201, 404)
* response time < 200ms
* walidacja typów:

  * userId → integer
  * id → integer
  * title → string
  * body → string
* walidacja struktury odpowiedzi
* iteracja po tablicach (GET lista)

---

## 🐞 Wykryte błędy

### 1. Brak walidacji pola `title`

API akceptuje `title` jako integer zamiast string.

### 2. Brak walidacji pola `body`

API akceptuje `body` jako integer zamiast string.

---

## 📸 Screenshots

<img width="1495" height="834" alt="image" src="https://github.com/user-attachments/assets/65379f8d-0a49-403c-9609-4546e26f18c5" />
<img width="1495" height="816" alt="image" src="https://github.com/user-attachments/assets/663b451b-9843-4b9c-a423-f7b5f5ee6972" />
<img width="1495" height="816" alt="image" src="https://github.com/user-attachments/assets/530d338a-6954-4d31-a1fd-68ebbe96f6d6" />
<img width="1495" height="816" alt="image" src="https://github.com/user-attachments/assets/d0c0d4db-7676-4f8c-ad3a-f78d81c160ce" />

---

## ▶️ Jak uruchomić

1. Zaimportuj plik `postman_collection.json` do Postmana
2. Uruchom wybrane requesty
3. Sprawdź zakładkę **Tests**

---

## 🎯 Wnioski

Projekt pokazuje:

* umiejętność testowania API REST
* znajomość Postmana i testów w JavaScript
* testowanie pozytywne i negatywne
* wykrywanie problemów walidacji danych

---

## 👤 Autor

Hubert Nieśpiał
