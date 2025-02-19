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
