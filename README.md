
# ScreenMatch Frases con Spring

## Descripción

Este proyecto es una API REST desarrollada en Spring Boot que permite obtener frases aleatorias de personajes de series y películas. Los usuarios pueden acceder a las frases mediante un endpoint y recibir un objeto JSON con los detalles de la frase.

## Tecnologías utilizadas

- **Spring Boot**: Framework principal para el desarrollo de la API.
- **JPA/Hibernate**: Para la gestión de la base de datos.
- **PostgreSQL**: Base de datos utilizada para almacenar las frases.
- **Cors**: Configurado para permitir peticiones desde dominios específicos.

## Endpoints

- **GET /series/frases**: Devuelve una frase aleatoria de una serie o película.

## Instalación

### Requisitos

- Java 17 o superior
- Maven
- PostgreSQL

### Pasos de instalación

1. Clona el repositorio:
    ```bash
    git clone https://github.com/tuusuario/screenmatch-frases-con-spring.git
    ```

2. Configura el archivo `application.properties` con las credenciales de tu base de datos PostgreSQL:

    ```properties
    spring.datasource.url=jdbc:postgresql://${DB_HOST}/screenmatch_frases
    spring.datasource.username=${DB_USER}
    spring.datasource.password=${DB_PASSWORD}
    spring.datasource.driver-class-name=org.postgresql.Driver
    hibernate.dialect=org.hibernate.dialect.HSQLDialect

    spring.jpa.hibernate.ddl-auto=update

    spring.jpa.show-sql=true
    spring.jpa.format-sql=true

    spring.jpa.properties.hibernate.format_sql=true
    ```

3. Ejecuta el proyecto con Maven:

    ```bash
    mvn spring-boot:run
    ```

4. Accede a la API en `http://localhost:8080/series/frases`.

## Estructura del Proyecto

```
src/
├── main/
│   ├── java/
│   │   ├── com/
│   │   │   ├── aluracursos/
│   │   │   │   ├── screenmatch_frases/
│   │   │   │   │   ├── controller/      # Contiene los controladores de la API
│   │   │   │   │   ├── dto/             # Contiene los DTOs
│   │   │   │   │   ├── model/           # Contiene las entidades
│   │   │   │   │   ├── repository/      # Contiene los repositorios JPA
│   │   │   │   │   ├── service/         # Contiene los servicios de la lógica de negocio
│   │   │   │   │   └── config/          # Contiene la configuración de CORS
├── resources/
│   └── application.properties           # Configuración de la base de datos y demás propiedades
```

## Cambios por versión

## [2.0.0] - 2024-11-24

### Added
- Se creó el paquete 'config' y la clase 'CorsConfiguration'.
- Se configuró CORS para permitir solicitudes desde 'http://127.0.0.1:5500'.
- Se habilitaron los métodos HTTP: 'GET', 'POST', 'PUT', 'DELETE', 'OPTIONS', 'HEAD', 'TRACE' y 'CONNECT' en las solicitudes CORS.

## [1.0.1] - 2024-11-24

### Added
- Se creó el paquete 'model' y la clase 'Frase' con los atributos 'id', 'titulo', 'frase', 'personaje', y 'poster'.
- Se implementó el paquete 'dto' y se creó el record 'FraseDTO' con los campos 'titulo', 'frase', 'personaje', y 'poster'.
- Se añadió el paquete 'repository' y la interfaz 'FraseRepository' con un método personalizado para obtener una frase aleatoria utilizando la función 'RANDOM' de la base de datos.
- Se generaron los getters y setters de la clase 'Frase' para permitir el acceso y modificación de los atributos.
- Se creó el paquete 'service' y se implementó la clase 'FraseService' que utiliza el repositorio para obtener una frase aleatoria y devolverla como 'FraseDTO'.
- Se añadió el paquete 'controller' y la clase 'FraseController' con el endpoint 'GET /series/frases' para obtener una frase aleatoria.

## [1.0.0] - 2024-11-23

### Added
- Se añadió configuración para la base de datos PostgreSQL en `application.properties`.
    - **spring.datasource.url**: URL de conexión utilizando variables de entorno (`DB_HOST`, `DB_USER`, `DB_PASSWORD`).
    - **hibernate.dialect**: Configuración del dialecto de Hibernate (`HSQLDialect`).
    - **spring.jpa.hibernate.ddl-auto**: Habilitación de la auto-actualización de esquemas (`update`).
    - **spring.jpa.show-sql**: Activación de logs para consultas SQL (`true`).
    - **spring.jpa.format-sql**: Formato legible para las consultas SQL en los logs (`true`).

### Changed
- Se mejoró la estructura y configuración del archivo `application.properties` para optimizar la conexión con la base de datos.

### Fixed
- No se realizaron cambios relacionados con errores en esta versión.

### Notes
- Esta versión establece la base para la gestión de frases icónicas en el proyecto **ScreenMatch Frases**.
## Licencia

Este proyecto está bajo la Licencia MIT.
