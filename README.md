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

Diff sirve para tomar dos archivos o incluso dos directorios y mostrar las diferencias entre ellos. Esto es muy útil ya que evita errores de ojo humano. 

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
    * `>`: Redirige la salida del comando "diff" a un nuevo archivo, p.e.:`diff -u old_file new_file > change.diff`
    * `<`: Redirige el contenido del archivo hacia la entrada estándar, p.e.: `patch cpu_usage.py < cpu_usage.diff`
***

### ✅ ¿Por Qué Es Importante?

Entender `diff` es esencial en el desarrollo de software. Es el motor detrás de los sistemas de control de versiones como **Git**. Comandos como `git diff` o `git show` usan este mismo formato para que puedas ver con precisión qué modificaste, facilitando la revisión de código y la colaboración.

***

### Herramientas `diff` Especializadas y Alternativas Visuales

Además del `diff` estándar, existen herramientas más avanzadas y visuales que facilitan la comparación y fusión de archivos. Estas son algunas de las más populares.

#### 1. `wdiff`: Comparación Palabra por Palabra

The wdiff command highlights the words that changed in a file by color, in addition to working line by line.
Mientras que `diff` se enfoca en líneas completas, **`wdiff`** (word diff) se especializa en mostrar las diferencias **palabra por palabra**. Esto es extremadamente útil para textos largos o párrafos donde un pequeño cambio no justifica marcar toda la línea.

* **`[-palabra-]`**: Muestra una palabra **eliminada**.
* **`{+palabra+}`**: Muestra una palabra **agregada**.

Es la herramienta perfecta para revisar documentos, artículos o cualquier texto donde los cambios son sutiles.

#### 2. `meld`: El Comparador Visual e Intuitivo

**`meld`** es una herramienta gráfica (GUI) que lleva la comparación de archivos a otro nivel. En lugar de leer texto en la terminal, te presenta los archivos uno al lado del otro, resaltando las diferencias con colores.

* **Comparación de 2 y 3 archivos**: Es ideal no solo para ver qué cambió, sino también para resolver conflictos de `merge` en Git, ya que puede mostrar la versión base, tu versión y la otra versión simultáneamente.
* **Edición en vivo**: Permite editar los archivos directamente desde la ventana de comparación para fusionar los cambios de manera sencilla.
* **Comparación de directorios**: También puede comparar carpetas enteras para ver qué archivos han sido añadidos, eliminados o modificados.


#### 3. `KDiff3`: Potencia para Fusiones (Merges)

Al igual que `meld`, **`KDiff3`** es otra potente herramienta visual. Aunque su interfaz puede parecer más densa, es muy apreciada por su robusto motor de fusión de 3 vías.

* **Especialista en Merges**: Su principal fortaleza es ayudar a resolver conflictos de `merge` complejos, mostrando claramente de dónde viene cada línea de código (del archivo base, del tuyo o del otro).
* **Fusión automática**: Incluye una función para intentar fusionar los cambios automáticamente, lo que puede ahorrar mucho tiempo.

#### 4. `vimdiff`: La Solución Integrada en Vim

Para los usuarios del editor de texto **Vim**, **`vimdiff`** es la solución integrada. Es una forma de usar el poder de `diff` sin salir del editor.

* **Vista dividida**: Abre los archivos en ventanas verticales u horizontales, mostrando las diferencias resaltadas con colores.
* **Navegación y fusión con comandos**: Utiliza los comandos nativos de Vim para navegar rápidamente entre las diferencias (`]c` y `[c`) y para mover los cambios de una ventana a otra (`do` y `dp`), haciendo que el proceso de fusión sea rápido y eficiente para quienes dominan el editor.

¿Para qué se usa el comando patch? 
El comando patch toma el archivo generado por diff y aplica los cambios al archivo original. 

***

## 🤝 `diff` vs. `patch`: El Analista y el Aplicador

Hay una diferencia fundamental entre diff y patch, aunque es una de las relaciones más importantes en el control de versiones.

A menudo se usan juntos, pero `diff` es el **analista** (el que encuentra la diferencia) y `patch` es el **aplicador** (el que implementa la diferencia).

Piénsalo con esta analogía: **La Receta y el Cocinero.**

***

### `diff`: El Chef que Escribe la Receta 🕵️‍♂️

El propósito (**"Para Qué"**) de `diff` es **analizar** dos archivos (o dos versiones, como dos commits de Git) y **generar un informe** que describe *exactamente* qué líneas deben agregarse, eliminarse o cambiarse para convertir el Archivo A (original) en el Archivo B (nuevo).

* **Acción:** Compara A con B.
* **Resultado:** Un archivo de texto (un `.diff` o `.patch`) que es la **"receta"** de cómo convertir A en B.

En Git, cuando ejecutas `git diff`, estás pidiendo este informe. Git te muestra el análisis de `diff` en formato unificado (con `+` y `-`) para que *tú* puedas leerlo y entender qué cambió.

### `patch`: El Cocinero que Sigue la Receta 🛠️

El propósito (**"Para Qué"**) de `patch` es **tomar esa receta** (el archivo `.diff` generado por `diff`) y **aplicar esos cambios** a una copia del archivo original (A) para transformarlo exitosamente en el archivo nuevo (B).

* **Acción:** Lee la "receta" (`.patch`) y modifica el Archivo A.
* **Resultado:** El Archivo A se convierte en el Archivo B.

