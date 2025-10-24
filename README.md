# 📘 Quotes REST API — Mock JSON Server

This is a mock **Quotes API** built using [my-json-server.typicode.com](https://my-json-server.typicode.com/), designed for testing REST API operations such as **GET**, **POST**, **PUT**, **PATCH**, and **DELETE**.

It contains data about **famous authors** and their **quotes**, allowing you to simulate realistic API automation scenarios.

---

## 🌐 Base URL

```
https://my-json-server.typicode.com/edwardmrdoian/quotes-db
```

*(Replace `<Myusername>` with your GitHub username.)*

---

## 📂 Resources

### 1. `/authors`

Represents famous authors with metadata such as nationality, biography, and activity period.

#### Example Object
```json
{
  "id": 1,
  "name": "Albert Einstein",
  "birthYear": 1879,
  "nationality": "German",
  "knownFor": "Theory of Relativity",
  "bio": "Theoretical physicist who developed the theory of relativity, one of the two pillars of modern physics.",
  "activeYears": "1900–1955"
}
```

#### Available Endpoints

| Method | Endpoint | Description |
|--------|-----------|-------------|
| **GET** | `/authors` | Get all authors |
| **GET** | `/authors/:id` | Get a specific author by ID |
| **POST** | `/authors` | Add a new author |
| **PUT** | `/authors/:id` | Replace an existing author |
| **PATCH** | `/authors/:id` | Update specific fields of an author |
| **DELETE** | `/authors/:id` | Delete an author |

---

### 2. `/quotes`

Represents quotes from authors with detailed information such as category, language, and popularity.

#### Example Object
```json
{
  "id": 1,
  "authorId": 1,
  "quote": "Life is like riding a bicycle. To keep your balance, you must keep moving.",
  "category": "Motivation",
  "year": 1930,
  "likes": 12450,
  "language": "English",
  "dateAdded": "2021-06-10",
  "description": "Einstein reflects on persistence and the importance of progress."
}
```

#### Available Endpoints

| Method | Endpoint | Description |
|--------|-----------|-------------|
| **GET** | `/quotes` | Get all quotes |
| **GET** | `/quotes/:id` | Get a specific quote |
| **GET** | `/authors/:id/quotes` | Get all quotes by a specific author |
| **POST** | `/quotes` | Create a new quote |
| **PUT** | `/quotes/:id` | Replace an existing quote |
| **PATCH** | `/quotes/:id` | Update specific fields of a quote |
| **DELETE** | `/quotes/:id` | Delete a quote |

---

## 💡 Example Requests

### ➤ Get All Quotes
```bash
GET /quotes
```
**Response:**
```json
[
  {
    "id": 1,
    "authorId": 1,
    "quote": "Life is like riding a bicycle. To keep your balance, you must keep moving.",
    "category": "Motivation",
    "year": 1930,
    "likes": 12450,
    "language": "English",
    "dateAdded": "2021-06-10",
    "description": "Einstein reflects on persistence and the importance of progress."
  }
]
```

---

### ➤ Add New Quote
```bash
POST /quotes
```
**Request Body:**
```json
{
  "authorId": 3,
  "quote": "Without music, life would be a mistake.",
  "category": "Philosophy",
  "year": 1889,
  "likes": 12000,
  "language": "German",
  "dateAdded": "2025-10-25",
  "description": "A reflection on the essential role of art in human existence."
}
```

**Response:**
```json
{
  "id": 9,
  "authorId": 3,
  "quote": "Without music, life would be a mistake.",
  "category": "Philosophy",
  "year": 1889,
  "likes": 12000,
  "language": "German",
  "dateAdded": "2025-10-25",
  "description": "A reflection on the essential role of art in human existence."
}
```

---

### ➤ Update Quote Likes
```bash
PATCH /quotes/3
```
**Request Body:**
```json
{
  "likes": 16001
}
```
**Response:**
```json
{
  "id": 3,
  "authorId": 3,
  "quote": "He who has a why to live can bear almost any how.",
  "category": "Philosophy",
  "year": 1888,
  "likes": 16001,
  "language": "German",
  "dateAdded": "2021-07-01",
  "description": "A philosophical reflection about purpose and human strength."
}
```

---

### ➤ Delete a Quote
```bash
DELETE /quotes/7
```
**Response:**
```json
{}
```

---

## 🧠 Relationships

- Each **quote** references an **author** via `authorId`.
- You can access all quotes from an author using:
  ```
  GET /authors/:id/quotes
  ```
  Example:
  ```
  GET /authors/1/quotes
  ```

---

## 🧰 Use Cases

You can use this mock API to practice:
- ✅ API automation with **Rest Assured**, **Postman**, or **K6**
- ✅ CRUD testing scenarios
- ✅ Schema validation and response parsing
- ✅ Test data generation and request chaining
- ✅ Negative test cases (e.g., invalid IDs, missing fields)

---

## ⚙️ Setup Instructions

1. Fork or clone this repository.  
2. Keep the `db.json` file in the root directory.
3. Access your mock API using:
   ```
   https://my-json-server.typicode.com/<your-username>/quotes-db
   ```
4. Start testing endpoints directly in Postman or from your test automation project.

---

## 🧾 License

This mock API is provided for **educational and testing purposes only**.  
Feel free to modify the data, extend endpoints, or integrate it with your automation framework.
