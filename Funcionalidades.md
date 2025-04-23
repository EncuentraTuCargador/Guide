
## 🎯 Funcionalidades Clave

### 🔐 Registro y Autenticación de Usuarios

#### Registro
- **Ruta**: `POST /api/auth/register?rol={user|admin}`
- **Parámetros**:
  - **Body**: `RegisterRequestDTO`  
    ```json
    {
      "nombre": "...",
      "apellido1": "...",
      "apellido2": "...",
      "correo": "...",
      "contrasena": "...",
      "telefono": "...",
      "direccion": "..."
    }
    ```
  - **Query param**: `rol` (valor `user` o `admin`)
- **Flujo Backend (`AuthService.register`)**:
  1. Valida que no exista un usuario con el mismo correo.  
  2. Hashea la contraseña con BCrypt.  
  3. Crea la entidad `User` con el rol indicado y la persiste en la base de datos.  
  4. Genera un JWT que incluye `userId` y `rol`.  
  5. Devuelve un `AuthResponseDTO` con el token, el rol y datos básicos del usuario.

#### Login
- **Ruta**: `POST /api/auth/login`
- **Parámetros**:
  - **Body**: `LoginRequestDTO`
    ```json
    {
      "correo": "...",
      "contrasena": "..."
    }
    ```
- Comprueba credenciales y, si son válidas, devuelve un JWT y el perfil de usuario.

---
