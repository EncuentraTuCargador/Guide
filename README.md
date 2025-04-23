# Guide


## Arquitectura & Tecnologías

| Capa        | Tecnología / Herramienta                        |
|-------------|-------------------------------------------------|
| **Backend** | Java 17, Spring Boot, Spring Data JPA, MySQL, Maven, Docker Compose, Swagger UI |
| **API**     | REST API (`/api/auth`, `/api/v1/chargers`, `/api/v1/reservations`) |
| **Routing** | OSRM (para distancia y duración), Madrid Open Data (CSV), Google Maps Distance Matrix |
| **Frontend**| React (Create React App), React Router, Fetch API, Tailwind CSS (o estilos inline) |
| **Mapas**   | Google Maps JavaScript API                      |

---

## ⚙️ Requisitos Previos

- **Backend**  
  - Java 17  
  - Springboot  
  - MySQL (o Docker + docker-compose)  
  - Variables en `src/main/resources/application.yml`:  
    ```yaml
    spring:
      datasource:
        url: jdbc:mysql://localhost:3306/Backend_?serverTimezone=UTC
        username: root
        password: TU_PASSWORD
    ```
- **Frontend**
  - Node.js 14+ / npm
  - React
  - HTML5
  - CSS
  - JavaScript 
  - Archivo `.env` en la raíz de `frontend/`:
    ```env
    REACT_APP_API_URL=http://localhost:8080/api
    REACT_APP_GOOGLE_MAPS_API_KEY=TU_GOOGLE_MAPS_API_KEY
    ```

---


### 1. Backend

1. Edita `application.yml` con tus credenciales de MySQL.  
2. (Opcional) Levanta MySQL con Docker:
   ```bash
   docker-compose up -d


# Uso


## Registro

Crea una cuenta (rol user) o un administrador (rol admin).

## Login

Accede con correo y contraseña.

Página de Usuario

Acepta geolocalización.

Visualiza cargadores cercanos en el mapa y en la lista.

Filtra por tipo y pulsa Reservar si está disponible.

Consulta tu historial de reservas en el panel derecho.

Panel de Admin

Visualiza todas las reservas de todos los usuarios

![image](https://github.com/user-attachments/assets/796831ec-aa3f-469c-b008-19d4849046bc)


Image of the App working.
