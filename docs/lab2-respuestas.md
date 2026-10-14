\# Lab 2 — Preguntas de comprobación



\## 1. ¿Por qué es un problema crear un Issue sin criterios de aceptación, aunque la descripción sea clara?



Porque una descripción puede explicar la idea, pero no definir cómo comprobar que el trabajo está terminado. Los criterios de aceptación establecen condiciones concretas y verificables. Sin ellos, el autor y el revisor pueden tener interpretaciones diferentes sobre el resultado esperado.



\## 2. ¿Qué diferencia hay entre `Refs #N` y `Closes #N`?



`Refs #N` hace referencia a un Issue, pero no solicita su cierre automático. Se puede utilizar mientras el trabajo está en curso.



`Closes #N` vincula el cambio con el Issue y permite que GitHub lo cierre automáticamente cuando el Pull Request se integra en la rama predeterminada.



\## 3. ¿Qué ocurre si se ejecuta `git push` directamente a una rama `main` protegida?



Si la regla de protección prohíbe las modificaciones directas, GitHub rechaza el `push`. No significa necesariamente que haya fallado Git: es el sistema de protección funcionando como se ha configurado. El cambio debe enviarse mediante una rama y un Pull Request que cumpla los requisitos establecidos.



\## 4. ¿Qué riesgo existe al aprobar un Pull Request sin revisar los archivos?



Se pueden aceptar errores, cambios incompletos, problemas de seguridad, documentación incorrecta o modificaciones que no cumplen los criterios de aceptación. La aprobación debe basarse en una revisión real de los cambios y de las pruebas pertinentes.



\## 5. Si el revisor solicita cambios después de subir la rama, ¿hay que crear otro Pull Request?



No. Se corrige el código o la documentación en la misma rama y se crea un nuevo commit. Al hacer `git push`, GitHub actualiza automáticamente el Pull Request existente porque sigue asociado a esa rama de origen. Así se conserva la conversación y el historial de revisión.



\## 6. ¿Qué diferencia hay entre Merge commit, Squash and merge y Rebase and merge? ¿Cuál elegir para commits desordenados?



\- \*\*Merge commit:\*\* integra la rama y conserva sus commits, creando un commit de merge.

\- \*\*Squash and merge:\*\* combina los cambios de los commits de la rama en un único commit en la rama de destino.

\- \*\*Rebase and merge:\*\* vuelve a aplicar los commits sobre la rama de destino, creando una secuencia lineal sin un commit de merge.



Para una rama con commits temporales como `wip`, `fix`, `fix2` y `ok ya`, elegiría \*\*Squash and merge\*\*, porque permite integrar el resultado en un único commit más limpio y fácil de entender.



\## 7. ¿Por qué eliminar la rama después del merge no elimina el trabajo realizado?



Porque, después de integrar los cambios, estos forman parte del historial de la rama de destino. Eliminar la rama de trabajo elimina esa referencia a la rama, no los cambios ya integrados en `main`.



\## 8. ¿Qué información mínima debería incluir la descripción de un Pull Request?



Debería incluir:



\- \*\*Summary:\*\* objetivo del cambio.

\- \*\*Changes:\*\* lista de modificaciones realizadas.

\- \*\*Testing:\*\* comprobaciones o pruebas realizadas y sus resultados.

\- \*\*Related Issue:\*\* referencia al Issue relacionado, utilizando `Closes #N` cuando corresponda.



Esta información ayuda al revisor a comprender el cambio y verificar que cumple su objetivo.



\## 9. Si el revisor dice «esto está mal», ¿qué le falta al comentario? Reescribe un ejemplo.



El comentario es demasiado vago. No indica qué está mal, dónde se encuentra el problema ni cómo puede corregirse. Un buen comentario debe ser específico, respetuoso y accionable.



Ejemplo mejorado:



\*\*suggestion:\*\* In `CONTRIBUTING.md`, please add an example showing how to use an optional scope in a Conventional Commit, such as `docs(readme): clarify setup instructions`. This will help new contributors understand the format.



Este comentario identifica el archivo, propone una mejora concreta y explica su utilidad.



\## 10. ¿Qué diferencia hay entre proteger `main` y acordar en el equipo que nadie debe subir cambios directamente?



Una regla de protección de GitHub aplica una restricción técnica al repositorio, de acuerdo con sus opciones y permisos. Un acuerdo del equipo es una norma de trabajo que depende de que las personas la respeten.



Por tanto, el acuerdo ayuda a organizar el trabajo, mientras que la protección puede impedir técnicamente determinadas operaciones directas.



\## 11. ¿Qué diferencia hay entre `issue: (blocking)` y `nitpick: (if-minor)` en Conventional Comments?



`issue: (blocking)` indica un problema que bloquea la integración hasta que se resuelva.



`nitpick: (if-minor)` señala un detalle menor cuya corrección es opcional si realmente es poco importante. La segunda etiqueta comunica que el comentario no debería bloquear el cambio por sí solo.



\## 12. Si el siguiente commit utiliza `feat!:` para cambiar la firma de la función principal de una API pública, ¿qué tipo de cambio SemVer es y por qué?



Es un cambio \*\*MAJOR\*\* de SemVer, porque modifica de forma incompatible una API pública y puede obligar a los consumidores a adaptar su código. El signo `!` en `feat!:` indica un cambio incompatible (\*breaking change\*) según Conventional Commits.



\## 13. ¿Por qué puede ahorrar tiempo al equipo abrir un Draft Pull Request desde el primer commit estructural?



Porque permite compartir pronto el enfoque del trabajo y recibir comentarios antes de completar todos los detalles. El equipo puede detectar problemas de diseño, organización o alcance cuando todavía son más fáciles de corregir. Aunque el autor dedique tiempo a abrirlo antes, puede evitar retrabajo y revisiones tardías.



\---



\## Limitación de la revisión por pares



He realizado esta práctica individualmente. He creado el Issue, la rama de trabajo y el Pull Request; también he solicitado cambios, corregido la documentación en la misma rama y respondido al comentario.



Sin embargo, no he dispuesto de otra persona con permisos para realizar una aprobación independiente. Por ello, no afirmo que se haya completado la aprobación por pares. Esta limitación debe tenerse en cuenta al evaluar el requisito de revisión de la práctica.

