# 🧪 API Testing – `/api/v1/kits/:id/products`

Este proyecto contiene casos de prueba realizados para validar el endpoint **`/api/v1/kits/:id/products`**, que permite agregar productos a un kit existente.  
Las pruebas fueron diseñadas y ejecutadas utilizando **Postman**, documentadas en una hoja de pruebas funcionales y con seguimiento de errores en **Jira**.

---

## 📌 Objetivo del Proyecto

Verificar que el endpoint **`POST /api/v1/kits/:id/products`** funcione correctamente al recibir diferentes tipos de datos, garantizando la integridad y comportamiento esperado del sistema ante entradas válidas e inválidas.

---

## 🧰 Herramientas Utilizadas

| Herramienta | Uso |
|--------------|-----|
| **Postman** | Creación y ejecución de pruebas de API |
| **Jira** | Registro y seguimiento de defectos |
| **Excel** | Documentación de los casos de prueba |
| **GitHub** | Control de versiones y publicación del proyecto |

---

## 📂 Estructura del Proyecto

📁 API-Testing-Kits
│
├── 📄 Casos_de_prueba.xlsx
├── 📁 collections/
│ └── api_kits_collection.json
├── 📁 environments/
│ └── api_environment.json
└── README.md

---

## 🧩 Casos de Prueba Principales

| ID | Caso de prueba | Descripción | Datos de entrada | Resultado esperado | Resultado actual | Estado |
|----|----------------|--------------|------------------|--------------------|------------------|---------|
| 1 | Agregar productos existentes al kit | Envía una solicitud POST con `id=2` y una lista válida de productos | `"productsList": [1, 3]` | **200 OK** | 200 OK | ✅ APROBADO |
| 2 | Agregar productos no existentes al kit | Envía una solicitud con IDs de productos inexistentes | `"productsList": [99, 100]` | **400 Bad Request** | 200 OK | ❌ NO APROBADO |
| 3 | Comprobar si el parámetro `id` no acepta letras | Envía un valor alfanumérico en el parámetro `id` | `id="abc"` | **400 Bad Request** | 400 Bad Request | ✅ APROBADO |

---

## 📊 Resultados Generales

- ✅ 2 pruebas aprobadas  
- ❌ 1 prueba no aprobada  
- 📋 1 bug documentado en Jira  

🔗 **Enlace al bug reportado:**  
[https://benjaminveratoledo.atlassian.net/browse/TP-44](https://benjaminveratoledo.atlassian.net/browse/TP-44)

---

## ⚙️ Cómo Ejecutar las Pruebas

### 🔹 Desde Postman
1. Importa la colección `api_kits_collection.json`.  
2. Configura el entorno con la variable:
Base URL: https://api.myproject.demo
3. Ejecuta los requests manualmente o desde **Runner**.

### 🔹 Desde la Terminal (con Newman)
```bash
newman run collections/api_kits_collection.json -e environments/api_environment.json

```

## 🧠 Validaciones Incluidas

Código de estado HTTP (status code).

Validación de campos requeridos.

Manejo de errores para valores inválidos.

Pruebas negativas con datos incorrectos.

## 👨‍💻 Autor

Benjamín Vera
QA Engineer Jr
📍 Chile

🔗 LinkedIn 
www.linkedin.com/in/benjamin-vera-qa

💻 GitHub
https://github.com/Benjamin-vera-QA
