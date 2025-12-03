#  Proyecto TIF - Sistema de Facturación

Aplicación académica desarrollada con **Spring Boot**, **JPA/Hibernate** y **MySQL** para gestionar facturas, pagos y medios de pago.  
Incluye un frontend simple en HTML/JS que consume la API REST.

---

##  Tecnologías utilizadas
- Java 21
- Spring Boot 3
- Spring Data JPA / Hibernate
- MySQL (Workbench para DER)
- HTML, CSS, JavaScript (frontend básico)
- Postman (pruebas de API)

---

##  Estructura de entidades
- **Factura**  
  - `id_factura`  
  - `fecha_emision`  
  - Relación 1:1 con **Pago**

- **Pago**  
  - `id_pago`  
  - `fecha_pago`  
  - `total_pago`  
  - Relación N:1 con **MedioDePago**

- **MedioDePago**  
  - `id_medio_de_pago`  
  - `nombre`  
  - Relación 1:N con **Pago**

---

##  Requisitos previos
1. Tener instalado:
   - JDK 21
   - Maven
   - MySQL Server (puerto configurado en `application.properties`)
2. Crear la base de datos:
   ```sql
   CREATE DATABASE tifweb CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
Configurar credenciales en src/main/resources/application.properties:

properties
spring.datasource.url=jdbc:mysql://localhost:3306/tifweb?useSSL=false&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
 Ejecución
Clonar el repositorio:

bash
git clone https://github.com/usuario/proyecto-tif.git
cd proyecto-tif
Compilar y ejecutar:

bash
mvn spring-boot:run
Abrir el frontend en el navegador:

Código
http://localhost:8080/
Endpoints principales
Facturas
GET /facturas-front/traer → Listar todas las facturas

POST /facturas-front/crear → Crear nueva factura

PATCH /facturas-front/editar/{id} → Editar factura existente

Medios de Pago
GET /facturas-front/medios → Listar medios de pago

POST /facturas-front/medios → Crear nuevo medio de pago

 Pruebas con Postman
Ejemplo de creación de factura:

json
{
  "fechaEmision": "2025-12-02",
  "fechaPago": "2025-12-02",
  "medioDePago": "Efectivo",
  "totalPago": 12000
}
DER (Diagrama Entidad–Relación)
El modelo refleja:

Factura ↔ Pago → relación 1:1

Pago ↔ MedioDePago → relación N:1

Generado en MySQL Workbench a partir del script SQL.

Notas
Proyecto académico, orientado a practicar backend con Spring Boot y JPA.

El frontend es básico y sirve para probar la API.

Se recomienda usar Postman para validar los endpoints antes de integrarlos.

Autor
Maximiliano

