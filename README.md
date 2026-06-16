# BackPy_ET - Product Service

Microservicio desarrollado en Python Flask para la gestión de productos.

## Tecnologías

* Python 3.11
* Flask
* MariaDB/MySQL
* Docker
* Amazon ECS Fargate
* Amazon ECR
* GitHub Actions

## Funcionalidades

* CRUD de productos
* Consulta por nombre
* Consulta por precio
* Consulta por stock
* Persistencia en base de datos relacional

## Configuración

Variables de entorno:

```env
DB_HOST=
DB_PORT=3306
DB_USER=
DB_PASSWORD=
DB_NAME=products_db
PORT=8082
```

## Docker

Construcción local:

```bash
docker build -t backpy-et .
```

Ejecución:

```bash
docker run -p 8082:8082 backpy-et
```

## Endpoints

### Obtener productos

```http
GET /api/products
```

### Crear producto

```http
POST /api/products
```

### Actualizar producto

```http
PUT /api/products/:id
```

### Eliminar producto

```http
DELETE /api/products/:id
```

## CI/CD

Pipeline automatizado mediante GitHub Actions:

1. Checkout.
2. Configuración de credenciales AWS.
3. Login en ECR.
4. Build Docker.
5. Push automático a ECR.

Archivo:

```text
.github/workflows/deploy.yml
```

## AWS

Servicios utilizados:

* Amazon ECS Fargate
* Amazon ECR
* CloudWatch Logs
* IAM

## Seguridad

* Uso de variables de entorno.
* Gestión de credenciales mediante GitHub Secrets.
* Exposición únicamente del puerto 8082.
* Registro centralizado mediante CloudWatch Logs.

## Observabilidad

La aplicación genera logs visibles desde:

```text
AWS CloudWatch Logs
```

para monitoreo y diagnóstico de errores en producción.