En Git, esta es la lógica que se usa *internamente* todo el tiempo. Cuando haces un `git pull`, `git cherry-pick` o (a veces) `git merge`, Git está usando el concepto de `patch` por debajo: toma los "diffs" (commits) de otra rama y los "aplica" (patches) a tu rama actual para actualizar tus archivos.

***

### Resumen de la Diferencia

| Característica | `diff` | `patch` |
| :--- | :--- | :--- |
| **Propósito** | Encontrar y Reportar Cambios | Aplicar Cambios |
| **Verbo** | Analizar | Ejecutar |
| **Entrada** | Archivo A, Archivo B | Archivo A, Informe de `diff` |
| **Salida** | Informe de `diff` (la "receta") | Archivo B (el "resultado") |

En general, un diff/patch file incluye todos los cambios entre el primer archivo y el segundo, más el contexto necesario para entender los cambios y aplicarlos de vuelta al archivo original (siempre y cuando se utilice -u). 

### Ejemplo de uso de diff y patch: 
1.- Encontraremos la diferencia entre un archivo y otro y redigiremos dicha diferencia a un archivo 
`diff -u disk_usage_original.py disk_usage_fixed.py > disk_usage.diff`
2.- Mostramos el archivo diff generado
`cat disk_usage.diff`
3.- Agregamos el parche (patch) al archivo original
`patch disk_usage.py < disk_usage.diff`
4.- Corroboramos que el código inicial funcione como nosotros buscamos
`./disk_usage.py`

***

## ⚙️ Opciones de Comando Clave: `-r` y `-p1`

A medida que usas `diff` y `patch`, te encontrarás con parámetros (flags) que modifican su comportamiento. Dos de los más importantes son `-r` para `diff` y `-p1` para `patch`.

### `diff -r`: Comparando Directorios Completos 📂

* **¿Para qué se usa?**
    Hasta ahora, hemos visto cómo `diff` compara dos archivos. Pero, ¿qué pasa si queremos comparar dos **directorios** (carpetas) enteros, con todos los archivos y subcarpetas que contienen? Para esto sirve el parámetro `-r` (recursivo).

* **¿Cómo funciona?**
    Al usar `diff -r`, le ordenas a `diff` que "bucee" en las carpetas que le indicas. Hará lo siguiente:
    1.  Comparará archivo por archivo que exista en ambas rutas.
    2.  Te informará qué archivos o directorios existen **solamente** en una de las dos carpetas.
    3.  Te mostrará la salida de `diff` para cada par de archivos que tengan diferencias.

* **Ejemplo de uso:**
    ```bash
    # Compara todo el contenido de la carpeta de la versión antigua
    # contra la carpeta de la versión nueva.
    diff -r proyecto_v1/ proyecto_v2/
    ```

### `patch -p1`: El Adaptador de Rutas 🗺️

* **¿Para qué se usa?**
    Este es un parámetro para el comando `patch`. Su propósito es ayudar a `patch` a **encontrar los archivos correctos** que debe modificar, incluso si el archivo `.diff` (el parche) fue creado en una estructura de carpetas diferente.

* **El Problema:**
    Los parches generados por Git (y otras herramientas) a menudo incluyen prefijos en sus rutas de archivo. Verás esto en las cabeceras `---` y `+++` del parche:

    ```diff
    --- a/src/main.py
    +++ b/src/main.py
    ```

    Si estás en la carpeta raíz de tu proyecto (que contiene la carpeta `src`) e intentas aplicar este parche con `patch < mi_parche.diff`, `patch` buscará una carpeta llamada `a`, luego `src`, y fallará porque esa ruta no existe.

* **La Solución:**
    El parámetro `-p1` le dice a `patch`: "Por favor, **ignora el primer componente** (la primera parte) de todas las rutas de archivo que leas en el parche".

    * `patch` leerá `a/src/main.py`.
    * El `-p1` le hará ignorar el `a/`.
    * Buscará el archivo en `src/main.py`.
    * ¡Lo encontrará y aplicará el parche exitosamente!

* **Ejemplo de uso:**
    ```bash
    # Aplica el parche, ignorando el primer nivel de 
    # prefijo en las rutas (ej. "a/" y "b/")
    patch -p1 < disk_usage.diff
    ```
    Es una práctica casi estándar usar siempre `-p1` al aplicar parches generados por Git.

¿Cuál es la diferencia entre Git y GitHub? 
Git es un VCS, GitHub es un servicio que usa a Git para crear repositorios remotos. En Git se puede almacenar el historial de mi código, en GitHub se puede hacer lo mismo que en Git, pero con la posibilidad de colaborar con otros. 

¿Se puede usar Git/Github de la misma manera en Windows y Mac? 

¿Qué es un repositorio? 

¿Qué es un commit? 

Importancia de un portafolio: 
Los portafolios de GitHub dan a las empresas una idea de los proyectos en los que has trabajado y del tipo de código que puedes escribir.  

¿Qué hacen las personas cuando no conocen sobre control de versiones? 
Usualmente la manera primitiva de hacerlo era que cada miembro del equipo guardaba unna copia del documento, sea para mandarle su parte a los demás miembros del equipo, o para mantener un registro del documento que ya funcionaba pero que se le quieren hacer cambios que no se sabe si puedan ser considerados como errores en el futuro. Sin embargo, esto termina siendo conflictivo cuando todos los miembros del equipo hacen estas acciones, ya que no se mantiene un orden ni un registro de quién hizo qué, cuándo, cómo y por qué. 
