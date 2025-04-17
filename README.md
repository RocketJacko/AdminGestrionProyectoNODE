<p align="center">
  <img src="https://media.giphy.com/media/hvRJCLFzcasrR4ia7z/giphy.gif" width="80px">
</p>

<h1 align="center">👋 ¡Bienvenido al Selector de Proyectos Node.js!</h1>
<p align="center">
  Automatiza, selecciona y ejecuta tus proyectos de Node desde un solo lugar.
</p>


Un sistema centralizado que te permite seleccionar y ejecutar cualquier proyecto Node.js desde una única consola, sin tener que editar archivos manualmente.

<details>
<summary>🌍 Objetivo Principal</summary>

Tener un sistema reutilizable que te permita explorar, configurar y lanzar fácilmente proyectos Node.js alojados en una carpeta contenedora principal, usando un menú interactivo por consola.

</details>

<details>
<summary>🎯 Finalidad</summary>

Evitar tareas repetitivas como modificar manualmente el `package.json` de cada proyecto.  
Con este selector puedes cambiar dinámicamente el archivo de entrada (`main`) y el script de inicio (`start`) con solo unos clics.

</details>

<details>
<summary>🧠 Recomendaciones</summary>

- Agrupa todos tus proyectos Node.js en una sola carpeta raíz.  
- Asegúrate de que cada proyecto tenga su propio `package.json`.  
- Los nombres de archivos principales deben ser representativos.  
- Usa nombres en español e intuitivos para los scripts.

</details>

<details>
<summary>🧩 Módulos / Temas</summary>

- Exploración de carpetas  
- Detección automática de proyectos Node.js  
- Selección de archivos principales  
- Edición dinámica del `package.json`  
- Reejecución del proyecto seleccionado

</details>

<details>
<summary>🛠️ Primeros Pasos</summary>

1. Crea una carpeta principal (por ejemplo: `D:/MisProyectosNode/`)  
2. Dentro, ubica cada proyecto en su propia subcarpeta  
3. Asegúrate de que cada subcarpeta tenga un `package.json` válido

</details>

<details>
<summary>✅ Validaciones antes de continuar</summary>

- Verifica que tengas Node.js instalado (`node -v`)  
- Verifica que tengas acceso a la terminal/PowerShell  
- La carpeta contenedora debe tener al menos un proyecto válido

</details>

<details>
<summary>⚙️ Estructura del Proyecto</summary>

```bash
SelectorProyectosNode/
├── proyectos/            # Carpeta raíz con todos tus proyectos Node.js
├── selector.js           # Script principal para seleccionar y ejecutar proyectos
├── utils/                # Funciones auxiliares (por ejemplo para leer rutas)
├── README.md             # Documentación del proyecto
├── package.json          # Archivo de configuración del selector
└── tests/                # Pruebas unitarias (en desarrollo)
```
</details> 

<details> 

<summary> 💡 En desarrollo </summary>

🔧 Soporte para configuraciones personalizadas 

📁 Organización por etiquetas o tipos de proyectos  

🧠 Inteligencia para detectar archivos de entrada automáticamente  

💬 CLI con mensajes en varios idiomas  

🔌 Plugin system para extender funcionalidades

</details>

<details> 
  <summary>  🧽 Desinstalación </summary>

Simplemente elimina la carpeta del selector y cualquier alias global creado.  
Puedes reinstalarlo en cualquier momento desde este repositorio.

</details>



![Productividad](https://user-images.githubusercontent.com/74038190/218265814-3084a4ba-809c-4135-afc0-8685d0f634b3.gif)

Hecho con ❤️ para desarrolladores organizados y productivos.  
**Elaborado por Jesús Carmona**  
**Contacto: jesus.carmona966@pascualabravo.edu.co**

</details>

