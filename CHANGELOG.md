# 🔄 CHANGELOG

>                             `v0.0`: Intento fallido de subir Dashboard.
>                             `v0.1`: Documentación iniciada.  
>                             `v0.2`: ¡Dashboard recuperado!
<p align="center"> `v0.3`: EDA inicial, primeras visualizaciones, proyecto en blanco iniciado, conexión de datos. </p>  

>                             `v0.4`: Diseño de modelo entidad-relación (entidades, relaciones y cardinalidades) e implementación de modelo relacional (Llaves candidatas, foráneas y primarias; Configurar dependencias y restricciones).
>                             `v0.5`: Implementación de almacén de datos. 
>                             `v0.6`: Realización de proceso ETL con Power Query.  
>                             `v0.7`: Configuración del modelo semántico.  
>                             `v0.8`: Implementación de cubo OLAP con DAX.  
>                             `v0.9`: Confección de objetos visuales.  
>                             `v1.0`: Dashboard publicado.  

## 🔄 Detalle de versiones
Insights - Errores Capa 8 - Buenas prácticas.

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
> ...

## 🔧 `v0.2`: ¡Dashboard recuperado! - ¿Cómo lo hice? - ¡Así lo hice! 2025-06-05

Dashboard de rendimiento de campaña promocional enfocado en clientes con tarjeta de crédito aprobada.
<img alt="Presenta gráficos, dinámicos y segmentables, de distribución por categoría, rankings según distintas y resúmenes agregacionales de valores numéricos." Src="docs%2FCaptura%20de%20pantalla%202025-06-05%20225040.png" title="Dashboard de rendimiento de campaña promocional enfocado en clientes con tarjeta de crédito aprobada."/>

<strong><i><p align="justify">¿Cómo lo hice? Aún no lo sé, pero lo descubriré y lo plasmaré aquí.</p></i></strong>

### 💡 ¡Así lo hice! 🛠️ Recuperación manual de archivo .pbix eliminado accidentalmente
#### 🧩 Contexto
<p align="justify">
Durante la configuración de Git en un proyecto con archivos locales ya existentes (incluyendo el archivo Dashboard.pbix), se produjo un error de sincronización entre ramas (master local y main remota). Esto resultó en la eliminación del archivo .pbix desde el directorio visible en PyCharm.

#### ⚙️ Qué sucedió realmente
Aunque el archivo desapareció del explorador de archivos del proyecto, no había sido completamente destruido. PyCharm, al estar vinculado con Git, registró su existencia en el historial de versiones de la rama master (localmente).

#### ✅ Proceso de recuperación desde el historial local (paso a paso).  
Se identifica la rama local master como la que contenía originalmente el archivo `Dashboard.pbix`.  
  
En PyCharm, se accede al historial del proyecto o directamente al historial de Git.  
  
Allí aparece el archivo .pbix como parte de un commit anterior.  
  
Clic derecho sobre el archivo → “Abrir en aplicación asociada”  
  
Esto abrió correctamente el archivo .pbix en Power BI Desktop, confirmando que aún estaba intacto.  
  
Una vez abierto y verificado, el archivo se guardó manualmente en un directorio seguro fuera del proyecto Git.  
  
#### 🧠 Lección aprendida
Git no elimina archivos confirmados sin registro. Incluso si el archivo desaparece del árbol de archivos activo, su rastro permanece en el historial de commits, mientras no se hayan hecho operaciones destructivas como git gc, rebase con pérdida, o borrado del branch.

| Acción             | Qué hace                                                                   | Cambia tu código local    |
|--------------------|----------------------------------------------------------------------------|---------------------------|
| **Fetch**          | Descarga los cambios remotos **sin aplicarlos**                            | ❌ No                      |
| **Pull**           | Descarga los cambios remotos **y los fusiona con tu rama actual**          | ✅ Sí                      |
| **Update Project** | En PyCharm, aplica `Pull` y otras tareas de sincronización con el proyecto | ✅ Sí (depende de ajustes) |

#### 🔐 Cómo evitar esta situación en el futuro
| Recomendación                                                                                              | Detalles                                                                                          |
|------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| 💾 **Haz commits frecuentes**                                                                              | Aunque sea un estado parcial del archivo (`"WIP: progreso del dashboard"`), Git podrá rastrearlo. |
| 🌳 **Evita borrar ramas sin inspeccionarlas**                                                              | Usa `git log` o el panel de Git en PyCharm para ver qué contienen.                                |
| 🧭 **Antes de cambiar de rama o sincronizar con remoto**, guarda archivos críticos fuera del proyecto Git. |                                                                                                   |
| 🗃️ **Explora el historial visual en PyCharm**                                                             | `Git → Show History` puede salvarte si pierdes archivos visualmente pero siguen registrados.      |

