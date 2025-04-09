# Vue Jobs
![image](https://github.com/user-attachments/assets/ee320d68-7756-437b-95e4-0239a0e6c117)
![image](https://github.com/user-attachments/assets/77fdf1d3-891a-4cbf-aadf-5c23bd43ec03)
![image](https://github.com/user-attachments/assets/51cc9ea7-0b92-463a-b804-e3c67ed22413)

Este proyecto es una aplicación web desarrollada con **Vue 3** y **Vite** que permite a los usuarios explorar, agregar, editar y eliminar ofertas de trabajo.

## Tecnologías utilizadas

- **Vue 3**: Framework de JavaScript para construir interfaces de usuario.
- **Vite**: Herramienta de desarrollo rápida para proyectos de frontend.
- **Tailwind CSS**: Framework de CSS para estilos rápidos y personalizables.
- **Vue Router**: Librería para manejar rutas en aplicaciones Vue.
- **Axios**: Cliente HTTP para realizar solicitudes a la API.
- **JSON Server**: Servidor simulado para manejar datos de trabajos.
- **Vue Toastification**: Librería para mostrar notificaciones.
- **PrimeIcons**: Iconos utilizados en la interfaz.
- **Vue Spinner**: Componente para mostrar indicadores de carga.

## Requisitos previos

- **Node.js** (versión 16 o superior)
- **npm** (incluido con Node.js)

## Configuración del proyecto

1. Clona este repositorio:

   ```sh
   git clone <URL_DEL_REPOSITORIO>
   cd vue-crash-course
   ```

2. Instala las dependencias:

   ```sh
   npm install
   ```

## Comandos disponibles

### Ejecutar el proyecto en modo desarrollo

Inicia el servidor de desarrollo con Vite:

```sh
npm run dev
```

Esto abrirá la aplicación en `http://localhost:3000`.

### Iniciar el servidor de datos (JSON Server)

Ejecuta el servidor simulado para manejar los datos de trabajos:

```sh
npm run server
```

Esto iniciará el servidor en `http://localhost:8000`.

### Compilar para producción

Genera una versión optimizada del proyecto:

```sh
npm run build
```

### Previsualizar la compilación de producción

Sirve la compilación de producción localmente:

```sh
npm run preview
```

## Estructura del proyecto

```plaintext
src/
├── assets/          # Archivos estáticos (CSS, imágenes)
├── components/      # Componentes reutilizables de Vue
├── router/          # Configuración de rutas
├── views/           # Vistas principales de la aplicación
├── jobs.json        # Datos de trabajos simulados
├── main.js          # Punto de entrada principal
```

## Notas adicionales

- Asegúrate de que tanto el servidor de desarrollo como el servidor de datos estén corriendo simultáneamente para que la aplicación funcione correctamente.
- Puedes personalizar la configuración de Tailwind CSS en el archivo `tailwind.config.js`.

¡Disfruta desarrollando con Vue Jobs!
