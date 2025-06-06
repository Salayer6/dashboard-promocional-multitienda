# 🔄 CHANGELOG

- `v0.0`: Intento fallido de publicación.
- `v0.1`: Iniciar proceso de desarrollo+documentación como dios manda.
- `v0.2`: ¡Dashboard recuperado! - ¿Cómo lo hice? - ¡Así lo hice!
- `v0.3`: Proyecto en blanco iniciado, conexión de datos, EDA inicial, primeras visualizaciones.  
[...] Aquí estamos.
- `v1.0`: Producto terminado.

# 🔄 Detalle de versiones
## `v0.0` Intento fallido de publicación - 2025-06-04
#### 🔧 Versión 0: Subir archivo `.pbix` - Registro del incidente – Error en sincronización Git - Aprendizaje.
<p align="justify">
Durante la etapa inicial del proyecto, desarrollé un dashboard en Power BI de forma orgánica, sin configurar desde el principio un control de versiones. Una vez terminado, decidí subir el producto final a GitHub como parte de mi portafolio.
</p>

#### 🧨 Lo que ocurrió
Al sincronizar los archivos locales con el repositorio remoto en GitHub, cometí una serie de pasos, lo que provocó la eliminación irreversible de archivos clave, incluyendo el archivo `.pbix` y el dataset original.

#### 🧵 Secuencia problemática.
Se creó un nuevo proyecto en PyCharm, el cual usa por defecto la rama `master`.  
Se configuró el directorio del proyecto apuntando a una carpeta que ya contenía el dashboard final y los archivos de datos.  
Se agregó un `remote`, alias `origin` apuntando a un repositorio de GitHub cuyo branch principal era `main`.  
En ese punto, existía una incompatibilidad entre ramas locales y remotas (`master` vs. `main`) y una discrepancia de archivos: Git no reconocía los archivos existentes como parte del historial de cambios del repositorio remoto.  
Al intentar cambiar al branch `main` no permitía avanzar, por lo que en mi desconocimiento, hice clic primero en `commit` (Gracias a este clic pude recuperar el archivo), y luego hice clic en `Cambiar de branch > remote - main > checkout`. Acción la cual fue directamente a sincronizar los archivos locales según los que estaban en el origen remoto y los eliminó del proyecto local (solamente existía README.md).  
Resultado: se perdieron los archivos originales sin posibilidad de recuperación directa ni mediante software de recuperación de archivos eliminados.

### 🛡️ Cómo evitar este error en el futuro
#### ✅ Buenas prácticas al trabajar con Git y proyectos existentes
| Situación                                                        | Recomendación clara                                                                                                                      |
|------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Quieres versionar archivos ya creados localmente                 | Primero crear el repo en GitHub sin README ni archivos y clonar el repo vacío. Luego mover tus archivos ahí                              |
| Usas IDE como PyCharm                                            | Asegúrate de que la rama local (`master` o `main`) coincida con la del remoto, o crea una nueva rama sincronizada                        |
| Configuras Git en carpeta con archivos previos                   | Realiza primero un `git init`, luego `git add .`, `git commit -m "Inicio"`, y después agrega el remote con `git remote add origin <URL>` |
| Inicias con archivos en la carpeta pero sin control de versiones | Crea backup de seguridad antes de agregar Git, especialmente si hay riesgo de sobrescritura                                              |

#### 🧠 Lección aprendida
> "Git no es solo un respaldo. Es un sistema de control de versiones que, mal usado, puede forzar el borrado de archivos locales si interpreta que no deben estar ahí."

## 🔧 `v0.1`: Iniciar proceso de desarrollo+documentación como dios manda. 2025-06-05
> Markdown language skills: +1!  
> Markdown language skills: +1!  
> Markdown language skills: +1!  
> Markdown language skills: +1!  
> Markdown language skills: +1!  
> Markdown language skills: +1!  
...

## 🔧 `v0.2`: ¡Dashboard recuperado! - ¿Cómo lo hice? - ¡Así lo hice! 2025-06-05
¿Cómo lo hice? Aún no lo sé, pero lo descubriré y lo plasmaré aquí.  
Dashboard
![image](https://github.com/user-attachments/assets/fdf07643-e532-42cc-8f9e-547881ce3bda)

### 💡 ¡Así lo hice! 🛠️ Recuperación manual de archivo .pbix eliminado accidentalmente
#### 🧩 Contexto
<p align="justify">
Durante la configuración de Git en un proyecto con archivos locales ya existentes (incluyendo el archivo Dashboard.pbix), se produjo un error de sincronización entre ramas (master local y main remota). Esto resultó en la eliminación del archivo .pbix desde el directorio visible en PyCharm.

#### ⚙️ Qué sucedió realmente
Aunque el archivo desapareció del explorador de archivos del proyecto, no había sido completamente destruido. PyCharm, al estar vinculado con Git, registró su existencia en el historial de versiones de la rama master.

#### ✅ Proceso de recuperación (paso a paso)
Se identifica la rama local master como la que contenía originalmente el archivo `Dashboard.pbix`.

En PyCharm, se accede al historial del proyecto o directamente al historial de Git.

Allí aparece el archivo .pbix como parte de un commit anterior.

Clic derecho sobre el archivo → “Abrir en aplicación asociada”

Esto abrió correctamente el archivo .pbix en Power BI Desktop, confirmando que aún estaba intacto.

Una vez abierto y verificado, el archivo se guardó manualmente en un directorio seguro fuera del proyecto Git.

#### 🧠 Lección aprendida
Git no elimina archivos confirmados sin registro. Incluso si el archivo desaparece del árbol de archivos activo, su rastro permanece en el historial de commits, mientras no se hayan hecho operaciones destructivas como git gc, rebase con pérdida, o borrado de la rama.

#### 🔐 Cómo evitar esta situación en el futuro
| Recomendación                                                                                              | Detalles                                                                                          |
|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| 💾 **Haz commits frecuentes**                                                                              | Aunque sea un estado parcial del archivo (`"WIP: progreso del dashboard"`), Git podrá rastrearlo. |
| 🌳 **Evita borrar ramas sin inspeccionarlas**                                                              | Usa `git log` o el panel de Git en PyCharm para ver qué contienen.                                |
| 🧭 **Antes de cambiar de rama o sincronizar con remoto**, guarda archivos críticos fuera del proyecto Git. |                                                                                                   |
| 🗃️ **Explora el historial visual en PyCharm**                                                             | `Git → Show History` puede salvarte si pierdes archivos visualmente pero siguen registrados.      |


</p>
