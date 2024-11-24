# CHANGELOG

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
