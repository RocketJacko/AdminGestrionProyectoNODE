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

   <summary>Ver más</summary>

   <div align="center">

   

   Hecho con ❤️ para desarrolladores organizados y productivos.  
   <strong>Elaborado por Jesús Carmona</strong>  
   <strong>Contacto: jesus.carmona966@pascualabravo.edu.co</strong>

   </div>




