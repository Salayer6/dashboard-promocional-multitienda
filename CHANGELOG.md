# 🔄 CHANGELOG

>                             `v0.0`: Intento fallido de subir Dashboard. - 2025-06-04  
>                             `v0.1`: Documentación iniciada. - 2025-06-05  
>                             `v0.2`: ¡Dashboard recuperado! - 2025-06-05  

<p align="center">☀️ Aquí vamos 🌖<br> <code> _v0.3_</code>: EDA inicial, primeras visualizaciones, proyecto en blanco iniciado, conexión de datos  - 2025-06-08   </p>  

>                             `v0.4`: Diseño de modelo entidad-relación (entidades, relaciones y cardinalidades)
>                           e implementación de modelo relacional (Llaves candidatas, foráneas y primarias;
>                           Configurar dependencias y restricciones).
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

## 🔧 `v0.2`: ¡Dashboard recuperado! - ¿Cómo lo hice? - ¡Así lo hice! - 2025-06-05  

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

## `v0.3`: EDA inicial, primeras visualizaciones, proyecto en blanco iniciado, conexión de datos - 2025-06-08  
### Paso 0: Instalar librerías necesarias.  
Paquetes necesarios: numpy, pandas, matplotlib.pyplot, seaborn, pydrive.
En este caso serán instalados desde el instalador de paquetes de Anaconda Navigator.

### 📂 Paso 1: Publicación de la fuente de datos en Google Drive
<p align="justify">
Con el objetivo de mantener la fuente de datos accesible desde la nube, decido <strong>subir el archivo de datos a Google Drive</strong>, lo cual permite su <strong>conexión directa desde Power BI</strong>.  
<strong><i>Se opta por generar un enlace público para lectores.</i></strong>  

#### Enlace de fuente de datos.
📌 **Prerrequisito:** Instalar PyDrive desde administrador de paquetes Anaconda Navigator.

<a href="https://drive.google.com/file/d/19tBaQ5YbntGYRS3v10yBhrIXQ_uq3Dtc/view?usp=drive_link" target="_blank" rel="noopener noreferrer">
https://drive.google.com/file/d/19tBaQ5YbntGYRS3v10yBhrIXQ_uq3Dtc/view?usp=drive_link
</a>

#### Inicialización y conexión

[CONTINUE]

#### 🔠 Paso 2: Análisis exploratorio de datos y primeras visualizaciones
📌 **Prerrequisito:** Instalar el plugin `spyder-notebook` para ejecutar notebooks dentro de Spyder.  

🔧 **Configuración inicial:** No se creó un proyecto. Solo se configuró la carpeta de trabajo en Spyder.  

Usaré este notebook de referencia 💜 de **fabsta**  
<a href="https://github.com/fabsta/interesting_notebooks/blob/master/data-sciencetutorial-for-beginners.ipynb" target="_blank" rel="noopener noreferrer">
https://github.com/fabsta/interesting_notebooks/blob/master/data-sciencetutorial-for-beginners.ipynb
</a>

<p align="justify">
Usando la siguiente sentencia, me di cuenta de que existe una variable que, a pesar de estar incompleta, se puede usar en análisis que admitan valores nulos.<br>
<img alt="Se ejecuta el método .info() en la variable &#39;data&#39;." src="outputs%2FEDA%20Visualizations%2FCaptura%20de%20pantalla%202025-06-08%20170129.png" title="data.info()"/>

Pero vale la pena poner un letrero que lo explicite cada vez.
Como por ejemplo cambiar el nombre de la variable de "ACTIVIDAD" a ACTIVIDAD_95.
</p>

>data.rename(columns={"ACTIVIDAD": "ACTIVIDAD_95"}, inplace=True)  # Ej: 95% completitud  
>print(data.columns)

La columna `RANGO ETARIO` estaba configurada como índice. Se revirtió con:

>data = data.reset_index()  
>print(data.index)

Se generó un DataFrame, ordenado cronológicamente, con la clave primaria 'AÑO APERTURA TARJETA'
> data_sorted = data.sort_values(by='AÑO APERTURA TARJETA')  
> print("DataFrame ordenado por 'AÑO APERTURA TARJETA'. Puedes borrar 'data'.")

`data_sorted` será nuestro `DataFrame` de uso.

<p align="justify">
La columna CUPO MÁXIMO tenía comas como separador de miles y estaba encerrada en comillas, por lo que se limpió y convirtió a numérico entero:
</p>

> data_sorted["CUPO MÁXIMO"] = ( 
> data_sorted["CUPO MÁXIMO"]  
>     .astype(str)  
>    .str.replace(r'[\,,\"]', '', regex=True)  
>    .astype("int64")  
>)

