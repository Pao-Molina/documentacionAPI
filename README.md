# Proyecto: API de Reserva de libros en Catálogo Digital

* **Estudiante:** Paola Andrea Molina Valderrama*

**URL de la API:** `https://698a814b6c6f9ebe57b9f450.mockapi.io/Fichas`

## 1. Modelo de Datos Diseñado

Se configuró el recurso `Ficha` con la siguiente estructura de datos:

```json
{
        "titulo": "Mistborn",
        "resumen": "resumen 1",
        "bibliografia": {
            "autor": "Brandon Sanderson",
            "publicacion": "2006",
            "idioma": "ingles",
            "formato": [
                "tamaño: de bolsillo",
                "rustica",
                "audiolibro",
                "digital"
            ]
        },
        "genero": [
            "literatura fantastica",
            "aventura"
        ],
        "disponibilidad": false,
        "codigo": "1"
    } 


## 2. Bitácora de Operaciones CRUD (Respuestas de Postman)

### A. Obtener todos los registros (GET)

* **Status Code:** * `200 OK`

**Respuesta de Postman:**

```json
[
{
    "titulo": "Mistborn",
    "resumen": "resumen 1",
    "bibliografia": {
        "autor": "Brandon Sanderson",
        "publicacion": "2006",
        "idioma": "ingles",
        "formato": [
            "tamaño: de bolsillo",
            "rustica",
            "audiolibro",
            "digital"
        ]
    },
    "genero": [
        "literatura fantastica",
        "aventura"
    ],
    "disponibilidad": false,
    "codigo": "1"
} 
] 

### B. Creación de un nuevo registro (POST)

* **Status Code:** `201 Created`
* **Cuerpo enviado en Postman:**

```json
{
    "titulo": "Cien años de soledad",
    "resumen": "resumen 6",
    "bibliografia": {
        "autor": "Gabriel García Marquez",
        "publicacion": "1990",
        "idioma": "Español",
        "formato": [
            "tamaño: de bolsillo",
            "rustica",
            "audiolibro",
            "digital"
        ]
    },
    "genero": [
        "Realismo mágico",
        "aventura"
    ],
    "disponibilidad": true,
    "codigo": "1"
} 

* **Respuesta de Postman:**
```json
{
    "titulo": "Cien años de soledad",
    "resumen": "resumen 6",
    "bibliografia": {
        "autor": "Gabriel García Marquez",
        "publicacion": "1990",
        "idioma": "Español",
        "formato": [
            "tamaño: de bolsillo",
            "rustica",
            "audiolibro",
            "digital"
        ]
    },
    "genero": [
        "Realismo mágico",
        "aventura"
    ],
    "disponibilidad": true,
    "codigo": "9"
}```

### C. Consulta de registro individual (GET)

* **Endpoint:** `/Fichas/2`
* **Status Code:** `200 OK`
* **Respuesta de Postman:** 
```json
{
    "titulo": "El nombre del viento",
    "resumen": "resumen 2",
    "bibliografia": {
        "autor": "Patrick Rothfuss",
        "publicacion": "2007",
        "idioma": "español",
        "formato": [
            "audiolibro",
            "digital"
        ]
    },
    "genero": [
        "novela",
        "alta fantasia"
    ],
    "disponibilidad": true,
    "codigo": "2"
}

### D. Actualización de un registro (PUT)

* **Status Code:** `200 OK`
* **Modificación:** Se modificó la disponibilidad y el idioma

* **Respuesta de Postman:** 
```json
{
    "titulo": "El nombre del viento",
    "resumen": "resumen 2",
    "bibliografia": {
        "autor": "Patrick Rothfuss",
        "publicacion": "2007",
        "idioma": "ingles",
        "formato": [
            "audiolibro",
            "digital"
        ]
    },
    "genero": [
        "novela",
        "alta fantasia"
    ],
    "disponibilidad": false,
    "codigo": "2"
} 

### E. Eliminación de un registro (DELETE)

* **Status Code:** `200 OK`

* **Respuesta de Postman:** 
```json
{
    "titulo": "El rey de hierro",
    "resumen": "resumen 4",
    "bibliografia": {
        "autor": "Maurice Druon",
        "publicacion": "1955",
        "idioma": "Frances",
        "formato": [
            "tamaño: de bolsillo",
            "rustica",
            "digital"
        ]
    },
    "genero": [
        "ficcion"
    ],
    "disponibilidad": true,
    "codigo": "4"
}

### F. Validación de Recurso Inexistente (GET 404)

* **Status Code:** `404 Not found`

* **Respuesta de Postman:** 
```json
"Not found" 

## 3. Resumen de Endpoints y Códigos HTTP

| Acción       | Método | Endpoint    | Código HTTP   |
| :---         | :---   | :---        | :---          |
| Listar todo  | GET    | `/Fichas`   | 200 OK        |
| Crear        | POST   | `/Fichas`   | 201 Created   |
| Ver por ID   | GET    | `/Fichas/2` | 200 OK        |
| Actualizar   | PUT    | `/Fichas/2` | 200 OK        |
| Borrar       | DELETE | `/Fichas/4` | 200 OK        |
| Error        | GET    | `/Fichas/12`| 404 Not Found |





