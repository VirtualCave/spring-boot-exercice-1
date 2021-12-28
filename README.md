# spring-boot-exercice-1

Imagina que estamos trabajando en un proyecto para la plataforma de e-commerce de una compañía. Dicha empresa gestiona varias marcas dentro de dicha plataforma.

Partiendo de la siguiente infraestructura como base:

## Base de datos

Base de datos donde tendremos almacenadas las distintas tarifas que gestionaremos en el servicio

### Tabla de tarifas **T_RATES**

| ID | BRAND_ID | PRODUCT_ID | START_DATE | END_DATE   | PRICE | CURRENCY_CODE |
|----| -------- | ---------- | ---------- | ---------- | ----- | ------------- |
| 1  | 1        | 1          | 2022-01-01 | 2022-05-31 | 1550 | EUR           |
| 1  | 1        | 1          | 2022-06-01 | 2022-12-31 | 1850 | USC           |
| 1  | 2        | 1          | 2022-01-01 | 2022-05-31 | 2050 | EUR           |
| 1  | 2        | 1          | 2022-06-01 | 2022-12-31 | 2250 | USC           |
| 1  | 1        | 2          | 2022-01-01 | 2022-05-31 | 2550 | EUR           |
| 1  | 1        | 2          | 2022-06-01 | 2022-12-31 | 2850 | USC           |
| 1  | 2        | 2          | 2022-01-01 | 2022-05-31 | 3050 | EUR           |
| 1  | 2        | 2          | 2022-06-01 | 2022-12-31 | 3250 | USC           |
| ...| ...      | ...        | ...        | ...        | ...  | ...           |

* **ID**: Identificador único de la tarifa
* **BRAND_ID**: Identificador único de la marca
* **PRODUCT_ID**: Identificador único del producto
* **START_DATE**: Fecha de aplicación de la tarifa
* **END_DATE**: Fecha de fin de aplicación de la tarifa
* **PRICE**: Precio del producto sin decimales, los decimales deben extraerse del servicio de moneda
* **CURRENCY_CODE**: ID de la moneda en que está representado el precio

## Integraciones con servicios externos

### Servicio de gestión de monedas

En el fichero *currency-service-api-rest.yml* viene la definición OpenAPI del servicio de monedas que nos dará la información disponible de las monedas dadas de alta en la plataforma.

# ¿Qué se pide?
Se pide crear un servicio basado en spring boot que a se conecte a una BBDD postgres inicializada con los datos contenidos en el script *init-db.sql*, que publique un API rest con las siguientes operaciones:

* Permitir crear una tarifa nueva
* Permitir recuperar una tarifa por id
* Permitir modificar el precio de una tarifa
* Permitir borrar una tarifa por id
* Permitir a partir de una fecha, el identificador del producto y el identificador de la marca, recuperar la tarifa a aplicar con los precios correctamente formateados con los decimales proporcionados por el servicio de monedas

# ¿Qué se valorará?

* Especificación en OpenAPI de la API del micro
* Cobertura de tests
* Uso de diversos tipos de tests
* Optimización de accesos
* Una resolución reactiva se valorará positivamente