#### 🔍 Revisión de tipos de datos
> print(data_sorted[[  
>    "VECES QUE COMPRA EN PROMEDIO AL AÑO",   
>    "CANTIDAD HISTORICA DE ATRASOS EN PAGOS",   
>    "PORCENTAJE DE USO DEL CUPO"  
>]].dtypes)

#### 🧼 Revisión de caracteres ocultos
Con este código se mostrarán caracteres invisibles regularmente.
> for col in data_sorted.columns:  
>    print(repr(col))

#### 🔗 Matriz de correlación
> f, ax = plt.subplots(figsize=(18, 18))  
> sns.heatmap(data_sorted.corr(), annot=True, linewidths=.5, fmt='.1f', ax=ax)  
> plt.show()

<img alt="Muestra una grilla con los valores de correlación que tienen todos los cruces posibles de las variables.<br> Para esta etapa es requisito que todas las variables estén correctamente formateadas." src="outputs\EDA%20Visualizations\Figure%202025-06-08%20220804.png" title="Matriz de correlación"/>

#### 📈 Visualizaciones Exploratorias
> data_sorted['AÑO_STR'] = data_sorted['AÑO APERTURA TARJETA'].astype(str)  
> data_sorted.plot(  
>    x="AÑO_STR", y="CUPO MÁXIMO", kind='line',  
>     color='g', label='CUPO MÁXIMO',  
>     linewidth=1, alpha=0.5, grid=True, linestyle=':'  
>)  
> plt.title('Cupo según año de apertura de la tarjeta')  
> plt.xlabel('AÑO APERTURA TARJETA')  
> plt.ylabel('CUPO MÁXIMO')  
> plt.legend(loc='upper center')  
> plt.show()  

<img alt="Gráfico de líneas que muestra los niveles de cupo crediticio otorgado, organizados por año de apertura de la tarjeta" src="outputs\EDA%20Visualizations\Figure%202025-06-08%20222447.png" title="Gráfico de líneas de Cupo máximo según año de apertura"/>

🧠 Nota: Es importante ordenar previamente los datos por alguna dimensión de tiempo para evitar gráficos desordenados. Por ejemplo:
<img alt="Muestra un gráfico que genera líneas sin sentido porque se plotean en el orden del índice, que es pseudo-aleatorio" src="outputs\EDA%20Visualizations\Figure 2025-06-08 190722.png" title="Gráfico desordenado"/>

#### Scatter Plot: Atrasos vs. Frecuencia de Compra
> data_sorted.plot(  
>     kind='scatter',  
>     x='VECES QUE COMPRA EN PROMEDIO AL AÑO',  
>    y='CANTIDAD HISTORICA DE ATRASOS EN PAGOS',  
>     alpha=0.5,  
>     color='red'  
> )  
> plt.xlabel('Recurrencia de compra')  
> plt.ylabel('Historial de atrasos')  
> plt.title('Relación entre compras y atrasos')  
> plt.show()  

<img alt="Representa como se comportan dos variables numéricas para un mismo individuo" src="outputs\EDA%20Visualizations\Figure 2025-06-08 222938.png" title="Diagrama de dispersión"/>

#### Histograma: Unidades Compradas (Producto A vs Producto B)  
> plt.figure(figsize=(12, 8))  
> data_sorted["UNIDADES COMPRADAS DEL PRODUCTO A"].plot(  
>     kind='hist', bins=50, alpha=0.5, color='blue', label='Producto A'  
> )  
> data_sorted["UNIDADES COMPRADAS DEL PRODUCTO B"].plot(  
>     kind='hist', bins=50, alpha=0.5, color='green', label='Producto B'  
> )  
> plt.title('Comparación de Unidades Compradas')  
> plt.xlabel('Unidades')  
> plt.ylabel('Frecuencia')  
> plt.legend()  
> plt.grid(True)  
> plt.show()  

<img alt="Histograma de comparación entre Producto A y Producto B.Las barras están definidas según la cantidad de productos en oferta llevados y las barras contean la frecuencia de esa cantidad." src="outputs%2FEDA%20Visualizations%2FFigure%202025-06-09%20212444.png" title="# Histograma: 1 Dimensión y su frecuencia"/>

> data_sorted["PORCENTAJE DE USO DEL CUPO"].plot(kind='hist', bins=50, color='blue', alpha=0.7)  
> plt.title('Tipos de deudores')  
> plt.xlabel('Uso del cupo')  
> plt.ylabel('Frecuencia')  
> plt.tight_layout()  # Evita superposición de elementos  
> plt.show()  

