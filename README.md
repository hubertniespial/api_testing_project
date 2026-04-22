# API Testing Portfolio

## Opis projektu

Projekt zawiera testy API wykonane w Postmanie dla publicznego API:
https://jsonplaceholder.typicode.com/

Celem było sprawdzenie działania podstawowych operacji CRUD oraz weryfikacja poprawności danych zwracanych przez API.

---

## Technologie

* Postman
* JavaScript (testy w Postmanie)
* JSON
* Jira (raportowanie)

---

## Zakres testów

### GET

* pobranie pojedynczego posta (`GET /posts/1`)
* sprawdzenie struktury odpowiedzi
* weryfikacja typów danych (`userId`, `id`, `title`, `body`)
* czas odpowiedzi

Dodatkowo:

* niepoprawne `id` (`@`) → 404
* brak `id` (`GET /posts/`) → lista postów

---

### POST

* tworzenie posta z poprawnymi danymi (`201 Created`)
* sprawdzenie struktury odpowiedzi
* weryfikacja danych wejściowych

Testowane przypadki:

* pusty request body
* `userId` jako string
* `id` jako string
* `title` jako integer
* `body` jako integer
* wszystkie pola jako `null`

---

### PUT / PATCH

* aktualizacja posta (`PUT /posts/1`, `PATCH /posts/1`)
* sprawdzenie zmiany danych (`title`, `body`)
* weryfikacja, że `id` nie ulega zmianie

---

### DELETE

* usunięcie posta (`DELETE /posts/1`)
* sprawdzenie statusu odpowiedzi
* weryfikacja pustego response body

---

## Przykładowe testy

* weryfikacja statusów HTTP (200, 201, 404)
* sprawdzenie czasu odpowiedzi (< 200 ms)
* walidacja typów danych
* sprawdzenie struktury odpowiedzi
* iteracja po elementach listy (GET)

---

## Wykryte problemy

1. API akceptuje "title" jako integer zamiast string
2. API akceptuje "body" jako integer zamiast string
3. API akceptuje "userId" jako string zamiast integer
4. API przyjmuje "null" jako wartości dla pól "title", "body", "userId"

---

## Screenshots

<img width="1495" height="834" alt="image" src="https://github.com/user-attachments/assets/65379f8d-0a49-403c-9609-4546e26f18c5" />
<img width="1495" height="816" alt="image" src="https://github.com/user-attachments/assets/663b451b-9843-4b9c-a423-f7b5f5ee6972" />
<img width="1495" height="816" alt="image" src="https://github.com/user-attachments/assets/530d338a-6954-4d31-a1fd-68ebbe96f6d6" />
<img width="1495" height="816" alt="image" src="https://github.com/user-attachments/assets/d0c0d4db-7676-4f8c-ad3a-f78d81c160ce" />
<img width="1495" height="852" alt="image" src="https://github.com/user-attachments/assets/92c026b4-d55e-4097-9ade-64361b06a333" />


---

## Jak uruchomić

1. Zaimportuj plik `postman_collection.json` do Postmana
2. Uruchom requesty z kolekcji
3. Sprawdź wyniki w zakładce **Tests**

---

## Autor

Hubert Nieśpiał