Se deja configurado el proyecto con Update Method = Rebase
</p>

## `v0.3`: EDA inicial, primeras visualizaciones, proyecto en blanco iniciado, conexión de datos.    
### Paso 0: Instalar librerías necesarias.  
Paquetes necesarios: numpy, pandas, matplotlib.pyplot, seaborn, pydrive.
En este caso serán instalados desde el instalador de paquetes de Anaconda Navigator.

### 📂 Paso 1: Publicación de la fuente de datos en Google Drive
<p align="justify">
Con el objetivo de mantener la fuente de datos accesible desde la nube, decido <strong>subir el archivo de datos a Google Drive</strong>, lo cual permite su <strong>conexión directa desde Power BI</strong>.  
<strong><i>Se opta por generar un enlace público para lectores.</i></strong>  

#### Enlace de fuente de datos.
Prerrequisito: Instalar PyDrive desde administrador de paquetes Anaconda Navigator.

<a href="https://drive.google.com/file/d/19tBaQ5YbntGYRS3v10yBhrIXQ_uq3Dtc/view?usp=drive_link" target="_blank" rel="noopener noreferrer">
https://drive.google.com/file/d/19tBaQ5YbntGYRS3v10yBhrIXQ_uq3Dtc/view?usp=drive_link
</a>

#### Inicialización y conexión

[CONTINUE]

#### 🔠 Paso 2: Análisis exploratorio de datos y primeras visualizaciones
Prerrequisito: Instalar Plugin para ejecución de Python Notebooks `spyder-notebook`.  
En Spyder no se me hace necesario el uso de un proyecto, por lo que solamente configuraré la carpeta de trabajo.  

Usaré este notebook de referencia.  
<a href="https://github.com/Salayer6/dashboard-promocional-multitienda/blob/main/notebooks/Pandas%20EDA%20Notebook.ipynb" target="_blank" rel="noopener noreferrer">
CAMBIAR https://github.com/Salayer6/dashboard-promocional-multitienda/blob/main/notebooks/Pandas%20EDA%20Notebook.ipynb
</a>
<p align="justify">

Usando la siguiente sentencia, me di cuenta de que existe una variable que, a pesar de estar incompleta, se puede usar en análsis que admitan valores nulos.  
<img alt="se ejecuta el método info() en la variable &#39;data&#39;." Src="docs\Captura%20de%20pantalla%202025-06-08%20170129.png" title="data.info()"/>

Pero vale la pena poner un letrero que lo explicite cada vez.
Como por ejemplo cambiar el nombre de la variable de "ACTIVIDAD" a ACTIVIDAD_95.
>data.rename(columns={"ACTIVIDAD": "ACTIVIDAD_95"}, inplace=True)  # Ej: 95% completitud  
>print(data.columns)

Se detecta que la columna "RANGO ETARIO" se usa como índice. Se procede a eliminar esta configuración.
</p>

>data = data.reset_index()  
>print(data.[Index])



<p align="justify">
Se detecta que la columna "CUPO MÁXIMO" contiene comillas como si fuese un <i>string</i> y además contiene comas como separador de miles.<br>
Se procede a corregir con la siguiente sentencia:<br>
Para la columna 'CUPO MÁXIMO' de la variable 'data': Reemplazar <i>comillas</i> y <i>comas</i> con <i>nada</i>, luego convertir el valor a tipo 'Numérico entero'.
</p>

> data["CUPO MÁXIMO"] = (
>    data["CUPO MÁXIMO"]
>    .astype(str)
>    .str.replace(r'[\,,\"]', '', regex=True)
>    .astype("int64")
>)








#### 📂 Bonus: Comparar con GlueViz.
Hice, en 2 minutos, hice mucho más de lo que logré hice haciendo el EDA Inicial con una instancia de iPython. Incluye funciones de segmentación de datos y plantillas.  
Desarrollar expertise en esta herramienta entregará mucho rendimiento.
¿Se podrá hacer configuración total de las variables en uso?
De serlo, sería la mejor forma para realizar EDA inicial.

<img alt="Segmentaciones destacadas con rojo, plantillas de gráficos." height="576" src="docs\Captura%20de%20pantalla%202025-06-08%20155405.png" title="GlueViz - Visualizaciones rápidas" width="1024"/>

[CONTINUE]


### 📂 Paso 3: 
