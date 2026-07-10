| Concept                              | Why it is Important                                                 | Where in Your Code                             |
| ------------------------------------ | ------------------------------------------------------------------- | ---------------------------------------------- |
| **FastAPI Application**              | Creates the web application and API endpoints.                      | `app = FastAPI()`                              |
| **Database Connection**              | Connects FastAPI to the SQLite database.                            | `create_engine()`, `SessionLocal`, `get_db()`  |
| **SQLAlchemy Models**                | Defines the database tables (`User`, `Admin`).                      | `models.py`                                    |
| **Dependency Injection**             | Automatically provides the database session and authenticated user. | `Depends(get_db)`, `Depends(get_current_user)` |
| **Password Hashing**                 | Stores passwords securely instead of plain text.                    | `hash_password()`                              |
| **Password Verification**            | Checks whether the entered password matches the stored hash.        | `verify_password()`                            |
| **JWT Token**                        | Authenticates users without storing sessions on the server.         | `create_token()`                               |
| **JWT Decode**                       | Verifies the token and extracts user information.                   | `decode_token()`                               |
| **Authentication**                   | Identifies who the current user is.                                 | `get_current_user()`                           |
| **Authorization**                    | Checks whether the user has permission (admin or user).             | `require_admin()`                              |
| **HTTPBearer**                       | Reads the `Authorization: Bearer <token>` header.                   | `security = HTTPBearer()`                      |
| **Protected API**                    | Allows only logged-in users to access specific endpoints.           | `/profile`                                     |
| **Role-Based Access Control (RBAC)** | Gives different permissions to users and admins.                    | `role == "admin"`                              |
| **HTTPException**                    | Returns proper error responses like 401 and 403.                    | `raise HTTPException(...)`                     |
| **Environment Variables**            | Keeps sensitive data such as the secret key secure.                 | `load_dotenv()`, `SECRET_KEY`                  |
| **Form Data**                        | Receives form input from Swagger UI or HTML forms.                  | `Form(...)`                                    |

Authentication flow

Client Login
      │
      ▼
Receive JWT Token
      │
      ▼
Authorization: Bearer <JWT>
      │
      ▼
HTTPBearer
      │
      ▼
Extract Token
      │
      ▼
credentials.credentials
      │
      ▼
JWT Decode
      │
      ▼
Verify User
      │
      ▼
Protected API Access