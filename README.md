# 📇 Simple GoLang Contacts API

A simple **Golang REST API** to manage contacts (full CRUD) using  
[`gorilla/mux`](https://github.com/gorilla/mux). All logic is in `main.go`, perfect for learning or bootstrapping a new project.

---

## ⚙️ Requirements

| Tool  | Minimum Version | Check with         |
|-------|------------------|--------------------|
| Go    | **1.22**         | `go version`       |
| Git   | Any              | `git --version`    |

> 📝 Tip: Download Go from [go.dev/dl](https://go.dev/dl) and follow official setup instructions.

---

## 📦 Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/<your-username>/contacts-api-go.git
cd contacts-api-go

# Initialize Go module (if needed)
go mod init github.com/<your-username>/contacts-api-go

# Get required packages
go get github.com/gorilla/mux
```

---

## 🚀 Running the API

You can run the app directly or build a binary:

```bash
# Run directly
go run .

# Or build and run
go build -o contacts-api
./contacts-api
```

🟢 Server will start on `http://localhost:8080`

---

## 🔗 Available Endpoints

| Method | Endpoint            | Description              |
|--------|---------------------|--------------------------|
| GET    | `/contato`          | Get all contacts         |
| GET    | `/contato/{id}`     | Get a contact by ID      |
| POST   | `/contato/{id}`     | Create a new contact     |
| PUT    | `/contato/{id}`     | Update a contact by ID   |
| DELETE | `/contato/{id}`     | Delete a contact by ID   |

> 🧪 On startup, 3 Marvel characters are added for testing.

---

## 📥 Example Contact (JSON)

```json
{
  "firstname": "Natasha",
  "lastname": "Romanoff",
  "address": {
    "city": "Stalingrad",
    "state": "Volgograd"
  }
}
```

---

## 🧪 Example Usage (cURL/Postman)

```bash
# Get all contacts
curl -X GET http://localhost:8080/contato | jq

# Get a specific contact (e.g. ID 2)
curl -X GET http://localhost:8080/contato/2 | jq

# Create a new contact
curl -X POST http://localhost:8080/contato/0   -H "Content-Type: application/json"   -d '{"firstname":"Natasha","lastname":"Romanoff","address":{"city":"Stalingrad","state":"Volgograd"}}' | jq

# Update a contact (e.g. ID 1)
curl -X PUT http://localhost:8080/contato/1   -H "Content-Type: application/json"   -d '{"firstname":"Bruce","lastname":"Wayne","address":{"city":"Gotham","state":"NJ"}}'

# Delete a contact (e.g. ID 3)
curl -X DELETE http://localhost:8080/contato/3
```

---

## 🧱 Project Structure

```
contacts-api-go/
├── go.mod
├── go.sum
└── main.go   # Entry point (routes + logic)
```

---

## 💡 Suggested Improvements

- ✅ Replace in-memory slice with a real database (e.g., PostgreSQL, SQLite)
- ✅ Split code into separate layers: handlers, services, repositories
- ✅ Add validation for input data (`go-playground/validator`)
- ✅ Document API using Swagger/OpenAPI
- ✅ Add Docker support (`Dockerfile`, `docker-compose.yml`)
- ✅ Write unit and integration tests

---

## 📄 License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for more information.

---

> Made with ❤️ in Go. Happy coding! 🚀
