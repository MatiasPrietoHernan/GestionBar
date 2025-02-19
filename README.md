**IMPORTANTE**

# Para reinstalar las dependencias:
- dotnet restore

# Instrucciones:
- DataLayer: Es la capa de datos, ya están las dependencias: "EntityFrameworkCore.Sqlite", "EntityFrameworkCore.Tools", "EntityFrameworkCore.Design", "EntityFrameworkCore"
  - En esta carpeta van los modelos (Objetos que representan tablas, ejemplo, "Mozos")
  - En esta carpeta van los "Repositorios" que se van a comunicar a la base de datos y van hacer las operaciones correspondientes que necesitemos.
  - Tambien para llevar buenas practicas se utilizarán interfaces (Definición de funciones y variables que heredan las clases) este paso es clave para la inyección de dependencias.
  - Debe realizarse el "AppDbContext" para poder correr la migraciones de base de datos. Recomiendo crear un "AppDbContextFactory" para que no salte error ni de problemas las migraciones
  - Las migraciones recomiendo hacerlas desde la consola del administrador de paquetes:
    - Add-Migration InitialCreate
    - Update-Database  
- LogicLayer: Es la capa lógica de negocio, en esta carpeta haremos los interfaces y métodos para después inyectarlos en "Program.cs" y usarlos desde la PresentationLayer.
- PresentationLayer: Es la capa presentación, que son basicamente los formularios de windows form. Aqui dentro lo estructuraremos así:
  - Windows: Una carpeta para colocar las ventanas principales.
  - SecondWindows: Una carpeta para colocar las ventanas secundarias (Como por ejemplo formularios que se abran de las ventanas principales.)
 
## Esta es la estructura básica del proyecto. Cualquier duda me consultan a mi, sean ordenados y sigan este patrón. 

##Uso del Repositorio con Ramas

**Para evitar que el proyecto se rompa porque alguien mete cambios directamente en main, vamos a seguir estas reglas básicas para trabajar con ramas.**

1️⃣ **Clonar el Repositorio**

2️⃣ **Crear una Nueva Rama para Cada Cambio**

- Nunca trabajes directamente en main. En su lugar, creá una rama nueva:
  - git checkout -b nombre-de-tu-rama
    
3️⃣ **Hacer Cambios y Commits**

Después de hacer tus cambios en el código, agregalos y hacé commit:
- git add .
- git commit -m "Descripción clara del cambio"

4️⃣ **Subir la Rama al Remoto**

- Para que los demás puedan ver tu rama y hacer revisiones:
  - git push origin nombre-de-tu-rama

5️⃣ **Crear un Pull Request (PR)**

Esperar revisión antes de hacer el merge.

6️⃣ **Actualizar main y Sincronizar**

- Antes de empezar nuevas tareas, asegurate de tener la última versión de main:
  - git checkout main
  - git pull origin main

- Si ya tenías una rama pero main se actualizó, mergeala para evitar conflictos:
  - git checkout nombre-de-tu-rama
  - git merge main

📌 Reglas Generales

✅ **No tocar main directamente.**
✅ **Siempre crear una rama nueva para cada cambio.**
✅ **Hacer PRs antes de mergear a main.**
✅ **Sincronizar con main regularmente para evitar conflictos.**

#Si seguís estas reglas, no vamos a tener quilombos con el código. Cualquier duda, preguntá antes de hacer cagadas. 
