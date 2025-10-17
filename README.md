# learning-git-github
My journey to learn how to use Git/Github

* **Learning Objectives**
Describe the concept of version control and why it is important to use
Utilize the diff and patch commands to automate differentiating and editing files
Explain what Git is and its benefits of use
Install Git on local machine
Utilize Git to create and clone repositories, add code, check the status of code, and commit code

¿Qué es el control de versiones? 
VCS = sistema de control de versiones. Git es un VCS. 
Nos ayuda a retroceder fácilmente cuando se producen errores y a colaborar con otros. 
un VCS nos ayuda a que todos estén en sintonía para ejecutar un proyecto hasta su finalización, dado que en este, cada ingeniero podrá almacenar y compartir el código que crea, permitiendo así dar un seguimiento de las diferentes versiones, deshacer los cambios problemáticos y trabajar juntos de manera eficaz. El Version Control System también ayuda a entender por qué la infraestructura es de tal forma. 

¿Por qué es importante el control de versiones? 

¿Para qué se usa el comando diff? 
## 🔎 Entendiendo `diff`: Una Guía Rápida para Comparar Archivos

La herramienta `diff` es un comando fundamental que analiza dos archivos y muestra las diferencias línea por línea. Es increíblemente útil para rastrear cambios en el código, configuraciones o cualquier tipo de texto. A continuación, se explican los conceptos clave de su funcionamiento.

***

### Formatos de Salida

`diff` puede mostrar los cambios de varias maneras. Las dos más comunes son el formato normal y el formato unificado.

#### 1. Formato Normal (El predeterminado)

Este formato es compacto y usa una notación especial para describir los cambios:

* **`c` (Change)**: Indica que una o más líneas del primer archivo fueron **cambiadas**.
    * *Ejemplo*: `5c5,6` significa que la línea 5 del archivo original fue reemplazada por las líneas 5 y 6 del nuevo archivo.
* **`a` (Add)**: Indica que se **agregaron** líneas nuevas en el segundo archivo.
    * *Ejemplo*: `11a13,15` significa que después de la línea 11 del archivo original, se añadieron las líneas 13 a 15 del nuevo archivo.
* **`d` (Delete)**: Indica que una o más líneas fueron **eliminadas** del primer archivo.

#### 2. Formato Unificado (`diff -u`)

Este es el formato más popular y legible, ya que muestra los cambios junto a su contexto (las líneas que no cambiaron). Es el que usan herramientas como **Git**.

* **Cabecera (`---` y `+++`)**: Identifica los archivos que se están comparando.
    * `---`: El archivo original.
    * `+++`: El archivo nuevo o modificado.
* **Encabezado de Bloque (`@@ ... @@`)**: Indica el inicio de una sección con cambios (conocida como *hunk*).
    * *Ejemplo*: `@@ -2,7 +2,8 @@`
    * `-2,7`: Muestra que, en el archivo original, este bloque empieza en la **línea 2** y tiene una longitud de **7 líneas**.
    * `+2,8`: Muestra que, en el archivo nuevo, este bloque empieza en la **línea 2** y ahora tiene una longitud de **8 líneas**.
* **Prefijos de Línea**: Cada línea en el bloque tiene un símbolo que indica su estado.
    * ` ` (Un espacio): La línea no tiene cambios y está presente en ambos archivos. Sirve de contexto.
    * `+`: Es una línea **agregada** en el nuevo archivo.
    * `-`: Es una línea **eliminada** del archivo original.

***

### ✅ ¿Por Qué Es Importante?

Entender `diff` es esencial en el desarrollo de software. Es el motor detrás de los sistemas de control de versiones como **Git**. Comandos como `git diff` o `git show` usan este mismo formato para que puedas ver con precisión qué modificaste, facilitando la revisión de código y la colaboración.

¿Para qué se usa el comando patch? 

¿Cuál es la diferencia entre Git y GitHub? 
Git es un VCS, GitHub es un servicio que usa a Git para crear repositorios remotos. En Git se puede almacenar el historial de mi código, en GitHub se puede hacer lo mismo que en Git, pero con la posibilidad de colaborar con otros. 

¿Se puede usar Git/Github de la misma manera en Windows y Mac? 

¿Qué es un repositorio? 

¿Qué es un commit? 

Importancia de un portafolio: 
Los portafolios de GitHub dan a las empresas una idea de los proyectos en los que has trabajado y del tipo de código que puedes escribir.  

¿Qué hacen las personas cuando no conocen sobre control de versiones? 
Usualmente la manera primitiva de hacerlo era que cada miembro del equipo guardaba unna copia del documento, sea para mandarle su parte a los demás miembros del equipo, o para mantener un registro del documento que ya funcionaba pero que se le quieren hacer cambios que no se sabe si puedan ser considerados como errores en el futuro. Sin embargo, esto termina siendo conflictivo cuando todos los miembros del equipo hacen estas acciones, ya que no se mantiene un orden ni un registro de quién hizo qué, cuándo, cómo y por qué. 
