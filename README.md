# ExoAPI - Project and User Access Management

This API is designed to manage the projects and user access permissions for ExoAPI. It supports full CRUD functionality for projects, user authentication, and role-based access management with security features. The API follows agile methodologies, and the development was organized using SCRUM through Trello.

## Features

- **Project Management**: Full CRUD (Create, Read, Update, Delete) functionality for managing projects.
- **User Authentication**: JWT-based authentication for secure access control.
- **Error Handling**: Configured responses for error handling across different operations.
- **Security**: Secure user authentication and token-based authorization using JWT.
- **Database Integration**: Connects to SQL Server for storing projects and user data.

## Endpoints

### Projects
- **GET** `/api/projetos`: List all projects.
- **POST** `/api/projetos`: Create a new project.
- **GET** `/api/projetos/{id}`: Retrieve a specific project by ID.
- **PUT** `/api/projetos/{id}`: Update a specific project.
- **DELETE** `/api/projetos/{id}`: Delete a specific project.

### Users
- **GET** `/api/usuarios`: List all users.
- **POST** `/api/usuarios/login`: Authenticate a user and return a JWT token.
- **GET** `/api/usuarios/{id}`: Retrieve a specific user by ID.
- **PUT** `/api/usuarios/{id}`: Update a specific user.
- **DELETE** `/api/usuarios/{id}`: Delete a specific user.

## Technologies Used

- **.NET 6**: Backend framework for API development.
- **SQL Server**: For database management (SSMS used to create and manage the database).
- **JWT Authentication**: Secure user authentication using JSON Web Tokens.
- **Trello**: Used for agile project management with SCRUM methodology.
- **Swagger**: Integrated for API documentation and testing.

## Setup Instructions

### Prerequisites

- **.NET 6 SDK** installed
- **SQL Server** or **SQL Server Management Studio (SSMS)**
- **Node.js** (for dependency management if applicable)

### Steps

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/username/ExoApi-Project-Manager.git
    cd ExoApi-Project-Manager
    ```

2. **Install Dependencies**:
    Restore the .NET project dependencies:
    ```bash
    dotnet restore
    ```

3. **Database Setup**:
    Run the `cria-db.sql` file to create the necessary tables in SQL Server.
    - Ensure you have SQL Server running and connect using SSMS.
    - Execute the SQL script to create tables for `Projects` and `Users`.

4. **JWT Authentication Configuration**:
    The `Program.cs` file contains the JWT authentication setup. Update the key if needed:
    ```csharp
    IssuerSigningKey = new SymmetricSecurityKey(System.Text.Encoding.UTF8.GetBytes("exoapi-chave-autenticacao")),
    ```

5. **Running the API**:
    Start the API locally:
    ```bash
    dotnet run
    ```

6. **Testing**:
    Use **Postman** or **Insomnia** to test the API endpoints. You can also use **Swagger** by navigating to:
    ```
    http://localhost:{port}/swagger/index.html
    ```


## Security

- JWT is used for authentication. Ensure to manage the JWT token securely and store it properly in client applications.
- Sensitive data such as database connection strings and JWT secrets should be stored in environment variables or configuration files that are not exposed.

## Contributing

Feel free to open issues or submit pull requests for improvements. All contributions are welcome!

## License

This project is licensed under the MIT License.