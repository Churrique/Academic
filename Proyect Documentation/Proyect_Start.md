# Proyect_Start

[Descargar este documento](Proyect_Start.md)

## 1. Objetivo de este documento
Este archivo reúne los pasos iniciales para levantar el proyecto de manera ordenada, estableciendo las herramientas recomendadas, la secuencia de instalación y la configuración base para desarrollar la aplicación de control de estudios.

## 2. Herramientas recomendadas

| Herramienta | Propósito | Recomendación |
|---|---|---|
| Git | Control de versiones y colaboración | Obligatorio |
| Node.js | Ejecución del entorno de desarrollo | Versión LTS |
| pnpm | Gestión de dependencias | Recomendado |
| Astro | Framework principal para la web | Obligatorio |
| React | Componentes interactivos | Recomendado |
| Tailwind CSS | Estilos rápidos y consistentes | Recomendado |
| PostgreSQL 16 | Base de datos principal | Obligatorio |
| Prisma | ORM para acceso a datos | Recomendado |
| Docker | Entornos aislados y reproducibles | Opcional |
| Visual Studio Code | Editor principal de desarrollo | Recomendado |
| GitHub | Repositorio remoto | Recomendado |

## 3. Secuencia lógica de instalación
1. Instalar Git.
2. Instalar Node.js LTS.
3. Instalar pnpm.
4. Instalar PostgreSQL 16.
5. Instalar Visual Studio Code y extensiones útiles.
6. Crear el proyecto con Astro.
7. Agregar dependencias de React y Tailwind.
8. Configurar Prisma y la conexión a PostgreSQL.
9. Crear la estructura de carpetas del proyecto.
10. Ejecutar el servidor de desarrollo.

## 4. Pasos detallados

### 4.1 Instalar Git
- Descargar e instalar Git desde la página oficial.
- Verificar con:
  ```bash
  git --version
  ```

### 4.2 Instalar Node.js
- Instalar la versión LTS de Node.js.
- Verificar con:
  ```bash
  node --version
  npm --version
  ```

### 4.3 Instalar pnpm
```bash
npm install -g pnpm
```
Verificar:
```bash
pnpm --version
```

### 4.4 Instalar PostgreSQL 16
- Instalar PostgreSQL 16 en el sistema.
- Crear una base de datos para el proyecto.
- Crear un usuario con permisos de lectura, escritura y creación de estructuras.

### 4.5 Instalar Visual Studio Code
Recomendaciones de extensiones:
- Astro
- Prisma
- Tailwind CSS IntelliSense
- ESLint
- Prettier
- GitLens

### 4.6 Crear el proyecto con Astro
```bash
pnpm create astro@latest academic-app
cd academic-app
pnpm install
```

### 4.7 Agregar React y Tailwind
```bash
pnpm astro add react
pnpm astro add tailwind
```

### 4.8 Configurar Prisma
```bash
pnpm add prisma @prisma/client
pnpm prisma init
```
Luego ajustar el archivo de conexión a PostgreSQL.

### 4.9 Configurar variables de entorno
Crear un archivo .env con valores como:
```env
DATABASE_URL="postgresql://usuario:password@localhost:5432/academic_db"
```

### 4.10 Ejecutar el proyecto
```bash
pnpm dev
```
La aplicación quedará disponible en el puerto por defecto de Astro.

## 5. Estructura sugerida del proyecto
```text
src/
  components/
  layouts/
  pages/
  services/
  styles/
  utils/
prisma/
  schema.prisma
public/
  images/
```

## 6. Recomendaciones de desarrollo
- Mantener la lógica de negocio en servicios separados.
- Separar componentes reutilizables de las vistas.
- Usar rutas claras para módulos como alumnos, profesores, evaluaciones y reportes.
- Centralizar la configuración de idioma y reportes.
- Mantener un flujo de trabajo con ramas en Git.

## 7. Flujo de Git recomendado
```bash
git checkout -b feature/nombre-del-modulo
git add .
git commit -m "Agregar modulo de evaluaciones"
git push origin feature/nombre-del-modulo
```

## 8. Siguiente paso recomendado
Una vez levantado el entorno base, el siguiente paso será implementar los módulos de:
- autenticación y roles,
- gestión de alumnos,
- inscripción y prelación,
- evaluaciones continuas,
- reportes y constancias.
