 # ❗ Resolución de Error en la Instalación con `npm install -y`

 
<p align="center">
  <img src="https://media0.giphy.com/media/v1.Y2lkPTc5MGI3NjExNWMwNmZxd2hxaTB6N3NreDBiYzVsbTAxd2VkcDIxcWpqZ2Fidng3OSZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/11kEuHSQAXXiGQ/giphy.gif" />
</p>


 ## 🛠️ Descripción del Problema:

 Proceso: Intento de inicialización de un proyecto Node.js y posterior instalación de dependencias utilizando `npm` desde PowerShell.

 Error:
 ```powershell
 npm : No se puede cargar el archivo C:\Program Files\nodejs\npm.ps1.
 El archivo no está firmado digitalmente.
 No se puede ejecutar este script en el sistema actual.
 ```

 Causa: PowerShell tiene la política de ejecución configurada como `AllSigned`, lo que impide ejecutar scripts sin firmar como `npm.ps1`.

 ---

 ## 🔍 Diagnóstico del Entorno:

 - Sistema operativo: Windows  
 - Terminal: PowerShell  
 - Política actual: `AllSigned`  

 ---

 ## ✅ Solución Paso a Paso:

 ### 1. Verificar política actual

 ```powershell
 Get-ExecutionPolicy
 ```

 ### 2. Cambiar la política para permitir scripts locales

 ```powershell
 Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
 ```

 - `RemoteSigned`: Permite scripts locales sin firmar.  
 - `Scope CurrentUser`: Aplica solo al usuario actual.

 ---

 ## 🚀 Reintentar Inicialización del Proyecto

 ```powershell
 npm init -y
 ```

 Resultado esperado: creación del archivo `package.json`

 ---

 ## 📦 Instalación de dependencias

 ```powershell
 npm install -y
 ```

 Resultado:
 ```
 up to date, audited 1 package in 490ms
 found 0 vulnerabilities
 ```

 ---

 ## ✅ Conclusión:

 El problema se debió a una restricción de seguridad en PowerShell.  
 Cambiar la política de ejecución permitió ejecutar correctamente `npm`.  
 Siempre realiza estos cambios solo si confías en los scripts que vas a ejecutar.

 ---

 <details>
   <summary>Ver más</summary>

   <div align="center">

   

   Hecho con ❤️ para desarrolladores organizados y productivos.  
   <strong>Elaborado por Jesús Carmona</strong>  
   <strong>Contacto: jesus.carmona966@pascualabravo.edu.co</strong>

   </div>
 </details>




# Documentación de la Estructura del Proyecto Node.js

Esta documentación describe la estructura de carpetas y archivos del proyecto Node.js ubicado en **D:\DevProyectosNode**. La arquitectura del proyecto está orientada a la gestión y ejecución de múltiples proyectos Node.js dentro de un mismo entorno.

## Directorio Raíz: D:\DevProyectosNode\

Este es el directorio principal que contiene todos los archivos y carpetas esenciales para la gestión del entorno de desarrollo y los proyectos Node.js.

### `package.json`:
- **Descripción**: Archivo de manifiesto de Node.js. Define la información del proyecto (nombre, versión, scripts, dependencias, etc.) para las herramientas de gestión del entorno.
- **Importancia**: Fundamental para la gestión de dependencias y la ejecución de scripts a nivel del entorno de desarrollo.

### `README.md`:
- **Descripción**: Archivo Markdown que proporciona una descripción general del proyecto del entorno de desarrollo, instrucciones de uso, información de configuración y documentación relevante.
- **Importancia**: Punto de entrada para cualquier desarrollador que trabaje con este entorno.

### `node_modules\`:
- **Descripción**: Directorio donde se instalan todas las dependencias de los paquetes Node.js definidos en el package.json del directorio raíz.
- **Importancia**: Contiene las bibliotecas y herramientas necesarias para el funcionamiento del entorno de desarrollo.

### `selectorProyectos\`: 🔍 Módulo de selección de proyecto
- **Descripción**: Contiene archivos relacionados con la funcionalidad de selección y gestión de los proyectos Node.js dentro del entorno.
- **Contenido**:
  - `seleccionarProyecto.js`: Lógica principal para seleccionar e interactuar con un proyecto específico.
  - `actualizarPackage.js`: Funcionalidad para actualizar el archivo package.json de un proyecto seleccionado.
  - `interfazUsuario.js`: Código para la interfaz de usuario que permite interactuar con el selector de proyectos.

### `configuraciones\`: ⚙️ Configuraciones globales del entorno
- **Descripción**: Contiene archivos de configuración relevantes para todo el entorno de desarrollo.
- **Contenido**:
  - `rutasBase.js`: Define las rutas base o directorios principales utilizados por el sistema de gestión de proyectos.

### `scripts\`: 🚀 Script principal que lanza el sistema
- **Descripción**: Contiene scripts ejecutables que inician o gestionan el entorno de desarrollo.
- **Contenido**:
  - `index.js`: Punto de entrada principal del sistema de gestión de proyectos.

### `utilidades\`: 🧰 Funciones auxiliares reutilizables
- **Descripción**: Contiene funciones y módulos utilizados por diferentes partes del sistema.
- **Contenido**:
  - `consola.js`: Funciones personalizadas relacionadas con la salida y la interacción con la consola.

### `proyectos\`: 📂 CARPETA QUE CONTIENE TODOS LOS PROYECTOS NODE
- **Descripción**: Este directorio alberga todos los proyectos Node.js individuales gestionados por este entorno de desarrollo.
- **Contenido (Ejemplos)**:
  - `proyecto-calculadora\`:
    - `index.js`: Punto de entrada de la aplicación calculadora.
    - `package.json`: Archivo de manifiesto específico para el proyecto calculadora.
    - (Posiblemente `node_modules\`): Contiene las dependencias específicas de la calculadora.
  - `api-productos\`:
    - `app.js`: Punto de entrada de la API de productos.
    - `package.json`: Archivo de manifiesto específico para la API de productos.
    - (Posiblemente `node_modules\`): Contiene las dependencias específicas de la API.
  - ...otros proyectos: Otros directorios que representan proyectos Node.js individuales.

## Flujo de Trabajo General

Basándonos en la estructura, el flujo de trabajo podría ser el siguiente:

1. El desarrollador ejecuta el script principal del entorno de desarrollo (`node scripts/index.js`).
2. El script `index.js` utiliza el módulo `selectorProyectos` para presentar una interfaz para seleccionar un proyecto.
3. Una vez seleccionado un proyecto, el entorno ofrece funcionalidades para:
   - Ejecutar scripts definidos en el `package.json` del proyecto seleccionado.
   - Gestionar las dependencias del proyecto seleccionado.
   - Acceder a configuraciones globales definidas en la carpeta `configuraciones`.
   - Utilizar las funciones auxiliares de la carpeta `utilidades`.

## Consideraciones

- Este entorno de desarrollo centraliza la gestión de múltiples proyectos Node.js, proporcionando herramientas comunes.
- Cada proyecto dentro de la carpeta `proyectos` es un proyecto Node.js independiente con su propio archivo `package.json` y sus propias dependencias.
- El `package.json` en el directorio raíz contiene dependencias y scripts necesarios para el funcionamiento de las herramientas de gestión del entorno.


