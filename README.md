# Student Management REST API

A beginner-friendly ASP.NET Core 8 Web API demonstrating CRUD operations, model validation, correct HTTP status codes, and Swagger documentation.

## Features

- `GET /api/students` — get all students (`200 OK`)
- `GET /api/students/{id}` — get one student (`200 OK`, or `404 Not Found`)
- `POST /api/students` — create a student (`201 Created`)
- `PUT /api/students/{id}` — update a student (`200 OK`, or `404 Not Found`)
- `DELETE /api/students/{id}` — delete a student (`204 No Content`, or `404 Not Found`)
- Automatic request validation through `[ApiController]` and Data Annotations (`400 Bad Request`)
- Swagger UI for testing endpoints

## Requirements

- .NET 8 SDK
- Visual Studio 2022, Visual Studio Code, or another editor

Check your SDK:

```bash
dotnet --version
```

## Run the project

Open a terminal in the folder containing `StudentManagementApi.csproj`, then run:

```bash
dotnet restore
dotnet run
```

Open Swagger:

- http://localhost:5080/swagger

If you run the HTTPS profile, use the HTTPS URL printed in the terminal.

## Example request bodies

### POST /api/students

```json
{
  "name": "Shivanshu Singh",
  "email": "shivanshu@example.com",
  "age": 20,
  "course": "Computer Science"
}
```

### PUT /api/students/1

```json
{
  "name": "Aarav Sharma",
  "email": "aarav.updated@example.com",
  "age": 21,
  "course": "Computer Science"
}
```

## Test with curl

Get all:

```bash
curl http://localhost:5080/api/students
```

Get one:

```bash
curl http://localhost:5080/api/students/1
```

Create:

```bash
curl -X POST http://localhost:5080/api/students -H "Content-Type: application/json" -d "{\"name\":\"Shivanshu Singh\",\"email\":\"shivanshu@example.com\",\"age\":20,\"course\":\"Computer Science\"}"
```

Update:

```bash
curl -X PUT http://localhost:5080/api/students/1 -H "Content-Type: application/json" -d "{\"name\":\"Aarav Sharma\",\"email\":\"aarav.updated@example.com\",\"age\":21,\"course\":\"Computer Science\"}"
```

Delete:

```bash
curl -i -X DELETE http://localhost:5080/api/students/1
```

## Validation checks

Try sending an empty name, invalid email, or age outside 16–100. ASP.NET Core automatically returns `400 Bad Request` with validation details.

## Important note

This starter project uses an in-memory list so data resets when the API restarts. A database such as SQL Server or SQLite can be added as a future enhancement.

## GitHub upload

1. Extract the ZIP.
2. Open the extracted `StudentManagementApi` folder.
3. Initialize a Git repository or create a new GitHub repository.
4. Upload the project files. Do not upload `bin` or `obj` folders.
5. Suggested repository name: `StudentManagementApi`.
