# Respuestas — Git Fundamentals — Lab 1

## 1. Working Directory, Staging Area y Local Repository

El **Working Directory** es la zona donde están los archivos con los que estamos trabajando y donde realizamos modificaciones.

El **Staging Area** es la zona donde se preparan los cambios que queremos incluir en el siguiente commit mediante `git add`.

El **Local Repository** es el historial de commits almacenado localmente en la carpeta `.git`.

Por ejemplo, si creo `docs/ejemplo.md`, inicialmente está en el Working Directory. Después de ejecutar `git add docs/ejemplo.md`, pasa al Staging Area. Finalmente, después de ejecutar `git commit`, el cambio queda registrado en el Local Repository.

## 2. Modificar un archivo sin hacer `git add`

No. Si modifico un archivo pero no ejecuto `git add`, ese cambio no se incluye en el siguiente commit.

Esto ocurre porque el commit toma los cambios que están preparados en el Staging Area, no directamente todos los cambios del Working Directory.

## 3. ¿Por qué Git no muestra carpetas vacías?

Git no realiza seguimiento de carpetas vacías, sino de archivos.

Por eso, para conservar una carpeta vacía dentro del repositorio se puede crear un archivo `.gitkeep` dentro de ella. En esta práctica se utilizó `.gitkeep` para mantener la estructura de directorios.

## 4. ¿Qué es `HEAD`?

`HEAD` es la referencia que indica dónde estamos situados actualmente dentro del historial de Git. Normalmente apunta al commit actual de la rama en la que estamos trabajando.

Cuando cambiamos de rama, `HEAD` pasa a apuntar al commit correspondiente de esa rama.

## 5. `git switch -c` frente a `mkdir`

`git switch -c nombre-rama` crea una nueva rama de Git y cambia inmediatamente a ella.

`mkdir` solamente crea una carpeta en el sistema de archivos; no crea una rama de Git.

En la práctica comprobamos la diferencia al crear `feature/customer-search`: el archivo `customer-search.md` existía en esa rama, pero no aparecía al cambiar a `main`.

## 6. Marcadores de conflicto

En un conflicto de merge, `HEAD` identifica la versión que está actualmente en la rama en la que estamos haciendo el merge.

La línea `=======` separa las dos versiones que entran en conflicto.

La parte posterior indica la versión procedente de la rama que estamos intentando fusionar.

Para resolver el conflicto hay que elegir o combinar el contenido correcto y eliminar todos los marcadores de conflicto.

## 7. ¿Por qué no utilizar `git commit --amend` después de hacer push?

Porque `git commit --amend` modifica el último commit y cambia su historial.

Si el commit ya fue enviado al repositorio remoto, modificarlo puede provocar que el historial local y remoto dejen de coincidir y obligar a reescribir el historial remoto.

Por eso el `amend` se debe utilizar con cuidado y, especialmente en esta práctica, antes de hacer push.

## 8. ¿Qué ocurre si eliminamos `.git`?

Al eliminar `.git` se pierde el repositorio Git local: historial de commits, ramas, configuración del repositorio y demás metadatos de Git.

Los archivos del proyecto que están fuera de `.git` permanecen en el disco.

Por tanto, se pierde el historial de Git, pero no necesariamente el código o los archivos del proyecto.

## 9. Diferencia entre Git y GitHub

**Git** es el sistema de control de versiones que permite registrar cambios, crear ramas, realizar commits y gestionar el historial de un proyecto.

**GitHub** es una plataforma que permite alojar repositorios Git y facilita la colaboración, publicación y gestión de proyectos mediante una interfaz web y otras herramientas.

Git puede utilizarse sin GitHub.

## 10. ¿Por qué no guardar contraseñas reales en `.env` aunque el repositorio sea privado?

Porque las credenciales son información sensible y un repositorio privado no debe considerarse un lugar seguro para almacenar secretos.

Una contraseña podría quedar expuesta por un error de configuración, por compartir el repositorio, por una copia, por un acceso indebido o por aparecer posteriormente en el historial.

Por eso no se deben incluir contraseñas reales, claves ni otros secretos en el repositorio.

## 11. Error `non-fast-forward`

Un error `non-fast-forward` normalmente significa que el repositorio remoto contiene cambios que no están presentes en el historial local.

El primer paso recomendado es actualizar el repositorio local, normalmente mediante:

```text
git pull
```

Después se pueden revisar y resolver los cambios antes de volver a hacer push.

## 12. Conventional Commits

Para añadir un índice utilizaría:

```text
feat: add index
```

Para corregir una restricción incorrecta utilizaría:

```text
fix: correct invalid constraint
```

Para actualizar el README utilizaría:

```text
docs: update README
```

La idea de Conventional Commits es utilizar tipos y mensajes consistentes que describan claramente la naturaleza del cambio.
