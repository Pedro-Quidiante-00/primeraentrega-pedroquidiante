
# Guía de Instalación Personalizada de Tailwind CSS

Esta es una guía paso a paso para configurar un proyecto con Tailwind CSS desde cero, utilizando una estructura de carpetas `input` y `public` y un script de `npm` para automatizar la compilación.

## Pasos

### 1\. Requisito Previo

hay que tener **Node.js** instalado en tu sistema.
```bash
node -v
```
-----
### 2\. Inicializar el Proyecto
Antes de instalar cualquier cosa, necesitas crear un archivo `package.json` 

```bash
npm init -y
```

-----

### 3\. Instalar Tailwind CSS

Ahora, con el proyecto inicializado, instala Tailwind CSS y su CLI como dependencias de desarrollo:

```bash
npm install -D tailwindcss @tailwindcss/cli
```

-----

### 4\. Crear Estructura de Carpetas y Archivos

Crea las carpetas y los archivos necesarios para tus estilos:

1.  Crea una carpeta llamada `input`.
2.  Dentro de `input`, crea un archivo vacío llamado `input.css`.
3.  Crea una carpeta llamada `public`.
4.  Dentro de `public`, crea un archivo vacío llamado `assest`, y despues una carpeta que se llame `css` en esta carpeta colocaras un archivo que se llamara `style`.

-----

### 5\. Configurar el Archivo de Entrada

Abre el archivo `input/input.css` y añade la siguiente directiva `@import` para incluir todos los estilos base, componentes y utilidades de Tailwind:

```css
@import "tailwindcss";
```

-----

### 6\. Configurar el Script de Compilación

Abre tu archivo `package.json`. En la sección `"scripts"`, añade un nuevo script llamado `"watch"`. E

```json
"scripts": {
"watch": "npx @tailwindcss/cli -i ./input/input.css -o ./public/style.css --watch"
},
```

-----

### 7\. Enlazar el CSS en tu HTML

Para que tus estilos se apliquen, enlaza el archivo `style.css` generado en tu documento HTML.

Crea un archivo como `index.html` en la raíz de tu proyecto y asegúrate de que la etiqueta `<link>` esté dentro del `<head>` y apunte a la ruta correcta del archivo de salida.

**Ejemplo de `index.html`:**

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Proyecto con Tailwind CSS</title>
    
    <link href="./public/style.css" rel="stylesheet">

</head>
<body>

    <h1 class="text-3xl font-bold underline text-center text-blue-600 p-4">
        ¡Hola, Tailwind!
    </h1>

</body>
</html>
```

-----

### 8\. Ejecutar el Script

Finalmente, para iniciar el proceso de compilación puedes ocupar uno de estos métodos:

#### primer metodo

1.  Abre el archivo `package.json`.
2.  Busca la línea del script `"watch"`.
3.  Haz **clic derecho** sobre `"watch"` y selecciona **Run** (o "Ejecutar").

#### segundo metodo

Ejecuta el siguiente comando en la terminal de tu proyecto:

```bash
npm run watch
```

Ahora, Tailwind comenzará a observar tus archivos y, al abrir `index.html` en el navegador, verás los estilos aplicados.

