# 🧠 API CRUD de Usuarios (NestJS)

Este proyecto es un **ejemplo educativo** de una **API CRUD de usuarios en NestJS**, sin base de datos, utilizando un **arreglo en memoria**.  
Ideal para clases, demostraciones o prácticas básicas de backend con NestJS.

---

## 🚀 Requisitos previos

Asegúrate de tener instalado:

- [Node.js](https://nodejs.org/) (v16 o superior)
- [Nest CLI](https://docs.nestjs.com/cli/overview)

Instalar Nest CLI si aún no lo tienes:
```bash
npm i -g @nestjs/cli
```

---

## 🧩 Pasos para crear el proyecto

1. **Crear un nuevo proyecto Nest:**
   ```bash
   nest new crud-usuarios
   ```

2. **Entrar al directorio:**
   ```bash
   cd crud-usuarios
   ```

3. **Crear un módulo CRUD de usuarios:**
   ```bash
   nest g resource usuarios
   ```
   Cuando te pregunte:
   - **Tipo de transporte:** REST API  
   - **¿Deseas CRUD endpoints generados?** Sí  
   - **¿Qué tipo de base de datos usarás?** Ninguna  

   Esto generará la estructura:
   ```
   src/usuarios/
   ├── dto/
   ├── entities/
   ├── usuarios.controller.ts
   ├── usuarios.service.ts
   ├── usuarios.module.ts
   ```

4. **Reemplaza el contenido generado** con los archivos de ejemplo que se encuentran en este repositorio o guía.

---

## 📁 Estructura del código

El CRUD de usuarios funciona sobre un arreglo en memoria que simula una base de datos:

```
src/
├── usuarios/
│   ├── dto/
│   │   ├── create-usuario.dto.ts
│   │   └── update-usuario.dto.ts
│   ├── entities/
│   │   └── usuario.entity.ts
│   ├── usuarios.controller.ts
│   ├── usuarios.service.ts
│   └── usuarios.module.ts
├── main.ts
```

---

## 🧠 Descripción de funcionalidades

| Método | Ruta | Descripción |
|--------|------|-------------|
| **POST** | `/usuarios` | Crear un nuevo usuario |
| **GET** | `/usuarios` | Obtener todos los usuarios |
| **GET** | `/usuarios/:id` | Obtener un usuario por ID |
| **PATCH** | `/usuarios/:id` | Actualizar un usuario existente |
| **DELETE** | `/usuarios/:id` | Eliminar un usuario |

---

## ▶️ Ejecutar el servidor

Iniciar el proyecto en modo desarrollo:
```bash
npm run start:dev
```

El servidor se ejecutará en:
```
http://localhost:3000
```

---

## 🧪 Ejemplos de uso (cURL / Postman)

**Crear un usuario**
```bash
curl -X POST http://localhost:3000/usuarios   -H "Content-Type: application/json"   -d '{"nombre": "Juan", "correo": "juan@mail.com"}'
```

**Listar usuarios**
```bash
curl http://localhost:3000/usuarios
```

**Obtener usuario por ID**
```bash
curl http://localhost:3000/usuarios/1
```

**Actualizar usuario**
```bash
curl -X PATCH http://localhost:3000/usuarios/1   -H "Content-Type: application/json"   -d '{"nombre": "Juan Actualizado"}'
```

**Eliminar usuario**
```bash
curl -X DELETE http://localhost:3000/usuarios/1
```

---

## 💡 Notas importantes

- El arreglo de usuarios está **en memoria**, por lo tanto, los datos se **pierden al reiniciar** el servidor.  
- Puedes extender el ejemplo para guardar los datos en un archivo `.json` o conectar una base de datos real (MongoDB, PostgreSQL, etc.).
- Los DTO (`Data Transfer Objects`) ayudan a **controlar la forma de los datos** que entran y salen de la API.
- Este ejemplo utiliza la arquitectura típica de NestJS:
  - **Controller** → maneja las rutas y peticiones HTTP  
  - **Service** → contiene la lógica del negocio  
  - **Module** → agrupa y organiza las dependencias  

---

## 📚 Recursos recomendados

- 📘 [Documentación oficial de NestJS](https://docs.nestjs.com/)
- 🎓 [NestJS Crash Course - Traversy Media (YouTube)](https://www.youtube.com/watch?v=F_oOtaxb0L8)
- 🧱 [NestJS Awesome List (GitHub)](https://github.com/juliandavidmr/awesome-nestjs)

