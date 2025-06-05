# Dashboard para análisis de rendimiento [Campaña promocional - Multitienda]
#### Un estudio transversal por Ignacio Salas, Estudiante de Data Science. 

<p align="justify">
Este es un estudio de corte transversal que busca conocer los resultados luego de aplicar una táctica comercial enfocada en fomentar, realizando descuentos, que nuestros clientes usuarios de la tarjeta de crédito de la casa hagan uso del cupo crediticio que se les ha otorgado y, posteriormente, realizar una mirada transversal a lo acontecido para poder conocer: I. El rendimiento de la campaña (Eficacia, eficiencia y costo comparativo). II. El perfil de nuestros clientes en los que nos hemos enfocado.
</p>

## 📊 Herramientas a utilizar
- Power BI Desktop
- [Python + pandas]
- Git y GitHub
- [Fuente de datos: CSV, Google Spreadsheets]

## 🔄 Registro de versiones
#### 🔧 Paso 0: Subir archivo `.pbix` - Registro del incidente – Error en sincronización Git - Aprendizaje.
<p align="justify">
Durante la etapa inicial del proyecto, desarrollé un dashboard en Power BI de forma orgánica, sin configurar desde el principio un control de versiones. Una vez terminado, decidí subir el producto final a GitHub como parte de mi portafolio.
</p>

#### 🧨 Lo que ocurrió
Al sincronizar los archivos locales con el repositorio remoto en GitHub, cometí una serie de pasos, lo que provocó la eliminación irreversible de archivos clave, incluyendo el archivo `.pbix` y el dataset original.

#### 🧵 Secuencia problemática.
Se creó un nuevo proyecto en PyCharm, el cual usa por defecto la rama `master`.  
Se configuró el directorio del proyecto apuntando a una carpeta que ya contenía el dashboard final y los archivos de datos.  
Se agregó un `remote`, alias `origin` apuntando a un repositorio de GitHub cuyo branch principal era `main`.  
En ese punto, existía una incompatibilidad entre ramas locales y remotas (`master` vs `main`) y una discrepancia de archivos: Git no reconocía los archivos existentes como parte del historial de cambios del repositorio remoto.  
Al intentar sincronizar, el sistema de control de versiones interpretó que los archivos locales no estaban versionados correctamente y los eliminó del proyecto local para ajustarse al contenido del remoto (solamente existía README.md).  
Resultado: se perdieron los archivos originales sin posibilidad de recuperación directa.

### 🛡️ Cómo evitar este error en el futuro
#### ✅ Buenas prácticas al trabajar con Git y proyectos existentes
| Situación | Recomendación clara |
|--------------|--------------|
| Quieres versionar archivos ya creados localmente | Primero crear el repo en GitHub sin README ni archivos y clonar el repo vacío. Luego mover tus archivos ahí |
| Usas IDE como PyCharm | Asegúrate de que la rama local (`master` o `main`) coincida con la del remoto, o crea una nueva rama sincronizada |
| Configuras Git en carpeta con archivos previos | Realiza primero un `git init`, luego `git add .`, `git commit -m "Inicio"`, y después agrega el remote con `git remote add origin <URL>` |
| Inicias con archivos en la carpeta pero sin control de versiones | Crea backup de seguridad antes de agregar Git, especialmente si hay riesgo de sobrescritura|

🧠 Lección aprendida
> "Git no es solo un respaldo. Es un sistema de control de versiones que, mal usado, puede forzar el borrado de archivos locales si interpreta que no deben estar ahí."

## 🔄Changelog
- `v0.1`: Documentación iniciada.
- `v0.2`: Proyecto iniciado, conexión de datos, EDA inicial, primeras visualizaciones
- `v1.0`: Dashboard terminado

## 📜 Licencia
Este proyecto está licenciado bajo GNU Affero General Public License v3.0 (AGPL-3.0).

He elegido esta licencia porque creo en la colaboración abierta, pero también en la reciprocidad. Si alguien utiliza este código como base para ofrecer un servicio en línea (por ejemplo, dashboards públicos o soluciones comerciales), esta licencia asegura que las mejoras y adaptaciones sean compartidas con la comunidad bajo los mismos términos.

En otras palabras: puedes estudiar, usar y modificar este software libremente, pero si decides ponerlo en producción como parte de un servicio o producto, deberás también liberar tu versión bajo AGPL.

Esto permite que el conocimiento circule, que se valore el trabajo invertido y que no se privatice lo que nace como un esfuerzo comunitario.

Si tienes alguna duda, necesidad especial  o quieres negociar una licencia alternativa para uso cerrado o comercial, puedes escribirme directamente.