<img alt="Histograma que muestra los niveles de uso de cupo y, con las barras, muestran la frecuencia de esa cantidad." src="outputs%2FEDA%20Visualizations%2FFigure 2025-06-09 213655.png" title="# Histograma 2: 1 Dimensión y su frecuencia"/>

> data_sorted["VECES QUE COMPRA EN PROMEDIO AL AÑO"].plot(kind='hist', bins=50, color='green', alpha=0.7)  
> plt.title('Recurrencia de compra')  
> plt.xlabel('Veces promedio que compra al año')  
> plt.tight_layout()  # Evita superposición de elementos  
> plt.show()  

<img alt="Histograma que muestra qué tanto los clientes vuelven a comprar en el año y, con las barras, muestran la frecuencia de esa cantidad." src="outputs%2FEDA%20Visualizations%2FFigure%202025-06-09%20213753.png" title="# Histograma 3: 1 Dimensión y su frecuencia"/>

### Generar visualizaciones filtradas
#### Mostrar aquellos que compren más de 20 veces promedio al año. Solamente hubo cuatro clientes.
> x = data_sorted["VECES QUE COMPRA EN PROMEDIO AL AÑO"]>29  
> data[x]  

<img alt="Tabla filtrada que genera ranking de clientes que compran más de 29 veces promedio al año" src="outputs%2FEDA%20Visualizations%2FCaptura%20de%20pantalla%202025-06-09%20215556.png" title="Ranking de compradores que compraron más de 29 veces promedio"/>  

#### Mostrar aquellos que compren más de veinte veces promedio al año, y que también tenga un historial de atrasos de pagos menor a diez veces. Solamente hubo dos clientes.
> data_sorted[np.logical_and(data_sorted['VECES QUE COMPRA EN PROMEDIO AL AÑO']>29,  
> data_sorted['CANTIDAD HISTORICA DE ATRASOS EN PAGOS'  
> ]<10  
> )  
> ]  

<img alt="Tabla filtrada que genera ranking de clientes que compran más de 29 veces promedio al año" src="outputs%2FEDA%20Visualizations%2FCaptura%20de%20pantalla%202025-06-09%20220201.png" title="Ranking de compradores que compraron más de 29 veces promedio, y que también tenga un historial de atrasos de pagos menor a diez veces"/>

#### Mostrar aquellos que compren más de veinte veces promedio al año, que tenga un historial de atrasos de pagos menor a diez veces, y que también tenga un estado de deuda pagado, o "sin deuda". Se podría decir que es el mejor cliente de la tienda.
> data[(data_sorted['VECES QUE COMPRA EN PROMEDIO AL AÑO']>29) &  
>      (data_sorted['CANTIDAD HISTORICA DE ATRASOS EN PAGOS']<10) &  
>      (data_sorted['ESTADO ACTUAL']=="SIN DEUDA")]  

<img alt="Tabla filtrada que genera ranking de clientes que compran más de 29 veces promedio al año, que tenga un historial de atrasos de pagos menor a diez veces, y que también tenga un estado de deuda pagado, o 'sin deuda'" src="outputs%2FEDA%20Visualizations%2FCaptura%20de%20pantalla%202025-06-09%20221345.png" title="Ranking de compradores que compraron más de 29 veces promedio, que tenga un historial de atrasos de pagos menor a diez veces, y que también tenga un estado de deuda pagado, o 'sin deuda'"/>

### 📌 Conclusión del Paso

<p>
Se realizó una limpieza básica de columnas con formato incorrecto.

Se identificaron tendencias significativas que pueden guiar el modelado posterior.

Las visualizaciones iniciales ayudan a entender patrones de comportamiento en los clientes.
</p>

#### 📂 Bonus: Comparar eficiencia con GlueViz.
<p>
Hice, en 2 minutos, mucho más de lo que logré en comparación cuando hice el EDA Inicial con una instancia de iPython.  
La herramienta incluye plantillas y funciones de segmentación de datos.  
Desarrollar expertise en esta herramienta entregará mucho rendimiento.
¿Se podrá hacer configuración total de las variables en uso?
De serlo, sería la mejor forma para realizar EDA inicial.
</p>
<img alt="Segmentaciones destacadas con rojo, plantillas de gráficos." height="576" src="docs\Captura%20de%20pantalla%202025-06-08%20155405.png" title="GlueViz - Visualizaciones rápidas" width="1024"/>

---
### 📂 Paso 3: Realizar conexión con documento histórico consolidado y subir nuevos registros procesados.

